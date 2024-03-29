      
## Listado de colonias
Regresa el listado del catálogo de Colonias

 **URL**

  /api/catalogos/colonias

 **Method:**

  `GET`

**URL Params**

  - includes[]=municipio, municipio.estado <br><br>
  Ejemplo URI: `api/catalogos/colonias?includes[]=municipio.estado&limit=5`

**Success Response:**

* **Code:** 200 <br />
  **Content:** 
  
      {
        "colonias": [
            {
              "id": 1,
              "municipio_id": 84,
              "codigo_postal": "1000",
              "nombre": "SAN ANGEL",
              "created_at": "2017-05-29 16:31:16",
              "updated_at": "2017-05-29 16:31:16",
              "municipio": {
                "id": 84,
                "estado_id": 9,
                "nombre": "ALVARO OBREGON",
                "created_at": "2017-05-29 16:31:02",
                "updated_at": "2017-05-29 16:31:02",
                "estado": {
                  "id": 9,
                  "nombre": "DISTRITO FEDERAL",
                  "created_at": "2017-05-29 16:31:01",
                  "updated_at": "2017-05-29 16:31:01"
                }
              }
            },
            {
              "id": 2,
              "municipio_id": 84,
              "codigo_postal": "1000",
              "nombre": "VILLA OBREGON",
              "created_at": "2017-05-29 16:31:16",
              "updated_at": "2017-05-29 16:31:16",
              "municipio": {
                "id": 84,
                "estado_id": 9,
                "nombre": "ALVARO OBREGON",
                "created_at": "2017-05-29 16:31:02",
                "updated_at": "2017-05-29 16:31:02",
                "estado": {
                  "id": 9,
                  "nombre": "DISTRITO FEDERAL",
                  "created_at": "2017-05-29 16:31:01",
                  "updated_at": "2017-05-29 16:31:01"
                }
              }
            },
            {
              "id": 3,
              "municipio_id": 84,
              "codigo_postal": "1005",
              "nombre": "MAIL BOXES MBE POST SA DE CV",
              "created_at": "2017-05-29 16:31:16",
              "updated_at": "2017-05-29 16:31:16",
              "municipio": {
                "id": 84,
                "estado_id": 9,
                "nombre": "ALVARO OBREGON",
                "created_at": "2017-05-29 16:31:02",
                "updated_at": "2017-05-29 16:31:02",
                "estado": {
                  "id": 9,
                  "nombre": "DISTRITO FEDERAL",
                  "created_at": "2017-05-29 16:31:01",
                  "updated_at": "2017-05-29 16:31:01"
                }
              }
            },
            {
              "id": 4,
              "municipio_id": 84,
              "codigo_postal": "1010",
              "nombre": "LOS ALPES",
              "created_at": "2017-05-29 16:31:16",
              "updated_at": "2017-05-29 16:31:16",
              "municipio": {
                "id": 84,
                "estado_id": 9,
                "nombre": "ALVARO OBREGON",
                "created_at": "2017-05-29 16:31:02",
                "updated_at": "2017-05-29 16:31:02",
                "estado": {
                  "id": 9,
                  "nombre": "DISTRITO FEDERAL",
                  "created_at": "2017-05-29 16:31:01",
                  "updated_at": "2017-05-29 16:31:01"
                }
              }
            },
            {
              "id": 5,
              "municipio_id": 84,
              "codigo_postal": "1020",
              "nombre": "GUADALUPE INN",
              "created_at": "2017-05-29 16:31:16",
              "updated_at": "2017-05-29 16:31:16",
              "municipio": {
                "id": 84,
                "estado_id": 9,
                "nombre": "ALVARO OBREGON",
                "created_at": "2017-05-29 16:31:02",
                "updated_at": "2017-05-29 16:31:02",
                "estado": {
                  "id": 9,
                  "nombre": "DISTRITO FEDERAL",
                  "created_at": "2017-05-29 16:31:01",
                  "updated_at": "2017-05-29 16:31:01"
                }
              }
            }
        ]
      }

 
**Datos de una colonia**
----
  Regresa la información de una colonia en específico y sus relaciones

 **URL**

  /api/catalogos/colonias/ID

 **Method:**

  `GET`
      
  **URL Params**

  - includes[]=municipio, municipio.estado, sucursales, agentes, agentesEnServicio, agentesNoDisponible <br><br>
  Ejemplo URI: `api/catalogos/colonias/1?includes[]=municipio.estado&includes[]=agentes&includes[]=sucursales`
  

 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 

        { 
            "colonias": {
                "id": 1,
                "municipio_id": 84,
                "codigo_postal": "1000",
                "nombre": "SAN ANGEL",
                "created_at": "2017-05-29 16:31:16",
                "updated_at": "2017-05-29 16:31:16",
                "municipio": {
                  "id": 84,
                  "estado_id": 9,
                  "nombre": "ALVARO OBREGON",
                  "created_at": "2017-05-29 16:31:02",
                  "updated_at": "2017-05-29 16:31:02",
                  "estado": {
                    "id": 9,
                    "nombre": "DISTRITO FEDERAL",
                    "created_at": "2017-05-29 16:31:01",
                    "updated_at": "2017-05-29 16:31:01"
                  }
                },
                "agentes": [
                  {
                    "id": 3,
                    "user_id": 7,
                    "colonia_id": 1,
                    "numero_control": "qwer12",
                    "estatus": null,
                    "created_at": "2017-05-29 19:08:31",
                    "updated_at": "2017-05-29 19:25:50",
                    "deleted_at": null,
                    "lat": -99.1,
                    "long": 83.29,
                    "imagen": null,
                    "imagen_path": null
                  }
                ],
                "sucursales": []
            }
        }
    