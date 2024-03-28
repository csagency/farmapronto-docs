## Sucursales a visitar
Regresa el polyline para trasar la ruta a seguir

**URL**

    api/supervisor/sucursales/visitar/{user_id}?lat=&lon=

 **Method:**

  `GET`
  
 **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data
      X-Requested-With: XMLHttpRequest
      
      
 **Data Params**
    
      
 **URL Params**
      
     - user_id":  'uid del supervisor'
     - lat":  'Es la latitus de la posición del supervisor para comenar a trazar la ruta'
     - lon":  'Es la longitud de la posición del supervisor para comenar a trazar la ruta'
             
  **Success Response:**
  
  * **Code:** 200 <br />
    **Content:** 
    
        {
          "overview_polyline": "dHrMVlDvzHw@zRiHvVlDvHxFdBdIsArFoIhJwGvWyO|NyWzG
          {AhPvGjXMHvVlDvO`LaFVlDvzHw@zRiFdBdIsArFoIhJbR?h@_Gx@_TMHvVlDvzHw@zRiB
          xAB[mGhCczVlDvzHw@zRi@qAMHvVlDvmDFdBdIsArFoVlDvzHw@zRiIhJ"
          
        }
        
  **Error Response:**
  
    * **Code:** 401 Unauthorized <br />
      **Content:** 
    
            {
              "error": "Unauthenticated."
            }
                    
     * **Code:** 406 Not Acceptable <br />
        **Content:** 
      
            {
              "error": "El usuario no cuenta con perfil de Supervisor."
            }
            
            
      * **Code:** 422 Unprocessable Entitie <br />
             **Content:** 
                
                 {
                   "message": "The given data was invalid.",
                   "errors": {
                     "lat": [
                       "La latitud es requerida."
                     ],
                     "lon": [
                       "La longitud es requerida."
                     ]
                   }
                 }       
              

## Obtener actividades pendientes en la sucursal
Regresa las actividades del supervisor que están pendientes en la sucursal

**URL**

    api/supervisor/sucursales/actividades/{sucursal_id}/{supervisor_id}

 **Method:**

  `GET`
  
 **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data
      X-Requested-With: XMLHttpRequest
      
      
 **Data Params**
    
      
 **URL Params**
      
     - user_id":  'uid del supervisor'
     - sucursal_id":  'uid de la sucursal'
             
  **Success Response:**
  
  * **Code:** 200 <br />
    **Content:** 
    
        {
          "actividades": [
            {
              "id": 113,
              "tipo_actividad_id": 16,
              "sucursal_id": 1,
              "user_id": 19,
              "inicio_at": null,
              "termino_at": null,
              "plazo_min": "2019-07-15 00:00:00",
              "plazo_max": "2019-07-28 23:59:59",
              "created_at": "2019-07-15 09:49:04",
              "updated_at": "2019-07-15 09:49:04",
              "deleted_at": null
            },
            {
              "id": 173,
              "tipo_actividad_id": 3,
              "sucursal_id": 1,
              "user_id": 19,
              "inicio_at": null,
              "termino_at": null,
              "plazo_min": "2019-07-01 00:00:00",
              "plazo_max": "2019-07-31 23:59:59",
              "created_at": "2019-07-16 09:38:32",
              "updated_at": "2019-07-16 09:38:32",
              "deleted_at": null
            },
            {
              "id": 117,
              "tipo_actividad_id": 17,
              "sucursal_id": 1,
              "user_id": 19,
              "inicio_at": null,
              "termino_at": null,
              "plazo_min": "2019-07-15 00:00:00",
              "plazo_max": "2019-08-04 23:59:59",
              "created_at": "2019-07-15 09:49:04",
              "updated_at": "2019-07-15 09:49:04",
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
                    
     * **Code:** 406 Not Acceptable <br />
        **Content:** 
      
            {
              "error": "El usuario no cuenta con perfil de Supervisor."
            }
                     
        
                     
## Comenzar una actividad
Regresa la actidad que se comenzo a realizar

**URL**

    api/supervisor/sucursal/actividad/iniciar/{actividad_id}

 **Method:**

  `GET`
  
 **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data
      X-Requested-With: XMLHttpRequest
      
      
 **Data Params**
    
      
 **URL Params**
      
     - actividad_id":  'uid de la actividad'
              
  **Success Response:**
  
  * **Code:** 200 <br />
    **Content:** 
    
        {
          "actividad": {
            "id": 113,
            "tipo_actividad_id": 16,
            "sucursal_id": 1,
            "user_id": 19,
            "inicio_at": {
              "date": "2019-07-16 12:05:37.060939",
              "timezone_type": 3,
              "timezone": "America\/Mexico_City"
            },
            "termino_at": null,
            "plazo_min": "2019-07-15 00:00:00",
            "plazo_max": "2019-07-28 23:59:59",
            "created_at": "2019-07-15 09:49:04",
            "updated_at": "2019-07-16 12:05:37",
            "deleted_at": null
          }
        }
        
  **Error Response:**
  
    * **Code:** 401 Unauthorized <br />
      **Content:** 
    
            {
              "error": "Unauthenticated."
            }
                    
     * **Code:** 406 Not Acceptable <br />
        **Content:** 
      
            {
              "error": "El usuario no cuenta con perfil de Supervisor."
            }
                     
                     
## Finalizar actividad
Regresa la actidad que se finalizo

**URL**

    api/supervisor/sucursal/actividad/terminar/{actividad_id}

 **Method:**

  `GET`
  
 **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data
      X-Requested-With: XMLHttpRequest
      
      
 **Data Params**
    
      
 **URL Params**
      
     - actividad_id":  'uid de la actividad'
              
  **Success Response:**
  
  * **Code:** 200 <br />
    **Content:** 
    
        {
          "actividad": {
            "id": 113,
            "tipo_actividad_id": 16,
            "sucursal_id": 1,
            "user_id": 19,
            "inicio_at": "2019-07-16 12:05:37",
            "termino_at": {
              "date": "2019-07-16 12:06:45.600287",
              "timezone_type": 3,
              "timezone": "America\/Mexico_City"
            },
            "plazo_min": "2019-07-15 00:00:00",
            "plazo_max": "2019-07-28 23:59:59",
            "created_at": "2019-07-15 09:49:04",
            "updated_at": "2019-07-16 12:06:45",
            "deleted_at": null
          }
        }
        
  **Error Response:**
  
    * **Code:** 401 Unauthorized <br />
      **Content:** 
    
            {
              "error": "Unauthenticated."
            }
                    
     * **Code:** 406 Not Acceptable <br />
        **Content:** 
      
            {
              "error": "El usuario no cuenta con perfil de Supervisor."
            }
                     
