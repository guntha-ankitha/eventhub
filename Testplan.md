

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
| Selenium  | Latest                |
| API Tool  | Postman               |
| DB        | PostgreSQL            |
| Build     | QA                    |
| IDE       | Eclipse / IntelliJ    |

---

# 8. Entry Criteria

Testing begins when

* Requirements approved
* QA build deployed
* APIs available
* Test Data ready
* Test Environment ready

---

# 9. Exit Criteria

Testing ends when

* 100% planned test cases executed
* Critical defects closed
* High severity defects closed or accepted
* Regression passed
* Test Summary Report completed

---

# 10. Test Deliverables

* Test Plan
* Test Strategy
* Test Scenarios
* Test Cases
* API Collection
* Automation Scripts
* Bug Report
* Test Execution Report
* RTM
* Test Summary Report

---

# 11. Defect Management

Tool

* Jira

Bug Lifecycle

New

↓

Assigned

↓

In Progress

↓

Fixed

↓

Retest

↓

Closed

Rejected / Duplicate / Deferred whenever applicable

---

# 12. Automation Scope

| Module            | Automate |
| ----------------- | -------- |
| Login             | ✅        |
| Registration      | ✅        |
| Event Creation    | ✅        |
| Booking           | ✅        |
| Booking Reference | ✅        |
| Price Validation  | ✅        |
| Pagination        | ✅        |
| Seat Validation   | ✅        |
| Cancellation      | ✅        |
| Clear Bookings    | ✅        |

---

# 13. Manual Test Coverage

| Requirement        | Manual |
| ------------------ | ------ |
| Login              | ✅      |
| Registration       | ✅      |
| Event Creation     | ✅      |
| Event Limit        | ✅      |
| FIFO               | ✅      |
| Sandbox Isolation  | ✅      |
| Booking            | ✅      |
| Refund Eligibility | ✅      |
| Warning Banner     | ✅      |
| Pagination         | ✅      |
| Seat Count         | ✅      |
| Price              | ✅      |

---

# 14. API Coverage

| API              | Verify       |
| ---------------- | ------------ |
| POST /login      | Login        |
| POST /signup     | Register     |
| GET /events      | Event List   |
| POST /events     | Create Event |
| POST /bookings   | Booking      |
| DELETE /booking  | Cancel       |
| DELETE /bookings | Clear All    |

---

# 15. Business Rules Validation Checklist

| Business Rule                                    | Manual | API | Automation |
| ------------------------------------------------ | ------ | --- | ---------- |
| Booking Reference starts with event title letter | ✅      | ✅   | ✅          |
| Seat count decreases immediately                 | ✅      | ✅   | ✅          |
| Price = Quantity × Ticket Price                  | ✅      | ✅   | ✅          |
| Max 6 Events                                     | ✅      | ✅   | ✅          |
| FIFO Event Deletion                              | ✅      | ✅   | ✅          |
| Max 9 Bookings                                   | ✅      | ✅   | ✅          |
| FIFO Booking Deletion                            | ✅      | ✅   | ✅          |
| Refund Eligibility                               | ✅      | ❌   | ✅          |
| Spinner (4 sec)                                  | ✅      | ❌   | ✅          |
| Sandbox Isolation                                | ✅      | ✅   | ✅          |
| Static Events Protected                          | ✅      | ✅   | ✅          |
| Pagination                                       | ✅      | ❌   | ✅          |

---


