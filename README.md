# node-aws-beanstack

Simple application deployment with GitHub actions and automatic HTTPS certification using letsencrypt in Elastic Beanstalk's single-instance environment, with automatic certificate renewal using a cron job.

## What needs to change (configuration)

- `.platform\hooks\postdeploy\00_get_certificate.sh`
  - Replace "DOMAIN" and EMAIL placeholders
- `.platform\nginx\conf.d\https-listener.conf`
  - Replace "DOMAIN" placeholders
- `.github\workflows\deploy-to-eb.yml`
  - S3Bucket with your s3 bucket id
  - `APPLICATION_NAME` with the name of your beanstack application
  - `BS_ENV_NAME` with environment name
- Set up a secret in your github repository
  - `ACCESS_KEY_ID` your IAM access key
  - `SECRET_ACCESS_KEY` your secret IAM access key

AND we're done, happy deployment ;)
