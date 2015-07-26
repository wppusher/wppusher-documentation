# Push to deploy

* [GitHub setup](#github-setup)
* [Bitbucket setup](#bitbucket-setup)
* [GitLab setup](#gitlab-setup)
* [301 Troubleshooting](#301-troubleshooting)

Push to deploy means that WP Pusher will automatically update your themes and plugins whenever you push to GitHub, Bitbucket or GitLab. This works by GitHub or Bitbucket sending a POST request to a special URL on your WordPress site (a webhook) whenever something is changed.

Each plugin or theme has its own unique Push-to-Deploy URL. This URL is listen under "WP Pusher" > "Plugins / Themes" for each package. Remember to keep this URL secret, since it contains a secret token. Copy the "Push to deploy URL".

## GitHub setup

In order to set up a webhook, navigate to the settings page of your GitHub repository. Go to "Webhooks & Services" and click "Add webhook". Paste the "Push to deploy URL" in the field "Payload URL", leave the defaults and click "Add webhook". Now, the only thing you need is to make sure Push-to-Deploy is enabled for the particular plugin or theme in WP Pusher.

## Bitbucket setup

In order to set up a webhook, navigate to the settings page of your Bitbucket repository. Go to "Integrations" -> "Webhooks" and click "Add webhook". Enter a name and paste the Push-to-Deploy URL. Click "Save". Now, the only thing you need is to make sure Push-to-Deploy is enabled for the particular plugin or theme in WP Pusher.

## GitLab setup

In order to set up a webhook, navigate to the settings page of your GitLab repository. Go to "Web Hooks". Paste the "Push to deploy URL" and select "Push events". Click "Add Web Hook". Now, the only thing you need is to make sure Push-to-Deploy is enabled for the particular plugin or theme in WP Pusher.

## 301 troubleshooting

If nothing happens when you push to GitHub and you see nothing in the WP Pusher log, you most probably have a redirect problem. If you use GitHub, you can check the response from the webhook. If this is a 301 redirect response, WordPress and WP Pusher never got the webhook payload from GitHub (or Bitbucket or GitLab). This problem is caused when WordPress and your webserver is configured differently. Most probably, one has a trailing backslash and the other hasn't. WP Pusher uses WordPress' `site_url` to generate the Push-to-Deploy URL, so if this does not include a trailing backslash when the server is configured to add one, this will cause a redirect. GitHub (or Bitbucket or GitLab) will not follow a redirect, so neither WordPress nor WP Pusher will know anything about the webhook and nothing will be updated.

Let's say you have entered the following Push-to-Deploy URL and see a 301 redirect response:

```
http://blog.wppusher.com?wppusher-hook&token=12345678
```

Adding a backslash will solve the issue in most cases:

```
http://blog.wppusher.com/?wppusher-hook&token=12345678
```
