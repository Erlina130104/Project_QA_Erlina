# Test Case Documentation

This folder contains complete documentation for 127 test cases created for the e-commerce website (practicesoftwaretesting.com).

## File List

- `Test_Case_Link.pdf` - PDF file containing link to Google Spreadsheet with all 127 test cases

## How to Access Test Cases

1. Open the `Test_Case_Link.pdf` file in this folder
2. Click on the Google Spreadsheet link provided in the PDF
3. You will be directed to the complete test case documentation in Google Spreadsheet format

## Overview

This test case documentation covers comprehensive testing of various e-commerce website features, from user registration, login, account management, product catalog, to security testing.

## Test Case Structure

Each test case is documented with the following structure:

| Column | Description |
|--------|-------------|
| **TC ID** | Unique identifier for each test case (e.g., REG-001, LGN-002) |
| **Test Case Title** | Short title describing the test case |
| **Priority** | Level of importance (High, Medium, Low) |
| **Type** | Test type (Functional, Validation, UI, Negative, etc.) |
| **Pre-condition** | Initial conditions that must be met before test execution |
| **Test Steps** | Detailed steps to be performed |
| **Test Data** | Specific data used for testing |
| **Expected Result** | Expected outcome |
| **Actual Result** | Actual outcome when test is executed |
| **Status** | PASS or FAIL |
| **Note** | Additional notes or explanations |
| **Severity** | Bug severity level (if any: Critical, High, Medium, Low) |
| **Severity Impact** | Impact of the bug on the system |
| **Link JIRA** | Link to bug report in JIRA (if available) |

## Test Case Categories

### Test Case Summary per Feature

| No | Feature | Positive Test Cases | Negative Test Cases | Total |
|----|---------|---------------------|---------------------|-------|
| 1 | Customer Registration | 3 | 9 | 12 |
| 2 | Login | 8 | 6 | 14 |
| 3 | My Account Page | 11 | 1 | 12 |
| 4 | Home - Product Catalog Feature | 11 | - | 11 |
| 5 | Categories Feature - Hand Tools | 13 | - | 13 |
| 6 | Categories Feature - Power Tools | 17 | 1 | 18 |
| 7 | Categories Feature - Special Tools | 5 | 6 | 11 |
| 8 | Categories Feature - Rentals | 3 | - | 3 |
| 9 | Product Detail Page (PDP) - Rentals | 10 | - | 10 |
| 10 | Contact Feature | 5 | 6 | 11 |
| 11 | Security Negative Testing | - | 12 | 12 |
| **Total** | | **86** | **41** | **127** |

### Test Case Details per Feature

#### 1. Customer Registration (12 Test Cases)

Testing of new user registration feature including:

**Positive Test Cases (3):**
- REG-001: Verify registration page display
- REG-002: Registration with all valid fields
- REG-003: Password strength indicator validation

**Negative Test Cases (9):**
- REG-004: Registration without filling required fields
- REG-005: Invalid email format validation
- REG-006: Password length validation less than 8 characters
- REG-007: Password validation without uppercase letter (FAILED)
- REG-008: Password validation without special character (FAILED)
- REG-009: Password strength indicator validation
- REG-010: Invalid date of birth format validation
- REG-011: Phone number non-numeric validation
- REG-012: "Register" button validation before fields are filled (FAILED)

#### 2. Login (14 Test Cases)
Testing of login feature with various valid and invalid credential scenarios.

#### 3. My Account Page (12 Test Cases)
Testing of user account page functionality including menu navigation, edit profile, view favorites, view invoices, and view messages.

#### 4. Home - Product Catalog Feature (11 Test Cases)
Testing of product catalog on the homepage including product display, search functionality, filtering and sorting, and pagination.

#### 5. Categories Feature - Hand Tools (13 Test Cases)
Testing of Hand Tools category with various browse and filter scenarios.

#### 6. Categories Feature - Power Tools (18 Test Cases)
Testing of Power Tools category including 1 negative test case.

#### 7. Categories Feature - Special Tools (11 Test Cases)
Testing of Special Tools category with 5 positive and 6 negative test cases.

#### 8. Categories Feature - Rentals (3 Test Cases)
Testing of Rentals category for rental products.

#### 9. Product Detail Page (PDP) - Rentals (10 Test Cases)
Testing of product detail page for Rentals category including product information display, add to cart functionality, product specifications, and related products.

#### 10. Contact Feature (11 Test Cases)
Testing of contact form with 5 positive and 6 negative test cases.

#### 11. Security Negative Testing (12 Test Cases)
Testing of application security including SQL Injection testing, XSS testing, authentication testing, authorization testing, and input validation testing.

## Testing Results

| Metric | Count | Percentage |
|--------|-------|------------|
| **Total Test Cases** | 127 | 100% |
| **Status PASS** | 118 | 92.9% |
| **Status FAIL** | 9 | 7.1% |

Out of 127 test cases executed, 118 test cases passed and 9 test cases failed due to bugs found.

**Testing Results Breakdown:**
- Positive Test Cases: 86 test cases - verifying features work as expected
- Negative Test Cases: 41 test cases - verifying error handling and input validation

## Bugs Found

From 127 test cases executed, 9 bugs were found across different severity levels.

### Bug Summary Report

#### Critical Severity Bugs (3)

| Bug ID | Feature | Issue | Security Impact |
|--------|---------|-------|-----------------|
| **SEC-004** | Registration | Stored XSS in First Name field | Risk of session theft and malicious script injection |
| **SEC-006** | Search | Reflected XSS in search bar | Can be used for phishing and cookie theft |
| **SEC-007** | Login | No brute force protection | Password can be guessed with unlimited attempts |

#### High Severity Bugs (1)

| Bug ID | Feature | Issue | Impact |
|--------|---------|-------|--------|
| **CAT-ST-007** | Categories | Application does not properly handle invalid category URLs. Should display 404, not network error | Poor error handling impacts user experience and SEO |

#### Medium Severity Bugs (5)

| Bug ID | Feature | Issue | Impact |
|--------|---------|-------|--------|
| **REG-007** | Registration | Password validation: missing uppercase error message is misleading | Poor user experience and confusing error message |
| **REG-008** | Registration | Password validation: missing special character error message not informative | Users do not understand password requirements |
| **REG-012** | Registration | Register button not disabled before fields are filled | Poor user experience; multiple errors appear at once |
| **CNT-001** | Contact | Misleading error message about empty file attachments | User confusion; prevents message sending |
| **CAT-ST-008** | Categories | Filter state lost on page refresh | Poor user experience; users must reselect filters |

### Critical Bugs Detail

#### 1. SEC-004: Stored XSS in First Name Field
- **Severity**: Critical
- **Feature**: Registration
- **Issue**: The First Name field is vulnerable to Stored XSS attacks
- **Security Impact**: Attackers can inject malicious scripts that execute when other users view the profile, leading to session theft and potential account compromise

#### 2. SEC-006: Reflected XSS in Search Bar
- **Severity**: Critical
- **Feature**: Search
- **Issue**: Search bar reflects unsanitized user input, allowing XSS attacks
- **Security Impact**: Can be exploited for phishing attacks and stealing user cookies/sessions

#### 3. SEC-007: No Brute Force Protection
- **Severity**: Critical
- **Feature**: Login
- **Issue**: System allows unlimited login attempts without rate limiting
- **Security Impact**: Attackers can perform brute force attacks to guess passwords

### Medium Severity Bugs Detail

#### 1. REG-007: Password Validation - Missing Uppercase
- **Severity**: Medium
- **Issue**: Inaccurate and misleading error message
- **Expected**: "Password must contain at least 1 uppercase letter"
- **Actual**: "Password can not include invalid characters"
- **Impact**: Poor user experience due to confusing error message

#### 2. REG-008: Password Validation - Missing Special Character
- **Severity**: Medium
- **Issue**: Uninformative error message
- **Expected**: "Password must contain at least 1 special character"
- **Actual**: "Password can not include invalid characters"
- **Impact**: Users don't understand what's wrong with their password

#### 3. REG-012: Register Button Not Disabled
- **Severity**: Medium
- **Issue**: Register button can be clicked before required fields are filled
- **Expected**: Register button should be disabled until all required fields are filled
- **Actual**: Button is clickable and multiple errors appear simultaneously
- **Impact**: Poor user experience; users can submit empty forms

## Testing Methodology

**Test Case Design**
- Based on requirements and user stories
- Using Equivalence Partitioning and Boundary Value Analysis techniques
- Covering both positive and negative scenarios

**Test Execution**
- Manual testing without automation tools
- Testing performed on environment: https://practicesoftwaretesting.com
- Browsers used: Chrome/Firefox
- Documentation with screenshots for each bug

**Bug Reporting**
- Each bug documented in JIRA/Atlassian
- Includes: reproduction steps, expected vs actual result, severity, screenshot
- Bug report link included in test case column

## Severity Classification

| Level | Description | Example |
|-------|-------------|---------|
| **Critical** | System crash, data loss, security breach | Successful SQL Injection |
| **High** | Main feature not functioning | Login fails with valid credentials |
| **Medium** | Feature works but has UX/validation issues | Unclear error message |
| **Low** | Typo, alignment, incorrect color | Label typo |

## How to Use This Documentation

1. Open the `Test_Case_Link.pdf` file in this folder
2. Click on the Google Spreadsheet link provided
3. Select the feature sheet you want to test
4. Follow the steps in the "Test Steps" column
5. Use the test data listed in the "Test Data" column
6. Document results:
   - Record results in "Actual Result" column
   - Mark PASS or FAIL in "Status" column
   - Add screenshot if bug is found
7. Report bug: If FAIL, document in JIRA and add link

## Tools Used

- Google Spreadsheet for test case documentation
- Browser DevTools for element inspection and debugging
- JIRA/Atlassian for bug tracking and project management
- Screenshot tools for visual bug documentation
- Postman for API testing (if required)

## Conclusion

Out of 127 test cases executed, 92.9% passed and 7.1% failed. Most features function properly, however 9 bugs were found that need to be fixed, particularly related to security vulnerabilities, validation, and uninformative error messages.

## Recommendations

1. **Critical Priority**: Fix all security vulnerabilities (XSS and brute force protection) immediately
2. Improve error messages to be more specific and user-friendly
3. Enhance password validation by clearly displaying password requirements
4. Implement button state management to disable submit button until form is valid
5. Implement proper error handling for invalid URLs (404 pages)
6. Add session management and rate limiting for login attempts
7. Sanitize all user inputs to prevent XSS attacks
8. Consider automation for regression testing in the future
9. Conduct penetration testing to identify additional security vulnerabilities

## Notes

- The complete test case documentation is maintained in Google Spreadsheet for easy collaboration and real-time updates
- Access link is provided in the PDF file for security and version control purposes
- All test cases are organized by feature in separate sheets within the spreadsheet

---

**Created by**: Erlina Febiola Nainggolan  
**Testing Period**: December 2025  
**Last Updated**: December 6, 2025  
**Environment**: https://practicesoftwaretesting.com