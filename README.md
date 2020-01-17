# action-gcloud-run

An example GitHub Action which published a Docker container to Google Container Registry and then deploys the container to [Google Cloud Run](https://cloud.google.com/run/)

This GitHub Action does the following:

1. Configures the `gcloud` CLI
2. Build the docker image
3. Pushes the docker image to GCP Container Registry
4. Deploys the docker image to GCP Cloud Run

This GitHub Action requires the following config:

- GCP_PROJECT ([secret](https://help.github.com/en/actions/automating-your-workflow-with-github-actions/creating-and-using-encrypted-secrets))
  - The GCP project used for Google Container Registry and Google Cloud Run
- GCP_EMAIL ([secret](https://help.github.com/en/actions/automating-your-workflow-with-github-actions/creating-and-using-encrypted-secrets))
  - The email address of the service account used to run this action
- GCP_REGION ([secret](https://help.github.com/en/actions/automating-your-workflow-with-github-actions/creating-and-using-encrypted-secrets))
  - The region the Google Run service is hosted in
- GCP_KEY ([secret](https://help.github.com/en/actions/automating-your-workflow-with-github-actions/creating-and-using-encrypted-secrets))
  - A based64 encode version of the JSON key for the service account
- IMAGE
  - The name of the container image
- SERVICE
  - The name of the Google Cloud Run service
