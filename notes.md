# My Troubleshooting Notes

Format: what went wrong -> what fixed it -> why (in my own words)

---

## Git: "configure your user.name and user.email"
**Problem:** VS Code refused to commit, showed a popup about user.name/user.email.
**Fix:** Ran these once in the terminal:
  git config --global user.name "Krishna Nakka"
  git config --global user.email "knakka4@gmail.com"
**Why:** Git attaches an author to every commit. This is a one-time setup per machine, not per project.

---

## .env file saved as .env.txt
**Problem:** My API key wasn't loading. Turned out VS Code/Windows had saved the file as ".env.txt" instead of ".env".
**Fix:** Renamed it in VS Code Explorer, removing ".txt" completely.
**Why:** The dotenv library looks for a file named exactly ".env" — a hidden extension trick on Windows can silently add ".txt".

---

## Empty Python file, no output, no error
**Problem:** Ran test_connection.py, got zero output — no answer, no error.
**Fix:** Checked with `type test_connection.py` in terminal — file was empty. Re-saved the code properly (Ctrl+S) and confirmed with `type` again before rerunning.
**Why:** An empty .py file runs "successfully" and prints nothing. Silence isn't always success — always verify file contents when output looks wrong.

---

## Gemini model "gemini-2.0-flash" not found (404)
**Problem:** google.api_core.exceptions.NotFound: model no longer available.
**Fix:** Google's error message itself named the replacement model (gemini-3.6-flash). Also had to switch from the old `google-generativeai` package (deprecated) to the new `google-genai` package.
**Why:** AI APIs update model names/SDKs frequently. When a model 404s, check the error text first — it often tells you the new name directly.

---

## PowerShell heredoc (@' ... '@) syntax error
**Problem:** Tried to write a file directly from the terminal using a multi-line here-string, got a syntax error.
**Fix:** Abandoned the terminal approach, wrote the file directly in the VS Code editor instead and saved with Ctrl+S.
**Why:** Pasting multi-line here-strings into some terminals (VS Code's integrated one included) can break formatting. The editor is more reliable for writing file content.

---

## (Add new entries below as they come up)