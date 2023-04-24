# 🎉 DEMO Laravel Honeypot

Laravel Honeypot is a simple package for preventing spam submissions on web forms. It works by adding a hidden field to forms, which is invisible to users but is detected by bots, who then trigger an error and are blocked from submitting the form.

![version](https://img.shields.io/badge/version-1.0-blue)
![rating](https://img.shields.io/badge/rating-★★★★★-yellow)
![uptime](https://img.shields.io/badge/uptime-100%25-brightgreen)

### 🚀 Setup

- Install Package

```shell
composer require spatie/laravel-honeypot
```

- Publish Config

```shell
php artisan vendor:publish --provider="Spatie\Honeypot\HoneypotServiceProvider" --tag=config
```

- Add Honeypot

```php
<form method="POST" action="{{ route('contactForm.submit') }}")>
    @honeypot
    <input name="myField" type="text">
</form>
```

- Add Middleware

```php
use App\Http\Controllers\ContactFormSubmissionController;
use Spatie\Honeypot\ProtectAgainstSpam;

Route::post('contact', [ContactFormSubmissionController::class, 'create'])->middleware(ProtectAgainstSpam::class);
```

### 🏆 Run

- [http://localhost:8000](http://localhost:8000)

```shell
php artisan serve
```