      
## Listado de incidencias tipo "Reparación" del agente
Regresa el listado de las incidencias tipo "Reparación" registradas por el agente

 **URL**

  /api/agentes/incidencias-reparacion

 **Method:**

  `GET`
  
 **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json

**URL Params**

  - includes[]= agente , motivo <br><br>
  Ejemplo URI: `api/agentes/incidencias-reparacion?includes[]=agente`
  
  
  * Nueva relaciones `incidenciaGasto.estatus` 
  
  donde devuelve el siguiente objeto
  
  
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
  		},



Donde pueden validar los diferentes estatus que contenga

  Estatus de incidencia_gasto
  
  
    pendiente, aprobada, rechazada, en-reparacion, revision, reportada, reparada


**Success Response:**

* **Code:** 200 <br />
  **Content:** 
  
      {
      	"incidencias": [
            {
              "id": 6968,
              "agente_id": 95,
              "folio": "RE6968",
              "fecha": "2019-05-16 00:00:00",
              "km": "",
              "km_evidencia": null,
              "motivo_id": 6,
              "vehiculo_id": 2,
              "observaciones": "gdfhrtrehrtehhehh",
              "evidencia": null,
              "proveedor_id": null,
              "tipo_creacion": "dashboard_store",
              "created_at": "2019-05-16 18:50:18",
              "updated_at": "2019-05-17 11:45:52",
              "motivo": {
                "id": 6,
                "nombre": "Reparación",
                "created_at": "2019-05-14 18:11:46",
                "updated_at": "2019-05-14 18:11:46"
              },
              "vehiculo": {
                "id": 2,
                "sucursal_id": 22,
                "placas": "M5ZV4",
                "modelo": "2017",
                "marca": "BAJAJ BOXER",
                "num_serie": "MD2A21BZ0HWG98454",
                "color": "ROJO",
                "num_poliza": "280228008",
                "ultimo_servicio": "2018-06-12",
                "bloqueado": 1,
                "created_at": "2017-11-29 17:52:16",
                "updated_at": "2019-05-07 10:36:14",
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

      
**Registro de incidencia reparación**
----
  Regresa la información del registro en formato json

 **URL**

  /api/agentes/incidencias-reparacion

 **Method:**

  `POST`
  
  **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data

 
 **Data Params**

 ***Required:***
    
     'fecha' => 'required|date',
     'motivo_id' => 'required|exists:catalogo_motivos_incidencias,id',
     'vehiculo_id' => 'nullable|exists:vehiculos,id',
     'observaciones' => 'nullable',
     'km' => 'nullable',
     'km_evidencia' => 'nullable|image',
     'evidencia' => 'nullable|image',
     'proveedor_id' => 'nullable',
     'gastos_ids' => 'nullable|array',
     'montos' => 'nullable|array',
     'tipo_creacion' => 'nullable|in:api_checkin,api_checkout,api_store',
     'mantenimiento_id' => 'nullable|exists:agentes_mantenimiento,id',


****Catalogo de motivos**** [/api/catalogos/incidencias-motivos](https://github.com/csagency/farmapronto/blob/develop/resources/docs/catalogos/incidencias-motivos.md)

 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
        	"incidencia": {
                "id": 6971,
                "agente_id": 95,
                "folio": "RE6971",
                "fecha": "2019-05-19 11:11:11",
                "km": null,
                "km_evidencia": null,
                "motivo_id": 6,
                "vehiculo_id": 1,
                "observaciones": null,
                "evidencia": null,
                "proveedor_id": null,
                "tipo_creacion": "api_agente",
                "created_at": "2019-05-20 10:40:59",
                "updated_at": "2019-05-20 10:40:59",
                "incidencia_gasto": {
                  "id": 6633,
                  "agente_incidencia_id": 6971,
                  "archivo_evidencia": null,
                  "archivo_ticket": null,
                  "num_ticket": null,
                  "factura": 0,
                  "monto": null,
                  "pagado": null,
                  "reposicion_datos": 0,
                  "litros_cargados": null,
                  "litros_aprobados": null,
                  "descripcion_sucursal": null,
                  "monto_sucursal": null,
                  "archivo_evidencia_sucursal": null,
                  "razon_improcedencia": null,
                  "razon_rechazo": null,
                  "tiempo_revision": null,
                  "tiempo_revision_tipo": null,
                  "tiempo_reparacion": null,
                  "tiempo_reparacion_tipo": null,
                  "created_at": "2019-05-20 10:40:59",
                  "updated_at": "2019-05-20 10:40:59",
                  "estatus": [
                    {
                      "id": 12,
                      "nombre": "Reportada",
                      "key": "reportada",
                      "created_at": "2019-05-14 18:11:46",
                      "updated_at": "2019-05-14 18:11:46",
                      "pivot": {
                        "incidencia_gasto_id": 6633,
                        "estatus_id": 12,
                        "created_at": "2019-05-20 10:40:59",
                        "updated_at": "2019-05-20 10:40:59"
                      }
                    }
                  ],
                  "gastos": []
                },
                "motivo": {
                  "id": 6,
                  "nombre": "Reparación",
                  "created_at": "2019-05-14 18:11:46",
                  "updated_at": "2019-05-14 18:11:46"
                },
                "vehiculo": null,
                "agente": {
                  "id": 95,
                  "user_id": 3050,
                  "numero_control": "4051",
                  "estatus": 1,
                  "puesto": null,
                  "created_at": "2018-07-04 11:12:45",
                  "updated_at": "2019-05-14 10:41:12",
                  "deleted_at": null,
                  "lat": "18.9284293",
                  "lon": "-98.9706133",
                  "imagen": null,
                  "imagen_path": null,
                  "vehiculo_id": 2,
                  "sucursal_base_id": 85,
                  "supervisor": 0,
                  "user": {
                    "id": 3050,
                    "name": "Raul",
                    "last_name": "Morales",
                    "second_last_name": "Rojas",
                    "telephone": "7352667625",
                    "clave": null,
                    "email": "repartidor112@grupofarmapronto.com",
                    "player_id": "45687df5-2434-4460-9f31-ca90863f21c8",
                    "activo": 1,
                    "baja": 0,
                    "fb_id": null,
                    "slack_webhook_url": null,
                    "created_at": "2018-07-04 11:12:45",
                    "updated_at": "2019-05-14 12:13:26",
                    "deleted_at": null,
                    "last_login": null
                  }
                }
            }
        }
        
 
 **Error Response:**

  * **Code:** 422 Unprocessable Entity <br />
    **Content:** 
    
        {
            "fecha": [
                "El campo fecha es obligatorio."
            ],
            "motivo_id": [
                "El campo motivo id es inválido."
            ]
        }


**Incidencia Show**
----
  Regresa la información de una incidencia registrada por el agente

 **URL**

  /api/agentes/incidencias/ID

 **Method:**

  `GET`
  
  **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data
      
  **URL Params**

  - includes[]= agente, motivo<br><br>
  Ejemplo URI: `api/agentes/incidencias/1?includes[]=agente`
  

 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
        	"incidencia": {
                "id": 6971,
                "agente_id": 95,
                "folio": "RE6971",
                "fecha": "2019-05-19 11:11:11",
                "km": null,
                "km_evidencia": null,
                "motivo_id": 6,
                "vehiculo_id": 1,
                "observaciones": null,
                "evidencia": null,
                "proveedor_id": null,
                "tipo_creacion": "api_agente",
                "created_at": "2019-05-20 10:40:59",
                "updated_at": "2019-05-20 10:40:59",
                "motivo": {
                  "id": 6,
                  "nombre": "Reparación",
                  "created_at": "2019-05-14 18:11:46",
                  "updated_at": "2019-05-14 18:11:46"
                },
                "vehiculo": {
                  "id": 1,
                  "sucursal_id": 84,
                  "placas": "CS-380",
                  "modelo": "YBR125C Express",
                  "marca": "Yamaha",
                  "num_serie": "",
                  "color": "",
                  "num_poliza": "",
                  "ultimo_servicio": "0000-00-00",
                  "bloqueado": 0,
                  "created_at": "2017-11-29 17:51:39",
                  "updated_at": "2019-05-06 17:07:17",
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


**Actualización de incidencia**
----
  Actualiza la información de una incidencia tipo reparación registrada por el agente

 **URL**

  /api/agentes/incidencias-reparacion/ID

 **Method:**

  `POST`
    
 **Headers**
 
    Authorization: Bearer access_token
    Accept: application/json
    Content-Type: multipart/form-data
    
 **Data Params**
 
  ***Required:***
     
        'fecha' => 'required|date',
        'motivo_id' => 'required|exists:catalogo_motivos_incidencias,id',
        'vehiculo_id' => 'nullable|exists:vehiculos,id',
        'observaciones' => 'nullable',
        'km' => 'nullable',
        'km_evidencia' => 'nullable|image',
        'evidencia' => 'nullable|image',
        'proveedor_id' => 'nullable',
        'gastos_ids' => 'nullable|array',
        'montos' => 'nullable|array',
        'tipo_creacion' => 'nullable|in:api_checkin,api_checkout,api_store',
        'mantenimiento_id' => 'nullable|exists:agentes_mantenimiento,id',
    
    ****Catalogo de motivos**** [/api/catalogos/incidencias-motivos](https://github.com/csagency/farmapronto/blob/develop/resources/docs/catalogos/incidencias-motivos.md)
 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
        	"incidencia": {
                "id": 6971,
                "agente_id": 95,
                "folio": "RE6971",
                "fecha": "2019-05-20 11:11:11",
                "km": null,
                "km_evidencia": null,
                "motivo_id": "6",
                "vehiculo_id": "1",
                "observaciones": null,
                "evidencia": null,
                "proveedor_id": null,
                "tipo_creacion": "api_agente",
                "created_at": "2019-05-20 10:40:59",
                "updated_at": "2019-05-20 11:34:02",
                "incidencia_gasto": {
                  "id": 6633,
                  "agente_incidencia_id": 6971,
                  "archivo_evidencia": null,
                  "archivo_ticket": null,
                  "num_ticket": null,
                  "factura": 0,
                  "monto": 0,
                  "pagado": null,
                  "reposicion_datos": 0,
                  "litros_cargados": null,
                  "litros_aprobados": null,
                  "descripcion_sucursal": null,
                  "monto_sucursal": null,
                  "archivo_evidencia_sucursal": null,
                  "razon_improcedencia": null,
                  "razon_rechazo": null,
                  "tiempo_revision": null,
                  "tiempo_revision_tipo": null,
                  "tiempo_reparacion": null,
                  "tiempo_reparacion_tipo": null,
                  "created_at": "2019-05-20 10:40:59",
                  "updated_at": "2019-05-20 11:33:50",
                  "estatus": [
                    {
                      "id": 12,
                      "nombre": "Reportada",
                      "key": "reportada",
                      "created_at": "2019-05-14 18:11:46",
                      "updated_at": "2019-05-14 18:11:46",
                      "pivot": {
                        "incidencia_gasto_id": 6633,
                        "estatus_id": 12,
                        "created_at": "2019-05-20 10:40:59",
                        "updated_at": "2019-05-20 10:40:59"
                      }
                    },
                    {
                      "id": 1,
                      "nombre": "Pendiente",
                      "key": "pendiente",
                      "created_at": "2019-05-14 18:11:46",
                      "updated_at": "2019-05-14 18:11:46",
                      "pivot": {
                        "incidencia_gasto_id": 6633,
                        "estatus_id": 1,
                        "created_at": "2019-05-20 11:35:17",
                        "updated_at": "2019-05-20 11:35:17"
                      }
                    }
                  ],
                  "gastos": [
                    {
                      "id": 2091,
                      "incidencia_gasto_id": 6633,
                      "catalogo_gasto_id": 191,
                      "monto": 10000,
                      "created_at": "2019-05-20 11:35:17",
                      "updated_at": "2019-05-20 11:35:17",
                      "tipo_gasto": {
                        "id": 191,
                        "nombre": "Prueba",
                        "motivo_id": 6,
                        "created_at": "2019-05-16 13:37:40",
                        "updated_at": "2019-05-16 13:37:40"
                      }
                    }
                  ]
                },
                "motivo": {
                  "id": 6,
                  "nombre": "Reparación",
                  "created_at": "2019-05-14 18:11:46",
                  "updated_at": "2019-05-14 18:11:46"
                },
                "vehiculo": {
                  "id": 1,
                  "sucursal_id": 84,
                  "placas": "CS-380",
                  "modelo": "YBR125C Express",
                  "marca": "Yamaha",
                  "num_serie": "",
                  "color": "",
                  "num_poliza": "",
                  "ultimo_servicio": "0000-00-00",
                  "bloqueado": 0,
                  "created_at": "2017-11-29 17:51:39",
                  "updated_at": "2019-05-06 17:07:17",
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

  * **Code:** 422 Unprocessable Entity <br />
    **Content:** 
    
        {
          "fecha": [
              "El campo fecha es obligatorio."
          ],
          "motivo_id": [
              "El campo motivo id es obligatorio."
          ]
          "gastos_ids": [
              "El campo gastos ids debe ser un conjunto."
          ],
          "montos": [
              "El campo montos debe ser un conjunto."
          ]
        }


**Eliminar incidencia**
----
  Elimina una incidencia en específico

 **URL**

  /api/agentes/incidencias/ID

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
        	"incidencia": null
        }

 **Error Responses:**

  * **Code:** 401 Unauthorized <br />
    **Content:** 
    
        {
          "error": "Unauthenticated."
        }
        


**Marcar como "Revisión" la incidencia**
----
  Añade el estatus "Revisión" a la incidencia

 **URL**

  /api/agentes/incidencias-reparacion/ID/revisar

 **Method:**

  `POST`
    
 **Headers**
 
    Authorization: Bearer access_token
    Accept: application/json
    Content-Type: multipart/form-data
    
 **Data Params**
 
  ***Required:***
     
        'tiempo_revision' => 'required',
        'tiempo_revision_tipo' => 'required|in:dias,horas',
    

 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
        	"incidencia": {
                "id": 6971,
                "agente_id": 95,
                "folio": "RE6971",
                "fecha": "2019-05-20 11:11:11",
                "km": null,
                "km_evidencia": null,
                "motivo_id": 6,
                "vehiculo_id": 1,
                "observaciones": null,
                "evidencia": null,
                "proveedor_id": null,
                "tipo_creacion": "api_agente",
                "created_at": "2019-05-20 10:40:59",
                "updated_at": "2019-05-20 11:34:02",
                "incidencia_gasto": {
                  "id": 6633,
                  "agente_incidencia_id": 6971,
                  "archivo_evidencia": null,
                  "archivo_ticket": null,
                  "num_ticket": null,
                  "factura": 0,
                  "monto": 0,
                  "pagado": null,
                  "reposicion_datos": 0,
                  "litros_cargados": null,
                  "litros_aprobados": null,
                  "descripcion_sucursal": null,
                  "monto_sucursal": null,
                  "archivo_evidencia_sucursal": null,
                  "razon_improcedencia": null,
                  "razon_rechazo": null,
                  "tiempo_revision": 1,
                  "tiempo_revision_tipo": "horas",
                  "tiempo_reparacion": null,
                  "tiempo_reparacion_tipo": null,
                  "created_at": "2019-05-20 10:40:59",
                  "updated_at": "2019-05-20 12:47:20",
                  "estatus": [
                    {
                      "id": 12,
                      "nombre": "Reportada",
                      "key": "reportada",
                      "created_at": "2019-05-14 18:11:46",
                      "updated_at": "2019-05-14 18:11:46",
                      "pivot": {
                        "incidencia_gasto_id": 6633,
                        "estatus_id": 12,
                        "created_at": "2019-05-20 10:40:59",
                        "updated_at": "2019-05-20 10:40:59"
                      }
                    },
                    {
                      "id": 1,
                      "nombre": "Pendiente",
                      "key": "pendiente",
                      "created_at": "2019-05-14 18:11:46",
                      "updated_at": "2019-05-14 18:11:46",
                      "pivot": {
                        "incidencia_gasto_id": 6633,
                        "estatus_id": 1,
                        "created_at": "2019-05-20 11:35:17",
                        "updated_at": "2019-05-20 11:35:17"
                      }
                    },
                    {
                      "id": 13,
                      "nombre": "Revisión",
                      "key": "revision",
                      "created_at": "2019-05-14 18:11:46",
                      "updated_at": "2019-05-14 18:11:46",
                      "pivot": {
                        "incidencia_gasto_id": 6633,
                        "estatus_id": 13,
                        "created_at": "2019-05-20 12:47:20",
                        "updated_at": "2019-05-20 12:47:20"
                      }
                    }
                  ],
                  "gastos": [
                    {
                      "id": 2091,
                      "incidencia_gasto_id": 6633,
                      "catalogo_gasto_id": 191,
                      "monto": 10000,
                      "created_at": "2019-05-20 11:35:17",
                      "updated_at": "2019-05-20 11:35:17",
                      "tipo_gasto": {
                        "id": 191,
                        "nombre": "Prueba",
                        "motivo_id": 6,
                        "created_at": "2019-05-16 13:37:40",
                        "updated_at": "2019-05-16 13:37:40"
                      }
                    }
                  ]
                },
                "motivo": {
                  "id": 6,
                  "nombre": "Reparación",
                  "created_at": "2019-05-14 18:11:46",
                  "updated_at": "2019-05-14 18:11:46"
                },
                "vehiculo": {
                  "id": 1,
                  "sucursal_id": 84,
                  "placas": "CS-380",
                  "modelo": "YBR125C Express",
                  "marca": "Yamaha",
                  "num_serie": "",
                  "color": "",
                  "num_poliza": "",
                  "ultimo_servicio": "0000-00-00",
                  "bloqueado": 0,
                  "created_at": "2017-11-29 17:51:39",
                  "updated_at": "2019-05-06 17:07:17",
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

  * **Code:** 422 Unprocessable Entity <br />
    **Content:** 
    
        {
            "tiempo_revision": [
              "El campo tiempo revision es obligatorio."
            ],
            "tiempo_revision_tipo": [
              "El campo tiempo revision tipo es obligatorio."
            ]
        }
             


**Marcar como "En Reparación" la incidencia**
----
  Añade el estatus "En Reparación" a la incidencia

 **URL**

  /api/agentes/incidencias-reparacion/ID/en-reparacion

 **Method:**

  `POST`
    
 **Headers**
 
    Authorization: Bearer access_token
    Accept: application/json
    Content-Type: multipart/form-data
    
 **Data Params**
 
  ***Required:***
     
        'tiempo_reparacion' => 'required',
        'tiempo_reparacion_tipo' => 'required|in:dias,horas',
    

 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
        	"incidencia": {
                "id": 6971,
                "agente_id": 95,
                "folio": "RE6971",
                "fecha": "2019-05-20 11:11:11",
                "km": null,
                "km_evidencia": null,
                "motivo_id": 6,
                "vehiculo_id": 1,
                "observaciones": null,
                "evidencia": null,
                "proveedor_id": null,
                "tipo_creacion": "api_agente",
                "created_at": "2019-05-20 10:40:59",
                "updated_at": "2019-05-20 11:34:02",
                "incidencia_gasto": {
                  "id": 6633,
                  "agente_incidencia_id": 6971,
                  "archivo_evidencia": null,
                  "archivo_ticket": null,
                  "num_ticket": null,
                  "factura": 0,
                  "monto": 0,
                  "pagado": null,
                  "reposicion_datos": 0,
                  "litros_cargados": null,
                  "litros_aprobados": null,
                  "descripcion_sucursal": null,
                  "monto_sucursal": null,
                  "archivo_evidencia_sucursal": null,
                  "razon_improcedencia": null,
                  "razon_rechazo": null,
                  "tiempo_revision": 1,
                  "tiempo_revision_tipo": "horas",
                  "tiempo_reparacion": 1,
                  "tiempo_reparacion_tipo": "horas",
                  "created_at": "2019-05-20 10:40:59",
                  "updated_at": "2019-05-20 12:53:38",
                  "estatus": [
                    {
                      "id": 12,
                      "nombre": "Reportada",
                      "key": "reportada",
                      "created_at": "2019-05-14 18:11:46",
                      "updated_at": "2019-05-14 18:11:46",
                      "pivot": {
                        "incidencia_gasto_id": 6633,
                        "estatus_id": 12,
                        "created_at": "2019-05-20 10:40:59",
                        "updated_at": "2019-05-20 10:40:59"
                      }
                    },
                    {
                      "id": 1,
                      "nombre": "Pendiente",
                      "key": "pendiente",
                      "created_at": "2019-05-14 18:11:46",
                      "updated_at": "2019-05-14 18:11:46",
                      "pivot": {
                        "incidencia_gasto_id": 6633,
                        "estatus_id": 1,
                        "created_at": "2019-05-20 11:35:17",
                        "updated_at": "2019-05-20 11:35:17"
                      }
                    },
                    {
                      "id": 13,
                      "nombre": "Revisión",
                      "key": "revision",
                      "created_at": "2019-05-14 18:11:46",
                      "updated_at": "2019-05-14 18:11:46",
                      "pivot": {
                        "incidencia_gasto_id": 6633,
                        "estatus_id": 13,
                        "created_at": "2019-05-20 12:47:20",
                        "updated_at": "2019-05-20 12:47:20"
                      }
                    },
                    {
                      "id": 2,
                      "nombre": "Aprobada",
                      "key": "aprobada",
                      "created_at": "2019-05-14 18:11:46",
                      "updated_at": "2019-05-14 18:11:46",
                      "pivot": {
                        "incidencia_gasto_id": 6633,
                        "estatus_id": 2,
                        "created_at": "2019-05-20 12:53:26",
                        "updated_at": "2019-05-20 12:53:26"
                      }
                    },
                    {
                      "id": 14,
                      "nombre": "En Reparación",
                      "key": "en-reparacion",
                      "created_at": "2019-05-14 18:11:46",
                      "updated_at": "2019-05-14 18:11:46",
                      "pivot": {
                        "incidencia_gasto_id": 6633,
                        "estatus_id": 14,
                        "created_at": "2019-05-20 12:53:38",
                        "updated_at": "2019-05-20 12:53:38"
                      }
                    }
                  ],
                  "gastos": [
                    {
                      "id": 2091,
                      "incidencia_gasto_id": 6633,
                      "catalogo_gasto_id": 191,
                      "monto": 10000,
                      "created_at": "2019-05-20 11:35:17",
                      "updated_at": "2019-05-20 11:35:17",
                      "tipo_gasto": {
                        "id": 191,
                        "nombre": "Prueba",
                        "motivo_id": 6,
                        "created_at": "2019-05-16 13:37:40",
                        "updated_at": "2019-05-16 13:37:40"
                      }
                    }
                  ]
                },
                "vehiculo": {
                  "id": 1,
                  "sucursal_id": 84,
                  "placas": "CS-380",
                  "modelo": "YBR125C Express",
                  "marca": "Yamaha",
                  "num_serie": "",
                  "color": "",
                  "num_poliza": "",
                  "ultimo_servicio": "0000-00-00",
                  "bloqueado": 1,
                  "created_at": "2017-11-29 17:51:39",
                  "updated_at": "2019-05-20 12:53:38",
                  "deleted_at": null
                },
                "motivo": {
                  "id": 6,
                  "nombre": "Reparación",
                  "created_at": "2019-05-14 18:11:46",
                  "updated_at": "2019-05-14 18:11:46"
                }
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
            "tiempo_reparacion": [
              "El campo tiempo reparacion es obligatorio."
            ],
            "tiempo_reparacion_tipo": [
              "El campo tiempo reparacion tipo es obligatorio."
            ]
        }
             
                        
  * **Code:** 409 Conflict <br />
  **Content:** 

        {
          "error": "No se pudo agregar el estatus. La incidencia no ha sido aprobada."
        }



**Marcar como "Reparada" la incidencia**
----
  Añade el estatus "Reparada" a la incidencia

 **URL**

  /api/agentes/incidencias-reparacion/ID/reparar

 **Method:**

  `POST`
    
 **Headers**
 
    Authorization: Bearer access_token
    Accept: application/json
    Content-Type: multipart/form-data
    
 **Data Params**
 
  ***Required:***
     
        'archivos_evidencia' => 'required|array',
    

 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
        	"incidencia": {
                "id": 6971,
                "agente_id": 95,
                "folio": "RE6971",
                "fecha": "2019-05-20 11:11:11",
                "km": null,
                "km_evidencia": null,
                "motivo_id": 6,
                "vehiculo_id": 1,
                "observaciones": null,
                "evidencia": null,
                "proveedor_id": null,
                "tipo_creacion": "api_agente",
                "created_at": "2019-05-20 10:40:59",
                "updated_at": "2019-05-20 11:34:02",
                "incidencia_gasto": {
                  "id": 6633,
                  "agente_incidencia_id": 6971,
                  "archivo_evidencia": null,
                  "archivo_ticket": null,
                  "num_ticket": null,
                  "factura": 0,
                  "monto": 0,
                  "pagado": null,
                  "reposicion_datos": 0,
                  "litros_cargados": null,
                  "litros_aprobados": null,
                  "descripcion_sucursal": null,
                  "monto_sucursal": null,
                  "archivo_evidencia_sucursal": null,
                  "razon_improcedencia": null,
                  "razon_rechazo": null,
                  "tiempo_revision": 1,
                  "tiempo_revision_tipo": "horas",
                  "tiempo_reparacion": 1,
                  "tiempo_reparacion_tipo": "horas",
                  "created_at": "2019-05-20 10:40:59",
                  "updated_at": "2019-05-20 12:53:38",
                  "estatus": [
                    {
                      "id": 12,
                      "nombre": "Reportada",
                      "key": "reportada",
                      "created_at": "2019-05-14 18:11:46",
                      "updated_at": "2019-05-14 18:11:46",
                      "pivot": {
                        "incidencia_gasto_id": 6633,
                        "estatus_id": 12,
                        "created_at": "2019-05-20 10:40:59",
                        "updated_at": "2019-05-20 10:40:59"
                      }
                    },
                    {
                      "id": 1,
                      "nombre": "Pendiente",
                      "key": "pendiente",
                      "created_at": "2019-05-14 18:11:46",
                      "updated_at": "2019-05-14 18:11:46",
                      "pivot": {
                        "incidencia_gasto_id": 6633,
                        "estatus_id": 1,
                        "created_at": "2019-05-20 11:35:17",
                        "updated_at": "2019-05-20 11:35:17"
                      }
                    },
                    {
                      "id": 13,
                      "nombre": "Revisión",
                      "key": "revision",
                      "created_at": "2019-05-14 18:11:46",
                      "updated_at": "2019-05-14 18:11:46",
                      "pivot": {
                        "incidencia_gasto_id": 6633,
                        "estatus_id": 13,
                        "created_at": "2019-05-20 12:47:20",
                        "updated_at": "2019-05-20 12:47:20"
                      }
                    },
                    {
                      "id": 2,
                      "nombre": "Aprobada",
                      "key": "aprobada",
                      "created_at": "2019-05-14 18:11:46",
                      "updated_at": "2019-05-14 18:11:46",
                      "pivot": {
                        "incidencia_gasto_id": 6633,
                        "estatus_id": 2,
                        "created_at": "2019-05-20 12:53:26",
                        "updated_at": "2019-05-20 12:53:26"
                      }
                    },
                    {
                      "id": 14,
                      "nombre": "En Reparación",
                      "key": "en-reparacion",
                      "created_at": "2019-05-14 18:11:46",
                      "updated_at": "2019-05-14 18:11:46",
                      "pivot": {
                        "incidencia_gasto_id": 6633,
                        "estatus_id": 14,
                        "created_at": "2019-05-20 12:53:38",
                        "updated_at": "2019-05-20 12:53:38"
                      }
                    },
                    {
                      "id": 15,
                      "nombre": "Reparada",
                      "key": "reparada",
                      "created_at": "2019-05-14 18:11:46",
                      "updated_at": "2019-05-14 18:11:46",
                      "pivot": {
                        "incidencia_gasto_id": 6633,
                        "estatus_id": 15,
                        "created_at": "2019-05-20 13:23:34",
                        "updated_at": "2019-05-20 13:23:34"
                      }
                    }
                  ],
                  "gastos": [
                    {
                      "id": 2091,
                      "incidencia_gasto_id": 6633,
                      "catalogo_gasto_id": 191,
                      "monto": 10000,
                      "created_at": "2019-05-20 11:35:17",
                      "updated_at": "2019-05-20 11:35:17",
                      "tipo_gasto": {
                        "id": 191,
                        "nombre": "Prueba",
                        "motivo_id": 6,
                        "created_at": "2019-05-16 13:37:40",
                        "updated_at": "2019-05-16 13:37:40"
                      }
                    }
                  ]
                },
                "vehiculo": {
                  "id": 1,
                  "sucursal_id": 84,
                  "placas": "CS-380",
                  "modelo": "YBR125C Express",
                  "marca": "Yamaha",
                  "num_serie": "",
                  "color": "",
                  "num_poliza": "",
                  "ultimo_servicio": "0000-00-00",
                  "bloqueado": 0,
                  "created_at": "2017-11-29 17:51:39",
                  "updated_at": "2019-05-20 13:23:34",
                  "deleted_at": null
                },
                "motivo": {
                  "id": 6,
                  "nombre": "Reparación",
                  "created_at": "2019-05-14 18:11:46",
                  "updated_at": "2019-05-14 18:11:46"
                }
            }
        }

 **Error Response:**

  * **Code:** 401 Unauthorized <br />
    **Content:** 
    
        {
          "error": "Unauthenticated."
        }
        
                 
  * **Code:** 409 Conflict <br />
  **Content:** 

        {
          "error": "No se pudo agregar el estatus. La incidencia no ha sido marcada como En Reparación."
        }


         
  * **Code:** 410 Gone <br />
  **Content:** 

        {
          "error": "Solamente pueden agregarse máximo 5 imágenes de evidencia."
        }


  * **Code:** 422 Unprocessable Entity <br />
    **Content:** 
    
        {
            "evidencias": [
              "El campo archivos evidencia es obligatorio."
            ]
        }
        



**Confirmar incidencia**
----

  #### Agrega estatus `confirmada` En indicencias gastos

  Actualización de los gastos relacionados a la incidencia

 **URL**

  /api/agentes/incidencias/ID/gastos

 **Method:**

  `POST`

 **Headers**

    Authorization: Bearer access_token
    Accept: application/json
    Content-Type: multipart/form-data

 **Data Params**

  ***Required:***

            'archivo_evidencia' => 'nullable|image',
            'archivo_ticket' => 'required|image',
            'monto' => 'required',
            'litros_cargados' => 'nullable',


 **Success Response:**

  * **Code:** 200 <br />
    **Content:**

        {
            "incidencia": {
                "id": 8546,
                "agente_id": 168,
                "folio": "RE8546",
                "fecha": "2019-06-25 13:59:05",
                "km": "615591",
                "km_evidencia": "uploads\/images\/incidencias\/5d126f0a3a89a.jpg",
                "motivo_id": 6,
                "vehiculo_id": 38,
                "observaciones": null,
                "evidencia": "uploads\/images\/incidencias\/5d126f09b7702.jpg",
                "proveedor_id": 0,
                "tipo_creacion": "api_store",
                "mantenimiento_id": null,
                "created_at": "2019-06-25 13:59:22",
                "updated_at": "2019-06-25 13:59:22",
                "deleted_at": null
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
           "error": "Model no Found."
         }


  * **Code:** 422 Unprocessable Entity <br />
    **Content:**

        {
          "archivo_evidencia": [
              "El campo archivo_evidencia es obligatorio."
          ],
          "archivo_ticket": [
              "El campo archivo_ticket es obligatorio."
          ],
          "monto": [
              "El campo archivo_ticket es obligatorio."
          ]
        }

