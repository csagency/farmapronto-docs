**Acceso**
----

Metodo de autentificación y acceso con oAuth 2.0 <br>
Cada usuario debera solicitar su access token para realizar solicitudes a la API

 **URL**

    /api-v2/login/custom

 **Method:**

  `POST`

 **Data Params**
    
     'email'        => 'required|string|email',
     'password'     => 'required|string',
     'tipo_usuario' => 'required|string|in:sucursal',

+ Request (application/json)
    + Body
        + FormParams
    
                [
                    'email' => 'sucursal24@grupofarmapronto.com',
                    'password' => 'secret',
                    'tipo_usuario' => 'sucursal',
                ]

**Success Response:**

* **Code:** 200 <br />
  **Content:** 

        {
            "access_token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsImp0aSI6ImQwOGJhYjU2OWEzMGE3YWZhZWVhMGMzNGExMTUxYjUxMjdiMGY5YmJmNDhhMGJhNzkwNWVjZTVmYjFkMmU2Y2JiMDViNjkyMjFiNGI3NWMyIn0.eyJhdWQiOiIyIiwianRpIjoiZDA4YmFiNTY5YTMwYTdhZmFlZWEwYzM0YTExNTFiNTEyN2IwZjliYmY0OGEwYmE3OTA1ZWNlNWZiMWQyZTZjYmIwNWI2OTIyMWI0Yjc1YzIiLCJpYXQiOjE1NjQwMDc0OTQsIm5iZiI6MTU2NDAwNzQ5NCwiZXhwIjoxNTk1NjI5ODk0LCJzdWIiOiIxNjQiLCJzY29wZXMiOltdfQ.KMA_9TTvzWJrlvPvNNco77CpFHyOU9ZzMk0u7CECU8lgbN-oNwiQX7e1nZRTe8jmgGMoqI0oYyvaWlGogTd6_foP1E3yaOY2sm0b4zVkLHYQXuKh2yeSBt0ZwImWn5E33i5h-1HzcQBmPr7LsP_Ko00GOWgheCA07xa1nuzUYNDZVpqdd86l5Yv7k4zI55fBRp9WrjDF4dzPW_hOk5Nf4gy8RLxgdELUM6WnIkQCpv3aXaMj8jq2kF-4ufWrw7j0TxX_O2-vWVRCsFnVSAG0hSeiNNZPrkqp8hS66gkof7YbMDhhkva_cVlVcJX8Vkhnw9ix8i7XVNDgfGsARbN5OJAAmiGW_hKoFtVgyTTEGM0j9omR3OwhC3XAIQQmSA94315tPoZqFswpC-XdsXe4eK6VlR1GAS8kXIkVXwNKYt9cpra9GKGf4wdLJWC2LakrQGK9RjY_DobSnPSNHvITVi0KWW84lKnSskVECYR2jLdvDPNun-6jNFwuoxSOnht4zI1mh6QFav_vNuYvKBCrHWo--D2ezWJOKRywGgma3jfHHEf-F8aVbTjvOdTSA0KVF1niA1VZSpHhg2AVUGHU6JtRxLNy6kvehtTsxLZWF7DzWVikXCfSlffr6RViwSdHdh2oaNcCk-_pNojH_GVc6XJd_SThfMfDnW4S2dTqU-s",
            "token_type": "Bearer",
            "refresh_token": "",
            "expires_at": "2019-07-31 17:31:34"
        }
            

**Error Response:**

  * **Code:** 401 Unauthorized <br />
    **Content:** 
  
          {
            "error": "Unauthorized."
          }
           
                
                
**Logout**
----

Cerrar sesión y expira el token de acceso activo

**Headers**
 
    Authorization: Bearer access_token
    Accept: application/json

**Requesting Tokens [DELETE /api-v2/logout]**

+ Response 200 (application/json) Ejemplo:
    + Body

            {
            	"token_deleted": "Token de acceso ha expirado"
            }
      
 
 
**Obtener información de un usuario tipo sucursal**
----
  Regresa la información del usuario de tipo sucursal y sus relaciones

 **URL**

    /api-v2/sucursales/{ID}

 **Method:**

  `GET`
  
  **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data
      
   **URL Params**
  
    - includes[]=sucursal.horariosAtencion, sucursal.colonia, sucursal.municipio, roles  <br><br>
    Ejemplo URI: `api-v2/sucursales/12?includes[]=sucursal.horariosAtencion`
    

 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
             "usuario": {
                "id": 133,
                "name": "Sucursal 24",
                "last_name": "YY",
                "second_last_name": "62742",
                "telephone": "0000000000",
                "clave": "SUYYCTPD",
                "email": "sucursal24@grupofarmapronto.com",
                "player_id": "3feb52c3-7280-4c7d-adbe-17824a5b63df",
                "tipo_usuario": "sucursal",
                "activo": 1,
                "baja": 0,
                "fb_id": null,
                "webhook_url": null,
                "created_at": "2017-07-05 13:45:03",
                "updated_at": "2019-12-30 20:20:41",
                "deleted_at": null,
                "last_login": "2019-09-26 18:21:37",
                "sucursal": {
                  "id": 22,
                  "user_id": 133,
                  "codigo": "24",
                  "nombre": "YY",
                  "telefono": "7772575916",
                  "colonia_id": 34661,
                  "municipio_id": 502,
                  "estado_id": 17,
                  "zona_sucursal_id": 4,
                  "ciudad_cobertura_id": null,
                  "direccion": "AV.MORELOS SUR",
                  "direccion_numero": "157",
                  "codigo_postal": "62050",
                  "lon": "-99.23195740395204",
                  "lat": "18.90517509983967",
                  "ancla": 0,
                  "checkin": 1,
                  "dias": "LUN, MAR, MIE, JUE, VIE, SAB, DOM",
                  "horario_inicio": "07:00:00",
                  "horario_final": "23:00:00",
                  "24_hrs": 0,
                  "base": 0,
                  "almacen": 1,
                  "comercializadora": 1,
                  "pickup": 0,
                  "domicilio_propios": 1,
                  "domicilio_terceros": 0,
                  "created_at": "2017-03-16 17:50:05",
                  "updated_at": "2019-12-21 12:33:40",
                  "deleted_at": null,
                  "horarios_atencion": [
                    {
                      "id": 1,
                      "sucursal_id": 22,
                      "dia": 0,
                      "dia_nombre": "Domingo",
                      "horario_inicio": "10:00:00",
                      "horario_final": "20:00:00",
                      "created_at": "2020-04-23 16:24:28",
                      "updated_at": "2020-04-23 16:24:28",
                      "deleted_at": null
                    },
                    {
                      "id": 2,
                      "sucursal_id": 22,
                      "dia": 1,
                      "dia_nombre": "Lunes",
                      "horario_inicio": "07:00:00",
                      "horario_final": "22:00:00",
                      "created_at": "2020-04-23 16:31:24",
                      "updated_at": "2020-04-23 16:33:29",
                      "deleted_at": null
                    }
                  ],
                  "colonia": {
                    "id": 34661,
                    "municipio_id": 502,
                    "codigo_postal": "62050",
                    "nombre": "LAS PALMAS SUR",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  }
                }
             }
        }
 
**Error Response:**

  * **Code:** 401 Unauthorized <br />
      **Content:** 
      
          {
            "error": "Unauthenticated."
          }

**Actualización del usuario sucursal**
----
  Actualiza la información del usuario sucursal

 **URL**

    /api-v2/sucursales/me

 **Method:**

  `PUT`
    
 **Headers**
 
    Authorization: Bearer access_token
    Accept: application/json
    Content-Type: application/x-www-form-urlencoded

    
 **application/x-www-form-urlencoded**
 
    'name' => '',
    'last_name' => '',
    'second_last_name' => '',
    'telephone' => '',
    'email' => 'email|unique:users,email,'.auth()->user()->id,
    'password' => 'min:6',
    'colonia_id' => '',
    'player_id' => '',
    'comercializadora' => 'nullable|boolean',
    
 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
        	"usuario": {
                "id": 133,
                "name": "Sucursal 24",
                "last_name": "YY",
                "second_last_name": "62742",
                "telephone": "0000000000",
                "clave": "SUYYCTPD",
                "email": "sucursal24@grupofarmapronto.com",
                "player_id": "3feb52c3-7280-4c7d-adbe-17824a5b63df",
                "tipo_usuario": "sucursal",
                "activo": 1,
                "baja": 0,
                "fb_id": null,
                "webhook_url": null,
                "created_at": "2017-07-05 13:45:03",
                "updated_at": "2019-12-30 20:20:41",
                "deleted_at": null,
                "last_login": "2019-09-26 18:21:37",
                "sucursal": {
                  "id": 22,
                  "user_id": 133,
                  "codigo": "24",
                  "nombre": "YY",
                  "telefono": "7772575916",
                  "colonia_id": 34661,
                  "municipio_id": 502,
                  "estado_id": 17,
                  "zona_sucursal_id": 4,
                  "ciudad_cobertura_id": null,
                  "direccion": "AV.MORELOS SUR",
                  "direccion_numero": "157",
                  "codigo_postal": "62050",
                  "lon": "-99.23195740395204",
                  "lat": "18.90517509983967",
                  "ancla": 0,
                  "checkin": 1,
                  "dias": "LUN, MAR, MIE, JUE, VIE, SAB, DOM",
                  "horario_inicio": "07:00:00",
                  "horario_final": "23:00:00",
                  "24_hrs": 0,
                  "base": 0,
                  "almacen": 1,
                  "comercializadora": 1,
                  "pickup": 0,
                  "domicilio_propios": 1,
                  "domicilio_terceros": 0,
                  "created_at": "2017-03-16 17:50:05",
                  "updated_at": "2019-12-21 12:33:40",
                  "deleted_at": null
                },
                "roles": [
                  {
                    "id": 2,
                    "role": "Sucursal",
                    "key": "sucursal",
                    "created_at": "2018-04-16 11:11:52",
                    "updated_at": "2018-04-16 11:11:52",
                    "pivot": {
                      "user_id": 133,
                      "rol_id": 2
                    }
                  },
                  {
                    "id": 1,
                    "role": "Cliente",
                    "key": "cliente",
                    "created_at": "2018-04-16 11:11:52",
                    "updated_at": "2018-04-16 11:11:52",
                    "pivot": {
                      "user_id": 133,
                      "rol_id": 1
                    }
                  }
                ]
            }
        }

 **Error Response:**

  * **Code:** 401 Unauthorized <br />
    **Content:** 
    
        {
          "error": "Unauthenticated."
        }

**Listado de sucursales y sus usuarios**
----
  Regresa la información del sucursales y sus usuarios

 **URL**

    /api-v2/sucursales?limit=2
 
 
 **Parametros**
 - limit | numérico, define el total de resultados por petición
 - includes[] incluye relaciones del modelo 
    - user
    - users
    - colonia
    - municipio
    - estado
    - listaPrecio
    - pedidos
    - horariosAtencion
  
 **Method:**

  `GET`
  
  **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json

 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
        	"sucursales": [
                {
                  "id": 1,
                  "user_id": 5396,
                  "codigo": "1",
                  "nombre": "AA",
                  "telefono": "7772575993",
                  "colonia_id": 34727,
                  "municipio_id": 502,
                  "estado_id": 17,
                  "zona_sucursal_id": 3,
                  "ciudad_cobertura_id": null,
                  "direccion": "AV. VICENTE GUERRERO",
                  "direccion_numero": "107",
                  "codigo_postal": "62230",
                  "lon": "-99.23085095421447",
                  "lat": "18.95742636448077",
                  "ancla": 0,
                  "checkin": 0,
                  "dias": "LUN, MAR, MIE, JUE, VIE, SAB, DOM",
                  "horario_inicio": "07:00:00",
                  "horario_final": "22:59:00",
                  "24_hrs": 0,
                  "base": 0,
                  "almacen": 0,
                  "comercializadora": 1,
                  "pickup": 0,
                  "domicilio_propios": 1,
                  "domicilio_terceros": 0,
                  "created_at": "2017-03-16 17:50:05",
                  "updated_at": "2019-10-22 11:25:11",
                  "deleted_at": null,
                  "user": {
                    "id": 5396,
                    "name": "SUCURSAL",
                    "last_name": "AA",
                    "second_last_name": ".",
                    "telephone": "7772575993",
                    "clave": null,
                    "email": "sucursal1@grupofarmapronto.com",
                    "player_id": "6eacbbe4-d1ff-4b4a-818c-c9bdbc061eea",
                    "tipo_usuario": "sucursal",
                    "activo": 1,
                    "baja": 0,
                    "fb_id": null,
                    "webhook_url": null,
                    "created_at": "2018-09-04 17:03:52",
                    "updated_at": "2020-03-18 07:14:53",
                    "deleted_at": null,
                    "last_login": "2020-03-18 07:14:53"
                  },
                  "users": []
                },
                {
                  "id": 2,
                  "user_id": 54,
                  "codigo": "2",
                  "nombre": "BB",
                  "telefono": "",
                  "colonia_id": 18488,
                  "municipio_id": 365,
                  "estado_id": 12,
                  "zona_sucursal_id": 1,
                  "ciudad_cobertura_id": null,
                  "direccion": "AV. INSURGENTES",
                  "direccion_numero": "28",
                  "codigo_postal": "39010",
                  "lon": "-99.5080652",
                  "lat": "17.5628592",
                  "ancla": 0,
                  "checkin": 0,
                  "dias": "LUN, MAR, MIE, JUE, VIE, SAB, DOM",
                  "horario_inicio": "07:00:00",
                  "horario_final": "22:30:00",
                  "24_hrs": 0,
                  "base": 0,
                  "almacen": 0,
                  "comercializadora": 1,
                  "pickup": 0,
                  "domicilio_propios": 1,
                  "domicilio_terceros": 0,
                  "created_at": "2017-03-16 17:50:05",
                  "updated_at": "2019-05-21 10:55:47",
                  "deleted_at": null,
                  "user": {
                    "id": 54,
                    "name": "Sucursal 3",
                    "last_name": "CC",
                    "second_last_name": "39000",
                    "telephone": "0000000000",
                    "clave": null,
                    "email": "sucursal3@grupofarmapronto.com",
                    "player_id": "418aa64d-76ff-4bd6-a2e1-9b5645048835",
                    "tipo_usuario": "sucursal",
                    "activo": 1,
                    "baja": 0,
                    "fb_id": null,
                    "webhook_url": null,
                    "created_at": "2017-07-05 13:45:00",
                    "updated_at": "2019-12-09 14:17:09",
                    "deleted_at": null,
                    "last_login": null
                  },
                  "users": []
                }
            ]
        }
 
**Error Response:**

  * **Code:** 401 Unauthorized <br />
      **Content:** 
      
          {
            "error": "Unauthenticated."
          }

**Datos del usuario tipo sucursal**
----
  Regresa la información del usuario de tipo sucursal y sus relaciones

 **URL**

    /api-v2/sucursales/me

 **Method:**

  `GET`
  
  **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data

 **URL Params**
  
    - includes[]=sucursal.horariosAtencion, sucursal.colonia, sucursal.municipio, roles  <br><br>
    Ejemplo URI: `api-v2/sucursales/12?includes[]=sucursal`
    
  
 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
            "usuario": {
                "id": 133,
                "name": "Sucursal 24",
                "last_name": "YY",
                "second_last_name": "62742",
                "telephone": "0000000000",
                "clave": "SUYYCTPD",
                "email": "sucursal24@grupofarmapronto.com",
                "player_id": "3feb52c3-7280-4c7d-adbe-17824a5b63df",
                "tipo_usuario": "sucursal",
                "activo": 1,
                "baja": 0,
                "fb_id": null,
                "webhook_url": null,
                "created_at": "2017-07-05 13:45:03",
                "updated_at": "2019-12-30 20:20:41",
                "deleted_at": null,
                "last_login": "2019-09-26 18:21:37",
                "sucursal": {
                  "id": 22,
                  "user_id": 133,
                  "codigo": "24",
                  "nombre": "YY",
                  "telefono": "7772575916",
                  "colonia_id": 34661,
                  "municipio_id": 502,
                  "estado_id": 17,
                  "zona_sucursal_id": 4,
                  "ciudad_cobertura_id": null,
                  "direccion": "AV.MORELOS SUR",
                  "direccion_numero": "157",
                  "codigo_postal": "62050",
                  "lon": "-99.23195740395204",
                  "lat": "18.90517509983967",
                  "ancla": 0,
                  "checkin": 1,
                  "dias": "LUN, MAR, MIE, JUE, VIE, SAB, DOM",
                  "horario_inicio": "07:00:00",
                  "horario_final": "23:00:00",
                  "24_hrs": 0,
                  "base": 0,
                  "almacen": 1,
                  "comercializadora": 1,
                  "pickup": 0,
                  "domicilio_propios": 1,
                  "domicilio_terceros": 0,
                  "created_at": "2017-03-16 17:50:05",
                  "updated_at": "2019-12-21 12:33:40",
                  "deleted_at": null
            }
        }
 
**Error Response:**

  * **Code:** 401 Unauthorized <br />
      **Content:** 
      
          {
            "error": "Unauthenticated."
          }
          
          
**Checkin**
----
Realiza checkin de la sucursal

**URL**

    /api-v2/sucursales/checkin

**Method:**

`POST`
  
**Headers**

    Authorization: Bearer access_token
    Accept: application/json
    Content-Type: application/x-www-form-urlencoded
  
**Success Response:**

* **Code:** 200 <br />
  **Content:** 
  
      {
        "check": {
            "sucursal_id": 22,
            "user_id": 133,
            "tipo": "checkin",
            "updated_at": "2020-04-27 18:07:27",
            "created_at": "2020-04-27 18:07:27",
            "id": 2,
            "sucursal": {
              "id": 22,
              "user_id": 133,
              "codigo": "24",
              "nombre": "YY",
              "telefono": "7772575916",
              "colonia_id": 34661,
              "municipio_id": 502,
              "estado_id": 17,
              "zona_sucursal_id": 4,
              "ciudad_cobertura_id": null,
              "direccion": "AV.MORELOS SUR",
              "direccion_numero": "157",
              "codigo_postal": "62050",
              "lon": "-99.23195740395204",
              "lat": "18.90517509983967",
              "ancla": 0,
              "checkin": 1,
              "dias": "LUN, MAR, MIE, JUE, VIE, SAB, DOM",
              "horario_inicio": "07:00:00",
              "horario_final": "23:00:00",
              "24_hrs": 0,
              "base": 0,
              "almacen": 1,
              "comercializadora": 1,
              "pickup": 0,
              "domicilio_propios": 1,
              "domicilio_terceros": 0,
              "disponible": 1,
              "created_at": "2017-03-16 17:50:05",
              "updated_at": "2020-04-27 18:07:27",
              "deleted_at": null
            }
        }
      }

**Error Response:**

* **Code:** 401 Unauthorized <br />
  **Content:** 
  
      {
        "error": "Unauthenticated."
      }

**Último Checkin**
----
Regresa la información del último checkin del día de la sucursal

**URL**

    /api-v2/sucursales/checkin/last

**Method:**

`POST`
  
**Headers**

    Authorization: Bearer access_token
    Accept: application/json
    Content-Type: application/x-www-form-urlencoded
  
**Success Response:**

* **Code:** 200 <br />
  **Content:** 
  
      {
          "checkin": {
            "id": 4,
            "sucursal_id": 22,
            "user_id": 133,
            "check_id": null,
            "tipo": "checkin",
            "created_at": "2020-04-29 13:22:23",
            "updated_at": "2020-04-29 13:22:23",
            "deleted_at": null,
            "sucursal": {
              "id": 22,
              "user_id": 133,
              "codigo": "24",
              "nombre": "YY",
              "telefono": "7772575916",
              "colonia_id": 34661,
              "municipio_id": 502,
              "estado_id": 17,
              "zona_sucursal_id": 4,
              "ciudad_cobertura_id": 1,
              "direccion": "AV.MORELOS SUR",
              "direccion_numero": "157",
              "codigo_postal": "62050",
              "lon": "-99.23195740395204",
              "lat": "18.90517509983967",
              "ancla": 0,
              "checkin": 1,
              "dias": "LUN, MAR, MIE, JUE, VIE, SAB, DOM",
              "horario_inicio": "07:00:00",
              "horario_final": "23:00:00",
              "24_hrs": 0,
              "base": 0,
              "almacen": 1,
              "comercializadora": 1,
              "pickup": 0,
              "domicilio_propios": 1,
              "domicilio_terceros": 0,
              "disponible": 1,
              "created_at": "2017-03-16 17:50:05",
              "updated_at": "2020-04-29 13:22:23",
              "deleted_at": null
            },
            "user": {
              "id": 133,
              "name": "Sucursal 24",
              "last_name": "YY",
              "second_last_name": "62742",
              "telephone": "0000000000",
              "clave": "SUYYCTPD",
              "email": "sucursal24@grupofarmapronto.com",
              "player_id": null,
              "tipo_usuario": "sucursal",
              "activo": 1,
              "baja": 0,
              "fb_id": null,
              "webhook_url": null,
              "created_at": "2017-07-05 13:45:03",
              "updated_at": "2020-04-27 18:09:38",
              "deleted_at": null,
              "last_login": "2019-09-26 18:21:37"
            }
          }
      }

**Error Response:**

* **Code:** 401 Unauthorized <br />
  **Content:** 
  
      {
        "error": "Unauthenticated."
      }
      
**Obtiene código de verificación**
----
  Actualiza el código de verificación de sucursal 

 **URL**

    /api-v2/sucursales/codigo-verificacion

 **Method:**

  `POST`
    
 **Headers**
 
    Accept: application/json
    
 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
        	"user": {
                "id": 133,
                "name": "Sucursal 24",
                "last_name": "YY",
                "second_last_name": "62742",
                "telephone": "527772273622",
                "clave": "SUYYCTPD",
                "email": "sucursal24@grupofarmapronto.com",
                "player_id": "3feb52c3-7280-4c7d-adbe-17824a5b63df",
                "tipo_usuario": "sucursal",
                "activo": 1,
                "baja": 0,
                "fb_id": null,
                "webhook_url": null,
                "created_at": "2017-07-05 13:45:03",
                "updated_at": "2020-05-21 11:39:55",
                "deleted_at": null,
                "last_login": "2019-09-26 18:21:37",
                "plain_code": 4909,
                "nombre_completo": "Sucursal 24 YY",
                "sucursal": {
                  "id": 22,
                  "user_id": 133,
                  "codigo": "24",
                  "nombre": "YY",
                  "telefono": "7772575916",
                  "colonia_id": 34661,
                  "municipio_id": 502,
                  "estado_id": 17,
                  "zona_sucursal_id": 4,
                  "ciudad_cobertura_id": 1,
                  "direccion": "AV.MORELOS SUR",
                  "direccion_numero": "157",
                  "codigo_postal": "62050",
                  "lon": "-99.23195740395204",
                  "lat": "18.90517509983967",
                  "ancla": 0,
                  "checkin": 1,
                  "dias": "LUN, MAR, MIE, JUE, VIE, SAB, DOM",
                  "horario_inicio": "07:00:00",
                  "horario_final": "23:00:00",
                  "24_hrs": 0,
                  "base": 0,
                  "almacen": 1,
                  "comercializadora": 1,
                  "pickup": 0,
                  "domicilio_propios": 1,
                  "domicilio_terceros": 0,
                  "disponible": 0,
                  "created_at": "2017-03-16 17:50:05",
                  "updated_at": "2020-05-08 16:28:10",
                  "deleted_at": null
                }
            }
        }

        
**Error Response:**

  * **Code:** 401 Unauthorized <br />
      **Content:** 
      
          {
            "error": "Unauthenticated."
          }
        
* **Code:** 404 Not Found <br />
    **Content:** 
    
        {
            "message": "Sucursal no disponible"
        }
       

**Valida código de verificación**
----
  Valida el código de verificación de sucursal 

 **URL**

    /api-v2/sucursales/verificar

 **Method:**

  `POST`
    
 **Headers**
 
    Accept: application/json
    
 **Body**
 
    'codigo_verificacion' => 'required'
    
 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
        	"user": {
                "id": 133,
                "name": "Sucursal 24",
                "last_name": "YY",
                "second_last_name": "62742",
                "telephone": "527772273622",
                "clave": "SUYYCTPD",
                "email": "sucursal24@grupofarmapronto.com",
                "player_id": "3feb52c3-7280-4c7d-adbe-17824a5b63df",
                "tipo_usuario": "sucursal",
                "activo": 1,
                "baja": 0,
                "fb_id": null,
                "webhook_url": null,
                "created_at": "2017-07-05 13:45:03",
                "updated_at": "2020-05-21 11:39:55",
                "deleted_at": null,
                "last_login": "2019-09-26 18:21:37",
                "nombre_completo": "Sucursal 24 YY",
                "sucursal": {
                  "id": 22,
                  "user_id": 133,
                  "codigo": "24",
                  "nombre": "YY",
                  "telefono": "7772575916",
                  "colonia_id": 34661,
                  "municipio_id": 502,
                  "estado_id": 17,
                  "zona_sucursal_id": 4,
                  "ciudad_cobertura_id": 1,
                  "direccion": "AV.MORELOS SUR",
                  "direccion_numero": "157",
                  "codigo_postal": "62050",
                  "lon": "-99.23195740395204",
                  "lat": "18.90517509983967",
                  "ancla": 0,
                  "checkin": 1,
                  "dias": "LUN, MAR, MIE, JUE, VIE, SAB, DOM",
                  "horario_inicio": "07:00:00",
                  "horario_final": "23:00:00",
                  "24_hrs": 0,
                  "base": 0,
                  "almacen": 1,
                  "comercializadora": 1,
                  "pickup": 0,
                  "domicilio_propios": 1,
                  "domicilio_terceros": 0,
                  "disponible": 0,
                  "created_at": "2017-03-16 17:50:05",
                  "updated_at": "2020-05-08 16:28:10",
                  "deleted_at": null
                }
            }
        }

                
**Error Response:**

  * **Code:** 401 Unauthorized <br />
      **Content:** 
      
          {
            "error": "Unauthenticated."
          }
          
* **Code:** 422 Unproccesable Entity <br />
    **Content:** 
    
        {
              "codigo_verificacion": [
                "El campo codigo verificacion es obligatorio."
              ]
        }
        
* **Code:** 404 Not Found <br />
    **Content:** 
    
        {
            "message": "Sucursal no disponible"
        }
               
* **Code:** 410 Gone <br />
    **Content:** 
    
        {
            "message": "Código de verificación incorrecto."
        }