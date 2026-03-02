# Authentication API

## Overview

 This document describes the authentication endpoints used to sign users in and out of the application.
**Base URL:** `{BASE_URL}/api/{VERSION}`  
**Response Format:** JSON  
**Auth Type:** Bearer Token (`Authorization: Bearer <token>`)
## 1) Login

Authenticates a user and returns an authentication token.

**URL:** `{BASE_URL}/api/{VERSION}/auth/login`  
**Method:** `POST`  
**Headers:**

| Header | Value |
|---|---|
| Authorization | `Bearer <authentication_token>` |

> Note: If your implementation does not require an Authorization header for login, remove this section. Typically, login does **not** require a token.
### Request Parameters

| Name | Data Type | Required | Description |
|---|---|---:|---|
| username | string | Yes | Username for login |
| password | string | Yes | Password for login |

### Example Request (JSON)
```json
{
  "username": "jane.doe",
  "password": "Password@123"
}
```
### Response Body

| Field   | Data Type | Description                              |
|---------|----------|------------------------------------------|
| status  | boolean  | `true` if success, `false` otherwise     |
| message | string   | Status message                           |
| data    | object   | Logged-in user details and token         |

---

### Data Object Fields

| Field       | Data Type | Description                               |
|-------------|----------|-------------------------------------------|
| id          | integer  | User ID of the logged-in user             |
| first_name  | string   | First name of the user                    |
| last_name   | string   | Last name of the user                     |
| email       | string   | Email ID of the user                      |
| role_uuid   | string   | UUID of the user role                     |
| role_name   | string   | Role name                                 |
| site_uuid   | string   | UUID of the site                          |
| team_uuid   | string   | UUID of the team                          |
| last_login  | string   | Last login time of the user               |
| token       | string   | Authentication token                      | 

## 2. Logout

Signs out users from the application when access is no longer needed.

**URL:** `{BASE_URL}/api/{VERSION}/auth/logout`  
**Method:** `GET`  
**Return Type:** `JSON`

### Headers

| Header        | Value                                      |
|---------------|--------------------------------------------|
| Authorization | `Bearer <authentication_token>`            |

---

### Request Parameters

None

---

### Response Body

| Field   | Data Type | Description                              |
|---------|----------|------------------------------------------|
| status  | boolean  | `true` if success, `false` otherwise     |
| message | string   | Status message                           |
| data    | null     | Always `null` for this endpoint          |

---

### Example Success Response

```json
{
  "status": true,
  "message": "Logout successful",
  "data": null
}
