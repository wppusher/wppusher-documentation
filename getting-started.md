# Getting Started

Installing and setting up WP Pusher on a WordPress installation is really easy. This short guide will help you get started.

* [Installation](#installation)
* [Setup](#setup)
  * [GitHub](#github)
  * [Bitbucket](#bitbucket)
* [Installing packages](#installing-packages)
* [Managing packages](#managing-packages)

## Installation

* Log in to your WordPress dashboard and navigate to the 'Plugins' page
* Click the 'Add New' button in the top of the page
* Type in 'WP Pusher' in the 'Search Plugins' field
* Identify the WP Pusher plugin on the list and click 'Install Now'
* If asked, confirm that you want to install the plugin by clicking 'OK'
* When the plugin is successfully installed, click the 'Activate Plugin' link
* If WP Pusher was successfully installed, you should now see a menu item called 'WP Pusher' in the sidebar of the dashboard

![Install WP Pusher](https://cloud.githubusercontent.com/assets/1430546/5602678/be84b804-935e-11e4-9afd-aca747bcccb9.png)

## Setup

WP Pusher **only** requires setup if you are using private repositories.

### GitHub

If you are using private GitHub repositories for your themes or plugins, WP Pusher will need a token to access those. You can see GitHub's guide for creating access tokens [here](https://help.github.com/articles/creating-an-access-token-for-command-line-use/). WP Pusher only needs access to `repo` and `public_repo` in order to work.

### Bitbucket

Bitbucket, like GitHub, does _not_ support downloading zipballs with a token. Therefore, if you are using private repositories on Bitbucket, WP Pusher will need a username and a password. **We strongly recommend** that you create a seperate user on Bitbucket that has **read-only access** to your repositories and use this with WP Pusher.

## Installing packages

Installing packages (themes or plugins) with WP Pusher is very simple. From the left side menu in your WordPress dashboard, navigate to "WP Pusher" -> "New plugin / theme". Here, you need to specify 3 options:

1. The repository handle: {GitHub or Bitbucket username}/{Repository name}. Example: petersuhm/hello-user-wordpress-plugin.
2. Whether the repository is hosted on GitHub or Bitbucket.
3. Whether the repository is private.

## Managing packages

Packages can be managed and updates by navigating from the left side menu to "WP Pusher" -> "All plugins / themes". From here you can edit the repository name or manually update the package. By clicking "Update plugin / theme", WP Pusher will fetch the newest version of the repository and install it on WordPress.

If you have bought a WP Pusher Pro license, you can also choose wheth to enable [push to deploy](/push-to-deploy).
