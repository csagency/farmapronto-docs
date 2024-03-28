## Listado de proveedores incidencias
Regresa el listado de los proveedores de incidencias

 **URL**

    /api/catalogos/proveedores-incidencias-sucursales

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
            "proveedores": [
                {
                  "id": 1,
                  "nombre": "Proveedor prueba",
                  "ciudad": "CUERNAVACA",
                  "direccion": "Prolongración Ahuatepec 307",
                  "servicios": "prueba",
                  "created_at": "2020-06-25 14:25:24",
                  "updated_at": "2020-06-25 14:29:55",
                  "deleted_at": null
                }
           ]
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

    /api/catalogos/proveedores-incidencias-sucursales/{ID}

 **Method:**

  `GET`
  
 **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data
     
 **URL Params**

      - includes[] = incidencias
        Ejemplo URI: `api/catalogos/proveedores-incidencias-sucursales/1?includes[]=incidencias`

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
