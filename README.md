
## Installation

Create new folder
```bash
  mkdir project
  cd /project
```

Clone this project

```bash
  https://github.com/Locasee/backend-CC.git
```

```bash
Cloning into 'backend-CC'...
remote: Enumerating objects: 125, done.
remote: Counting objects: 100% (125/125), done.
remote: Compressing objects: 100% (93/93), done.
Receivingremote: Total 125 (delta 14), reused 125 (delta 14), pack-reused 0
Receiving objects: 100% (125/125), 300.93 KiB | 4.18 MiB/s, done.
Resolving deltas: 100% (14/14), done.
```

Change directory

```bash
  cd backend-CC
```

## How To Use
Copy file .env.example to .env

```bash
  copy .env.example .env 
```

Install Composer

```bash
  composer install
```

Install NPM

```bash
  npm install
```

Setting database in .env

```bash
  ....
# Database
DB_HOST=localhost
DB_PORT=3306
DB_DATABASE=YOUR_DATABASE
DB_USERNAME=YOUR_USERNAME_DATABASE
DB_PASSWORD=YOUR_PASSWORD_DATABASE
....
```

Generate key .env
```bash
  php artisan migrate:key
```

Store /storage
```bash
  php artisan storage:link
```

Migrate Database
```bash
  php artisan migrate
```
Running Program
```bash
  php artisan serve
```

```bash
  Starting Laravel development server: http://127.0.0.1:8000
  [Mon Jun 13 08:50:12 2022] PHP 8.1.6 Development Server (http://127.0.0.1:8000)
  started
```
























