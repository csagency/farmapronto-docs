
## Listado de zonas del avatar
Devuelve el listado de todas las zonas del avatar. 

 **URL**

  /api/avatar/zonas

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
            "zonas": [
            		{
            			"id": 1,
            			"nombre": "Cabeza",
            			"avatar_seccion_id": 1,
            			"created_at": "2018-04-27 12:27:06",
            			"updated_at": "2018-04-27 12:27:06",
            			"deleted_at": null
            		},
            		{
            			"id": 2,
            			"nombre": "Cara",
            			"avatar_seccion_id": 1,
            			"created_at": "2018-04-27 12:27:06",
            			"updated_at": "2018-04-27 12:27:06",
            			"deleted_at": null
            		},
            		{
            			"id": 3,
            			"nombre": "Ojos",
            			"avatar_seccion_id": 1,
            			"created_at": "2018-04-27 12:27:06",
            			"updated_at": "2018-04-27 12:27:06",
            			"deleted_at": null
            		},
            		{
            			"id": 4,
            			"nombre": "Boca",
            			"avatar_seccion_id": 1,
            			"created_at": "2018-04-27 12:27:06",
            			"updated_at": "2018-04-27 12:27:06",
            			"deleted_at": null
            		},
            		{
            			"id": 5,
            			"nombre": "Nariz",
            			"avatar_seccion_id": 1,
            			"created_at": "2018-04-27 12:27:06",
            			"updated_at": "2018-04-27 12:27:06",
            			"deleted_at": null
            		},
            		{
            			"id": 6,
            			"nombre": "Oídos",
            			"avatar_seccion_id": 1,
            			"created_at": "2018-04-27 12:27:06",
            			"updated_at": "2018-04-27 12:27:06",
            			"deleted_at": null
            		},
            		{
            			"id": 7,
            			"nombre": "Estómago",
            			"avatar_seccion_id": 2,
            			"created_at": "2018-04-27 12:27:06",
            			"updated_at": "2018-04-27 12:27:06",
            			"deleted_at": null
            		},
            		{
            			"id": 8,
            			"nombre": "Brazo",
            			"avatar_seccion_id": 3,
            			"created_at": "2018-04-27 12:27:06",
            			"updated_at": "2018-04-27 12:27:06",
            			"deleted_at": null
            		},
            		{
            			"id": 9,
            			"nombre": "Mano",
            			"avatar_seccion_id": 3,
            			"created_at": "2018-04-27 12:27:06",
            			"updated_at": "2018-04-27 12:27:06",
            			"deleted_at": null
            		},
            		{
            			"id": 10,
            			"nombre": "Piernas",
            			"avatar_seccion_id": 4,
            			"created_at": "2018-04-27 12:27:06",
            			"updated_at": "2018-04-27 12:27:06",
            			"deleted_at": null
            		},
            		{
            			"id": 11,
            			"nombre": "Pies",
            			"avatar_seccion_id": 4,
            			"created_at": "2018-04-27 12:27:06",
            			"updated_at": "2018-04-27 13:44:12",
            			"deleted_at": null
            		},
            		{
            			"id": 12,
            			"nombre": "Pelvis",
            			"avatar_seccion_id": 5,
            			"created_at": "2018-04-27 12:27:06",
            			"updated_at": "2018-04-27 12:27:06",
            			"deleted_at": null
            		}
            	]
      }

 **Error Response:**
      
  * **Code:** 401 Unauthorized <br />
      **Content:** 
      
          {
            "error": "Unauthenticated."
          }


**Detalle de la zona avatar**
----
Devuelve el detalle de la zona, así como los síntomas que coinciden con el sexo del usuario.

 **URL**

  /api/avatar/zonas/ID

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
        	"zona": {
                "id": 3,
                "nombre": "Ojos",
                "avatar_seccion_id": 1,
                "created_at": "2018-05-18 17:14:47",
                "updated_at": "2018-05-18 17:14:47",
                "deleted_at": null,
                "sintomas_sexo": [
                    {
                        "id": 4,
                        "nombre": "Irritados",
                        "avatar_seccion_id": 1,
                        "avatar_zona_id": 3,
                        "sexo": "Hombre",
                        "created_at": "2018-05-18 17:14:48",
                        "updated_at": "2018-05-18 17:14:48",
                        "deleted_at": null
                    },
                    {
                        "id": 5,
                        "nombre": "Secos",
                        "avatar_seccion_id": 1,
                        "avatar_zona_id": 3,
                        "sexo": "Hombre",
                        "created_at": "2018-05-18 17:14:48",
                        "updated_at": "2018-05-18 17:14:48",
                        "deleted_at": null
                    },
                    {
                        "id": 6,
                        "nombre": "Ardor",
                        "avatar_seccion_id": 1,
                        "avatar_zona_id": 3,
                        "sexo": "Hombre",
                        "created_at": "2018-05-18 17:14:48",
                        "updated_at": "2018-05-18 17:14:48",
                        "deleted_at": null
                    },
                    {
                        "id": 7,
                        "nombre": "Lagañas",
                        "avatar_seccion_id": 1,
                        "avatar_zona_id": 3,
                        "sexo": "Hombre",
                        "created_at": "2018-05-18 17:14:48",
                        "updated_at": "2018-05-18 17:14:48",
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
