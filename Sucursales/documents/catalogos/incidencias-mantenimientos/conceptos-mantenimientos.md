## Listado de conceptos de mantenimientos
Regresa el listado de conceptos de mantenimientos de una categoría de mantenimiento<br>

 **URL**

    /api/catalogos/incidencias-mantenimientos/conceptos-mantenimientos/{categoriaMantenimientoId}

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
                "conceptosMantenimientos": [
                    {
                        "id": 1,
                        "categoria_mantenimiento_id": 1,
                        "nombre": "Concepto de mantenimiento 1",
                        "created_at": "2022-11-07 12:57:23",
                        "updated_at": "2022-11-07 12:57:23"
                    },
                    {
                        "id": 2,
                        "categoria_mantenimiento_id": 1,
                        "nombre": "Concepto de mantenimiento 2 updated",
                        "created_at": "2022-11-07 12:58:12",
                        "updated_at": "2022-11-07 15:15:44"
                    }
                ]
            }

**Error Response:**

  * **Code:** 401 Unauthorized <br />
    **Content:** 
  
          {
            "error": "Unauthenticated."
          }
