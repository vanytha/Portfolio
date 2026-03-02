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
