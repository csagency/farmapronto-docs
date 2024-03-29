      
## Listado de municipios
Regresa el listado del catálogo de Municipios

 **URL**

  /api/catalogos/municipios

 **Method:**

  `GET`

**URL Params**

  - includes[]=estados <br><br>
  Ejemplo URI: `api/catalogos/municipios?includes[]=estado&limit=10`

**Success Response:**

* **Code:** 200 <br />
  **Content:** 
  
      {
        "municipios": [
            {
              "id": 1,
              "estado_id": 31,
              "nombre": "ABALA",
              "created_at": "2017-05-29 16:31:01",
              "updated_at": "2017-05-29 16:31:01",
              "estado": {
                "id": 31,
                "nombre": "YUCATAN",
                "created_at": "2017-05-29 16:31:01",
                "updated_at": "2017-05-29 16:31:01"
              }
            },
            {
              "id": 2,
              "estado_id": 7,
              "nombre": "ABASOLO",
              "created_at": "2017-05-29 16:31:02",
              "updated_at": "2017-05-29 16:31:02",
              "estado": {
                "id": 7,
                "nombre": "COAHUILA",
                "created_at": "2017-05-29 16:31:01",
                "updated_at": "2017-05-29 16:31:01"
              }
            },
            {
              "id": 3,
              "estado_id": 11,
              "nombre": "ABASOLO",
              "created_at": "2017-05-29 16:31:02",
              "updated_at": "2017-05-29 16:31:02",
              "estado": {
                "id": 11,
                "nombre": "GUANAJUATO",
                "created_at": "2017-05-29 16:31:01",
                "updated_at": "2017-05-29 16:31:01"
              }
            },
            {
              "id": 4,
              "estado_id": 19,
              "nombre": "ABASOLO",
              "created_at": "2017-05-29 16:31:02",
              "updated_at": "2017-05-29 16:31:02",
              "estado": {
                "id": 19,
                "nombre": "NUEVO LEON",
                "created_at": "2017-05-29 16:31:01",
                "updated_at": "2017-05-29 16:31:01"
              }
            },
            {
              "id": 5,
              "estado_id": 28,
              "nombre": "ABASOLO",
              "created_at": "2017-05-29 16:31:02",
              "updated_at": "2017-05-29 16:31:02",
              "estado": {
                "id": 28,
                "nombre": "TAMAULIPAS",
                "created_at": "2017-05-29 16:31:01",
                "updated_at": "2017-05-29 16:31:01"
              }
            },
            {
              "id": 6,
              "estado_id": 20,
              "nombre": "ABEJONES",
              "created_at": "2017-05-29 16:31:02",
              "updated_at": "2017-05-29 16:31:02",
              "estado": {
                "id": 20,
                "nombre": "OAXACA",
                "created_at": "2017-05-29 16:31:01",
                "updated_at": "2017-05-29 16:31:01"
              }
            },
            {
              "id": 7,
              "estado_id": 5,
              "nombre": "ACACOYAGUA",
              "created_at": "2017-05-29 16:31:02",
              "updated_at": "2017-05-29 16:31:02",
              "estado": {
                "id": 5,
                "nombre": "CHIAPAS",
                "created_at": "2017-05-29 16:31:01",
                "updated_at": "2017-05-29 16:31:01"
              }
            },
            {
              "id": 8,
              "estado_id": 21,
              "nombre": "ACAJETE",
              "created_at": "2017-05-29 16:31:02",
              "updated_at": "2017-05-29 16:31:02",
              "estado": {
                "id": 21,
                "nombre": "PUEBLA",
                "created_at": "2017-05-29 16:31:01",
                "updated_at": "2017-05-29 16:31:01"
              }
            },
            {
              "id": 9,
              "estado_id": 30,
              "nombre": "ACAJETE",
              "created_at": "2017-05-29 16:31:02",
              "updated_at": "2017-05-29 16:31:02",
              "estado": {
                "id": 30,
                "nombre": "VERACRUZ",
                "created_at": "2017-05-29 16:31:01",
                "updated_at": "2017-05-29 16:31:01"
              }
            },
            {
              "id": 10,
              "estado_id": 5,
              "nombre": "ACALA",
              "created_at": "2017-05-29 16:31:02",
              "updated_at": "2017-05-29 16:31:02",
              "estado": {
                "id": 5,
                "nombre": "CHIAPAS",
                "created_at": "2017-05-29 16:31:01",
                "updated_at": "2017-05-29 16:31:01"
              }
            }
        ]
      }

 
**Datos de un municipio**
----
  Regresa la información de un municipio en específico y sus relaciones

 **URL**

  /api/catalogos/municipios/ID

 **Method:**

  `GET`
      
  **URL Params**

  - includes[]=estado, ciudades <br><br>
  Ejemplo URI: `api/catalogos/municipios/10?includes[]=estado&includes[]=ciudades`
  

 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 

        { 
            "municipios": {
                "id": 10,
                "estado_id": 5,
                "nombre": "ACALA",
                "created_at": "2017-05-29 16:31:02",
                "updated_at": "2017-05-29 16:31:02",
                "estado": {
                  "id": 5,
                  "nombre": "CHIAPAS",
                  "created_at": "2017-05-29 16:31:01",
                  "updated_at": "2017-05-29 16:31:01"
                },
                "ciudades": [
                  {
                    "id": 8601,
                    "municipio_id": 10,
                    "codigo_postal": "29370",
                    "nombre": "ACALA",
                    "created_at": "2017-05-29 16:31:27",
                    "updated_at": "2017-05-29 16:31:27"
                  },
                  {
                    "id": 8602,
                    "municipio_id": 10,
                    "codigo_postal": "29378",
                    "nombre": "SAN JOAQUIN",
                    "created_at": "2017-05-29 16:31:27",
                    "updated_at": "2017-05-29 16:31:27"
                  },
                  {
                    "id": 8603,
                    "municipio_id": 10,
                    "codigo_postal": "29379",
                    "nombre": "ADOLFO LOPEZ MATEOS",
                    "created_at": "2017-05-29 16:31:27",
                    "updated_at": "2017-05-29 16:31:27"
                  },
                  {
                    "id": 8604,
                    "municipio_id": 10,
                    "codigo_postal": "29380",
                    "nombre": "20 DE NOVIEMBRE",
                    "created_at": "2017-05-29 16:31:27",
                    "updated_at": "2017-05-29 16:31:27"
                  },
                  {
                    "id": 8605,
                    "municipio_id": 10,
                    "codigo_postal": "29387",
                    "nombre": "UNION BUENA VISTA",
                    "created_at": "2017-05-29 16:31:27",
                    "updated_at": "2017-05-29 16:31:27"
                  },
                  {
                    "id": 8606,
                    "municipio_id": 10,
                    "codigo_postal": "29388",
                    "nombre": "LA CONCEPCION",
                    "created_at": "2017-05-29 16:31:27",
                    "updated_at": "2017-05-29 16:31:27"
                  }
                ]
            }
        }
    
    

**Verificar cobertura de pedidos por latlon devolviendo ciudades**
----
  Regresa la información de un municipio en específico y sus relaciones

 **URL**

  /api/validar-cobertura

 **Method:**

  `POST`

 ***Required:***
    
     lat=[required]
     lon=[required]
     
 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 



           {
            "ciudades_cobertura_verificada": [
                {
                    "id": 2,
                    "estado_id": 17,
                    "municipio_id": 495,
                    "lat": "18.812222",
                    "lon": "-98.955833",
                    "nombre": "Cuautla",
                    "created_at": "2018-09-03 16:57:19",
                    "updated_at": "2018-09-03 16:57:19",
                    "distancia": 13.39052716363,
                    "estado": {
                        "id": 17,
                        "nombre": "MORELOS",
                        "created_at": "2017-03-16 17:47:54",
                        "updated_at": "2017-03-16 17:47:54"
                    },
                    "municipio": {
                        "id": 495,
                        "estado_id": 17,
                        "nombre": "CUAUTLA",
                        "created_at": "2017-03-16 17:47:55",
                        "updated_at": "2017-03-16 17:47:55"
                    }
                },
                {
                    "id": 3,
                    "estado_id": 17,
                    "municipio_id": 2345,
                    "lat": "18.906389",
                    "lon": "-98.970278",
                    "nombre": "Oaxtepec",
                    "created_at": "2018-09-03 16:57:19",
                    "updated_at": "2018-09-03 16:57:19",
                    "distancia": 5.150751153989,
                    "estado": {
                        "id": 17,
                        "nombre": "MORELOS",
                        "created_at": "2017-03-16 17:47:54",
                        "updated_at": "2017-03-16 17:47:54"
                    },
                    "municipio": {
                        "id": 2345,
                        "estado_id": 17,
                        "nombre": "YAUTEPEC",
                        "created_at": "2017-03-16 17:47:57",
                        "updated_at": "2017-03-16 17:47:57"
                    }
                }
            ]
           }
        
        
 **Error Response:**

  * **Code:** 406 <br />
    **Content:** 
    
    
        Zona sin cobertura
    
    
    
 **Error Response:**

  * **Code:** 410 <br />
    **Content:** 
    
    
        Zona sin cobertura de horario