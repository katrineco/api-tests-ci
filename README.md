# API Test Automation CI/CD

Automated API testing project built with Postman, Newman and GitHub Actions.

## Overview

This project validates NASA's Astronomy Picture of the Day (APOD) API through automated API tests executed in a CI/CD pipeline.

The workflow automatically:

* Runs Postman collections with Newman
* Validates API responses and status codes
* Generates HTML and JSON test reports
* Stores execution logs as artifacts
* Publishes reports using GitHub Pages
* Uses GitHub Secrets for secure API key management

## Tech Stack

https://katrineco.github.io/api-tests-ci/

View the latest automated test execution report published through GitHub Pages.

## Tech Stack

* Postman
* Newman
* GitHub Actions
* GitHub Pages
* NASA APOD API

## Test Scenarios

### Get Full APOD

Validates:

* Status code is 200
* Response time is below the defined threshold

### Get Short APOD

Validates retrieval of APOD data using a simplified request.

### Get Date Ranged APOD

Validates retrieval of APOD entries for a specific date range.

### Get APOD Using Collection Variables

Validates API requests using collection variables and environment configuration.

## CI/CD Pipeline

The pipeline is automatically triggered on:

* Push events
* Pull Requests
* Manual execution via GitHub Actions

Pipeline stages:

1. Checkout repository
2. Setup Node.js
3. Install Newman
4. Execute API test suite
5. Generate reports
6. Upload artifacts
7. Deploy reports to GitHub Pages

## Reports

Generated artifacts:

* HTML Report
* JSON Report
* Newman Execution Log

## Security

The NASA API Key is stored securely using GitHub Secrets and is not exposed in source code or workflow logs.

## Project Structure

```text
.github/
└── workflows/
    └── api-tests.yml

tests/
└── collection.json

reports/
├── index.html
├── results.json
└── newman-log.txt
```

## Author

Katrine Camarini Oyakawa

QA Analyst | API Testing | Test Automation | CI/CD
