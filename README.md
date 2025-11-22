# Rumah Sakit 2025 - Hospital Management System

<!-- Badges (GitHub Actions + Codecov) -->
[![Build Status](https://github.com/yusuppsaputra/rumahsakit-2025/actions/workflows/ci.yml/badge.svg)](https://github.com/yusuppsaputra/rumahsakit-2025/actions)
[![Coverage](https://codecov.io/gh/yusuppsaputra/rumahsakit-2025/branch/main/graph/badge.svg)](https://codecov.io/gh/yusuppsaputra/rumahsakit-2025)

Proyek ini adalah sistem manajemen rumah sakit berbasis Laravel (dilengkapi Filament pada antarmuka admin) dan dikemas untuk pengembangan lokal menggunakan Docker Compose (nginx, php-fpm, MariaDB).

## Ringkasan cepat
- Laravel app di `src/`
- Docker: `nginx/`, `php/`, `db/` dan `docker-compose.yml` pada root proyek
- Menggunakan Filament untuk panel admin

## Menjalankan dengan Docker
1. Salin environment contoh jika ada: `cp src/.env.example src/.env` dan sesuaikan.
2. Jalankan service:

```powershell
docker compose up -d --build
```

3. Masuk ke container PHP bila perlu menjalankan perintah artisan:

```powershell
docker compose exec php bash
```

4. Jalankan migrasi dan seeder:

```powershell
php artisan migrate --seed
```

## Pengembangan lokal (opsional)
```powershell
cd src
composer install
npm install
npm run dev
cp .env.example .env
php artisan key:generate
php artisan migrate --seed
php artisan serve
```

## Menjalankan test

Di folder `src/`:

```powershell
php artisan test
# atau jika menggunakan Pest
./vendor/bin/pest
```

## Kontribusi
- Fork, buat branch fitur, lalu buka PR ke `main` dengan penjelasan perubahan.

## Catatan
- Jika workflow GitHub Actions atau layanan coverage berbeda, ganti URL badge di bagian atas README.

---

Jika Anda mau, saya juga bisa:
- Commit file ini dan buat branch + PR opsional ke remote,
- Menambahkan badges lain (Docker Hub, PHPStan, Psalm), atau
- Menambahkan instruksi deploy.
