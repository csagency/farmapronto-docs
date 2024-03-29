
## Listado de todos los pedidos con filtro por estatus
Regresa el listado de todos los pedidos que estan disponibles

 **URL**

  /api/sucursales/pedidos

 **Method:**

  `GET`
  
 **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json


**Success Response:**

* **Code:** 200 <br />
  **Content:** 
  
      {
      	"pedidos": [
      		{
      			"id": 40,
      			"user_id": 4,
      			"cliente_direccion_id": 42,
      			"created_at": "2017-06-28 12:37:41",
      			"updated_at": "2017-06-28 12:37:41",
      			"estado": {
      				"id": 2,
      				"pedido_id": 40,
      				"paso": "aceptado",
      				"created_at": "2017-06-28 12:37:42",
      				"updated_at": "2017-06-28 12:37:42"
      			}
      		},
      		{
      			"id": 42,
      			"user_id": 4,
      			"cliente_direccion_id": 44,
      			"created_at": "2017-06-30 11:01:37",
      			"updated_at": "2017-06-30 11:01:37",
      			"estado": {
      				"id": 13,
      				"pedido_id": 42,
      				"paso": "recibido",
      				"created_at": "2017-06-30 11:01:37",
      				"updated_at": "2017-06-30 11:01:37"
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
       
      
      
## Listado de pedidos pendientes o disponibles
Regresa el listado de todos los pedidos que estan disponibles

 **URL**

  /api/sucursales/pedidos/pendientes

 **Method:**

  `GET`
  
 **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json


**Success Response:**

* **Code:** 200 <br />
  **Content:** 
  
      {
      	"pedidos": [
      		{
      			"id": 19,
      			"user_id": 16,
      			"cliente_direccion_id": 21,
      			"created_at": "2017-06-22 13:00:15",
      			"updated_at": "2017-06-22 13:00:15"
      		},
      		{
      			"id": 20,
      			"user_id": 16,
      			"cliente_direccion_id": 22,
      			"created_at": "2017-06-22 13:07:58",
      			"updated_at": "2017-06-22 13:07:58"
      		},
      		{
      			"id": 23,
      			"user_id": 16,
      			"cliente_direccion_id": 25,
      			"created_at": "2017-06-22 13:14:04",
      			"updated_at": "2017-06-22 13:14:04"
      		},
      		{
      			"id": 24,
      			"user_id": 16,
      			"cliente_direccion_id": 26,
      			"created_at": "2017-06-22 13:15:19",
      			"updated_at": "2017-06-22 13:15:19"
      		}...
      	   ]
        }

**Error Response:**

* **Code:** 401 Unauthorized <br />
  **Content:** 
  
      {
        "error": "Unauthenticated."
      }
       
 
  
**Datos del pedido**
----
  Regresa la información a detalle de un pedido y sus relaciones

 **URL**

  /api/sucursales/pedidos/ID

 **Method:**

  `GET`
  
  **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data
      
  **URL Params**

  - includes[]=cliente, direccion, estado, evidencias, pedidoProductos.listaPrecio.producto, envio.agente   <br><br>
  Ejemplo URI: `api/sucursales/pedidos/1?includes[]=cliente&includes[]=direccion&includes[]=pedidoProductos.listaPrecio.producto&includes[]=estado&includes[]=evidencias&includes[]=envio.agente`
  

 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        { 
          "pedido": [
            {
              "id": 1,
              "user_id": 2,
              "cliente_direccion_id": 1,
              "monto": 100,
              "delivery_at": "2017-06-06 00:00:00",
              "created_at": null,
              "updated_at": null,
              "cliente": {
                "id": 2,
                "name": "Sucursal",
                "last_name": "Farmapronto",
                "second_last_name": " test",
                "telephone": "7777777776",
                "email": "sucursal@grupofarmapronto.com",
                "created_at": "2017-05-29 16:30:59",
                "updated_at": "2017-05-29 16:30:59",
                "deleted_at": null
              },
              "direccion": {
                "id": 1,
                "user_id": 2,
                "estado_id": 9,
                "municipio_id": 84,
                "colonia_id": 1,
                "calle": "vgvf",
                "numero_interior": "12",
                "numero_exterior": null,
                "codigo_postal": 62220,
                "tipo": "casa",
                "created_at": null,
                "updated_at": null
              },
              "pedido_productos": [
                {
                  "id": 1,
                  "lista_precio_id": 1,
                  "pedido_id": 1,
                  "precio": 10,
                  "cantidad": 10,
                  "created_at": null,
                  "updated_at": null,
                  "lista_precio": {
                    "id": 1,
                    "producto_id": 1,
                    "ciudad_id": 1,
                    "precio": 10,
                    "created_at": null,
                    "updated_at": null,
                    "producto": {
                      "id": 1,
                      "farmapronto_id": "1",
                      "sku": "736085400892",
                      "nombre": "3-A OFTENO 1MG GTS 5ML",
                      "descripcion": "3-A OFTENO 1MG GTS 5ML",
                      "categoria_id": 6,
                      "laboratorio": "Bayer",
                      "receta": 0,
                      "destacado": 0,
                      "archivo": null,
                      "created_at": "2017-05-29 16:32:54",
                      "updated_at": "2017-05-29 16:32:54",
                      "activo": 1
                    }
                  }
                }
              ],
              "estado": [
                {
                  "id": 1,
                  "pedido_id": 1,
                  "paso": "enviado",
                  "created_at": "2017-05-30 11:45:58",
                  "updated_at": "2017-05-30 11:45:58"
                },
                {
                  "id": 2,
                  "pedido_id": 1,
                  "paso": "entregado",
                  "created_at": "2017-05-30 11:54:48",
                  "updated_at": "2017-05-30 11:54:48"
                }
              ],
              "evidencias": [
                {
                  "id": 1,
                  "pedido_id": 1,
                  "tipo": "receta",
                  "archivo": "/urldelarchivo",
                  "created_at": "2017-05-30 11:54:48",
                  "updated_at": "2017-05-30 11:54:48"
                }
              ],
              "envio": {
                "id": 1,
                "pedido_id": 1,
                "sucursal_id": 1,
                "agente_id": 3,
                "puntaje": 50,
                "created_at": "2017-05-29 19:17:18",
                "updated_at": "2017-05-29 19:17:18",
                "agente": {
                  "id": 3,
                  "user_id": 7,
                  "colonia_id": 1,
                  "numero_control": "qwer12",
                  "estatus": null,
                  "created_at": "2017-05-29 19:08:31",
                  "updated_at": "2017-05-29 19:25:50",
                  "deleted_at": null,
                  "lat": -99.1,
                  "long": 83.29,
                  "imagen": null,
                  "imagen_path": null
                }
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

**Verificar y Aceptar pedido**
----
  Acepta un pedido pendiente

 **URL**

  /api/sucursales/pedidos/pendiente

 **Method:**

  `POST`
    
 **Headers**
 
    Authorization: Bearer access_token
    Accept: application/json
    Content-Type: application/x-www-form-urlencoded
    
    
**Data Params**
    
    `id=PedidoID`
    
 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
        	"pedido": {
        		"id": 342,
        		"user_id": 134,
        		"cliente_direccion_id": 305,
        		"asistencia": 0,
        		"folio": null,
        		"created_at": "2017-08-17 18:33:50",
        		"updated_at": "2017-08-17 18:33:50",
        		"envio": {
        			"id": 173,
        			"pedido_id": 342,
        			"sucursal_id": 23,
        			"agente_id": null,
        			"codigo_verificacion": "7666",
        			"aceptado": 0,
        			"created_at": "2017-08-17 18:45:10",
        			"updated_at": "2017-08-17 18:45:10",
        			"delivery_at": null,
        			"agente": null
        		},
        		"estado": {
        			"id": 1011,
        			"pedido_id": 342,
        			"paso": "recibido",
        			"created_at": "2017-08-17 18:33:51",
        			"updated_at": "2017-08-17 18:33:51"
        		},
        		"cliente": {
        			"id": 134,
        			"name": "Erick",
        			"last_name": "Daniel",
        			"second_last_name": "Brito",
        			"telephone": "527773274199",
        			"email": "erick.dbrito@gmail.com",
        			"player_id": "262b4034-bd45-4e4e-b020-7b54b3fd5e81",
        			"activo": 0,
        			"slack_webhook_url": null,
        			"created_at": "2017-07-18 10:43:09",
        			"updated_at": "2017-07-28 10:37:19",
        			"deleted_at": null
        		},
        		"agentes": [
        			{
        				"id": 2,
        				"user_id": 124,
        				"numero_control": "00000",
        				"estatus": 1,
        				"created_at": "2017-06-22 18:25:32",
        				"updated_at": "2017-08-17 17:55:11",
        				"deleted_at": null,
        				"lat": "18.9361389",
        				"lon": "-99.230313",
        				"imagen": null,
        				"imagen_path": null,
        				"vehiculo_id": null,
        				"pivot": {
        					"pedido_id": 342,
        					"agente_id": 2,
        					"aceptado": 0
        				}
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
          
                  
  * **Code:** 400 Unauthorized <br />
        **Content:** 
        
            {
              "error": "Agentes no disponibles"
            }
            
            
  * **Code:** 422 Unauthorized <br />
        **Content:** 
        
            {
              "error": "El pedido ya ha sido aceptado por otra sucursal."
            }


**Rechazar pedido**
----
  Acepta un pedido pendiente

 **URL**

  /api/sucursales/pedidos/pendiente/rechazar

 **Method:**

  `POST`
    
 **Headers**
 
    Authorization: Bearer access_token
    Accept: application/json
    Content-Type: application/x-www-form-urlencoded
    
    
**Data Params**
    
    `id=required|exists:pedidos,id`
    `rechazar=required|boolean`
    
 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
        	"pedido": {
        		"id": 130,
        		"user_id": 4,
        		"cliente_direccion_id": 249,
        		"created_at": "2017-07-14 13:30:51",
        		"updated_at": "2017-07-14 13:30:51"
        	},
        	"pedido_sucursal": {
        		"id": 23,
        		"user_id": 73,
        		"codigo": "25",
        		"nombre": "ZZ",
        		"telefono": null,
        		"colonia_id": 34739,
        		"municipio_id": 502,
        		"estado_id": 17,
        		"direccion": "NUEVA INGLATERRA",
        		"direccion_numero": "500",
        		"codigo_postal": "62240",
        		"lon": "-99.234965",
        		"lat": "18.9517001",
        		"created_at": "2017-03-16 17:50:05",
        		"updated_at": "2017-07-05 13:45:03",
        		"pivot": {
        			"pedido_id": 130,
        			"sucursal_id": 23,
        			"rechazado": 1
        		}
        	}
        }

 **Error Response:**
  
  * **Code:** 401 Unauthorized <br />
      **Content:** 
      
          {
            "error": "Unauthenticated."
          }
          
   * **Code:** 422 Unproccesable <br />
        **Content:** 
        
            {
            	"id": [
            		"El campo id es obligatorio."
            	],
            	"rechazar": [
            		"El campo rechazar es obligatorio."
            	]
            }


**Finalizar pedido**
----
  Finaliza un pedido por medio del ID, validando el método de pago y si la evidencia de la entrega ha sido almacenada

 **URL**

  /api/sucursales/pedidos/IDpedido

 **Method:**

  `PUT`
    
 **Headers**
 
    Authorization: Bearer access_token
    Accept: application/json
    Content-Type: multipart/form-data
    
**Data Params**
    
    `estado=[optional|in:pagado]`
    
 **Example**
   
      'estado' = "pagado"
    
 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
          "pedidoFinalizado": {
              "id": 2,
              "pedido_id": 1,
              "paso": "finalizado",
              "created_at": "2017-05-30 11:54:48",
              "updated_at": "2017-06-08 17:30:58"
          }
        }

 **Error Response:**

  * **Code:** 422 Unprocessable Entity <br />
      **Content:** 
      
          {   
            "paso": [
              "El campo estado es inválido."
            ]
          }
          
  * **Code:** 401 Unauthorized <br />
      **Content:** 
      
          {
            "error": "Unauthenticated."
          }


     
  ** Asignar calificacion al repartidor  Agente **
  ----
    Asigna calificacion al repartidor
  
   **URL**
  
    /api/sucursales/pedidos/{IdPedido}/calificaciones
  
   **Method:**
  
    `POST`
      
   **Headers**
    
       Authorization: Bearer access_token
       Accept: application/json
       Content-Type: application/x-www-form-urlencoded
      
      
**Data Params**

 ***Required:***
    
    'evaluado_id' => 'required|exists:users,id',
    'calificacion' => 'required|in:1,2,3,4,5',
    'comentario' => 'nullable|max:255',
    
      
 **Success Response:**
  
   * **Code:** 200 <br />
      **Content:** 
      
          {
          	"pedido": {
          		"id": 38,
          		"user_id": 4,
          		"cliente_direccion_id": 40,
          		"created_at": "2017-06-23 11:49:19",
          		"updated_at": "2017-06-23 11:49:19"
          	},
          	"calificacion": {
          		"evaluado_id": "4",
          		"calificacion": "3",
          		"comentario": "Comentario",
          		"user_id": 2,
          		"pedido_id": 38,
          		"updated_at": "2017-06-23 12:19:29",
          		"created_at": "2017-06-23 12:19:29",
          		"id": 2
          	}
          }
  
   **Error Responses:**
    * **Code:** 422 Unprocessable Entity <br />
       **Content:** 
       
          {
          	"evaluado_id": [
          		"El campo evaluado id es obligatorio."
          	],
          	"calificacion": [
          		"El campo calificacion es obligatorio."
          	]
          }
              
  
   * **Code:** 401 Unauthorized <br />
      **Content:** 
      
          {
            "error": "Unauthenticated."
          }
          

     
  ** Usuarios Agentes **
  ----
    Lista los usuarios agentes 
  
   **URL**
  
    /api/sucursales/agentes
  
   **Method:**
  
    `GET`
      
   **Headers**
    
       Authorization: Bearer access_token
       Accept: application/json
      
      
 **Success Response:**
  
   * **Code:** 200 <br />
      **Content:** 
      
          {
          	"usuarios": [
          		{
          			"id": 3,
          			"name": "Agente",
          			"last_name": "Farmapronto",
          			"second_last_name": "test",
          			"telephone": "7777777779",
          			"email": "agente@grupofarmapronto.com",
          			"player_id": "f4c9ba4f-4a15-421f-9801-c8646bea915c",
          			"created_at": "2017-03-16 17:47:54",
          			"updated_at": "2017-03-16 17:47:54",
          			"deleted_at": null,
          			"agente_perfil": {
          				"id": 1,
          				"user_id": 3,
          				"colonia_id": null,
          				"numero_control": "",
          				"estatus": "No disponible",
          				"created_at": null,
          				"updated_at": "2017-06-28 13:11:03",
          				"deleted_at": null,
          				"lat": "18.9816681",
          				"lon": "-99.2465937",
          				"imagen": null,
          				"imagen_path": null
          			}
          		}
          	]
          }
  
   * **Code:** 401 Unauthorized <br />
      **Content:** 
      
          {
            "error": "Unauthenticated."
          }
          
          

     
  ** Mostrar Agentes con pedidos pendienes **
  ----
    Lista los usuarios agentes  con pedidos pendientes que tengan un delivery_at igual a null <br>
    Muestra si tiene evidencias con estatus = pendiente y si tiene pago pendiente con referencia igual a null
  
   **URL**
  
    /api/sucursales/agentes/3
  
   **Method:**
  
    `GET`
      
   **Headers**
    
       Authorization: Bearer access_token
       Accept: application/json
      
      
 **Success Response:**
  
   * **Code:** 200 <br />
      **Content:** 
      
          {
          	"user": {
          		"id": 3,
          		"name": "Agente",
          		"last_name": "Farmapronto",
          		"second_last_name": "test",
          		"telephone": "7777777779",
          		"email": "agente@grupofarmapronto.com",
          		"player_id": "f4c9ba4f-4a15-421f-9801-c8646bea915c",
          		"created_at": "2017-03-16 17:47:54",
          		"updated_at": "2017-03-16 17:47:54",
          		"deleted_at": null,
          		"agente_perfil": {
          			"id": 1,
          			"user_id": 3,
          			"colonia_id": null,
          			"numero_control": "",
          			"estatus": "No disponible",
          			"created_at": null,
          			"updated_at": "2017-06-28 13:11:03",
          			"deleted_at": null,
          			"lat": "18.9816681",
          			"lon": "-99.2465937",
          			"imagen": null,
          			"imagen_path": null,
          			"envio": [
          				{
          					"id": 15,
          					"pedido_id": 41,
          					"sucursal_id": 24,
          					"agente_id": 1,
          					"codigo_verificacion": "9357",
          					"aceptado": 1,
          					"created_at": "2017-06-28 12:54:58",
          					"updated_at": "2017-06-28 13:23:41",
          					"delivery_at": null,
          					"pedido": {
          						"id": 41,
          						"user_id": 4,
          						"cliente_direccion_id": 43,
          						"created_at": "2017-06-28 12:40:48",
          						"updated_at": "2017-06-28 12:40:48",
                                "folio": "APP0000254",
          						"estado": {
          							"id": 12,
          							"pedido_id": 41,
          							"paso": "entregado",
          							"created_at": "2017-06-29 13:57:04",
          							"updated_at": "2017-06-29 13:57:04"
          						},
          						"evidencia": null,
          						"pago": null
          					}
          				}
          			]
          		}
          	}
          }
  
   * **Code:** 401 Unauthorized <br />
      **Content:** 
      
          {
            "error": "Unauthenticated."
          }
          
          
          
**Añadir productos en stock de sucursal sobre un pedido **
  ----
    Añade los productos que tiene en stock una sucursal sobre un pedido,
  
   **URL**
  
    /api/sucursales/pedidos/{IDPedido}/productos/stock
  
   **Method:**
  
    `POST`
      
   **Headers**
    
       Authorization: Bearer access_token
       Accept: application/json
       Content-Type: application/x-www-form-urlencoded
      
      
 **Success Response:**
  
   * **Code:** 200 <br />
      **Content:** 
      
          {
          	"pedido": {
          		"id": 129,
          		"user_id": 4,
          		"cliente_direccion_id": 248,
          		"created_at": "2017-07-14 13:27:48",
          		"updated_at": "2017-07-14 13:27:48",
          		"sucursal_productos": [
          			{
          				"id": 1,
          				"pedido_id": 129,
          				"producto_id": 12,
          				"sucursal_id": 23,
          				"cantidad": 2,
          				"created_at": "2017-07-19 18:58:11",
          				"updated_at": "2017-07-19 18:58:11"
          			},
          			{
          				"id": 2,
          				"pedido_id": 129,
          				"producto_id": 14,
          				"sucursal_id": 23,
          				"cantidad": 2,
          				"created_at": "2017-07-19 19:11:22",
          				"updated_at": "2017-07-19 19:11:22"
          			},
          			{
          				"id": 3,
          				"pedido_id": 129,
          				"producto_id": 15,
          				"sucursal_id": 23,
          				"cantidad": 2,
          				"created_at": "2017-07-19 19:18:06",
          				"updated_at": "2017-07-19 19:18:06"
          			}
          		]
          	}
          }
  
   * **Code:** 400 Bad Request <br />
      **Content:** 
      
          {
          	"message": "Producto ya añadido al pedido"
          }
          
   
** Añade motivo y actualiza estatus de la receta del pedido **
  ----
    Aceptar o rechazar receta con motivo
  
   **URL**
  
    /api/sucursales/pedidos/{IDPedido}/recetas/{idReceta}
  
   **Method:**
  
    `PUT`
      
  **Data Params**
      
    'motivo' => 'max:255',
    'aceptado' => 'boolean',
    
   **Headers**
    
       Authorization: Bearer access_token
       Accept: application/json
       Content-Type: application/x-www-form-urlencoded
      
      
 **Success Response:**
  
   * **Code:** 200 <br />
      **Content:** 
      
          {
          	"pedido": {
          		"id": 129,
          		"user_id": 4,
          		"cliente_direccion_id": 248,
          		"created_at": "2017-07-14 13:27:48",
          		"updated_at": "2017-07-14 13:27:48",
                "folio": "APP0000254",
               
          	},
          	"receta": {
                "id": 20,
                "pedido_id": null,
                "producto_id": 1,
                "user_id": 131,
                "tipo": "receta",
                "archivo": "http:\/\/farmapronto.dev\/uploads\/recetas\/E1CcjpZzkfQOk9f27JTzhAbnppE2ckr0CTzrZH1I.png",
                "created_at": "2017-07-20 13:03:38",
                "updated_at": "2017-07-20 13:03:38",
                "fisico": 0,
                "estatus": "pendiente",
                "motivo": "Receta incorrecta",
                "aceptado": 1,
            }
          }
  