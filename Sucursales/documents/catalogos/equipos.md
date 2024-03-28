## Listado de equipos
Regresa el listado de equipos<br>

**URL**

    /api/catalogos/equipos

**Method:**

`GET`

**Headers**

      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data 

**Success Response:**

* **Code:** 200 <br />
  **Content:**

        {
            "equipos": [
                {
                    "id": 87,
                    "key": "1-pdv",
                    "nombre": "1 PDV",
                    "created_at": "2023-02-10 12:34:18",
                    "updated_at": "2023-02-10 12:34:18"
                },
                {
                    "id": 81,
                    "key": "adaptador-de-corriente-monitor",
                    "nombre": "Adaptador de corriente monitor",
                    "created_at": "2022-09-25 12:05:07",
                    "updated_at": "2022-09-25 12:05:07"
                },
                {
                    "id": 85,
                    "key": "audifonos",
                    "nombre": "Audifonos",
                    "created_at": "2022-11-18 10:04:13",
                    "updated_at": "2022-11-18 10:04:13"
                },
                {
                    "id": 96,
                    "key": "balun",
                    "nombre": "Balun",
                    "created_at": "2023-12-18 12:02:04",
                    "updated_at": "2023-12-18 12:02:04"
                },
                {
                    "id": 101,
                    "key": "baluns-y-pulpos",
                    "nombre": "baluns y pulpos",
                    "created_at": "2023-12-29 16:16:03",
                    "updated_at": "2023-12-29 16:16:03"
                },
                {
                    "id": 91,
                    "key": "base-de-lector-de-codigo-de-barras",
                    "nombre": "base de lector de código de barras",
                    "created_at": "2023-04-28 10:35:41",
                    "updated_at": "2023-04-28 10:35:41"
                },
                {
                    "id": 88,
                    "key": "base-lector-de-codigo",
                    "nombre": "Base lector de codigo",
                    "created_at": "2023-03-31 21:16:32",
                    "updated_at": "2023-03-31 21:16:32"
                },
                {
                    "id": 71,
                    "key": "bateria-para-no-break",
                    "nombre": "Batería para no break",
                    "created_at": "2022-02-17 10:40:20",
                    "updated_at": "2022-02-17 10:40:20"
                },
                {
                    "id": 44,
                    "key": "bocinas",
                    "nombre": "Bocinas",
                    "created_at": "2021-06-11 17:01:18",
                    "updated_at": "2021-06-11 17:01:18"
                },
                {
                    "id": 11,
                    "key": "brix",
                    "nombre": "Brix",
                    "created_at": "2020-11-10 15:35:50",
                    "updated_at": "2020-11-10 15:35:50"
                },
                {
                    "id": 74,
                    "key": "brix-captura",
                    "nombre": "BRIX CAPTURA",
                    "created_at": "2022-04-08 09:45:14",
                    "updated_at": "2022-04-08 09:45:14"
                },
                {
                    "id": 63,
                    "key": "brix-con-kingston-desde-inicio",
                    "nombre": "BRIX CON KINGSTON DESDE INICIO",
                    "created_at": "2021-10-30 11:34:28",
                    "updated_at": "2021-10-30 11:34:28"
                },
                {
                    "id": 62,
                    "key": "brix-ssd-kingston",
                    "nombre": "BRIX SSD KINGSTON",
                    "created_at": "2021-10-30 10:36:43",
                    "updated_at": "2021-10-30 10:36:43"
                }, ...
            ]
        }

**Error Response:**

* **Code:** 401 Unauthorized <br />
  **Content:**

        {
          "error": "Unauthenticated."
        }

## Equipo especifico
Regresa un equipo especificado por medio de su id.<br>

**URL**

    /api/catalogos/equipos/{id}

**Method:**

`GET`

**Headers**

      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data 

**Success Response:**

* **Code:** 200 <br />
  **Content:**

        {
            "equipos": {
                "id": 1,
                "key": "prueba",
                "nombre": "prueba",
                "created_at": "2020-11-02 15:12:16",
                "updated_at": "2020-11-02 15:12:16"
            }
        }

**Error Response:**

* **Code:** 401 Unauthorized <br />
  **Content:**

        {
          "error": "Unauthenticated."
        }

## Registro de equipo
Registra un equipo y lo retorna.<br>

**URL**

    /api/catalogos/equipos

**BODY PARAMS**

    'nombre' => 'required|unique:catalogo_equipos,nombre|max:150',
    'key' => 'unique:catalogo_equipos,key'

**Method:**

`POST`

**Headers**

      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data 

**Success Response:**

* **Code:** 200 <br />
  **Content:**

        {
            "equipo": {
                "nombre": "Equipo test",
                "key": "equipo-test",
                "updated_at": "2024-02-08 09:16:17",
                "created_at": "2024-02-08 09:16:17",
                "id": 103
            }
        }

**Error Response:**

* **Code:** 401 Unauthorized <br />
  **Content:**

        {
          "error": "Unauthenticated."
        }
