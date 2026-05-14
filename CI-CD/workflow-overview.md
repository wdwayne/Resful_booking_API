# CI/CD Workflow Overview

This project uses GitHub Actions to automate API test execution.

## Workflow Steps
1. Checkout repository
2. Install Node.js dependencies
3. Execute Newman collection
4. Generate HTML report
5. Upload report artifact

## Trigger
- Push to main branch
- Pull requests