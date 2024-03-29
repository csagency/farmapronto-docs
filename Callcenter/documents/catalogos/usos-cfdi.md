      
## Listado de usos CFDI
Regresa el listado del catálogo de Usos CFDI

 **URL**

  /api/catalogos/usos-cfdi

 **Method:**

  `GET`

**Success Response:**

* **Code:** 200 <br />
  **Content:** 
  
      {
        "usos": [
            {
              "id": 1,
              "clave": "G01",
              "nombre": "ADQUISICIÓN DE MERCANCIAS",
              "created_at": "2019-07-11 17:03:38",
              "updated_at": "2019-07-11 17:03:38"
            },
            {
              "id": 2,
              "clave": "G03",
              "nombre": "GASTOS EN GENERAL",
              "created_at": "2019-07-11 17:03:39",
              "updated_at": "2019-07-11 17:03:39"
            },
            {
              "id": 3,
              "clave": "P01",
              "nombre": "POR DEFINIR",
              "created_at": "2019-07-11 17:03:39",
              "updated_at": "2019-07-11 17:03:39"
            }
        ]
      }

 
**Datos de un uso CFDI**
----
  Regresa la información de una uso CFDI en específico y sus relaciones

 **URL**

  /api/catalogos/usos-cfdi/ID

 **Method:**

  `GET`
      
  **URL Params**

  Ejemplo URI: `api/catalogos/catalogos/usos-cfdi/1
  

 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 

        {
            "uso": {
                "id": 2,
                "clave": "G03",
                "nombre": "GASTOS EN GENERAL",
                "created_at": "2019-07-11 17:03:39",
                "updated_at": "2019-07-11 17:03:39"
            }
        }