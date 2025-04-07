📚 scholaRSerbisyo

A full-stack system for scholar engagement, powered by Next.js (Web), React Native with Expo (Mobile), and Laravel (Backend).
🗂️ Project Structure

scholarserbisyo/
│
├── scholarserbisyoadmin/    # Next.js web admin
├── frontendmobile/          # React Native Expo app
├── ss_backend/              # Laravel API backend
└── README.md                # Root documentation

🛠️ Tech Stack
Layer	Technology
Web Frontend	Next.js (React)
Mobile Frontend	React Native with Expo
Backend	Laravel + Sail (Docker)
Database	MySQL
Auth	Laravel Sanctum / JWT
API	REST
Storage	Cloudflare R2 (S3-like)

🚀 Getting Started
📁 Clone the Repositories

Web Admin
git clone https://github.com/scholaRSerbisyo/scholaRSerbisyo_web_admin.git

cd scholaRSerbisyo_web_admin

Mobile App
git clone https://github.com/scholaRSerbisyo/frontend_mobile.git

cd frontend_mobile

Backend API
git clone https://github.com/scholaRSerbisyo/scholaRSerbisyo_backend.git

cd scholaRSerbisyo_backend

🔧 Setup Instructions

🌐 1. Web Frontend (Next.js)

cd scholarserbisyoadmin
npm install
npm run dev

Create .env.local:

ENV=http://localhost:8000

📱 2. Mobile Frontend (React Native Expo)

cd frontendmobile
npm install
npx expo start

Expo Requirements:

    Install Expo Go on your device (App Store / Play Store)

    Enable local network access

Create .env:

ENV=http://localhost:8000/api

🧠 3. Backend API (Laravel with Sail)

Start with Sail (Docker):

./vendor/bin/sail up -d

Or force recreate:

./vendor/bin/sail up --force-recreate -d


⚙️ Backend Environment Setup

Create your .env file and configure like so:

<details> <summary>Example .env (Click to expand)</summary>

APP_NAME=Laravel
APP_ENV=local
APP_KEY=base64:your-app-key-here
APP_DEBUG=true
APP_TIMEZONE=Asia/Manila
APP_URL=http://localhost

APP_LOCALE=en
APP_FALLBACK_LOCALE=en
APP_FAKER_LOCALE=en_US

LOG_CHANNEL=stack
LOG_LEVEL=debug

DB_CONNECTION=mysql
DB_HOST=mysql
DB_PORT=3306
DB_DATABASE=laravel
DB_USERNAME=sail
DB_PASSWORD=password

SESSION_DRIVER=database
SESSION_LIFETIME=120

QUEUE_CONNECTION=database
CACHE_STORE=database

REDIS_CLIENT=phpredis
REDIS_HOST=redis
REDIS_PORT=6379

MAIL_MAILER=smtp
MAIL_HOST=mailpit
MAIL_PORT=1025
MAIL_FROM_ADDRESS=hello@example.com
MAIL_FROM_NAME="${APP_NAME}"

FILESYSTEM_DISK=local

SCOUT_DRIVER=meilisearch
MEILISEARCH_HOST=http://meilisearch:7700
MEILISEARCH_NO_ANALYTICS=false

# Cloudflare R2
CLOUDFLARE_ACCOUNT_ID=your-cloudflare-account-id
CLOUDFLARE_ACCESS_KEY_ID=your-access-key-id
CLOUDFLARE_SECRET_ACCESS_KEY=your-secret-access-key
CLOUDFLARE_BUCKET_NAME=eventimages

</details>

🔐 Note: Never commit real credentials. Use .env.example for sharing environment config templates.

🧱 Run Migrations

./vendor/bin/sail artisan migrate

🌱 Run Seeders

Run all default seeders:

./vendor/bin/sail artisan db:seed

Includes:

    AdminTypesSeeder

    EventTypeSeeders

    ScholarTypesSeeder

    UserRolesSeeder

Run individual seeders if needed:

./vendor/bin/sail artisan db:seed --class=UserRolesSeeder

🧪 Run Backend Tests
./vendor/bin/sail artisan test
