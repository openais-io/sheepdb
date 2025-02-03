<p align="center">
  <img src="assets/logo.jpeg" alt="SheepDB Logo" width="200">
</p>

# SheepDB

SheepDB is a lightweight service that uses Google Spreadsheets as a storage backend. It provides both a CLI interface and an API server for managing your data.

## Features

- 🔄 Use Google Spreadsheets as a database
- 🚀 Simple CLI interface for data management
- 🌐 RESTful API server
- 📊 Easy data querying and manipulation
- 🔐 Secure authentication for API endpoints

## Prerequisites

- Google Cloud Project with enabled Google Sheets API
- Google Service Account credentials

For detailed instructions on setting up these prerequisites, please refer to our [Setup Guide](./HOW-TO.md).

## Installation

You can download the latest release from [here](https://github.com/openais-io/sheepdb/releases).

## Configuration

Configure the required environment variables by either setting them directly or using a .env file located in the same directory as the SheepDB executable:

```bash
GOOGLE_CLIENT_EMAIL=your-service-account@project.iam.gserviceaccount.com
GOOGLE_PRIVATE_KEY=your-service-account-private-key # You can get the value from the service-account.json file
GOOGLE_SPREADSHEET_ID=your-spreadsheet-id
API_KEY=your-api-key  # Required for API server
```

**IMPORTANT:** After configuring your environment variables, remember to grant "Editor" access to your Google Spreadsheets for the email address specified in GOOGLE_CLIENT_EMAIL.

## CLI Usage

SheepDB provides several commands for managing your spreadsheet data.

```bash
sheepdb --help
```

### Sheet Management

```bash
# Get sheet data
sheepdb sheet get <sheet-name>

# Create a new sheet
sheepdb sheet create <sheet-name> --columns "column1,column2,column3"

# Delete a sheet
sheepdb sheet delete <sheet-name>

# Add a row to a sheet
sheepdb sheet add-row <sheet-name> --data "value1,value2,value3"

# More detail
sheepdb sheet --help
```

### API Server

Start the API server:

```bash
sheepdb api-server start --port 9091
```

## API Endpoints

The API server provides RESTful endpoints for interacting with your spreadsheet:

- `GET /api/v1/sheets/:name` - Get sheet data
- `POST /api/v1/sheets` - Create a new sheet
- `DELETE /api/v1/sheets/:name` - Delete a sheet
- `POST /api/v1/sheets/:name/rows` - Add a row to a sheet

API documentation is available at `/docs` when running the server.

## Version

Current version: v0.3.0

## Troubleshooting

If you encounter any issues, please open an issue on GitHub.

## License

Apache License 2.0

Copyright (c) 2025 OpenAIS

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
