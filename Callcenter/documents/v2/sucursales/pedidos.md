## Listado de todos los pedidos con opción de filtro por estatus
Regresa el listado de todos los pedidos que estan disponibles

 **URL**

    /api-v2/sucursales/pedidos

 **Method:**

  `GET`
  
 **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json


  **URL Params**

  - includes[]=cliente.clientePerfil, direccion, estimado, pago, envio <br><br>
  Ejemplo URI: `api-v2/sucursales/pedidos?includes[]=cliente.clientePerfil`
  

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
       
      
      
      
## Listado de pedidos pendientes/ activos/ terminados
Regresa el listado de todos los pedidos que estan disponibles

 **URL**

    /api-v2/sucursales/pedidos/pendientes
    /api-v2/sucursales/pedidos/activos
    /api-v2/sucursales/pedidos/terminados

 **Method:**

  `GET`
  
 **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json

    
  **URL Params**

  - includes[]=cliente, direccion, estado, evidencias, pedidoProductos.listaPrecio.producto, envio.agente   <br><br>
  Ejemplo URI: `api-v2/sucursales/pedidos/pendientes?includes[]=cliente&includes[]=direccion&includes[]=pedidoProductos.listaPrecio.producto&includes[]=estado&includes[]=evidencias&includes[]=envio.agente`
  

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

    /api-v2/sucursales/pedidos/ID

 **Method:**

  `GET`
  
  **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data
      
  **URL Params**

  - includes[]=cliente, direccion, estado, evidencias, pedidoProductos.listaPrecio.producto, envio.agente   <br><br>
  Ejemplo URI: `api-v2/sucursales/pedidos/1?includes[]=cliente&includes[]=direccion&includes[]=pedidoProductos.listaPrecio.producto&includes[]=estado&includes[]=evidencias&includes[]=envio.agente`
  

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

**Marcar "en tránsito" pedido**
----
  Regresa la información de un pedido después de marcarlo como "en tránsito"

 **URL**

    /api-v2/sucursales/pedidos/ID/en-transito

 **Method:**

  `POST`
  
  **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data
     
 **Data Params**
    
    'repartidor_id' => 'nullable|exists:repartidores,id',
    'placas' => 'nullable',

 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        { 
             "pedido": {
               "id": 104640,
               "user_id": 1417,
               "cliente_direccion_id": 86118,
               "ciudad_cobertura_id": null,
               "asistencia": 0,
               "alerta_cliente": 0,
               "folio": "ERP0104640",
               "erp": 1,
               "usuario_erp": "MAUGUSTO",
               "codigo_confirmacion": null,
               "visto_callcenter": 1,
               "programado_at": null,
               "taxi": 0,
               "clon": 0,
               "pedidos_juntos": null,
               "cancelado_motivo": null,
               "cancelado_user_id": null,
               "observaciones": null,
               "liberado": null,
               "created_at": "2020-02-20 11:25:02",
               "updated_at": "2020-02-20 13:46:02",
               "deleted_at": null,
               "origen": null,
               "envio": {
                 "id": 102588,
                 "pedido_id": 104640,
                 "sucursal_id": 22,
                 "agente_id": 211,
                 "vehiculo_id": 73,
                 "repartidor_id": null,
                 "placas": null,
                 "tipo_envio": "domicilio_propios",
                 "codigo_verificacion": "7266",
                 "aceptado": 0,
                 "created_at": "2020-02-20 12:13:22",
                 "updated_at": "2020-02-20 13:45:33",
                 "delivery_at": "2020-02-20 13:08:27",
                 "estimated_at": "2020-02-20 13:05:58",
                 "outoftime": 1,
                 "outoftime_notified": "2020-02-20 12:52:02",
                 "tiempo_recoleccion": "7",
                 "tiempo_entrega": "37",
                 "taxi_cp_id": null,
                 "km_entrega": "12477",
                 "km_anterior": "12477",
                 "lat": "18.8993863",
                 "lon": "-99.2283154",
                 "en_ruta": 0,
                 "en_ruta_at": "2020-02-20 12:30:31"
               },
               "repartidor": [
                 {
                   "id": 211,
                   "user_id": 17204,
                   "numero_control": "4807",
                   "estatus": 1,
                   "puesto": null,
                   "created_at": "2019-07-18 15:48:15",
                   "updated_at": "2020-03-17 17:01:02",
                   "deleted_at": null,
                   "lat": "18.9301845",
                   "lon": "-99.2101104",
                   "imagen": null,
                   "imagen_path": null,
                   "vehiculo_id": 45,
                   "sucursal_base_id": 62,
                   "supervisor": 0,
                   "cant_errores_actuales": 52,
                   "pivot": {
                     "pedido_id": 104640,
                     "agente_id": 211,
                     "nip": "KEKC",
                     "created_at": null,
                     "updated_at": "2020-02-20 13:46:02"
                   }
                 }
               ],
               "pedido_bot": null
             },
             "estado": {
               "paso": "en transito",
               "pedido_id": 104640,
               "updated_at": "2020-04-28 18:28:55",
               "created_at": "2020-04-28 18:28:55",
               "id": 1130912
             } 
        }
 
 **Error Response:**

  * **Code:** 401 Unauthorized <br />
    **Content:** 
    
        {
          "error": "Unauthenticated."
        }
        
  * **Code:** 404 Not Found <br />
    **Content:** 
    
        {
          "error": "Sucursal no disponible."
        }
        
  * **Code:** 422 Unprocessable Entity <br />
    **Content:** 
    
        {
          "error": "Pedido no válido."
        }
           
  * **Code:** 423 Locked <br />
    **Content:** 
    
        {
          "error": "La sucursal no coincide con la del pedido indicado."
        }
        
        
        
**Marcar "entregado" pedido**
----
  Regresa la información de un pedido después de marcarlo como "entregado"

 **URL**

    /api-v2/sucursales/pedidos/ID/entregado

 **Method:**

  `POST`
  
  **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data

 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        { 
              "pedido": {
                "id": 104640,
                "user_id": 1417,
                "cliente_direccion_id": 86118,
                "ciudad_cobertura_id": null,
                "asistencia": 0,
                "alerta_cliente": 0,
                "folio": "ERP0104640",
                "erp": 1,
                "usuario_erp": "MAUGUSTO",
                "codigo_confirmacion": null,
                "visto_callcenter": 1,
                "programado_at": null,
                "taxi": 0,
                "clon": 0,
                "pedidos_juntos": null,
                "cancelado_motivo": null,
                "cancelado_user_id": null,
                "observaciones": null,
                "liberado": null,
                "created_at": "2020-02-20 11:25:02",
                "updated_at": "2020-02-20 13:46:02",
                "deleted_at": null,
                "origen": null,
                "envio": {
                  "id": 102588,
                  "pedido_id": 104640,
                  "sucursal_id": 22,
                  "agente_id": 211,
                  "vehiculo_id": 73,
                  "tipo_envio": "domicilio_propios",
                  "codigo_verificacion": "7266",
                  "aceptado": 0,
                  "created_at": "2020-02-20 12:13:22",
                  "updated_at": "2020-04-28 18:37:42",
                  "delivery_at": "2020-02-20 13:08:27",
                  "estimated_at": "2020-02-20 13:05:58",
                  "outoftime": 1,
                  "outoftime_notified": "2020-02-20 12:52:02",
                  "tiempo_recoleccion": "7",
                  "tiempo_entrega": 8,
                  "taxi_cp_id": null,
                  "km_entrega": "12477",
                  "km_anterior": "12477",
                  "lat": "18.8993863",
                  "lon": "-99.2283154",
                  "en_ruta": 0,
                  "en_ruta_at": "2020-02-20 12:30:31"
                },
                "pedido_bot": null
              },
              "estado": {
                "paso": "entregado",
                "pedido_id": 104640,
                "updated_at": "2020-04-28 18:37:42",
                "created_at": "2020-04-28 18:37:42",
                "id": 1130913
              } 
        }
 
 **Error Response:**

  * **Code:** 401 Unauthorized <br />
    **Content:** 
    
        {
          "error": "Unauthenticated."
        }
        
  * **Code:** 404 Not Found <br />
    **Content:** 
    
        {
          "error": "Sucursal no disponible."
        }
        
  * **Code:** 410 Gone <br />
    **Content:** 
    
        {
          "error": "No se puede marcar como entregado. Se necesita estado en tránsito."
        }
        
  * **Code:** 422 Unprocessable Entity <br />
    **Content:** 
    
        {
          "error": "Pedido no válido."
        }
           
  * **Code:** 423 Locked <br />
    **Content:** 
    
        {
          "error": "La sucursal no coincide con la del pedido indicado."
        }
        
   
        
        
**Marcar "escaneado" pedido**
----
  Regresa la información de un pedido después de marcarlo como "escaneado"

 **URL**

    /api-v2/sucursales/pedidos/ID/escaneado

 **Method:**

  `POST`
  
  **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data
      
         
 **Data Params**
    
    'tickets' => 'required|array'


 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        { 
              "pedido": {
                "id": 104640,
                "user_id": 1417,
                "cliente_direccion_id": 86118,
                "ciudad_cobertura_id": null,
                "asistencia": 0,
                "alerta_cliente": 0,
                "folio": "ERP0104640",
                "erp": 1,
                "traspaso": 0,
                "usuario_erp": "MAUGUSTO",
                "codigo_confirmacion": null,
                "visto_callcenter": 1,
                "programado_at": null,
                "taxi": 0,
                "clon": 0,
                "pedidos_juntos": null,
                "cancelado_motivo": null,
                "cancelado_user_id": null,
                "observaciones": null,
                "liberado": null,
                "created_at": "2020-02-20 11:25:02",
                "updated_at": "2020-02-20 13:46:02",
                "deleted_at": null,
                "origen": null,
                "envio": {
                  "id": 102588,
                  "pedido_id": 104640,
                  "sucursal_id": 22,
                  "agente_id": 211,
                  "vehiculo_id": 73,
                  "repartidor_id": null,
                  "placas": null,
                  "tipo_envio": "domicilio_propios",
                  "costo_envio": null,
                  "codigo_verificacion": "7266",
                  "aceptado": 0,
                  "created_at": "2020-02-20 12:13:22",
                  "updated_at": "2020-04-28 18:37:42",
                  "delivery_at": "2020-02-20 13:08:27",
                  "estimated_at": "2020-02-20 13:05:58",
                  "outoftime": 1,
                  "outoftime_notified": "2020-02-20 12:52:02",
                  "tiempo_recoleccion": "7",
                  "tiempo_entrega": "8",
                  "taxi_cp_id": null,
                  "km_entrega": "12477",
                  "km_anterior": "12477",
                  "lat": "18.8993863",
                  "lon": "-99.2283154",
                  "en_ruta": 0,
                  "en_ruta_at": "2020-02-20 12:30:31"
                },
                "tickets": [
                  {
                    "id": 3,
                    "pedido_id": 104640,
                    "user_id": 133,
                    "folio": "FOLIO1",
                    "created_at": "2020-05-13 12:21:31",
                    "updated_at": "2020-05-13 12:21:31"
                  },
                  {
                    "id": 4,
                    "pedido_id": 104640,
                    "user_id": 133,
                    "folio": "FOLIO2",
                    "created_at": "2020-05-13 12:21:31",
                    "updated_at": "2020-05-13 12:21:31"
                  }
                ]
              },
              "estado": {
                "paso": "embarcado",
                "pedido_id": 104640,
                "updated_at": "2020-05-13 12:21:31",
                "created_at": "2020-05-13 12:21:31",
                "id": 1130921
              } 
        }
 
 **Error Response:**

  * **Code:** 401 Unauthorized <br />
    **Content:** 
    
        {
          "error": "Unauthenticated."
        }
        
  * **Code:** 404 Not Found <br />
    **Content:** 
    
        {
          "error": "Sucursal no disponible."
        }
        
  * **Code:** 422 Unprocessable Entity <br />
    **Content:** 
    
        {
            "tickets": [
              "El campo tickets es obligatorio."
            ]
        }
           
  * **Code:** 423 Locked <br />
    **Content:** 
    
        {
          "error": "La sucursal no coincide con la del pedido indicado."
        }
        
                
  * **Code:** 424 Failed Dependency <br />
    **Content:** 
    
        {
           "error": "Pedido no válido."
        }
        


       
        
**Actualizar producto de pedido**
----
  Regresa la información de un pedido después de actualizar su producto y cantidades

 **URL**

    /api-v2/sucursales/pedidos/ID/productos/update

 **Method:**

  `POST`
  
  **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data
      
         
 **Data Params**
    
    'pedido_producto_id' => 'required|array',
    'cant' => 'required|array',


 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        { 
               "pedido": {
                   "id": 137062,
                   "user_id": 28612,
                   "cliente_direccion_id": 108112,
                   "ciudad_cobertura_id": null,
                   "asistencia": 0,
                   "alerta_cliente": 0,
                   "folio": "ERP0137062",
                   "erp": 1,
                   "traspaso": 0,
                   "usuario_erp": "MAUGUSTO",
                   "codigo_confirmacion": null,
                   "visto_callcenter": 1,
                   "programado_at": null,
                   "taxi": 0,
                   "clon": 0,
                   "pedidos_juntos": null,
                   "cancelado_motivo": null,
                   "cancelado_user_id": null,
                   "cancelado_observaciones": null,
                   "observaciones": null,
                   "liberado": null,
                   "created_at": "2020-07-16 12:19:31",
                   "updated_at": "2020-07-28 02:02:02",
                   "deleted_at": null,
                   "origen": null
               }
        }
 
 **Error Response:**

  * **Code:** 401 Unauthorized <br />
    **Content:** 
    
        {
          "error": "Unauthenticated."
        }
        
  * **Code:** 404 Not Found <br />
    **Content:** 
    
        {
          "error": "Sucursal no disponible."
        }
        
  * **Code:** 422 Unprocessable Entity <br />
    **Content:** 
    
        {
              "pedido_producto_id": [
                "El campo pedido producto id es obligatorio."
              ],
              "cant": [
                "El campo cant debe ser un conjunto."
              ]
        }
                
  * **Code:** 424 Failed Dependency <br />
    **Content:** 
    
        {
           "error": "Pedido no válido."
        }