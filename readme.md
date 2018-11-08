
# Laravel Starter App

This Laravel application project structure is used to start a new Laravel project. 

## Usage

Before cloning or downloading this Laravel application project structure, you need to install the framework and software requirements to run a Laravel application:

  *  Follow the installation guidelines in the Laravel website (https://laravel.com/docs/5.6/installation)
  * Use this script and instructions to install and configure a Laravel application for the first time (https://github.com/fraigo/laravel-install-script)


After downloading this project you need to run some commands to ensure your Laravel application has the software dependencies installed (run inside the `laravel-app` folder):

```bash
composer install
```

To create your application .env (environment) file, run the following command:

```
cp .env.example .env
```

Then, you need to generate the application key

```
php artisan key:generate
```

To start your application server, run the following command:

```
php artisan serve
```

And then, point your browser to the application URL

```
http://localhost:8000/
```

## Common tasks

This is a list of common tasks you need to follow, optionally, to change some default configurations, making your application more customized

### Configuration files

* `.env`: In the root directory, contains the Laravel application configuration, database, email and other services
* `config/app.php`: Uses the `.env` configurations for the most common properties, containing some extra configurations not listed in `.env`, like localization or timezone.



### Laravel application

Modify the file `.env` in the root directory to change the `APP_` variables:

```
APP_NAME=Laravel
APP_ENV=local
APP_KEY=base64:3laRWY+EYvd0TqWskcTY5KeQs5jboLf5SCqG5XFfBQw=
APP_DEBUG=true
APP_LOG_LEVEL=debug
APP_URL=http://localhost
```

### Database connection

Modify the file `.env` in the root directory to change the `DB_` variables:

DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=homestead
DB_USERNAME=homestead
DB_PASSWORD=secret

### Email delivery

Modify the file `.env` in the root directory to change the `MAIL_` variables. Actually, is configured to use a MailTrap account (visit https://mailtrap.io/ and signup for an username and password). However, you can use a standard SMTP server configuration.

```
MAIL_DRIVER=smtp
MAIL_HOST=smtp.mailtrap.io
MAIL_PORT=2525
MAIL_USERNAME=null
MAIL_PASSWORD=null
MAIL_ENCRYPTION=null
```

MailTrap is a tool to deliver all emails sent by your application to a "fake" SMTP server, redirecting and storing all messages in one place. A common mistake when you test applications with email delivery, is to deliver testing emails to real email address.


### Location related

Edit the `config/app.php` file to change this parameters:

**Timezone**, using a timezone name as specified in the PHP manual (http://php.net/manual/en/timezones.php). For example, `America/Los_Angeles`. 

```
'timezone' => 'UTC',
```

**Language** default and fallback. The first one is for default application translation. The second one is used when there is some attempt to change to an unavailable language for translation.

```
'locale' => 'en',
'fallback_locale' => 'en',
```

### Service providers

Under `'providers'` key in `config/app.php`, you can add extra service providers, using the full namespace class name (Example: `App\Providers\BroadcastServiceProvider::class`)

### Class Aliases

Useful when you need to use some custom Class Name as an alias, pointing to a real class name, allowing to swap and change between different implementation classes. Also, to avoid using a full namespace class name for some commonly used classes:

```
'Log' => Illuminate\Support\Facades\Log::class,
```

In this case, you can provide your own `Log` class (implementing all the original Log interface) to override the default behavior:

```
'Log' => App\Helpers\MyLogger::class,
```






## License

The Laravel framework is open-sourced software licensed under the [MIT license](https://opensource.org/licenses/MIT).

