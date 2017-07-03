# Course Viewer Actions

## lunchbox.course_viewer.header
Outputs whatever you echo to the head of the Lunchbox course viewer.

```php
add_action('lunchbox.course_viewer.header', function() {
	echo '<style>body { background-color: red; }</style>';
});
```

## lunchbox.course_viewer.footer
Outputs whatever you echo to the footer of the Lunchbox course viewer.

```php
add_action('lunchbox.course_viewer.footer', function() {
	echo '<style>body { background-color: red; }</style>';
});
```
