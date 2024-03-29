
## Listado de secciones del avatar
Devuelve un listado con las secciones en las que puede ser dividido el avatar.

 **URL**

  /api/avatar/secciones

 **Method:**

  `GET`

**Success Response:**

* **Code:** 200 <br />
  **Content:**

      {
            "secciones": [
                {
                    "id": 1,
                    "nombre": "Cara",
                    "created_at": "2018-04-27 12:27:06",
                    "updated_at": "2018-04-27 12:27:06",
                    "deleted_at": null
                },
                {
                    "id": 2,
                    "nombre": "Estómago",
                    "created_at": "2018-04-27 12:27:06",
                    "updated_at": "2018-04-27 12:27:06",
                    "deleted_at": null
                },
                {
                    "id": 3,
                    "nombre": "Brazos",
                    "created_at": "2018-04-27 12:27:06",
                    "updated_at": "2018-04-27 12:27:06",
                    "deleted_at": null
                },
                {
                    "id": 4,
                    "nombre": "Piernas",
                    "created_at": "2018-04-27 12:27:06",
                    "updated_at": "2018-04-27 12:27:06",
                    "deleted_at": null
                },
                {
                    "id": 5,
                    "nombre": "Pelvis",
                    "created_at": "2018-04-27 12:27:06",
                    "updated_at": "2018-04-27 12:27:06",
                    "deleted_at": null
                }
            ]
      }


**Detalle de la sección avatar**
----
Devuelve el detalle de una sección, así como las zonas dentro de esta.

 **URL**

  /api/avatar/secciones/ID

 **Method:**

  `GET`

 **Success Response:**

  * **Code:** 200 <br />
    **Content:**

        {
        	"seccion": {
            		"id": 1,
            		"nombre": "Cara",
            		"created_at": "2018-04-27 12:27:06",
            		"updated_at": "2018-04-27 12:27:06",
            		"deleted_at": null,
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
            			}
            		]
            	}
        }
