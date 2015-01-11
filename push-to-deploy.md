# Push to deploy

* [GitHub setup](#github-setup)
* [Bitbucket setup](#bitbucket-setup)

If you have a WP Pusher Pro license, you can enable push to deploy for your packages. Push to deploy means that WP Pusher will automatically update your themes and plugins whenever you push to either GitHub or Bitbucket. This works by GitHub or Bitbucket sending a POST request to a special URL on your WordPress site (a webhook) whenever something is changed.

## GitHub setup

First of all, you need to navigate to the WP Pusher dashboard, by clicking "WP Pusher Pro" in the left side menu. Here, you will find your unique "Push to deploy URL". Remember to keep this URL secret, since it contains a secret token. You can always choose to generate a new token, by clicking the button "Refresh token", as long as you remember to update all the webhooks you have set up on GitHub or Bitbucket afterwards. Copy the "Push to deploy URL".

In order to set up a webhook, navigate to the settings page of your GitHub repository. Go to "Webhooks & Services" and click "Add webhook". Paste the "Push to deploy URL" in the field "Payload URL", leave the defaults and click "Add webhook". Now, the only thing you need is to tick the checkbox for "Push to deploy" on the "WP Pusher Pro" -> "All plugins / themes" page.

## Bitbucket setup

First of all, you need to navigate to the WP Pusher dashboard, by clicking "WP Pusher Pro" in the left side menu. Here, you will find your unique "Push to deploy URL". Remember to keep this URL secret, since it contains a secret token. You can always choose to generate a new token, by clicking the button "Refresh token", as long as you remember to update all the webhooks you have set up on GitHub or Bitbucket afterwards. Copy the "Push to deploy URL".

In order to set up a webhook, navigate to the settings page of your Bitbucket repository. Go to "Integrations" -> "Hooks". Select "POST" in the dropdown list and click "Add hook". Paste the "Push to deploy URL" and click "Save". Now, the only thing you need is to tick the checkbox for "Push to deploy" on the "WP Pusher Pro" -> "All plugins / themes" page.
