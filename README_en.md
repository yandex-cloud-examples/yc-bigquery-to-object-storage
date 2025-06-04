# Exporting data from Google Big Query to Yandex Cloud Object Storage

This script is designed to export selected tables from Google Big Query to Google Storage and copy the exported data to your Yandex Cloud Object Storage.

What the script needs to run correctly:

1. One Google Storage bucket and one Yandex Object Storage bucket.
1. Google Cloud service account with access to your BigQuery project (`editor` for the BQ project) and GS bucket (`uploader`).
1. Yandex Cloud service account with OBS bucket access (`uploader`).
1. JSON file with your credentials for the GCP service account.
1. Access key for your Yandex Cloud service account.

Steps to follow:

1. Download the [CLI google-cloud-sdk](https://cloud.google.com/sdk/docs/install) utilities.
1. This script only refers to `gsutil`; however, it requires [gcloud CLI](https://cloud.google.com/sdk/docs/authorizing#authorizing_with_a_service_account) authentication.
1. Install [Google BigQuery Python SDK](https://github.com/googleapis/python-bigquery).
1. For the `bigquery` package to work as intended, provide the path to your JSON file in the `GOOGLE_APPLICATION_CREDENTIALS` environment variable.
1. For the `gsutil` utility to run correctly, specify the appropriate custom parameters in the `.boto` file and provide the path to that file in the `BOTO_CONFIG` environment variable.
1. Required arguments for the script to run: `--bq_project`, `--gs_bucket`, `--bq_location=US`, and `--yc_bucket`.
1. The `--gsutil_path` argument is optional. Specify it where your `PATH` variable does not provide the `gsutil` path.
