# File Downloader and AWS S3 Uploader

This script automates the process of downloading a file from a specified URL and then uploading it to an AWS S3 bucket.

## Description

When executed, this script will:
1. Download a file from a given URL.
2. If the download is successful, the file will be uploaded to a specified S3 bucket.
3. Email notifications will be sent upon success or failure of the download and upload operations.

## Prerequisites

- AWS CLI configured with the necessary permissions to write to the specified S3 bucket.
- A mail system (like `sendmail` or `postfix`) configured to send emails from the server executing the script.
- `wget` installed for downloading files.

## Configuration

Before using the script, you need to replace the placeholder values in the following variables:

- `S3_BUCKET_NAME`: Name of your AWS S3 bucket.
- `EMAIL_RECIPIENT`: Email address where you wish to receive notifications.
- `URL`: The URL from which the file needs to be downloaded.
- `TEMP_FILE`: The temporary location (including filename) to store the downloaded file.

## Usage

To run the script, simply execute:

```bash
./<script_name>.sh
```

Replace `<script_name>` with the name you've given to the script.

## Notifications

After a successful file download and its upload to S3, an email will be sent with the subject "File Upload Success". If there's any failure during these operations, appropriate emails with subjects "File Upload Failed" or "File Download Failed" will be sent.

## Cleanup

The script ensures that any temporary files created during its execution will be removed post-operation.

## Author

- **Pubudu Dias** - *Initial work* - [Date: 2023/04/20]

## Note

Avoid hardcoding sensitive information, such as URLs that might change or be confidential, directly in the script. Use environment variables or a configuration file. Always be cautious when automating file downloads and uploads, ensuring secure and reliable sources and destinations.