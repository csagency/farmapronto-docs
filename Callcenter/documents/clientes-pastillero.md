## Pastillero
Regresa los pastilleros añadidos por los usuarios

 **URL**

  /api/clientes/pastillero

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
      	"pastillero": [
      		{
      			"id": 1,
      			"user_id": 123,
      			"medicina": "Paracetamol",
      			"alerta_at": "2018-06-26 19:01:00",
      			"periodo_horas": "1",
      			"periodo_dias": 3,
      			"medida_medicina": "Cucharada",
      			"cantidad_medicina": "2",
      			"created_at": "2018-06-26 18:56:08",
      			"updated_at": "2018-06-26 18:56:08"
      		}
      	]
      }

**Error Response:**

* **Code:** 401 Unauthorized <br />
  **Content:**

      {
        "error": "Unauthenticated."
      }


**Registro de Pastillero**
----
  Almacena pastillero

 **URL**

  /api/clientes/pastillero

 **Method:**

  `POST`

  **URL Params**

  None

 **Data Params**

 ***Required:***


            'producto_id' => 'exists:productos,id',
            'alerta_at' => 'required|date',
            'periodo_horas' => 'required|numeric',
            'periodo_dias' => 'required|numeric',
            'periodo_semanas' => 'nullable|numeric',
            'periodo_meses' => 'nullable|numeric',
            'medida_medicina' => '',
            'cantidad_medicina' => '',
            'cantidad_caja' => '',
            'fecha_caducidad' => '',
            'presentacion_producto' => '',
            'primera_dosis' => ''


 **Success Response:**

  * **Code:** 200 <br />
    **Content:**



       {
           "pastillero": {
               "medicina": "Paracetamol 3",
               "alerta_at": "2019-03-15 17:45:00",
               "periodo_horas": "12",
               "periodo_meses": "4",
               "medida_medicina": "Cucharada",
               "cantidad_medicina": "2",
               "producto_id": "1",
               "cantidad_caja": "6",
               "fecha_caducidad": "2017-122",
               "presentacion_producto": "caja",
               "primera_dosis": "2019-03-15 17:45:00",
               "user_id": 9995,
               "updated_at": "2019-03-15 18:30:03",
               "created_at": "2019-03-15 18:30:03",
               "id": 357,
               "alertas": [],
               "producto": {
                   "id": 1,
                   "farmapronto_id": "000001",
                   "sku": "736085400892",
                   "nombre": "3-A OFTENO 1MG GTS 5ML",
                   "descripcion": "\u0000",
                   "categoria": "ORGANOS DE LOS SENTIDOS",
                   "categoria_id": 0,
                   "laboratorio": "SOPHIA",
                   "receta": 0,
                   "clave": "DISPONIBLE",
                   "tipo": 7,
                   "activos": "DICLOFENACO SODICO",
                   "keywords": "\u0000",
                   "destacado": 0,
                   "archivo": "uploads/images/productos/farma_default.png",
                   "created_at": "2017-03-16 17:49:19",
                   "updated_at": "2019-02-21 05:00:44",
                   "activo": 1,
                   "despliega": 1
               }
           }
       }

 **Error Response:**

  * **Code:** 422 Unprocessable Entity <br />
    **Content:**


        {
        	"medicina": [
        		"El campo medicina es obligatorio."
        	],
        	"alerta_at": [
        		"El campo alerta at es obligatorio."
        	],
        	"periodo_horas": [
        		"El campo periodo horas es obligatorio."
        	],
        	"periodo_dias": [
        		"El campo periodo dias es obligatorio."
        	],
        	"medida_medicina": [
        		"El campo medida medicina es obligatorio."
        	],
        	"cantidad_medicina": [
        		"El campo cantidad medicina es obligatorio."
        	]
        }


  * **Code:** 401 Unauthorized <br />
      **Content:**

          {
            "error": "Unauthenticated."
          }


**Detalle del pastillero**
----

 **URL**

  /api/clientes/pastillero/ID

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
        	"pastillero": [
        		{
        			"id": 1,
        			"user_id": 123,
        			"medicina": "Paracetamol",
        			"alerta_at": "2018-06-26 19:01:00",
        			"periodo_horas": "1",
        			"periodo_dias": 3,
        			"medida_medicina": "Cucharada",
        			"cantidad_medicina": "2",
        			"created_at": "2018-06-26 18:56:08",
        			"updated_at": "2018-06-26 18:56:08",
        			"alertas": [
        				{
        					"id": 1,
        					"pastillero_id": 1,
        					"alerta_at": "2018-06-26 19:01:00",
        					"created_at": "2018-06-26 18:56:08",
        					"updated_at": "2018-06-26 18:56:08"
        				},
        				{
        					"id": 2,
        					"pastillero_id": 1,
        					"alerta_at": "2018-06-26 21:01:00",
        					"created_at": "2018-06-26 18:56:08",
        					"updated_at": "2018-06-26 18:56:08"
        				},
                    }
                ],
                "producto": {
                			"id": 1,
                			"farmapronto_id": "000001",
                			"sku": "736085400892",
                			"nombre": "3-A OFTENO 1MG GTS 5ML",
                			"descripcion": "",
                			"categoria": "ORGANOS DE LOS SENTIDOS",
                			"categoria_id": 0,
                			"laboratorio": "SOPHIA",
                			"receta": 0,
                			"clave": "DISPONIBLE",
                			"tipo": 9,
                			"activos": "DICLOFENACO SODICO",
                			"keywords": "",
                			"destacado": 0,
                			"archivo": "uploads\/images\/productos\/farma_default.png",
                			"created_at": "2017-03-16 17:49:19",
                			"updated_at": "2018-10-10 20:01:53",
                			"activo": 1,
                			"despliega": 1
                		}
        }


 **Error Response:**

  * **Code:** 401 Unauthorized <br />
    **Content:**

        {
          "error": "Unauthenticated."
        }



**Actualización del pastillero**
----

 **URL**

  /api/clientes/pastillero/ID

 **Method:**

  `PUT`

 **Headers**

    Authorization: Bearer access_token
    Accept: application/json
    Content-Type: multipart/form-data

**Data Params**

 ***Required:***


             'medicina' => '',
             'producto_id' => 'exists:productos,id',
             'alerta_at' => 'required|date',
             'periodo_horas' => 'required|numeric',
             'periodo_dias' => 'required|numeric',
             'medida_medicina' => '',
             'cantidad_medicina' => '',
             'cantidad_caja' => '',
             'fecha_caducidad' => '',
             'presentacion_producto' => '',
             'primera_dosis' => ''


 **Success Response:**

  * **Code:** 200 <br />
    **Content:**

        {
        	"pastillero": {
        		"id": 1,
        		"user_id": 123,
        		"medicina": "Moesds",
        		"alerta_at": "2018-06-26 19:01:00",
        		"periodo_horas": "1",
        		"periodo_dias": "3",
        		"medida_medicina": "Cucharada",
        		"cantidad_medicina": "2",
        		"created_at": "2018-06-26 18:56:08",
        		"updated_at": "2018-06-26 19:00:09",
        		"alertas": [
        			{
        				"id": 73,
        				"pastillero_id": 1,
        				"alerta_at": "2018-06-26 19:01:00",
        				"created_at": "2018-06-26 19:00:09",
        				"updated_at": "2018-06-26 19:00:09"
        			},
        			{
        				"id": 74,
        				"pastillero_id": 1,
        				"alerta_at": "2018-06-26 21:01:00",
        				"created_at": "2018-06-26 19:00:09",
        				"updated_at": "2018-06-26 19:00:09"
        			},
        			{
                ],
                "producto": {
                			"id": 1,
                			"farmapronto_id": "000001",
                			"sku": "736085400892",
                			"nombre": "3-A OFTENO 1MG GTS 5ML",
                			"descripcion": "",
                			"categoria": "ORGANOS DE LOS SENTIDOS",
                			"categoria_id": 0,
                			"laboratorio": "SOPHIA",
                			"receta": 0,
                			"clave": "DISPONIBLE",
                			"tipo": 9,
                			"activos": "DICLOFENACO SODICO",
                			"keywords": "",
                			"destacado": 0,
                			"archivo": "uploads\/images\/productos\/farma_default.png",
                			"created_at": "2017-03-16 17:49:19",
                			"updated_at": "2018-10-10 20:01:53",
                			"activo": 1,
                			"despliega": 1
                		}
        }


 **Error Response:**

  * **Code:** 422 Unprocessable Entity <br />
      **Content:**

         {
         	"medicina": [
         		"El campo medicina es obligatorio."
         	],
         	"alerta_at": [
         		"El campo alerta at es obligatorio."
         	],
         	"periodo_horas": [
         		"El campo periodo horas es obligatorio."
         	],
         	"periodo_dias": [
         		"El campo periodo dias es obligatorio."
         	],
         	"medida_medicina": [
         		"El campo medida medicina es obligatorio."
         	],
         	"cantidad_medicina": [
         		"El campo cantidad medicina es obligatorio."
         	]
         }


  * **Code:** 401 Unauthorized <br />
      **Content:**

          {
            "error": "Unauthenticated."
          }


**Eliminar pastillero y sus alertas**
----

 **URL**

  /api/clientes/pastillero/ID

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
        	"pastillero": {
        		"id": 1,
        		"user_id": 123,
        		"medicina": "Moesds",
        		"alerta_at": "2018-06-26 19:00:09",
        		"periodo_horas": "1",
        		"periodo_dias": 3,
        		"medida_medicina": "Cucharada",
        		"cantidad_medicina": "2",
        		"created_at": "2018-06-26 18:56:08",
        		"updated_at": "2018-06-26 19:00:09"
        	}
        }

 **Error Responses:**

  * **Code:** 401 Unauthorized <br />
    **Content:**

        {
          "error": "Unauthenticated."
        }