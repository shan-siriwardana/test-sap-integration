# API Service Contracts Summary

This document provides an overview of the API contracts delivered as part of the checkout capability.  
For full details, see the respective OpenAPI specifications under `/docs`.

# API Contracts Overview

| API          | Operation         | URI                         | Sample Request                                                                                 | Sample Response                                                                                |
|--------------|------------------|-----------------------------|-------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------|
| Basket API   | Start Checkout   | `POST /baskets/{id}/sessions` | ```json<br>{ "basketId": "b_001" }<br>```                                                       | ```json<br>{ "checkoutSessionId": "cs_123", "expiresAt": "2025-09-09T12:45:00Z", "totals": { "grandTotal": 62.97, "currency": "NZD" } }<br>``` |
| Payment API  | Authorize Payment| `POST /payments/confirm`    | ```json<br>{ "checkoutSessionId": "cs_123", "paymentMethodId": "pm_abc" }<br>```                | ```json<br>{ "status": "AUTHORIZED" }<br>```                                                   |
| Checkout API | Confirm Checkout | `POST /checkout/confirm`    | ```json<br>{ "checkoutSessionId": "cs_123", "paymentMethodId": "pm_abc" }<br>```                | ```json<br>{ "orderId": "ORD-123", "status": "CONFIRMED" }<br>```                              |