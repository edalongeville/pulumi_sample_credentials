# pulumi_sample_credentials
Demo for issue: https://github.com/pulumi/pulumi-aws/issues/1340

## Requirements:
 - An AWS SSO setup and ready to use (https://docs.aws.amazon.com/singlesignon/latest/userguide/what-is.html)
 - Python 3.8.x
 - awscli Version 2 (https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2.html)
 - Poetry (https://python-poetry.org/docs/)
 - Pulumi (https://www.pulumi.com/docs/get-started/install/#installing-pulumi)

## How to reproduce the issue
This was tested on a clean install of Ubuntu.
 - Clone this repo.
 - `python3 -m venv .venv; source .venv/bin/activate`
 - `poetry install`
 - `poetry run pulumi up` Will confirm your are not authenticated
 - Copy the content of aws_config to ~/.aws/config, fill in the missing values.
 - `aws sso login`
 - `poetry run pulumi up`