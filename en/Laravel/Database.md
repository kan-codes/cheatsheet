```php
DB::connection('connection_name');
DB::statement('drop table users');
DB::listen(function($sql, $bindings, $time){ code_here; });
DB::transaction(function(){ transaction_code_here; });
// Cache a query for $time minutes
DB::table('users')->remember($time)->get();
// Escape raw input
DB::raw('sql expression here');
			

Selects

DB::table('name')->get();
DB::table('name')->distinct()->get();
DB::table('name')->select('column as column_alias')->get();
DB::table('name')->where('name', '=', 'John')->get();
DB::table('name')->whereBetween('column', array(1, 100))->get();
DB::table('name')->whereIn('column', array(1, 2, 3))->get();
DB::table('name')->whereNotIn('column', array(1, 2, 3))->get();
DB::table('name')->whereNull('column')->get();
DB::table('name')->whereNotNull('column')->get();
DB::table('name')->groupBy('column')->get();
// Default Eloquent sort is ascendant
DB::table('name')->orderBy('column')->get();
DB::table('name')->orderBy('column','desc')->get();
DB::table('name')->having('count', '>', 100)->get();
DB::table('name')->skip(10)->take(5)->get();
DB::table('name')->first();
DB::table('name')->pluck('column');
DB::table('name')->lists('column');
// Joins
DB::table('name')->join('table', 'name.id', '=', 'table.id')
    ->select('name.id', 'table.email');
			

Inserts, Updates, Deletes

DB::table('name')->insert(array('name' => 'John', 'email' => 'john@example.com'));
DB::table('name')->insertGetId(array('name' => 'John', 'email' => 'john@example.com'));
// Batch insert
DB::table('name')->insert(array(
	array('name' => 'John', 'email' => 'john@example.com')
	array('name' => 'James', 'email' => 'james@example.com')
));
// Update an entry
DB::table('name')->where('name', '=', 'John')
	->update(array('email' => 'john@example2.com'));
// Delete everything from a table
DB::table('name')->delete();
// Delete specific records
DB::table('name')->where('id', '>', '10')->delete();
DB::table('name')->truncate();
			

Aggregates

DB::table('name')->count();
DB::table('name')->max('column');
DB::table('name')->min('column');
DB::table('name')->avg('column');
DB::table('name')->sum('column');
DB::table('name')->increment('column');
DB::table('name')->increment('column', $amount);
DB::table('name')->decrement('column');
DB::table('name')->decrement('column', $amount);
DB::table('name')->remember(5)->get();
DB::table('name')->remember(5, 'cache-key-name')->get();
DB::table('name')->cacheTags('my-key')->remember(5)->get();
DB::table('name')->cacheTags(array('my-first-key','my-second-key'))->remember(5)->get();
			

Raw Expressions

// return rows
DB::select('select * from users where id = ?', array('value'));
// return nr affected rows
DB::insert('insert into foo set bar=2');
DB::update('update foo set bar=2');
DB::delete('delete from bar');
// returns void
DB::statement('update foo set bar=2');
// raw expression inside a statement
DB::table('name')->select(DB::raw('count(*) as count, column2'))->get();
```
