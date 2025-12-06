# API Testing Documentation

This folder contains API testing documentation performed using Postman on the e-commerce website.

## Base URL
https://api.practicesoftwaretesting.com

## Tested Endpoints

### 1. POST /login
**Purpose:** User login and authentication token retrieval

**Request:**
```
Method: POST
Body:
{
  "email": "user@example.com",
  "password": "password123"
}
```

**Expected Response:**
```
Status: 200
Body:
{
  "token": "eyJhbGc...",
  "user_id": 123
}
```

**Test Cases:**
- Login with valid email and password
- Login with incorrect password
- Login with unregistered email
- Login without filling required fields

### 2. GET /products
**Purpose:** Retrieve product list

**Query Parameters:**
- `search` - Search products by keyword
- `category` - Filter by category
- `limit` - Number of products per page
- `offset` - Pagination offset

**Expected Response:**
```
Status: 200
Body:
[
  {
    "id": 1,
    "name": "Product Name",
    "price": 99.99,
    "category": "tools"
  }
]
```

**Test Cases:**
- Get all products
- Search products with valid keyword
- Search with non-existent keyword
- Filter by category
- Pagination

### 3. GET /products/:id
**Purpose:** Retrieve product details by ID

**Path Parameters:**
- `id` - Product ID

**Expected Response:**
```
Status: 200
Body:
{
  "id": 1,
  "name": "Product Name",
  "price": 99.99,
  "description": "...",
  "image": "url",
  "stock": 10
}
```

**Test Cases:**
- Get product with valid ID
- Get product with non-existent ID
- Get product with invalid ID format

### 4. POST /cart
**Purpose:** Add product to cart

**Headers:**
```
Authorization: Bearer {token}
```

**Request:**
```
Method: POST
Body:
{
  "product_id": 1,
  "quantity": 2
}
```

**Expected Response:**
```
Status: 201
Body:
{
  "cart_id": 123,
  "product_id": 1,
  "quantity": 2,
  "total": 199.98
}
```

**Test Cases:**
- Add to cart with valid quantity
- Add to cart with quantity 0
- Add to cart with invalid product ID
- Add to cart without token (unauthorized)

### 5. GET /user/profile
**Purpose:** Retrieve user profile

**Headers:**
```
Authorization: Bearer {token}
```

**Expected Response:**
```
Status: 200
Body:
{
  "id": 123,
  "name": "Erlina",
  "email": "erlina@example.com",
  "phone": "081234567890"
}
```

**Test Cases:**
- Get profile with valid token
- Get profile with invalid token
- Get profile without token

## Test Results

| Metric | Count | Percentage |
|--------|-------|------------|
| Total API Endpoints | 5 | - |
| Total Test Cases | 12 | - |
| PASS | 11 | 92% |
| FAIL | 1 | 8% |

## Vulnerabilities Found

1. **No Login Attempt Limit** - Unlimited login retry attempts are allowed
2. **Weak Password Validation** - Password requirements are not strict enough

## Tools Used

- Postman
- Postman Collection: `postman_collection.json`

## How to Use

1. Import the `postman_collection.json` file into Postman
2. Set environment variables for the base URL
3. Execute requests one by one
4. Document responses and results