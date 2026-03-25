# Uptime Monitoring

This repository now includes a GitHub Actions workflow that checks endpoint uptime every 10 minutes.

## Workflow

- File: `.github/workflows/uptime-monitor.yml`
- Trigger:
  - Scheduled: every 10 minutes
  - Manual: **Actions -> Uptime monitor -> Run workflow**

## Configure the URL

Set one of the following in your GitHub repository settings:

1. **Repository variable** (recommended): `UPTIME_URL`
2. **Repository secret**: `UPTIME_URL`

The workflow also accepts a manual input (`url`) when run with `workflow_dispatch`.

## Expected response

The check succeeds for HTTP status codes in the `2xx`-`3xx` range and fails otherwise.

## Notes

- If your app exposes a dedicated health endpoint, prefer using that (for example `/health`).
- If no URL is configured, the workflow fails with a clear error.
