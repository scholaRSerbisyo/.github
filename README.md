# 📚 scholaRSerbisyo

A full-stack system for scholar engagement, powered by Next.js (Web), React Native with Expo (Mobile), and Laravel (Backend).

---

## 🗂️ Project Structure

```
scholarserbisyo/
│
├── scholarserbisyoadmin/    # Next.js web admin
├── frontendmobile/          # React Native Expo app
├── ss_backend/              # Laravel API backend
└── README.md                # Root documentation
```

---

## 🛠️ Tech Stack

| Layer           | Technology                 |
|----------------|----------------------------|
| Web Frontend   | Next.js (React)            |
| Mobile Frontend| React Native with Expo     |
| Backend        | Laravel + Sail (Docker)    |
| Database       | MySQL                      |
| Auth           | Laravel Sanctum / JWT      |
| API            | REST                       |
| Storage        | Cloudflare R2 (S3-like)    |

---

## 🚀 Getting Started

### 📁 Clone the Repositories

#### Web Admin

```bash
git clone https://github.com/scholaRSerbisyo/scholaRSerbisyo_web_admin.git
cd scholaRSerbisyo_web_admin
```

#### Mobile App

```bash
git clone https://github.com/scholaRSerbisyo/frontend_mobile.git
cd frontend_mobile
```

#### Backend API

```bash
git clone https://github.com/scholaRSerbisyo/scholaRSerbisyo_backend.git
cd scholaRSerbisyo_backend
```

---

## 🔧 Setup Instructions

### 🌐 1. Web Frontend (Next.js)

```bash
cd scholarserbisyoadmin
npm install
npm run dev
```

Create `.env.local`:

```env
ENV=http://localhost:8000
```

---

### 📱 2. Mobile Frontend (React Native Expo)

```bash
cd frontendmobile
npm install
npx expo start
```

#### Expo Requirements

- Install **Expo Go** on your device (App Store / Play Store)
- Enable **local network access**

Create `.env`:

```env
ENV=http://localhost:8000/api
```

---

### 🧠 3. Backend API (Laravel with Sail)

Install Composer:

```bash
composer install
```

Start with Sail (Docker):

```bash
./vendor/bin/sail up -d
```

Or force recreate:

```bash
./vendor/bin/sail up --force-recreate -d
```

---

### ⚙️ Backend Environment Setup

Create your `.env` file and configure like so:

<details>
<summary>Example .env (Click to expand)</summary>

```env
APP_NAME=Laravel
APP_ENV=local
APP_KEY=base64:your-app-key-here
APP_DEBUG=true
APP_TIMEZONE=Asia/Manila
APP_URL=http://localhost

APP_LOCALE=en
APP_FALLBACK_LOCALE=en
APP_FAKER_LOCALE=en_US

APP_MAINTENANCE_DRIVER=file
# APP_MAINTENANCE_STORE=database

BCRYPT_ROUNDS=12

LOG_CHANNEL=stack
LOG_STACK=single
LOG_DEPRECATIONS_CHANNEL=null
LOG_LEVEL=debug

DB_CONNECTION=mysql
DB_HOST=mysql
DB_PORT=3306
DB_DATABASE=laravel
DB_USERNAME=sail
DB_PASSWORD=password

SESSION_DRIVER=database
SESSION_LIFETIME=120
SESSION_ENCRYPT=false
SESSION_PATH=/
SESSION_DOMAIN=null

BROADCAST_CONNECTION=log
FILESYSTEM_DISK=local
QUEUE_CONNECTION=database

CACHE_STORE=database
CACHE_PREFIX=

MEMCACHED_HOST=127.0.0.1

REDIS_CLIENT=phpredis
REDIS_HOST=redis
REDIS_PASSWORD=null
REDIS_PORT=6379

MAIL_MAILER=smtp
MAIL_HOST=mailpit
MAIL_PORT=1025
MAIL_USERNAME=null
MAIL_PASSWORD=null
MAIL_ENCRYPTION=null
MAIL_FROM_ADDRESS="hello@example.com"
MAIL_FROM_NAME="${APP_NAME}"

AWS_ACCESS_KEY_ID=your-aws-access-key-id
AWS_SECRET_ACCESS_KEY=your-aws-secret-access-key
AWS_DEFAULT_REGION=us-east-1
AWS_BUCKET=your-aws-bucket-name
AWS_USE_PATH_STYLE_ENDPOINT=false

VITE_APP_NAME="${APP_NAME}"

SCOUT_DRIVER=meilisearch
MEILISEARCH_HOST=http://meilisearch:7700
MEILISEARCH_NO_ANALYTICS=false

# Cloudflare R2
CLOUDFLARE_ACCOUNT_ID=your-cloudflare-account-id
CLOUDFLARE_ACCESS_KEY_ID=your-cloudflare-access-key
CLOUDFLARE_SECRET_ACCESS_KEY=your-cloudflare-secret-key
CLOUDFLARE_BUCKET_NAME=eventimages
```

</details>

> 🔐 **Note:** Never commit real credentials. Use `.env.example` for sharing environment config templates.

---

## 🧱 Run Migrations

```bash
./vendor/bin/sail artisan migrate
```

---

## 🌱 Run Seeders

Run all default seeders:

```bash
./vendor/bin/sail artisan db:seed
```

Includes:

- AdminTypesSeeder
- EventTypeSeeders
- ScholarTypesSeeder
- UserRolesSeeder

Run individual seeders if needed:

```bash
./vendor/bin/sail artisan db:seed --class=UserRolesSeeder
```

---

## 🧪 Run Backend Tests

```bash
./vendor/bin/sail artisan test
```
