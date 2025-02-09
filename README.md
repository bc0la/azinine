# Azinine

```text
 ░▒▓██████▓▒░  ░▒▓████████▓▒░ ░▒▓█▓▒░ ░▒▓███████▓▒░  ░▒▓█▓▒░ ░▒▓███████▓▒░  ░▒▓████████▓▒░
░▒▓█▓▒░░▒▓█▓▒░        ░▒▓█▓▒░ ░▒▓█▓▒░ ░▒▓█▓▒░░▒▓█▓▒░ ░▒▓█▓▒░ ░▒▓█▓▒░░▒▓█▓▒░ ░▒▓█▓▒░
░▒▓█▓▒░░▒▓█▓▒░      ░▒▓██▓▒░  ░▒▓█▓▒░ ░▒▓█▓▒░░▒▓█▓▒░ ░▒▓█▓▒░ ░▒▓█▓▒░░▒▓█▓▒░ ░▒▓█▓▒░
░▒▓████████▓▒░    ░▒▓██▓▒░    ░▒▓█▓▒░ ░▒▓█▓▒░░▒▓█▓▒░ ░▒▓█▓▒░ ░▒▓█▓▒░░▒▓█▓▒░ ░▒▓██████▓▒░
░▒▓█▓▒░░▒▓█▓▒░  ░▒▓██▓▒░      ░▒▓█▓▒░ ░▒▓█▓▒░░▒▓█▓▒░ ░▒▓█▓▒░ ░▒▓█▓▒░░▒▓█▓▒░ ░▒▓█▓▒░
░▒▓█▓▒░░▒▓█▓▒░ ░▒▓█▓▒░        ░▒▓█▓▒░ ░▒▓█▓▒░░▒▓█▓▒░ ░▒▓█▓▒░ ░▒▓█▓▒░░▒▓█▓▒░ ░▒▓█▓▒░
░▒▓█▓▒░░▒▓█▓▒░ ░▒▓████████▓▒░ ░▒▓█▓▒░ ░▒▓█▓▒░░▒▓█▓▒░ ░▒▓█▓▒░ ░▒▓█▓▒░░▒▓█▓▒░ ░▒▓████████▓▒░
```

A cloud security assessment tool focused on gathering configuration data from Azure and AWS for security reviews and penetration tests. This is not yet pretty or functional and is just the groundwork.

Uses a combo of scoutsuite reports and manual queries as data sources.

## Features

- Interactive TUI interface for easy configuration and execution
- Automated authentication handling for both Azure (Browser & Service Principal) and AWS
- Automated security checks for common misconfigurations
- Direct integration with pwndoc-ng API for automated reporting
- Support for both guided and automated assessment workflows

### Azure Checks (planned)

- [ ] Pull Function App environment vars/source code
- [ ] Storage Blob Access Permissions

### AWS Checks

- [x] Access key last rotate date  via scoutsuite (to add configurable threshold)
- [ ] CloudFormation Template Analysis
- [ ] Lambda Source Code Review
- [ ] Lambda Environment Variables Analysis
- [ ] S3 Bucket Security Configuration Review
- [ ] SQS Queue Configuration Analysis
- [ ] IAM Permission Review

## Getting Started

### Prerequisites

- Go 1.19 or higher
- Valid Azure/AWS credentials
- pwndoc-ng instance (for automated reporting)

### Configuration

Configure the tool using either:

- Interactive configuration wizard in the TUI
- Manual config.json file:

```json
{
  "PwndocUrl": "https://your-pwndoc-instance:8443",
  "PwndocAuditName": "your-audit-name",
  "OutputDir": "/path/to/outputs",
  "ScoutSuiteReportsDir": "~/path/to/scoutsuite/reports",
  "TenantID": "azure-tenant-id",
  "ClientID": "azure-client-id",
  "ClientSecret": "azure-client-secret"
}
```

## Usage

```bash
# Run the TUI interface
./azinine tui

# Additional commands coming soon...
```

## Architecture

- TUI based on [Bubble Tea](https://github.com/charmbracelet/bubbletea)
- Modular design for easy addition of new security checks
- Asynchronous execution with progress tracking
- Automated report generation via pwndoc-ng API

## Contributing

Contributions are welcome! Please feel free to submit pull requests.
