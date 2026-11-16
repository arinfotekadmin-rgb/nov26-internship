# 11. Troubleshooting and Debugging

## Node command not recognised
- Reopen the terminal.
- Check that Node.js is on PATH.
- Reinstall the LTS installer if needed.

## npm install fails
- Read the first error, not only the final line.
- Check internet, proxy and Node.js compatibility.

## Cannot GET /api/students
- Check the URL and HTTP method.
- Confirm the router is registered with `app.use`.
- Confirm the router export and import paths.
- Restart the server.

## req.body is undefined
- Add `app.use(express.json())` before routes.
- Send `Content-Type: application/json`.

## MySQL ECONNREFUSED
- Check the MySQL Windows service.
- Confirm host and port.

## MySQL access denied
- Check username, password and host-specific grants.
- Test the account in Workbench.

## Unknown database
- Check that the database exists and matches `DB_NAME`.

## Debugging sequence
1. Reproduce the error.
2. Read the full terminal message.
3. Identify Node, Express, network or MySQL as the failing layer.
4. Run the SQL independently in Workbench.
5. Test the API with Postman.
6. Fix one cause at a time and retest.
