# Express.js Route Handler Missing Error Handling for Invalid User ID

This repository demonstrates a common error in Express.js route handlers: missing error handling for invalid input.  Specifically, this example shows a route that fetches a user by ID.  If the provided ID is not a valid integer, the code will throw an error.

## Bug

The `bug.js` file contains the problematic code.  It attempts to parse the user ID as an integer without checking if the parsing was successful.  If the ID is not a number, `parseInt(userId)` will return `NaN`, leading to a potential crash or unexpected behavior.

## Solution

The `bugSolution.js` file provides a corrected version.  It includes error handling to check if `parseInt(userId)` returns a valid integer.  If not, it returns an appropriate error response.

## How to reproduce

1. Clone this repository.
2. Run `npm install express`
3. Run `node bug.js` and make a request to `/users/abc` (or any non-numeric ID).  You should see a server error.
4. Run `node bugSolution.js` and make the same request.  You should now see a 404 error response.