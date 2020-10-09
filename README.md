# Docker-Laravel

This is a demo Laravel project with docker.

**Website**: http://127.0.0.1:8080

**Database**: http://127.0.0.1:8081

# How to build
### 1. Pull code
Pull code from server

### 2. Create file .env
Create file .env from file .env.example 

Change value params:
    
```
APP_PORT=8080
APP_ADMINER=8081

DB_USERNAME=root
DB_PASSWORD=root
DB_DATABASE=laravel
```

### 3. Run command in root folder
```
 docker-compose up -d
```

### 4. Create, update vendor folder in root folder by command:
First, access to app by command
```
docker-compose exec app bash
```
after, create vendor folder by command
```
composer install
```

### 5. Attach app container create APP_KEY by command
```
php artisan key:generate
```
If break this step then after first time access website, click generate key.

### 6. Finished: Check by go to browser
```
Website: 
127.0.0.1:8080
Database: 
127.0.0.1:8081
```













