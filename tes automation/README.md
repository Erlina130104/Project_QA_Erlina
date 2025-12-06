# Test Automation - Selenium

This folder contains test automation scripts created using Selenium for automated testing.

## Overview

I have created 4 automation scripts to test the main features of the e-commerce website:
1. Test Login
2. Test Product Search
3. Test Product Filtering
4. Test Add to Cart

## Prerequisites

- Python 3.7+
- Selenium WebDriver
- ChromeDriver or Firefox WebDriver

## Setup

1. Install dependencies:
```bash
pip install selenium
```

2. Download WebDriver:
   - Chrome: https://chromedriver.chromium.org/
   - Firefox: https://github.com/mozilla/geckodriver/releases

3. Place WebDriver in the same folder as the script or add to PATH

## Automation Scripts

### 1. Test Login (test_login.py)

**Purpose:** Test login feature with various scenarios

**Test Cases:**
- Login with valid email and password
- Login with incorrect password
- Login with unregistered email
- Login with empty fields

**How to Run:**
```bash
python test_login.py
```

**Expected Result:**
All test cases PASS, user successfully logs in or appropriate error message appears according to scenario

### 2. Test Product Search (test_search.py)

**Purpose:** Test product search feature

**Test Cases:**
- Search product with existing keyword
- Search product with non-existent keyword
- Search with special characters
- Search with empty field

**How to Run:**
```bash
python test_search.py
```

**Expected Result:**
Search successfully displays matching products or "No results found" message

### 3. Test Product Filtering (test_filter.py)

**Purpose:** Test product filtering feature

**Test Cases:**
- Filter by category
- Filter by brand
- Filter by price range
- Combination of multiple filters

**How to Run:**
```bash
python test_filter.py
```

**Expected Result:**
Products are filtered according to selected criteria

### 4. Test Add to Cart (test_add_to_cart.py)

**Purpose:** Test add to cart feature

**Test Cases:**
- Add to cart with valid quantity
- Add to cart with quantity 0
- Add to cart multiple products
- Verify cart total

**How to Run:**
```bash
python test_add_to_cart.py
```

**Expected Result:**
Products are successfully added to cart and total is updated correctly

## Run All Tests

```bash
pytest test_*.py
```

## Test Results

| Metric | Count | Percentage |
|--------|-------|------------|
| Total Scripts | 4 | - |
| PASS | 4 | 100% |
| FAIL | 0 | 0% |

## Important Notes

- Ensure the website is accessible before running automation
- Selenium will open the browser automatically
- Do not close the browser while tests are running
- Screenshots will be saved in the folder if any failures occur

## Troubleshooting

**WebDriver not found:**
- Ensure WebDriver is in PATH or in the same folder as the script

**Element not found:**
- Website may be loading slowly, increase wait time

**Connection refused:**
- Ensure the website is accessible