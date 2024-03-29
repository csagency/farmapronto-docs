
## Valida hora de pedidos programados
Regresa el listado del catálogo de Estados

 **URL**

  /api/validar-pedidos-programados

 **Method:**

  `POST`


**Input**


    programado_at  => 2018-11-03 16:20



 **Headers**

   Accept: application/json
   Content-Type: application/x-www-form-urlencoded



**Success Response:**

* **Code:** 200 <br />
  **Content:**


    "Pedidos disponibles"



**Error Response:**

* **Code:** 422 <br />
  **Content:**


      {
        "error": "programado_at obligatorio"
      }


* **Code:** 422 <br />
  **Content:**


      {
      	"error": "Pedidos programados fuera del horario"
      }


## Valida horario de zona

 **URL**

  /api/validar-horario/{ciudad_cobertura_id}

 **Method:**

  `GET`


 **Headers**

   Accept: application/json
   Content-Type: application/x-www-form-urlencoded



**Success Response:**

* **Code:** 200 <br />
  **Content:**


           {
               "ciudad": {
                   "id": 1,
                   "estado_id": 17,
                   "municipio_id": 502,
                   "lat": "18.92421",
                   "lon": "-99.221566",
                   "nombre": "CUERNAVACA",
                   "horario_final": "07:00",
                   "horario_inicio": "22:00",
                   "_24_hrs": 0,
                   "validada": 0,
                   "created_at": "2018-09-03 16:57:19",
                   "updated_at": "2018-09-03 16:57:19"
               },
               "taxi": 0,
               "now": {
                   "date": "2018-12-04 19:14:30.784283",
                   "timezone_type": 3,
                   "timezone": "America\/Mexico_City"
               }
           }


* **Code:** 406 <br />
  **Content:**


      {
      	"error": "Horario de entrega no disponible"
      }


## Obtener costo de taxi al CP

 **URL**

  /api/obtener-costo-taxi/{codigo_postal}

 **Method:**

  `GET`


 **Headers**

   Accept: application/json
   Content-Type: application/x-www-form-urlencoded



**Success Response:**

* **Code:** 200 <br />
  **Content:**


        {
            "taxi_cp": {
                "id": 1,
                "cp": "62270",
                "costo": 60,
                "created_at": "2018-11-06 14:06:59",
                "updated_at": "2018-11-06 16:19:31"
              }
        }


**Error Response:**

* **Code:** 422 <br />
  **Content:**


      {
        "error": "Código postal obligatorio"
      }
      
* **Code:** 406 <br />
  **Content:**


      {
      	"error": "Por el momento no contamos con costo de taxi al CP ingresado"
      }
