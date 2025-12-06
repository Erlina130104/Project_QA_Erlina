# QA Tester Portfolio - Erlina Febiola Nainggolan

Hello, I'm Erlina Febiola Nainggolan, a QA Tester with experience in web application and API testing. In this repository, I document all the testing work I have completed.

## About This Portfolio

This portfolio contains comprehensive documentation of testing I performed on an e-commerce website (practicesoftwaretesting.com). Testing includes manual testing, API testing, test automation, and security testing.

I have created and executed 127 test cases with results of 92.9% pass and 7.1% fail. From this testing, I found 9 bugs that need to be fixed, including 3 critical security vulnerabilities.

## Folder Structure

### Tes_Case_Link
This folder contains a link to the Excel file with 127 test cases that I documented in Google Spreadsheet. Test cases cover all main website features:
- Customer Registration (12 test cases)
- User Login (14 test cases)
- My Account Page (12 test cases)
- Home - Product Catalog Feature (11 test cases)
- Categories Feature - Hand Tools (13 test cases)
- Categories Feature - Power Tools (18 test cases)
- Categories Feature - Special Tools (11 test cases)
- Categories Feature - Rentals (3 test cases)
- Sub-section: Product Detail Page - Rentals (10 test cases)
- Contact Feature (11 test cases)
- Security Negative Testing (12 test cases)

Each test case has complete documentation including TC ID, priority, type, pre-condition, test steps, test data, expected result, actual result, status (PASS/FAIL), additional notes, severity, and JIRA link for bug tracking.

### Manual_Testing
This folder contains documentation of manually executed test cases. Inside this folder are screenshots of testing results, bug reports, and security vulnerability findings.

Structure is divided by feature:
- Categories Feature - Power Tools
- Categories Feature - Rentals
- Categories Feature - Special Tools
- Categories Feature - Hand Tools
- Contact Feature
- Customer Registration Feature
- Home_Product Catalog Feature
- Login Feature
- My Account Page
- Security Negative Test

### Bug_Reporting_JIRA
This folder contains complete bug reports I created in JIRA format. Each bug is documented with industry-standard format that includes:
- Bug ID and tracking number
- Clear title and description
- Priority/Severity level
- Detailed steps to reproduce
- Expected vs Actual result
- Screenshot as evidence
- Bug labels and categories
- Security impact analysis

Total 9 bug reports in PDF format:
- BW-1: Stored XSS vulnerability in First Name field (Registration)
- BW-2: Reflected XSS vulnerability in search bar
- BW-3: No brute force protection on Login
- BW-4: Application does not properly handle invalid category URLs
- BW-5: Password validation error message for missing uppercase is misleading
- BW-6: Register button not disabled before fields are filled
- BW-7: Misleading error message about empty file attachments
- BW-8: Filter state lost on page refresh
- BW-9: Password validation error message for missing special character not informative

### tes_api
In this folder, I document API testing performed with Postman. Testing covers several important endpoints:
- Login endpoint (POST)
- Get Products endpoint (GET)
- Add to Cart endpoint (POST)
- User Profile endpoint (GET)
- Negative test cases

From testing results, all endpoints run according to expectations with good response time and appropriate status codes.

### tes_automation
This folder contains test automation scripts I created with Selenium. Several automation scripts have been created for testing main features:
- Login automation
- Product search automation
- Product filtering automation
- Add to cart automation

### CV_QA
This folder contains my CV in PDF format which includes:
- Professional profile
- Work experience and projects
- Technical skills (Manual Testing, Automation, API Testing, Security Testing)
- Tools mastered (Selenium, Postman, JIRA, Excel, etc.)
- Certifications and training
- Contact information

## Testing Results

| Metric | Count | Percentage |
|--------|-------|------------|
| Total Test Cases | 127 | 100% |
| Status PASS | 118 | 92.9% |
| Status FAIL | 9 | 7.1% |

### Test Case Breakdown

| No | Feature | Positive | Negative | Total |
|----|---------|----------|----------|-------|
| 1 | Customer Registration | 3 | 9 | 12 |
| 2 | Login | 8 | 6 | 14 |
| 3 | My Account Page | 11 | 1 | 12 |
| 4 | Home - Product Catalog Feature | 11 | - | 11 |
| 5 | Categories Feature - Hand Tools | 13 | - | 13 |
| 6 | Categories Feature - Power Tools | 17 | 1 | 18 |
| 7 | Categories Feature - Special Tools | 5 | 6 | 11 |
| 8 | Categories Feature - Rentals | 3 | - | 3 |
| 9 | Product Detail Page - Rentals | 10 | - | 10 |
| 10 | Contact Feature | 5 | 6 | 11 |
| 11 | Security Negative Testing | - | 12 | 12 |

### Bugs Found

#### Critical Severity (3 bugs)

**1. SEC-004: Stored XSS in Registration Form**
- **Severity**: Critical
- **Location**: First Name field on registration page
- **Issue**: Malicious scripts can be stored in database and executed when user data is displayed
- **Reproduction**: Input `<script>alert('XSS')</script>` in First Name field
- **Impact**: Risk of session theft, cookie theft, and malicious script injection that threatens other users
- **Bug Report**: BW-1 - Documented in JIRA format

**2. SEC-006: Reflected XSS in Search Bar**
- **Severity**: Critical
- **Location**: Search bar on Home page
- **Issue**: Search input is not sanitized so scripts can be executed immediately
- **Reproduction**: Search with input `<script>alert('Hacked')</script>`
- **Impact**: Can be used for phishing, cookie theft through shared links
- **Bug Report**: BW-2 - Documented in JIRA format

**3. SEC-007: No Brute Force Protection**
- **Severity**: Critical
- **Location**: Login page
- **Issue**: No login attempt limitation or CAPTCHA
- **Impact**: Passwords can be guessed with unlimited attempts (brute force attack)
- **Bug Report**: BW-3 - Documented in JIRA format

#### High Severity (1 bug)

**4. CAT-ST-007: Invalid Category URL Handling**
- **Severity**: High
- **Location**: Categories page
- **Issue**: Application displays network error for invalid category URLs instead of 404 page
- **Impact**: Poor error handling impacts user experience and SEO
- **Bug Report**: BW-4 - Documented in JIRA format

#### Medium Severity (5 bugs)

**5. REG-007: Password Validation - Missing Uppercase**
- **Severity**: Medium
- **Issue**: Error message is inaccurate and misleading
- **Expected**: "Password must contain at least 1 uppercase letter"
- **Actual**: "Password can not include invalid characters"
- **Impact**: Poor user experience due to confusing error message
- **Bug Report**: BW-5 - Documented in JIRA format

**6. REG-012: Register Button Not Disabled**
- **Severity**: Medium
- **Issue**: Register button can be clicked before required fields are filled
- **Expected**: Register button should be disabled until all required fields are filled
- **Actual**: Button is clickable and multiple errors appear simultaneously
- **Impact**: Poor user experience, users can submit empty forms
- **Bug Report**: BW-6 - Documented in JIRA format

**7. CNT-001: Misleading Error Message**
- **Severity**: Medium
- **Issue**: Error message "Currently we only allow empty files" appears even when no file is uploaded
- **Expected**: Message sent successfully or specific error if there's a problem
- **Actual**: Irrelevant error appears
- **Impact**: User confusion and inability to send message
- **Bug Report**: BW-7 - Documented in JIRA format

**8. CAT-ST-008: Filter State Lost on Page Refresh**
- **Severity**: Medium
- **Issue**: Selected filters are lost when page is refreshed
- **Expected**: Filter state is saved and remains active after refresh
- **Actual**: Filters return to default after refresh
- **Impact**: Users must reselect filters every time they refresh the page
- **Bug Report**: BW-8 - Documented in JIRA format

**9. REG-008: Password Validation - Missing Special Character**
- **Severity**: Medium
- **Issue**: Error message is not informative about required special characters
- **Expected**: "Password must contain at least 1 special character"
- **Actual**: "Password can not include invalid characters"
- **Impact**: Users don't know what's wrong with their password
- **Bug Report**: BW-9 - Documented in JIRA format

## Testing Methodology

**Test Case Design**
- Created based on requirements and user stories
- Using Equivalence Partitioning and Boundary Value Analysis techniques
- Covering positive and negative scenarios
- Focus on user journey and critical path

**Test Execution**
- Manual testing for functional and UI testing
- Automation testing using Selenium for regression tests
- API testing with Postman for backend validation
- Security testing to find vulnerabilities (XSS, SQL Injection, Authentication)

**Bug Reporting**
- Bugs documented in industry-standard JIRA format
- Complete documentation: Bug ID, title, description, priority/severity
- Detailed and developer-friendly steps to reproduce
- Clear Expected vs Actual results
- Screenshots and visual evidence for each bug
- Bug labels and categories (functional, security, UI, validation)
- Security impact analysis for critical bugs

## Tools Used

- **Google Spreadsheet** - Test case documentation
- **Postman** - API testing and documentation
- **Selenium WebDriver** - Test automation
- **Browser DevTools** - Debugging and inspection
- **JIRA/Atlassian** - Bug tracking, project management, and issue documentation
- **Screenshot Tools** - Visual bug documentation
- **Git/GitHub** - Version control and portfolio documentation

## Skills Demonstrated

### Manual Testing
- Functional Testing
- UI/UX Testing
- Negative Testing
- Validation Testing
- Exploratory Testing

### Automation Testing
- Selenium WebDriver
- Test Script Development
- Page Object Model
- Test Framework Setup

### API Testing
- REST API Testing
- Postman Collection Development
- Request/Response Validation
- API Status Code Validation
- Negative API Testing

### Security Testing
- XSS (Cross-Site Scripting) Testing
- SQL Injection Testing
- CSRF Protection Testing
- Authentication Testing
- Authorization Testing
- Brute Force Testing
- Input Validation Testing

### Documentation
- Test Case Documentation
- Bug Reporting with JIRA
- Test Summary Report
- Severity Classification
- Test Plan Creation

## Severity Classification

| Level | Description | Example |
|-------|-------------|---------|
| Critical | System crash, data loss, security breach that threatens user security | XSS vulnerability, SQL Injection, No brute force protection |
| High | Main feature not functioning properly or poor error handling | Login fails with valid credentials, 404 page not displayed |
| Medium | Feature works but has UX, validation, or error message issues | Unclear error message, improper button state |
| Low | Typo, alignment, incorrect color, minor UI issues | Label typo, inconsistent spacing |

## Website Tested

**URL**: https://practicesoftwaretesting.com  
**Type**: E-commerce Website  
**Testing Period**: December 2025  
**Browser**: Chrome, Firefox  
**Testing Environment**: Production

## Recommendations

Based on testing results, here are the recommended priorities for fixes:

### Critical Priority
1. Implement input sanitization to prevent XSS attacks
2. Add rate limiting and CAPTCHA for brute force protection
3. Implement Content Security Policy (CSP)
4. Review and fix all input validation across the application

### High Priority
5. Fix error handling for invalid URLs (display 404 page)
6. Implement proper session management

### Medium Priority
7. Fix all error messages to be more informative and user-friendly
8. Implement state management for filters (save in URL parameters)
9. Disable submit button until form is valid
10. Improve password validation feedback with real-time indicator

## Contact

**Email**: erlinanainggolan130104@gmail.com  
**LinkedIn**: https://www.linkedin.com/in/erlina-febiola-nainggolan-293b11368/  
**GitHub**: https://github.com/Erlina130104  
**Portfolio JIRA**: https://erlina-qa-portfolio.atlassian.net

---

Thank you for viewing my portfolio. This documentation was created to demonstrate my capabilities in Quality Assurance and Software Testing.