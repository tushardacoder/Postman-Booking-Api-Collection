# 📌 Booking API – Postman Automation Collection

A complete **Postman automation suite** for testing the **Restful Booker API**, covering full CRUD operations, authentication, dynamic data generation, and detailed assertion scripts.  
This project is ideal for demonstrating **API testing, scripting, and automation skills**.

---

## 🚀 Features

### ✔ Complete Automated API Test Collection
This collection includes:

- **Create Booking**
- **Get All Bookings**
- **Get Booking by ID**
- **Update Booking (PUT/PATCH)**
- **Delete Booking**
- **Token Generation (Authentication)**

---

## ✔ Postman Scripts Included

### 🟦 Pre-request Scripts
Used for:
- Generating dynamic request data  
- Setting environment variables  
- Preparing token/auth requests  

### 🟩 Dynamic Test Data Generation
Uses Postman's built-in variables:

```
{{$randomFirstName}}
{{$randomLastName}}
{{$randomInt}}
{{$randomBoolean}}
```

### 🟧 Test Scripts for Validation
Covers:

- Response body checks  
- Status code validation  
- Variable updates  
- Data consistency assertions  
- ID & token extraction  

---

## ✔ Environment Configuration

The environment JSON provides:

| Variable | Description |
|---------|-------------|
| `base_url` | Base API URL |
| `firstname`, `lastname` | Randomly generated data |
| `totalprice` | Random integer |
| `depositpaid` | Boolean |
| `additionalneeds` | String value |
| `check_in`, `check_out` | Auto-generated dates |
| `bookingid` | Stored booking ID |
| `token` | Auth token |

---

## 📂 Project Structure

```
📁 Postman-Booking-API-Automation
│
├── 📄 BookingAPIs.postman_collection.json
├── 📄 Test_Env.postman_environment.json
└── 📘 README.md
```

---

## 🧪 How to Use

### 1️⃣ Import the Collection  
In Postman:  
`File → Import`  
Choose:  
✔ `BookingAPIs.postman_collection.json`

### 2️⃣ Import the Environment  
Go to **Environments → Import**  
✔ `Test_Env.postman_environment.json`

### 3️⃣ Set Base URL  
Example:

```
https://restful-booker.herokuapp.com
```

### 4️⃣ Run the Collection  
Using Collection Runner:

- Environment: **Test_Env**
- Click **Run**  
- All CRUD test cases execute automatically

---

## 🛠 Technologies Used

- **Postman**
- **JavaScript** (Pre-request & Test scripts)
- **RESTful API Testing**
- **Dynamic Environment Variables**
- **Moment.js** for date handling

---

## ✨ Key Testing Logic

### 🔹 Dynamic Data Generation

```javascript
pm.environment.set("fname", pm.variables.replaceIn("{{$randomFirstName}}"));
pm.environment.set("lname", pm.variables.replaceIn("{{$randomLastName}}"));
pm.environment.set("price_product", pm.variables.replaceIn("{{$randomInt}}"));
pm.environment.set("is_depositpaid", pm.variables.replaceIn("{{$randomBoolean}}"));
```

---

### 🔹 Dynamic Dates (Moment.js)

```javascript
const checkin_date = require('moment')().format("YYYY-MM-DD");
const checkout_date = require('moment')().add(4,'d').format("YYYY-MM-DD");

pm.environment.set("check_in", checkin_date);
pm.environment.set("check_out", checkout_date);
```

---

### 🔹 Response Validation

```javascript
pm.test("First Name Check", function () {
    pm.expect(pm.environment.get("fname"))
      .to.eql(responsedata.firstname);
});
```

---

## 🏁 Final Output Summary

After running the collection:

✔ Booking ID stored automatically  
✔ Authentication token generated  
✔ Token reused for **Update** and **Delete**  
✔ All CRUD operations fully automated  
✔ Dynamic data ensures fresh test runs  
✔ Validations ensure consistency  

---

## 💡 Why This Project Is Useful

This repository demonstrates strong knowledge in:

- API Automation Testing  
- Postman scripting (JS-based)  
- Environment & collection management  
- Working with dynamic variables  
- CRUD workflow automation  
- Token-based authentication testing  

