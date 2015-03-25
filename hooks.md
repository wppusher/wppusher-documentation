# Hooks

WP Pusher has 4 kinds of actions that you can use in your WordPress application:

* `wppusher_plugin_was_installed`
* `wppusher_theme_was_installed`
* `wppusher_plugin_was_updated`
* `wppusher_theme_was_updated`

You can use an action like this:

```php
add_action('wppusher_theme_was_installed', 'doSomethingAfterThemeHasBeenInstalled', 10, 1);

doSomethingAfterThemeHasBeenInstalled($stylesheet)
{
    var_dump($stylesheet);
}
```
