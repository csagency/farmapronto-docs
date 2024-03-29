
## Listado de saludables avatar
Devuelve el listado de los saludables avatar.

 **URL**

  /api/avatar/saludables

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
            "saludables": [
            		{
            			"id": 1,
            			"nombre": "Vitaminas",
            			"sexo": "Hombre",
            			"created_at": "2018-04-27 14:27:25",
            			"updated_at": "2018-04-27 14:27:25",
            			"deleted_at": null
            		}
            	]
      }

 **Error Response:**

  * **Code:** 406 Not Acceptable <br />
    **Content:**

        "El usuario no cuenta con perfil de cliente"
        "Usuario no válido"
      
  * **Code:** 401 Unauthorized <br />
      **Content:** 
      
          {
            "error": "Unauthenticated."
          }


**Productos del saludable**
----
Devuelve el detalle de un saludable, así como el listado de sus productos asociados y una lista de precios.

 **URL**

  /api/avatar/saludables/ID

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
        	"saludable": {
            		"id": 1,
            		"nombre": "Vitaminas",
            		"sexo": "Hombre",
            		"created_at": "2018-04-27 14:27:25",
            		"updated_at": "2018-04-27 14:27:25",
            		"deleted_at": null,
            		"productos": [
            			{
            				"id": 9301,
            				"farmapronto_id": "010459",
            				"sku": "7501258206723",
            				"nombre": "VITAMINA C 1 GR C\/10  CPR EFERV (OXITAL)",
            				"descripcion": "VITAMINA C 1 GR C\/10  CPR EFERV (OXITAL)",
            				"categoria": "VITAMINICOS",
            				"categoria_id": 0,
            				"laboratorio": "Bayer",
            				"receta": 0,
            				"clave": "SUJETO A DISPONIBILIDAD",
            				"tipo": 107,
            				"activos": "ACIDO ASCORBICO",
            				"destacado": 0,
            				"archivo": null,
            				"created_at": "2017-03-16 17:49:28",
            				"updated_at": "2018-04-25 06:34:05",
            				"activo": 1,
            				"pivot": {
            					"avatar_saludable_id": 1,
            					"producto_id": 9301
            				},
            				"lista_precios": [
            					{
            						"id": 6674,
            						"zona_id": 22,
            						"producto_id": 9301,
            						"precio": 101,
            						"created_at": "2017-06-22 17:57:20",
            						"updated_at": "2018-04-06 07:04:01"
            					}
            				]
            			},
            			{
            				"id": 24971,
            				"farmapronto_id": "027255",
            				"sku": "7502009744082",
            				"nombre": "VITAMINA C  225G C\/75 GOMITAS  (ANIMALIN)",
            				"descripcion": "VITAMINA C  225G C\/75 GOMITAS  (ANIMALIN)",
            				"categoria": "VITAMINICOS",
            				"categoria_id": 0,
            				"laboratorio": "Bayer",
            				"receta": 0,
            				"clave": "SUJETO A DISPONIBILIDAD",
            				"tipo": 62,
            				"activos": "ACIDO ASCORBICO",
            				"destacado": 0,
            				"archivo": null,
            				"created_at": "2017-03-16 17:49:41",
            				"updated_at": "2018-04-25 06:39:29",
            				"activo": 1,
            				"pivot": {
            					"avatar_saludable_id": 1,
            					"producto_id": 24971
            				},
            				"lista_precios": [
            					{
            						"id": 15764,
            						"zona_id": 22,
            						"producto_id": 24971,
            						"precio": 85.5,
            						"created_at": "2017-06-22 19:33:38",
            						"updated_at": "2017-12-24 06:53:45"
            					}
            				]
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



**Listado de saludables por sexo**
----
Devuelve un listado de saludables filtrados por un 'sexo' en específico.

 **URL**

  /api/avatar/saludables/filtroSexo/{sexo}

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
        	"saludables": [
                {
                    "id": 3,
                    "nombre": "Prueba",
                    "sexo": "Nños",
                    "created_at": "2018-07-27 10:27:43",
                    "updated_at": "2018-07-27 10:27:43",
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
