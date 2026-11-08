# Serverless - Monitoring Serverless app with CloudWatch and X-Ray

> Logging and monitoring on AWS.

A hands-on workshop from the [AWS First Cloud Journey](https://github.com/vanhoangkha/aws-first-cloud-journey) series, available in English and Vietnamese.

**Read the workshop online:** https://vanhoangkha.github.io/000085-Logandmonitor/

## Overview

Application monitoring and observation is an important step in application deployment to ensure that all of the application's services are working properly and are capable of handling in the event of a failure. AWS provides a tool to help us do that like AWS CloudWatch, AWS X-Ray, and AWS CloudTrail. In this article, we will learn how to debug AWS Lambda through AWS CloudWatch, monitor Lambda using CloudWatch's built-in metrics or custom metrics that we define, and how trace the API using AWS X-Ray.

Amazon CloudWatch monitors the AWS resources you use and the applications you run in real-time. Use CloudWatch to collect and track metrics, which are variables you can measure for your resources and applications. All the cloud services being used will provide metrics to CloudWatch and automatically display them when accessing the CloudWatch dashboard. CloudWatch also provides the following services: - Metrics: a set of metrics integrated into the AWS services that are being used - Logs: collect and store log files - Events: send notifications in response to events - Alarms: set trigger thresholds (alerts) to trigger an action

## Workshop contents

1. Preparing
2. Monitoring with CloudWatch
   - Debugging with CloudWatch logs
   - Create custom metric
   - Creating Alerts with CloudWatch Alarm
3. Tracing with X-ray
4. Cleanup

## Prerequisites

- An AWS account with permissions to create the resources used in the labs
- Basic familiarity with the AWS Management Console
- [Hugo](https://gohugo.io/installation/) (extended edition) if you want to run the site locally

## Run locally

```bash
git clone https://github.com/vanhoangkha/000085-Logandmonitor.git
cd 000085-Logandmonitor
hugo server
```

Then open http://localhost:1313 in your browser.

## Repository structure

| Path | Purpose |
| --- | --- |
| `content/` | Workshop pages (`*.md` English, `*.vi.md` Vietnamese) |
| `static/` | Images and other static assets |
| `layouts/` | Hugo layout overrides |
| `themes/` | Hugo theme |
| `config.toml` | Site configuration |

## Cost and cleanup

The labs create AWS resources that may incur charges. Complete the **Clean up** chapter when you finish to remove them.

## Contributing

Contributions are welcome. See [CONTRIBUTING.md](CONTRIBUTING.md).

To report a security issue, see [SECURITY.md](SECURITY.md).

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE).
