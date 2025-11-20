📌 Booking API – Postman Automation Collection

This project contains a complete Postman automation suite for testing the Restful Booker API, including CRUD operations, environment variables, dynamic test data generation, and assertion scripts.

🚀 Features
✔ Automated API Test Collection

The collection includes:

Create Booking

Get All Bookings

Get Booking by ID

Update Booking

Delete Booking

Token Generation for Authorization

✔ Postman Scripts Added

Pre-request scripts

Dynamic data using Postman variables
({{$randomFirstName}}, {{$randomBoolean}}, {{$randomInt}}, etc.)

Test scripts validating:

Response body

Status codes

Environment variable updates

Data consistency

✔ Environment Configuration

The environment JSON contains:

Base URL

Firstname / Lastname

Total price

Deposit paid (boolean)

Additional needs

Check-in & Check-out date values

Booking ID

Token

📂 Project Structure
📁 Postman-Booking-API-Automation
│
├── 📄 BookingAPIs.postman_collection.json
├── 📄 Test_Env.postman_environment.json
└── 📘 README.md

🧪 How to Use
1️⃣ Import the Collection

Open Postman → File → Import
Select:
✔ BookingAPIs.postman_collection.json

2️⃣ Import the Environment

Go to Environments → Import
Select:
✔ Test_Env.postman_environment.json

3️⃣ Set Base URL

Example:

https://restful-booker.herokuapp.com

4️⃣ Run the Collection

Use Collection Runner:

Environment: Test_Env

Run all test cases

🛠 Technologies Used

Postman

JavaScript (for test scripts)

RESTful APIs

Environment Variables

Pre-request Scripts

Dynamic JSON Payloads

📥 Download Files (from this repo)
File	Description
BookingAPIs.postman_collection.json	Complete API test collection
Test_Env.postman_environment.json	Environment with dynamic variables
✨ Highlights of the Testing Logic
🔹 Dynamic Data Generation
pm.environment.set("fname", pm.variables.replaceIn("{{$randomFirstName}}"));
pm.environment.set("lname", pm.variables.replaceIn("{{$randomLastName}}"));
pm.environment.set("price_product", pm.variables.replaceIn("{{$randomInt}}"));
pm.environment.set("is_depositpaid", pm.variables.replaceIn("{{$randomBoolean}}"));

🔹 Moment.js date handling
const checkin_date = require('moment')().format("YYYY-MM-DD");
const checkout_date = require('moment')().add(4,'d').format("YYYY-MM-DD");

pm.environment.set("check_in", checkin_date);
pm.environment.set("check_out", checkout_date);

🔹 Response validation
pm.test("First Name Check", function(){
    pm.expect(pm.environment.get("fname")).to.eql(responsedata.firstname);
});

🏁 Final Output

After running:

Booking ID is stored automatically

Token is generated and used in Update/Delete

Data validation runs through Postman test scripts

Complete CRUD flow is automated

💡 Why This Project Is Useful

This repository demonstrates:

API automation testing knowledge

Working with dynamic environment variables

Writing test scripts in Postman

Handling authentication tokens

Complete CRUD workflow automation
