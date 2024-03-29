      
## Listado de pedidos del agente
Regresa el listado de todos los pedidos del realizados por el agente

 **URL**

  /api/agentes/pedidos/

 **Method:**

  `GET`
  
 **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json

**URL Params**

  - includes[]=pedido, sucursal, agente  <br><br>
  Ejemplo URI: `api/agentes/pedidos`
  


**Filtros por estatus**

  - estatus=aceptado,en transito, llegando,entregado,finalizado  <br><br>
  - activo=true  <br><br>
  Ejemplo URI: `api/agentes/pedidos?estatus=aceptado`<br>
  Ejemplo URI: `api/agentes/pedidos?activo=true`
  

**Success Response:**

* **Code:** 200 <br />
  **Content:** 
  
      {
      	"pedidos": [
      		{
      			"id": 38,
      			"user_id": 4,
      			"cliente_direccion_id": 40,
                "asistencia": 0,
      			"folio": "APP0000254",
      			"created_at": "2017-06-23 11:49:19",
      			"updated_at": "2017-06-23 11:49:19",
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
                    "id": 1012,
                    "pedido_id": 342,
                    "paso": "aceptado",
                    "created_at": "2017-08-17 18:45:10",
                    "updated_at": "2017-08-17 18:45:10"
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
       
       
## Listado de pedidos que puede aceptar
Regresa el listado de todos los pedidos pendientes que puede aceptar

 **URL**

  /api/agentes/pedidos/pendientes

 **Method:**

  `GET`
  
 **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json

**URL Params**

  - includes[]=pedido, sucursal, agente  <br><br>
  Ejemplo URI: `api/agentes/pedidos`
  
  
**Success Response:**

* **Code:** 200 <br />
  **Content:** 
  
      {
      	"pedidos": [
      		{
      			"id": 23,
      			"user_id": 122,
      			"cliente_direccion_id": 308,
      			"asistencia": 0,
      			"folio": "APP0000023",
      			"created_at": "2017-09-08 17:56:05",
      			"updated_at": "2017-09-08 17:56:05",
      			"codigo_confirmacion": null,
      			"cliente": {
      				"id": 122,
      				"name": "Aldo",
      				"last_name": "Albert",
      				"second_last_name": "Carrillo",
      				"telephone": "527771491262",
      				"email": "aldo@csgroup.mx",
      				"player_id": "d280c7bd-c017-419e-981b-1fee0b526427",
      				"activo": 1,
      				"slack_webhook_url": null,
      				"created_at": "2017-09-05 10:49:11",
      				"updated_at": "2017-09-07 18:36:47",
      				"deleted_at": null
      			},
      			"agente": [],
      			"estado": {
      				"id": 81,
      				"pedido_id": 23,
      				"paso": "entregado",
      				"created_at": "2017-09-08 17:57:20",
      				"updated_at": "2017-09-08 17:57:20"
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
       
  
**Datos del pedido**
----
  Regresa la información de una pedido a cargo del agente y sus relaciones

 **URL**

  /api/agentes/pedidos/ID

 **Method:**

  `GET`
  
  **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data
      
  **URL Params**

  - includes[]=envio, envio.agente, cliente  <br><br>
  Ejemplo URI: `api/agentes/pedidos/1?includes[]=envio&includes[]=envio.agente&includes[]=cliente`
  

 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
        	"pedidos": [
        		{
        			"id": 1,
        			"user_id": 4,
        			"cliente_direccion_id": 1,
        			"folio": "APP0000254",
        			"created_at": "2017-06-22 18:12:55",
        			"updated_at": "2017-06-22 18:12:55",
        			"envio": {
        				"id": 1,
        				"pedido_id": 1,
        				"sucursal_id": 22,
        				"agente_id": 1,
        				"codigo_verificacion": "5119",
        				"puntaje": 0,
        				"created_at": "2017-06-22 18:15:33",
        				"updated_at": "2017-06-22 18:18:45",
        				"agente": {
        					"id": 1,
        					"user_id": 3,
        					"colonia_id": null,
        					"numero_control": "123213",
        					"estatus": "Recoger pedido",
        					"created_at": null,
        					"updated_at": "2017-06-22 18:18:45",
        					"deleted_at": null,
        					"lat": "18.9776027",
        					"lon": "-99.2347359",
        					"imagen": null,
        					"imagen_path": null
        				}
        			},
        			"cliente": {
        				"id": 4,
        				"name": "Cliente",
        				"last_name": "CS",
        				"second_last_name": "Group",
        				"telephone": "7777777778",
        				"email": "test@csgroup.mx",
        				"created_at": "2017-03-28 18:38:38",
        				"updated_at": "2017-03-28 18:38:38",
        				"deleted_at": null
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



**Actualización de pedido**
----
  Actualiza la información de envio de un pedido

 **URL**

  /api/agentes/pedidos/IDpedido

 **Method:**

  `PUT`
    
 **Headers**
 
    Authorization: Bearer access_token
    Accept: application/json
    Content-Type: multipart/form-data
    
**Data Params**

 ***Required:***
    
    `paso=[required|in:recibido,aceptado,en transito,llegando,entregado]`
    
 **Example**
   
      'paso' => 'in:aceptado,aceptado agente,embarcado,en transito,entregado,llegando,finalizado',
      'pedido_id' => 'exists:pedidos,id',
      'estimated_at' => '',
      'delivery_at' => 'date',
      'lat' => '',
      'lon' => '',
      'vehiculo_id' => 'required_with:km',
      'km' => 'nullable',
      'bateria' => 'nullable',
    
 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
        	"pedido": {
        		"id": 38,
        		"user_id": 4,
        		"cliente_direccion_id": 40,
        		"folio": "APP0000254",
        		"created_at": "2017-06-23 11:49:19",
        		"updated_at": "2017-06-23 11:49:19",
        		"estados": [
        			{
        				"id": 1,
        				"pedido_id": 38,
        				"paso": "aceptado",
        				"created_at": "2017-06-27 17:36:18",
        				"updated_at": "2017-06-27 17:36:18"
        			},
        			{
        				"id": 8,
        				"pedido_id": 38,
        				"paso": "en transito",
        				"created_at": "2017-06-29 11:28:18",
        				"updated_at": "2017-06-29 11:28:18"
        			},
        			{
        				"id": 9,
        				"pedido_id": 38,
        				"paso": "llegando",
        				"created_at": "2017-06-29 11:28:32",
        				"updated_at": "2017-06-29 11:28:32"
        			}
        		],
        		"estado": {
        			"id": 9,
        			"pedido_id": 38,
        			"paso": "llegando",
        			"created_at": "2017-06-29 11:28:32",
        			"updated_at": "2017-06-29 11:28:32"
        		}
        	}
        }

 **Error Response:**

  * **Code:** 422 Unprocessable Entity <br />
      **Content:** 
      
          {   
            "paso": [
              "El campo paso es inválido."
            ],
            "vehiculo_id": [
              "El campo vehiculo id es obligatorio cuando km está presente."
            ]
          }
          
  * **Code:** 401 Unauthorized <br />
      **Content:** 
      
          {
            "error": "Unauthenticated."
          }

            
  * **Code:** 409 Unauthorized <br />
    **Content:**

        {
          "error": "No se puede marcar este estado dentro de la geocerca"
        }



  * **Code:** 410 Gone <br />
    **Content:**

        {
            "error": "No se puede marcar como llegando. Se necesita estado en tránsito."
        }


  * **Code:** 411 Length Required <br />
    **Content:**

        {
            "error": "No se puede marcar este estado hasta que pasen 5 minutos de estado en tránsito."
        }


  * **Code:** 412 Precondition Failed <br />
    **Content:**

        {
            "error": "El pedido ha sido eliminado o no existe."
        }
        
 * **Code:** 413 Payload Too Large <br />
    **Content:**

        {
            "error": "El kilometraje ingresado es inválido. Es mínimo al anterior o excede el límite."
        }

        
** Actualizar ubicación del agente con pedido asignado **
----
 Request para actualizar el historico de ubicaciones del agente durante un pedido

 **URL**

  /api/agentes/pedidos/IDpedido/ubicaciones

 **Method:**

  `POST`
    
 **Headers**
  
     Authorization: Bearer access_token
     Accept: application/json
     Content-Type: application/x-www-form-urlencoded
    
 **Data Params**
 
  ***Required:***
     
        'lat' => 'required',
        'lon' => 'required',
        'desvio' => 'boolean|required',  | ejemplo [ 0:1 ]
        'detencion' => 'nullable|boolean'
     
    
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
        		"created_at": "2017-03-16 17:47:54",
        		"updated_at": "2017-03-16 17:47:54",
        		"deleted_at": null,
        		"agente_perfil": {
        			"id": 1,
        			"user_id": 3,
        			"colonia_id": null,
        			"numero_control": "",
        			"estatus": "Recoger pedido",
        			"created_at": null,
        			"updated_at": "2017-06-23 15:02:04",
        			"deleted_at": null,
        			"lat": "10",
        			"lon": "35",
        			"imagen": null,
        			"imagen_path": null
        		}
        	},
        	"pedido": {
        		"id": 38,
        		"user_id": 4,
        		"cliente_direccion_id": 40,
        		"folio": "APP0000254",
        		"created_at": "2017-06-23 11:49:19",
        		"updated_at": "2017-06-23 11:49:19"
        	},
        	"ubicacion": {
        		"agente_id": 1,
        		"pedido_id": 38,
        		"lat": "10",
        		"lon": "35",
        		"desvio": "0",
        		"detencion": "0",
        		"updated_at": "2017-06-23 15:09:49",
        		"created_at": "2017-06-23 15:09:49",
        		"id": 9
        	}
        }

 **Error Responses:**
  * **Code:** 422 Unprocessable Entity <br />
    **Content:** 
    
        {
        	"lat": [
        		"El campo lat es obligatorio."
        	],
        	"lon": [
        		"El campo lon es obligatorio."
        	],
        	"desvio": [
        		"El campo desvio es obligatorio."
        	]
        	"detencion": [
                "El campo detencion debe tener un valor verdadero o falso."
            ]
        }
            

  * **Code:** 401 Unauthorized <br />
    **Content:** 
    
        {
          "error": "Unauthenticated."
        }
        
        
**  Historico de ubicaciones del agente durante el pedido **
----
  Obtiene el historico de ubicaciones del agente durante un pedido

 **URL**

  /api/agentes/pedidos/IDpedido/ubicaciones

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
        	"ubicaciones": [
        		{
        			"id": 2,
        			"pedido_id": 38,
        			"agente_id": 1,
        			"lat": "10",
        			"lon": "35",
        			"desvio": "0",
        			"detencion": "0",
        			"created_at": "2017-06-23 14:35:10",
        			"updated_at": "2017-06-23 14:35:10",
        			"agente": {
        				"id": 1,
        				"user_id": 3,
        				"colonia_id": null,
        				"numero_control": "",
        				"estatus": "Recoger pedido",
        				"created_at": null,
        				"updated_at": "2017-06-23 15:09:49",
        				"deleted_at": null,
        				"lat": "10",
        				"lon": "35",
        				"imagen": null,
        				"imagen_path": null
        			},
        			"pedido": {
        				"id": 38,
        				"user_id": 4,
        				"cliente_direccion_id": 40,
        				"folio": "APP0000254",
        				"created_at": "2017-06-23 11:49:19",
        				"updated_at": "2017-06-23 11:49:19",
        				"envio": {
        					"id": 14,
        					"pedido_id": 38,
        					"sucursal_id": 24,
        					"agente_id": 1,
        					"codigo_verificacion": "3420",
        					"puntaje": 0,
        					"created_at": "2017-06-23 11:51:07",
        					"updated_at": "2017-06-23 11:51:07"
        				}
        			}
        		},
        		{
        			"id": 3,
        			"pedido_id": 38,
        			"agente_id": 1,
        			"lat": "10",
        			"lon": "35",
        			"desvio": "0",
        			"detencion": "0",
        			"created_at": "2017-06-23 14:36:04",
        			"updated_at": "2017-06-23 14:36:04",
        			"agente": {
        				"id": 1,
        				"user_id": 3,
        				"colonia_id": null,
        				"numero_control": "",
        				"estatus": "Recoger pedido",
        				"created_at": null,
        				"updated_at": "2017-06-23 15:09:49",
        				"deleted_at": null,
        				"lat": "10",
        				"lon": "35",
        				"imagen": null,
        				"imagen_path": null
        			},
        			"pedido": {
        				"id": 38,
        				"user_id": 4,
        				"cliente_direccion_id": 40,
        				"created_at": "2017-06-23 11:49:19",
        				"updated_at": "2017-06-23 11:49:19",
        				"envio": {
        					"id": 14,
        					"pedido_id": 38,
        					"sucursal_id": 24,
        					"agente_id": 1,
        					"codigo_verificacion": "3420",
        					"puntaje": 0,
        					"created_at": "2017-06-23 11:51:07",
        					"updated_at": "2017-06-23 11:51:07"
        				}
        			}
        		}...
            ]
        }

  * **Code:** 401 Unauthorized <br />
    **Content:** 
    
        {
          "error": "Unauthenticated."
        }
        

     
  ** Asignar calificacion al repartidor  y a la sucursal **
  ----
    Asigna calificacion al repartidor y sucursal, se debera enviar el id del usuario sucursal y el id del usuario agente para su evaluación
  
   **URL**
  
    /api/clientes/agentes/pedidos/{IdPedido}/calificaciones
  
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
          		"folio": "APP0000254",
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
          
          
**Aceptar pedido**
----
  Acepta un pedido pendiente

 **URL**

  /api/agentes/pedidos/aceptar

 **Method:**

  `POST`
    
 **Headers**
 
    Authorization: Bearer access_token
    Accept: application/json
    Content-Type: application/x-www-form-urlencoded
    
    
**Data Params**
    
    `id=PedidoID`
    `aceptar=1|boolean`
    
    
 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
        	"pedido": {
        		"id": 110,
        		"user_id": 135,
        		"cliente_direccion_id": 342,
        		"asistencia": 0,
        		"alerta_cliente": 0,
        		"folio": "APP0000110",
        		"codigo_confirmacion": null,
        		"visto_callcenter": 0,
        		"created_at": "2017-10-30 11:12:20",
        		"updated_at": "2017-10-30 11:12:20",
        		"envio": {
        			"id": 197,
        			"pedido_id": 110,
        			"sucursal_id": 22,
        			"agente_id": 11,
        			"codigo_verificacion": "4097",
        			"aceptado": 1,
        			"created_at": "2017-10-30 11:14:41",
        			"updated_at": "2017-10-30 13:33:49",
        			"delivery_at": null,
        			"agente": {
        				"id": 11,
        				"user_id": 129,
        				"numero_control": "2471",
        				"estatus": 1,
        				"puesto": null,
        				"created_at": "2017-10-15 10:39:38",
        				"updated_at": "2017-10-30 11:30:12",
        				"deleted_at": null,
        				"lat": "18.9362806",
        				"lon": "-99.2295446",
        				"imagen": null,
        				"imagen_path": null,
        				"vehiculo_id": null
        			}
        		},
        		"estado": {
        			"id": 585,
        			"pedido_id": 110,
        			"paso": "aceptado agente",
        			"created_at": "2017-10-30 13:33:49",
        			"updated_at": "2017-10-30 13:33:49"
        		},
        		"cliente": {
        			"id": 135,
        			"name": "Julio",
        			"last_name": "Gutiérrez",
        			"second_last_name": "Tello",
        			"telephone": "527771911612",
        			"email": "benjamin.gutierrez@grupofarmapronto.com",
        			"player_id": "ceb93ce8-4e65-40ea-96d6-5290a88b52ee",
        			"activo": 1,
        			"slack_webhook_url": null,
        			"created_at": "2017-10-19 13:09:41",
        			"updated_at": "2017-10-25 09:57:45",
        			"deleted_at": null
        		},
        		"agente": [
        			{
        				"id": 11,
        				"user_id": 129,
        				"numero_control": "2471",
        				"estatus": 1,
        				"puesto": null,
        				"created_at": "2017-10-15 10:39:38",
        				"updated_at": "2017-10-30 11:30:12",
        				"deleted_at": null,
        				"lat": "18.9362806",
        				"lon": "-99.2295446",
        				"imagen": null,
        				"imagen_path": null,
        				"vehiculo_id": null,
        				"pivot": {
        					"pedido_id": 110,
        					"agente_id": 11,
        					"nip": "RX9Y",
        					"aceptado": 1,
        					"liberado": 0
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
          
          
  * **Code:** 422 Unprocessable Entity <br />
      **Content:**           
          
          {
          	"id": [
          		"El campo id es obligatorio."
          	],
          	"aceptado": [
          		"El campo aceptado es obligatorio."
          	]
          }
          


**Cancelar pedido**
----
  Cancela un pedido ya aceptado por el agente

 **URL**

  /api/agentes/pedidos/cancelar

 **Method:**

  `POST`
    
 **Headers**
 
    Authorization: Bearer access_token
    Accept: application/json
    Content-Type: application/x-www-form-urlencoded
    
    
**Data Params**
    
    `id=PedidoID`
    `cancelar=1|boolean`
    'motivo' => 'nullable|in:productos,tiempo,pago,no_cliente',
    'lat' => 'nullable',
    'lon' => 'nullable'
    
    
 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
        	"pedido": {
        		"id": 110,
        		"user_id": 135,
        		"cliente_direccion_id": 342,
        		"asistencia": 0,
        		"alerta_cliente": 0,
        		"folio": "APP0000110",
        		"codigo_confirmacion": null,
        		"visto_callcenter": 0,
        		"created_at": "2017-10-30 11:12:20",
        		"updated_at": "2017-10-30 11:12:20",
        		"estado": {
        			"id": 584,
        			"pedido_id": 110,
        			"paso": "cancelado agente",
        			"created_at": "2017-10-30 13:25:58",
        			"updated_at": "2017-10-30 13:25:58"
        		},
        		"envio": {
        			"id": 197,
        			"pedido_id": 110,
        			"sucursal_id": 22,
        			"agente_id": null,
        			"codigo_verificacion": "4097",
        			"aceptado": 0,
        			"created_at": "2017-10-30 11:14:41",
        			"updated_at": "2017-10-30 13:25:58",
        			"delivery_at": null
        		},
        		"sucursal": [
        			{
        				"id": 22,
        				"user_id": 133,
        				"codigo": "24",
        				"nombre": "YY",
        				"telefono": null,
        				"colonia_id": 34660,
        				"municipio_id": 502,
        				"estado_id": 17,
        				"direccion": "AV.MORELOS SUR",
        				"direccion_numero": "157",
        				"codigo_postal": "62050",
        				"lon": "-99.2341139",
        				"lat": "18.9051954",
        				"created_at": "2017-03-16 17:50:05",
        				"updated_at": "2017-07-05 13:45:03",
        				"deleted_at": null,
        				"pivot": {
        					"pedido_id": 110,
        					"sucursal_id": 22,
        					"aceptado": 1,
        					"rechazado": 0,
        					"activo": 1
        				}
        			}
        		],
        		"agentes": [
        			{
        				"id": 11,
        				"user_id": 129,
        				"numero_control": "2471",
        				"estatus": 1,
        				"puesto": null,
        				"created_at": "2017-10-15 10:39:38",
        				"updated_at": "2017-10-30 11:30:12",
        				"deleted_at": null,
        				"lat": "18.9362806",
        				"lon": "-99.2295446",
        				"imagen": null,
        				"imagen_path": null,
        				"vehiculo_id": null,
        				"pivot": {
        					"pedido_id": 110,
        					"agente_id": 11,
        					"aceptado": 0,
        					"liberado": 0,
        					"nip": null
        				}
        			},
        			{
        				"id": 14,
        				"user_id": 137,
        				"numero_control": "3447",
        				"estatus": 1,
        				"puesto": null,
        				"created_at": "2017-10-19 18:22:24",
        				"updated_at": "2017-10-30 10:41:06",
        				"deleted_at": null,
        				"lat": "18.9051213",
        				"lon": "-99.231828",
        				"imagen": null,
        				"imagen_path": null,
        				"vehiculo_id": null,
        				"pivot": {
        					"pedido_id": 110,
        					"agente_id": 14,
        					"aceptado": 0,
        					"liberado": 0,
        					"nip": null
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
            	"error": "El pedido no se puede cancelar"
            }
            
            
            {
                "error": "El pedido no tiene sucursal asignada"
            }
            
            {
                "error": "El pedido no puede ser cancelado, el pedido ya ha sido liberado"
            }
            
            {
                "error": "Falta mandar acción de cancelar"
            }
            
            {
                "error": "El pedido no puede ser cancelado, debe de estar cerca del domicilio de entrega"
            }
            
          
          
  * **Code:** 422 Unprocessable Entity <br />
      **Content:**           
          
          {
          	"id": [
          		"El campo id es obligatorio."
          	]
          }
          


**Actualizar información de pago del pedido**
----
  Acepta un pedido pendiente

 **URL**

  agentes/pedidos/[IDPEDIDO]/pagos

 **Method:**

  `PUT`
    
 **Headers**
 
    Authorization: Bearer access_token
    Accept: application/json
    Content-Type: application/x-www-form-urlencoded
    
**Data Params**
    
    'metodo_pago' => 'in:efectivo,tarjeta',
    'monto_efectivo' => 'numeric',
    'tarjeta' => 'in:credito,debito',
    'last4' => 'numeric|max:9999',
    'tipo' => 'in:visa,mc,amex'
    
    
 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
            "pedido": {
                "id": 156,
                "user_id": 141,
                "cliente_direccion_id": 232,
                "asistencia": 0,
                "folio": null,
                "created_at": "2017-07-19 12:05:14",
                "updated_at": "2017-07-19 12:05:14",
                "envio": {
                    "id": 65,
                    "pedido_id": 156,
                    "sucursal_id": 50,
                    "agente_id": 2,
                    "codigo_verificacion": "4712",
                    "aceptado": 1,
                    "created_at": "2017-07-19 12:10:43",
                    "updated_at": "2017-07-19 12:10:57",
                    "delivery_at": null
                },
                "pago": {
                    "id": 153,
                    "pedido_id": 156,
                    "estado": "pendiente",
                    "metodo_pago": "tarjeta",
                    "monto_efectivo": null,
                    "monto": "50",
                    "referencia": null,
                    "created_at": "2017-07-19 12:05:14",
                    "updated_at": "2017-07-26 17:35:22",
                    "facturacion_id": null,
                    "tarjeta": {
                        "id": 27,
                        "pedido_pago_id": 153,
                        "user_id": 141,
                        "last4": "1111",
                        "tarjeta": "debito",
                        "tipo": "visa",
                        "created_at": "2017-07-26 17:41:55",
                        "updated_at": "2017-07-26 17:43:15"
                    }
                }
            },
            "agente": {
                "id": 2,
                "user_id": 124,
                "numero_control": "00000",
                "estatus": 1,
                "created_at": "2017-06-22 18:25:32",
                "updated_at": "2017-07-24 17:17:40",
                "deleted_at": null,
                "lat": "18.9361389",
                "lon": "-99.230313",
                "imagen": null,
                "imagen_path": null,
                "vehiculo_id": null
            }
        }

 **Error Response:**
  
  * **Code:** 401 Unauthorized <br />
      **Content:** 
      
          {
            "error": "Unauthenticated."
          }
          
          
**Añade recetas del pedido**
----

 **URL**

  /api/agentes/pedidos/{IDPedido}/recetas

 **Method:**

  `POST`
    
 **Headers**
 
    Authorization: Bearer access_token
    Accept: application/json
    Content-Type: multipart/form-data
    
**Data Params**

 ***Required:***
    
    
    
        'producto_id' => 'required|exists:productos,id',
        'archivo' => 'required|image'
    
   
 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
           {
                "pedido": {
                    "id": 2599,
                    "user_id": 1160,
                    "cliente_direccion_id": 2975,
                    "asistencia": 0,
                    "alerta_cliente": 0,
                    "folio": "ERP0002599",
                    "erp": 1,
                    "codigo_confirmacion": null,
                    "visto_callcenter": 1,
                    "created_at": "2018-05-03 18:32:10",
                    "updated_at": "2018-05-03 20:05:05"
                },
                "receta": {
                    "id": 195,
                    "pedido_id": 2599,
                    "producto_id": 27780,
                    "user_id": 1160,
                    "tipo": "receta",
                    "archivo": "http:\/\/farmapronto-multiples.csgroup.mx\/uploads\/recetas\/vopa9z8AzWQEA1Ofi2plavoofn40F7F37LZ8UutF.png",
                    "motivo": null,
                    "aceptado": 0,
                    "created_at": "2018-05-03 18:32:11",
                    "updated_at": "2018-05-04 12:36:46",
                    "fisico": 0,
                    "estatus": "pendiente",
                    "producto": {
                        "id": 27780,
                        "farmapronto_id": "030085",
                        "sku": "7501471889833",
                        "nombre": "MP AMOXICILINA 250MG SUSP 75ML",
                        "descripcion": "MP AMOXICILINA 250MG SUSP 75ML",
                        "categoria": "ANTIBIOTICOS",
                        "categoria_id": 0,
                        "laboratorio": "Bayer",
                        "receta": 1,
                        "clave": "SUJETO A DISPONIBILIDAD",
                        "tipo": 106,
                        "activos": "AMOXICILINA",
                        "destacado": 0,
                        "archivo": null,
                        "created_at": "2017-03-16 17:49:44",
                        "updated_at": "2018-05-04 06:39:32",
                        "activo": 1
                    }
                }
           }

 **Error Response:**

  * **Code:** 422 Unprocessable Entity <br />
      **Content:** 
      
          {   
            "producto_id": [
              "El campo paso es requerido."
            ],
            "archivo": [
              "El campo paso es requerido."
            ]
          }
          
  * **Code:** 401 Unauthorized <br />
      **Content:** 
      
          {
            "error": "Unauthenticated."
          }
          
     
     
            
**Actualizar ubicación del cliente del pedido asignado**
----     

 Request para actualizar las coordenadas de un cliente si se encuentra a 100mts de diferencia de la última ubicación

 **URL**

  /api/agentes/pedidos/IDpedido/ubicacion-cliente

 **Method:**

  `POST`
    
 **Headers**
  
     Authorization: Bearer access_token
     Accept: application/json
     Content-Type: application/x-www-form-urlencoded
    
 **Data Params**
 
  ***Required:***
     
        'lat' => 'required',
        'lon' => 'required',
     
    
 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
            "pedido": {
                "id": 51885,
                "user_id": 1442,
                "cliente_direccion_id": 48722,
                "ciudad_cobertura_id": null,
                "asistencia": 0,
                "alerta_cliente": 0,
                "folio": "ERP0051885",
                "erp": 1,
                "usuario_erp": "LOCHOA",
                "codigo_confirmacion": null,
                "visto_callcenter": 1,
                "programado_at": null,
                "taxi": 0,
                "clon": 0,
                "pedidos_juntos": "51885,51878",
                "cancelado_motivo": null,
                "cancelado_user_id": null,
                "created_at": "2019-04-25 10:01:50",
                "updated_at": "2019-05-07 17:24:15",
                "deleted_at": null,
                "cliente": {
                  "id": 1442,
                  "name": "RECIDENCIA",
                  "last_name": "VILLAS DEL SOL .",
                  "second_last_name": ".",
                  "telephone": "7555542118",
                  "clave": "REVIMLJI",
                  "email": "uno@uno.com",
                  "player_id": null,
                  "activo": 1,
                  "baja": 0,
                  "fb_id": null,
                  "slack_webhook_url": null,
                  "created_at": "2018-05-11 19:07:32",
                  "updated_at": "2018-10-22 17:31:46",
                  "deleted_at": null,
                  "last_login": null,
                  "cliente_perfil": {
                    "id": 1334,
                    "user_id": 1442,
                    "active": 1,
                    "deleted_at": null,
                    "created_at": "2018-05-11 19:07:32",
                    "updated_at": "2019-05-07 17:27:30",
                    "sexo": null,
                    "fecha_nacimiento": null,
                    "edad": null,
                    "imagen": null,
                    "imagen_path": null,
                    "zona_id": null,
                    "especial": 0,
                    "lat": "17.6319566",
                    "lon": "-101.54549",
                    "categoria_id": null
                  }
                }
              }
            }
        }

 **Error Responses:**
  * **Code:** 422 Unprocessable Entity <br />
    **Content:** 
    
        {
        	"lat": [
        		"El campo lat es obligatorio."
        	],
        	"lon": [
        		"El campo lon es obligatorio."
        	]
        }
            

  * **Code:** 401 Unauthorized <br />
    **Content:** 
    
        {
          "error": "Unauthenticated."
        }
        
        
        
                
**Almacena las polilíneas de los pedidos juntos**
----

 **URL**

    /api/agentes/pedidos/rutas

 **Method:**

  `POST`
    
 **Headers**
 
    Authorization: Bearer access_token
    Accept: application/json
    Content-Type: multipart/form-data
    
**Data Params**
    
    'polylines' => 'required|array'
    
   
 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
            "polylines": {
               "72828": "ymqrBz{s|Qi@LS@m@Kg@@k@Lo@PM]CSIWOJcB`AkC|AqA`AqAfAg@^cBbAq@TiB\\aF`AwGpAqFdAqPdDkEx@aB^aFpAuIhBcGlAaKjB_Dr@o@LoDn@yGfAgNpC{Ct@yCf@{Dz@}@N}GnAsE|@gAToBh@u@Lg@QMMKSCs@CqA@_AFg@Ty@t@yCZeB`@aBXeAn@aCf@wBBg@Ac@Em@WsAEi@}AjCWb@cB~D}DEmHOiGU_GIeDQwCQOACAEAIDCJHHD?G`BD^@t@En@_@p@St@Ct@?f@FJ^Vv@TZZT\\B\\Jz@V~@Xt@j@`AbAbAZVn@ZtA`@x@L\\@bA@VF~@E^Bz@M"
            }
        }

 **Error Response:**
          
  * **Code:** 401 Unauthorized <br />
      **Content:** 
      
          {
            "error": "Unauthenticated."
          }
        
          
  * **Code:** 422 Unprocessable Entity <br />
       **Content:** 
       
           {   
             "polylines": [
               "El campo polylines es obligatorio."
             ]
           }