# MetroFlats UK – Fixed Version

This folder contains the fixed, production-ready version of the MetroFlats UK Property Estimator & Feasibility web app.

## Contents
- `index.html` – Main frontend (all logic, UI, and integration)

## Notes
- All old/duplicate HTML files have been removed from the root.
- Backend files remain in the root for reference or API key management.

## Frontend Usage

1. Open `index.html` in your browser for the full app experience. All logic runs client-side, including property analysis, map integration, and AI chat (via OpenAI API).
2. The app uses encrypted API keys for Google Maps and OpenAI. These are decrypted in-browser using Pyodide (Python in WebAssembly).

## Backend (API Key Server)

To serve API keys securely (for development or production):

1. Install Node.js and dependencies:
	```
	npm install express
	```
2. Set your API keys as environment variables:
	- `GMAPS_KEY` for Google Maps
	- `OPENAI_KEY` for OpenAI
3. Start the server:
	```
	node server.js
	```
4. The server exposes `/api/keys` (CORS-restricted) for frontend use if you wish to fetch keys dynamically (not required for encrypted keys).

## Encrypting API Keys for Frontend

Use `encrypt_keys.py` to generate encrypted keys for embedding in the frontend:

1. Run:
	```
	python encrypt_keys.py
	```
2. Follow prompts to enter your API keys. The script outputs encrypted strings to paste into the frontend code.

## Project Structure

- `index.html` – Main frontend (all logic, UI, and integration)
- `server.js` – Node.js backend for serving API keys (optional)
- `encrypt_keys.py` – Script to encrypt API keys for frontend use
- `main.py` – (Not used by frontend; placeholder)
