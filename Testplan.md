

# Test Plan – EventHub Application

## 1. Document Information

| Item             | Details                    |
| ---------------- | -------------------------- |
| Project          | EventHub                   |
| Module           | Event Management & Booking |
| Version          | 1.0                        |
| Prepared By      | Guntha Ankitha             |
| Testing Type     | Manual + Automation        |
| Test Level       | Regression Testing         |
| Test Environment | QA                         |

---

# 2. Objective

The objective of this test plan is to validate that the EventHub application satisfies all functional and non-functional business requirements. Testing will ensure event creation, booking, booking management, seat calculations, pricing, refund eligibility, sandbox isolation, FIFO pruning, and security rules work correctly while maintaining application quality before release.

---

# 3. Scope

## In Scope

* User Registration/Login
* Event Listing
* Event Creation
* Event Update
* Event Deletion
* Booking Tickets
* Booking Cancellation
* Clear All Bookings
* Seat Availability
* Booking Reference Validation
* Refund Eligibility
* Price Calculation
* Pagination
* FIFO Logic
* User Sandbox Isolation
* API Validation
* UI Validation
* Cross Browser Testing

### Out of Scope

* Payment Gateway
* Email Notifications
* SMS Notifications
* Performance Testing
* Security Penetration Testing

---

# 4. Test Objectives

Verify:

* User can register/login.
* User can browse events.
* Booking flow works correctly.
* Seat count updates correctly.
* Booking reference format is correct.
* FIFO pruning works.
* Pagination works.
* Price calculation is correct.
* Refund eligibility behaves correctly.
* User isolation is maintained.
* Static events cannot be modified.
* Dynamic events behave according to requirements.

---

# 5. Test Strategy

## A. Manual Testing

### Functional Testing

Modules:

* Login
* Registration
* Event Management
* Booking
* Cancellation
* Refund Eligibility
* Price Calculation
* Booking Reference
* Sandbox Isolation

---

### UI Testing

Verify:

* Layout
* Buttons
* Labels
* Error Messages
* Success Messages
* Warning Banners
* Spinner
* Pagination

---

### Regression Testing

After every build verify:

* Login
* Event Creation
* Booking
* Cancellation
* Seat Count
* Price
* Booking Reference

---

### Smoke Testing

* Application launches
* Login works
* Event page loads
* Booking works

---

### Sanity Testing

Whenever developers fix bugs:

Verify only affected module.

---

### Exploratory Testing

Random testing on

* Invalid quantity
* Refresh during booking
* Double clicking Book button
* Browser Back button
* Multiple tabs

---

## B. API Testing

Validate

* Login API
* Register API
* Events API
* Booking API
* Delete Booking API
* Create Event API

Verify

* Status Codes
* Response Time
* JSON Schema
* Authorization
* Headers
* Error Messages

---

## C. Automation Testing (Selenium)

Automate

High Priority Regression Cases

Examples

* Login
* Event Search
* Create Event
* Book Event
* Delete Booking
* Clear Bookings
* Price Validation
* Booking Reference Validation
* Refund Eligibility
* Pagination

Framework

* Java
* Selenium WebDriver
* TestNG
* Maven
* Page Object Model
* Extent Reports
* Jenkins CI/CD

---

# 6. Risk Based Testing

High Priority Modules

* Login
* Booking
* Seat Calculation
* FIFO Logic
* Booking Reference
* User Isolation

Medium Priority

* Pagination
* Warning Banner
* Refund Eligibility

Low Priority

* UI Cosmetics

---

# 7. Test Environment

| Component | Value                 |
| --------- | --------------------- |
| OS        | Windows 11            |
| Browser   | Chrome, Edge, Firefox |
| Java      | JDK 21                |
| Selenium  | Latest 3.14           |
| API Tool  | Postman               |
| DB        | PostgreSQL            |
| Build     | QA                    |
| IDE       | Eclipse / IntelliJ    |

---

# 8. Entry Criteria

We can start once requirements are signed off, the QA build is deployed, APIs are reachable, test data is prepared, and the environment is stable.

---

# 9. Exit Criteria

Testing is done when all planned test cases have been run. There should be no open critical defects. High-severity defects must either be fixed or officially accepted by the team. Regression testing must pass. And the test summary report must be completed.

---

# 10. Test Deliverables

Test plan, test scenarios and cases, the Postman collection, automation scripts, bug reports, execution reports, the RTM (requirement traceability matrix), and the final test summary report.

---

# 11. Defect Management

Bugs are logged and tracked in Jira, following the standard lifecycle:

New → Assigned → In Progress → Fixed → Retest → Closed

(with Rejected, Duplicate, or Deferred as alternate paths where applicable)

---

# 12. Coverage Summary

Automated: Login, registration, event creation, booking, booking reference, price validation, pagination, seat validation, cancellation, clear bookings.

Manual Test coverage:login, registration, and creating events. It also covers event limits and FIFO logic. Sandbox isolation, booking, and refund eligibility are tested manually too. So are the warning banner, pagination, seat count, and price.

API Coverage:The POST /login API is tested for user login, and POST /signup is tested for registration. GET /events verifies the event listing, while POST /events verifies event creation. Booking is tested through POST /bookings, cancelling a single booking uses DELETE /booking, and clearing all bookings at once uses DELETE /bookings.

---

# 13. Business Rules Validation Checklist

| Business Rule | Manual | API | Automation |
|---|---|---|---|
| Booking reference starts with event title letter | ✔ | ✔ | ✔ |
| Seat count decreases immediately | ✔ | ✔ | ✔ |
| Price = Quantity × Ticket Price | ✔ | ✔ | ✔ |
| Max 6 events | ✔ | ✔ | ✔ |
| FIFO event deletion | ✔ | ✔ | ✔ |
| Max 9 bookings | ✔ | ✔ | ✔ |
| FIFO booking deletion | ✔ | ✔ | ✔ |
| Refund eligibility | ✔ | ✘ | ✔ |
| Spinner (4 sec) | ✔ | ✘ | ✔ |
| Sandbox isolation | ✔ | ✔ | ✔ |
| Static events protected | ✔ | ✔ | ✔ |
| Pagination | ✔ | ✘ | ✔ |

---


