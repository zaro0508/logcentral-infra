# Overview
Install, configure and manage the AWS logcentral account.

## Central Logging
The purpose of this repo is to manage the Sage central logging account.  The use of a central
logging is an [established best practice](https://aws.amazon.com/blogs/architecture/central-logging-in-multi-account-environments).
It helps security teams detect malicious activities both in real-time and during incident response.
It provides protection to log data in case it is accidentally or intentionally deleted.  It also
helps application teams correlate and analyze log data across multiple application tiers.

## Instructions to create or update CF stacks

```
# unlock repo
git-crypt unlock
# set env vars
source env_vars && source env_vars.secret
# Run sceptre to create or update CF stacks
```

The above should setup resources for the account.  Once the infrastructure for the account has been setup
you can access and view the account using the [AWS console](https://AWS-account-ID-or-alias.signin.aws.amazon.com/console).

*Note - This project depends on CF templates from other accounts.*

## Continuous Integration
We have configured Travis to deploy CF template updates.  Travis deploys using
[sceptre](https://sceptre.cloudreach.com/latest/about.html)

# Contributions

## Issues
* https://sagebionetworks.jira.com/projects/IT

## Builds
* https://travis-ci.org/Sage-Bionetworks/logcentral-infra

## Secrets
* We use [git-crypt](https://github.com/AGWA/git-crypt) to hide secrets.
Access to secrets is tightly controlled.  You will be required to
have your own [GPG key](https://help.github.com/articles/generating-a-new-gpg-key)
and you must request access by a maintainer of this project.
