      
## Listado de planes de lealtad del cliente
Regresa el listado de todos los planes de lealtad del cliente

 **URL**

  api/clientes/planes-lealtad?includes[]=tipo_tarjeta

 **Method:**

  `GET`
  
 **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data

**URL Params**

  - includes[]=cliente, laboratorio  <br><br>
  Ejemplo URI: `api/clientes/planes-lealtad`
  


**Success Response:**

* **Code:** 200 <br />
  **Content:** 
  
  
      {
        "planesLealtad": [
          {
            "id": 1,
            "user_id": 8843,
            "folio": null,
            "descripcion": null,
            "numero_tarjeta": "1234551231",
            "vigente": 1,
            "expiracion": null,
            "created_at": "2019-11-11 17:37:37",
            "updated_at": "2019-11-11 17:37:37",
            "deleted_at": null,
            "tipo_tarjeta_id": 1,
            "nip": null,
            "tipo_tarjeta": {
              "id": 1,
              "nombre": "MTCL_KMC",
              "descripcion": "TARJETA FARMAPRONTO",
              "created_at": "2019-11-11 17:19:59",
              "updated_at": "2019-11-11 17:19:59"
            }
          }
        ]
      }
      

**Error Response:**

* **Code:** 401 Unauthorized <br />
  **Content:** 
  
      {
         "error": "Unauthenticated."
      }
       
       
**Registro de nuevo plan de lealtad**
----
  Regresa la información del registro en formato json

 **URL**

  /api/clientes/planes-lealtad/

 **Method:**

  `POST`
  
  **URL Params**

  None
 
 **Data Params**
    
    tipo_tarjeta_id=[required
    descripcion=[nullable]
    numero_tarjeta=[required]
    vigente=[nullable]
    expiracion=[nullable]
 

 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
            "planLealtad": {
              "tipo_tarjeta_id": "1",
              "descripcion": "Plan anual",
              "numero_tarjeta": "1234567890123456",
              "expiracion": "2018-05-20",
              "user_id": 4,
              "updated_at": "2017-05-18 13:02:11",
              "created_at": "2017-05-18 13:02:11",
              "id": 1
            }
        }
 
 **Error Response:**

  * **Code:** 422 Unprocessable Entity <br />
    **Content:** 
    
        {
            "tipo_tarjeta_id": [
              "El campo tipo_tarjeta_id  es inválido."
            ],
            "numero_tarjeta": [
              "El campo numero tarjeta es obligatorio."
            ]
        }
        
  * **Code:** 401 Unauthorized <br />
      **Content:** 
      
          {
            "error": "Unauthenticated."
          }
 
**Datos del plan de lealtad**
----
  Regresa la información de un plan de lealtad del cliente y sus relaciones ejemplo: cliente, laboratorio

 **URL**

  /api/clientes/planes-lealtad/ID

 **Method:**

  `GET`
  
  **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data
      
  **URL Params**

  - includes[]=cliente, laboratorio <br><br>
  Ejemplo URI: `api/clientes/planes-lealtad/1?includes[]=cliente&includes[]=laboratorio`
  

 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 

        { 
            "planLealtad": {
              "id": 1,
              "user_id": 4,
              "descripcion": "Plan anual",
              "numero_tarjeta": "1234567890123456",
              "expiracion": "2018-05-20",
              "cliente": {
                "id": 4,
                "name": "Cliente",
                "last_name": "CS",
                "second_last_name": "Group",
                "telephone": "7777777778",
                "email": "test@csgroup.mx",
                "created_at": "2017-05-18 11:29:10",
                "updated_at": "2017-05-18 11:29:10",
                "deleted_at": null
              },
              "tipo_tarjeta": {
                "id": 1,
                "nombre": "MTCL_KMC",
                "descripcion": "MTCL_KMC",
                "created_at": "2017-04-04 00:00:00",
                "updated_at": null,
              }
            }
        }
 
 **Error Response:**

  * **Code:** 401 Unauthorized <br />
    **Content:** 
    
        {
          "error": "Unauthenticated."
        }



**Actualización de plan de lealtad**
----
  Actualiza la información de un plan de lealtad del cliente

 **URL**

  /api/clientes/planes-lealtad/ID

 **Method:**

  `PUT`
    
 **Headers**
 
    Authorization: Bearer access_token
    Accept: application/json
    Content-Type: multipart/form-data
    
**Data Params**
    
    tipo_tarjeta_id=[required]
    descripcion=[nullable]
    numero_tarjeta=[required]
    vigente=[nullable]
    expiracion=[nullable]
 

 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        
        
            {
                "planLealtad": {
                  "tipo_tarjeta_id": "1",
                  "descripcion": "Plan anual",
                  "numero_tarjeta": "1234567890123456",
                  "expiracion": "2018-05-20",
                  "user_id": 4,
                  "updated_at": "2017-05-18 13:02:11",
                  "created_at": "2017-05-18 13:02:11",
                  "id": 1
                }
            }
                

 **Error Response:**

  * **Code:** 422 Unprocessable Entity <br />
      **Content:** 
      
          
          {
              "laboratorio_id": [
                "El campo laboratorio id es inválido."
              ],
              "folio": [
                "El campo folio es obligatorio."
              ],
              "numero_tarjeta": [
                "El campo numero tarjeta es obligatorio."
              ],
              "vigente": [
                "El campo vigente es obligatorio."
              ],
              "expiracion": [
                "El campo expiracion es obligatorio."
              ]
          }
          
          
  * **Code:** 401 Unauthorized <br />
      **Content:** 
      
          {
            "error": "Unauthenticated."
          }


**Eliminar plan de lealtad**
----
  Elimina un plan de lealtad del cliente

 **URL**

  /api/clientes/planes-lealtad/ID

 **Method:**

  `DELETE`
    
 **Headers**
  
     Authorization: Bearer access_token
     Accept: application/json
     Content-Type: multipart/form-data
    
    
 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
            "planesLealtad": null
        }

 **Error Responses:**

  * **Code:** 401 Unauthorized <br />
    **Content:** 
    
        {
            "error": "Unauthenticated."
        }