# Logging

This article goes into detail about how the Lunchbox logging system works so that you can explore the plugin logs to determine what is happening behind the scenes and so you can use it with your own custom integrations.

Lunchbox has a custom table that captures any logged data. The table name is `{$wpdb->prefix}_lunchbox_logs`

The main Lunchbox instance has a `log` property which contains the `Logger` class. To use it, simply call the main `Lunchbox()` function and access the log property.

If you'd like to include any data along with your log, simply pass an array with a key of `payload`.

### Basic Example

```php
  // Log an interesting event
  Lunchbox()->log->info( __('Lunchbox is a neat tool', 'lunchbox') );

  // Log a warning
  Lunchbox()->log->warn( __('Something bad happened', 'lunchbox'), array('payload' => json_encode($data) ) );
```

## Using logging levels

Logging levels should be used to help determine the priority of the information that is being logged. The following methods are available on the `log` property to add logged information at different priority levels.

```php
  debug()     // Detailed debug information
  info()      // Interesting events
  notice()    // Uncommon events
  warn()      // Exceptional occurrences that are not errors
  error()     // Runtime errors
  critical()  // Critical conditions
  alert()     // Action must be taken immediately
```

## Using logging channels

It can be helpful to set a specific channel that your log should be recorded with so you can easily find all logs related to that channel in the future. To do this, simply call the `withName` method on the `log` property, passing the name of the channel that you'd like the log to be recorded in.

### Example

```php
  Lunchbox()->log->withName('lunchbox.integrations')->debug('Here is more information', array('payload' => json_encode($data) ) );
```
