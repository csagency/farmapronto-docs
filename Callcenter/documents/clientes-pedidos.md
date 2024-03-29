
## Petición para saber si se pueden realizar pedidos
Regresa en activo un boolean pasa conocer el estatus de pedidos. Cuando es `activo` es true se podrán realizar pedidos

 **URL**

    /api/config

 **Method:**

  `GET`
  
 **Headers**
   
      Accept: application/json

**URL Params**
    
    {
        "config": "pedidos",
        "activo": 1,
        "updated_at": "2018-03-07 14:47:05"
    }
      
      
## Listado de pedidos realizador por el cliente
Regresa el listado de todos los pedidos del cliente

 **URL**

  /api/clientes/pedidos/

 **Method:**

  `GET`
  
 **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data

**URL Params**

  - includes[]=cliente.user, pago, estado, envio  <br><br>
  Ejemplo URI: `api/clientes/pedidos?includes[]=cliente&includes[]=pago`
  


**Success Response:**

* **Code:** 200 <br />
  **Content:** 
  
      {
          "pedidos": [
            {
            "id": 1,
            "user_id": 16,
            "cliente_direccion_id": 1,
            "created_at": "2017-06-20 12:41:49",
            "updated_at": "2017-06-20 12:41:49"
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
              "pago": null
            }
          ]
      }

**Error Response:**

* **Code:** 401 Unauthorized <br />
  **Content:** 
  
      {
        "error": "Unauthenticated."
      }



       
**Registro de nuevo pedido**
----
  Regresa la información del registro en formato json

 **URL**

  /api/clientes/pedidos/

 **Method:**

  `POST`
  
  **Headers**

  Content-Type: multipart/form-data
  Accept: application/json
  Authorization: token
 
 **Data Params**

 ***Required:***
    
    'direccion_id' => 'required_if:estado_id,|exists:clientes_direcciones,id',
    'estado_id' => 'required_if:direccion_id,|exists:catalogo_estados,id',
    'municipio_id' => 'required_if:direccion_id,|exists:catalogo_municipios,id',
    'colonia_id' => 'nullable|exists:catalogo_colonias,id',
    'calle' => 'nullable',
    'numero_interior' => 'nullable',
    'numero_exterior' => 'nullable',
    'codigo_postal' => 'nullable',
    'tipo' => 'required_if:direccion_id,',
    'lat' => 'required_if:direccion_id,',
    'lon' => 'required_if:direccion_id,',
    'monto' => '',
    'productos' => 'required|array',
    'cantidades' => 'required|array',
    'beneficios_ids' => 'array',
    'pago_tarjeta' => 'in:credito,debito',
    'tarjeta_id' => 'exists:clientes_tarjetas,id',
    'pago_last4' => 'numeric|max:9999',
    'pago_tipo_tarjeta' => 'in:visa,mc,amex',
    'metodo_pago' => 'in:efectivo,tarjeta,saldo',
    'recetas[]' => 'array',
    'factura_id' => 'exists:clientes_facturacion,id',
    'promocion_id' => 'exists:promociones,id|nullable',
    'programado_at' => 'nullable|date',
    'ciudad_cobertura_id' => 'nullable|exists:ciudades_cobertura,id',
    'taxi_cp_id' => 'nullable|exists:catalogo_taxis_cp,id',
    'observaciones' => 'nullable',

 **Example**
  
     productos[0]: 1
     cantidades[0]: 2
     productos[0]: 2
     cantidades[0]: 5
     

 **Success Response:**

  * **Code:** 200 <br />
    **Content:**

    
    
        {
        	"pedido": {
        		"user_id": 9995,
        		"cliente_direccion_id": 24692,
        		"taxi": false,
        		"ciudad_cobertura_id": "1",
        		"updated_at": "2018-12-04 18:57:43",
        		"created_at": "2018-12-04 18:57:39",
        		"id": 24741,
        		"folio": "APP0024741",
        		"usuario_erp": "APP",
        		"pago": {
        			"id": 24741,
        			"pedido_id": 24741,
        			"estado": "pendiente",
        			"metodo_pago": "tarjeta",
        			"monto_efectivo": null,
        			"monto": 71,
        			"referencia": null,
        			"created_at": "2018-12-04 18:57:39",
        			"updated_at": "2018-12-04 18:57:40",
        			"facturacion_id": null,
        			"tarjeta": {
        				"id": 2140,
        				"pedido_pago_id": 24741,
        				"user_id": null,
        				"last4": "2340",
        				"tarjeta": "credito",
        				"tipo": "visa",
        				"created_at": "2018-12-04 18:57:40",
        				"updated_at": "2018-12-04 18:57:40"
        			}
        		},
        		"sucursales": [
        			{
        				"id": 1,
        				"user_id": 5396,
        				"codigo": "1",
        				"nombre": "AA",
        				"telefono": "7772575993",
        				"colonia_id": 34727,
        				"municipio_id": 502,
        				"estado_id": 17,
        				"ciudad_cobertura_id": null,
        				"direccion": "AV. VICENTE GUERRERO",
        				"direccion_numero": "107",
        				"codigo_postal": "62230",
        				"lon": "-99.23085095421447",
        				"lat": "18.95742636448077",
        				"ancla": 1,
        				"dias": "LUN, MAR, MIE, JUE, VIE, SAB, DOM",
        				"horario_inicio": "07:00:00",
        				"horario_final": "22:59:00",
        				"24_hrs": 0,
        				"created_at": "2017-03-16 17:50:05",
        				"updated_at": "2018-09-04 17:45:49",
        				"deleted_at": null,
        				"pivot": {
        					"pedido_id": 24741,
        					"sucursal_id": 1,
        					"aceptado": 0,
        					"rechazado": 0,
        					"activo": 0
        				}
        			},
        			{
        				"id": 23,
        				"user_id": 73,
        				"codigo": "25",
        				"nombre": "ZZ",
        				"telefono": "7772575981",
        				"colonia_id": 34739,
        				"municipio_id": 502,
        				"estado_id": 17,
        				"ciudad_cobertura_id": null,
        				"direccion": "NUEVA INGLATERRA",
        				"direccion_numero": "500",
        				"codigo_postal": "62240",
        				"lon": "-99.227994",
        				"lat": "18.951769",
        				"ancla": 1,
        				"dias": "LUN, MAR, MIE, JUE, VIE, SAB, DOM",
        				"horario_inicio": "07:00:00",
        				"horario_final": "22:58:00",
        				"24_hrs": 0,
        				"created_at": "2017-03-16 17:50:05",
        				"updated_at": "2018-06-20 16:33:07",
        				"deleted_at": null,
        				"pivot": {
        					"pedido_id": 24741,
        					"sucursal_id": 23,
        					"aceptado": 0,
        					"rechazado": 0,
        					"activo": 0
        				}
        			},
        			{
        				"id": 62,
        				"user_id": 111,
        				"codigo": "86",
        				"nombre": "Q",
        				"telefono": "7772575913",
        				"colonia_id": 34754,
        				"municipio_id": 502,
        				"estado_id": 17,
        				"ciudad_cobertura_id": null,
        				"direccion": "LEÑEROS",
        				"direccion_numero": "68",
        				"codigo_postal": "62290",
        				"lon": "-99.21034696802599",
        				"lat": "18.930405497133883",
        				"ancla": 1,
        				"dias": "LUN, MAR, MIE, JUE, VIE, SAB, DOM",
        				"horario_inicio": "07:00:00",
        				"horario_final": "23:00:00",
        				"24_hrs": 0,
        				"created_at": "2017-07-05 13:45:09",
        				"updated_at": "2018-05-08 11:12:10",
        				"deleted_at": null,
        				"pivot": {
        					"pedido_id": 24741,
        					"sucursal_id": 62,
        					"aceptado": 0,
        					"rechazado": 0,
        					"activo": 0
        				}
        			}
        		],
        		"direccion": {
        			"id": 24692,
        			"user_id": 9995,
        			"estado_id": 1,
        			"municipio_id": 502,
        			"colonia_id": null,
        			"colonia_str": null,
        			"calle": null,
        			"numero_interior": null,
        			"numero_exterior": null,
        			"codigo_postal": null,
        			"referencia": null,
        			"tipo": "casa",
        			"lon": "-99.230098",
        			"lat": "18.935879",
        			"created_at": "2018-12-04 18:57:39",
        			"updated_at": "2018-12-04 18:57:39",
        			"deleted_at": null
        		},
        		"estado": {
        			"id": 256800,
        			"pedido_id": 24741,
        			"paso": "recibido",
        			"created_at": "2018-12-04 18:57:40",
        			"updated_at": "2018-12-04 18:57:40"
        		},
        		"pedido_productos": [
        			{
        				"id": 40611,
        				"lista_precio_id": 21,
        				"pedido_id": 24741,
        				"precio": 35.5,
        				"cantidad": 2,
        				"gratis": 0,
        				"disponible": 1,
        				"created_at": "2018-12-04 18:57:40",
        				"updated_at": "2018-12-04 18:57:40"
        			}
        		]
        	}
        }


 
 **Error Response:**

  * **Code:** 422 Unprocessable Entity <br />
    **Content:** 
    
        {
          "cliente_direccion_id": [
            "El campo cliente direccion id es inválido."
          ],
          "delivery_at": [
            "El campo delivery at es obligatorio."
          ],
          "productos": [
            "El campo productos es obligatorio."
          ],
          "cantidades": [
            "El campo cantidades es obligatorio."
          ]
        }
        
  * **Code:** 401 Unauthorized <br />
      **Content:** 
      
          {
            "error": "Unauthenticated."
          }
          
          
  * **Code:** 406 Not Accepted <br />
        **Content:** 
        
            {
              "error": "Pedidos deshabilitados."
            }
            
  * **Code:** 409 Unauthorized <br />
    **Content:**

        {
          "error": "Lo sentimos la zona no cuenta con cobertura."
        }



  * **Code:** 410 Gone <br />
    **Content:**

        {
            "error": "Pedidos programados fuera del horario"
        }


  * **Code:** 411 Length Required <br />
    **Content:**

        {
            "error": "La ciudad de envío no corresponde a la ciudad de dirección de entrega"
        }



  * **Code:** 412 Precondition Failed <br />
    **Content:**

        {
            "error": "El pedido no pudo ser procesado, favor de intentarlo de nuevo."
        }
        

        
  * **Code:** 413 Payload Too Large <br />
    **Content:**

        {
            "error": "El cliente no cuenta con el saldo suficiente, favor de intentarlo de nuevo con otro método de pago."
        }
          
               
  * **Code:** 414 URI Too Long <br />
    **Content:**

        {
            "error": "El código postal del costo de taxi no corresponde al de la dirección de entrega"
        } 
        
  * **Code:** 415 URI Too Long <br />
    **Content:**

        {
            "error": "Lo sentimos la zona no cuenta con cobertura de 24 hrs."
        }      
 
**Datos del pedido**
----
  Regresa la información de una pedido del cliente y sus relaciones ejemplo: pedidoProcutos, listaPrecio

 **URL**

  /api/clientes/pedidos/ID

 **Method:**

  `GET`
  
  **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data
      
  **URL Params**

  - includes[]=pedidoProductos.listaPrecio, pago, estado, envio  <br><br>
  Ejemplo URI: `api/clientes/pedidos/5?includes[]=pedidoProductos.listaPrecio`
  

 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        { 
          "pedido": {
            "id": 10,
            "user_id": 16,
            "cliente_direccion_id": 10,
            "folio": "APP0000254",
            "created_at": "2017-06-21 11:44:32",
            "updated_at": "2017-06-21 11:44:32"
            "pedido_productos": [
              {
                "id": 1,
                "lista_precio_id": 1,
                "pedido_id": 5,
                "precio": 20,
                "cantidad": 2,
                "created_at": "2017-05-17 18:39:57",
                "updated_at": "2017-05-17 18:39:57",
                "lista_precio": {
                  "id": 1,
                  "producto_id": 1,
                  "ciudad_id": 1,
                  "precio": 10,
                  "created_at": null,
                  "updated_at": null
                }
              },
              {
                "id": 2,
                "lista_precio_id": 2,
                "pedido_id": 5,
                "precio": 250,
                "cantidad": 5,
                "created_at": "2017-05-17 18:39:57",
                "updated_at": "2017-05-17 18:39:57",
                "lista_precio": {
                  "id": 2,
                  "producto_id": 2,
                  "ciudad_id": 1,
                  "precio": 50,
                  "created_at": null,
                  "updated_at": null
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



  * **Code:** 406 Unauthorized <br />
    **Content:**

        {
          "error": "Pedidos deshabilitados"
        }


  * **Code:** 409 Unauthorized <br />
    **Content:**

        {
          "error": "Lo sentimos la zona no cuenta con cobertura."
        }



  * **Code:** 410 Gone <br />
    **Content:**

        {
        	"error": "Pedidos programados fuera del horario"
        }



 * **Code:** 412 Gone <br />
    **Content:**

        {
        	"error": "El pedido no pudo ser procesado, favor de intentarlo de nuevo."
        }



**Actualización de pedido**
----
  Actualiza la información de un pedido del cliente

 **URL**

  /api/clientes/pedidos/ID

 **Method:**

  `PUT`
    
 **Headers**
 
    Authorization: Bearer access_token
    Accept: application/json
    Content-Type: multipart/form-data
    
**Data Params**

 ***Optional:***
    

    'estado_id' => 'exists:catalogo_estados,id',
    'municipio_id' => 'exists:catalogo_municipios,id',
    'colonia_id' => 'exists:catalogo_colonias,id',
    'calle' => '',
    'numero_interior' => '',
    'codigo_postal' => '',
    'tipo' => 'in:casa,oficina',
    'lat' => '',
    'lon' => '',
    'monto' => '',
    'productos' => '',
    'cantidades' => '',
    'pago_last4' => 'numeric|max:9999',
    'tarjeta_id' => 'exists:clientes_tarjetas,id',
    'pago_tipo_tarjeta' => 'in:visa,mc,amex',
    'metodo_pago' => 'in:efectivo,tarjeta',
    'factura_id' => 'exists:clientes_facturacion,id',
    'observaciones' => 'nullable',
    
 **Example**
   
      productos[0]: 1
      cantidades[0]: 2
    
 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
        	"pedido": {
        		"user_id": 4,
        		"cliente_direccion_id": 226,
        		"updated_at": "2017-07-13 17:06:58",
        		"created_at": "2017-07-13 17:06:58",
                "folio": "APP0000254",
        		"id": 107,
        		"evidencias": [],
        		"pago": {
        			"id": 104,
        			"pedido_id": 107,
        			"estado": "pendiente",
        			"metodo_pago": null,
        			"monto_efectivo": null,
        			"monto": 751,
        			"referencia": null,
        			"created_at": "2017-07-13 17:06:58",
        			"updated_at": "2017-07-13 17:06:58",
        			"facturacion_id": 20,
                    "facturacion": {
                        "id": 20,
                        "rfc": "BRAE881014167",
                        "alias": "PERSONA L",
                        "cliente_direccion_id": null,
                        "created_at": "2017-07-14 15:53:12",
                        "updated_at": "2017-07-14 15:53:12",
                        "estado_id": 17,
                        "municipio_id": 502,
                        "calle": "Av universidad",
                        "numero": "49",
                        "colonia": "CHAMILPA",
                        "codigo_postal": "62210",
                        "user_id": 131
                    }
        			"tarjeta": {
        				"id": 4,
        				"pedido_pago_id": 104,
        				"last4": "2343",
        				"tipo": "amex",
        				"created_at": "2017-07-13 17:06:58",
        				"updated_at": "2017-07-13 17:06:58"
        			}
        		},
        		"direccion": {
        			"id": 226,
        			"user_id": 4,
        			"estado_id": 1,
        			"municipio_id": 2,
        			"colonia_id": null,
        			"calle": null,
        			"numero_interior": null,
        			"numero_exterior": null,
        			"codigo_postal": null,
        			"referencia": null,
        			"tipo": "casa",
        			"lon": "-99.2306653",
        			"lat": "18.9358035",
        			"created_at": "2017-07-13 17:06:58",
        			"updated_at": "2017-07-13 17:06:58"
        		},
        		"sucursales": [],
        		"estado": {
        			"id": 32,
        			"pedido_id": 107,
        			"paso": "recibido",
        			"created_at": "2017-07-13 17:06:58",
        			"updated_at": "2017-07-13 17:06:58"
        		}
        	}
        }

 **Error Response:**

  * **Code:** 422 Unprocessable Entity <br />
      **Content:** 
      
          {
              "estado_id": [
                "El campo estado es obligatorio."
              ],
              "municipio_id": [
                "El campo municipio es obligatorio."
              ],
              "colonia_id": [
                "El campo colonia es obligatorio."
              ],
              "calle": [
                "El campo calle es obligatorio."
              ],
              "numero_interior": [
                "El campo numero interior es obligatorio."
              ],
              "codigo_postal": [
                "El campo codigo postal es obligatorio."
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



**Actualización pago del pedido**
----
  Actualiza en pago de un pedido

 **URL**

  /api/clientes/pedidos/ID/pago

 **Method:**

  `PUT`
    
 **Headers**
 
    Authorization: Bearer access_token
    Accept: application/json
    Content-Type: application/x-www-form-urlencoded
    
**Data Params**

 ***Optional:***
    
            'metodo_pago' => 'nullable|in:efectivo,tarjeta',
            'estado' => 'nullable|in:pendiente,pagado,rechazado,reembolsado',
            'monto_efectivo' => 'nullable|integer',
            'facturacion_id' => 'nullable',
            'pago_last4' => 'numeric|max:9999',
            'pago_tipo_tarjeta' => 'in:visa,mc,amex'
    
   
 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
        	"pedido": {
        		"id": 10,
        		"user_id": 16,
        		"cliente_direccion_id": 10,
        		"created_at": "2017-06-21 11:44:32",
        		"updated_at": "2017-06-21 11:44:32",
                "folio": "APP0000254",
        		"pago": {
        			"id": 1,
        			"pedido_id": 10,
        			"estado": "pagado",
        			"metodo_pago": "efectivo",
        			"monto_efectivo": "444",
        			"monto": "0",
        			"referencia": "",
        			"created_at": "2017-06-21 19:00:12",
        			"updated_at": "2017-06-21 14:00:12",
        			"facturacion_id": "4",
        			"facturacion": {
        				"id": 4,
        				"rfc": "BIAE881014QV6",
        				"cliente_direccion_id": 2,
        				"created_at": "2017-06-21 13:47:17",
        				"updated_at": "2017-06-21 13:47:17",
        				"estado_id": null,
        				"municipio_id": null,
        				"calle": null,
        				"numero": null,
        				"colonia": null,
        				"codigo_postal": null,
        				"user_id": 16
        			},
        			"tarjeta": {
                        "id": 5,
                        "pedido_pago_id": 105,
                        "last4": "2340",
                        "tipo": "visa",
                        "created_at": "2017-07-13 17:12:47",
                        "updated_at": "2017-07-13 17:15:00"
                    }
        		}
        	}
        }

 **Error Response:**
          
  * **Code:** 401 Unauthorized <br />
      **Content:** 
      
          {
            "error": "Unauthenticated."
          }



**Eliminar pedido**
----
  Elimina un pedido del cliente

 **URL**

  /api/clientes/pedidos/ID

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
        	"pedido": null
        }

 **Error Responses:**

  * **Code:** 401 Unauthorized <br />
    **Content:** 
    
        {
          "error": "Unauthenticated."
        }
        
        
  **Asignar calificacion al repartidor **
  ----
    Asigna calificacion al repartidor
  
   **URL**
  
    /api/clientes/pedidos/{IdPedido}/calificaciones
  
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
                "folio": "APP0000254",
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
          
 

## Listado de pedidos activos del cliente

Petición para validar si tiene cualquier pedido que no esté en estatus Liberado o Entregado


 **URL**

  /api/clientes/pedidos/activos

 **Method:**

  `GET`

 **Headers**

      Authorization: Bearer access_token
      Accept: application/json

**URL Params**

  - includes[]=cliente.user, pago, estado, envio  <br><br>
  Ejemplo URI: `api/clientes/pedidos/activos?includes[]=cliente&includes[]=pago`



**Success Response:**

* **Code:** 200 <br />
  **Content:**

      {
      	"pedidos": [
      		{
      			"id": 17712,
      			"user_id": 1934,
      			"cliente_direccion_id": 7210,
      			"asistencia": 0,
      			"alerta_cliente": 0,
      			"folio": "APP0017712",
      			"erp": 0,
      			"codigo_confirmacion": null,
      			"visto_callcenter": 0,
      			"created_at": "2018-09-20 17:12:45",
      			"updated_at": "2018-09-20 17:12:45",
      			"deleted_at": null
      		}
      	]
      }


* Respuesta 200 sin pedidos activos



        {
            "pedidos": []
        }



**Error Response:**

* **Code:** 401 Unauthorized <br />
  **Content:**

      {
        "error": "Unauthenticated."
      }


## Solicitar liga de cobro
Regresa URL  liga de cobro para pago por tarjeta de credito

 **URL**

  /api/clientes/pedidos/{id}/obtener-liga-pago

 **Method:**

  `POST`

 **Headers**

      Authorization: Bearer access_token
      Accept: application/json


**Success Response:**

* **Code:** 200 <br />
  **Content:**

      {
      	"liga_cobro": "https:\/\/wppsandbox.mit.com.mx\/i\/LBR2X51S"
      }


**Error Response:**

* **Code:** 401 Unauthorized <br />
  **Content:**

      {
        "error": "Unauthenticated."
      }