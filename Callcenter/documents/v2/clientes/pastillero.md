## Pastillero
Regresa los pastilleros añadidos por los usuarios

 **URL**

    /api-v2/clientes/pastillero

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
              "id": 529,
              "user_id": 23516,
              "producto_id": null,
              "medicina": null,
              "alerta_at": "2020-05-01 17:50:00",
              "periodo_horas": "12",
              "periodo_dias": null,
              "periodo_meses": null,
              "periodo_semanas": null,
              "medida_medicina": null,
              "cantidad_medicina": null,
              "created_at": "2020-04-30 14:41:03",
              "updated_at": "2020-04-30 14:41:03",
              "fecha_caducidad": null,
              "presentacion_producto": null,
              "cantidad_caja": null,
              "primera_dosis": null,
              "producto": null
            },
            {
              "id": 530,
              "user_id": 23516,
              "producto_id": 1,
              "medicina": null,
              "alerta_at": "2020-05-01 17:50:00",
              "periodo_horas": "12",
              "periodo_dias": null,
              "periodo_meses": null,
              "periodo_semanas": null,
              "medida_medicina": null,
              "cantidad_medicina": null,
              "created_at": "2020-04-30 14:41:25",
              "updated_at": "2020-04-30 14:41:25",
              "fecha_caducidad": null,
              "presentacion_producto": null,
              "cantidad_caja": null,
              "primera_dosis": null,
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
                "tipo": 4,
                "activos": "DICLOFENACO SODICO",
                "keywords": "",
                "destacado": 0,
                "archivo": null,
                "created_at": "2017-03-16 17:49:19",
                "updated_at": "2020-03-18 06:00:46",
                "activo": 1,
                "despliega": 1
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


**Registro de Pastillero**
----
  Almacena pastillero

 **URL**

    /api-v2/clientes/pastillero

 **Method:**

  `POST`

  **URL Params**

  None

 **Data Params**

       'medicina' => '',
       'producto_id' => 'exists:productos,id',
       'alerta_at' => 'required|date',
       'periodo_horas' => 'required|numeric',
       'periodo_dias' => 'nullable|numeric',
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
           "alerta_at": "2020-05-01 17:50:00",
           "periodo_horas": "12",
           "producto_id": "1",
           "user_id": 23516,
           "updated_at": "2020-04-30 14:41:25",
           "created_at": "2020-04-30 14:41:25",
           "id": 530,
           "alertas": [],
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
             "tipo": 4,
             "activos": "DICLOFENACO SODICO",
             "keywords": "",
             "destacado": 0,
             "archivo": null,
             "created_at": "2017-03-16 17:49:19",
             "updated_at": "2020-03-18 06:00:46",
             "activo": 1,
             "despliega": 1
           }
         }
       }

 **Error Response:**

  * **Code:** 422 Unprocessable Entity <br />
    **Content:**


        {
        	  "alerta_at": [
                "El campo alerta at es obligatorio."
              ],
              "periodo_horas": [
                "El campo periodo horas es obligatorio."
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

    /api-v2/clientes/pastillero/ID

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
                  "id": 530,
                  "user_id": 23516,
                  "producto_id": 1,
                  "medicina": null,
                  "alerta_at": "2020-05-01 17:50:00",
                  "periodo_horas": "12",
                  "periodo_dias": null,
                  "periodo_meses": null,
                  "periodo_semanas": null,
                  "medida_medicina": null,
                  "cantidad_medicina": null,
                  "created_at": "2020-04-30 14:41:25",
                  "updated_at": "2020-04-30 14:41:25",
                  "fecha_caducidad": null,
                  "presentacion_producto": null,
                  "cantidad_caja": null,
                  "primera_dosis": null,
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
                    "tipo": 4,
                    "activos": "DICLOFENACO SODICO",
                    "keywords": "",
                    "destacado": 0,
                    "archivo": null,
                    "created_at": "2017-03-16 17:49:19",
                    "updated_at": "2020-03-18 06:00:46",
                    "activo": 1,
                    "despliega": 1
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



**Actualización del pastillero**
----

 **URL**

    /api-v2/clientes/pastillero/ID

 **Method:**

  `PUT`

 **Headers**

    Authorization: Bearer access_token
    Accept: application/json
    Content-Type: multipart/form-data

**Data Params**

    'medicina' => '',
    'producto_id' => 'exists:productos,id',
    'alerta_at' => 'required|date',
    'periodo_horas' => 'required|numeric',
    'periodo_dias' => 'nullable|numeric',
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
            "pastillero": [
                {
                  "id": 530,
                  "user_id": 23516,
                  "producto_id": 1,
                  "medicina": null,
                  "alerta_at": "2020-05-01 17:50:00",
                  "periodo_horas": "12",
                  "periodo_dias": null,
                  "periodo_meses": null,
                  "periodo_semanas": null,
                  "medida_medicina": null,
                  "cantidad_medicina": null,
                  "created_at": "2020-04-30 14:41:25",
                  "updated_at": "2020-04-30 14:41:25",
                  "fecha_caducidad": null,
                  "presentacion_producto": null,
                  "cantidad_caja": null,
                  "primera_dosis": null,
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
                    "tipo": 4,
                    "activos": "DICLOFENACO SODICO",
                    "keywords": "",
                    "destacado": 0,
                    "archivo": null,
                    "created_at": "2017-03-16 17:49:19",
                    "updated_at": "2020-03-18 06:00:46",
                    "activo": 1,
                    "despliega": 1
                  }
                }
            ]
        }


 **Error Response:**

  * **Code:** 422 Unprocessable Entity <br />
      **Content:**

         {
         	  "alerta_at": [
                "El campo alerta at es obligatorio."
              ],
              "periodo_horas": [
                "El campo periodo horas es obligatorio."
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

    /api-v2/clientes/pastillero/ID

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
            "id": 529,
            "user_id": 23516,
            "producto_id": null,
            "medicina": null,
            "alerta_at": "2020-05-01 17:50:00",
            "periodo_horas": "12",
            "periodo_dias": null,
            "periodo_meses": null,
            "periodo_semanas": null,
            "medida_medicina": null,
            "cantidad_medicina": null,
            "created_at": "2020-04-30 14:41:03",
            "updated_at": "2020-04-30 14:41:03",
            "fecha_caducidad": null,
            "presentacion_producto": null,
            "cantidad_caja": null,
            "primera_dosis": null
          }
        }

 **Error Responses:**

  * **Code:** 401 Unauthorized <br />
    **Content:**

        {
          "error": "Unauthenticated."
        }