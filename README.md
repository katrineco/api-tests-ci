# api-tests-ci

Postman/Newman API test suite for the [NASA APOD API](https://api.nasa.gov/planetary/apod), running on GitHub Actions CI.

Built as part of the Coursera course **Modern API Automation: From Postman to AI-Driven Pipelines**. Developed using VS Code with AI assistance, organized on a feature branch for clean commits.

## Tests

- **Get Full APOD** — full request with expected status 200 and response time < 8000ms
- **Get Short APOD** — minimal GET request
- **Get Short Data Ranged APOD** — date-range query (start_date / end_date)
- **Get Short API Saved In Collections** — GET using a collection-variable API key

## Run locally

```bash
npm install -g newman newman-reporter-htmlextra

newman run collection.json \
  --env-var api_key=YOUR_NASA_API_KEY \
  -r cli,htmlextra \
  --reporter-htmlextra-export reports/report.html
```

## CI

The workflow in `.github/workflows/api-tests.yml` runs on push/PR to `main`, installing Newman and executing the collection with the `NASA_API_KEY` secret from GitHub. An HTML report is uploaded as a build artifact.
