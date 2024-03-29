      
**Acceso**
----

Metodo de autentificación y acceso con oAuth 2.0
Cada usuario debera solicitar su access token para realizar solicitudes a la API

**URL**

    /api-v2/login/usersapp

 **Method:**

  `POST`
  

 **Data Params**
   
    [
        'grant_type' => 'password',
        'client_id' => '1',
        'client_secret' => 'GNqBUGJIRLv5gTf7D6RdE3uPwUT1zmFPNkXhRZSF',
        'username' => '',
        'password' => 'secret', 
        'scope' => '*',
    ]

+ Response 200 (application/json) Ejemplo:
    + Body

            {
              "token_type": "Bearer",
              "expires_in": 3155677200,
              "access_token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsImp0aSI6IjdhODdkMGJjMmVlMTJhNmQ3ZTI5NmY2OGQwYzI2YjIwMmQ2NDZjODNjYTEzY2FlYTJiY2E4MjY1YzNmMGViOGJkOGUzODE4YmQxZWU1ZDYxIn0.eyJhdWQiOiIyIiwianRpIjoiN2E4N2QwYmMyZWUxMmE2ZDdlMjk2ZjY4ZDBjMjZiMjAyZDY0NmM4M2NhMTNjYWVhMmJjYTgyNjVjM2YwZWI4YmQ4ZTM4MThiZDFlZTVkNjEiLCJpYXQiOjE0NzYzNzYzODgsIm5iZiI6MTQ3NjM3NjM4OCwiZXhwIjo0NjMyMDUzNTg4LCJzdWIiOiI1Iiwic2NvcGVzIjpbIioiXX0.tei_23uMOiMsULzH0udypr7QU4JcQ7ulCn8tNMCsIojxgDRwDc6mJF8ilCOY8dHEcirrqZ0DpKTTgCnIYuSg8amKprqqIrgB2_WOxMRidHkCHtj297SJysTPMvTSOiPp8EzCJsbmYJ9kiuC-SC5b-ShmBsFnMB8w7hgCOv7aueJU4xndemUryXF6n1_AZtUdbvhN-ehyAaFk4OUfgZMy9I9fCxfuWeRrZvJBYWz7U3MBSnHKvH-U0mnnKYZ_8cCiQYYJlC625j4msuOWwR6Lr8fqSsU8L5KtGwrdTITaPeVwSzDpfGbvVjyAjRjeSq0lpYVlIymyFZD0T7NvHQW1hmShHiWMKQpKO16vEj8fgew7QJY123p3z0ljXKDhozLp54BWjBuhAlZWxyx5SQUOm9iQhgTA21MGFUmP2MUglvUGQkohqj6gwKJhJ0goowaRHhxeahQiRl4msHnk2e5HuWAPmFU0mwcrvWmaSnlzptCnm5-Y6fLmTYG50zHRmukabcBjcaLiaIcnfhNjeXX3QxPr4mPOOm_TvBb43PNMo6y3FJm47fBHaQw_KloUlXkp9w9EIVVEUwxomailyxxmNk8s73cGFXCgHwNz1CDl2sv80b-8AuXwD-eB__86wI1NZIgpudKW7_nIz3b4KCMAvEl5Fl5KRoHNXcP3ssiNagc",
              "refresh_token": "MPPIVvvE+QgrLYB9ZmhG6UXmzDKWC+lHIlU/vgSRbRISPDMm2h2OnWcblJZq9KAcZglnEfLUDispII1XAZ3rewULHbmSWhygMaFe1CNJvr7OS0i7tYS5tymA3Av7pfCqzMUn/x3aXYdsbr7gwjJTrKW9ljBZnND8CfhKl+byrXPmzoWXYG/4k6YZ8c7PG2WPHzNdcsT4xAYHFJio8NIg0tQtERlGIyjuQzGOjQJK8+1HLV2dUpK1S9r2qgKX+naaM7QPZrGKzMdH51G3r7e/Ke6C0ks0tNNY2O519W3eJTAB1StGMKw9WD6zXsdr6P+LSPTovvGjYuASP0YdUVqjigq/ZVMzF+Kodz9gC3ZXggM+UV/EGFrE6j29uxJE6wyiYpl87642p63bFjsHQb+2lBrfVwaSCsrCDk5FYgioSWIawwGlkMtr2UZrUVvzvKwdiSfOW3d7hCFe1zsa88gGg/YXeOvX32ClY/CHuzllD9wotf+OP+uyywfAclCbuA2QTxUrROFOWUsdqgAaGP/9Slf8R5fZG/GpVG1zfp6JReaWccoYtfw8sTM14YaSUOkP79LT8SpRbHk/tqQr8S5HEfxVxFG2ZhA+4m8MHrtcAqI9x9TsjJSbxk/0fW0/hgA6CBGNHHEFBowRF5HMnBWw6LIdycXwDEFwJO6S2RIrlrg="
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

       
**Registro de cliente**
----
  Regresa la información del registro en formato json

 **URL**

    /api-v2/clientes/registro

 **Method:**

  `POST`
 
 **Data Params**
    
     'name' => 'required',
     'last_name' => 'required',
     'second_last_name' => 'nullable',
     'telephone' => 'required|numeric|digits_between:10,12',
     'email' => 'required|email',
     'codigo_postal' => 'required',
     'fecha_nacimiento' => 'required',
     'terminos' => 'required',
     'aviso' => 'required',



 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 

            {
                "cliente": {
                    "telephone": "527772273622",
                    "name": "Abril",
                    "last_name": "Prueba",
                    "second_last_name": "V2",
                    "email": "jabrilmtz17@gmail.com",
                    "clave": "ABPRELSY",
                    "updated_at": "2020-04-20 22:22:55",
                    "created_at": "2020-04-20 22:22:55",
                    "id": 23516,
                    "cliente_direcciones": [],
                    "cliente_perfil": {
                      "id": 23097,
                      "user_id": 23516,
                      "active": 1,
                      "deleted_at": null,
                      "created_at": "2020-04-20 22:22:55",
                      "updated_at": "2020-04-20 22:22:55",
                      "sexo": null,
                      "fecha_nacimiento": "1995-08-17",
                      "edad": null,
                      "imagen": null,
                      "imagen_path": null,
                      "zona_id": null,
                      "especial": 0,
                      "lat": null,
                      "lon": null,
                      "categoria_id": null,
                      "codigo_postal": null
                    }
                  }
            }


 **Error Response:**

  * **Code:** 422 Unprocessable Entity <br />
    **Content:** 
    
        {
            "name": [
              "El campo nombre es obligatorio."
            ],
            "last_name": [
              "El campo primer apellido es obligatorio."
            ],
            "telephone": [
              "El campo teléfono es obligatorio."
            ],
            "email": [
              "El campo correo electrónico es obligatorio."
            ],
            "codigo_postal": [
              "El campo código postal es obligatorio."
            ],
            "fecha_nacimiento": [
              "El campo fecha nacimiento es obligatorio."
            ],
            "terminos": [
              "El campo terminos es obligatorio."
            ],
            "aviso": [
              "El campo aviso es obligatorio."
            ]
        }

  * **Code:** 423 Locked <br />
    **Content:** 
    
        "error": "Teléfono ya registrado",
          "user": {
            "id": 10547,
            "name": "Abril",
            "last_name": "Abril",
            "second_last_name": null,
            "telephone": "527772273622",
            "clave": "ABAB9RIW",
            "email": "abril@cs.com",
            "player_id": null,
            "tipo_usuario": null,
            "activo": 1,
            "baja": 0,
            "fb_id": null,
            "webhook_url": null,
            "created_at": "2018-12-17 17:58:21",
            "updated_at": "2018-12-18 10:49:09",
            "deleted_at": null,
            "last_login": null
          }
    
 
**Datos del cliente**
----

  Regresa la información del cliente y sus relaciones ejemplo perfil, direcciones, planes de lealtad y pedidos

 **URL**

    /api-v2/clientes/me

 **Method:**

  `GET`
  
  **URL Params**

  - includes[]=clientePerfil.sucursal, clienteDirecciones, ultimaDireccion, clientePedidos, clientePlanes, clienteComunicacion, facturacion, tarjetas  <br><br>
  Ejemplo URI: `api/clientes/me?includes[]=clientePerfil&includes[]=clienteDirecciones`
  

 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
          "cliente": {
              "id": 23516,
              "name": "Abril",
              "last_name": "Prueba",
              "second_last_name": "V2",
              "telephone": "527772273622",
              "clave": "ABPRELSY",
              "email": "jabrilmtz17@gmail.com",
              "player_id": null,
              "tipo_usuario": null,
              "activo": 1,
              "baja": 0,
              "fb_id": null,
              "webhook_url": null,
              "created_at": "2020-04-20 22:22:55",
              "updated_at": "2020-04-21 00:07:26",
              "deleted_at": null,
              "last_login": null,
              "cliente_perfil": {
                "id": 23097,
                "user_id": 23516,
                "active": 1,
                "deleted_at": null,
                "created_at": "2020-04-20 22:22:55",
                "updated_at": "2020-04-20 22:22:55",
                "sexo": null,
                "fecha_nacimiento": "1995-08-17",
                "edad": null,
                "imagen": null,
                "imagen_path": null,
                "zona_id": null,
                "especial": 0,
                "lat": null,
                "lon": null,
                "categoria_id": null,
                "codigo_postal": null
              }
          }
        }


**Actualización del cliente**
----
  Actualiza la información del cliente y su info de perfil

 **URL**

    /api-v2/clientes/me

 **Method:**

  `POST`
    
 **Headers**
 
    Authorization: Bearer access_token
    Accept: application/json
    Content-Type: multipart/form-data
    
 **Data Params**
 
    'name' => '',
    'last_name' => '',
    'second_last_name' => '',
    'telephone' => 'unique:users,telephone,'.$user->id,
    'email' => 'email',
    'estado_id' => '',
    'ciudad_id' => '',
    'colonia_id' => '',
    'direccion' => '',
    'sexo' => 'in:masculino,femenino',
    'fecha_nacimiento' => '',
    'edad' => '',
    'password' => 'min:4',
    'player_id' => '',
    'imagen' => '',
    'imagen_path' => '',
    'plataforma' => 'in:ios,android'

 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
          "cliente": {
              "id": 23516,
              "name": "Abril",
              "last_name": "Prueba",
              "second_last_name": "V2",
              "telephone": "527772273622",
              "clave": "ABPRELSY",
              "email": "jabrilmtz17@gmail.com",
              "player_id": null,
              "tipo_usuario": null,
              "activo": 1,
              "baja": 0,
              "fb_id": null,
              "webhook_url": null,
              "created_at": "2020-04-20 22:22:55",
              "updated_at": "2020-04-21 00:07:26",
              "deleted_at": null,
              "last_login": null,
              "cliente_perfil": {
                "id": 23097,
                "user_id": 23516,
                "active": 1,
                "deleted_at": null,
                "created_at": "2020-04-20 22:22:55",
                "updated_at": "2020-04-20 22:22:55",
                "sexo": null,
                "fecha_nacimiento": "1995-08-17",
                "edad": null,
                "imagen": null,
                "imagen_path": null,
                "zona_id": null,
                "especial": 0,
                "lat": null,
                "lon": null,
                "categoria_id": null,
                "codigo_postal": null
              },
              "plataforma": null
          }
        }


 **Error Response:**

  * **Code:** 401 Unauthorized <br />
    **Content:** 
    
        {
          "error": "Unauthenticated."
        }



**Actualiza el código de verificación del cliente**
----
  Actualiza el código de verificación del cliente 

 **URL**

    /api-v2/clientes/codigo-verificacion

 **Method:**

  `POST`
    
 **Headers**
 
    Accept: application/json
    
 **Body**
 
    telephone => required|exists:users,telephone
    
 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
        	"cliente": {
                "id": 23516,
                "name": "Abril",
                "last_name": "Prueba",
                "second_last_name": "V2",
                "telephone": "527772273622",
                "clave": "ABPRELSY",
                "email": "jabrilmtz17@gmail.com",
                "player_id": null,
                "tipo_usuario": null,
                "activo": 1,
                "baja": 0,
                "fb_id": null,
                "webhook_url": null,
                "created_at": "2020-04-20 22:22:55",
                "updated_at": "2020-04-21 00:07:26",
                "deleted_at": null,
                "last_login": null,
                "plain_code": 9972
            }
        }

        
* **Code:** 422 Unproccesable Entity <br />
    **Content:** 
    
        {
            "telephone": [
                "El campo teléfono es inválido."
            ]
        }
        
* **Code:** 404 Not Found <br />
    **Content:** 
    
        {
            "message": "No existe un cliente con ese número de teléfono."
        }
       
       
**Actualiza sucursal del cliente**
----
  Actualiza el código de verificación del cliente 

 **URL**

    /api-v2/clientes/sucursal

 **Method:**

  `POST`
    
 **Headers**
 
    Accept: application/json
    
 **Body**
 
    'sucursal_id' => 'required|exists:sucursales,id'
    
 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
        	"cliente": {
                "id": 23516,
                "name": "Abril",
                "last_name": "Prueba",
                "second_last_name": "V2",
                "telephone": "527772273622",
                "clave": "ABPRELSY",
                "email": "jabrilmtz17@gmail.com",
                "player_id": null,
                "tipo_usuario": null,
                "activo": 1,
                "baja": 0,
                "fb_id": null,
                "webhook_url": null,
                "created_at": "2020-04-20 22:22:55",
                "updated_at": "2020-04-21 00:07:26",
                "deleted_at": null,
                "last_login": null,
                "cliente_perfil": {
                  "id": 23097,
                  "user_id": 23516,
                  "active": 1,
                  "deleted_at": null,
                  "created_at": "2020-04-20 22:22:55",
                  "updated_at": "2020-04-21 00:53:13",
                  "sexo": null,
                  "fecha_nacimiento": "1995-08-17",
                  "edad": null,
                  "imagen": null,
                  "imagen_path": null,
                  "zona_id": null,
                  "especial": 0,
                  "lat": null,
                  "lon": null,
                  "categoria_id": null,
                  "codigo_postal": null,
                  "sucursal_id": 13,
                  "sucursal": {
                    "id": 13,
                    "user_id": 64,
                    "codigo": "13",
                    "nombre": "P",
                    "telefono": "7772575921",
                    "colonia_id": 35045,
                    "municipio_id": 2345,
                    "estado_id": 17,
                    "zona_sucursal_id": 10,
                    "ciudad_cobertura_id": null,
                    "direccion": "EMPERADOR",
                    "direccion_numero": "3-B",
                    "codigo_postal": "62738",
                    "lon": "-98.970514",
                    "lat": "18.906802",
                    "ancla": 1,
                    "checkin": 0,
                    "dias": "LUN, MAR, MIE, JUE, VIE, SAB, DOM",
                    "horario_inicio": "07:00:00",
                    "horario_final": "22:00:00",
                    "24_hrs": 0,
                    "base": 0,
                    "almacen": 0,
                    "created_at": "2017-03-16 17:50:05",
                    "updated_at": "2019-10-18 17:16:10",
                    "deleted_at": null
                  }
                }
            }
        }

        
* **Code:** 422 Unproccesable Entity <br />
    **Content:** 
    
        {
            "sucursal_id": [
               "El campo sucursal id es obligatorio."
            ]
        }


**Cancela cuenta de usuario**
----
Cancela acceso a usuario

**URL**

    /api-v2/clientes/cancelAccount

**Method:**

`DELETE`

**Headers**

    Accept: application/json,
    Authorization: Bearer access_token


**Body**

    N/A

**Success Response:**

* **Code:** 200 <br />
  **Content:**

      { 
         "message": "La cuenta ha sido eliminada correctamente. A partir de este momento tendrás 30 días para recuperarla. si no se recupera, toda la infromación será eliminada"
      }


**Recupera cuenta de usuario**
----
Recupera acceso a usuario

**URL**

    /api-v2/clientes/restoreAccount

**Method:**

`POST`

**Headers**

    Accept: application/json,
    Content-Type: multipart/form-data


**Body**

    'telphone' => 'required'

**Success Response:**

* **Code:** 200 <br />
  **Content:**

      {
        "message": "La cuenta ha sido recuperada"
      }


* **Code:** 401 Unauthenticated <br />
  **Content:**

        {
          "error": "Unauthenticated."
        }
       