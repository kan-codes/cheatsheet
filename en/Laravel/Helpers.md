```php
Arrays

array_add($array, 'key', 'value');
// Build a new array using a callback
array_build($array, function(){});
// Divide an array into two arrays. One with keys and the other with values
array_divide($array);
// Flatten a multi-dimensional associative array with dots
array_dot($array);
// Get all of the given array except for a specified array of items
array_except($array, array('key'));
// Fetch a flattened array of a nested array element
array_fetch($array, 'key');
// Return the first element in an array passing a given truth test
array_first($array, function($key, $value){}, $default);
// Strips keys from the array
array_flatten($array);
// Remove one or many array items from a given array using "dot" notation
array_forget($array, 'foo');
// Dot notation
array_forget($array, 'foo.bar');
// Get an item from an array using "dot" notation
array_get($array, 'foo', 'default');
array_get($array, 'foo.bar', 'default');
// Get a subset of the items from the given array
array_only($array, array('key'));
// Return array of key => values
array_pluck($array, 'key');
// Return and remove 'key' from array
array_pull($array, 'key');
// Set an array item to a given value using "dot" notation
array_set($array, 'key', 'value');
// Dot notation
array_set($array, 'key.subkey', 'value');
array_sort($array, function(){});
// First element of an array
head($array);
// Last element of an array
last($array);
			

Paths

app_path();
//  Get the path to the public folder
public_path();
// App root path
base_path();
// Get the path to the storage folder
storage_path();
			

Strings

// Convert a value to camel case
camel_case($value);
// Get the class "basename" of the given object / class
class_basename($class);
// Escape a string
e('<html>');
// Determine if a given string starts with a given substring
starts_with('Foo bar.', 'Foo');
// Determine if a given string ends with a given substring
ends_with('Foo bar.', 'bar.');
// Convert a string to snake case
snake_case('fooBar');
// Determine if a given string contains a given substring
str_contains('Hello foo bar.', 'foo');
// Result: foo/bar/
str_finish('foo/bar', '/');
str_is('foo*', 'foobar');
str_plural('car');
str_random(25);
str_singular('cars');
// Result: FooBar
studly_case('foo_bar');
trans('foo.bar');
trans_choice('foo.bar', $count);
			

URLs and Links

action('FooController@method', $parameters);
link_to('foo/bar', $title, $attributes, $secure);
link_to_asset('img/foo.jpg', $title, $attributes, $secure);
link_to_route('route.name', $title, $parameters, $attributes);
link_to_action('FooController@method', $title, $params, $attrs);
// HTML Link
asset('img/photo.jpg', $title, $attributes);
// HTTPS link
secure_asset('img/photo.jpg', $title, $attributes);
secure_url('path', $parameters);
route($route, $parameters, $absolute = true);
url('path', $parameters = array(), $secure = null);
		

Miscellaneous

csrf_token();
dd($value);
value(function(){ return 'bar'; });
with(new Foo)->chainedMethod();
```
