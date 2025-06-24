# product_and_seller_management

# Laravel Marketplace API & Admin Panel

A modern Laravel-based marketplace project with:
- Admin and Seller authentication (UI + API)
- Seller management (skills, products, brands)
- Product management with multiple brands and image upload
- Beautiful UI for admin and seller dashboards
- Secure, role-based access

---

# Features
- Admin & Seller login (UI + API)
- Add, list, and delete sellers (admin)
- Add, list, and delete products (seller)
- Multiple brands per product, with image upload
- Pagination, search, and modern Bootstrap UI
- API endpoints for all major actions
- Proper error handling and status codes

---

# Dependencies
- **Laravel 10+**
- **PHP 8.1+**
- **MySQL**
- **Bootstrap 5** (UI)
- **Laravel Sanctum** (API authentication)
- **Intervention/Image** (optional, for advanced image handling)

---

## Quick Start

### 1. Clone & Install
```bash
composer install
cp .env.example .env
php artisan key:generate
```

### 2. Configure Database
- Update `.env` with your DB credentials:
  ```
  DB_DATABASE=laravel_pune_api
  DB_USERNAME=root
  DB_PASSWORD=
  ```
- Create the database in phpMyAdmin or MySQL CLI.

### 3. Run Migrations & Seeders
```bash
php artisan migrate:fresh
php artisan db:seed --class=AdminSeeder
php artisan db:seed --class=SkillSeeder
```

### 4. Image Upload (IMPORTANT!)
If product brand images are not showing, run:
```bash
php artisan storage:link
```
This creates a symbolic link so images in `storage/app/public` are accessible from `public/storage`.

### 5. Start the Server
```bash
php artisan serve
```
Visit: [http://127.0.0.1:8000](http://127.0.0.1:8000)

---

## Default Admin Credentials
- **Email:** admin@example.com
- **Password:** password

## seller credentials:
- **Email:** pratik@gmail.com
-**Password:** password123
---

## API Endpoints (Main)
- `POST /api/admin/login` — Admin login
- `POST /api/admin/sellers` — Add seller (admin)
- `GET /api/admin/sellers` — List sellers (admin)
- `POST /api/seller/login` — Seller login
- `POST /api/seller/products` — Add product (seller)
- `DELETE /api/seller/products/{id}` — Delete product (seller)

See `API_DOCUMENTATION.md` for full details and request/response examples.

---

## UI Pages
- `/` — Landing page
- `/admin/login` — Admin login
- `/admin/sellers-list` — Admin sellers list (with add seller button)
- `/admin/sellers/add` — Add seller form
- `/seller/login` — Seller login
- `/seller/dashboard` — Seller dashboard (list, add, delete products)
- `/seller/add-product` — Add product form

---

## Security & Best Practices
- Sanctum token-based API authentication
- Role-based access (admin/seller)
- Input validation everywhere
- CSRF protection for forms
- File upload validation
- Proper HTTP status codes and error messages

