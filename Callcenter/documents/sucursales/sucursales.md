      
**Acceso**
----

Metodo de autentificación y acceso con oAuth 2.0 <br>
Cada usuario debera solicitar su access token para realizar solicitudes a la API

 **URL**

   `/api/login/custom`

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

**Requesting Tokens [DELETE /api/logout]**

+ Response 200 (application/json) Ejemplo:
    + Body

            {
            	"token_deleted": "Token de acceso ha expirado"
            }
      
       
**Registro de usuario tipo sucursal**
----
  Regresa la información del registro en formato json

 **URL**

  /api/sucursales/registro/

 **Method:**

  `POST`
  
  **URL Params**

  None
 
 **Data Params**

 ***Required:***
    
        'name' => 'required',
        'last_name' => 'required',
        'second_last_name' => 'required',
        'telephone' => 'required',
        'email' => 'required|email|unique:users',
        'password' => 'min:6|required',
        'player_id' => '',
        'sucursal_id' => 'exists:sucursales,id'


 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
        	"user": {
        		"name": "234",
        		"last_name": "123",
        		"second_last_name": "123",
        		"telephone": "s2",
        		"email": "testsucursal2@cs.com",
        		"updated_at": "2017-07-11 19:22:48",
        		"created_at": "2017-07-11 19:22:48",
        		"id": 132,
        		"sucursales": [
        			{
        				"id": 1,
        				"user_id": 52,
        				"codigo": "1",
        				"nombre": "AA",
        				"telefono": null,
        				"colonia_id": 34733,
        				"municipio_id": 502,
        				"estado_id": 17,
        				"direccion": "AV. VICENTE GUERRERO",
        				"direccion_numero": "107",
        				"codigo_postal": "62230",
        				"lon": null,
        				"lat": null,
        				"created_at": "2017-03-16 17:50:05",
        				"updated_at": "2017-07-05 13:44:59",
        				"pivot": {
        					"user_id": 132,
        					"sucursal_id": 1
        				}
        			}
        		]
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
            ],
            "email": [
              "El campo correo electrónico es obligatorio."
            ],
            "password": [
              "El campo contraseña es obligatorio."
            ]
        }

 
**Obtener información de un usuario tipo sucursal**
----
  Regresa la información del usuario de tipo sucursal y sus relaciones

 **URL**

  /api/sucursales/{ID}

 **Method:**

  `GET`
  
  **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data
      
   **URL Params**
  
    - includes[]=sucursales, roles  <br><br>
    Ejemplo URI: `api/sucursales/12?includes[]=roles`
    

 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
            "sucursal": {
              "id": 12,
              "name": "Encargado",
              "last_name": "Sucursal",
              "second_last_name": "API",
              "telephone": "7771234567",
              "email": "apisucursaltest2@grupofarmapronto.com",
              "created_at": "2017-06-06 16:33:29",
              "updated_at": "2017-06-06 16:49:13",
              "deleted_at": null,
              "roles": [
                {
                  "id": 3,
                  "name": "sucursal",
                  "guard_name": "web",
                  "created_at": "2019-10-28 17:22:59",
                  "updated_at": "2019-10-28 17:22:59",
                  "pivot": {
                    "model_id": 133,
                    "role_id": 3
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




**Actualización del usuario sucursal**
----
  Actualiza la información del usuario sucursal

 **URL**

  /api/sucursales/me

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
        	"sucursal": {
        		"id": 53,
        		"name": "ererre",
        		"last_name": "df",
        		"second_last_name": "df",
        		"telephone": "s2",
        		"email": "sucursal2@grupofarmapronto.com",
        		"player_id": null,
        		"activo": 1,
        		"created_at": "2017-07-05 13:45:00",
        		"updated_at": "2017-07-11 19:32:04",
        		"deleted_at": null,
        		"sucursales": [
        			{
        				"id": 2,
        				"user_id": 53,
        				"codigo": "2",
        				"nombre": "BB",
        				"telefono": null,
        				"colonia_id": 18488,
        				"municipio_id": 365,
        				"estado_id": 12,
        				"direccion": "AV. INSURGENTES",
        				"direccion_numero": "28",
        				"codigo_postal": "39010",
        				"lon": "12321",
        				"lat": "12312www",
        				"created_at": "2017-03-16 17:50:05",
        				"updated_at": "2017-07-11 19:29:25",
        				"pivot": {
        					"user_id": 53,
        					"sucursal_id": 2
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

  /api/sucursales?limit=2
 
 
 **Parametros**
 - limit | numérico, define el total de resultados por petición
 - includes[] incluye relaciones del modelo 
    - colonia
    - municipio
    - estado
    - listaPrecio
    - pedidos
  
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
        			"user_id": 52,
        			"codigo": "1",
        			"nombre": "AA",
        			"telefono": null,
        			"colonia_id": 34733,
        			"municipio_id": 502,
        			"estado_id": 17,
        			"direccion": "AV. VICENTE GUERRERO",
        			"direccion_numero": "107",
        			"codigo_postal": "62230",
        			"lon": null,
        			"lat": null,
        			"created_at": "2017-03-16 17:50:05",
        			"updated_at": "2017-07-05 13:44:59",
        			"users": [
        				{
        					"id": 131,
        					"name": "234",
        					"last_name": "123",
        					"second_last_name": "123",
        					"telephone": "s2",
        					"email": "testsucursal@cs.com",
        					"player_id": null,
        					"activo": 1,
        					"created_at": "2017-07-11 19:22:27",
        					"updated_at": "2017-07-11 19:22:27",
        					"deleted_at": null,
        					"pivot": {
        						"sucursal_id": 1,
        						"user_id": 131
        					}
        				},
        				{
        					"id": 132,
        					"name": "234",
        					"last_name": "123",
        					"second_last_name": "123",
        					"telephone": "s2",
        					"email": "testsucursal2@cs.com",
        					"player_id": null,
        					"activo": 1,
        					"created_at": "2017-07-11 19:22:48",
        					"updated_at": "2017-07-11 19:22:48",
        					"deleted_at": null,
        					"pivot": {
        						"sucursal_id": 1,
        						"user_id": 132
        					}
        				}
        			]
        		},
        		{
        			"id": 2,
        			"user_id": 53,
        			"codigo": "2",
        			"nombre": "BB",
        			"telefono": null,
        			"colonia_id": 18488,
        			"municipio_id": 365,
        			"estado_id": 12,
        			"direccion": "AV. INSURGENTES",
        			"direccion_numero": "28",
        			"codigo_postal": "39010",
        			"lon": "12321",
        			"lat": "12312www",
        			"created_at": "2017-03-16 17:50:05",
        			"updated_at": "2017-07-11 19:29:25",
        			"users": [
        				{
        					"id": 53,
        					"name": "ererre",
        					"last_name": "df",
        					"second_last_name": "df",
        					"telephone": "s2",
        					"email": "sucursal2@grupofarmapronto.com",
        					"player_id": null,
        					"activo": 1,
        					"created_at": "2017-07-05 13:45:00",
        					"updated_at": "2017-07-11 19:32:04",
        					"deleted_at": null,
        					"pivot": {
        						"sucursal_id": 2,
        						"user_id": 53
        					}
        				}
        			]
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

  /api/sucursales/me

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
          "sucursal": {
              "id": 12,
              "name": "API",
              "last_name": "Sucursal",
              "second_last_name": "test",
              "telephone": "7771234567",
              "email": "apisucursaltest2@grupofarmapronto.com",
              "created_at": "2017-06-06 16:33:29",
              "updated_at": "2017-06-06 16:33:29",
              "deleted_at": null
            }
        }
 
**Error Response:**

  * **Code:** 401 Unauthorized <br />
      **Content:** 
      
          {
            "error": "Unauthenticated."
          }




**Obtener sucursales por estado**
----
  Regresa sucursales por estado id

 **URL**

  /api/sucursales/estado/{ID_ESTADO}?includes[]=municipio&includes[]=colonia

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
        	"sucursales": [
        		{
        			"id": 2,
        			"user_id": 53,
        			"codigo": "2",
        			"nombre": "BB",
        			"telefono": null,
        			"colonia_id": 18488,
        			"municipio_id": 365,
        			"estado_id": 12,
        			"direccion": "AV. INSURGENTES",
        			"direccion_numero": "28",
        			"codigo_postal": "39010",
        			"lon": null,
        			"lat": null,
        			"created_at": "2017-03-16 17:50:05",
        			"updated_at": "2017-07-05 13:45:00",
        			"municipio": {
        				"id": 365,
        				"estado_id": 12,
        				"nombre": "CHILPANCINGO DE LOS BRAVO",
        				"created_at": "2017-03-16 17:47:55",
        				"updated_at": "2017-03-16 17:47:55"
        			},
        			"colonia": {
        				"id": 18488,
        				"municipio_id": 365,
        				"codigo_postal": "39010",
        				"nombre": "AZTECA",
        				"created_at": "2017-03-16 17:48:25",
        				"updated_at": "2017-03-16 17:48:25"
        			}
        		},
        		{
        			"id": 3,
        			"user_id": 54,
        			"codigo": "3",
        			"nombre": "CC",
        			"telefono": null,
        			"colonia_id": 18485,
        			"municipio_id": 365,
        			"estado_id": 12,
        			"direccion": "FRANCISCO I. MADERO",
        			"direccion_numero": "11",
        			"codigo_postal": "39000",
        			"lon": null,
        			"lat": null,
        			"created_at": "2017-03-16 17:50:05",
        			"updated_at": "2017-07-05 13:45:00",
        			"municipio": {
        				"id": 365,
        				"estado_id": 12,
        				"nombre": "CHILPANCINGO DE LOS BRAVO",
        				"created_at": "2017-03-16 17:47:55",
        				"updated_at": "2017-03-16 17:47:55"
        			},
        			"colonia": {
        				"id": 18485,
        				"municipio_id": 365,
        				"codigo_postal": "39000",
        				"nombre": "CHILPANCINGO DE LOS BRAVOS CENTRO",
        				"created_at": "2017-03-16 17:48:25",
        				"updated_at": "2017-03-16 17:48:25"
        			}
        		}...
        	]
        }
 
**Error Response:**

  * **Code:** 401 Unauthorized <br />
      **Content:** 
      
          {
            "error": "Unauthenticated."
          }

