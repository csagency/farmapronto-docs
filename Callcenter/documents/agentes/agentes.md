      
**Acceso**
----

Metodo de autentificación y acceso con oAuth 2.0
Cada usuario debera solicitar su access token para realizar solicitudes a la API

 **URL**

   `/api/login/custom`

 **Method:**

  `POST`

 **Data Params**
    
     'email'        => 'required|string|email',
     'password'     => 'required|string',
     'tipo_usuario' => 'required|string|in:repartidor',

+ Request (application/json)
    + Body
        + FormParams
    
                [
                    'email' => 'supervisor@farma.com',
                    'password' => 'secret',
                    'tipo_usuario' => 'repartidor',
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
  
       
**Registro de agente**
----
  Regresa la información del registro en formato json

 **URL**

  /api/agentes/registro/

 **Method:**

  `POST`
  
  **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data
      
  **URL Params**

  None
 
 **Data Params**

 ***Required:***
    
     `name=[required]`
     `last_name=[required]`
     `second_last_name=[required]`
     `telephone=[required]`
     `email=[required|unique]`
     `password=[required|min:6]`
     `numero_control=[required|unique]`
     `estatus=[boolean]`
     `lat=[optional]`
     `lon=[optional]`
     `imagen=[optional]`
     `imagen_path=[optional]`
     `player_id=[optional]`


 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
            "agente": {
              "name": "Agente",
              "last_name": "Prueba",
              "second_last_name": "API",
              "telephone": "7770987345",
              "email": "agenteapi@grupofarmapronto.com",
              "updated_at": "2017-05-29 17:04:02",
              "created_at": "2017-05-29 17:04:02",
              "id": 5,
              "agente_perfil": {
                "id": 1,
                "user_id": 5,
                "colonia_id": 2,
                "numero_control": "1234qwer12",
                "estatus": null,
                "created_at": "2017-05-29 17:04:02",
                "updated_at": "2017-05-29 17:04:02",
                "deleted_at": null,
                "lat": null,
                "lon": null,
                "imagen": null,
                "imagen_path": null
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
            ],
            "email": [
              "El campo correo electrónico es obligatorio."
            ],
            "password": [
                "El campo contraseña es obligatorio."
            ],
            "numero_control": [
              "El campo numéro de control es obligatorio."
            ]
        }

 
**Datos del agente**
----
  Regresa la información del usuario y su perfil agente

 **URL**

  /api/agentes/me

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
        	"agente": {
        		"id": 3,
        		"name": "Agente",
        		"last_name": "Farmapronto",
        		"second_last_name": "test",
        		"telephone": "7777777779",
        		"email": "agente@grupofarmapronto.com",
        		"player_id": "null",
        		"created_at": "2017-03-16 17:47:54",
        		"updated_at": "2017-03-16 17:47:54",
        		"deleted_at": null,
        		"agente_perfil": {
        			"id": 1,
        			"user_id": 3,
        			"numero_control": "23423",
        			"estatus": "en transito",
        			"created_at": "2017-06-22 18:25:32",
        			"updated_at": "2017-06-22 17:38:45",
        			"deleted_at": null,
        			"lat": "99990",
        			"lon": "120",
        			"imagen": null,
        			"imagen_path": null,
        			"vehiculo_id": null,
        			"perfil": null
        		}
        	}
        }
 
 **Error Response:**

  * **Code:** 401 Unauthorized <br />
      **Content:** 
      
          {
            "error": "Unauthenticated."
          }



**Actualización del agente**
----
  Actualiza la información del usuario agente y su perfil incluyendo sus coordenadas

 **URL**

  /api/agentes/me

 **Method:**

  `POST`
    
 **Headers**
 
    Authorization: Bearer access_token
    Accept: application/json
    Content-Type: multipart/form-data
    
 **Multipart**
 
      'name' => '',
      'last_name' => '',
      'second_last_name' => '',
      'telephone' => '',
      'email' => 'email|unique:users,email,'.$user->id,
      'password' => 'min:6',
      'numero_control' => '',
      'estatus' => 'boolean',
      'lat' => 'numeric|min:13|max:33',
      'lon' => 'numeric|min:-120|max:-80',
      'imagen' => '',
      'imagen_path' => '',
      'player_id' => '',
      'motivo' => ''
    
 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
        	"agente": {
        		"id": 3,
        		"name": "Agente",
        		"last_name": "Farmapronto",
        		"second_last_name": "test",
        		"telephone": "7777777779",
        		"email": "agente@grupofarmapronto.com",
        		"player_id": "null",
        		"created_at": "2017-03-16 17:47:54",
        		"updated_at": "2017-03-16 17:47:54",
        		"deleted_at": null,
        		"agente_perfil": {
        			"id": 1,
        			"user_id": 3,
        			"colonia_id": 1,
        			"numero_control": "23423",
        			"estatus": null,
        			"created_at": "2017-06-22 18:25:32",
        			"updated_at": "2017-06-22 17:33:38",
        			"deleted_at": null,
        			"lat": "1232123",
        			"lon": "1324234",
        			"imagen": null,
        			"imagen_path": null
        		}
        	}
        }

 **Error Response:**

  * **Code:** 401 Unauthorized <br />
    **Content:** 
    
        {
          "error": "Unauthenticated."
        }
        
        
  * **Code:** 409 Conflict <br />
    **Content:** 
    
        {
          "error": "El usuario no cuenta con perfil de agente."
        }


  * **Code:** 422 Unprocessable Entity <br />
    **Content:** 
    
        {
          "email": [
            "correo electrónico ya ha sido registrado."
          ]
          "lat": [
             "El tamaño de lat debe ser de al menos 13."
          ],
          "lon": [
             "lon no debe ser mayor a -80."
          ]
        }
