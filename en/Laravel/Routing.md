```php
Route::get('foo', function(){});
Route::get('foo', 'ControllerName@function');
Route::controller('foo', 'FooController');
			

RESTful Controllers

Route::resource('posts','PostsController');
//Specify a subset of actions to handle on the route
Route::resource('photo', 'PhotoController',['only' => ['index', 'show']]);
Route::resource('photo', 'PhotoController',['except' => ['update', 'destroy']]);
			

Triggering Errors

App::abort(404);
App::missing(function($exception){});
throw new NotFoundHttpException;
			

Route Parameters

Route::get('foo/{bar}', function($bar){});
Route::get('foo/{bar?}', function($bar = 'bar'){});
			

HTTP Verbs

Route::any('foo', function(){});
Route::post('foo', function(){});
Route::put('foo', function(){});
Route::patch('foo', function(){});
Route::delete('foo', function(){});
// RESTful actions
Route::resource('foo', 'FooController');
			

Secure Routes

Route::get('foo', array('https', function(){}));

Route Constraints

Route::get('foo/{bar}', function($bar){})
	->where('bar', '[0-9]+');
Route::get('foo/{bar}/{baz}', function($bar, $baz){})
	->where(array('bar' => '[0-9]+', 'baz' => '[A-Za-z]'))
			

// Set a pattern to be used across routes
			Route::pattern('bar', '[0-9]+')
			

Filters

// Declare an auth filter
Route::filter('auth', function(){});
// Register a class as a filter
Route::filter('foo', 'FooFilter');
Route::get('foo', array('before' => 'auth', function(){}));
// Routes in this group are guarded by the 'auth' filter
Route::get('foo', array('before' => 'auth', function(){}));
Route::group(array('before' => 'auth'), function(){});
// Pattern filter
Route::when('foo/*', 'foo');
// HTTP verb pattern
Route::when('foo/*', 'foo', array('post'));
			

Named Routes

Route::currentRouteName();
Route::get('foo/bar', array('as' => 'foobar', function(){}));
			

Route Prefixing

// This route group will carry the prefix 'foo'
Route::group(array('prefix' => 'foo'), function(){})
			

Route Namespacing

// This route group will carry the namespace 'Foo\Bar'
Route::group(array('namespace' => 'Foo\Bar'), function(){})
			

Sub-Domain Routing

// {sub} will be passed to the closure
Route::group(array('domain' => '{sub}.example.com'), function(){});
```
