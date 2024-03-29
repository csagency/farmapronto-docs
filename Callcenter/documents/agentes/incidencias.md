      
## Listado de incidencias del agente
Regresa el listado de las incidencias registradas por el agente

 **URL**

  /api/agentes/incidencias/

 **Method:**

  `GET`
  
 **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json

 **Data Params**
    
     'vehiculo_id' => 'nullable|exists:vehiculos,id'
     
**URL Params**

  - includes[]= agente.user , motivo, incidenciaGasto.gastos.tipoGasto, incidenciaGasto.gastos.evidencias, incidenciaGasto.estatus, incidenciaGasto.evidencias.incidenciaGastoExtra, vehiculo.sucursal, proveedor, callCenter, alertas, check <br><br>
  Ejemplo URI: `api/agentes/incidencias?includes[]=incidenciaGasto.estatus&includes[]=incidenciaGasto.gastos.tipoGasto&includes[]=vehiculo.sucursal&includes[]=agente.user&includes[]=proveedor&includes[]=errorOperativo&sort[0][key]=id&sort[0][direction]=DESC`
  
  - vehiculo_id <br><br>
    Ejemplo URI: `api/agentes/incidencias?vehiculo_id=1`
  
  
  * Nueva relaciones `incidenciaGasto.estatus` 
  
  donde devuelve el siguiente objeto
  
  
            "incidencia_gasto": {
                    "id": 8501,
                    "agente_incidencia_id": 8839,
                    "archivo_evidencia": null,
                    "archivo_ticket": null,
                    "archivo_factura": null,
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
                    "rechazo_costos": 0,
                    "tiempo_revision": null,
                    "tiempo_revision_tipo": null,
                    "tiempo_reparacion": null,
                    "tiempo_reparacion_tipo": null,
                    "created_at": "2019-08-02 10:38:08",
                    "updated_at": "2019-08-02 10:38:08",
                    "estatus": [
                      {
                        "id": 1,
                        "nombre": "Pendiente",
                        "key": "pendiente",
                        "created_at": "2019-06-07 16:29:17",
                        "updated_at": "2019-06-07 16:29:17",
                        "deleted_at": null,
                        "pivot": {
                          "incidencia_gasto_id": 8501,
                          "estatus_id": 1,
                          "created_at": "2019-08-02 10:38:08",
                          "updated_at": "2019-08-02 10:38:08"
                        }
                      },
                      {
                        "id": 2,
                        "nombre": "Aprobada para cotizar",
                        "key": "aprobada",
                        "created_at": "2019-06-07 16:29:17",
                        "updated_at": "2019-08-01 17:28:43",
                        "deleted_at": null,
                        "pivot": {
                          "incidencia_gasto_id": 8501,
                          "estatus_id": 2,
                          "created_at": "2019-08-02 10:38:13",
                          "updated_at": "2019-08-02 10:38:08"
                        }
                      }
                    ],
                    "gastos": [
                      {
                        "id": 3800,
                        "incidencia_gasto_id": 8501,
                        "catalogo_gasto_id": 112,
                        "monto": 0,
                        "created_at": "2019-08-02 10:38:08",
                        "updated_at": "2019-08-02 10:38:08",
                        "tipo_gasto": {
                          "id": 112,
                          "nombre": "APOYO TAXI",
                          "motivo_id": 5,
                          "tiempo_vida": null,
                          "uso_promedio": null,
                          "tiempo_reparacion": null,
                          "created_at": "2019-04-25 16:03:41",
                          "updated_at": "2019-05-10 13:10:10"
                        }
                      },
                      {
                        "id": 3801,
                        "incidencia_gasto_id": 8501,
                        "catalogo_gasto_id": 210,
                        "monto": 0,
                        "created_at": "2019-08-02 10:38:08",
                        "updated_at": "2019-08-02 10:38:08",
                        "tipo_gasto": {
                          "id": 210,
                          "nombre": "Mano de Obra Mantenimiento Preventivo",
                          "motivo_id": 5,
                          "tiempo_vida": null,
                          "uso_promedio": null,
                          "tiempo_reparacion": null,
                          "created_at": "2019-05-24 13:26:12",
                          "updated_at": "2019-05-24 13:26:12"
                        }
                      }
                    ]
            }



Donde pueden validar los diferentes estatus que contenga

  Estatus de incidencia_gasto
  
  
    pendiente, aprobada, rechazada, confirmada, improcedente, validada, cotizada, reparada, rechazada-confirmar, lista-validar


**Success Response:**

* **Code:** 200 <br />
  **Content:** 
  
      {
      	"incidencias": [
                {
                  "id": 8839,
                  "agente_id": 28,
                  "folio": "GG8839",
                  "fecha": "2019-08-02 09:00:00",
                  "km": "100",
                  "km_evidencia": "uploads\/images\/incidencias\/HsW2l70Nx7N14L9ySuyOncnnN8S0womtgycZJQQK.png",
                  "motivo_id": 5,
                  "vehiculo_id": 42,
                  "observaciones": "hfgdjdj",
                  "evidencia": "uploads\/images\/incidencias\/IUhFLQ1ndD6pcS8M7SVdomNgyLyGVkssopolkhqg.png",
                  "proveedor_id": null,
                  "tipo_creacion": "dashboard_store",
                  "mantenimiento_id": null,
                  "created_at": "2019-08-02 10:38:08",
                  "updated_at": "2019-08-02 10:38:08",
                  "deleted_at": null,
                  "incidencia_gasto": {
                    "id": 8501,
                    "agente_incidencia_id": 8839,
                    "archivo_evidencia": null,
                    "archivo_ticket": null,
                    "archivo_factura": null,
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
                    "rechazo_costos": 0,
                    "tiempo_revision": null,
                    "tiempo_revision_tipo": null,
                    "tiempo_reparacion": null,
                    "tiempo_reparacion_tipo": null,
                    "created_at": "2019-08-02 10:38:08",
                    "updated_at": "2019-08-02 10:38:08",
                    "estatus": [
                      {
                        "id": 1,
                        "nombre": "Pendiente",
                        "key": "pendiente",
                        "created_at": "2019-06-07 16:29:17",
                        "updated_at": "2019-06-07 16:29:17",
                        "deleted_at": null,
                        "pivot": {
                          "incidencia_gasto_id": 8501,
                          "estatus_id": 1,
                          "created_at": "2019-08-02 10:38:08",
                          "updated_at": "2019-08-02 10:38:08"
                        }
                      },
                      {
                        "id": 2,
                        "nombre": "Aprobada para cotizar",
                        "key": "aprobada",
                        "created_at": "2019-06-07 16:29:17",
                        "updated_at": "2019-08-01 17:28:43",
                        "deleted_at": null,
                        "pivot": {
                          "incidencia_gasto_id": 8501,
                          "estatus_id": 2,
                          "created_at": "2019-08-02 10:38:13",
                          "updated_at": "2019-08-02 10:38:08"
                        }
                      }
                    ],
                    "gastos": [
                      {
                        "id": 3800,
                        "incidencia_gasto_id": 8501,
                        "catalogo_gasto_id": 112,
                        "monto": 0,
                        "created_at": "2019-08-02 10:38:08",
                        "updated_at": "2019-08-02 10:38:08",
                        "tipo_gasto": {
                          "id": 112,
                          "nombre": "APOYO TAXI",
                          "motivo_id": 5,
                          "tiempo_vida": null,
                          "uso_promedio": null,
                          "tiempo_reparacion": null,
                          "created_at": "2019-04-25 16:03:41",
                          "updated_at": "2019-05-10 13:10:10"
                        }
                      },
                      {
                        "id": 3801,
                        "incidencia_gasto_id": 8501,
                        "catalogo_gasto_id": 210,
                        "monto": 0,
                        "created_at": "2019-08-02 10:38:08",
                        "updated_at": "2019-08-02 10:38:08",
                        "tipo_gasto": {
                          "id": 210,
                          "nombre": "Mano de Obra Mantenimiento Preventivo",
                          "motivo_id": 5,
                          "tiempo_vida": null,
                          "uso_promedio": null,
                          "tiempo_reparacion": null,
                          "created_at": "2019-05-24 13:26:12",
                          "updated_at": "2019-05-24 13:26:12"
                        }
                      }
                    ]
                  },
                  "vehiculo": {
                    "id": 42,
                    "sucursal_id": 84,
                    "placas": "CS-381",
                    "modelo": "YBR125C Express",
                    "marca": "Yamaha",
                    "num_serie": "",
                    "color": "",
                    "num_poliza": "",
                    "ultimo_servicio": "0000-00-00",
                    "bloqueado": 0,
                    "created_at": "2019-04-29 13:10:43",
                    "updated_at": "2019-06-10 18:52:48",
                    "deleted_at": null,
                    "sucursal": {
                      "id": 84,
                      "user_id": 2429,
                      "codigo": "cs-2",
                      "nombre": "Sucursal CS NO ELIMINAR",
                      "telefono": "7777771234",
                      "colonia_id": 34641,
                      "municipio_id": 502,
                      "estado_id": 17,
                      "zona_sucursal_id": 3,
                      "ciudad_cobertura_id": null,
                      "direccion": "Ahuatepec 307",
                      "direccion_numero": "222222",
                      "codigo_postal": "62000",
                      "lon": "-99.228404",
                      "lat": "18.938236",
                      "ancla": 0,
                      "dias": "LUN, MAR, MIE, JUE, VIE",
                      "horario_inicio": "07:00:00",
                      "horario_final": "20:00:00",
                      "24_hrs": 0,
                      "base": 0,
                      "almacen": 0,
                      "created_at": "2018-11-30 13:45:25",
                      "updated_at": "2019-06-26 17:52:47",
                      "deleted_at": null
                    }
                  },
                  "agente": {
                    "id": 28,
                    "user_id": 164,
                    "numero_control": "0202",
                    "estatus": 0,
                    "puesto": null,
                    "created_at": "2018-01-10 13:10:55",
                    "updated_at": "2018-01-10 17:19:00",
                    "deleted_at": null,
                    "lat": "18.9359768",
                    "lon": "-99.2302717",
                    "imagen": null,
                    "imagen_path": null,
                    "vehiculo_id": null,
                    "sucursal_base_id": null,
                    "supervisor": 1,
                    "cant_errores_actuales": 0,
                    "user": {
                      "id": 164,
                      "name": "Supervisor",
                      "last_name": "Prueba",
                      "second_last_name": "Prueba",
                      "telephone": "77731020437",
                      "clave": "SUPRGSG9",
                      "email": "supervisor@farma.com",
                      "player_id": "9c5d1e43-8495-4180-883c-eebd50333741",
                      "tipo_usuario": "repartidor",
                      "activo": 0,
                      "baja": 0,
                      "fb_id": null,
                      "webhook_url": null,
                      "created_at": "2018-01-10 13:10:55",
                      "updated_at": "2019-07-24 13:15:59",
                      "deleted_at": null,
                      "last_login": null
                    }
                  },
                  "proveedor": null,
                  "error_operativo": null,
                  "motivo": {
                    "id": 5,
                    "nombre": "Gastos generales",
                    "key": "generales",
                    "prefix": "GG",
                    "created_at": "2019-05-21 13:28:24",
                    "updated_at": "2019-08-01 14:08:52"
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

  * **Code:** 422 Unprocessable Entity <br />
    **Content:** 
    
        {
            "vehiculo_id": [
               "El campo vehiculo id es inválido."
            ]
        }
      
**Registro de incidencia**
----
  Regresa la información del registro en formato json

 **URL**

  /api/agentes/incidencias/

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
                "id": 8843,
                "agente_id": 28,
                "folio": "GG8843",
                "fecha": "2019-08-02 12:12:12",
                "km": "1100",
                "km_evidencia": null,
                "motivo_id": 5,
                "vehiculo_id": 42,
                "observaciones": null,
                "evidencia": null,
                "proveedor_id": null,
                "tipo_creacion": "api_store",
                "mantenimiento_id": null,
                "created_at": "2019-08-02 13:21:24",
                "updated_at": "2019-08-02 13:21:24",
                "deleted_at": null,
                "motivo": {
                  "id": 5,
                  "nombre": "Gastos generales",
                  "key": "generales",
                  "prefix": "GG",
                  "created_at": "2019-05-21 13:28:24",
                  "updated_at": "2019-08-01 14:08:52"
                },
                "agente": {
                  "id": 28,
                  "user_id": 164,
                  "numero_control": "0202",
                  "estatus": 0,
                  "puesto": null,
                  "created_at": "2018-01-10 13:10:55",
                  "updated_at": "2018-01-10 17:19:00",
                  "deleted_at": null,
                  "lat": "18.9359768",
                  "lon": "-99.2302717",
                  "imagen": null,
                  "imagen_path": null,
                  "vehiculo_id": null,
                  "sucursal_base_id": null,
                  "supervisor": 1,
                  "cant_errores_actuales": 0,
                  "user": {
                    "id": 164,
                    "name": "Supervisor",
                    "last_name": "Prueba",
                    "second_last_name": "Prueba",
                    "telephone": "77731020437",
                    "clave": "SUPRGSG9",
                    "email": "supervisor@farma.com",
                    "player_id": "9c5d1e43-8495-4180-883c-eebd50333741",
                    "tipo_usuario": "repartidor",
                    "activo": 0,
                    "baja": 0,
                    "fb_id": null,
                    "webhook_url": null,
                    "created_at": "2018-01-10 13:10:55",
                    "updated_at": "2019-07-24 13:15:59",
                    "deleted_at": null,
                    "last_login": null
                  }
                },
                "vehiculo": {
                  "id": 42,
                  "sucursal_id": 84,
                  "placas": "CS-381",
                  "modelo": "YBR125C Express",
                  "marca": "Yamaha",
                  "num_serie": "",
                  "color": "",
                  "num_poliza": "",
                  "ultimo_servicio": "0000-00-00",
                  "bloqueado": 0,
                  "created_at": "2019-04-29 13:10:43",
                  "updated_at": "2019-06-10 18:52:48",
                  "deleted_at": null,
                  "sucursal": {
                    "id": 84,
                    "user_id": 2429,
                    "codigo": "cs-2",
                    "nombre": "Sucursal CS NO ELIMINAR",
                    "telefono": "7777771234",
                    "colonia_id": 34641,
                    "municipio_id": 502,
                    "estado_id": 17,
                    "zona_sucursal_id": 3,
                    "ciudad_cobertura_id": null,
                    "direccion": "Ahuatepec 307",
                    "direccion_numero": "222222",
                    "codigo_postal": "62000",
                    "lon": "-99.228404",
                    "lat": "18.938236",
                    "ancla": 0,
                    "dias": "LUN, MAR, MIE, JUE, VIE",
                    "horario_inicio": "07:00:00",
                    "horario_final": "20:00:00",
                    "24_hrs": 0,
                    "base": 0,
                    "almacen": 0,
                    "created_at": "2018-11-30 13:45:25",
                    "updated_at": "2019-06-26 17:52:47",
                    "deleted_at": null
                  }
                },
                "incidencia_gasto": {
                  "id": 8505,
                  "agente_incidencia_id": 8843,
                  "archivo_evidencia": null,
                  "archivo_ticket": null,
                  "archivo_factura": null,
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
                  "rechazo_costos": 0,
                  "tiempo_revision": null,
                  "tiempo_revision_tipo": null,
                  "tiempo_reparacion": null,
                  "tiempo_reparacion_tipo": null,
                  "created_at": "2019-08-02 13:21:24",
                  "updated_at": "2019-08-02 13:21:24",
                  "estatus": [
                    {
                      "id": 1,
                      "nombre": "Pendiente",
                      "key": "pendiente",
                      "created_at": "2019-06-07 16:29:17",
                      "updated_at": "2019-06-07 16:29:17",
                      "deleted_at": null,
                      "pivot": {
                        "incidencia_gasto_id": 8505,
                        "estatus_id": 1,
                        "created_at": "2019-08-02 13:21:24",
                        "updated_at": "2019-08-02 13:21:24"
                      }
                    }
                  ],
                  "gastos": [
                    {
                      "id": 3804,
                      "incidencia_gasto_id": 8505,
                      "catalogo_gasto_id": 210,
                      "monto": 0,
                      "created_at": "2019-08-02 13:21:24",
                      "updated_at": "2019-08-02 13:21:24",
                      "tipo_gasto": {
                        "id": 210,
                        "nombre": "Mano de Obra Mantenimiento Preventivo",
                        "motivo_id": 5,
                        "tiempo_vida": null,
                        "uso_promedio": null,
                        "tiempo_reparacion": null,
                        "created_at": "2019-05-24 13:26:12",
                        "updated_at": "2019-05-24 13:26:12"
                      }
                    },
                    {
                      "id": 3805,
                      "incidencia_gasto_id": 8505,
                      "catalogo_gasto_id": 112,
                      "monto": 0,
                      "created_at": "2019-08-02 13:21:24",
                      "updated_at": "2019-08-02 13:21:24",
                      "tipo_gasto": {
                        "id": 112,
                        "nombre": "APOYO TAXI",
                        "motivo_id": 5,
                        "tiempo_vida": null,
                        "uso_promedio": null,
                        "tiempo_reparacion": null,
                        "created_at": "2019-04-25 16:03:41",
                        "updated_at": "2019-05-10 13:10:10"
                      }
                    }
                  ]
                },
                "proveedor": null,
                "error_operativo": null,
                "call_center": []
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
            "evidencia": [
                "evidencia debe ser una imagen."
            ]
        }
        
           
  * **Code:** 409 Conflict <br />
  **Content:** 

        {
          "error": "El kilometraje no coincide. Favor de verificar."
        }
        
 * **Code:** 410 Gone <br />
  **Content:** 

        {
          "error": "No se ha realizado checkin del vehículo."
        }

 * **Code:** 411 Length Required <br />
  **Content:** 

        {
          "error": "¡ERROR! Se debe agregar otro gasto adicional a Mano de obra."
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

  - includes[]= agente.user , motivo, incidenciaGasto.gastos.tipoGasto, incidenciaGasto.estatus, vehiculo.sucursal, proveedor, callCenter, alertas, check <br><br>
  Ejemplo URI: `api/agentes/incidencias/1?includes[]=incidenciaGasto.estatus&includes[]=incidenciaGasto.gastos.tipoGasto&includes[]=vehiculo.sucursal&includes[]=agente.user&includes[]=proveedor&includes[]=errorOperativo&includes[]=callCenter&includes[]=alertas&includes[]=check`
  

 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
            "incidencia": {
                "id": 8843,
                "agente_id": 28,
                "folio": "GG8843",
                "fecha": "2019-08-02 12:12:12",
                "km": "1100",
                "km_evidencia": null,
                "motivo_id": 5,
                "vehiculo_id": 42,
                "observaciones": null,
                "evidencia": null,
                "proveedor_id": null,
                "tipo_creacion": "api_store",
                "mantenimiento_id": null,
                "created_at": "2019-08-02 13:21:24",
                "updated_at": "2019-08-02 13:21:24",
                "deleted_at": null,
                "motivo": {
                  "id": 5,
                  "nombre": "Gastos generales",
                  "key": "generales",
                  "prefix": "GG",
                  "created_at": "2019-05-21 13:28:24",
                  "updated_at": "2019-08-01 14:08:52"
                },
                "vehiculo": {
                  "id": 42,
                  "sucursal_id": 84,
                  "placas": "CS-381",
                  "modelo": "YBR125C Express",
                  "marca": "Yamaha",
                  "num_serie": "",
                  "color": "",
                  "num_poliza": "",
                  "ultimo_servicio": "0000-00-00",
                  "bloqueado": 0,
                  "created_at": "2019-04-29 13:10:43",
                  "updated_at": "2019-06-10 18:52:48",
                  "deleted_at": null,
                  "sucursal": {
                    "id": 84,
                    "user_id": 2429,
                    "codigo": "cs-2",
                    "nombre": "Sucursal CS NO ELIMINAR",
                    "telefono": "7777771234",
                    "colonia_id": 34641,
                    "municipio_id": 502,
                    "estado_id": 17,
                    "zona_sucursal_id": 3,
                    "ciudad_cobertura_id": null,
                    "direccion": "Ahuatepec 307",
                    "direccion_numero": "222222",
                    "codigo_postal": "62000",
                    "lon": "-99.228404",
                    "lat": "18.938236",
                    "ancla": 0,
                    "dias": "LUN, MAR, MIE, JUE, VIE",
                    "horario_inicio": "07:00:00",
                    "horario_final": "20:00:00",
                    "24_hrs": 0,
                    "base": 0,
                    "almacen": 0,
                    "created_at": "2018-11-30 13:45:25",
                    "updated_at": "2019-06-26 17:52:47",
                    "deleted_at": null
                  }
                },
                "incidencia_gasto": {
                  "id": 8505,
                  "agente_incidencia_id": 8843,
                  "archivo_evidencia": null,
                  "archivo_ticket": null,
                  "archivo_factura": null,
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
                  "rechazo_costos": 0,
                  "tiempo_revision": null,
                  "tiempo_revision_tipo": null,
                  "tiempo_reparacion": null,
                  "tiempo_reparacion_tipo": null,
                  "created_at": "2019-08-02 13:21:24",
                  "updated_at": "2019-08-02 13:21:24",
                  "gastos": [
                    {
                      "id": 3804,
                      "incidencia_gasto_id": 8505,
                      "catalogo_gasto_id": 210,
                      "monto": 0,
                      "created_at": "2019-08-02 13:21:24",
                      "updated_at": "2019-08-02 13:21:24",
                      "tipo_gasto": {
                        "id": 210,
                        "nombre": "Mano de Obra Mantenimiento Preventivo",
                        "motivo_id": 5,
                        "tiempo_vida": null,
                        "uso_promedio": null,
                        "tiempo_reparacion": null,
                        "created_at": "2019-05-24 13:26:12",
                        "updated_at": "2019-05-24 13:26:12"
                      }
                    },
                    {
                      "id": 3805,
                      "incidencia_gasto_id": 8505,
                      "catalogo_gasto_id": 112,
                      "monto": 0,
                      "created_at": "2019-08-02 13:21:24",
                      "updated_at": "2019-08-02 13:21:24",
                      "tipo_gasto": {
                        "id": 112,
                        "nombre": "APOYO TAXI",
                        "motivo_id": 5,
                        "tiempo_vida": null,
                        "uso_promedio": null,
                        "tiempo_reparacion": null,
                        "created_at": "2019-04-25 16:03:41",
                        "updated_at": "2019-05-10 13:10:10"
                      }
                    }
                  ],
                  "estatus": [
                    {
                      "id": 1,
                      "nombre": "Pendiente",
                      "key": "pendiente",
                      "created_at": "2019-06-07 16:29:17",
                      "updated_at": "2019-06-07 16:29:17",
                      "deleted_at": null,
                      "pivot": {
                        "incidencia_gasto_id": 8505,
                        "estatus_id": 1,
                        "created_at": "2019-08-02 13:21:24",
                        "updated_at": "2019-08-02 13:21:24"
                      }
                    }
                  ]
                },
                "agente": {
                  "id": 28,
                  "user_id": 164,
                  "numero_control": "0202",
                  "estatus": 0,
                  "puesto": null,
                  "created_at": "2018-01-10 13:10:55",
                  "updated_at": "2018-01-10 17:19:00",
                  "deleted_at": null,
                  "lat": "18.9359768",
                  "lon": "-99.2302717",
                  "imagen": null,
                  "imagen_path": null,
                  "vehiculo_id": null,
                  "sucursal_base_id": null,
                  "supervisor": 1,
                  "cant_errores_actuales": 0,
                  "user": {
                    "id": 164,
                    "name": "Supervisor",
                    "last_name": "Prueba",
                    "second_last_name": "Prueba",
                    "telephone": "77731020437",
                    "clave": "SUPRGSG9",
                    "email": "supervisor@farma.com",
                    "player_id": "9c5d1e43-8495-4180-883c-eebd50333741",
                    "tipo_usuario": "repartidor",
                    "activo": 0,
                    "baja": 0,
                    "fb_id": null,
                    "webhook_url": null,
                    "created_at": "2018-01-10 13:10:55",
                    "updated_at": "2019-07-24 13:15:59",
                    "deleted_at": null,
                    "last_login": null
                  }
                },
                "proveedor": null,
                "error_operativo": null,
                "call_center": [],
                "alertas": [],
                "check": null
            }
        }
 
 **Error Response:**

  * **Code:** 401 Unauthorized <br />
    **Content:** 
    
        {
          "error": "Unauthenticated."
        }


**Actualización de incidencia (No funcional)**
----
  Actualiza la información de una incidencia registrada por el agente

 **URL**

  /api/agentes/incidencias/ID

 **Method:**

  `PUT`
    
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
                "id": 5,
                "agente_id": 21,
                "fecha": "2017-11-29",
                "motivo_id": "1",
                "observaciones": "Llanta ponchada",
                "evidencia": "incidencias\/E8EtpYxkn8diYgUynN09tqbDoXSe1JbXR1iK5kIE.png",
                "created_at": "2017-11-30 14:06:09",
                "updated_at": "2017-11-30 14:07:41",
                "motivo": {
                    "id": 1,
                    "nombre": "Llantas",
                    "created_at": "2017-11-29 13:39:03",
                    "updated_at": "2017-11-29 13:39:03"
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
          "evidencia": [
              "evidencia debe ser una imagen."
          ],
          "km_evidencia": [
             "km evidencia debe ser una imagen."
          ],
          "gastos_ids": [
              "El campo gastos ids debe ser un conjunto."
          ],
          "montos": [
              "El campo montos debe ser un conjunto."
          ]
        }


  * **Code:** 409 Conflict <br />
  **Content:** 

        {
          "error": "El kilometraje ingresado es inválido. Es mínimo al anterior."
        }
          

**Añadir costos de reparación**
----

  #### Agrega estatus `cotizada` en indicencias gastos

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

        'proveedor_id' => 'nullable',
        'gastos_ids' => 'required|array',
        'montos' => 'required|array',
        'monto' => 'required',
        'litros_cargados' => 'nullable',


 **Success Response:**

  * **Code:** 200 <br />
    **Content:**

        {
            "incidencia": {
                "id": 8843,
                "agente_id": 28,
                "folio": "GG8843",
                "fecha": "2019-08-02 12:12:12",
                "km": "1100",
                "km_evidencia": null,
                "motivo_id": 5,
                "vehiculo_id": 42,
                "observaciones": null,
                "evidencia": null,
                "proveedor_id": null,
                "tipo_creacion": "api_store",
                "mantenimiento_id": null,
                "created_at": "2019-08-02 13:21:24",
                "updated_at": "2019-08-02 13:21:24",
                "deleted_at": null,
                "agente": {
                  "id": 28,
                  "user_id": 164,
                  "numero_control": "0202",
                  "estatus": 0,
                  "puesto": null,
                  "created_at": "2018-01-10 13:10:55",
                  "updated_at": "2018-01-10 17:19:00",
                  "deleted_at": null,
                  "lat": "18.9359768",
                  "lon": "-99.2302717",
                  "imagen": null,
                  "imagen_path": null,
                  "vehiculo_id": null,
                  "sucursal_base_id": null,
                  "supervisor": 1,
                  "cant_errores_actuales": 0,
                  "user": {
                    "id": 164,
                    "name": "Supervisor",
                    "last_name": "Prueba",
                    "second_last_name": "Prueba",
                    "telephone": "77731020437",
                    "clave": "SUPRGSG9",
                    "email": "supervisor@farma.com",
                    "player_id": "9c5d1e43-8495-4180-883c-eebd50333741",
                    "tipo_usuario": "repartidor",
                    "activo": 0,
                    "baja": 0,
                    "fb_id": null,
                    "webhook_url": null,
                    "created_at": "2018-01-10 13:10:55",
                    "updated_at": "2019-07-24 13:15:59",
                    "deleted_at": null,
                    "last_login": null
                  }
                },
                "motivo": {
                  "id": 5,
                  "nombre": "Gastos generales",
                  "key": "generales",
                  "prefix": "GG",
                  "created_at": "2019-05-21 13:28:24",
                  "updated_at": "2019-08-01 14:08:52"
                },
                "vehiculo": {
                  "id": 42,
                  "sucursal_id": 84,
                  "placas": "CS-381",
                  "modelo": "YBR125C Express",
                  "marca": "Yamaha",
                  "num_serie": "",
                  "color": "",
                  "num_poliza": "",
                  "ultimo_servicio": "0000-00-00",
                  "bloqueado": 0,
                  "created_at": "2019-04-29 13:10:43",
                  "updated_at": "2019-06-10 18:52:48",
                  "deleted_at": null,
                  "sucursal": {
                    "id": 84,
                    "user_id": 2429,
                    "codigo": "cs-2",
                    "nombre": "Sucursal CS NO ELIMINAR",
                    "telefono": "7777771234",
                    "colonia_id": 34641,
                    "municipio_id": 502,
                    "estado_id": 17,
                    "zona_sucursal_id": 3,
                    "ciudad_cobertura_id": null,
                    "direccion": "Ahuatepec 307",
                    "direccion_numero": "222222",
                    "codigo_postal": "62000",
                    "lon": "-99.228404",
                    "lat": "18.938236",
                    "ancla": 0,
                    "dias": "LUN, MAR, MIE, JUE, VIE",
                    "horario_inicio": "07:00:00",
                    "horario_final": "20:00:00",
                    "24_hrs": 0,
                    "base": 0,
                    "almacen": 0,
                    "created_at": "2018-11-30 13:45:25",
                    "updated_at": "2019-06-26 17:52:47",
                    "deleted_at": null
                  }
                },
                "incidencia_gasto": {
                  "id": 8505,
                  "agente_incidencia_id": 8843,
                  "archivo_evidencia": null,
                  "archivo_ticket": null,
                  "archivo_factura": null,
                  "num_ticket": null,
                  "factura": 0,
                  "monto": 50000,
                  "pagado": null,
                  "reposicion_datos": 0,
                  "litros_cargados": null,
                  "litros_aprobados": null,
                  "descripcion_sucursal": null,
                  "monto_sucursal": null,
                  "archivo_evidencia_sucursal": null,
                  "razon_improcedencia": null,
                  "razon_rechazo": null,
                  "rechazo_costos": 0,
                  "tiempo_revision": null,
                  "tiempo_revision_tipo": null,
                  "tiempo_reparacion": null,
                  "tiempo_reparacion_tipo": null,
                  "created_at": "2019-08-02 13:21:24",
                  "updated_at": "2019-08-02 13:54:42",
                  "estatus": [
                    {
                      "id": 1,
                      "nombre": "Pendiente",
                      "key": "pendiente",
                      "created_at": "2019-06-07 16:29:17",
                      "updated_at": "2019-06-07 16:29:17",
                      "deleted_at": null,
                      "pivot": {
                        "incidencia_gasto_id": 8505,
                        "estatus_id": 1,
                        "created_at": "2019-08-02 13:21:24",
                        "updated_at": "2019-08-02 13:21:24"
                      }
                    },
                    {
                      "id": 2,
                      "nombre": "Aprobada para cotizar",
                      "key": "aprobada",
                      "created_at": "2019-06-07 16:29:17",
                      "updated_at": "2019-08-01 17:28:43",
                      "deleted_at": null,
                      "pivot": {
                        "incidencia_gasto_id": 8505,
                        "estatus_id": 2,
                        "created_at": "2019-08-02 13:31:24",
                        "updated_at": "2019-08-02 13:21:24"
                      }
                    },
                    {
                      "id": 10,
                      "nombre": "Cotizada",
                      "key": "cotizada",
                      "created_at": "2019-06-07 16:29:17",
                      "updated_at": "2019-06-07 16:29:17",
                      "deleted_at": null,
                      "pivot": {
                        "incidencia_gasto_id": 8505,
                        "estatus_id": 10,
                        "created_at": "2019-08-02 13:54:42",
                        "updated_at": "2019-08-02 13:54:42"
                      }
                    }
                  ],
                  "gastos": [
                    {
                      "id": 3806,
                      "incidencia_gasto_id": 8505,
                      "catalogo_gasto_id": 210,
                      "monto": 20000,
                      "created_at": "2019-08-02 13:54:42",
                      "updated_at": "2019-08-02 13:54:42",
                      "tipo_gasto": {
                        "id": 210,
                        "nombre": "Mano de Obra Mantenimiento Preventivo",
                        "motivo_id": 5,
                        "tiempo_vida": null,
                        "uso_promedio": null,
                        "tiempo_reparacion": null,
                        "created_at": "2019-05-24 13:26:12",
                        "updated_at": "2019-05-24 13:26:12"
                      }
                    },
                    {
                      "id": 3807,
                      "incidencia_gasto_id": 8505,
                      "catalogo_gasto_id": 112,
                      "monto": 30000,
                      "created_at": "2019-08-02 13:54:42",
                      "updated_at": "2019-08-02 13:54:42",
                      "tipo_gasto": {
                        "id": 112,
                        "nombre": "APOYO TAXI",
                        "motivo_id": 5,
                        "tiempo_vida": null,
                        "uso_promedio": null,
                        "tiempo_reparacion": null,
                        "created_at": "2019-04-25 16:03:41",
                        "updated_at": "2019-05-10 13:10:10"
                      }
                    }
                  ]
                },
                "proveedor": null,
                "error_operativo": null,
                "call_center": []
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
            "gastos_ids": [
              "El campo gastos ids es obligatorio."
            ],
            "montos": [
              "El campo montos es obligatorio."
            ],
            "monto": [
              "El campo monto es obligatorio."
            ]
        }


  * **Code:** 409 Conflict <br />
  **Content:** 

        {
          "error": "El monto del gasto Mano de Obra Mantenimiento Preventivo excede el límite, favor de verificarlo o comunicarse con un supervisor."
        }


**Marcar como reparada/confirmada**
----

  #### Agrega estatus `reparada` en indicencias gastos o `confirmada` en incidencias gasolina

  Actualización de los gastos relacionados a la incidencia

 **URL**

  /api/agentes/incidencias/ID/reparar

 **Method:**

  `POST`

 **Headers**

    Authorization: Bearer access_token
    Accept: application/json
    Content-Type: multipart/form-data

 **Data Params**

  ***Required:***

    'monto' => 'required',
    'archivo_ticket' => 'required|image',
    'archivo_factura' => 'nullable|image',
    'archivo_evidencia' => 'nullable|image',
    'litros_cargados' => 'nullable',
    'evidencias' => 'nullable|array',
    'archivo_km' => 'nullable|image',
    'km' => 'nullable',


 -Ejemplo<br>
        
        210 => ID de la tabla catalogo_gastos_incidencias
    
        'evidencias[210][0]'

 **Success Response:**

  * **Code:** 200 <br />
    **Content:**

        {
            "incidencia": {
                "id": 8844,
                "agente_id": 28,
                "folio": "GG8844",
                "fecha": "2019-08-02 13:13:13",
                "km": "1100",
                "km_evidencia": null,
                "motivo_id": 5,
                "vehiculo_id": 42,
                "observaciones": null,
                "evidencia": null,
                "proveedor_id": null,
                "tipo_creacion": "api_store",
                "mantenimiento_id": null,
                "created_at": "2019-08-02 14:19:37",
                "updated_at": "2019-08-02 14:19:37",
                "deleted_at": null,
                "incidencia_gasto": {
                  "id": 8506,
                  "agente_incidencia_id": 8844,
                  "archivo_evidencia": null,
                  "archivo_ticket": "uploads\/images\/incidencias\/gastos\/\/iAlnzPomTphb8YUIyF3uXXqzM9iYZVuKUxqoWG13.png",
                  "archivo_factura": "uploads\/images\/incidencias\/gastos\/\/K121uTrf0CxEfaMkN2mgKDq4Kygpr561ar2mMUA6.png",
                  "num_ticket": null,
                  "factura": 0,
                  "monto": 50000,
                  "pagado": null,
                  "reposicion_datos": 0,
                  "litros_cargados": null,
                  "litros_aprobados": null,
                  "descripcion_sucursal": null,
                  "monto_sucursal": null,
                  "archivo_evidencia_sucursal": null,
                  "razon_improcedencia": null,
                  "razon_rechazo": null,
                  "rechazo_costos": 0,
                  "tiempo_revision": null,
                  "tiempo_revision_tipo": null,
                  "tiempo_reparacion": null,
                  "tiempo_reparacion_tipo": null,
                  "created_at": "2019-08-02 14:19:37",
                  "updated_at": "2019-08-02 17:45:37",
                  "estatus": [
                    {
                      "id": 1,
                      "nombre": "Pendiente",
                      "key": "pendiente",
                      "created_at": "2019-06-07 16:29:17",
                      "updated_at": "2019-06-07 16:29:17",
                      "deleted_at": null,
                      "pivot": {
                        "incidencia_gasto_id": 8506,
                        "estatus_id": 1,
                        "created_at": "2019-08-02 14:19:37",
                        "updated_at": "2019-08-02 14:19:37"
                      }
                    },
                    {
                      "id": 2,
                      "nombre": "Aprobada para cotizar",
                      "key": "aprobada",
                      "created_at": "2019-06-07 16:29:17",
                      "updated_at": "2019-08-01 17:28:43",
                      "deleted_at": null,
                      "pivot": {
                        "incidencia_gasto_id": 8506,
                        "estatus_id": 2,
                        "created_at": "2019-08-02 14:20:37",
                        "updated_at": "2019-08-02 14:19:37"
                      }
                    },
                    {
                      "id": 10,
                      "nombre": "Cotizada",
                      "key": "cotizada",
                      "created_at": "2019-06-07 16:29:17",
                      "updated_at": "2019-06-07 16:29:17",
                      "deleted_at": null,
                      "pivot": {
                        "incidencia_gasto_id": 8506,
                        "estatus_id": 10,
                        "created_at": "2019-08-02 14:30:06",
                        "updated_at": "2019-08-02 14:30:06"
                      }
                    },
                    {
                      "id": 15,
                      "nombre": "Reparada",
                      "key": "reparada",
                      "created_at": "2019-06-07 16:29:17",
                      "updated_at": "2019-06-07 16:29:17",
                      "deleted_at": null,
                      "pivot": {
                        "incidencia_gasto_id": 8506,
                        "estatus_id": 15,
                        "created_at": "2019-08-02 17:45:37",
                        "updated_at": "2019-08-02 17:45:37"
                      }
                    }
                  ],
                  "gastos": [
                    {
                      "id": 3810,
                      "incidencia_gasto_id": 8506,
                      "catalogo_gasto_id": 210,
                      "monto": 20000,
                      "created_at": "2019-08-02 14:30:06",
                      "updated_at": "2019-08-02 14:30:06",
                      "tipo_gasto": {
                        "id": 210,
                        "nombre": "Mano de Obra Mantenimiento Preventivo",
                        "motivo_id": 5,
                        "tiempo_vida": null,
                        "uso_promedio": null,
                        "tiempo_reparacion": null,
                        "created_at": "2019-05-24 13:26:12",
                        "updated_at": "2019-05-24 13:26:12"
                      },
                      "evidencias": [
                        {
                          "id": 8,
                          "incidencia_gasto_id": 8506,
                          "incidencia_gasto_extra_id": 3810,
                          "url_archivo": "uploads\/images\/incidencias\/gastos\/\/dnAo59zlOKYo8Icoyqqp6sgJD60F4K8uAc7uwb9U.png",
                          "created_at": "2019-08-02 17:45:28",
                          "updated_at": "2019-08-02 17:45:28"
                        },
                        {
                          "id": 9,
                          "incidencia_gasto_id": 8506,
                          "incidencia_gasto_extra_id": 3810,
                          "url_archivo": "uploads\/images\/incidencias\/gastos\/\/dspXGDwB84mj4PBaHOqk2eWW0h8hQLgGLdx5moW3.png",
                          "created_at": "2019-08-02 17:45:37",
                          "updated_at": "2019-08-02 17:45:37"
                        }
                      ]
                    },
                    {
                      "id": 3811,
                      "incidencia_gasto_id": 8506,
                      "catalogo_gasto_id": 112,
                      "monto": 30000,
                      "created_at": "2019-08-02 14:30:06",
                      "updated_at": "2019-08-02 14:30:06",
                      "tipo_gasto": {
                        "id": 112,
                        "nombre": "APOYO TAXI",
                        "motivo_id": 5,
                        "tiempo_vida": null,
                        "uso_promedio": null,
                        "tiempo_reparacion": null,
                        "created_at": "2019-04-25 16:03:41",
                        "updated_at": "2019-05-10 13:10:10"
                      },
                      "evidencias": []
                    }
                  ]
                },
                "agente": {
                  "id": 28,
                  "user_id": 164,
                  "numero_control": "0202",
                  "estatus": 0,
                  "puesto": null,
                  "created_at": "2018-01-10 13:10:55",
                  "updated_at": "2018-01-10 17:19:00",
                  "deleted_at": null,
                  "lat": "18.9359768",
                  "lon": "-99.2302717",
                  "imagen": null,
                  "imagen_path": null,
                  "vehiculo_id": null,
                  "sucursal_base_id": null,
                  "supervisor": 1,
                  "cant_errores_actuales": 0,
                  "user": {
                    "id": 164,
                    "name": "Supervisor",
                    "last_name": "Prueba",
                    "second_last_name": "Prueba",
                    "telephone": "77731020437",
                    "clave": "SUPRGSG9",
                    "email": "supervisor@farma.com",
                    "player_id": "9c5d1e43-8495-4180-883c-eebd50333741",
                    "tipo_usuario": "repartidor",
                    "activo": 0,
                    "baja": 0,
                    "fb_id": null,
                    "webhook_url": null,
                    "created_at": "2018-01-10 13:10:55",
                    "updated_at": "2019-07-24 13:15:59",
                    "deleted_at": null,
                    "last_login": null
                  }
                },
                "motivo": {
                  "id": 5,
                  "nombre": "Gastos generales",
                  "key": "generales",
                  "prefix": "GG",
                  "created_at": "2019-05-21 13:28:24",
                  "updated_at": "2019-08-01 14:08:52"
                },
                "vehiculo": {
                  "id": 42,
                  "sucursal_id": 84,
                  "placas": "CS-381",
                  "modelo": "YBR125C Express",
                  "marca": "Yamaha",
                  "num_serie": "",
                  "color": "",
                  "num_poliza": "",
                  "ultimo_servicio": "0000-00-00",
                  "bloqueado": 0,
                  "created_at": "2019-04-29 13:10:43",
                  "updated_at": "2019-06-10 18:52:48",
                  "deleted_at": null,
                  "sucursal": {
                    "id": 84,
                    "user_id": 2429,
                    "codigo": "cs-2",
                    "nombre": "Sucursal CS NO ELIMINAR",
                    "telefono": "7777771234",
                    "colonia_id": 34641,
                    "municipio_id": 502,
                    "estado_id": 17,
                    "zona_sucursal_id": 3,
                    "ciudad_cobertura_id": null,
                    "direccion": "Ahuatepec 307",
                    "direccion_numero": "222222",
                    "codigo_postal": "62000",
                    "lon": "-99.228404",
                    "lat": "18.938236",
                    "ancla": 0,
                    "dias": "LUN, MAR, MIE, JUE, VIE",
                    "horario_inicio": "07:00:00",
                    "horario_final": "20:00:00",
                    "24_hrs": 0,
                    "base": 0,
                    "almacen": 0,
                    "created_at": "2018-11-30 13:45:25",
                    "updated_at": "2019-06-26 17:52:47",
                    "deleted_at": null
                  }
                },
                "proveedor": null,
                "error_operativo": null,
                "call_center": []
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
          "archivo_ticket": [
            "El campo archivo ticket es obligatorio."
          ],
          "monto": [
            "El campo monto es obligatorio."
          ]
        }

**Eliminar incidencia**
----
  Elimina una incidencia en específico y el archivo de evidencia

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
        
        

**Verificar errores operativos**
----
  Verificar si existen incidencias que puedan generar errores operativos

 **URL**

  /api/agentes/incidencias/verificar-errores-operativos

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
            "incidencia": {
                "id": 6950,
                "agente_id": 95,
                "folio": "GA6950",
                "fecha": "2019-05-14 07:18:24",
                "km": "40454",
                "km_evidencia": null,
                "motivo_id": 4,
                "vehiculo_id": 20,
                "observaciones": null,
                "evidencia": null,
                "proveedor_id": null,
                "tipo_creacion": "dashboard_checkin",
                "created_at": "2019-05-14 07:18:24",
                "updated_at": "2019-05-14 07:18:24"
            },
            "num_error": 3
        }

 **Error Responses:**

  * **Code:** 401 Unauthorized <br />
    **Content:** 
    
        {
          "error": "Unauthenticated."
        }