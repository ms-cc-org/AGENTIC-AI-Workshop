## Troubleshooting Guide (All Notebooks, Live Mode)

Each entry below covers a common failure you may hit during the workshop: **the error you see**, then **how to fix it**.

### 1. Wrong API key

**Error:** `AuthenticationError: Error code: 401 - {'type': 'error', 'error': {'type': 'authentication_error', 'message': 'API key is invalid.'}}`

**Fix:** Your key is either mistyped or expired. Click the key icon in the Colab sidebar, delete the secret, paste a fresh key from console.anthropic.com, toggle Notebook Access back on, and re-run from the top.

### 2. Missing API key (env var unset or Colab secret not created)

**Error:** `TypeError: "Could not resolve authentication method. Expected one of api_key, auth_token, or credentials to be set. Or for one of the 'X-Api-Key' or 'Authorization' headers to be explicitly omitted"`

**Fix:** The SDK can't find any key at all. In Colab: click the key icon, add a secret named exactly `ANTHROPIC_API_KEY`, turn on Notebook Access, then re-run from the top. If running locally, `export ANTHROPIC_API_KEY=sk-ant-...` in your terminal.

### 3. Wrong model name

**Error:** `NotFoundError: Error code: 404 - model: claude-3-opus-13579`

**Fix:** That model ID doesn't exist. Check for typos. The workshop uses `claude-haiku-4-5-20251001`. Fix the `MODEL = ` line in the Setup cell and re-run.

### 4. Rate-limit error

**Error:** `RateLimitError: Error code: 429 - Number of request tokens has exceeded your per-minute rate limit`

**Fix:** You've hit Anthropic's per-minute quota. Wait 60 seconds and re-run the cell. If the whole room hits it at once, stagger: half the room runs, then the other half. Free-tier keys have lower limits than paid keys.

### 5. Tool call returns garbage / unusable data

**Error:** The agent prints `observe: xy GARBAGE DATA ...` (or whatever the tool returned), then either retries the tool until `max_steps` stops it, or gives up with a message like "I received malformed data."

**What's happening:** The agent loop didn't crash -- the `try/except` in `run_agent` caught it. The model saw the garbage as a tool result and decided what to do. This is the design working: the agent observes and reacts. If it loops, `max_steps` is the safety net.

### 6. Tool function raises an exception (crash mid-loop)

**Error:** The agent prints `observe: ERROR: HTTPSConnectionPool: Max retries exceeded...` (or whatever the exception was), then continues to the next step.

**What's happening:** Look at `run_agent`: `except Exception as e: result = f'ERROR: {e}'`. The loop catches tool exceptions, turns them into an error string, and feeds that back to the model as the tool result. The agent doesn't crash; it sees the error and decides what to do next. This is why every tool call is wrapped in try/except.

### 7. Empty user input (TASK left blank)

**Error (mock mode):** The agent replies with `[mock reply to]` -- an empty echo. No crash, but no useful output.

**Error (live mode):** `BadRequestError: Error code: 400 - {'type': 'error', 'error': {'type': 'invalid_request_error', 'message': 'messages.0: user messages must have non-empty content'}, 'request_id': .....`

**Fix (mock):** Mock mode doesn't validate input -- it just echoes. Type a real task into the TASK field and re-run. **Fix (live):** The API rejects empty messages. Put a real question in the TASK field and re-run the cell.

### 8. Network timeout mid-agent-loop

**Error:** `APITimeoutError: Request timed out or interrupted. This could be due to a network timeout, dropped connection, or request cancellation.`

**Fix:** Colab lost its connection to Anthropic mid-request. Check your WiFi. If it happens repeatedly, the API may be slow -- wait a minute, then re-run. The agent loop does not auto-retry; re-running the cell restarts from the beginning.

### 9. PROVIDER set to "anthropic" but the live-model cell was never run (NB1 only)

**Error:** `RuntimeError: PROVIDER is not 'mock'. Run the following 'Enable a live model' cell just below Setup, then re-run from the top.`

**Fix:** You changed PROVIDER to `'anthropic'` but skipped the cell that defines the Anthropic backend. Run that cell (the one right below Setup titled "Enable a live model"), then Runtime > Run All.

### 10. PROVIDER set to an unsupported value (NB2, NB3, NB4)

**Error:** `ValueError: PROVIDER must be 'mock' or 'anthropic'; got 'openai'`

**Fix:** This workshop only supports `mock` and `anthropic`. Change PROVIDER back to one of those two values and re-run.

### 11. Agent hits max_steps (runaway loop)

**Error:** The agent prints each tool call step, then returns `"Stopped: hit max_steps."` as the final answer instead of a real response.

**What's happening:** The agent kept calling tools and never decided it was done. `max_steps` is the safety net that stopped an infinite loop. In mock mode this means the mock script had too many tool entries and no "final". With a live provider, the model may need a clearer task or a higher `max_steps` limit.

### 12. sentence-transformers fails to load (NB3, NB4 optional)

**Error:** `RuntimeError: WARNING: REAL EMBEDDINGS UNAVAILABLE ... sentence-transformers failed to load.`

**Fix:** Run `%pip install sentence-transformers` in a new cell, then Runtime > Restart Runtime, then re-run all cells from the top. If it still fails, check that you're on a standard Colab runtime (not a TPU runtime).
