## Obtener los últimos insumos registrados en la sucursal
Regresa el listado de los últimos registros de inventario de la sucursal echos 
por el encargado o auxiliar

 **URL**

    api/insumos/ultimos/registrados/sucursal/{id_sucursal}
    
 **Method:**

  `GET`
  
 **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data
      X-Requested-With: XMLHttpRequest
      
 **Data Params**
    
     
 **URL Params**

       - sucursal_id":  'uid de la sucursal'
       
**Success Response:**

* **Code:** 200 <br />
  **Content:** 
  
      {
        "historial_id": 5,
        "sucursal_id": "3",
        "comentarios": "null",
        "validated_at": "null",
        "has_error": 1,
        "insumos_sucursal": [
          {
            "id": 17,
            "historial_inventario_id": 5,
            "sucursal_inventario_id": 5,
            "pasado": 0,
            "actual": 0,
            "error": 1,
            "tipo_error": "Agotado",
            "created_at": "2019-07-10 13:08:39",
            "updated_at": "2019-07-10 13:08:39"
          },
          {
            "id": 18,
            "historial_inventario_id": 5,
            "sucursal_inventario_id": 9,
            "pasado": 4,
            "actual": 4,
            "error": 0,
            "tipo_error": null,
            "created_at": "2019-07-10 13:08:39",
            "updated_at": "2019-07-10 13:08:39"
          },
          {
            "id": 19,
            "historial_inventario_id": 5,
            "sucursal_inventario_id": 10,
            "pasado": 2,
            "actual": 2,
            "error": 0,
            "tipo_error": null,
            "created_at": "2019-07-10 13:08:39",
            "updated_at": "2019-07-10 13:08:39"
          },
          {
            "id": 20,
            "historial_inventario_id": 5,
            "sucursal_inventario_id": 11,
            "pasado": 2,
            "actual": 2,
            "error": 0,
            "tipo_error": null,
            "created_at": "2019-07-10 13:08:39",
            "updated_at": "2019-07-10 13:08:39"
          }
        ]
      }

**Error Response:**

  * **Code:** 401 Unauthorized <br />
    **Content:** 
  
          {
            "error": "Unauthenticated."
          }
          
          
## Validar inventario
Regresa que se valido el inventario

 **URL**

    api/insumos/validar/ultimos/registrados/sucursal
    
 **Method:**

  `POST`
  
 **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data
      X-Requested-With: XMLHttpRequest
      
 **Data Params**

    - historial_id: 'Es el uid del historial del inventario'
    - comentarios: 'Son los comentarios realizados por el supervisor' (puede ser nullo) 
 
 **URL Params**


**Success Response:**

* **Code:** 200 <br />
  **Content:** 
  
      {
        "mensaje": "Inventario Validado"
      }

**Error Response:**

  * **Code:** 401 Unauthorized <br />
    **Content:** 
  
          {
            "error": "Unauthenticated."
          }
          
  * **Code:** 422 Unprocessable Entity <br />
    **Content:** 
    
        {
          "message": "The given data was invalid.",
          "errors": {
            "historial_id": [
              "El id del historial es requerido."
            ]
          }
        }
        
