**Listado de tarjetas**
----

   Listado de tarjetas del cliente
   
   **URL**
  
    /api-v2/clientes/tarjetas
  
   **Method:**
  
    `GET`
      
   **Headers**
    
       Authorization: Bearer access_token
       Accept: application/json
      
 **Success Response:**
  
   * **Code:** 200 <br />
      **Content:** 
      
          {
              "tarjetas": [
                {
                  "id": 1244,
                  "user_id": 23516,
                  "tarjeta": "debito",
                  "last4": "1234",
                  "tipo": "visa",
                  "created_at": "2020-05-04 16:46:06",
                  "updated_at": "2020-05-04 16:46:06"
                }
              ]
          }
              
  
   * **Code:** 401 Unauthorized <br />
      **Content:** 
      
          {
            "error": "Unauthenticated."
          }
          
     
      
      
**Mostrar tarjeta por id  **
----

  Tarjeta por id
   
   **URL**
  
    /api-v2/clientes/tarjetas/{IDReceta}
  
   **Method:**
  
    `GET`
      
   **Headers**
    
       Authorization: Bearer access_token
       Accept: application/json
      
 **Success Response:**
  
   * **Code:** 200 <br />
      **Content:** 
      
         {
              "tarjeta": {
                "id": 1245,
                "user_id": 23516,
                "tarjeta": "debito",
                "last4": "1234",
                "tipo": "visa",
                "created_at": "2020-05-04 16:47:55",
                "updated_at": "2020-05-04 16:47:55"
              }
         }
              
  
   * **Code:** 401 Unauthorized <br />
      **Content:** 
      
          {
            "error": "Unauthenticated."
          }
         
        
        
  
  
**Agregar tarjeta **
----

  Agregar tarjeta al usuario
  
   **URL**
  
    /api-v2/clientes/tarjetas
  
   **Method:**
  
    `POST`
      
   **Headers**
    
       Authorization: Bearer access_token
       Accept: application/json
       Content-Type: multipart/form-data
      
      
**Data Params**

 ***Required:***
    
        'tarjeta' => 'required|in:credito,debito',
        'last4' => 'required|numeric|max:9999',
        'tipo' => 'required|in:visa,mc,amex',
    
      
 **Success Response:**
  
   * **Code:** 200 <br />
      **Content:** 
      
          {
               "user": {
                 "id": 23516,
                 "name": "Abril",
                 "last_name": "Prueba",
                 "second_last_name": "V2",
                 "telephone": "527772273622",
                 "clave": "ABPRELSY",
                 "email": "jabrilmtz17@gmail.com",
                 "player_id": null,
                 "tipo_usuario": null,
                 "activo": 1,
                 "baja": 0,
                 "fb_id": null,
                 "webhook_url": null,
                 "created_at": "2020-04-20 22:22:55",
                 "updated_at": "2020-04-28 09:52:48",
                 "deleted_at": null,
                 "last_login": null
               },
               "tarjeta": {
                 "user_id": 23516,
                 "tarjeta": "debito",
                 "last4": "1234",
                 "tipo": "visa",
                 "updated_at": "2020-05-04 16:46:06",
                 "created_at": "2020-05-04 16:46:06",
                 "id": 1244
               }
          }
  
   **Error Responses:**
    * **Code:** 422 Unprocessable Entity <br />
       **Content:** 
       
          {
          	  "tarjeta": [
                "El campo tarjeta es obligatorio."
              ],
              "last4": [
                "El campo last4 es obligatorio."
              ],
              "tipo": [
                "El campo tipo es obligatorio."
              ]
          }
              
  
   * **Code:** 401 Unauthorized <br />
      **Content:** 
      
          {
            "error": "Unauthenticated."
          }
        
        

**Actualizar tarjeta **
----

  Actualiza tarjeta
  
   **URL**
  
    /api-v2/clientes/tarjetas/{IDTarjeta}
  
   **Method:**
  
    `PUT`
      
   **Headers**
    
       Authorization: Bearer access_token
       Accept: application/json
       Content-Type: multipart/form-data
      
      
**Data Params**

 ***Required:***
    
        'tarjeta' => 'in:credito,debito',
        'last4' => 'numeric|max:9999',
        'tipo' => 'in:visa,mc,amex',
    
      
 **Success Response:**
  
   * **Code:** 200 <br />
      **Content:** 
      
          {
              "user": {
                "id": 23516,
                "name": "Abril",
                "last_name": "Prueba",
                "second_last_name": "V2",
                "telephone": "527772273622",
                "clave": "ABPRELSY",
                "email": "jabrilmtz17@gmail.com",
                "player_id": null,
                "tipo_usuario": null,
                "activo": 1,
                "baja": 0,
                "fb_id": null,
                "webhook_url": null,
                "created_at": "2020-04-20 22:22:55",
                "updated_at": "2020-04-28 09:52:48",
                "deleted_at": null,
                "last_login": null
              },
              "tarjeta": {
                "id": 1245,
                "user_id": 23516,
                "tarjeta": "debito",
                "last4": "1234",
                "tipo": "visa",
                "created_at": "2020-05-04 16:47:55",
                "updated_at": "2020-05-04 16:47:55"
              }
          }
  

  
   * **Code:** 401 Unauthorized <br />
      **Content:** 
      
          {
            "error": "Unauthenticated."
          }
        
      

**Eliminar tarjeta **
----

  Eliminar tarjeta del usuario
  
   **URL**
  
    /api-v2/clientes/tarjetas/{IDTarjeta}
  
   **Method:**
  
    `DELETE`
      
   **Headers**
    
       Authorization: Bearer access_token
       Accept: application/json
       Content-Type: multipart/form-data
      
      
      
 **Success Response:**
  
   Respuesta Tarjeta : 1  = Eliminado
   Respuesta Tarjeta : 0  = No encontrado
   
  
   * **Code:** 200 <br />
      **Content:** 
      
         {
         	"user": {
                "id": 23516,
                "name": "Abril",
                "last_name": "Prueba",
                "second_last_name": "V2",
                "telephone": "527772273622",
                "clave": "ABPRELSY",
                "email": "jabrilmtz17@gmail.com",
                "player_id": null,
                "tipo_usuario": null,
                "activo": 1,
                "baja": 0,
                "fb_id": null,
                "webhook_url": null,
                "created_at": "2020-04-20 22:22:55",
                "updated_at": "2020-04-28 09:52:48",
                "deleted_at": null,
                "last_login": null
              },
              "tarjeta": 1
         }
  

  
   * **Code:** 401 Unauthorized <br />
      **Content:** 
      
          {
            "error": "Unauthenticated."
          }
        