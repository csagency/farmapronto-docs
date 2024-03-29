      
**Acceso**
----

Metodo de autentificación y acceso con oAuth 2.0
Cada usuario debera solicitar su access token para realizar solicitudes a la API

## Requesting Tokens [POST /oauth/token]

+ Request (application/json)
    + Body
        + FormParams
    
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

**Requesting Tokens [DELETE /api/logout]**

+ Response 200 (application/json) Ejemplo:
    + Body

            {
            	"token_deleted": "Token de acceso ha expirado"
            }



**FB verificación**
----

Verifica que tenga un FB_ID valido registrado

**Headers**

    Accept: application/json

**Requesting Tokens [POST /api/auth/facebook]**


* application/x-www-form-urlencoded


           fb_id: required


+ Response 200 (application/json) Ejemplo:
    + Body

            {
            	"user": {
            		"id": 5898,
            		"name": "Erick",
            		"last_name": "Brito",
            		"second_last_name": null,
            		"telephone": "527773274199",
            		"email": "erick@cs.com",
            		"player_id": null,
            		"activo": 1,
            		"fb_id": "733337",
            		"slack_webhook_url": null,
            		"created_at": "2018-09-24 17:00:46",
            		"updated_at": "2018-09-24 17:00:46",
            		"deleted_at": null,
            		"last_login": null
            	}
            }


+ Response 422 (application/json) Ejemplo:
    + Body

            {
                "fb_id": [
                    "El campo fb id es inválido."
                ]
            }


       
**Registro de cliente**
----
  Regresa la información del registro en formato json

 **URL**

  /api/clientes/registro/

 **Method:**

  `POST`
  
  **URL Params**

  None
 
 **Data Params**

 ***Required:***
    
     name=[required]
     last_name=[required]
     second_last_name=[required]
     telephone=[required|unique]
     email=[required]
     password=[required]
     estado_id=[optional]
     ciudad_id=[optional]
     colonia_id=[optional]
     direccion=[optional]
     referencia=[optional]
     sexo=[optional|in:femenino,masculino]
     fecha_nacimiento=[optional]
     edad=[optional]
     imagen=[optional]
     imagen_path=[optional]
     player_id = [optional]
     reset => [boolean]
     'fb_id' => 'nullable',
     'clave_invitado' => 'nullable|exists:users,clave,deleted_at,NULL'



 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 


            {
                "cliente": {
                    "name": "Erick",
                    "last_name": "Brito",
                    "telephone": "527773274199",
                    "email": "erick@cs.com",
                    "fb_id": "733337",
                    "clave": "ERBRUFUM",
                    "updated_at": "2018-10-19 21:52:18",
                    "created_at": "2018-10-19 21:52:18",
                    "id": 6887,
                    "cliente_direcciones": [],
                    "cliente_perfil": {
                        "id": 6714,
                        "user_id": 6887,
                        "active": 1,
                        "deleted_at": null,
                        "created_at": "2018-10-19 21:52:18",
                        "updated_at": "2018-10-19 21:52:18",
                        "sexo": null,
                        "fecha_nacimiento": null,
                        "edad": null,
                        "imagen": null,
                        "imagen_path": null,
                        "zona_id": null
                    },
                    "invito_usuario": [
                        {
                            "id": 5381,
                            "name": "Rocío",
                            "last_name": "Parada",
                            "second_last_name": null,
                            "telephone": null,
                            "clave": "PAMR8810",
                            "email": null,
                            "player_id": null,
                            "activo": 0,
                            "fb_id": null,
                            "slack_webhook_url": null,
                            "created_at": "2018-09-04 13:18:25",
                            "updated_at": "2018-09-10 13:06:51",
                            "deleted_at": null,
                            "last_login": null,
                            "pivot": {
                                "invitado_id": 6887,
                                "user_id": 5381,
                                "created_at": "2018-10-19 21:52:18",
                                "updated_at": "2018-10-19 21:52:18"
                            }
                        }
                    ],
                    "user_role": {
                        "id": 2653,
                        "user_id": 6887,
                        "rol_id": 1,
                        "created_at": "2018-10-19 21:52:18",
                        "updated_at": "2018-10-19 21:52:18"
                    },
                    "cliente": {
                        "id": 6714,
                        "user_id": 6887,
                        "active": 1,
                        "deleted_at": null,
                        "created_at": "2018-10-19 21:52:18",
                        "updated_at": "2018-10-19 21:52:18",
                        "sexo": null,
                        "fecha_nacimiento": null,
                        "edad": null,
                        "imagen": null,
                        "imagen_path": null,
                        "zona_id": null
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
          "second_last_name": [
            "El campo segundo apellido es obligatorio."
          ],
          "telephone": [
            "El campo teléfono es obligatorio."
          ]
        }

 
**Datos del cliente**
----

  Regresa la información del cliente y sus relaciones ejemplo perfil, direcciones, planes de lealtad y pedidos

 **URL**

  /api/clientes/me

 **Method:**

  `GET`
  
  **URL Params**

  - includes[]=userCliente, userDirecciones, userPedidos, userPlanes  <br><br>
  Ejemplo URI: `api/clientes/me?includes[]=clientePerfil&includes[]=clienteDirecciones`
  

 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
          "cliente": {
            "id": 6,
            "name": "Erick",
            "last_name": "Brito",
            "second_last_name": "Arr",
            "telephone": "527773274199",
            "email": null,
            "created_at": "2017-05-09 12:43:09",
            "updated_at": "2017-05-09 12:43:09",
            "deleted_at": null,
            "cliente_perfil": {
              "id": 1,
              "user_id": 6,
              "active": 1,
              "deleted_at": null,
              "created_at": "2017-05-09 12:43:09",
              "updated_at": "2017-05-09 12:43:09",
              "sexo": null,
              "fecha_nacimiento": null,
              "edad": null,
              "imagen": null,
              "imagen_path": null
            },
            "cliente_direcciones": []
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
          "second_last_name": [
            "El campo segundo apellido es obligatorio."
          ],
          "telephone": [
            "El campo teléfono es obligatorio."
          ]
        }



**Actualización del cliente**
----

  Actualiza la información del cliente y su info de perfil

 **URL**

  /api/clientes/me

 **Method:**

  `POST`
    
 **Headers**
 
    Authorization: Bearer access_token
    Accept: application/json
    Content-Type: multipart/form-data
    
 **Multipart**
 
    sexo:masculino|femenino
    fecha_nacimiento:date
    imagen:file image
    name:
    last_name:
    second_last_name:
    telephone:unique
    email:
    player_id:
    'plataforma' => 'in:ios,android'

 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
          "cliente": {
            "id": 7,
            "name": "Erick ",
            "last_name": "Brito",
            "second_last_name": "Arroyo",
            "telephone": "527773274199",
            "email": "test2@csgroup.mx",
            "player_id": "null",
            "created_at": "2017-05-08 19:25:41",
            "updated_at": "2017-05-08 19:25:41",
            "deleted_at": null,
            "cliente_perfil": {
              "id": 8,
              "user_id": 7,
              "active": 1,
              "deleted_at": null,
              "created_at": "2017-05-08 19:25:41",
              "updated_at": "2017-05-10 14:01:53",
              "sexo": "masculino",
              "fecha_nacimiento": null,
              "edad": null,
              "imagen": null,
              "imagen_path": null,
              "zona_id": 22,
            }
          },
          "plataforma": {
          			"id": 9,
          			"user_id": 1934,
          			"plataforma_id": 2,
          			"tipo": "ios",
          			"created_at": "2018-09-19 19:05:55",
          			"updated_at": "2018-09-19 19:06:05",
          			"plataforma": {
          				"id": 2,
          				"nombre": "app",
          				"created_at": "2018-09-19 18:59:41",
          				"updated_at": "2018-09-19 18:59:41"
          			}
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

  /api/clientes/codigo-verificacion

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
        		"id": 9,
        		"name": "Erick",
        		"last_name": "Brito",
        		"second_last_name": "ddd",
        		"telephone": "527772374199",
        		"email": null,
        		"created_at": "2017-05-15 15:29:58",
        		"updated_at": "2017-05-16 14:25:53",
        		"deleted_at": null,
        		"plain_password": "174l7D"
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


**Cambia la contraseña con el código de verificación del cliente**
----
  Actualiza la contraseña del cliente 

 **URL**

  /api/clientes/password/update

 **Method:**

  `POST`
    
 **Headers**
 
    Accept: application/json
    
 **Body**
 
    'telephone' => 'required|exists:users,telephone'
    'codigo' => 'required',
    'password' => 'required|min:4|confirmed'
    'password_confirmation' => 'required|min:4'
    
 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
          "cliente": {
            "id": 7890,
            "name": "Prueba",
            "last_name": "Test",
            "second_last_name": null,
            "telephone": "527773754507",
            "clave": "ISACZN5D",
            "email": "isra@cs.com",
            "player_id": "a5f4a66a-5819-4076-8fc1-42b85151922b",
            "activo": 1,
            "fb_id": null,
            "slack_webhook_url": null,
            "created_at": "2018-10-12 10:22:19",
            "updated_at": "2018-11-20 18:44:35",
            "deleted_at": null,
            "last_login": null
          },
          "message": "Contraseña actualizada."
        }

        
* **Code:** 422 Unproccesable Entity <br />
    **Content:** 
    
        {
          "telephone": [
            "El campo teléfono es obligatorio."
          ],
          "codigo": [
            "El campo código es obligatorio."
          ],
          "password": [
            "El campo contraseña es obligatorio."
          ]
        }
        
* **Code:** 400 Bad Request <br />
    **Content:** 
    
        {
           "message": "Código de verificación incorrecto"
        }
        
* **Code:** 404 Not Found <br />
    **Content:** 
    
        {
            "message": "No existe un cliente con ese número de teléfono."
        }

**Activar cliente**
----
  Activa la cuenta de usuario cliente

 **URL**

  /api/clientes/me/activar

 **Method:**

  `PUT`
    
 **Headers**
 
    Authorization: Bearer access_token
    Accept: application/json
    Content-Type: application/x-www-form-urlencoded
    
 **application/x-www-form-urlencoded**
 
    verificacion: 1234
    
 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
        	"cliente": {
        		"id": 4,
        		"name": "Cliente",
        		"last_name": "CS",
        		"second_last_name": "Group",
        		"telephone": "527773274199",
        		"email": "erick.dbrito@gmail.com",
        		"player_id": "f13276df-b3c2-42e0-b66a-a6b22445035b",
        		"active": 1,
        		"created_at": "2017-03-16 17:47:54",
        		"updated_at": "2017-07-18 16:42:03",
        		"deleted_at": null
        	},
        	"message": "Cuenta verificada"
        }

 **Error Response:**

  * **Code:** 401 Unauthorized <br />
    **Content:** 
    
        {
          "error": "Unauthenticated."
        }
        
  * **Code:** 422 Unproccesable <br />

        {
            "verificacion": [
                "El campo verificacion es obligatorio."
            ]
        }
        
         
**Listado de recetas del cliente**
----

  Recetas del cliente
   **URL**
  
    /api/clientes/recetas
  
   **Method:**
  
    `GET`
      
   **Headers**
    
       Authorization: Bearer access_token
       Accept: application/json
      
 **Success Response:**
  
   * **Code:** 200 <br />
      **Content:** 
      
          {
          	"recetas": [
          		{
          			"id": 20,
          			"pedido_id": null,
          			"producto_id": 1,
          			"user_id": 131,
          			"tipo": "receta",
          			"archivo": "http:\/\/farmapronto.dev\/uploads\/recetas\/E1CcjpZzkfQOk9f27JTzhAbnppE2ckr0CTzrZH1I.png",
          			"created_at": "2017-07-20 13:03:38",
          			"updated_at": "2017-07-20 13:03:38",
          			"fisico": 0,
          			"estatus": "pendiente",
          			"producto": {
          				"id": 1,
          				"farmapronto_id": "000001",
          				"sku": "736085400892",
          				"nombre": "3-A OFTENO 1MG GTS 5ML",
          				"descripcion": "3-A OFTENO 1MG GTS 5ML",
          				"categoria": "ORGANOS DE LOS SENTIDOS",
          				"categoria_id": 0,
          				"laboratorio": "Bayer",
          				"receta": 0,
          				"clave": "Disponible",
          				"tipo": 38,
          				"activos": "DICLOFENACO SODICO",
          				"destacado": 0,
          				"archivo": null,
          				"created_at": "2017-03-16 17:49:19",
          				"updated_at": "2017-07-14 13:02:30",
          				"activo": 1
          			}
          		}
          	]
          }
              
  
   * **Code:** 401 Unauthorized <br />
      **Content:** 
      
          {
            "error": "Unauthenticated."
          }
          
     
      
**Mostrar receta por id**
----

  Recetas por id
   **URL**
  
    /api/clientes/recetas/{IDReceta}?includes[]=producto
  
   **Method:**
  
    `GET`
      
   **Headers**
    
       Authorization: Bearer access_token
       Accept: application/json
      
 **Success Response:**
  
   * **Code:** 200 <br />
      **Content:** 
      
          {
          	"receta": {
          		"id": 20,
          		"pedido_id": null,
          		"producto_id": 1,
          		"user_id": 131,
          		"tipo": "receta",
          		"archivo": "http:\/\/farmapronto.dev\/uploads\/recetas\/E1CcjpZzkfQOk9f27JTzhAbnppE2ckr0CTzrZH1I.png",
          		"created_at": "2017-07-20 13:03:38",
          		"updated_at": "2017-07-20 13:03:38",
          		"fisico": 0,
          		"estatus": "pendiente",
          		"producto": {
          			"id": 1,
          			"farmapronto_id": "000001",
          			"sku": "736085400892",
          			"nombre": "3-A OFTENO 1MG GTS 5ML",
          			"descripcion": "3-A OFTENO 1MG GTS 5ML",
          			"categoria": "ORGANOS DE LOS SENTIDOS",
          			"categoria_id": 0,
          			"laboratorio": "Bayer",
          			"receta": 0,
          			"clave": "Disponible",
          			"tipo": 38,
          			"activos": "DICLOFENACO SODICO",
          			"destacado": 0,
          			"archivo": null,
          			"created_at": "2017-03-16 17:49:19",
          			"updated_at": "2017-07-14 13:02:30",
          			"activo": 1
          		}
          	}
          }
              
  
   * **Code:** 401 Unauthorized <br />
      **Content:** 
      
          {
            "error": "Unauthenticated."
          }
         
        
        
     
**Listado de recetas del cliente por pedido **
----

  Recetas del cliente
   **URL**
  
    api/clientes/recetas/pedido/{IDPedido}?includes[]=producto&includes[]=pedido
    
   **Method:**
  
    `GET`
      
   **Headers**
    
       Authorization: Bearer access_token
       Accept: application/json
      
 **Success Response:**
  
   * **Code:** 200 <br />
      **Content:** 
      
          {
          	"recetas": [
          		{
          			"id": 18,
          			"pedido_id": 129,
          			"producto_id": 1,
          			"user_id": 131,
          			"tipo": "receta",
          			"archivo": "http:\/\/farmapronto.dev\/uploads\/recetas\/MghJblytAUo6XGlPZi7unlHLAhq7rmiL7mfDVQ4f.png",
          			"created_at": "2017-07-14 13:27:48",
          			"updated_at": "2017-07-14 13:27:48",
          			"fisico": 0,
          			"estatus": "pendiente",
          			"producto": {
          				"id": 1,
          				"farmapronto_id": "000001",
          				"sku": "736085400892",
          				"nombre": "3-A OFTENO 1MG GTS 5ML",
          				"descripcion": "3-A OFTENO 1MG GTS 5ML",
          				"categoria": "ORGANOS DE LOS SENTIDOS",
          				"categoria_id": 0,
          				"laboratorio": "Bayer",
          				"receta": 0,
          				"clave": "Disponible",
          				"tipo": 38,
          				"activos": "DICLOFENACO SODICO",
          				"destacado": 0,
          				"archivo": null,
          				"created_at": "2017-03-16 17:49:19",
          				"updated_at": "2017-07-14 13:02:30",
          				"activo": 1
          			},
          			"pedido": {
          				"id": 129,
          				"user_id": 4,
          				"cliente_direccion_id": 248,
          				"created_at": "2017-07-14 13:27:48",
          				"updated_at": "2017-07-14 13:27:48"
          			}
          		}
          	]
          }
              
  
   * **Code:** 401 Unauthorized <br />
      **Content:** 
      
          {
            "error": "Unauthenticated."
          }
          
**Agregar imagen de receta por producto **
----

  Agregar imagenes de receta por producto
  
   **URL**
  
    /api/clientes/recetas
  
   **Method:**
  
    `POST`
      
   **Headers**
    
       Authorization: Bearer access_token
       Accept: application/json
       Content-Type: multipart/form-data
      
      
**Data Params**

 ***Required:***
    
    'producto_id' => 'required|exists:productos,id',
    'archivo' => 'required|image,
    
      
 **Success Response:**
  
   * **Code:** 200 <br />
      **Content:** 
      
          {
          	"user": {
          		"id": 131,
          		"name": "Erick 2",
          		"last_name": "OOOO",
          		"second_last_name": "A",
          		"telephone": "527773274199",
          		"email": "erick.dbrito@gmail.com",
          		"player_id": "123123123",
          		"activo": 1,
          		"created_at": "2017-07-18 17:59:03",
          		"updated_at": "2017-07-19 18:54:23",
          		"deleted_at": null
          	},
          	"receta": {
          		"producto_id": "1",
          		"tipo": "receta",
          		"archivo": "http:\/\/farmapronto.dev\/uploads\/recetas\/DXPIaQjEpfvgy0Xr3K0E7u7GBiaZTEYQoUVujqus.png",
          		"fisico": false,
          		"estatus": "pendiente",
          		"user_id": 131,
          		"updated_at": "2017-07-20 13:04:55",
          		"created_at": "2017-07-20 13:04:55",
          		"id": 21,
          		"producto": {
          			"id": 1,
          			"farmapronto_id": "000001",
          			"sku": "736085400892",
          			"nombre": "3-A OFTENO 1MG GTS 5ML",
          			"descripcion": "3-A OFTENO 1MG GTS 5ML",
          			"categoria": "ORGANOS DE LOS SENTIDOS",
          			"categoria_id": 0,
          			"laboratorio": "Bayer",
          			"receta": 0,
          			"clave": "Disponible",
          			"tipo": 38,
          			"activos": "DICLOFENACO SODICO",
          			"destacado": 0,
          			"archivo": null,
          			"created_at": "2017-03-16 17:49:19",
          			"updated_at": "2017-07-14 13:02:30",
          			"activo": 1
          		}
          	}
          }
  
   **Error Responses:**
    * **Code:** 422 Unprocessable Entity <br />
       **Content:** 
       
          {
          	"producto_id": [
          		"El campo producto id es obligatorio."
          	],
          	"archivo": [
          		"El campo archivo es obligatorio."
          	]
          }
              
  
   * **Code:** 401 Unauthorized <br />
      **Content:** 
      
          {
            "error": "Unauthenticated."
          }
        
         
**Listado de tarjetas**
----

   Listado de tarjetas del cliente
   
   **URL**
  
    /api/clientes/tarjetas
  
   **Method:**
  
    `GET`
      
   **Headers**
    
       Authorization: Bearer access_token
       Accept: application/json
      
 **Success Response:**
  
   * **Code:** 200 <br />
      **Content:** 
      
          {
          	"tarjetas": [
          		{
          			"id": 22,
          			"pedido_pago_id": null,
          			"user_id": 134,
          			"last4": "2344",
          			"tarjeta": "credito",
          			"tipo": "mc",
          			"created_at": "2017-07-25 17:24:50",
          			"updated_at": "2017-07-25 17:24:50"
          		}
          	]
          }
              
  
   * **Code:** 401 Unauthorized <br />
      **Content:** 
      
          {
            "error": "Unauthenticated."
          }
          
     
      
**Mostrar tarjeta por id  **
----

  Tarjeta por id
   
   **URL**
  
    /api/clientes/tarjetas/{IDReceta}
  
   **Method:**
  
    `GET`
      
   **Headers**
    
       Authorization: Bearer access_token
       Accept: application/json
      
 **Success Response:**
  
   * **Code:** 200 <br />
      **Content:** 
      
         {
         	"tarjeta": {
         		"id": 22,
         		"user_id": 134,
         		"last4": "2344",
         		"tarjeta": "credito",
         		"tipo": "mc",
         		"created_at": "2017-07-25 17:24:50",
         		"updated_at": "2017-07-25 17:24:50"
         	}
         }
              
  
   * **Code:** 401 Unauthorized <br />
      **Content:** 
      
          {
            "error": "Unauthenticated."
          }
         
        
        
  
**Agregar tarjeta **
----

  Agregar tarjeta al usuario
  
   **URL**
  
    /api/clientes/tarjetas
  
   **Method:**
  
    `POST`
      
   **Headers**
    
       Authorization: Bearer access_token
       Accept: application/json
       Content-Type: multipart/form-data
      
      
**Data Params**

 ***Required:***
    
        'tarjeta' => 'required|in:credito,debito',
        'last4' => 'required|numeric|max:9999',
        'tipo' => 'required|in:visa,mc,amex',
    
      
 **Success Response:**
  
   * **Code:** 200 <br />
      **Content:** 
      
          {
          	"user": {
          		"id": 134,
          		"name": "Erick",
          		"last_name": "Daniel",
          		"second_last_name": "Brito",
          		"telephone": "7773274199",
          		"email": "erick.dbrito@gmail.com",
          		"player_id": null,
          		"activo": 1,
          		"created_at": "2017-07-18 10:43:09",
          		"updated_at": "2017-07-21 16:35:41",
          		"deleted_at": null
          	},
          	"tarjeta": {
          		"user_id": 134,
          		"tarjeta": "credito",
          		"last4": "2344",
          		"tipo": "mc",
          		"updated_at": "2017-07-25 17:32:46",
          		"created_at": "2017-07-25 17:32:46",
          		"id": 23
          	}
          }
  
   **Error Responses:**
    * **Code:** 422 Unprocessable Entity <br />
       **Content:** 
       
          {
          	"tarjeta": [
          		"El campo tarjeta es obligatorio."
          	],
          	"last4": [
          		"El campo last4 es obligatorio."
          	],
          	"tipo": [
          		"El campo tipo es obligatorio."
          	]
          }
              
  
   * **Code:** 401 Unauthorized <br />
      **Content:** 
      
          {
            "error": "Unauthenticated."
          }
        
        

**Actualizar tarjeta **
----

  Actualiza tarjeta
  
   **URL**
  
    /api/clientes/tarjetas/{IDTarjeta}
  
   **Method:**
  
    `PUT`
      
   **Headers**
    
       Authorization: Bearer access_token
       Accept: application/json
       Content-Type: multipart/form-data
      
      
**Data Params**

 ***Required:***
    
        'tarjeta' => 'in:credito,debito',
        'last4' => 'numeric|max:9999',
        'tipo' => 'in:visa,mc,amex',
    
      
 **Success Response:**
  
   * **Code:** 200 <br />
      **Content:** 
      
          {
          	"user": {
          		"id": 134,
          		"name": "Erick",
          		"last_name": "Daniel",
          		"second_last_name": "Brito",
          		"telephone": "7773274199",
          		"email": "erick.dbrito@gmail.com",
          		"player_id": null,
          		"activo": 1,
          		"created_at": "2017-07-18 10:43:09",
          		"updated_at": "2017-07-21 16:35:41",
          		"deleted_at": null
          	},
          	"tarjeta": {
          		"id": 22,
          		"user_id": 134,
          		"last4": "2345",
          		"tarjeta": "credito",
          		"tipo": "amex",
          		"created_at": "2017-07-25 17:24:50",
          		"updated_at": "2017-07-25 17:33:52"
          	}
          }
  

  
   * **Code:** 401 Unauthorized <br />
      **Content:** 
      
          {
            "error": "Unauthenticated."
          }
        
      

**Eliminar tarjeta **
----

  Eliminar tarjeta del usuario
  
   **URL**
  
    /api/clientes/tarjetas/{IDTarjeta}
  
   **Method:**
  
    `DELETE`
      
   **Headers**
    
       Authorization: Bearer access_token
       Accept: application/json
       Content-Type: multipart/form-data
      
      
      
 **Success Response:**
  
   Respuesta Tarjeta : 1  = Eliminado
   Respuesta Tarjeta : 0  = No encontrado
   
  
   * **Code:** 200 <br />
      **Content:** 
      
         {
         	"user": {
         		"id": 134,
         		"name": "Erick",
         		"last_name": "Daniel",
         		"second_last_name": "Brito",
         		"telephone": "7773274199",
         		"email": "erick.dbrito@gmail.com",
         		"player_id": null,
         		"activo": 1,
         		"created_at": "2017-07-18 10:43:09",
         		"updated_at": "2017-07-21 16:35:41",
         		"deleted_at": null
         	},
         	"tarjeta": 1
         }
  

  
   * **Code:** 401 Unauthorized <br />
      **Content:** 
      
          {
            "error": "Unauthenticated."
          }
        
        

**Solicita asistencia a callcenter **
----
    Solicita asistencia a callcenter
  
   **URL**
  
    /api/clientes/callcenter
  
   **Method:**
  
    `POST`
      
   **Headers**
    
       Authorization: Bearer access_token
       Accept: application/json
       Content-Type: application/x-www-form-urlencoded
      
      
**Data Params**

 ***Required:***
    
    'asistencia' => 'required|boolean',
    
     
 **Success Response:**
  
   * **Code:** 200 <br />
      **Content:** 
      
          {
          	"user": {
          		"id": 134,
          		"name": "Erick",
          		"last_name": "Daniel",
          		"second_last_name": "Brito",
          		"telephone": "7773274199",
          		"email": "erick.dbrito@gmail.com",
          		"player_id": null,
          		"activo": 1,
          		"created_at": "2017-07-18 10:43:09",
          		"updated_at": "2017-07-21 16:35:41",
          		"deleted_at": null,
          		"asistencias": [
          			{
          				"user_id": 134,
          				"atendido_at": null,
          				"created_at": "2017-07-26 13:27:44",
          				"updated_at": "2017-07-26 13:27:44"
          			}
          		]
          	}
          }
  
   **Error Responses:**
    * **Code:** 422 Unprocessable Entity <br />
       **Content:** 
       
          {
          	"asistencia": [
          		"El campo asistencia es obligatorio."
          	]
          }
              
  
   * **Code:** 401 Unauthorized <br />
      **Content:** 
      
          {
            "error": "Unauthenticated."
          }
          
   
   

**Solicita recuperar password **
----
  
   **URL**
  
    /api/clientes/password/reset
  
   **Method:**
  
    `POST`
      
   **Headers**
    
       Accept: application/json
       Content-Type: application/x-www-form-urlencoded
      
      
**Data Params**

 ***Required:***
    
    'telephone' => 'required',
    
     
  
   * **Code:** 404 Not found <br />
      **Content:** 
      
          {
            "error": "Registro no encontrado."
          }
          
   