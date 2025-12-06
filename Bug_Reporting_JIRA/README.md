# Bug Reporting - JIRA Documentation

## Overview
This folder contains comprehensive bug reports for software testing documentation, formatted for JIRA issue tracking system. All bugs have been identified, documented, and categorized by severity level.

## Bug Summary

### Total Bugs Identified: 9

#### Critical Severity (3 bugs)
- [#BW-1] Stored XSS vulnerability found in First Name field on Registration page
- [#BW-2] Reflected XSS vulnerability found in search bar
- [#BW-3] No brute force protection on Login page

#### High Severity (1 bug)
- [#BW-4] Application does not properly handle invalid category URLs

#### Medium Severity (5 bugs)
- [#BW-5] Password validation error message for missing uppercase is misleading
- [#BW-6] Register button not disabled before fields are filled
- [#BW-7] Misleading error message about empty file attachments
- [#BW-8] Filter state lost on page refresh
- [#BW-9] Password validation error message for missing special character not informative

## Security Vulnerabilities Breakdown

### Critical Security Issues (3)
1. Stored XSS in Registration Form
   - Risk: Session theft, cookie theft, malicious script injection
   - Impact: Affects all users who view compromised profiles

2. Reflected XSS in Search Bar
   - Risk: Phishing attacks, cookie theft via malicious links
   - Impact: Can be exploited through shared URLs

3. No Brute Force Protection
   - Risk: Unlimited password guessing attempts
   - Impact: Account compromise through automated attacks

## File Structure
```
Bug_Reporting_JIRA/
├── [#BW-1] Stored XSS vulnerability found in...pdf
├── [#BW-2] Reflected XSS vulnerability found...pdf
├── [#BW-3] No brute force protection on Lo...pdf
├── [#BW-4] Application does not properly h...pdf
├── [#BW-5] Password validation error messa...pdf
├── [#BW-6] Register button not disabled be...pdf
├── [#BW-7] Misleading error message about...pdf
├── [#BW-8] Filter state lost on page refresh.pdf
└── [#BW-9] Password validation error messa...pdf
```

## Bug Categories

### Security Bugs (3)
- XSS vulnerabilities (Stored and Reflected)
- Authentication security (Brute force)

### User Experience Bugs (5)
- Form validation issues
- Error message clarity
- State management

### Error Handling Bugs (1)
- Invalid URL handling

## Document Format

Each bug report contains:
- Bug ID: Unique identifier (BW-1 to BW-9)
- Title: Clear description of the issue
- Priority: Highest/High/Medium
- Type: Bug
- Status: To Do
- Labels: Categorization tags (security, xss, validation, etc.)
- Description: Detailed explanation of the issue
- Steps to Reproduce: Step-by-step guide
- Expected Result: What should happen
- Actual Result: What actually happens
- Impact: Business and security implications
- Attachments: Screenshots and evidence

## Testing Details

- Project: Bug_Website / Practice Software Testing QA
- Reporter: Erlina Febiola Nainggolan
- Created: December 2025
- Status: All bugs are currently in "To Do" status

## Recommended Actions

### Immediate Priority (Critical)
1. Fix all XSS vulnerabilities (BW-1, BW-2)
2. Implement brute force protection (BW-3)

### High Priority
3. Fix invalid URL error handling (BW-4)

### Medium Priority
4. Improve form validation and error messages (BW-5 to BW-9)

## Notes

- All bugs are documented in bilingual format (Indonesian and English)
- Each report includes screenshots for visual reference
- Security bugs require immediate attention due to potential user data compromise
- UX bugs should be addressed to improve user satisfaction and conversion rates

## Contact

QA Engineer: Erlina Febiola Nainggolan  
JIRA Project: Bug_Website  
Documentation Date: December 2025

---

This documentation is part of comprehensive software testing and quality assurance processes.