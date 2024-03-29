      
## Listado de incidencias de los agentes asignados a la sucursal

 **URL**

  /api/sucursales/me/incidencias

 **Method:**

  `GET`
  
 **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json

**URL Params**

  - includes[]= agente , motivo <br><br>
  Ejemplo URI: `api/sucursales/me/incidencias?includes[]=agente`
  
  

**Success Response:**

* **Code:** 200 <br />
  **Content:** 
  
  
      {
      	"incidencias": [
      		{
      			"id": 280,
      			"agente_id": 90,
      			"fecha": "2018-08-08 00:00:00",
      			"km": "120",
      			"motivo_id": 4,
      			"vehiculo_id": 1,
      			"observaciones": "prueba",
      			"evidencia": "uploads\/images\/incidencias\/Z7SYn4XlsNQ7oL4jeW30YAv0dfQoBP2FkNTpEc3k.png",
      			"created_at": "2018-08-09 13:59:47",
      			"updated_at": "2018-08-09 13:59:47",
      			"incidencia_gasto": {
      				"id": 5,
      				"agente_incidencia_id": 280,
      				"archivo_evidencia": null,
      				"archivo_ticket": null,
      				"monto": null,
      				"created_at": "2018-08-09 13:59:47",
      				"updated_at": "2018-08-09 13:59:47",
      				"estatus": [
      					{
      						"id": 1,
      						"nombre": "Pendiente",
      						"key": "pendiente",
      						"created_at": "2018-08-09 13:59:43",
      						"updated_at": "2018-08-09 13:59:43",
      						"pivot": {
      							"incidencia_gasto_id": 5,
      							"estatus_id": 1,
      							"created_at": "2018-08-09 13:59:47",
      							"updated_at": "2018-08-09 13:59:47"
      						}
      					}
      				]
      			}
      		},
      		{
      			"id": 281,
      			"agente_id": 90,
      			"fecha": "2018-08-08 00:00:00",
      			"km": "120",
      			"motivo_id": 4,
      			"vehiculo_id": 1,
      			"observaciones": "prueba",
      			"evidencia": "uploads\/images\/incidencias\/oeB9tuoh6vfmhe1UU7hOe22pDINYNbzR6hMQaNTS.png",
      			"created_at": "2018-08-09 14:00:24",
      			"updated_at": "2018-08-09 14:00:24",
      			"incidencia_gasto": {
      				"id": 6,
      				"agente_incidencia_id": 281,
      				"archivo_evidencia": null,
      				"archivo_ticket": null,
      				"monto": null,
      				"created_at": "2018-08-09 14:00:24",
      				"updated_at": "2018-08-09 14:00:24",
      				"estatus": [
      					{
      						"id": 1,
      						"nombre": "Pendiente",
      						"key": "pendiente",
      						"created_at": "2018-08-09 13:59:43",
      						"updated_at": "2018-08-09 13:59:43",
      						"pivot": {
      							"incidencia_gasto_id": 6,
      							"estatus_id": 1,
      							"created_at": "2018-08-09 14:00:25",
      							"updated_at": "2018-08-09 14:00:25"
      						}
      					}
      				]
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


## Incidencia Show

 **URL**

  /api/sucursales/me/incidencias/{id}?includes[]=incidenciaGasto.estatus

 **Method:**

  `GET`
  
 **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json

**URL Params**

  - includes[]= incidenciaGasto.estatus <br><br>
  
  

**Success Response:**

* **Code:** 200 <br />
  **Content:** 
  
  
          {
            "incidencia": {
                "id": 280,
                "agente_id": 90,
                "fecha": "2018-08-08 00:00:00",
                "km": "120",
                "motivo_id": 4,
                "vehiculo_id": 1,
                "observaciones": "prueba",
                "evidencia": "uploads\/images\/incidencias\/Z7SYn4XlsNQ7oL4jeW30YAv0dfQoBP2FkNTpEc3k.png",
                "created_at": "2018-08-09 13:59:47",
                "updated_at": "2018-08-09 13:59:47",
                "motivo": {
                    "id": 4,
                    "nombre": "Por gasolina",
                    "created_at": "2017-11-29 19:00:12",
                    "updated_at": "2017-11-29 19:00:12"
                },
                "vehiculo": {
                    "id": 1,
                    "sucursal_id": 80,
                    "placas": "CS-380",
                    "modelo": "YBR125C Express",
                    "marca": "Yamaha",
                    "num_serie": null,
                    "color": null,
                    "num_poliza": null,
                    "ultimo_servicio": null,
                    "created_at": "2017-11-29 17:51:39",
                    "updated_at": "2018-03-30 12:47:57",
                    "deleted_at": null
                },
                "incidencia_gasto": {
                    "id": 5,
                    "agente_incidencia_id": 280,
                    "archivo_evidencia": null,
                    "archivo_ticket": null,
                    "monto": null,
                    "created_at": "2018-08-09 13:59:47",
                    "updated_at": "2018-08-09 13:59:47",
                    "estatus": [
                        {
                            "id": 1,
                            "nombre": "Pendiente",
                            "key": "pendiente",
                            "created_at": "2018-08-09 13:59:43",
                            "updated_at": "2018-08-09 13:59:43",
                            "pivot": {
                                "incidencia_gasto_id": 5,
                                "estatus_id": 1,
                                "created_at": "2018-08-09 13:59:47",
                                "updated_at": "2018-08-09 13:59:47"
                            }
                        }
                    ]
                }
            }
          }

**Error Response:**

* **Code:** 401 Unauthorized <br />
  **Content:** 
  
      {
        "error": "Unauthenticated."
      }

* **Code:** 404 Not found <br />
  **Content:** 
  
      {
        "error": "Model not found."
      }



**Actualización de incidencia DEPRECATED**
----
  Actualiza el estatus de la incidencia agregando el estatus  `en-proceso` para notificar al repartidor o `confirmada` para finalizar proceso de incidencia

 **URL**

  /api/sucursales/me/incidencias/ID

 **Method:**

  `PUT`
    
 **Headers**
 
    Authorization: Bearer access_token
    Accept: application/json
    
 **Data Params**
 
  ***Required:***
     
    'estatus' => 'required|exists:incidencias_gastos_estatus,key'
    
 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
    
    
        {
        	"incidencia": {
        		"id": 280,
        		"agente_id": 90,
        		"fecha": "2018-08-08 00:00:00",
        		"km": "120",
        		"motivo_id": 4,
        		"vehiculo_id": 1,
        		"observaciones": "prueba",
        		"evidencia": "uploads\/images\/incidencias\/Z7SYn4XlsNQ7oL4jeW30YAv0dfQoBP2FkNTpEc3k.png",
        		"created_at": "2018-08-09 13:59:47",
        		"updated_at": "2018-08-09 13:59:47",
        		"incidencia_gasto": {
        			"id": 5,
        			"agente_incidencia_id": 280,
        			"archivo_evidencia": null,
        			"archivo_ticket": null,
        			"monto": null,
        			"created_at": "2018-08-09 13:59:47",
        			"updated_at": "2018-08-09 13:59:47",
        			"estatus": [
        				{
        					"id": 1,
        					"nombre": "Pendiente",
        					"key": "pendiente",
        					"created_at": "2018-08-09 13:59:43",
        					"updated_at": "2018-08-09 13:59:43",
        					"pivot": {
        						"incidencia_gasto_id": 5,
        						"estatus_id": 1,
        						"created_at": "2018-08-09 13:59:47",
        						"updated_at": "2018-08-09 13:59:47"
        					}
        				},
        				{
        					"id": 4,
        					"nombre": "En proceso",
        					"key": "en-proceso",
        					"created_at": "2018-08-09 13:59:43",
        					"updated_at": "2018-08-09 13:59:43",
        					"pivot": {
        						"incidencia_gasto_id": 5,
        						"estatus_id": 4,
        						"created_at": "2018-08-09 15:18:34",
        						"updated_at": "2018-08-09 15:18:34"
        					}
        				},
        				{
        					"id": 7,
        					"nombre": "Confirmada",
        					"key": "confirmada",
        					"created_at": "2018-08-09 13:59:43",
        					"updated_at": "2018-08-09 13:59:43",
        					"pivot": {
        						"incidencia_gasto_id": 5,
        						"estatus_id": 7,
        						"created_at": "2018-08-09 15:21:25",
        						"updated_at": "2018-08-09 15:21:25"
        					}
        				},
        				{
        					"id": 6,
        					"nombre": "Tarjeta devuelta",
        					"key": "tarjeta-devuelta",
        					"created_at": "2018-08-09 13:59:43",
        					"updated_at": "2018-08-09 13:59:43",
        					"pivot": {
        						"incidencia_gasto_id": 5,
        						"estatus_id": 6,
        						"created_at": "2018-08-09 15:21:25",
        						"updated_at": "2018-08-09 15:21:25"
        					}
        				},
        				{
        					"id": 7,
        					"nombre": "Confirmada",
        					"key": "confirmada",
        					"created_at": "2018-08-09 13:59:43",
        					"updated_at": "2018-08-09 13:59:43",
        					"pivot": {
        						"incidencia_gasto_id": 5,
        						"estatus_id": 7,
        						"created_at": "2018-08-09 15:21:25",
        						"updated_at": "2018-08-09 15:21:25"
        					}
        				}
        			]
        		},
        		"motivo": {
        			"id": 4,
        			"nombre": "Por gasolina",
        			"created_at": "2017-11-29 19:00:12",
        			"updated_at": "2017-11-29 19:00:12"
        		},
        		"vehiculo": {
        			"id": 1,
        			"sucursal_id": 80,
        			"placas": "CS-380",
        			"modelo": "YBR125C Express",
        			"marca": "Yamaha",
        			"num_serie": null,
        			"color": null,
        			"num_poliza": null,
        			"ultimo_servicio": null,
        			"created_at": "2017-11-29 17:51:39",
        			"updated_at": "2018-03-30 12:47:57",
        			"deleted_at": null
        		}
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
          "error": "Model not found."
        }

  * **Code:** 422 Unprocessable Entity <br />
    **Content:** 
    
        {
          "estatus": [
              "El campo estatus es obligatorio."
          ]
        }



        {
            "estatus": [
                "El campo estatus es inválido."
            ]
        }
        
**Actualización de incidencia UPDATE**
----
  Actualiza el estatus de la incidencia agregando el estatus  `en-proceso` para notificar al repartidor o `confirmada` para finalizar proceso de incidencia

 **URL**

  /api/sucursales/me/incidencias/ID

 **Method:**

  `POST`
    
 **Headers**
 
    Authorization: Bearer access_token
    Accept: application/json
    Content-Type: multipart/form-data
    
 **Data Params**
 
  ***Required:***
     
    'estatus' => 'required|exists:incidencias_gastos_estatus,key'
    'archivo_evidencia_sucursal' => 'image',
    'monto_sucursal' => 'nullable',
    'descripcion_sucursal' => 'nullable|max:200'
    
 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
    
    
        {
        	"incidencia": {
        		"id": 280,
        		"agente_id": 90,
        		"fecha": "2018-08-08 00:00:00",
        		"km": "120",
        		"motivo_id": 4,
        		"vehiculo_id": 1,
        		"observaciones": "prueba",
        		"evidencia": "uploads\/images\/incidencias\/Z7SYn4XlsNQ7oL4jeW30YAv0dfQoBP2FkNTpEc3k.png",
        		"created_at": "2018-08-09 13:59:47",
        		"updated_at": "2018-08-09 13:59:47",
        		"incidencia_gasto": {
        			"id": 5,
        			"agente_incidencia_id": 280,
        			"archivo_evidencia": null,
        			"archivo_ticket": null,
        			"monto": null,
        			"descripcion_sucursal": "KM 120, ok todo bien",
        			"monto_sucursal": 1000,
        			"archivo_evidencia_sucursal": "uploads\/images\/incidencias\/gastos\/tINSBjXcORv603UVydyLY6NqhsAIbL45iWfcaljs.png",
        			"razon_improcedencia": null,
        			"created_at": "2018-08-09 13:59:47",
        			"updated_at": "2018-08-21 11:58:50",
        			"estatus": [
        				{
        					"id": 1,
        					"nombre": "Pendiente",
        					"key": "pendiente",
        					"created_at": "2018-08-09 13:59:43",
        					"updated_at": "2018-08-09 13:59:43",
        					"pivot": {
        						"incidencia_gasto_id": 5,
        						"estatus_id": 1,
        						"created_at": "2018-08-09 13:59:47",
        						"updated_at": "2018-08-09 13:59:47"
        					}
        				},
        				{
        					"id": 4,
        					"nombre": "En proceso",
        					"key": "en-proceso",
        					"created_at": "2018-08-09 13:59:43",
        					"updated_at": "2018-08-09 13:59:43",
        					"pivot": {
        						"incidencia_gasto_id": 5,
        						"estatus_id": 4,
        						"created_at": "2018-08-09 15:18:34",
        						"updated_at": "2018-08-09 15:18:34"
        					}
        				},
        				{
        					"id": 7,
        					"nombre": "Confirmada",
        					"key": "confirmada",
        					"created_at": "2018-08-09 13:59:43",
        					"updated_at": "2018-08-09 13:59:43",
        					"pivot": {
        						"incidencia_gasto_id": 5,
        						"estatus_id": 7,
        						"created_at": "2018-08-09 15:21:25",
        						"updated_at": "2018-08-09 15:21:25"
        					}
        				},
        				{
        					"id": 6,
        					"nombre": "Tarjeta devuelta",
        					"key": "tarjeta-devuelta",
        					"created_at": "2018-08-09 13:59:43",
        					"updated_at": "2018-08-09 13:59:43",
        					"pivot": {
        						"incidencia_gasto_id": 5,
        						"estatus_id": 6,
        						"created_at": "2018-08-09 15:21:25",
        						"updated_at": "2018-08-09 15:21:25"
        					}
        				},
        				{
        					"id": 7,
        					"nombre": "Confirmada",
        					"key": "confirmada",
        					"created_at": "2018-08-09 13:59:43",
        					"updated_at": "2018-08-09 13:59:43",
        					"pivot": {
        						"incidencia_gasto_id": 5,
        						"estatus_id": 7,
        						"created_at": "2018-08-09 15:21:25",
        						"updated_at": "2018-08-09 15:21:25"
        					}
        				}
        			]
        		},
        		"motivo": {
        			"id": 4,
        			"nombre": "Por gasolina",
        			"created_at": "2017-11-29 19:00:12",
        			"updated_at": "2017-11-29 19:00:12"
        		},
        		"vehiculo": {
        			"id": 1,
        			"sucursal_id": 80,
        			"placas": "CS-380",
        			"modelo": "YBR125C Express",
        			"marca": "Yamaha",
        			"num_serie": null,
        			"color": null,
        			"num_poliza": null,
        			"ultimo_servicio": null,
        			"created_at": "2017-11-29 17:51:39",
        			"updated_at": "2018-03-30 12:47:57",
        			"deleted_at": null
        		}
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
          "error": "Model not found."
        }

  * **Code:** 422 Unprocessable Entity <br />
    **Content:** 
    
        {
          "estatus": [
              "El campo estatus es obligatorio."
          ]
        }



        {
            "estatus": [
                "El campo estatus es inválido."
            ]
        }