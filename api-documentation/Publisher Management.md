# Publisher Management API

## Overview

The Publisher Management API allows administrators to create, retrieve, update, and delete publisher records in the system.

**Base URL:** `{BASE_URL}/api/{VERSION}`  
**Response Format:** `JSON`  
**Authentication:** Bearer Token required for all endpoints

Header:
```
Authorization: Bearer <authentication_token>
```

---

# 1. Add Publisher

Creates a new publisher in the system.

**URL:** `{BASE_URL}/api/{VERSION}/publishers`  
**Method:** `POST`

---

### Request Parameters

| Name           | Data Type | Required | Description                |
|----------------|----------|----------|----------------------------|
| publisher_name | string   | Yes      | Name of the publisher      |
| address1       | string   | No       | Address line 1             |
| address2       | string   | No       | Address line 2             |
| email          | string   | No       | Email ID                   |
| contact_number | string   | No       | Contact number             |
| country_uuid   | string   | Yes      | UUID of the country        |
| site_uuid      | string   | Yes      | UUID of the site           |

---

### Example Request

```json
{
  "publisher_name": "ABC Publications",
  "address1": "123 Main Street",
  "address2": "Suite 400",
  "email": "contact@abcpublications.com",
  "contact_number": "+1-555-123-4567",
  "country_uuid": "11111111-2222-3333-4444-555555555555",
  "site_uuid": "66666666-7777-8888-9999-000000000000"
}
```

---

### Example Success Response

```json
{
  "status": true,
  "message": "Publisher created successfully",
  "data": null
}
```

---

# 2. Get Publisher

Retrieves details of a specific publisher.

**URL:** `{BASE_URL}/api/{VERSION}/publishers/{publisher_id}`  
**Method:** `GET`

---

### Path Parameters

| Parameter     | Data Type | Description              |
|---------------|----------|--------------------------|
| publisher_id  | integer  | Unique publisher ID      |

---

### Example Success Response

```json
{
  "status": true,
  "message": "Publisher retrieved successfully",
  "data": {
    "publisher_id": 101,
    "publisher_name": "ABC Publications",
    "address1": "123 Main Street",
    "address2": "Suite 400",
    "email": "contact@abcpublications.com",
    "contact_number": "+1-555-123-4567",
    "country_uuid": "11111111-2222-3333-4444-555555555555",
    "site_uuid": "66666666-7777-8888-9999-000000000000",
    "created_at": "2026-03-02T10:30:00Z"
  }
}
```

---

# 3. Delete Publisher

Deletes a publisher from the system.

**URL:** `{BASE_URL}/api/{VERSION}/publishers/{publisher_id}`  
**Method:** `DELETE`

---

### Example Success Response

```json
{
  "status": true,
  "message": "Publisher deleted successfully",
  "data": null
}
```

---

# Common Error Responses

| HTTP Code | Description                  |
|-----------|------------------------------|
| 400       | Invalid request parameters   |
| 401       | Unauthorized                 |
| 404       | Publisher not found          |
| 500       | Internal server error        |

---

# Response Structure

All responses follow a consistent structure:

| Field   | Data Type | Description                          |
|---------|----------|--------------------------------------|
| status  | boolean  | `true` if success, `false` otherwise |
| message | string   | Status message                       |
| data    | object / null | Response payload (if applicable) |
