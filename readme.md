## About Laravel

Laravel is a web application framework with expressive, elegant syntax. We believe development must be an enjoyable and creative experience to be truly fulfilling. Laravel attempts to take the pain out of development by easing common tasks used in the majority of web projects, such as:

Error: SQLSTATE[42000]: Syntax error or access violation: 1071 Specified key was too long; max key length is 767 bytes (SQL: alter table `users` add unique `users_email_unique`(`email  
  `))    
Error: SQLSTATE[42000]: Syntax error or access violation: 1071 Specified key was too long;

To fix this, edit your AppServiceProvider.php file and inside the boot method set a default string length:

use Illuminate\Support\Facades\Schema;

public function boot()
{
    Schema::defaultStringLength(191);
}



Change configuration values in config/backpack/base.php to make the admin panel your own. Backpack is white label, so you can change everything: menu color, project name, developer name etc.

If your application only has one login screen (for the admins), that means you're not going to use the auth controllers that Laravel provided by default. You're only going to use Backpack's auth controllers. You can keep the Laravel ones in your project, of course. But some people like to delete them to not get confused later on:

# OPTIONAL! Please read the notice above.
rm -rf app/Http/Controllers/Auth #deletes laravel's demo auth controllers



## License

The Laravel framework is open-sourced software licensed under the [MIT license](https://opensource.org/licenses/MIT).
