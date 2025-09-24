# Laravel Application

Aplikasi web modern yang dibangun dengan Laravel 12 dan dilengkapi dengan berbagai tools untuk development yang optimal.

## Tech Stack

- **Backend**: Laravel 12 (PHP 8.2+)
- **Frontend**: Vite + TailwindCSS 4.0
- **Database**: SQLite (default), MySQL/PostgreSQL support
- **Server**: FrankenPHP (Laravel Octane)
- **Queue**: Laravel Horizon
- **Testing**: Pest PHP
- **Code Quality**: PHPStan (Level 10), Laravel Pint

## Fitur Utama

- ⚡ **High Performance**: Laravel Octane dengan FrankenPHP server
- 🎯 **Queue Management**: Laravel Horizon untuk background jobs
- 🔍 **Debugging**: Laravel Telescope untuk monitoring aplikasi
- 📊 **Logging**: Laravel Pail untuk real-time log monitoring
- 🧪 **Testing**: Pest PHP untuk testing yang ekspresif
- 📝 **Code Quality**: PHPStan level 10 untuk static analysis
- 🎨 **Modern Frontend**: TailwindCSS 4.0 dengan Vite

## Requirements

- PHP 8.2 atau lebih tinggi
- Composer
- Node.js & npm
- SQLite (atau database lain sesuai konfigurasi)

## Installation

1. **Clone repository**
   ```bash
   git clone https://github.com/kungfufafa/l12.git
   cd l12
   ```

2. **Install dependencies**
   ```bash
   composer install
   npm install
   ```

3. **Setup environment**
   ```bash
   cp .env.example .env
   php artisan key:generate
   ```

4. **Setup database**
   ```bash
   touch database/database.sqlite
   php artisan migrate
   ```

## Development

### Quick Start
Jalankan semua services sekaligus dengan satu command:
```bash
composer run dev
```

Command ini akan menjalankan:
- Laravel development server
- Queue worker
- Real-time logs (Pail)
- Vite dev server untuk frontend

### Manual Commands

**Start development server:**
```bash
php artisan serve
```

**Build frontend assets:**
```bash
npm run dev          # Development
npm run build        # Production
```

**Queue worker:**
```bash
php artisan queue:listen
```

**Real-time logs:**
```bash
php artisan pail
```

## Testing

**Run all tests:**
```bash
composer run test
# atau
php artisan test
```

**Run specific test:**
```bash
php artisan test --filter=TestName
```

## Code Quality

**Static analysis dengan PHPStan:**
```bash
vendor/bin/phpstan analyse
```

**Code formatting dengan Pint:**
```bash
vendor/bin/pint
```

## Production Deployment

1. **Optimize aplikasi:**
   ```bash
   composer install --optimize-autoloader --no-dev
   php artisan config:cache
   php artisan route:cache
   php artisan view:cache
   ```

2. **Build frontend assets:**
   ```bash
   npm run build
   ```

3. **Setup FrankenPHP untuk production:**
   ```bash
   php artisan octane:start --server=frankenphp
   ```

## Monitoring & Debugging

- **Telescope**: Akses `/telescope` untuk monitoring aplikasi
- **Horizon**: Akses `/horizon` untuk queue management
- **Logs**: Gunakan `php artisan pail` untuk real-time logging

## Project Structure

```
app/
├── Http/           # Controllers, Middleware, Requests
├── Models/         # Eloquent Models
└── Providers/      # Service Providers

config/             # Configuration files
database/           # Migrations, Seeders, Factories
resources/          # Views, CSS, JS
routes/             # Route definitions
tests/              # Test files
```

## License

Proyek ini menggunakan lisensi [MIT](https://opensource.org/licenses/MIT).
