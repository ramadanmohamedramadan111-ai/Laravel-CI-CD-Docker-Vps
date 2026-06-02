# API توثيق - Products

توثيق مختصر للـ API الخاص بالـ `products` حتى يتمكن أي شخص من تجربة الواجهات عبر Postman أو curl.

Base URL
- استخدم المتغير `{{base_url}}`، مثال محلي: `http://localhost` أو داخل الـ Docker: `http://localhost:8000` حسب إعدادك.

نقاط النهاية
- `GET /api/products` — جلب قائمة المنتجات (paginated)
- `GET /api/products/{id}` — جلب منتج واحد
- `POST /api/products` — إنشاء منتج جديد
- `PUT /api/products/{id}` — تحديث كامل لمنتج
- `PATCH /api/products/{id}` — تحديث جزئي لمنتج
- `DELETE /api/products/{id}` — حذف منتج

أمثلة جسم الطلب (JSON)

Create (POST /api/products)

{
  "name": "قلم حبر",
  "description": "قلم حبر أسود عالي الجودة",
  "price": 4.50,
  "stock": 120
}

Update (PUT /api/products/1)

{
  "name": "قلم جِل",
  "description": "قلم جِل أزرق",
  "price": 5.00,
  "stock": 80
}

ردود متوقعة
- `200 OK` — عند نجاح `GET`, `PUT`, `PATCH`
- `201 Created` — عند نجاح `POST`
- `204 No Content` — عند نجاح `DELETE`
- `422 Unprocessable Entity` — عند فشل التحقق من صحة البيانات

تشغيل محلي سريع
- إن قمت بتعديل PHP أو تستخدم Docker، تأكد من تشغيل الميغريشن والسيِدرز: في مجلد `app`:

```bash
php artisan migrate --seed
```

- إذا كنت داخل Docker، استبدل الأمر بما يناسب خدمة الـ PHP في `docker-compose.yml`، مثال:

```bash
docker-compose run --rm app php artisan migrate --seed
```

ملف مجموعة Postman
- يوجد ملف المجموعة في `docs/postman_collection.json` يمكن استيراده مباشرة في Postman. تأكد من ضبط متغير `base_url` في بيئة Postman قبل التشغيل.

ملاحظات
- إن لم تتوفر قاعدة بيانات أو كانت نسخة PHP الحالية غير مطابقة لمتطلبات الـ Composer، يمكنك استيراد مجموعة Postman وتجربة الطلبات يدوياً مع تغيير `base_url` إلى بيئة تعمل أو إلى mock server.
<p align="center"><a href="https://laravel.com" target="_blank"><img src="https://raw.githubusercontent.com/laravel/art/master/logo-lockup/5%20SVG/2%20CMYK/1%20Full%20Color/laravel-logolockup-cmyk-red.svg" width="400" alt="Laravel Logo"></a></p>

<p align="center">
<a href="https://github.com/laravel/framework/actions"><img src="https://github.com/laravel/framework/workflows/tests/badge.svg" alt="Build Status"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/dt/laravel/framework" alt="Total Downloads"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/v/laravel/framework" alt="Latest Stable Version"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/l/laravel/framework" alt="License"></a>
</p>

## About Laravel

Laravel is a web application framework with expressive, elegant syntax. We believe development must be an enjoyable and creative experience to be truly fulfilling. Laravel takes the pain out of development by easing common tasks used in many web projects, such as:

- [Simple, fast routing engine](https://laravel.com/docs/routing).
- [Powerful dependency injection container](https://laravel.com/docs/container).
- Multiple back-ends for [session](https://laravel.com/docs/session) and [cache](https://laravel.com/docs/cache) storage.
- Expressive, intuitive [database ORM](https://laravel.com/docs/eloquent).
- Database agnostic [schema migrations](https://laravel.com/docs/migrations).
- [Robust background job processing](https://laravel.com/docs/queues).
- [Real-time event broadcasting](https://laravel.com/docs/broadcasting).

Laravel is accessible, powerful, and provides tools required for large, robust applications.

## Learning Laravel

Laravel has the most extensive and thorough [documentation](https://laravel.com/docs) and video tutorial library of all modern web application frameworks, making it a breeze to get started with the framework.

In addition, [Laracasts](https://laracasts.com) contains thousands of video tutorials on a range of topics including Laravel, modern PHP, unit testing, and JavaScript. Boost your skills by digging into our comprehensive video library.

You can also watch bite-sized lessons with real-world projects on [Laravel Learn](https://laravel.com/learn), where you will be guided through building a Laravel application from scratch while learning PHP fundamentals.

## Agentic Development

Laravel's predictable structure and conventions make it ideal for AI coding agents like Claude Code, Cursor, and GitHub Copilot. Install [Laravel Boost](https://laravel.com/docs/ai) to supercharge your AI workflow:

```bash
composer require laravel/boost --dev

php artisan boost:install
```

Boost provides your agent 15+ tools and skills that help agents build Laravel applications while following best practices.

## Contributing

Thank you for considering contributing to the Laravel framework! The contribution guide can be found in the [Laravel documentation](https://laravel.com/docs/contributions).

## Code of Conduct

In order to ensure that the Laravel community is welcoming to all, please review and abide by the [Code of Conduct](https://laravel.com/docs/contributions#code-of-conduct).

## Security Vulnerabilities

If you discover a security vulnerability within Laravel, please send an e-mail to Taylor Otwell via [taylor@laravel.com](mailto:taylor@laravel.com). All security vulnerabilities will be promptly addressed.

## License

The Laravel framework is open-sourced software licensed under the [MIT license](https://opensource.org/licenses/MIT).
