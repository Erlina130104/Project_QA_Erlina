# Manual Testing Documentation

This folder contains comprehensive documentation of manual testing performed on the e-commerce website (practicesoftwaretesting.com).

## Overview

I have conducted comprehensive manual testing on the e-commerce web application with a focus on:
- Functional testing
- UI/UX testing
- Negative testing
- Security testing

## Test Case Summary

| No | Feature | Positive Test Cases | Negative Test Cases | Total |
|----|---------|---------------------|---------------------|-------|
| 1 | Customer Registration | 3 | 9 | 12 |
| 2 | Login | 8 | 6 | 14 |
| 3 | My Account Page | 11 | 1 | 12 |
| 4 | Home Feature - Product Catalog | 11 | - | 11 |
| 5 | Categories Feature - Hand Tools | 13 | - | 13 |
| 6 | Categories Feature - Power Tools | 17 | 1 | 18 |
| 7 | Categories Feature - Special Tools | 5 | 6 | 11 |
| 8 | Categories Feature - Rentals | 3 | - | 3 |
| 9 | Sub-section: Product Detail Page (PDP) - Rentals | 10 | - | 10 |
| 10 | Contact Feature | 5 | 6 | 11 |
| 11 | Security Negative Testing | - | 12 | 12 |
| **Total** | | | | **127** |

## Folder Structure

Based on the File Explorer structure, the testing documentation is divided into:

1. **Categories Feature - Power Tools** - Testing of Power Tools category
2. **Categories Feature - Rentals** - Testing of Rentals category
3. **Categories Feature - Special Tools** - Testing of Special Tools category
4. **Categories Feature - Hand Tools** - Testing of Hand Tools category
5. **Contact Feature** - Testing of Contact page
6. **Customer Registration Feature** - Testing of user registration feature
7. **Home Feature_Product Catalog** - Testing of product catalog
8. **Login Feature** - Testing of login feature
9. **My Account Page** - Testing of user account page
10. **Security Negative Test** - Testing of application security

## Testing Details per Feature

### 1. Customer Registration (12 Test Cases)
Testing of registration feature with various scenarios:
- Registration with valid data (3 positive cases)
- Registration with empty fields (9 negative cases)
- Email format validation
- Password strength validation
- Appropriate error messages

### 2. Login (14 Test Cases)
Testing of login feature with:
- Successful login with valid credentials (8 positive cases)
- Failed login with various error scenarios (6 negative cases)
- Invalid email format
- Incorrect password
- Empty fields

### 3. My Account Page (12 Test Cases)
Testing of features on My Account page:
- Menu navigation (11 positive cases)
- Edit profile
- View favorites
- View invoices
- View messages
- Error scenarios (1 negative case)

### 4. Product Catalog & Categories (66 Test Cases)
Testing of product features including:

**Home Feature - Product Catalog (11 cases)**
- Product search
- Filtering and sorting
- Pagination

**Hand Tools Category (13 cases)**
- Browsing hand tools products
- Category-specific filtering

**Power Tools Category (18 cases)**
- Browsing power tools products
- Filtering and searching
- 1 negative case

**Special Tools Category (11 cases)**
- Browsing special tools
- 5 positive and 6 negative cases

**Rentals Category (3 cases)**
- Browsing rental products

**Product Detail Page - Rentals (10 cases)**
- Rental product details
- Add to cart
- Product information

### 5. Contact (11 Test Cases)
Testing of contact page:
- Submit contact form (5 positive cases)
- Form validation (6 negative cases)
- Error messages

### 6. Security Negative Testing (12 Test Cases)
Testing of application security:
- SQL Injection
- XSS (Cross-Site Scripting)
- CSRF protection
- Session management
- Input validation
- Authentication bypass attempts

## Tools Used

- **Browser**: Chrome/Firefox for manual testing
- **Browser DevTools**: For element inspection and debugging
- **Postman**: For API testing
- **Screenshot Tools**: For testing evidence documentation

## Testing Methodology

1. **Test Case Design**: Designing test cases based on requirements
2. **Test Execution**: Executing test cases manually
3. **Bug Reporting**: Documenting bugs found
4. **Test Documentation**: Screenshots and descriptions of testing results

## Bug Severity Classification

- **Critical**: Bugs that cause application crashes or data loss
- **High**: Bugs affecting main features or security
- **Medium**: Bugs affecting functionality but with available workarounds
- **Low**: Cosmetic bugs or typos that don't affect functionality

## Testing Results

Out of **127 total test cases** executed:
- **Positive Test Cases**: Verifying features work as expected
- **Negative Test Cases**: Verifying error handling and validation

Detailed testing results (Pass/Fail) can be found in each feature's documentation folder.

## Important Notes

1. All testing was performed **manually** without automation frameworks
2. Testing was conducted on environment: practicesoftwaretesting.com
3. Each test case includes:
   - Test steps
   - Expected result
   - Actual result
   - Screenshot (when necessary)
   - Status (Pass/Fail)

4. Bugs found are documented with:
   - Bug ID
   - Severity level
   - Reproduction steps
   - Expected vs Actual behavior
   - Screenshot/video evidence

## Recommendations

Based on testing results, several areas requiring special attention:
- **Security**: Need strengthening in input validation and authentication
- **Error Handling**: Some error messages need to be more informative
- **UI/UX**: Several flows could be improved for better user experience

---

**Tested by**: Erlina Febiola Nainggolan  
**Testing Period**: December 2025  
**Last Updated**: December 4, 2025