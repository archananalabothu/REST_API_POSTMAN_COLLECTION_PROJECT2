Here is a concise README you can drop into a Newman collection runner repo and then customize with your file names.

text
# Newman Collection Runner – Hotel Booking API

CLI automation setup for running Postman collections with Newman and generating HTML reports for the Hotel Booking REST API.

## Project Structure

.
├── postman/
│ ├── HotelBooking.postman_collection.json
│ └── HotelBooking.environment.json
├── newman/
│ └── reports/ # HTML reports output
└── README.md

text

## Prerequisites

- Node.js (includes npm)
- Global installs:
npm install -g newman
npm install -g newman-reporter-htmlextra

text

## Run the Collection (CLI only)

From repo root:

newman run postman/HotelBooking.postman_collection.json
-e postman/HotelBooking.environment.json

text

## Run with HTML Report (htmlextra)

newman run postman/HotelBooking.postman_collection.json
-e postman/HotelBooking.environment.json
-r cli,htmlextra
--reporter-htmlextra-export "newman/reports/HotelBooking-report.html"

text

On Windows CMD you can use `^` instead of `\` for line breaks or put the whole command on a single line.

## Environment Variables

`postman/HotelBooking.environment.json` typically contains:

- `baseUrl` – API base URL  
- `username`, `password` – credentials for `/auth`  
- `token`, `bookingId` – set dynamically from test scripts

## Viewing Reports

After a run with the HTML reporter, open:

newman/reports/HotelBooking-report.html

text

in your browser to see a detailed summary of passed/failed requests and assertions.
