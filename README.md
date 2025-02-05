# Express.js Route Handler Missing Error Handling for Invalid User ID

This repository demonstrates a common error in Express.js route handlers: the lack of proper error handling for invalid input.  Specifically, the code attempts to parse a user ID as an integer but doesn't handle the case where the ID is not a valid integer. This can lead to unexpected behavior or crashes.

The `bug.js` file contains the buggy code. The `bugSolution.js` file provides a corrected version with improved error handling.

## Bug

The `bug.js` file shows an Express.js route handler that fetches a user by ID.  If the ID is not a valid integer, the `parseInt()` function will return `NaN`, and the subsequent `find()` operation will not find the user.  This results in an implicit error that is not handled gracefully.

## Solution

The `bugSolution.js` file demonstrates how to improve the error handling. It explicitly checks if `parseInt(userId)` results in `NaN` and returns a 400 Bad Request response if it does.  This provides a more robust and user-friendly experience.