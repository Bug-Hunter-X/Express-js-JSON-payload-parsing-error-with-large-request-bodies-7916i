# Express.js JSON Payload Parsing Error with Large Request Bodies

This repository demonstrates a common issue encountered when working with Express.js and large JSON payloads. The problem arises when the request body exceeds the default size limit imposed by the body-parser middleware.

## Bug Description
The Express.js server fails to properly parse the JSON data received in the request body if the size exceeds the default limit. This results in an error, preventing the server from processing the request correctly.

## Solution
To resolve this issue, increase the body-parser's limit using `express.json({ limit: 'YOUR_LIMIT' })` where `YOUR_LIMIT` can be expressed in bytes, kilobytes (kb), megabytes (mb), or gigabytes (gb). For instance, to allow up to 100mb of request body data you would use `express.json({ limit: '100mb' })`.

## Steps to Reproduce
1. Clone the repository.
2. Run `npm install` to install the dependencies.
3. Run `node bug.js` to start the server.
4. Send a POST request with a JSON payload larger than the default limit to `/data`.
5. Observe the error response.
6. Run `node bugSolution.js` to start the server with the updated body-parser limit.
7. Repeat step 4. The request should now be processed without errors.

## Technologies Used
* Node.js
* Express.js