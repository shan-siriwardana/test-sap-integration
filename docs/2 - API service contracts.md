# API Service Contracts Summary

This document provides an overview of the API contracts delivered as part of the checkout capability.  
For full details, see the respective OpenAPI specifications under `/docs`.

---

| API                  | Operation            | URI                               | Sample Request                                                                 | Sample Response                                                                 |
|-----------------------|----------------------|-----------------------------------|---------------------------------------------------------------------------------|---------------------------------------------------------------------------------|
| **Basket API**       | Create Basket        | `POST /baskets`                   | _N/A (omitted for assignment)_                                                  | `201 Created` with basketId                                                     |
|                       | Add Items            | `POST /baskets/{basketId}/items`  | _N/A (omitted for assignment)_                                                  | `200 OK`                                                                        |
|                       | Start Checkout       | `POST /baskets/{basketId}/sessions` | `{ "basketId": "b_001" }`                                                      | `{ "checkoutSessionId": "cs_8fb7e4", "expiresAt": "2025-09-09T12:45:00Z", ... }`|
| **Payment API**      | Authorize Payment     | `POST /payments/confirm`          | `{ "checkoutSessionId": "cs_8fb7e4", "paymentMethodId": "pm_abc123" }`          | `{ "status": "AUTHORIZED" }`                                                    |
|                       | Capture Payment      | `POST /payments/{authId}/capture` | `{ "amount": 120.00 }`                                                          | `{ "status": "CAPTURED", "captureId": "cap_77a1f3" }`                           |
| **Checkout API**     | Start Checkout        | `POST /checkout/start`            | `{ "basketId": "b_001", "customerId": "cust_12345" }`                           | `{ "checkoutSessionId": "cs_8fb7e4", "totals": { "grandTotal": 62.97, ... } }`  |
|                       | Confirm Checkout     | `POST /checkout/confirm`          | `{ "checkoutSessionId": "cs_8fb7e4", "paymentMethodId": "pm_abc123" }`          | `{ "orderId": "ORD-12345", "status": "CONFIRMED" }`                             |
| **Order API**        | Create Order          | `POST /orders`                    | `{ "checkoutSessionId": "cs_8fb7e4", "customerId": "cust_12345", "authId": "auth_5f2c9d" }` | `{ "orderId": "ORD-12345", "status": "CONFIRMED" }`                             |

---

✅ This table gives interviewers a quick bird’s-eye view.  
They can dive deeper into the OpenAPI YAML files if they want details.