## Listado de motivos incidencias
Regresa el listado de los motivos de incidencias soporte

 **URL**

    /api/catalogos/motivos-incidencias-soporte

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
           "motivos": [
               {
                 "id": 1,
                 "nombre": "Pruebas CS",
                 "key": "pruebas-cs",
                 "prefix": "CS",
                 "created_at": "2020-08-10 16:41:18",
                 "updated_at": "2020-08-10 16:41:18",
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
          
            
                    
## Detalle de motivo incidencia
Regresa el registro de un motivo incidencia soporte

 **URL**

    /api/catalogos/motivos-incidencias-soporte/{ID}

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
           "motivo": {
               "id": 1,
               "nombre": "Pruebas CS",
               "key": "pruebas-cs",
               "prefix": "CS",
               "created_at": "2020-08-10 16:41:18",
               "updated_at": "2020-08-10 16:41:18",
               "deleted_at": null
           }
      }

**Error Response:**

  * **Code:** 401 Unauthorized <br />
    **Content:** 
  
          {
            "error": "Unauthenticated."
          }  
