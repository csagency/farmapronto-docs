## Listado de proveedores incidencias
Regresa el listado de los proveedores de incidencias

 **URL**

    /api/catalogos/proveedores-incidencias

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
            "proveedores": []
      }

**Error Response:**

  * **Code:** 401 Unauthorized <br />
    **Content:** 
  
          {
            "error": "Unauthenticated."
          }  
          
            
                    
## Detalle de proveedor incidencia
Regresa el registro de un proveedor incidencia

 **URL**

    /api/catalogos/proveedores-incidencias/{ID}

 **Method:**

  `GET`
  
 **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data
     
 **URL Params**

      - includes[] = incidencias
        Ejemplo URI: `api/catalogos/proveedores-incidencias/2?includes[]=incidencias`

**Success Response:**

* **Code:** 200 <br />
  **Content:** 
  
      {
           "proveedor": null
      }

**Error Response:**

  * **Code:** 401 Unauthorized <br />
    **Content:** 
  
          {
            "error": "Unauthenticated."
          }  
