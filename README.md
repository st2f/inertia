# laravel with inertia & react

## install
```bash
composer create-project laravel/laravel inertia
cd inertia
composer require laravel/breeze --dev
php artisan breeze:install
# options ex : React with Inertia, Dark mode, PHPUnit
```

## optional mysql containers

you can change default ports in .env
- ADMINER_PORT=8007
- DB_PORT=3307

```bash
mkdir dbdata
docker compose build && docker compose up -d
```

adminer : http://localhost:8007

mariadb :
- mysql -h inertiadb -uinertia_user -P 3307 -pinertia_pwd
- laravel will use DB_HOST=0.0.0.0

## migrate db data

```bash
# db config in .env
php artisan migrate
```

## install node

```bash
npm install

# if you don't have npm
sudo apt install npm
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.3/install.sh | bash
nvm install 18
nvm use 18
```

## run app dev

```bash
# in terminal 1
npm run dev
# in terminal 2
php artisan serve

# if ctrl-C does not stop these processes : kill -9 `lsof -t -i:8000,5173`
```

- laravel http://127.0.0.1:8000 (php8)
- vite http://127.0.0.1:5173 (node)

## run app prod
```bash
npm run build
# and remove file public/hot
# you can serve locally (http://127.0.0.1:8000) w/ : php artisan serve
```

