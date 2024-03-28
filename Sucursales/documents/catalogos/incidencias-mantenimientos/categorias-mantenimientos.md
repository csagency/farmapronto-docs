## Listado de categorías de mantenimientos
Regresa el listado de categorías de mantenimientos<br>

 **URL**

    /api/catalogos/incidencias-mantenimientos/categorias-mantenimientos

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
                "categoriasMantenimientos": [
                    {
                        "id": 1,
                        "nombre": "Categoría de mantenimiento test 1 updated",
                        "created_at": "2022-11-07 09:10:29",
                        "updated_at": "2022-11-07 09:28:34"
                    }
                ]
            }

**Error Response:**

  * **Code:** 401 Unauthorized <br />
    **Content:** 
  
          {
            "error": "Unauthenticated."
          }
