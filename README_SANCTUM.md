# Laravel Sanctum API

Sistema de autenticación API con Laravel Sanctum y MySQL.

## Características

- ✅ Registro de usuarios
- ✅ Login con tokens Bearer
- ✅ Autenticación con Laravel Sanctum
- ✅ Base de datos MySQL
- ✅ Endpoints protegidos

## Instalación

1. Clonar repositorio:
```bash
git clone [URL_DEL_REPO]
cd mi-proyecto-laravel
```

2. Instalar dependencias:
```bash
composer install
```

3. Configurar entorno:
```bash
cp .env.example .env
php artisan key:generate
```

4. Configurar base de datos en `.env`:
```env
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=laravel_sanctum
DB_USERNAME=root
DB_PASSWORD=
```

5. Ejecutar migraciones:
```bash
php artisan migrate
```

6. Iniciar servidor:
```bash
php artisan serve
```

## API Endpoints

### Registro
```
POST /api/register
Content-Type: application/json

{
    "name": "Usuario Test",
    "email": "test@ejemplo.com",
    "password": "12345678",
    "password_confirmation": "12345678"
}
```

### Login
```
POST /api/login
Content-Type: application/json

{
    "email": "test@ejemplo.com",
    "password": "12345678"
}
```

### Usuario autenticado (requiere token)
```
GET /api/user
Authorization: Bearer {token}
```

### Logout (requiere token)
```
POST /api/logout
Authorization: Bearer {token}
```

## Tecnologías

- Laravel 12
- Laravel Sanctum
- MySQL
- PHP 8.2+

## Servidor en Producción

Para subir a un servidor:

1. Configura las variables de entorno apropiadas
2. Asegúrate de tener MySQL instalado
3. Ejecuta las migraciones en el servidor
4. Configura un servidor web (Apache/Nginx)