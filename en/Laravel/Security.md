```php
Passwords

Hash::make('secretpassword');
Hash::check('secretpassword', $hashedPassword);
Hash::needsRehash($hashedPassword);
			

Auth

// Determine if the current user is authenticated
Auth::check();
// Get the currently authenticated user
Auth::user();
// Get the ID of the currently authenticated user
Auth::id();
// Attempt to authenticate a user using the given credentials
Auth::attempt(array('email' => $email, 'password' => $password));
// 'Remember me' by passing true to Auth::attempt()
Auth::attempt($credentials, true);
// Log in for a single request
Auth::once($credentials);
// Log a user into the application
Auth::login(User::find(1));
// Log the given user ID into the application
Auth::loginUsingId(1);
// Log the user out of the application
Auth::logout();
// Validate a user's credentials
Auth::validate($credentials);
// Attempt to authenticate using HTTP Basic Auth
Auth::basic('username');
// Perform a stateless HTTP Basic login attempt
Auth::onceBasic();
// Send a password reminder to a user
Password::remind($credentials, function($message, $user){});
			

Encryption

Crypt::encrypt('secretstring');
Crypt::decrypt($encryptedString);
Crypt::setMode('ctr');
Crypt::setCipher($cipher);
```
