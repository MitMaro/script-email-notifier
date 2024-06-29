# Script Email Notifier

[![GitHub license](https://img.shields.io/badge/license-ISC-blue.svg)](https://raw.githubusercontent.com/MitMaro/script-email-notifier/master/LICENSE.md)

A script runner that will automatically send an email on script failure.

## Requirements

The script has been tested with the follow. Other versions may also work.

- Bash >= 5.1
- sendemail >= 1.56

## Install

Simply clone this repository.

```shell
git clone https://github.com/MitMaro/script-email-notifier
```

Place the script on your `PATH`, or use the full path to the script.

## Update

To update, from the project directory, run:

```shell
git pull
``` 

## Usage

The script will automatically run the provided script:

```shell
email-notify ./my/script script arguments
```

### Configuration

The script is configured using environment variables. These environment variables can be set globally in your shell profile, provided during the script execution, or through any other mechanism for setting environment variables.

```shell
EMAILNOTIFY_FROM='me@example.com' email-notify
```

| name                  | default              | required | description                              |
|-----------------------|----------------------|----------|------------------------------------------|
| EMAILNOTIFY_SERVER    |                      | Yes      | The SMTP server to send the email using. |
| EMAILNOTIFY_TO        |                      | Yes      | The email address to send the email.     |
| EMAILNOTIFY_SUBJECT   | Script Failed To Run | No       | The subject of the sent email.           |
| EMAILNOTIFY_FROM      | admin@<hostname>     | No       | The email who is sending the email.      |
| EMAILNOTIFY_SENDEMAIL | sendemail            | No       | The name or path to `sendemail`          |

## Use case

This script is used to send an email when cron jobs fails, or to alert on the failure of a background script.

## License

Server Rsync Backup is released under the ISC license. See [LICENSE](LICENSE).
