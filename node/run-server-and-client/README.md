## How To Run A Server And Client Simultaneously

1. Install npm-run-all on the client
2. Add a script in the client/package.json to run the server
    ```json
    "server": "cd ../server && npm run dev"
    ```
3. Add a script to start the client, and run the "server" script from above
    ```json
    "dev": "run-p server start"
    ```
    This script uses the run parallel command (from npm-run-all) to run the script that starts the server, as well as the script to start the client, at the same time

4. Add a proxy to point to the port that the server will run on. For example, if the server will run on port 3001,
    ```json
    "proxy": "http://localhost:3001"
    ```
5. Run npm run dev