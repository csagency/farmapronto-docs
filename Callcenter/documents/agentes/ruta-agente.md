      
## Regresa el id de la ultima ruta del repartidor
Regresa el id de la ultima ruta del repartidor generada en el día actual

 **URL**

  /api/agentes/getRutaActiva

 **Method:**

  `GET`
  
 **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json

**Success Response:**

* **Code:** 200 <br />
  **Content:** 
  
      {
        "last_ruta_id": 72363
      }

**Error Response:**

* **Code:** 401 Unauthorized <br />
  **Content:** 
  
      {
        "error": "Unauthenticated."
      }
       
       
