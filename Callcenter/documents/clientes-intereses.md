## Catalogo Intereses
Regresa catálogo de intereses

 **URL**

  /api/catalogos/intereses

 **Method:**

  `GET`

 **Headers**

      Accept: application/json

**Success Response:**

* **Code:** 200 <br />
  **Content:**


      {
          "intereses": [
            {
              "id": 4,
              "titulo": "Bebés",
              "key": "bebes",
              "created_at": "2018-08-17 07:51:38",
              "updated_at": "2018-08-17 07:51:38",
              "deleted_at": null
            },
            {
              "id": 5,
              "titulo": "Dermatológicos",
              "key": "dermatologicos",
              "created_at": "2018-08-17 07:52:09",
              "updated_at": "2018-08-17 07:52:09",
              "deleted_at": null
            },
            {
              "id": 6,
              "titulo": "Naturismo",
              "key": "naturismo",
              "created_at": "2018-08-17 07:55:57",
              "updated_at": "2018-08-17 07:55:57",
              "deleted_at": null
            },
            {
              "id": 7,
              "titulo": "Vitaminas y Suplementos",
              "key": "vitaminas-y-suplementos",
              "created_at": "2018-08-17 07:57:49",
              "updated_at": "2018-08-17 07:57:49",
              "deleted_at": null
            },
            {
              "id": 8,
              "titulo": "Diabetes",
              "key": "diabetes",
              "created_at": "2018-08-17 07:58:15",
              "updated_at": "2018-08-17 07:58:15",
              "deleted_at": null
            },
            {
              "id": 9,
              "titulo": "Hipertensión",
              "key": "hipertension",
              "created_at": "2018-08-17 07:58:32",
              "updated_at": "2018-08-17 07:58:32",
              "deleted_at": null
            },
            {
              "id": 10,
              "titulo": "Higiene Personal",
              "key": "higiene-personal",
              "created_at": "2018-08-17 07:59:05",
              "updated_at": "2018-08-17 07:59:05",
              "deleted_at": null
            },
            {
              "id": 11,
              "titulo": "Ortopedia",
              "key": "ortopedia",
              "created_at": "2018-08-17 07:59:19",
              "updated_at": "2018-08-17 07:59:19",
              "deleted_at": null
            }
          ],
          "intereses_farmatips": [
            {
              "id": 1,
              "nombre": "Diabetes",
              "created_at": null,
              "updated_at": null,
              "deleted_at": null
            },
            {
              "id": 2,
              "nombre": "Hipertensión",
              "created_at": null,
              "updated_at": null,
              "deleted_at": null
            },
            {
              "id": 3,
              "nombre": "Salud",
              "created_at": null,
              "updated_at": null,
              "deleted_at": null
            }
          ]
        }


## Intereses del cliente
Regresa intereses guardados por el cliente

 **URL**

  /api/clientes/me/intereses

 **Method:**

  `GET`

 **Headers**

      Accept: application/json

**Success Response:**

* **Code:** 200 <br />
  **Content:**


      {
      	"intereses": [
      		{
      			"id": 1,
      			"titulo": "Bebés",
      			"key": "bebes",
      			"created_at": "2018-07-23 17:58:06",
      			"updated_at": "2018-07-23 17:58:06",
      			"deleted_at": null,
      			"pivot": {
      				"user_id": 123,
      				"catalogo_interes_id": 1,
      				"created_at": "2018-07-23 18:55:48",
      				"updated_at": "2018-07-23 18:55:48"
      			}
      		},
      		{
      			"id": 3,
      			"titulo": "Higiene personal",
      			"key": "higiene-personal",
      			"created_at": "2018-07-23 18:50:11",
      			"updated_at": "2018-07-23 18:50:11",
      			"deleted_at": null,
      			"pivot": {
      				"user_id": 123,
      				"catalogo_interes_id": 3,
      				"created_at": "2018-07-23 18:55:48",
      				"updated_at": "2018-07-23 18:55:48"
      			}
      		}
      	]
      }

**Error Response:**

* **Code:** 401 Unauthorized <br />
  **Content:**

      {
        "error": "Unauthenticated."
      }



**Registro  y actualización de intereses**
----
  Registra y actualiza los intereses del cliente por medio de array

 **URL**

  /api/clientes/me/intereses

 **Method:**

  `POST`

  **URL Params**

  None

 **Data Params**

 ***Required:***


    'intereses' => 'array|required'


 **Success Response:**

  * **Code:** 200 <br />
    **Content:**



       {
       	"intereses": [
       		{
       			"id": 1,
       			"titulo": "Bebés",
       			"key": "bebes",
       			"created_at": "2018-07-23 17:58:06",
       			"updated_at": "2018-07-23 17:58:06",
       			"deleted_at": null,
       			"pivot": {
       				"user_id": 123,
       				"catalogo_interes_id": 1,
       				"created_at": "2018-07-23 18:55:48",
       				"updated_at": "2018-07-23 18:55:48"
       			}
       		},
       		{
       			"id": 3,
       			"titulo": "Higiene personal",
       			"key": "higiene-personal",
       			"created_at": "2018-07-23 18:50:11",
       			"updated_at": "2018-07-23 18:50:11",
       			"deleted_at": null,
       			"pivot": {
       				"user_id": 123,
       				"catalogo_interes_id": 3,
       				"created_at": "2018-07-23 18:55:48",
       				"updated_at": "2018-07-23 18:55:48"
       			}
       		}
       	]
       }

 **Error Response:**

  * **Code:** 422 Unprocessable Entity <br />
    **Content:**


        {
        	"intereses": [
        		"El campo intereses es obligatorio."
        	]
        }


  * **Code:** 401 Unauthorized <br />
      **Content:**

          {
            "error": "Unauthenticated."
          }

