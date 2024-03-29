      
## Tipos de tarjetas todas las referencias

 **URL**

  /api/catalogos/plan-lealtad-tipo-tarjetas
  
  
 **Method:**

  `GET`
  
 **Headers**
   
      Accept: application/json
      Content-Type: multipart/form-data



**Success Response:**

* **Code:** 200 <br />
  **Content:** 


      {
        "tipo_tarjetas": [
          {
            "id": 1,
            "nombre": "MTCL_KMC",
            "descripcion": "TARJETA FARMAPRONTO",
            "created_at": "2019-11-11 17:19:59",
            "updated_at": "2019-11-11 17:19:59"
          },
          {
            "id": 2,
            "nombre": "CDSORO",
            "descripcion": "TARJETA FARMAPRONTO",
            "created_at": "2019-11-11 17:19:59",
            "updated_at": "2019-11-11 17:19:59"
          },
          {
            "id": 3,
            "nombre": "MTCL_MRZ",
            "descripcion": "TARJETA FARMAPRONTO",
            "created_at": "2019-11-11 17:19:59",
            "updated_at": "2019-11-11 17:19:59"
          },
          .....
        ]
      }
      
      
      
            
## Tipos de tarjetas todas las referencias agrupadas por tipo

 **URL**

  /api/catalogos/plan-lealtad-tipo-tarjetas/agrupado

 **Method:**

  `GET`
  
 **Headers**
   
      Accept: application/json
      Content-Type: multipart/form-data



**Success Response:**

* **Code:** 200 <br />
  **Content:** 


      {
        "tipo_tarjetas": [
          {
            "id": 14,
            "nombre": "ABBOTT",
            "descripcion": " TARJETA FARMAPRONTO",
            "created_at": "2019-11-11 17:20:00",
            "updated_at": "2019-11-11 17:20:00"
          },
          {
            "id": 41,
            "nombre": "EMAP",
            "descripcion": "E-MAP CUPON VIRTUAL",
            "created_at": "2019-11-11 17:20:11",
            "updated_at": "2019-11-11 17:20:11"
          },
          {
            "id": 51,
            "nombre": "NOVO",
            "descripcion": "T.NUEVOYO ",
            "created_at": "2019-11-11 17:20:33",
            "updated_at": "2019-11-11 17:20:33"
          },
          {
            "id": 5,
            "nombre": "ABBOTT",
            "descripcion": "TARJETA ABRACE LA VIDA \"ABBOTT\" ",
            "created_at": "2019-11-11 17:19:59",
            "updated_at": "2019-11-11 17:19:59"
          },
          {
            "id": 12,
            "nombre": "ABBOTT",
            "descripcion": "TARJETA ABRACE LA VIDA \"ABBOTT\" \/ TARJETA FARMAPRONTO",
            "created_at": "2019-11-11 17:20:00",
            "updated_at": "2019-11-11 17:20:00"
          },
          {
            "id": 47,
            "nombre": "MSD",
            "descripcion": "TARJETA ACOMPAÑAME  \"MSD\" Y   \"TARJETA FARMAPRONTO\" ",
            "created_at": "2019-11-11 17:20:22",
            "updated_at": "2019-11-11 17:20:22"
          },
          {
            "id": 23,
            "nombre": "ASOFARMA",
            "descripcion": "TARJETA ACTUA \"ASOFARMA\" ",
            "created_at": "2019-11-11 17:20:02",
            "updated_at": "2019-11-11 17:20:02"
          },
          {
            "id": 1,
            "nombre": "MTCL_KMC",
            "descripcion": "TARJETA FARMAPRONTO",
            "created_at": "2019-11-11 17:19:59",
            "updated_at": "2019-11-11 17:19:59"
          },
          {
            "id": 54,
            "nombre": "PFIZER",
            "descripcion": "TARJETA PFIZER CONMIGO ",
            "created_at": "2019-11-11 17:20:37",
            "updated_at": "2019-11-11 17:20:37"
          },
          {
            "id": 53,
            "nombre": "PFIZER",
            "descripcion": "TARJETA PFIZER CONMIGO Y TARJETA FARMAPRONTO",
            "created_at": "2019-11-11 17:20:37",
            "updated_at": "2019-11-11 17:20:37"
          },
          {
            "id": 42,
            "nombre": "MERCK",
            "descripcion": "TARJETA TU ALIADO POR TU SALUD \"MERCK\"",
            "created_at": "2019-11-11 17:20:11",
            "updated_at": "2019-11-11 17:20:11"
          },
          {
            "id": 58,
            "nombre": "TUGUIA",
            "descripcion": "TARJETA TU GUIA",
            "created_at": "2019-11-11 17:20:50",
            "updated_at": "2019-11-11 17:20:50"
          }
        ]
      }