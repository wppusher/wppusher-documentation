# Getting Started

Installing and setting up WP Pusher on a WordPress installation is really easy. This short guide will help you get started.

* [Installation](#installation-from-wordpressorg)
* [Setup](#setup)
  * [GitHub](#github)
  * [Bitbucket](#bitbucket)
* [Installing packages](#installing-packages)
* [Managing packages](#managing-packages)

## Installation from WordPress.org

_WP Pusher is no longer available through WordPress.org_

## Setup

WP Pusher **only** requires setup if you are using private repositories.

### GitHub

If you are using private GitHub repositories for your themes or plugins, WP Pusher will need a token to access those. You can see GitHub's guide for creating access tokens [here](https://help.github.com/articles/creating-an-access-token-for-command-line-use/). WP Pusher only needs access to `repo` and `public_repo` in order to work.

### Bitbucket

Bitbucket, like GitHub, does _not_ support downloading zipballs with a token. Therefore, if you are using private repositories on Bitbucket, WP Pusher will need a username and a password. **We strongly recommend** that you create a seperate user on Bitbucket that has **read-only access** to your repositories and use this with WP Pusher.

### GitLab

If you are using GitLab, you will have to add your personal token to WP Pusher. You find the token under "Settings" > "Account". You also have to insert the base url for your GitLab installation. It default to "https://gitlab.com".

## Installing packages

Installing packages (themes or plugins) with WP Pusher is very simple. From the left side menu in your WordPress dashboard, navigate to "WP Pusher" -> "New plugin / theme". Here, you need to specify 3 options:

1. The repository handle: {GitHub or Bitbucket username}/{Repository name}. Example: petersuhm/hello-user-wordpress-plugin.
2. Whether the repository is hosted on GitHub or Bitbucket.
3. Whether the repository is private.
4. You can optionally select "Dry run", which means that the plugin won't actually be installed. It will just be added to the packages that WP Pusher controls. This is useful for already installed plugins. If you choose this option, be aware that the folder name fo the package must exactly match the slug of the repository.

## Managing packages

Packages can be managed and updates by navigating from the left side menu to "WP Pusher" -> "All plugins / themes". From here you can edit the repository name or manually update the package. By clicking "Update plugin / theme", WP Pusher will fetch the newest version of the repository and install it on WordPress.

If you have bought a WP Pusher Pro license, you can also choose to enable [push to deploy](/push-to-deploy.md).
