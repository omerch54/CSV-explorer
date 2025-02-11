# CSV-Explorer

## Contributors
Developed by Zeeshan Bhalwani (zbhalwan) & Omer Chaudhry (mchaud11)

## Project Description
CSV-Explorer integrates previously separate front-end (Echo) and back-end (Server) components. The primary development focused on the front-end, now interacting with the API server from Sprint 3. The previous web app (Echo) has been converted to use the React framework for a more responsive and interactive experience.

## Usage

You can use four valid CSV files located in the `data` package within the `backend` directory:

- `rand.csv` – Small file without headers  
- `smallstardata.csv` – Small file with headers  
- `ten-star.csv` – Small file with headers  
- `stardata.csv` – Large file with headers  

### Commands:
1. `mode brief` / `mode verbose` – Toggle between display modes (default: brief).
2. `load_file <filepath>` – Load a CSV file (must be one of the paths above).
3. `view` – Display the loaded CSV file as a table.
4. `search <value> <column index/header>` – Search for a value by column index (zero-based) or header.

### Shortcuts:
- `ctrl + [` – Populate input with `load_file`
- `ctrl + b` – Populate input with `mode brief`
- `ctrl + v` – Populate input with `mode verbose`
- `ctrl + .` – Populate input with `view`
- `ctrl + s` – Populate input with `search`
- `enter` – Submit the command

### Adding a New Command
To add a new command, create a new file in the `api` directory defining its functionality. Then, register it using `registerCommand()`. To remove a command, use `removeCommand()`.

## Design Overview

The project repository contains two main directories:

- `backend`: API server code. See the README in this directory for more details.
- `frontend`: React-based interface for interacting with the backend API.
  - `src` directory includes:
    - `api`: Handles API interactions, mode switching, and command processing.
    - `components`: Contains UI components like input boxes, history, tables, and headers.
    - `App.tsx`: Main application component.
    - `Main.tsx`: Entry point for rendering the React app.
  - `styles`: CSS styles for the web app.
  - `tests`: Contains DOM and integration tests.

## Tests
The `frontend/src/tests` directory includes:

- `integration.dom.test.tsx` – DOM integration tests
- `main.unit.test.tsx` – Unit tests
- `mocks.dom.tsx` – Tests using mocked API and command responses

To run tests, ensure the server is running (`Server.java`), then navigate to the `frontend` directory and run `npm test`. The `mocks.dom.tsx` tests do not require the server to be running.

## Errors and Bugs
While various API errors exist, we focus on handling common ones in a user-friendly manner:

- `error_bad_request` – Invalid request format.
- `error_datasource` – Data source unavailable (e.g., missing file, API error).
- `error_internal` – Unexpected system error (logged for developer review).
- `error_bad_json` – Malformed JSON request.

## Running the Program
1. Start the backend server:
   - Navigate to `backend/src/main/server`
   - Run `Server.java`
   - Access `localhost:3232` for API endpoints (details in backend README)
2. Start the frontend:
   - Navigate to `frontend`
   - Run `npm install`
   - Start with `npm start` or `npm run dev`
3. Run tests:
   - Start `Server.java`
   - Navigate to `frontend`
   - Run `npm test`

CSV-Explorer makes it easy to interact with CSV files through a streamlined interface with powerful search and command capabilities.

