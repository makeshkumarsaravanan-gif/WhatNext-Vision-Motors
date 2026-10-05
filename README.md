# WhatNext Vision Motors 🚗

## Shaping the Future of Mobility with Innovation and Excellence

WhatNext Vision Motors is a **Salesforce-based Vehicle Order Management and Dealership CRM solution** designed to modernize vehicle sales operations, automate order processing, and improve customer experience.

The system provides a centralized platform for managing vehicles, dealers, customers, vehicle orders, test drives, and service requests. Salesforce automation is used to validate vehicle stock, assign orders to dealers, update order statuses, manage inventory, and send automated test-drive reminders.

---

## 📌 Project Overview

Traditional vehicle ordering processes often rely on manual records, spreadsheets, and disconnected systems. This can result in:

- Incorrect or duplicate vehicle orders
- Lack of real-time stock visibility
- Delays in dealer assignment
- Manual order-status updates
- Missed test-drive reminders
- Difficulty monitoring dealership performance

**WhatNext Vision Motors** addresses these challenges by implementing an automated Salesforce CRM solution.

### Key Objectives

- Automate vehicle order processing
- Validate vehicle stock before confirming orders
- Automatically assign orders to dealers
- Maintain accurate vehicle inventory
- Automate order-status updates
- Schedule test-drive reminders
- Provide real-time reports and dashboards
- Improve customer satisfaction and operational efficiency

---

# ✨ Key Features

## 🚘 Vehicle Management

Manage vehicle information including:

- Vehicle name and model
- Vehicle type
- Price
- Stock quantity
- Availability status
- Associated dealer

## 👤 Customer Management

Maintain centralized customer information such as:

- Customer name
- Email
- Phone
- Address
- Preferred vehicle type

## 🏢 Dealer Management

Manage dealership information and associate vehicles and orders with authorized dealers.

## 🛒 Automated Vehicle Ordering

Customers can place vehicle orders through Salesforce. The system validates the order and processes it according to vehicle availability.

## 📦 Stock Validation

Apex triggers verify vehicle stock before an order can be processed. Orders for vehicles with zero available stock are prevented.

## 📍 Automatic Dealer Assignment

Salesforce Flow automatically assigns an order to the appropriate dealer based on customer and dealer location information.

## 🔄 Automated Order Processing

Pending orders are automatically processed when vehicle stock becomes available.

## 🚗 Test Drive Management

Customers can schedule test drives, while automated Salesforce Flow sends reminder emails before the scheduled test drive.

## 📊 Reports & Dashboards

Managers can monitor:

- Order status
- Vehicle sales
- Dealer performance
- Inventory
- Customer activity
- Overall operational performance

---

# 🏗️ Solution Architecture

The solution is built using Salesforce CRM components.

```text
                    ┌─────────────────────┐
                    │      Customer       │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │   Vehicle Order     │
                    └──────────┬──────────┘
                               │
                 ┌─────────────┴─────────────┐
                 ▼                           ▼
        ┌─────────────────┐         ┌──────────────────┐
        │ Stock Validation│         │ Dealer Assignment│
        │  Apex Trigger   │         │ Salesforce Flow  │
        └────────┬────────┘         └────────┬─────────┘
                 │                           │
                 └─────────────┬─────────────┘
                               ▼
                    ┌─────────────────────┐
                    │  Order Processing   │
                    │ Batch / Scheduled   │
                    │       Apex          │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │ Reports & Dashboards│
                    └─────────────────────┘
```

---

# 🗃️ Salesforce Data Model

The project contains the following custom Salesforce objects:

| Object | Purpose |
|---|---|
| `Vehicle__c` | Stores vehicle details and stock information |
| `Vehicle_Dealer__c` | Stores dealer information |
| `Vehicle_Customer__c` | Stores customer information |
| `Vehicle_Order__c` | Tracks vehicle orders |
| `Vehicle_Test_Drive__c` | Manages test-drive bookings |
| `Vehicle_Service_Request__c` | Tracks vehicle service requests |

### Main Relationships

```text
Customer
   │
   ├──────────────► Vehicle Order ◄────────────── Vehicle
   │
   ├──────────────► Test Drive   ◄────────────── Vehicle
   │
   └──────────────► Service Request ◄─────────── Vehicle

Dealer
   │
   └──────────────► Vehicle / Vehicle Order
```

---

# ⚙️ Technology Stack

| Category | Technology |
|---|---|
| CRM Platform | Salesforce |
| User Interface | Salesforce Lightning |
| Database | Salesforce Custom Objects |
| Automation | Salesforce Flow |
| Business Logic | Apex |
| Validation | Apex Triggers / Validation Rules |
| Bulk Processing | Batch Apex |
| Scheduling | Scheduled Apex |
| Reporting | Salesforce Reports |
| Analytics | Salesforce Dashboards |
| Development Environment | Salesforce Developer Org |

---

# 🤖 Automation

The project uses multiple Salesforce automation technologies to reduce manual effort and improve operational efficiency.

## Record-Triggered Flow

Used for:

- Automatic dealer assignment
- Order-status processing
- Test-drive reminder emails

## Apex Trigger

The `VehicleOrderTrigger` validates vehicle availability and prevents orders when the selected vehicle is out of stock.

It also updates vehicle stock when an order is confirmed.

## Batch Apex

`VehicleOrderBatch` processes pending orders and confirms them when new vehicle stock becomes available.

## Scheduled Apex

`VehicleOrderBatchScheduler` schedules the batch process automatically at a defined time.

---

# 🔄 Order Processing Flow

```text
Customer Places Order
        │
        ▼
   Check Vehicle
        │
        ▼
 Is Stock Available?
      /       \
    Yes        No
     │          │
     ▼          ▼
Assign Dealer  Keep Order Pending
     │          │
     ▼          ▼
Confirm Order  Batch Job Checks Stock
     │          │
     ▼          │
 Reduce Stock ◄─┘
     │
     ▼
Update Order Status
```

---

# 📧 Test Drive Reminder Flow

```text
Test Drive Created
        │
        ▼
Status = Scheduled
        │
        ▼
Scheduled Flow
        │
        ▼
One Day Before Test Drive
        │
        ▼
Retrieve Customer Email
        │
        ▼
Send Reminder Email
```

---

# 🧩 Project Modules

The project consists of the following modules:

1. Salesforce Account Setup
2. Data Modeling
3. Custom Objects
4. Custom Fields
5. Object Relationships
6. Lightning App
7. Salesforce Flows
8. Apex Triggers
9. Batch Apex
10. Scheduled Apex
11. Reports
12. Dashboards
13. Functional Testing

---

# 🧪 Testing

The application was tested to verify the following functionality:

- Vehicle creation
- Customer creation
- Dealer creation
- Vehicle order creation
- Stock validation
- Out-of-stock order prevention
- Dealer assignment
- Order-status updates
- Inventory updates
- Batch processing
- Scheduled processing
- Test-drive reminder emails
- Reports and dashboards

---

# ✅ Advantages

- Centralized vehicle and customer data
- Automated business processes
- Reduced manual intervention
- Accurate inventory management
- Faster dealer assignment
- Real-time reporting
- Improved customer experience
- Scalable for multiple dealerships

---

# ⚠️ Limitations

- Dependent on the Salesforce platform
- Requires initial Salesforce configuration
- Dealer location matching can be improved with GPS integration
- Advanced customer communication requires additional integrations

---

# 🚀 Future Scope

The platform can be enhanced with:

- 📱 Mobile vehicle-ordering application
- 📍 GPS-based dealer assignment
- 💬 SMS and WhatsApp notifications
- 🤖 AI-based demand forecasting
- 📈 Advanced sales analytics
- 💳 Online payment integration
- 🔔 Real-time customer notifications
- 🗺️ Map-based dealer discovery
- 🧠 AI-powered vehicle recommendations

---

# 🎯 Project Outcome

The WhatNext Vision Motors Salesforce implementation transforms a traditionally manual vehicle-ordering process into an **automated, centralized, and scalable CRM solution**.

By combining **Salesforce Flow, Apex Triggers, Batch Apex, Scheduled Apex, Reports, and Dashboards**, the system improves:

- Order accuracy
- Inventory management
- Dealer operations
- Customer engagement
- Operational efficiency

---

# 👨‍💻 Project Information

| Attribute | Details |
|---|---|
| **Project** | WhatNext Vision Motors |
| **Platform** | Salesforce CRM |
| **Domain** | Automobile / Vehicle Order Management |
| **Methodology** | Agile |
| **Environment** | Salesforce Developer Org |

---

# 📌 Conclusion

WhatNext Vision Motors demonstrates how Salesforce CRM can be used to build an end-to-end vehicle sales and dealership management platform.

The solution combines **data management, workflow automation, Apex programming, scheduled processing, and analytics** to create a more efficient and customer-focused mobility experience.

> **WhatNext Vision Motors — Shaping the Future of Mobility with Innovation and Excellence. 🚗**


<img width="1366" height="768" alt="Lightning App" src="https://github.com/user-attachments/assets/9538f70a-5dfb-490b-8fc7-33e845437a10" />
