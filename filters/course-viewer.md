# Course Viewer Filters

## lunchbox.course_viewer.title
Changes the value of the HTML `<title>` element, shown in a browser's title bar or on the course viewer's tab.

```php
add_filter('lunchbox.course_viewer.title', function($title) {
    return 'My even better custom title';
});
```

### Arguments

#### $title `string`
The default title value to be used for the Lunchbox Course Viewer page.

```php
// Default is {$course_title} – {$site_name}
// eg: Creating Video Courses with Lunchbox – Lunchbox 
$title = get_the_title() . ' – ' . get_bloginfo('name');
```
