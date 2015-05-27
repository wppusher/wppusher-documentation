# Push to deploy

* [GitHub setup](#github-setup)
* [Bitbucket setup](#bitbucket-setup)
* [GitLab setup](#gitlab-setup)
* [301 Troubleshooting](#301-troubeshooting)

If you have a WP Pusher Pro license, you can enable push to deploy for your packages. Push to deploy means that WP Pusher will automatically update your themes and plugins whenever you push to either GitHub or Bitbucket. This works by GitHub or Bitbucket sending a POST request to a special URL on your WordPress site (a webhook) whenever something is changed.

## GitHub setup

First of all, you need to navigate to the WP Pusher dashboard, by clicking "WP Pusher" in the left side menu. Here, you will find your unique "Push to deploy URL". Remember to keep this URL secret, since it contains a secret token. You can always choose to generate a new token, by clicking the button "Refresh token", as long as you remember to update all the webhooks you have set up on GitHub or Bitbucket afterwards. Copy the "Push to deploy URL".

In order to set up a webhook, navigate to the settings page of your GitHub repository. Go to "Webhooks & Services" and click "Add webhook". Paste the "Push to deploy URL" in the field "Payload URL", leave the defaults and click "Add webhook". Now, the only thing you need is to tick the checkbox for "Push to deploy" on the "WP Pusher" -> "Plugins / Themes" -> "Edit plugin / theme" page.

## Bitbucket setup

First of all, you need to navigate to the WP Pusher dashboard, by clicking "WP Pusher" in the left side menu. Here, you will find your unique "Push to deploy URL". Remember to keep this URL secret, since it contains a secret token. You can always choose to generate a new token, by clicking the button "Refresh token", as long as you remember to update all the webhooks you have set up on GitHub or Bitbucket afterwards. Copy the "Push to deploy URL".

In order to set up a webhook, navigate to the settings page of your Bitbucket repository. Go to "Integrations" -> "Hooks". Select "POST" in the dropdown list and click "Add hook". Paste the "Push to deploy URL" and click "Save". Now, the only thing you need is to tick the checkbox for "Push to deploy" on the "WP Pusher" -> "Plugins / Themes" -> "Edit plugin / theme" page.

## GitLab setup

First of all, you need to navigate to the WP Pusher dashboard, by clicking "WP Pusher" in the left side menu. Here, you will find your unique "Push to deploy URL". Remember to keep this URL secret, since it contains a secret token. You can always choose to generate a new token, by clicking the button "Refresh token", as long as you remember to update all the webhooks you have set up in GitLab afterwards. Copy the "Push to deploy URL".

In order to set up a webhook, navigate to the settings page of your GitLab repository. Go to "Web Hooks". Paste the "Push to deploy URL" and select "Push events". Click "Add Web Hook". Now, the only thing you need is to tick the checkbox for "Push to deploy" on the "WP Pusher" -> "Plugins / Themes" -> "Edit plugin / theme" page.

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
