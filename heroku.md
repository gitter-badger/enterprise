# Deploying on Heroku
> Codecov deploys to Heroku easily with a single click.

## Overview
1. Deploy
2. Config


## Deploy
[![Deploy](https://www.herokucdn.com/deploy/button.png)](https://heroku.com/deploy)
> After deployed please configure your environment


## Config

Below is a list of configuration varibles which can be modified to customerize your Enterprise app. Set these values via Heroku CLI: `heroku config:set SETTING=value -a your-codecov-app`

```sh
# Setup
# ---------------------------------
ENTERPRISE_COMPANY  # (required) provided by Codecov staff
ENTERPRISE_LICENSE  # (required) provided by Codecov staff
GUEST_ACCESS        # allow non-logged in users to view public repos
LOGLVL: WARNING     # info, debug or warning
COOKIE_SECRET       # (required) string used to encrypt secure cookies
MEDIA_URL           # (default) static files are served from Codecov's Amazon S3
                    # (localhost) set value to 'localhost' to serve js/css/images locally
                    # (advanced) set value to url to privatly hosting static files for advanced usage

# Services
# ---------------------------------
DATABASE_URL           # (required) postgres url
REDIS_URL              # (required) used for celery and storing reports before processing (REDISCLOUD_URL is backup)
RABBITMQ_URL           # specify to use a rabbitmq as the celery broker
LOGENTRIES_TOKEN       # logging product interactions: https://logentries.com
MAILGUN_ENDPOINT       # Mailgun url to send system emails from
GOOGLE_ANALYTICS_KEY   # front-end tracking
AWS_ACCESS_KEY_ID      #
AWS_SECRET_ACCESS_KEY  #
AWS_BUCKET             # bucket to store archived reports
AWS_HASH_KEY           # random string to encrypt upload path

# Github
# ---------------------------------
GITHUB_CLIENT_ID            # (required) from https://github.com/settings/applications/new
GITHUB_CLIENT_SECRET        # (required) from https://github.com/settings/applications/new
GITHUB_ACCESS_TOKEN         # used to post comments, statuses, etc. Generate a full access token at https://github.com/settings/tokens/new
GITHUB_ORGANIZATIONS        # List of organizations. Users must be a member of at least one. (optional) (default all)
GITHUB_GLOBAL_UPLOAD_TOKEN  # a secret string that is used as a global token for uploading reports

# Github Enterprise
# ---------------------------------
GITHUB_ENTERPRISE_URL                  # (required) the base url of your Github Enterprise ex. https://enterprise-hostname.com
GITHUB_ENTERPRISE_CLIENT_ID            # (required) from https://github.com/settings/applications/new
GITHUB_ENTERPRISE_CLIENT_SECRET        # (required) from https://github.com/settings/applications/new
GITHUB_ENTERPRISE_ACCESS_TOKEN         # used to post comments, statuses, etc.
GITHUB_ENTERPRISE_GLOBAL_UPLOAD_TOKEN  # a secret string that is used as a global token for uploading reports
GITHUB_ENTERPRISE_API_URL              # (optional) the base url of your Github Enterprise API defaults to `GITHUB_ENTERPRISE_URL + "/api/v3"`

# Bitbucket
# ---------------------------------
BITBUCKET_CLIENT_ID            #
BITBUCKET_CLIENT_SECRET        #
BITBUCKET_ACCESS_TOKEN         # (key:secret) used to post comments, statuses, etc.
BITBUCKET_ORGANIZATIONS        # List of teams. Users must be a member of at least one. (optional) (default all)
BITBUCKET_GLOBAL_UPLOAD_TOKEN  # a secret string that is used as a global token for uploading reports

# Gitlab
# ---------------------------------
GITLAB_CLIENT_ID            #
GITLAB_CLIENT_SECRET        #
GITLAB_ACCESS_TOKEN         # used to post comments, statuses, etc.
GITLAB_ORGANIZATIONS        # List of teams. Users must be a member of at least one. (optional) (default all)
GITLAB_GLOBAL_UPLOAD_TOKEN  # a secret string that is used as a global token for uploading reports

# Gitlab Enterprise
# ---------------------------------
GITLAB_ENTERPRISE_URL                  #
GITLAB_ENTERPRISE_CLIENT_ID            #
GITLAB_ENTERPRISE_CLIENT_SECRET        #
GITLAB_ENTERPRISE_ACCESS_TOKEN         # used to post comments, statuses, etc.
GITLAB_ENTERPRISE_GLOBAL_UPLOAD_TOKEN  # a secret string that is used as a global token for uploading reports
```