## Listado de gastos incidencias
Regresa el listado de los gastos de incidencias

 **URL**

    /api/catalogos/gastos-incidencias

 **Method:**

  `GET`
  
 **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data
      
       
 **Data Params**
    
    'motivo_id' => 'nullable|exists:catalogo_motivos_incidencias,id'
     
 **URL Params**

      - motivo_id = 1
        Devuelve todos los registros de tipo llantas
        Ejemplo URI: `api/catalogos/gastos-incidencias?motivo_id=1`
     

**Success Response:**

* **Code:** 200 <br />
  **Content:** 
  
      {
            "gastos": []
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
            "motivo_id": [
              "El campo motivo id es inválido."
            ]
        }
            
                    
## Detalle de gasto incidencia
Regresa el registro de un gasto de incidencia

 **URL**

    /api/catalogos/gastos-incidencias/{ID}

 **Method:**

  `GET`
  
 **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data
     
 **URL Params**

      - includes[] = motivo
        Ejemplo URI: `api/catalogos/gastos-incidencias/1?includes[]=motivo`

**Success Response:**

* **Code:** 200 <br />
  **Content:** 
  
      {
           "gasto": []
      }

**Error Response:**

  * **Code:** 401 Unauthorized <br />
    **Content:** 
  
          {
            "error": "Unauthenticated."
          }  
