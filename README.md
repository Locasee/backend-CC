
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








## API Reference

#### User Register

```
  POST http://127.0.0.1:8000/api/register
```

| Parameter | Type     | Description                |
| :-------- | :------- | :------------------------- |
| `name` | `string` | **Required** |
| `email` | `string` | **Required** |
| `password` | `string` | **Required** |
| `phone_number` | `string` | **Required** |
| `address` | `string` | **Required** |

Result :
```http
{
    "data": {
        "name": "Annas Abdurrahman",
        "email": "admin02@admin.com",
        "phone_number": "085602602602",
        "address": "Jl. Mangga Besar IV K",
        "provinsi_id": null,
        "kabupaten_id": null,
        "kecamatan_id": null,
        "avatar_url": "",
        "updated_at": "2022-06-13T02:17:51.000000Z",
        "created_at": "2022-06-13T02:17:51.000000Z",
        "id": 1
    },
    "message": "Register success."
}
```

#### User Login

```
  POST http://127.0.0.1:8000/api/login
```

| Parameter | Type     | Description                       |
| :-------- | :------- | :-------------------------------- |
| `email`      | `string` | **Required** |
| `password`   | `string` | **Required** |


Result : 
```http
  {
    "data": {
        "id": 1,
        "name": "Aflian M",
        "email": "admin02@admin.com",
        "phone_number": "085602602602",
        "address": "Jl. Mangga Besar IV K",
        "avatar_url": "",
        "provinsi_id": null,
        "kabupaten_id": null,
        "kecamatan_id": null,
        "email_verified_at": null,
        "created_at": "2022-06-13T02:17:51.000000Z",
        "updated_at": "2022-06-13T02:17:51.000000Z",
        "provinsi": null,
        "kabupaten": null,
        "kecamatan": null
    },
    "access_token": "1|phX7hoAVlEOSnSTyHVKvVDfFaNh2JmPQHXQHFMbu",
    "token_type": "Bearer",
    "message": "Login success."
}
```

#### User Update

```
  POST http://127.0.0.1:8000/api/user/{id_user}?_method=PUT
```

| Parameter | Type     | Description                       |
| :-------- | :------- | :-------------------------------- |
| `name`      | `string` | **Required** |
| `email`   | `string` | **Required** |
| `phone_number`   | `string` | **Required** |
| `image`   | `file` | **Required** |

```http
{
    "data": {
        "id": 1,
        "name": "Aflian Update",
        "email": "admin01@admin.com",
        "phone_number": "0856",
        "address": "Jl. Mabes (Update)",
        "avatar_url": "/storage/user/1/avatar.png",
        "provinsi_id": null,
        "kabupaten_id": null,
        "kecamatan_id": null,
        "email_verified_at": null,
        "created_at": "2022-06-13T02:17:51.000000Z",
        "updated_at": "2022-06-13T02:28:03.000000Z"
    },
    "message": "User updated successfully."
}
```


#### POST Land

```
  POST http://127.0.0.1:8000/api/post
```

| Parameter | Type     | Description                       |
| :-------- | :------- | :-------------------------------- |
| `Authorization`      | `Bearear` | **Required** |
| `title`      | `string` | **Required** |
| `desc`      | `text` | **Required** |
| `price`      | `integer` | **Required** |
| `area`      | `integer` | **Required** |
| `address`      | `string` | **Required** |
| `latitude`      | `string` | **Required** |
| `longitude`      | `string` | **Required** |
| `user_id`      | `integer` | **Required** |
| `provinsi_id`      | `integer` | **Required** |
| `kabupaten_id`      | `integer` | **Required** |
| `kecamatan_id`      | `integer` | **Required** |
| `images[]`      | `file` | **Required** |

Result :

```http
{
    "data": {
        "title": "Post Yang Benar Ini",
        "desc": "Ini adalah percobaan",
        "price": "9999999999999",
        "area": "900",
        "address": "Jl Jenderal Sudirman",
        "latitude": "-7.567591846289804",
        "longitude": "110.85050209864643",
        "user_id": "1",
        "provinsi_id": "11",
        "kabupaten_id": "1171",
        "kecamatan_id": "1171020",
        "images": [
            "/storage/post/2/images/0.jpg",
            "/storage/post/2/images/1.png"
        ],
        "updated_at": "2022-06-13T02:24:44.000000Z",
        "created_at": "2022-06-13T02:24:42.000000Z",
        "id": 2
    },
    "message": "Post created successfully."
}
```

#### GET All Post Land

```
  GET http://127.0.0.1:8000/api/post/
```

| Parameter | Type     | Description                       |
| :-------- | :------- | :-------------------------------- |
| `Authorization`      | `Bearear` | **Required** |


Result :

```http
{
    "data": [
        {
            "id": 2,
            "title": "Post Yang Benar Ini",
            "desc": "Ini adalah percobaan",
            "price": 9999999999999,
            "area": 900,
            "address": "Jl Jenderal Sudirman",
            "latitude": -7.567591846289804,
            "longitude": 110.85050209864643,
            "images": [
                "/storage/post/2/images/0.jpg",
                "/storage/post/2/images/1.png"
            ],
            "user_id": 1,
            "provinsi_id": 11,
            "kabupaten_id": 1171,
            "kecamatan_id": 1171020,
            "created_at": "2022-06-13T02:24:42.000000Z",
            "updated_at": "2022-06-13T02:24:44.000000Z",
            "deleted_at": null,
            "user": {
                "id": 1,
                "name": "Aflian Update",
                "email": "admin01@admin.com",
                "phone_number": "0856",
                "address": "Jl. Mabes (Update)",
                "avatar_url": "/storage/user/1/avatar.png",
                "provinsi_id": null,
                "kabupaten_id": null,
                "kecamatan_id": null,
                "email_verified_at": null,
                "created_at": "2022-06-13T02:17:51.000000Z",
                "updated_at": "2022-06-13T02:28:03.000000Z"
            },
            "provinsi": {
                "id": 11,
                "title": "ACEH"
            },
            "kabupaten": {
                "id": 1171,
                "provinsi_id": 11,
                "title": "KOTA BANDA ACEH"
            },
            "kecamatan": {
                "id": 1171020,
                "kabupaten_id": 1171,
                "title": "BAITURRAHMAN"
            }
        }
    ],
    "message": "Posts fetched."
}
```

#### GET Single Post Land

```
  GET http://127.0.0.1:8000/api/post/{id_posts}
```

| Parameter | Type     | Description                       |
| :-------- | :------- | :-------------------------------- |
| `Authorization`      | `Bearear` | **Required** |


Result :
```http
{
    "data": {
        "id": 2,
        "title": "Post Yang Benar Ini",
        "desc": "Ini adalah percobaan",
        "price": 9999999999999,
        "area": 900,
        "address": "Jl Jenderal Sudirman",
        "latitude": -7.567591846289804,
        "longitude": 110.85050209864643,
        "images": [
            "/storage/post/2/images/0.jpg",
            "/storage/post/2/images/1.png"
        ],
        "user_id": 1,
        "provinsi_id": 11,
        "kabupaten_id": 1171,
        "kecamatan_id": 1171020,
        "created_at": "2022-06-13T02:24:42.000000Z",
        "updated_at": "2022-06-13T02:24:44.000000Z",
        "deleted_at": null,
        "user": {
            "id": 1,
            "name": "Aflian Update",
            "email": "admin01@admin.com",
            "phone_number": "0856",
            "address": "Jl. Mabes (Update)",
            "avatar_url": "/storage/user/1/avatar.png",
            "provinsi_id": null,
            "kabupaten_id": null,
            "kecamatan_id": null,
            "email_verified_at": null,
            "created_at": "2022-06-13T02:17:51.000000Z",
            "updated_at": "2022-06-13T02:28:03.000000Z"
        },
        "provinsi": {
            "id": 11,
            "title": "ACEH"
        },
        "kabupaten": {
            "id": 1171,
            "provinsi_id": 11,
            "title": "KOTA BANDA ACEH"
        },
        "kecamatan": {
            "id": 1171020,
            "kabupaten_id": 1171,
            "title": "BAITURRAHMAN"
        }
    },
    "message": "Posdddts fetched."
}
```

#### GET USER Post Land

```
  GET http://127.0.0.1:8000/api/post/user/{id_user}
```

| Parameter | Type     | Description                       |
| :-------- | :------- | :-------------------------------- |
| `Authorization`      | `Bearear` | **Required** |

```http
{
    "data": [
        {
            "id": 2,
            "title": "Post Yang Benar Ini",
            "desc": "Ini adalah percobaan",
            "price": 9999999999999,
            "area": 900,
            "address": "Jl Jenderal Sudirman",
            "latitude": -7.567591846289804,
            "longitude": 110.85050209864643,
            "images": [
                "/storage/post/2/images/0.jpg",
                "/storage/post/2/images/1.png"
            ],
            "user_id": 1,
            "provinsi_id": 11,
            "kabupaten_id": 1171,
            "kecamatan_id": 1171020,
            "created_at": "2022-06-13T02:24:42.000000Z",
            "updated_at": "2022-06-13T02:24:44.000000Z",
            "deleted_at": null,
            "user": {
                "id": 1,
                "name": "Annas Update",
                "email": "admin01@admin.com",
                "phone_number": "0856",
                "address": "Jl. Mabes (Update)",
                "avatar_url": "/storage/user/1/avatar.png",
                "provinsi_id": null,
                "kabupaten_id": null,
                "kecamatan_id": null,
                "email_verified_at": null,
                "created_at": "2022-06-13T02:17:51.000000Z",
                "updated_at": "2022-06-13T02:28:03.000000Z"
            },
            "provinsi": {
                "id": 11,
                "title": "ACEH"
            },
            "kabupaten": {
                "id": 1171,
                "provinsi_id": 11,
                "title": "KOTA BANDA ACEH"
            },
            "kecamatan": {
                "id": 1171020,
                "kabupaten_id": 1171,
                "title": "BAITURRAHMAN"
            }
        }
    ],
    "message": "Posts fetched."
}
```

#### Filter Search  Land

```
  GET http://127.0.0.1:8000/api/post/filter?search={text}
```

| Parameter | Type     | Description                       |
| :-------- | :------- | :-------------------------------- |
| `Authorization`      | `Bearear` | **Required** |

Result :
```http
{
    "data": [
        {
            "id": 2,
            "title": "Post Yang Benar Ini",
            "desc": "Ini adalah percobaan",
            "price": 9999999999999,
            "area": 900,
            "address": "Jl Jenderal Sudirman",
            "latitude": -7.567591846289804,
            "longitude": 110.85050209864643,
            "images": [
                "/storage/post/2/images/0.jpg",
                "/storage/post/2/images/1.png"
            ],
            "user_id": 1,
            "provinsi_id": 11,
            "kabupaten_id": 1171,
            "kecamatan_id": 1171020,
            "created_at": "2022-06-13T02:24:42.000000Z",
            "updated_at": "2022-06-13T02:24:44.000000Z",
            "deleted_at": null,
            "user": {
                "id": 1,
                "name": "Annas Update",
                "email": "admin01@admin.com",
                "phone_number": "0856",
                "address": "Jl. Mabes (Update)",
                "avatar_url": "/storage/user/1/avatar.png",
                "provinsi_id": null,
                "kabupaten_id": null,
                "kecamatan_id": null,
                "email_verified_at": null,
                "created_at": "2022-06-13T02:17:51.000000Z",
                "updated_at": "2022-06-13T02:28:03.000000Z"
            },
            "provinsi": {
                "id": 11,
                "title": "ACEH"
            },
            "kabupaten": {
                "id": 1171,
                "provinsi_id": 11,
                "title": "KOTA BANDA ACEH"
            },
            "kecamatan": {
                "id": 1171020,
                "kabupaten_id": 1171,
                "title": "BAITURRAHMAN"
            }
        }
    ],
    "message": "Posts fetched."
}
```

#### UPDATE Post Land

```
  POST http://127.0.0.1:8000/api/post/{id_posts}?_method=PUT
```

| Parameter | Type     | Description                       |
| :-------- | :------- | :-------------------------------- |
| `Authorization`      | `Bearear` | **Required** |
| `title`      | `string` | **Required** |
| `desc`      | `text` | **Required** |
| `price`      | `integer` | **Required** |
| `area`      | `integer` | **Required** |
| `address`      | `string` | **Required** |
| `latitude`      | `string` | **Required** |
| `longitude`      | `string` | **Required** |
| `user_id`      | `integer` | **Required** |
| `provinsi_id`      | `integer` | **Required** |
| `kabupaten_id`      | `integer` | **Required** |
| `kecamatan_id`      | `integer` | **Required** |
| `images[]`      | `file` | **Required** |

Result :
```http
{
    "data": {
        "id": 2,
        "title": "Post Keempat Update",
        "desc": "Ini adalah percobaan update post.",
        "price": "120000000",
        "area": "1222",
        "address": "Jl Jenderal Sudirman",
        "latitude": "-7.567591846289804",
        "longitude": "110.85050209864643",
        "images": [
            "/storage/post/2/images/0.jpg",
            "/storage/post/2/images/1.png",
            "/storage/post/2/images/2.png"
        ],
        "user_id": "1",
        "provinsi_id": "11",
        "kabupaten_id": "1172",
        "kecamatan_id": "1101010",
        "created_at": "2022-06-13T02:24:42.000000Z",
        "updated_at": "2022-06-13T02:39:51.000000Z",
        "deleted_at": null
    },
    "message": "Post updated successfully."
}
```


#### DELETE Post Land

```
  DELETE http://127.0.0.1:8000/api/post/{id_posts}
```
| Parameter | Type     | Description                       |
| :-------- | :------- | :-------------------------------- |
| `Authorization`      | `Bearear` | **Required** |

```http
{
    "data": {
        "id": 3,
        "title": "Post Yang Benar Inisssss",
        "desc": "Ini adalah percobaan",
        "price": 9999999999999,
        "area": 900,
        "address": "Jl Jenderal Sudirman",
        "latitude": -7.567591846289804,
        "longitude": 110.85050209864643,
        "images": [
            "/storage/post/3/images/0.jpg",
            "/storage/post/3/images/1.png"
        ],
        "user_id": 1,
        "provinsi_id": 11,
        "kabupaten_id": 1171,
        "kecamatan_id": 1171020,
        "created_at": "2022-06-13T02:50:06.000000Z",
        "updated_at": "2022-06-13T02:50:07.000000Z",
        "deleted_at": null
    },
    "message": "Post deleted successfully."
}
```















