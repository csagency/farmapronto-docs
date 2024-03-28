## Listado de motivos incidencias
Regresa el listado de los motivos de incidencias

 **URL**

    /api/catalogos/motivos-incidencias-sucursales

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
                 "nombre": "Gastos generales",
                 "key": "gastos-generales",
                 "prefix": "GG",
                 "created_at": "2020-06-24 19:19:05",
                 "updated_at": "2020-06-24 19:19:05",
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
Regresa el registro de un motivo incidencia

 **URL**

    /api/catalogos/motivos-incidencias-sucursales/{ID}

 **Method:**

  `GET`
  
 **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data
     
 **URL Params**

      - includes[] = gastos
        Ejemplo URI: `api/catalogos/motivos-incidencias-sucursales/1?includes[]=gastos`

**Success Response:**

* **Code:** 200 <br />
  **Content:** 
  
      {
           "motivo": {
               "id": 1,
               "nombre": "Gastos generales",
               "key": "gastos-generales",
               "prefix": "GG",
               "created_at": "2020-06-24 19:19:05",
               "updated_at": "2020-06-24 19:19:05",
               "deleted_at": null,
               "gastos": [
                 {
                   "id": 1,
                   "motivo_id": 1,
                   "nombre": "Prueba",
                   "tiempo_vida": "1",
                   "uso_promedio": "ewdsdsf",
                   "tiempo_reparacion": null,
                   "created_at": "2020-06-24 20:11:02",
                   "updated_at": "2020-06-24 20:48:26",
                   "deleted_at": null
                 }
               ]
           }
      }

**Error Response:**

  * **Code:** 401 Unauthorized <br />
    **Content:** 
  
          {
            "error": "Unauthenticated."
          }  
