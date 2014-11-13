```php
Executing Commands

SSH::run(array $commands);
SSH::into($remote)->run(array $commands); // specify remote, otherwise assumes default
SSH::run(array $commands, function($line)
{
	echo $line.PHP_EOL;
});
			

Tasks

SSH::define($taskName, array $commands); // define
SSH::task($taskName, function($line) // execute
{
	echo $line.PHP_EOL;
});
			

SFTP Uploads

SSH::put($localFile, $remotePath);
SSH::putString($string, $remotePath);
```
