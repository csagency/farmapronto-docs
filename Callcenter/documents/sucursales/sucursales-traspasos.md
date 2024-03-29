      
## Listado de traspasos generados por la sucursal

 **URL**

  /api/sucursales/traspasos/

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
            "pedidos": [
                {
                    "id": 17522,
                    "user_id": 2429,
                    "cliente_direccion_id": 17795,
                    "asistencia": 0,
                    "alerta_cliente": 0,
                    "folio": "TRA0017522",
                    "erp": 0,
                    "codigo_confirmacion": null,
                    "visto_callcenter": 0,
                    "created_at": "2018-09-19 12:45:33",
                    "updated_at": "2018-09-19 12:45:34",
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
       
       
**Registro de nuevo traspaso**
----

 **URL**

  /api/sucursales/traspaso/

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
    'productos' => 'required',
    'cantidades' => 'required',
    'metodo_pago' => 'traspaso',
    'recetas[]' => 'array',

     

 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        
        
            {
            	"pedido": {
            		"user_id": 2429,
            		"cliente_direccion_id": 17795,
            		"updated_at": "2018-09-19 12:45:34",
            		"created_at": "2018-09-19 12:45:33",
            		"id": 17522,
            		"folio": "TRA0017522",
            		"pago": {
            			"id": 17522,
            			"pedido_id": 17522,
            			"estado": "pendiente",
            			"metodo_pago": "traspaso",
            			"monto_efectivo": null,
            			"monto": 92,
            			"referencia": null,
            			"created_at": "2018-09-19 12:45:34",
            			"updated_at": "2018-09-19 12:45:34",
            			"facturacion_id": null
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
            				"direccion": "AV. VICENTE GUERRERO",
            				"direccion_numero": "107",
            				"codigo_postal": "62230",
            				"lon": "-99.23085095421447",
            				"lat": "18.95742636448077",
            				"ancla": 1,
            				"dias": "LUN, MAR, MIE, JUE, VIE, SAB, DOM",
            				"horario_inicio": "07:00:00",
            				"horario_final": "22:59:00",
            				"created_at": "2017-03-16 17:50:05",
            				"updated_at": "2018-09-04 17:45:49",
            				"deleted_at": null,
            				"pivot": {
            					"pedido_id": 17522,
            					"sucursal_id": 1,
            					"aceptado": 0,
            					"rechazado": 0,
            					"activo": 0
            				}
            			},
            			{
            				"id": 4,
            				"user_id": 55,
            				"codigo": "4",
            				"nombre": "D",
            				"telefono": "3520",
            				"colonia_id": 35225,
            				"municipio_id": 828,
            				"estado_id": 17,
            				"direccion": "ALTAMIRANO LOCAL",
            				"direccion_numero": "10",
            				"codigo_postal": "62900",
            				"lon": "-99.177816",
            				"lat": "18.61430176",
            				"ancla": 0,
            				"dias": "LUN, MAR, MIE, JUE, VIE, SAB, DOM",
            				"horario_inicio": "07:00:00",
            				"horario_final": "23:00:00",
            				"created_at": "2017-03-16 17:50:05",
            				"updated_at": "2018-05-17 10:40:06",
            				"deleted_at": null,
            				"pivot": {
            					"pedido_id": 17522,
            					"sucursal_id": 4,
            					"aceptado": 0,
            					"rechazado": 0,
            					"activo": 0
            				}
            			},
            			{
            				"id": 5,
            				"user_id": 56,
            				"codigo": "5",
            				"nombre": "E",
            				"telefono": "7772576360",
            				"colonia_id": 35071,
            				"municipio_id": 494,
            				"estado_id": 17,
            				"direccion": "NO REELECCION",
            				"direccion_numero": "14",
            				"codigo_postal": "62744",
            				"lon": "-98.949395",
            				"lat": "18.822184",
            				"ancla": 0,
            				"dias": "LUN, MAR, MIE, JUE, VIE, SAB, DOM",
            				"horario_inicio": "07:00:00",
            				"horario_final": "21:59:00",
            				"created_at": "2017-03-16 17:50:05",
            				"updated_at": "2018-05-10 09:28:29",
            				"deleted_at": null,
            				"pivot": {
            					"pedido_id": 17522,
            					"sucursal_id": 5,
            					"aceptado": 0,
            					"rechazado": 0,
            					"activo": 0
            				}
            			},
            			{
            				"id": 8,
            				"user_id": 59,
            				"codigo": "8",
            				"nombre": "LL",
            				"telefono": "",
            				"colonia_id": 35225,
            				"municipio_id": 828,
            				"estado_id": 17,
            				"direccion": "JOSEFA ORTIZ DE DOMINGUEZ",
            				"direccion_numero": "111",
            				"codigo_postal": "62900",
            				"lon": "-99.1789312",
            				"lat": "18.6149723",
            				"ancla": 0,
            				"dias": "LUN, MAR, MIE, JUE, VIE, SAB, DOM",
            				"horario_inicio": "07:00:00",
            				"horario_final": "23:00:00",
            				"created_at": "2017-03-16 17:50:05",
            				"updated_at": "2018-06-08 15:15:23",
            				"deleted_at": null,
            				"pivot": {
            					"pedido_id": 17522,
            					"sucursal_id": 8,
            					"aceptado": 0,
            					"rechazado": 0,
            					"activo": 0
            				}
            			},
            			{
            				"id": 9,
            				"user_id": 60,
            				"codigo": "9",
            				"nombre": "M",
            				"telefono": "7772576373",
            				"colonia_id": 35015,
            				"municipio_id": 2345,
            				"estado_id": 17,
            				"direccion": "JARDIN DE JUAREZ",
            				"direccion_numero": "6",
            				"codigo_postal": "62730",
            				"lon": "-99.0608389",
            				"lat": "18.8855676",
            				"ancla": 0,
            				"dias": "LUN, MAR, MIE, JUE, VIE, SAB, DOM",
            				"horario_inicio": "07:00:00",
            				"horario_final": "21:59:00",
            				"created_at": "2017-03-16 17:50:05",
            				"updated_at": "2018-05-10 10:51:43",
            				"deleted_at": null,
            				"pivot": {
            					"pedido_id": 17522,
            					"sucursal_id": 9,
            					"aceptado": 0,
            					"rechazado": 0,
            					"activo": 0
            				}
            			}
            		],
            		"direccion": {
            			"id": 17795,
            			"user_id": 2429,
            			"estado_id": 17,
            			"municipio_id": 502,
            			"colonia_id": 34644,
            			"colonia_str": null,
            			"calle": "Sor Juana Ines de la cruz",
            			"numero_interior": null,
            			"numero_exterior": null,
            			"codigo_postal": "62010",
            			"referencia": null,
            			"tipo": "casa",
            			"lon": "-99.2465340346098",
            			"lat": "18.918896777705214",
            			"created_at": "2018-09-19 12:45:33",
            			"updated_at": "2018-09-19 12:45:33",
            			"deleted_at": null
            		},
            		"estado": {
            			"id": 182461,
            			"pedido_id": 17522,
            			"paso": "recibido",
            			"created_at": "2018-09-19 12:45:34",
            			"updated_at": "2018-09-19 12:45:34"
            		}
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
          
          

 
**Detalle del traspaso**
----

 **URL**

  /api/sucursales/traspasos/ID

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
                    "id": 17522,
                    "user_id": 2429,
                    "cliente_direccion_id": 17795,
                    "asistencia": 0,
                    "alerta_cliente": 0,
                    "folio": "TRA0017522",
                    "erp": 0,
                    "codigo_confirmacion": null,
                    "visto_callcenter": 0,
                    "created_at": "2018-09-19 12:45:33",
                    "updated_at": "2018-09-19 12:45:34",
                    "deleted_at": null
                }
            }
 
 **Error Response:**

  * **Code:** 401 Unauthorized <br />
    **Content:** 
    
        {
          "error": "Unauthenticated."
        }


      
## Confirmar traspaso
Sucursal confirma traspaso


 **URL**

  /api/sucursales/traspasos/{id}/confirmar

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
          	"pedido": {
          		"id": 17523,
          		"user_id": 2429,
          		"cliente_direccion_id": 17796,
          		"asistencia": 0,
          		"alerta_cliente": 0,
          		"folio": "TRA0017523",
          		"erp": 0,
          		"codigo_confirmacion": null,
          		"visto_callcenter": 0,
          		"created_at": "2018-09-19 13:07:57",
          		"updated_at": "2018-09-19 13:07:57",
          		"deleted_at": null,
          		"estados": [
          			{
          				"id": 182464,
          				"pedido_id": 17523,
          				"paso": "confirmacion entrega",
          				"created_at": "2018-09-19 14:24:31",
          				"updated_at": "2018-09-19 14:24:31"
          			},
          			{
          				"id": 182462,
          				"pedido_id": 17523,
          				"paso": "recibido",
          				"created_at": "2018-09-19 13:07:57",
          				"updated_at": "2018-09-19 13:07:57"
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
       
       