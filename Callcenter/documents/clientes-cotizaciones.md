      
## Listado de cotizaciones

Regresa el listado de registros de cotizaciones

 **URL**

  /api/clientes/cotizaciones-recetas/

 **Method:**

  `GET`
  
   **URL Params**
  
    - includes[]= productos, cliente, agente, estados, estado, direccion
    - Ejemplo URI: `/api/clientes/cotizaciones-recetas?includes[]=estado` - Mostrará las cotizaciones con su último estado
    
 **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json

**Success Response:**

* **Code:** 200 <br />
  **Content:** 
  
     
        {
        	"cotizaciones": [
        		{
        			"id": 1,
        			"cliente_id": 4317,
        			"cliente_direccion_id": null,
        			"agente_id": null,
        			"activo": 0,
        			"archivo": "uploads\/images\/cotizaciones\/qvXyIHSNoiukLxmB3PMLyVBWXNoE3cYOW86IdEoN.png",
        			"urgente": 0,
        			"total": null,
        			"cant_productos": 0,
        			"created_at": "2018-10-08 11:49:25",
        			"updated_at": "2018-10-08 11:49:25",
        			"deleted_at": null
        		},
        		{
        			"id": 2,
        			"cliente_id": 4317,
        			"cliente_direccion_id": null,
        			"agente_id": null,
        			"activo": 0,
        			"archivo": "uploads\/images\/cotizaciones\/hMYxlu9Yjs4U3C94biyAg0J6bHJ1xuTo3MfO8hub.png",
        			"urgente": 0,
        			"total": null,
        			"cant_productos": 0,
        			"created_at": "2018-10-08 11:50:48",
        			"updated_at": "2018-10-08 11:50:48",
        			"deleted_at": null
        		},
        		{
        			"id": 3,
        			"cliente_id": 4317,
        			"cliente_direccion_id": null,
        			"agente_id": null,
        			"activo": 0,
        			"archivo": "uploads\/images\/cotizaciones\/kKNhNLARtWg8bfSrjdgcdwsXMInWxvi8rSRFrM75.png",
        			"urgente": 0,
        			"total": null,
        			"cant_productos": 0,
        			"created_at": "2018-10-08 11:51:23",
        			"updated_at": "2018-10-08 11:51:23",
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
       
       
** Crear nueva cotización **
----
  Regresa la información del registro en formato json

 **URL**

  /api/clientes/cotizaciones-recetas/


  **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: application/x-www-form-urlencoded

 **Method:**

  `POST`
  
  **URL Params**

  None
 
 **Data Params**
    
    'urgente' => 'nullable|boolean',
    'archivo' => 'required|image',


 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
        	"cotizacion": {
        		"agente_id": null,
        		"activo": 0,
        		"archivo": "uploads\/images\/cotizaciones\/kKNhNLARtWg8bfSrjdgcdwsXMInWxvi8rSRFrM75.png",
        		"urgente": false,
        		"cliente_id": 4317,
        		"updated_at": "2018-10-08 11:51:23",
        		"created_at": "2018-10-08 11:51:23",
        		"id": 3,
        		"estados": [
        			{
        				"id": 3,
        				"cotizacion_id": 3,
        				"estado": "pendiente",
        				"created_at": "2018-10-08 11:51:23",
        				"updated_at": "2018-10-08 11:51:23"
        			}
        		]
        	}
        }
        
        
 **Error Response:**

  * **Code:** 422 Unprocessable Entity <br />
    **Content:** 
    
        {
            "urgente": [
                "El campo urgente debe tener un valor verdadero o falso."
            ],
            "archivo": [
                "El campo archivo es obligatorio."
            ]
        }
        
  * **Code:** 401 Unauthorized <br />
      **Content:** 
      
          {
            "error": "Unauthenticated."
          }
 
 
 
 ** Actualiza cotización activo **
 ----
   Regresa la información del registro en formato json
 
  **URL**
 
   /api/clientes/cotizaciones-recetas/
 
 
   **Headers**
    
       Authorization: Bearer access_token
       Accept: application/json
       Content-Type: application/x-www-form-urlencoded
 
  **Method:**
 
   `POST`
   
   **URL Params**
 
   None
  
  **Data Params**
     
     
    'activo' => 'boolean|required',

 
 
  **Success Response:**
 
   * **Code:** 200 <br />
     **Content:** 
     
         {
         	"cotizacion": {
         		"id": 3,
         		"cliente_id": 4317,
         		"cliente_direccion_id": null,
         		"agente_id": null,
         		"activo": "1",
         		"archivo": "uploads\/images\/cotizaciones\/kKNhNLARtWg8bfSrjdgcdwsXMInWxvi8rSRFrM75.png",
         		"urgente": 0,
         		"total": null,
         		"cant_productos": 0,
         		"created_at": "2018-10-08 11:51:23",
         		"updated_at": "2018-10-08 11:54:23",
         		"deleted_at": null,
         		"estados": [
         			{
         				"id": 3,
         				"cotizacion_id": 3,
         				"estado": "pendiente",
         				"created_at": "2018-10-08 11:51:23",
         				"updated_at": "2018-10-08 11:51:23"
         			}
         		],
         		"cliente": {
         			"id": 4317,
         			"name": "Pedidos",
         			"last_name": "Prueba CS",
         			"second_last_name": "Prueba",
         			"telephone": "527773174199",
         			"email": "erick.dbrito@gmail.com",
         			"player_id": null,
         			"activo": 1,
         			"fb_id": null,
         			"slack_webhook_url": null,
         			"created_at": "2018-08-09 11:59:19",
         			"updated_at": "2018-08-09 11:59:19",
         			"deleted_at": null,
         			"last_login": null
         		},
         		"productos": []
         	}
         }
         
         
  **Error Response:**
 
   * **Code:** 422 Unprocessable Entity <br />
     **Content:** 
     
     
        {
        	"activo": [
        		"El campo activo es obligatorio."
        	]
        }
        
         
   * **Code:** 401 Unauthorized <br />
       **Content:** 
       
           {
             "error": "Unauthenticated."
           }
  
  
 
**Datos de la cotización**
----
  Regresa la información de la cotización  y sus relaciones ejemplo: productos, cliente, agente, estados, estado, direccion

 **URL**

  /api/clientes/cotizaciones-recetas/ID

 **Method:**

  `GET`
  
  **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      
  **URL Params**

    - includes[]= productos, cliente, agente, estados, estado, direccion
    Ejemplo URI: `api/clientes/cotizaciones-recetas/2?includes[]=productos&includes[]=estados&includes[]=agente&includes[]=cliente`
  

 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
            "cotizacion": {
                "id": 2,
                "cliente_id": 1417,
                "cliente_direccion_id": 17800,
                "agente_id": 1614,
                "archivo": "assets\/images\/test_cotizacion.png",
                "urgente": 0,
                "total": 1135,
                "cant_productos": 6,
                "created_at": "2018-09-09 19:19:19",
                "updated_at": "2018-09-17 18:23:35",
                "deleted_at": null,
                "productos": [
                    {
                        "id": 1,
                        "cotizacion_id": 2,
                        "lista_precio_id": 7768,
                        "precio": 55,
                        "cantidad": 2,
                        "gratis": 0,
                        "created_at": "2018-09-13 17:22:29",
                        "updated_at": "2018-09-13 17:41:47"
                    },
                    {
                        "id": 2,
                        "cotizacion_id": 2,
                        "lista_precio_id": 7447,
                        "precio": 112,
                        "cantidad": 2,
                        "gratis": 0,
                        "created_at": "2018-09-13 17:23:25",
                        "updated_at": "2018-09-13 18:44:12"
                    },
                    {
                        "id": 3,
                        "cotizacion_id": 2,
                        "lista_precio_id": 31194,
                        "precio": 400.5,
                        "cantidad": 2,
                        "gratis": 0,
                        "created_at": "2018-09-13 18:43:59",
                        "updated_at": "2018-09-17 18:23:35"
                    }
                ],
                "estados": [
                    {
                        "id": 4,
                        "cotizacion_id": 2,
                        "estado": "atendido",
                        "created_at": "2018-09-14 19:00:37",
                        "updated_at": "2018-09-14 19:00:37"
                    },
                    {
                        "id": 3,
                        "cotizacion_id": 2,
                        "estado": "recibido",
                        "created_at": "2018-09-09 19:19:19",
                        "updated_at": "2018-09-09 19:19:19"
                    }
                ],
                "agente": {
                    "id": 1614,
                    "name": "CITLALLY",
                    "last_name": "OCAMPO",
                    "second_last_name": ".",
                    "telephone": "7772082592",
                    "email": "citlally@grupofarmapronto.com",
                    "player_id": null,
                    "activo": 0,
                    "slack_webhook_url": null,
                    "created_at": "2018-05-18 12:53:32",
                    "updated_at": "2018-09-14 16:58:04",
                    "deleted_at": null,
                    "last_login": null
                },
                "cliente": {
                    "id": 1417,
                    "name": "ADELA",
                    "last_name": "MORA .",
                    "second_last_name": ".",
                    "telephone": "7773182642",
                    "email": "uno@uno.com",
                    "player_id": null,
                    "activo": 1,
                    "slack_webhook_url": null,
                    "created_at": "2018-05-11 11:49:38",
                    "updated_at": "2018-08-11 11:57:51",
                    "deleted_at": null,
                    "last_login": null
                }
            }
        }
 
 **Error Response:**

  * **Code:** 401 Unauthorized <br />
    **Content:** 
    
        {
          "error": "Unauthenticated."
        }