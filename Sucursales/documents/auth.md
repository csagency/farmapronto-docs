**Acceso**
----

Metodo de autentificación y acceso con oAuth 2.0
Cada usuario debera solicitar su access token para realizar solicitudes a la API


 **URL**

    /oauth/token

 **Method:**

  `POST`
      
  **Data Params**
      
       'grant_type' => 'required',
       'client_id' => 'required',
       'client_secret' => 'required',
       'username' => 'required',
       'password' => 'required',
       'scope' => 'required',

+ Example
    + Body
        + FormParams
    
                [
                    'grant_type' => 'password',
                    'client_id' => '2',
                    'client_secret' => 'hi300IT8Ae6lLbMWlszf6brrJE0WzlYrcU3TymvM',
                    'username' => 'admin@farmapronto-sucursales.com',
                    'password' => 'secret', 
                    'scope' => '*',
                ]


**Success Response:**

  * **Code:** 200 <br />
    **Content:** 

        {
          "token_type": "Bearer",
          "expires_in": 3155677200,
          "access_token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsImp0aSI6IjdhODdkMGJjMmVlMTJhNmQ3ZTI5NmY2OGQwYzI2YjIwMmQ2NDZjODNjYTEzY2FlYTJiY2E4MjY1YzNmMGViOGJkOGUzODE4YmQxZWU1ZDYxIn0.eyJhdWQiOiIyIiwianRpIjoiN2E4N2QwYmMyZWUxMmE2ZDdlMjk2ZjY4ZDBjMjZiMjAyZDY0NmM4M2NhMTNjYWVhMmJjYTgyNjVjM2YwZWI4YmQ4ZTM4MThiZDFlZTVkNjEiLCJpYXQiOjE0NzYzNzYzODgsIm5iZiI6MTQ3NjM3NjM4OCwiZXhwIjo0NjMyMDUzNTg4LCJzdWIiOiI1Iiwic2NvcGVzIjpbIioiXX0.tei_23uMOiMsULzH0udypr7QU4JcQ7ulCn8tNMCsIojxgDRwDc6mJF8ilCOY8dHEcirrqZ0DpKTTgCnIYuSg8amKprqqIrgB2_WOxMRidHkCHtj297SJysTPMvTSOiPp8EzCJsbmYJ9kiuC-SC5b-ShmBsFnMB8w7hgCOv7aueJU4xndemUryXF6n1_AZtUdbvhN-ehyAaFk4OUfgZMy9I9fCxfuWeRrZvJBYWz7U3MBSnHKvH-U0mnnKYZ_8cCiQYYJlC625j4msuOWwR6Lr8fqSsU8L5KtGwrdTITaPeVwSzDpfGbvVjyAjRjeSq0lpYVlIymyFZD0T7NvHQW1hmShHiWMKQpKO16vEj8fgew7QJY123p3z0ljXKDhozLp54BWjBuhAlZWxyx5SQUOm9iQhgTA21MGFUmP2MUglvUGQkohqj6gwKJhJ0goowaRHhxeahQiRl4msHnk2e5HuWAPmFU0mwcrvWmaSnlzptCnm5-Y6fLmTYG50zHRmukabcBjcaLiaIcnfhNjeXX3QxPr4mPOOm_TvBb43PNMo6y3FJm47fBHaQw_KloUlXkp9w9EIVVEUwxomailyxxmNk8s73cGFXCgHwNz1CDl2sv80b-8AuXwD-eB__86wI1NZIgpudKW7_nIz3b4KCMAvEl5Fl5KRoHNXcP3ssiNagc",
          "refresh_token": "MPPIVvvE+QgrLYB9ZmhG6UXmzDKWC+lHIlU/vgSRbRISPDMm2h2OnWcblJZq9KAcZglnEfLUDispII1XAZ3rewULHbmSWhygMaFe1CNJvr7OS0i7tYS5tymA3Av7pfCqzMUn/x3aXYdsbr7gwjJTrKW9ljBZnND8CfhKl+byrXPmzoWXYG/4k6YZ8c7PG2WPHzNdcsT4xAYHFJio8NIg0tQtERlGIyjuQzGOjQJK8+1HLV2dUpK1S9r2qgKX+naaM7QPZrGKzMdH51G3r7e/Ke6C0ks0tNNY2O519W3eJTAB1StGMKw9WD6zXsdr6P+LSPTovvGjYuASP0YdUVqjigq/ZVMzF+Kodz9gC3ZXggM+UV/EGFrE6j29uxJE6wyiYpl87642p63bFjsHQb+2lBrfVwaSCsrCDk5FYgioSWIawwGlkMtr2UZrUVvzvKwdiSfOW3d7hCFe1zsa88gGg/YXeOvX32ClY/CHuzllD9wotf+OP+uyywfAclCbuA2QTxUrROFOWUsdqgAaGP/9Slf8R5fZG/GpVG1zfp6JReaWccoYtfw8sTM14YaSUOkP79LT8SpRbHk/tqQr8S5HEfxVxFG2ZhA+4m8MHrtcAqI9x9TsjJSbxk/0fW0/hgA6CBGNHHEFBowRF5HMnBWw6LIdycXwDEFwJO6S2RIrlrg="
        }
                
 
                
**Logout**
----

Cerrar sesión y expira el token de acceso activo <br>

 **URL**

    /api/logout

 **Method:**

  `DELETE`
  
  **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data

**Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
            "token_deleted": "Token de acceso ha expirado"
        }
        

## Ver perfil
Regresa el perfil del usuario

 **URL**

    /api/me

 **Method:**

  `GET`
  
 **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data
      
     
 **URL Params**

      - includes[] = perfilSupervisor.zona.sucursales, perfilCapacitadora.zona.sucursales, perfilEncargada.sucursal, perfilGerente.area
        Ejemplo URI: `api/me?includes[]=perfilEncargada.sucursal`


**Success Response:**

* **Code:** 200 <br />
  **Content:** 
  
      {
        "usuario": {
            "id": 13,
            "nombre": "Encargada",
            "apellidos": "Prueba",
            "telefono": "5555555555",
            "player_id": null,
            "email": "encargada@farmapronto-sucursales.com",
            "email_verified_at": null,
            "created_at": "2019-06-27 17:59:19",
            "updated_at": "2019-06-27 17:59:19",
            "deleted_at": null,
            "perfil_encargada": {
              "id": 2,
              "user_id": 13,
              "sucursal_id": 4,
              "created_at": "2019-06-27 17:59:19",
              "updated_at": "2019-06-27 17:59:19",
              "deleted_at": null,
              "sucursal": {
                "id": 4,
                "nombre": "gsdg",
                "codigo": "gdsfg",
                "direccion": "gfsdg",
                "lat": null,
                "lon": null,
                "meta_encargadas": 3,
                "meta_auxiliares": 3,
                "meta_cajeras": 3,
                "fondo_venta_mensual": null,
                "fondo_callcenter": 3,
                "matutino": 1,
                "vespertino": 1,
                "intermedio": 0,
                "fondo_asignado": 3333333,
                "created_at": "2019-06-25 18:07:37",
                "updated_at": "2019-06-25 18:07:37",
                "deleted_at": null
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
        

## Editar perfil
Regresa el perfil actualizado del usuario

 **URL**

    /api/me

 **Method:**

  `POST`
  
 **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data
      
   
 **Data Params**
    
     'nombre' => 'nullable',
     'apellidos' => 'nullable',
     'telefono' => 'nullable',
     'player_id' => 'nullable',
     'email' => 'nullable|email|unique',
     'password' => 'nullable|min:6',


**Success Response:**

* **Code:** 200 <br />
  **Content:** 
  
      {
        "usuario": {
            "id": 13,
            "nombre": "Encargada",
            "apellidos": "Prueba",
            "telefono": "5555555555",
            "player_id": "1234567890",
            "email": "encargada@farmapronto-sucursales.com",
            "email_verified_at": null,
            "created_at": "2019-06-27 17:59:19",
            "updated_at": "2019-07-04 19:00:09",
            "deleted_at": null
        }
      }

**Error Response:**

 * **Code:** 401 Unauthorized <br />
   **Content:** 
  
       {
         "error": "Unauthenticated."
       }  
       
                   
## Actualizar ubicación del usuario
Regresa el perfil con las ubicaciones del usuario

 **URL**

    /api/location

 **Method:**

  `POST`
  
 **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data
      
   
 **Data Params**
    
     'lat' => 'required',
     'lon' => 'required',


**Success Response:**

* **Code:** 200 <br />
  **Content:** 
  
      {
        "user": {
            "id": 17,
            "perfil_id": null,
            "nombre": "Supervisor",
            "apellido_paterno": "Prueba",
            "apellido_materno": null,
            "telefono": "Farma",
            "player_id": null,
            "email": "supervisor@farmapronto-sucursales.com",
            "email_verified_at": null,
            "created_at": "2019-07-03 18:55:53",
            "updated_at": "2019-07-03 18:55:53",
            "deleted_at": null,
            "ultima_ubicacion_dia": {
              "id": 7,
              "user_id": 17,
              "lat": "18.9458269",
              "lon": "-99.2231424",
              "fuera_rango": 1,
              "created_at": "2019-08-13 17:20:28",
              "updated_at": "2019-08-13 17:20:28",
              "deleted_at": null
            },
            "ubicaciones": [
              {
                "id": 1,
                "user_id": 17,
                "lat": "18.9458269",
                "lon": "-99.2231424",
                "fuera_rango": 1,
                "created_at": "2019-08-13 14:20:45",
                "updated_at": "2019-08-13 14:22:45",
                "deleted_at": null
              },
              {
                "id": 3,
                "user_id": 17,
                "lat": "18.9458269",
                "lon": "-99.2231424",
                "fuera_rango": 1,
                "created_at": "2019-08-13 14:31:48",
                "updated_at": "2019-08-13 14:31:48",
                "deleted_at": null
              },
              {
                "id": 4,
                "user_id": 17,
                "lat": "18.9458269",
                "lon": "-99.2231424",
                "fuera_rango": 1,
                "created_at": "2019-08-13 14:32:01",
                "updated_at": "2019-08-13 14:32:01",
                "deleted_at": null
              },
              {
                "id": 5,
                "user_id": 17,
                "lat": "18.9458269",
                "lon": "-99.2231424",
                "fuera_rango": 0,
                "created_at": "2019-08-13 17:19:47",
                "updated_at": "2019-08-13 17:19:47",
                "deleted_at": null
              },
              {
                "id": 6,
                "user_id": 17,
                "lat": "18.9458269",
                "lon": "-99.2231424",
                "fuera_rango": 1,
                "created_at": "2019-08-13 17:20:06",
                "updated_at": "2019-08-13 17:20:06",
                "deleted_at": null
              },
              {
                "id": 7,
                "user_id": 17,
                "lat": "18.9458269",
                "lon": "-99.2231424",
                "fuera_rango": 1,
                "created_at": "2019-08-13 17:20:28",
                "updated_at": "2019-08-13 17:20:28",
                "deleted_at": null
              },
              {
                "id": 8,
                "user_id": 17,
                "lat": "18.9458269",
                "lon": "-99.2231424",
                "fuera_rango": 1,
                "created_at": "2019-08-13 17:21:28",
                "updated_at": "2019-08-13 17:21:28",
                "deleted_at": null
              }
            ],
            "alertas": [
              {
                "id": 1,
                "user_id": 17,
                "alerta_id": 1,
                "lat": "18.9458269",
                "lon": "-99.2231424",
                "created_at": "2019-08-13 14:31:48",
                "updated_at": "2019-08-13 14:31:48",
                "deleted_at": null
              },
              {
                "id": 2,
                "user_id": 17,
                "alerta_id": 1,
                "lat": "18.9458269",
                "lon": "-99.2231424",
                "created_at": "2019-08-13 17:19:47",
                "updated_at": "2019-08-13 17:19:47",
                "deleted_at": null
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