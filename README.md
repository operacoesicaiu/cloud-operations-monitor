# Cloud Operations Monitor

A centralized monitoring system for tracking the health and performance of cloud-based operations and workflows.

## Overview

This repository serves as the central monitoring hub for all cloud operations, providing real-time status tracking and logging capabilities for various worker services including Google Auth, Zenvia integration, and Zoho integration.

## Features

- **Real-time Monitoring**: Track the status of all cloud operations and workflows
- **Log Aggregation**: Centralized logging system for operational events
- **GitHub Actions Integration**: Automated monitoring triggered by repository dispatch events
- **Secure Operations**: All sensitive data is properly masked and secured

## Architecture

The monitoring system consists of:

- **Log Handler Workflow**: Processes repository dispatch events to update operational status
- **Daily Uptime Log**: Maintains a log of successful operations and system health
- **Secure Logging**: All logs are processed through secure logging functions

## Usage

### Triggering Monitoring Events

Monitoring events are triggered via GitHub repository dispatch events:

```bash
curl -X POST \
  https://api.github.com/repos/operacoesicaiu/cloud-operations-monitor/dispatches \
  -H 'Authorization: token YOUR_GITHUB_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{
    "event_type": "log_event",
    "client_payload": {
      "message": "Operation completed successfully"
    }
  }'
```

### Monitoring Workflows

The system monitors the following operations:
- Google Authentication workflows
- Zenvia SMS/communication integration
- Zoho CRM data synchronization
- Report generation and data export

## Security Features

- **Data Masking**: All sensitive information is automatically masked in logs
- **Secure Logging**: Custom logging functions prevent data exposure
- **Environment Variables**: All credentials stored securely as environment variables
- **Minimal Permissions**: GitHub Actions workflows use minimal required permissions

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests for your changes
5. Submit a pull request

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Support

For support and questions, please contact the development team.