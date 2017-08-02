# Enrollment Filters

## lunchbox.enrollment.drip.available_at
Modify the individual availability date and time for each lesson in the course that the current student just enrolled in.

This is triggered when a student enrolls in a course that has drip settings enabled.

```php
add_filter('lunchbox.enrollment.drip.available_at', function($date_available, $modifier, $period, $drip_type, $enrollment, $course, $lesson, $now) {
	$beginning_of_day = $date_available->setTime(00, 00, 00);
	return $beginning_of_day;
});
```

### Arguments

#### $date_available `DateTime`
The precalculated date and time that the passed lesson is available on.

#### $modifier `int`
The calculated offset for the number of periods from now that the passed lesson is available on.

#### $period `string`
The preferred period to offset any dripped lessons by (`days`, `weeks` etc.)

#### $drip_type `string`
The preferred drip type for the course that the student has enrolled in. (`delay_on_enrollment_date` etc.)

#### $enrollment `Lunchbox\Model\Enrollment object`

#### $course `Lunchbox\Model\Course object`

#### $student `Lunchbox\Model\Student object`

#### $now `DateTime`
A convenient `DateTime` object precreated for you to represent the current date and time.
