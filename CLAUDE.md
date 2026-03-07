# CLAUDE.md

## Project Overview

RETOLD is a Node.js project skeleton configured for deployment to Azure Web Apps. The repository is in its early stages with no application code yet — only CI/CD infrastructure and a `.gitignore` file exist.

## Repository Structure

```
RETOLD/
├── .github/
│   └── workflows/
│       └── azure-webapps-node.yml   # CI/CD: build, test, deploy to Azure
├── .gitignore                        # Git ignore rules (VS/C# template — needs updating for Node.js)
└── CLAUDE.md                         # This file
```

## Tech Stack

- **Runtime**: Node.js 20.x
- **Package Manager**: npm
- **Deployment**: Azure Web Apps via GitHub Actions

## Development Setup

No `package.json` exists yet. To initialize:

```sh
npm init -y
```

## Build & Test Commands

The CI pipeline runs these commands (all use `--if-present` so they are optional until configured):

```sh
npm install
npm run build --if-present
npm run test --if-present
```

No testing framework, linter, or formatter is configured yet.

## CI/CD Pipeline

**File**: `.github/workflows/azure-webapps-node.yml`

- **Triggers**: Push to `main`, or manual dispatch
- **Build**: Ubuntu latest, Node.js 20.x, npm install/build/test
- **Deploy**: Azure Web Apps (requires `AZURE_WEBAPP_PUBLISH_PROFILE` secret)
- **Note**: The `AZURE_WEBAPP_NAME` env var is still set to the placeholder `"your-app-name"`

## Git Conventions

- Default remote branch: `main`
- Local legacy branch: `master` (points to same initial commit)

## Current State & Notes

- No application source code exists yet
- The `.gitignore` is a Visual Studio/C# template and should be replaced with a Node.js-appropriate one when development begins
- Azure deployment secrets and app name are not yet configured
