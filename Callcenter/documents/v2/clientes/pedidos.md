## Listado de pedidos realizador por el cliente
Regresa el listado de todos los pedidos del cliente

 **URL**

    /api-v2/clientes/pedidos/

 **Method:**

  `GET`
  
 **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data

**URL Params**

  - includes[]=cliente.user, pago, estado, envio  <br><br>
  Ejemplo URI: `api-v2/clientes/pedidos?includes[]=cliente&includes[]=pago`
  


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



       
       
       
## Listado de pedidos activos del cliente

Petición para validar si tiene cualquier pedido que no esté en estatus Liberado o Entregado


**URL**

    /api-v2/clientes/pedidos/activos

**Method:**

 `GET`

**Headers**

     Authorization: Bearer access_token
     Accept: application/json

**URL Params**

 - includes[]=cliente.user, pago, estado, envio  <br><br>
 Ejemplo URI: `api-v2/clientes/pedidos/activos?includes[]=cliente&includes[]=pago`



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
       
       
       
**Nuevo pedido**
----
  Regresa la información de un nuevo pedido

 **URL**

    /api-v2/clientes/pedidos

 **Method:**

  `POST`
  
  **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data
      
      
 **Data Params**
    
    'direccion_id' => 'required_if:estado_id,|exists:clientes_direcciones,id',
    'sucursal_id' => 'required|exists:sucursales,id',
    'monto' => '',
    'monto_efectivo' => '',
    'costo_envio' => 'required',
    'productos' => 'required|array',
    'cantidades' => 'required|array',
    'beneficios_ids' => 'array',
    'pago_tarjeta' => 'in:credito,debito',
    'pago_last4' => 'numeric|max:9999',
    'pago_tipo_tarjeta' => 'in:visa,mc,amex',
    'metodo_pago' => 'required',
    'recetas' => 'array',
    'facturacion_id' => 'exists:clientes_facturacion,id',
    'tarjeta_id' => 'exists:clientes_tarjetas,id',
    'promocion_id' => 'exists:promociones,id|nullable',
    'carrito_id' => 'exists:carritos,id',
    'programado_at' => 'required|date',
    'ciudad_cobertura_id' => 'required|exists:ciudades_cobertura,id',
    'observaciones' => 'nullable',
    'tipo_envio' => 'required|in:pickup,domicilio_propios',
  

 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
          "pedido": {
            "user_id": 8843,
            "cliente_direccion_id": 66123,
            "ciudad_cobertura_id": "1",
            "observaciones": null,
            "updated_at": "2020-05-26 00:06:54",
            "created_at": "2020-05-26 00:06:53",
            "id": 121012,
            "folio": "COM0121012",
            "programado_at": "2020-05-25 23:40:00",
            "usuario_erp": "APP",
            "pago": {
              "id": 121002,
              "pedido_id": 121012,
              "estado": "pendiente",
              "metodo_pago": "efectivo",
              "monto_efectivo": null,
              "monto": 131.25,
              "referencia": null,
              "created_at": "2020-05-26 00:06:53",
              "updated_at": "2020-05-26 00:06:53",
              "facturacion_id": null,
              "monto_farmapronto": null,
              "monto_nomicash": null
            },
            "envio": null,
            "estado": {
              "id": 1248181,
              "pedido_id": 121012,
              "paso": "programado",
              "nomicash": null,
              "created_at": "2020-05-26 00:06:53",
              "updated_at": "2020-05-26 00:06:53"
            },
            "direccion": {
              "id": 66123,
              "user_id": 18124,
              "estado_id": 17,
              "municipio_id": 502,
              "colonia_id": null,
              "colonia_str": "Lomas de la Selva",
              "calle": "Avenida Vicente Guerrero",
              "numero_interior": null,
              "numero_exterior": "205",
              "codigo_postal": "62270",
              "referencia": "dnnd",
              "tipo": "hospital",
              "lon": "-99.2303102",
              "lat": "18.9361035",
              "created_at": "2019-08-30 09:41:00",
              "updated_at": "2019-08-30 10:46:42",
              "deleted_at": null
            },
            "sucursales": [
              {
                "id": 96,
                "user_id": 152,
                "codigo": "200",
                "nombre": "ENLACE",
                "telefono": "7771010030",
                "colonia_id": 34755,
                "municipio_id": 502,
                "estado_id": 17,
                "zona_sucursal_id": 3,
                "ciudad_cobertura_id": null,
                "direccion": "AV. GASODUCTO",
                "direccion_numero": "S\/N",
                "codigo_postal": "62300",
                "lon": "-99.2097",
                "lat": "18.9598",
                "ancla": 0,
                "checkin": 1,
                "dias": "LUN, MAR, MIE, JUE, VIE, SAB, DOM",
                "horario_inicio": "06:00:00",
                "horario_final": "17:00:00",
                "24_hrs": 0,
                "base": 1,
                "almacen": 0,
                "comercializadora": 1,
                "pickup": 0,
                "domicilio_propios": 1,
                "domicilio_terceros": 0,
                "disponible": 0,
                "created_at": "2019-09-03 05:14:53",
                "updated_at": "2019-12-20 12:11:49",
                "deleted_at": null,
                "pivot": {
                  "pedido_id": 121012,
                  "sucursal_id": 96,
                  "aceptado": 1,
                  "rechazado": 0,
                  "activo": 1,
                  "orden": 1,
                  "created_at": "2020-05-26 00:06:53",
                  "updated_at": "2020-05-26 00:06:53"
                }
              }
            ],
            "pedido_productos": [
              {
                "id": 207812,
                "lista_precio_id": 573,
                "pedido_id": 121012,
                "precio": 35,
                "precio_dia": null,
                "cantidad": 5,
                "gratis": 0,
                "disponible": 0,
                "coincide": 1,
                "created_at": "2020-05-26 00:06:53",
                "updated_at": "2020-05-26 00:06:53",
                "despachado": 0,
                "promociones": [
                  {
                    "id": 2,
                    "pedido_producto_id": 207812,
                    "promocion_producto_id": 1140,
                    "tipo_nombre": "% Descuento",
                    "created_at": "2020-05-26 00:06:53",
                    "updated_at": "2020-05-26 00:06:53",
                    "promocion_producto": {
                      "id": 1140,
                      "promocion_id": 1140,
                      "producto_id": 815,
                      "cantidad": 4,
                      "monto": "25.00",
                      "created_at": "2020-05-25 15:49:05",
                      "updated_at": "2020-05-25 15:49:05",
                      "deleted_at": null,
                      "promocion": {
                        "id": 1140,
                        "activo": 1,
                        "nombre": "Compra 4 y recibe 25% de descuento",
                        "descripcion": "* 0001-4 AMOXILINA 500 MG C\/12 CAPSULAS",
                        "modo": "combinados",
                        "grupo": "G I FARMA",
                        "fabricante": "AMSA GI",
                        "started_at": "2020-05-25",
                        "finished_at": "2021-05-25",
                        "tipo_id": 7,
                        "created_at": "2020-05-25 15:49:05",
                        "updated_at": "2020-05-25 15:51:33",
                        "deleted_at": null
                      }
                    }
                  }
                ]
              }
            ]
          }
        }
 
 
 **Error Response:**

  * **Code:** 422 Unprocessable Entity <br />
    **Content:** 
    
        {
           "direccion_id": [
             "El campo direccion id es obligatorio cuando estado es ."
           ],
           "sucursal_id": [
             "El campo sucursal id es obligatorio."
           ],
           "costo_envio": [
             "El campo costo envio es obligatorio."
           ],
           "productos": [
             "El campo productos es obligatorio."
           ],
           "cantidades": [
             "El campo cantidades es obligatorio."
           ],
           "metodo_pago": [
             "El campo metodo pago es obligatorio."
           ],
           "programado_at": [
             "El campo programado at es obligatorio."
           ]
           "ciudad_cobertura_id": [
             "El campo ciudad cobertura id es obligatorio."
           ],
           "tipo_envio": [
             "El campo tipo envio es obligatorio."
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
        
  * **Code:** 417 Payload Too Large <br />
    **Content:**

        {
            "error": "No fue posible canjear la promoción"
        }
        

**Editar pedido**
----
  Regresa la información de un pedido editado

 **URL**

    /api-v2/clientes/pedidos/ID

 **Method:**

  `POST`
  
  **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data
      
      
 **Data Params**
    
    'cliente_direccion_id' => 'nullable|exists:clientes_direcciones,id',
    'programado_at' => 'nullable|date',
    'observaciones' => 'nullable',
  

 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        { 
            "pedido": {
              "id": 109461,
              "user_id": 23516,
              "cliente_direccion_id": 89165,
              "ciudad_cobertura_id": 1,
              "asistencia": 0,
              "alerta_cliente": 0,
              "folio": "APP0109461",
              "erp": 0,
              "usuario_erp": "APP",
              "codigo_confirmacion": null,
              "visto_callcenter": 0,
              "programado_at": "",
              "taxi": 0,
              "clon": 0,
              "pedidos_juntos": null,
              "cancelado_motivo": null,
              "cancelado_user_id": null,
              "observaciones": null,
              "liberado": null,
              "created_at": "2020-04-29 18:40:17",
              "updated_at": "2020-04-29 18:55:31",
              "deleted_at": null,
              "origen": null,
              "envio": {
                "id": 107266,
                "pedido_id": 109461,
                "sucursal_id": 22,
                "agente_id": null,
                "vehiculo_id": null,
                "tipo_envio": "pickup",
                "costo_envio": null,
                "codigo_verificacion": "8910",
                "aceptado": 1,
                "created_at": "2020-04-29 18:40:18",
                "updated_at": "2020-04-29 18:40:18",
                "delivery_at": null,
                "estimated_at": null,
                "outoftime": 0,
                "outoftime_notified": null,
                "tiempo_recoleccion": null,
                "tiempo_entrega": null,
                "taxi_cp_id": null,
                "km_entrega": null,
                "km_anterior": null,
                "lat": null,
                "lon": null,
                "en_ruta": 0,
                "en_ruta_at": null
              },
              "direccion": {
                "id": 89165,
                "user_id": 23516,
                "estado_id": 17,
                "municipio_id": 502,
                "colonia_id": null,
                "colonia_str": "LOMAS DE LA SELVA",
                "calle": "PROLONGACION AHUATEPEC",
                "numero_interior": null,
                "numero_exterior": "307",
                "codigo_postal": "62270",
                "referencia": "DIRECCIÓN PRUEBAS",
                "tipo": "OFICINA",
                "lon": "-99.2324802",
                "lat": "18.9361581",
                "created_at": "2020-04-21 15:42:07",
                "updated_at": "2020-04-21 15:42:07",
                "deleted_at": null
              },
              "sucursales": [
                {
                  "id": 22,
                  "user_id": 133,
                  "codigo": "24",
                  "nombre": "YY",
                  "telefono": "7772575916",
                  "colonia_id": 34661,
                  "municipio_id": 502,
                  "estado_id": 17,
                  "zona_sucursal_id": 4,
                  "ciudad_cobertura_id": 1,
                  "direccion": "AV.MORELOS SUR",
                  "direccion_numero": "157",
                  "codigo_postal": "62050",
                  "lon": "-99.23195740395204",
                  "lat": "18.90517509983967",
                  "ancla": 0,
                  "checkin": 1,
                  "dias": "LUN, MAR, MIE, JUE, VIE, SAB, DOM",
                  "horario_inicio": "07:00:00",
                  "horario_final": "23:00:00",
                  "24_hrs": 0,
                  "base": 0,
                  "almacen": 1,
                  "comercializadora": 1,
                  "pickup": 0,
                  "domicilio_propios": 1,
                  "domicilio_terceros": 0,
                  "disponible": 1,
                  "created_at": "2017-03-16 17:50:05",
                  "updated_at": "2020-04-29 13:22:23",
                  "deleted_at": null,
                  "pivot": {
                    "pedido_id": 109461,
                    "sucursal_id": 22,
                    "aceptado": 1,
                    "rechazado": 0,
                    "activo": 1,
                    "orden": 1,
                    "created_at": "2020-04-29 18:40:18",
                    "updated_at": "2020-04-29 18:40:18"
                  }
                }
              ],
              "pedido_productos": [
                {
                  "id": 187882,
                  "lista_precio_id": 32453,
                  "pedido_id": 109461,
                  "precio": 0.01,
                  "precio_dia": null,
                  "cantidad": 100,
                  "gratis": 0,
                  "disponible": 0,
                  "coincide": 1,
                  "created_at": "2020-04-29 18:40:18",
                  "updated_at": "2020-04-29 18:40:18",
                  "despachado": 0
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
             "programado_at": [
               "El campo programado at no es una fecha válida."
             ]
        }

  * **Code:** 401 Unauthorized <br />
    **Content:** 
    
        {
          "error": "Unauthenticated."
        }
       
       
     
     
     
**Datos del pedido**
----
  Regresa la información de una pedido del cliente y sus relaciones ejemplo: pedidoProcutos, listaPrecio

 **URL**

    /api-v2/clientes/pedidos/ID

 **Method:**

  `GET`
  
  **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data
      
  **URL Params**

  - includes[]=pedidoProductos.listaPrecio, pago, estado, envio  <br><br>
  Ejemplo URI: `api-v2/clientes/pedidos/5?includes[]=pedidoProductos.listaPrecio`
  

 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        { 
           "pedido": {
               "id": 108822,
               "user_id": 2363,
               "cliente_direccion_id": 66561,
               "ciudad_cobertura_id": 1,
               "asistencia": 0,
               "alerta_cliente": 0,
               "folio": "APP0108822",
               "erp": 0,
               "usuario_erp": "APP",
               "codigo_confirmacion": null,
               "visto_callcenter": 1,
               "programado_at": null,
               "taxi": 0,
               "clon": 0,
               "pedidos_juntos": "108822,108787",
               "cancelado_motivo": null,
               "cancelado_user_id": null,
               "observaciones": "entrega de medicamento ",
               "liberado": null,
               "created_at": "2020-03-15 12:44:36",
               "updated_at": "2020-03-15 12:46:49",
               "deleted_at": null,
               "origen": null,
               "pedido_productos": [
                 {
                   "id": 186793,
                   "lista_precio_id": 34020,
                   "pedido_id": 108822,
                   "precio": 0.01,
                   "precio_dia": null,
                   "cantidad": 1,
                   "gratis": 0,
                   "disponible": 0,
                   "coincide": 1,
                   "created_at": "2020-03-15 12:44:36",
                   "updated_at": "2020-03-15 12:44:36",
                   "despachado": 0,
                   "lista_precio": {
                     "id": 34020,
                     "zona_id": 22,
                     "producto_id": 64481,
                     "precio": 0.01,
                     "created_at": "2018-04-06 08:31:53",
                     "updated_at": "2018-04-06 08:31:53"
                   }
                 }
               ],
               "estados": [
                 {
                   "id": 1124412,
                   "pedido_id": 108822,
                   "paso": "liberado",
                   "nomicash": null,
                   "created_at": "2020-03-15 13:25:30",
                   "updated_at": "2020-03-15 13:25:30"
                 },
                 {
                   "id": 1124394,
                   "pedido_id": 108822,
                   "paso": "entregado",
                   "nomicash": null,
                   "created_at": "2020-03-15 13:15:52",
                   "updated_at": "2020-03-15 13:15:52"
                 },
                 {
                   "id": 1124393,
                   "pedido_id": 108822,
                   "paso": "llegando",
                   "nomicash": null,
                   "created_at": "2020-03-15 13:15:50",
                   "updated_at": "2020-03-15 13:15:50"
                 },
                 {
                   "id": 1124347,
                   "pedido_id": 108822,
                   "paso": "en transito",
                   "nomicash": null,
                   "created_at": "2020-03-15 12:50:38",
                   "updated_at": "2020-03-15 12:50:38"
                 },
                 {
                   "id": 1124343,
                   "pedido_id": 108822,
                   "paso": "embarcado-cr",
                   "nomicash": null,
                   "created_at": "2020-03-15 12:49:34",
                   "updated_at": "2020-03-15 12:49:34"
                 },
                 {
                   "id": 1124334,
                   "pedido_id": 108822,
                   "paso": "embarcado",
                   "nomicash": null,
                   "created_at": "2020-03-15 12:47:44",
                   "updated_at": "2020-03-15 12:47:44"
                 },
                 {
                   "id": 1124329,
                   "pedido_id": 108822,
                   "paso": "aceptado agente",
                   "nomicash": null,
                   "created_at": "2020-03-15 12:46:49",
                   "updated_at": "2020-03-15 12:46:49"
                 },
                 {
                   "id": 1124328,
                   "pedido_id": 108822,
                   "paso": "por embarcar",
                   "nomicash": null,
                   "created_at": "2020-03-15 12:46:15",
                   "updated_at": "2020-03-15 12:46:15"
                 },
                 {
                   "id": 1124325,
                   "pedido_id": 108822,
                   "paso": "aceptado",
                   "nomicash": null,
                   "created_at": "2020-03-15 12:45:01",
                   "updated_at": "2020-03-15 12:45:01"
                 },
                 {
                   "id": 1124324,
                   "pedido_id": 108822,
                   "paso": "recibido",
                   "nomicash": null,
                   "created_at": "2020-03-15 12:44:36",
                   "updated_at": "2020-03-15 12:44:36"
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

**Eliminar pedido**
----
  Elimina un pedido del cliente

 **URL**

    /api-v2/clientes/pedidos/ID

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
        
        

**Horarios para entrega de pedido**
----
  Regresa la lista de posibles horarios de entrega de pedido

 **URL**

    /api-v2/clientes/pedidos/horarios

 **Method:**

  `POST`
  
  **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data
      
      
 **Data Params**
    
    'tipo_envio' => 'required|in:domicilio,pickup',
    'sucursal_id' => 'required|exists:sucursales,id',
  

 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        { 
           "horarios": {
               "hoy": [
                 {
                   "programado_at": "2020-05-22 18:00:00",
                   "texto": "De 06:00 PM a 07:00 PM"
                 },
                 {
                   "programado_at": "2020-05-22 19:00:00",
                   "texto": "De 07:00 PM a 08:00 PM"
                 },
                 {
                   "programado_at": "2020-05-22 20:00:00",
                   "texto": "De 08:00 PM a 09:00 PM"
                 },
                 {
                   "programado_at": "2020-05-22 21:00:00",
                   "texto": "De 09:00 PM a 10:00 PM"
                 },
                 {
                   "programado_at": "2020-05-22 22:00:00",
                   "texto": "De 10:00 PM a 11:00 PM"
                 }
               ],
               "manana": [
                 {
                   "programado_at": "2020-05-23 07:00:00",
                   "texto": "De 07:00 AM a 08:00 AM"
                 },
                 {
                   "programado_at": "2020-05-23 08:00:00",
                   "texto": "De 08:00 AM a 09:00 AM"
                 },
                 {
                   "programado_at": "2020-05-23 09:00:00",
                   "texto": "De 09:00 AM a 10:00 AM"
                 },
                 {
                   "programado_at": "2020-05-23 10:00:00",
                   "texto": "De 10:00 AM a 11:00 AM"
                 },
                 {
                   "programado_at": "2020-05-23 11:00:00",
                   "texto": "De 11:00 AM a 12:00 PM"
                 },
                 {
                   "programado_at": "2020-05-23 12:00:00",
                   "texto": "De 12:00 PM a 01:00 PM"
                 },
                 {
                   "programado_at": "2020-05-23 13:00:00",
                   "texto": "De 01:00 PM a 02:00 PM"
                 },
                 {
                   "programado_at": "2020-05-23 14:00:00",
                   "texto": "De 02:00 PM a 03:00 PM"
                 },
                 {
                   "programado_at": "2020-05-23 15:00:00",
                   "texto": "De 03:00 PM a 04:00 PM"
                 },
                 {
                   "programado_at": "2020-05-23 16:00:00",
                   "texto": "De 04:00 PM a 05:00 PM"
                 },
                 {
                   "programado_at": "2020-05-23 17:00:00",
                   "texto": "De 05:00 PM a 06:00 PM"
                 },
                 {
                   "programado_at": "2020-05-23 18:00:00",
                   "texto": "De 06:00 PM a 07:00 PM"
                 },
                 {
                   "programado_at": "2020-05-23 19:00:00",
                   "texto": "De 07:00 PM a 08:00 PM"
                 },
                 {
                   "programado_at": "2020-05-23 20:00:00",
                   "texto": "De 08:00 PM a 09:00 PM"
                 },
                 {
                   "programado_at": "2020-05-23 21:00:00",
                   "texto": "De 09:00 PM a 10:00 PM"
                 },
                 {
                   "programado_at": "2020-05-23 22:00:00",
                   "texto": "De 10:00 PM a 11:00 PM"
                 }
               ]
           }
        }
 
 
 **Error Response:**

  * **Code:** 422 Unprocessable Entity <br />
    **Content:** 
    
        {
           "tipo_envio": [
             "El campo tipo envio es obligatorio."
           ],
           "sucursal_id": [
             "El campo sucursal id es obligatorio."
           ]
        }

  * **Code:** 401 Unauthorized <br />
    **Content:** 
    
        {
          "error": "Unauthenticated."
        }

**Costos de envíos pedido**
----
  Regresa el costo de envío de un pedido

 **URL**

    /api-v2/clientes/pedidos/costos

 **Method:**

  `POST`
  
  **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data
      
      
 **Data Params**
    
    'tipo_envio' => 'required|in:domicilio,pickup',
    'total' => 'required',
  

 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        { 
           "costo": 5
        }
 
 
 **Error Response:**

  * **Code:** 422 Unprocessable Entity <br />
    **Content:** 
    
        {
             "tipo_envio": [
               "El campo tipo envio es obligatorio."
             ],
             "total": [
               "El campo total es obligatorio."
             ]
        }

  * **Code:** 401 Unauthorized <br />
    **Content:** 
    
        {
          "error": "Unauthenticated."
        }

**Calificación pedido**
----
  Almacena la calificación de un pedido

 **URL**

    /api-v2/clientes/pedidos/ID/calificaciones

 **Method:**

  `POST`
  
  **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data
      
      
 **Data Params**
    
    'evaluado_id' => 'required|exists:users,id',
    'calificacion' => 'required',
    'comentario' => 'nullable|max:255',
  

 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        { 
             "pedido": {
               "id": 116760,
               "user_id": 25306,
               "cliente_direccion_id": 94195,
               "ciudad_cobertura_id": 1,
               "asistencia": 0,
               "alerta_cliente": 0,
               "folio": "APP0116760",
               "erp": 0,
               "traspaso": 0,
               "usuario_erp": "APP",
               "codigo_confirmacion": null,
               "visto_callcenter": 0,
               "programado_at": "2020-05-06 15:00:00",
               "taxi": 0,
               "clon": 0,
               "pedidos_juntos": null,
               "cancelado_motivo": null,
               "cancelado_user_id": null,
               "observaciones": null,
               "liberado": null,
               "created_at": "2020-05-06 13:12:54",
               "updated_at": "2020-05-06 13:12:55",
               "deleted_at": null,
               "origen": null
             },
             "calificacion": {
               "evaluado_id": "133",
               "calificacion": "5",
               "user_id": 25306,
               "pedido_id": 116760,
               "updated_at": "2020-05-08 14:31:44",
               "created_at": "2020-05-08 14:31:44",
               "id": 196196
             }
        }
 
 
 **Error Response:**

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