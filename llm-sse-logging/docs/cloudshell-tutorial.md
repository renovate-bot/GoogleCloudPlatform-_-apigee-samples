# Logging Streaming server-sent events using Apigee

---

- This is a sample Apigee proxy to demonstrate Apigee with LLM workloads that streams server-sent events (SSE). SSE streaming reduces latency, and clients can receive response data as soon as it is generated by an LLM. This feature supports the use of AI agents that operate in real time environments, such as customer service bots or workflow orchestrators. For more info, check out this [page](https://cloud.google.com/apigee/docs/api-platform/develop/server-sent-events)
- In this sample, we will showcase how Apigee can extract the events from the target, consolidate them and send that to Cloud Logging

## Pre-Requisites

1. [Provision Apigee X](https://cloud.google.com/apigee/docs/api-platform/get-started/provisioning-intro)
2. Configure [external access](https://cloud.google.com/apigee/docs/api-platform/get-started/configure-routing#external-access) for API traffic to your Apigee X instance
3. Enable Vertex AI and Cloud Logging in your project
4. Make sure the following tools are available in your terminal's $PATH (Cloud Shell has these preconfigured)
    - [gcloud SDK](https://cloud.google.com/sdk/docs/install)
    - [apigeecli](https://github.com/apigee/apigeecli)
    - unzip
    - curl
    - jq

Let's get started!

---

## Setup environment

Ensure you have an active GCP account selected in the Cloud shell

```sh
gcloud auth login
```

Navigate to the 'llm-sse-logging' directory in the Cloud shell.

```sh
cd llm-sse-logging
```

Edit the provided sample `env.sh` file, and set the environment variables there.

Click <walkthrough-editor-open-file filePath="llm-sse-logging/env.sh">here</walkthrough-editor-open-file> to open the file in the editor

Then, source the `env.sh` file in the Cloud shell.

```sh
source ./env.sh
```

---

## Deploy Apigee configurations

Next, let's deploy the sample to Apigee. Just run

```bash
./deploy-llm-sse-logging.sh
```
---

## Conclusion

<walkthrough-conclusion-trophy></walkthrough-conclusion-trophy>

Congratulations! You've successfully deployed Apigee proxy that will log the SSE response

You can now go back to the [notebook](../llm_sse_logging_v1.ipynb) to test the sample.

<walkthrough-inline-feedback></walkthrough-inline-feedback>

## Cleanup

If you want to clean up the artifacts from this example in your Apigee Organization, first source your `env.sh` script, and then run

```bash
./clean-up-llm-sse-logging.sh
```
