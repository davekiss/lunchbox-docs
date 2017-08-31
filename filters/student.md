# Student Filters

## lunchbox.student.courses.show
Modify the individual list items output for the courses that the current student is enrolled in. This is triggered by the `[lunchbox.student.courses.show]` shortcode.

```php
add_filter('lunchbox.student.courses.show', function($list_item, $args, $course, $student) {
	$list_item = '<li><a href="mycoolwebsite.com">' . $course->title . '</a></li>';
	return $list_item;
});
```

### Arguments

#### $list_item `string`
The default list item entry for the link to the course that the student is enrolled in.

```php
sprintf('<li><a class="is-lunchbox-course-link %1$s" href="%2$s" title="%3$s">%3$s</a></li>', $args['class'], $course->link, $course->title )
```

#### $args `array`
The options passed to the shortcode.

```php
	$args = wp_parse_args( $args, array(
	  'class' => '',
	) );
```

#### $course `Lunchbox\Model\Course object`

#### $student `Lunchbox\Model\Student object`
