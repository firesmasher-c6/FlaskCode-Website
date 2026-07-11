# Flask Code

A desktop and terminal tool for transforming an AI into an AI agent that can assist with code-oriented workflows. Flask Code is only tested on Windows and supports Gemini, OpenRouter, and Groq providers, plus a Tkinter-powered GUI with markdown-style output, terminal commands, and API key slot management.

## Features

- Terminal and GUI chat interfaces
- Tkinter-based desktop chat window and dialogs
- Multi-provider support: Gemini, OpenRouter, Groq
- API key slot management via `.apikeys` and per-user `.apikeyml` settings
- Persistent user login / PIN access
- Commands for account registration, model switching, and file operations
- Lightweight Python implementation with YAML-backed settings

## Requirements

- Python 3.10+ recommended
- `PyYAML>=6.0`
- Tkinter support for GUI mode

> This project is only tested on Windows.

> On Windows, Python usually includes Tkinter. On Linux, install your distribution's `python3-tk` package.

## Installation

1. Clone or download this repository.
2. Install dependencies:

```bash
python -m pip install -r requirements.txt
```

3. Copy `.apikeys_example` to `.apikeys` and add your real API keys.

```bash
copy .apikeys_example .apikeys
```

4. Make sure `.apikeys` is not committed to Git; it is already ignored by `.gitignore`.

## Configure API Keys

Add the scripts `flaskc.ps1`, `flaskcode.ps1`, and `flck.ps1` to your PATH so you can launch the app from any PowerShell session. Also add `bin/launch.py` to PATH if you want a quick way to launch the GUI from the command line.


Open `.apikeys` and replace the placeholder values with your API keys:

```yaml
key_1: "YOUR_GEMINI_API_KEY"
key_2: "YOUR_SECOND_KEY_OR_PLACEHOLDER"
key_3: "YOUR_OPENROUTER_OR_FALLBACK_KEY"
```

- `key_1`, `key_2`, `key_3` are the slot names used by the application.
- The application can also read an environment variable named `GEMINI_API_KEY`.

## Running the App

- Terminal interface:

```bash
python main.py
```

- GUI interface:

```bash
python user-interface.py
```

## Useful Commands

From the terminal chat prompt, use commands like:

- `/register-as` — create a user account via Tkinter popup
- `/login-as <name> <password>` — log in as an existing user
- `/apikey <1|2|3>` — select which API key slot to use
- `/model <name>` — switch provider between `gemini`, `openrouter`, and `groq`
- `/logout` — log out
- `/exit` — quit the app

The app also supports hidden commands starting with `.` for advanced flows.

## Security

- Do not commit `.apikeys` to Git.
- Keep `.apikeys` private and never share your real API keys.
- Use `.apikeys_example` as a template for new installations.

## Files to Know

- `main.py` — terminal app entry point
- `user-interface.py` — Tkinter GUI entry point
- `.apikeys` — secret API key storage (ignored by git)
- `.apikeys_example` — example API key template
- `requirements.txt` — Python dependency list
- `apikey_settings.py` — per-user provider and key selection settings

## License

Include a license file in your repository if you want to release this project publicly.
