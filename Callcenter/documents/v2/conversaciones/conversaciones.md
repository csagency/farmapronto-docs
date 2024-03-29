      
## Listado de conversaciones usuario

Regresa el listado de registros de conversaciones del usuario

 **URL**

    /api-v2/conversaciones

 **Method:**

  `GET`
  
 **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json

**Success Response:**

* **Code:** 200 <br />
  **Content:** 
  
      {
      	"conversaciones": [
            {
              "id": 2,
              "pedido_id": 116763,
              "created_at": "2020-05-07 12:55:59",
              "updated_at": "2020-05-07 12:56:21",
              "deleted_at": null,
              "pivot": {
                "user_id": 25306,
                "pedido_conversacion_id": 2,
                "created_at": "2020-05-07 12:55:59",
                "updated_at": "2020-05-07 12:56:21"
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
       
       
** Crear mensaje de la conversación**
----
  Regresa la información del registro en formato json, al enviar el primer mensaje crea la conversación

 **URL**

    /api-v2/conversaciones


  **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: application/x-www-form-urlencoded

 **Method:**

  `POST`
  
 **Data Params**
    
    'pedido_id' => 'required|exists:pedidos,id',
    'tipo' => 'required|in:sucursal,cliente',
    'mensaje' => 'nullable',
    'imagen' => 'nullable',
    'lat' => 'nullable',
    'lon' => 'nullable',


 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
            "mensaje": {
                "pedido_conversacion_id": 1,
                "user_id": 25306,
                "tipo": "sucursal",
                "mensaje": "Buenas tardes",
                "imagen": null,
                "lat": null,
                "lon": null,
                "updated_at": "2020-05-07 14:15:01",
                "created_at": "2020-05-07 14:15:01",
                "id": 3
            }
        }
 **Error Response:**

  * **Code:** 422 Unprocessable Entity <br />
    **Content:** 
    
        {
              "pedido_id": [
                "El campo pedido id es obligatorio."
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
          
        
   
 
**Mensajes de la conversación**
----
  Regresa los mensajes de una conversación en específico

 **URL**

    /api-v2/conversaciones/ID

 **Method:**

  `GET`
  
  **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
     
 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
        	"pedido_conversacion": {
                "id": 1,
                "pedido_id": 116763,
                "created_at": "2020-05-07 14:12:46",
                "updated_at": "2020-05-07 14:12:46",
                "deleted_at": null,
                "mensajes": [
                  {
                    "id": 3,
                    "pedido_conversacion_id": 1,
                    "user_id": 25306,
                    "tipo": "sucursal",
                    "mensaje": "Buenas tardes",
                    "imagen": null,
                    "lat": null,
                    "lon": null,
                    "created_at": "2020-05-07 14:15:01",
                    "updated_at": "2020-05-07 14:15:01",
                    "deleted_at": null
                  },
                  {
                    "id": 4,
                    "pedido_conversacion_id": 1,
                    "user_id": 25306,
                    "tipo": "sucursal",
                    "mensaje": "Su pedido APP116763 va en camino",
                    "imagen": null,
                    "lat": null,
                    "lon": null,
                    "created_at": "2020-05-07 14:15:10",
                    "updated_at": "2020-05-07 14:15:10",
                    "deleted_at": null
                  },
                  {
                    "id": 5,
                    "pedido_conversacion_id": 1,
                    "user_id": 25306,
                    "tipo": "sucursal",
                    "mensaje": null,
                    "imagen": "uploads\/images\/conversaciones\/MP462ejAIzwSQ3ubj5FCqpPsFEc41WZ5UCE3H1vv.jpeg",
                    "lat": null,
                    "lon": null,
                    "created_at": "2020-05-07 14:15:35",
                    "updated_at": "2020-05-07 14:15:35",
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


**Mensajes de la conversación**
----
  Regresa los mensajes de una conversación en específico por Pedido ID

 **URL**

    /api-v2/conversaciones/pedido/IDpedido

 **Method:**

  `GET`
  
  **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
     
 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
        	"pedido_conversacion": {
                "id": 1,
                "pedido_id": 116763,
                "created_at": "2020-05-07 14:12:46",
                "updated_at": "2020-05-07 14:12:46",
                "deleted_at": null,
                "mensajes": [
                  {
                    "id": 3,
                    "pedido_conversacion_id": 1,
                    "user_id": 25306,
                    "tipo": "sucursal",
                    "mensaje": "Buenas tardes",
                    "imagen": null,
                    "lat": null,
                    "lon": null,
                    "created_at": "2020-05-07 14:15:01",
                    "updated_at": "2020-05-07 14:15:01",
                    "deleted_at": null
                  },
                  {
                    "id": 4,
                    "pedido_conversacion_id": 1,
                    "user_id": 25306,
                    "tipo": "sucursal",
                    "mensaje": "Su pedido APP116763 va en camino",
                    "imagen": null,
                    "lat": null,
                    "lon": null,
                    "created_at": "2020-05-07 14:15:10",
                    "updated_at": "2020-05-07 14:15:10",
                    "deleted_at": null
                  },
                  {
                    "id": 5,
                    "pedido_conversacion_id": 1,
                    "user_id": 25306,
                    "tipo": "sucursal",
                    "mensaje": null,
                    "imagen": "uploads\/images\/conversaciones\/MP462ejAIzwSQ3ubj5FCqpPsFEc41WZ5UCE3H1vv.jpeg",
                    "lat": null,
                    "lon": null,
                    "created_at": "2020-05-07 14:15:35",
                    "updated_at": "2020-05-07 14:15:35",
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


**Eliminar**
----
  Elimina una conversación completa

 **URL**

    /api-v2/conversaciones/ID

 **Method:**

  `DELETE`
    
 **Headers**
  
     Authorization: Bearer access_token
     Accept: application/json
    
    
 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
        	"pedido_conversacion": {
                "id": 1,
                "pedido_id": 116763,
                "created_at": "2020-05-07 11:36:04",
                "updated_at": "2020-05-07 11:36:04",
                "deleted_at": null,
                "mensajes": [
                  {
                    "id": 1,
                    "pedido_conversacion_id": 1,
                    "user_id": 25306,
                    "mensaje": "Hola",
                    "imagen": null,
                    "lat": null,
                    "lon": null,
                    "created_at": "2020-05-07 11:38:58",
                    "updated_at": "2020-05-07 11:38:58",
                    "deleted_at": null
                  },
                  {
                    "id": 2,
                    "pedido_conversacion_id": 1,
                    "user_id": 25306,
                    "mensaje": "Su pedido APP116763 va en camino",
                    "imagen": null,
                    "lat": null,
                    "lon": null,
                    "created_at": "2020-05-07 12:30:01",
                    "updated_at": "2020-05-07 12:30:01",
                    "deleted_at": null
                  },
                  {
                    "id": 3,
                    "pedido_conversacion_id": 1,
                    "user_id": 25306,
                    "mensaje": null,
                    "imagen": "uploads\/images\/conversaciones\/\/ohnEyitRqbFftZZrbWxmeZAdWLt27olyg2S5MNEW.jpeg",
                    "lat": null,
                    "lon": null,
                    "created_at": "2020-05-07 12:38:19",
                    "updated_at": "2020-05-07 12:38:19",
                    "deleted_at": null
                  },
                  {
                    "id": 4,
                    "pedido_conversacion_id": 1,
                    "user_id": 25306,
                    "mensaje": null,
                    "imagen": "uploads\/images\/conversaciones\/spxFE9ovFbqFLAwqx5552SHMX5DDCtULDmVYmDch.jpeg",
                    "lat": null,
                    "lon": null,
                    "created_at": "2020-05-07 12:38:41",
                    "updated_at": "2020-05-07 12:38:41",
                    "deleted_at": null
                  }
                ]
            }
        }

 **Error Responses:**

  * **Code:** 401 Unauthorized <br />
    **Content:** 
    
        {
          "error": "Unauthenticated."
        }