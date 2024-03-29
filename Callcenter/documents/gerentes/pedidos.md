## Listado de pedidos que tiene más de 2 mins y no tienen repartidor
Regresa el listado de todos los pedidos que tiene más de 2 mins y no tienen repartidor

 **URL**

  /api/gerentes/pedidos/sin_repartidor

 **Method:**

  `GET`
  
 **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      
      
 **Data Params**
    
     'fecha_inicio' => 'nullable|date|before:fecha_fin',
     'fecha_fin' => 'nullable|date|after:fecha_inicio',
     'sucursal_id' => 'nullable|exists:sucursales,id',

****Catalogo de sucursales base**** [/api/catalogos/sucursales-base](https://github.com/csagency/farmapronto/blob/develop/resources/docs/catalogos/sucursales.md)

**URL Params**

  - includes[]= sucursal, agente, estados, estado  <br><br>
  Ejemplo URI: `api/gerentes/pedidos/sin_repartidor?includes[]=estados`


**Filtro por fechas**

  Ejemplo URI: `api/gerentes/pedidos/sin_repartidor?fecha_inicio=2019-08-27&fecha_fin=2019-08-30`<br>
  

**Success Response:**

* **Code:** 200 <br />
  **Content:** 
  
      {
            "pedidos": [
                {
                  "id": 74859,
                  "user_id": 2333,
                  "cliente_direccion_id": 8162,
                  "ciudad_cobertura_id": 6,
                  "asistencia": 0,
                  "alerta_cliente": 0,
                  "folio": "APP0074859",
                  "erp": 0,
                  "usuario_erp": "APP",
                  "codigo_confirmacion": null,
                  "visto_callcenter": 1,
                  "programado_at": null,
                  "taxi": 0,
                  "clon": 0,
                  "pedidos_juntos": null,
                  "cancelado_motivo": null,
                  "cancelado_user_id": null,
                  "observaciones": "SOLUCION HARTMANN DE LA ZA A LA ZG",
                  "created_at": "2019-08-27 16:25:48",
                  "updated_at": "2019-08-29 13:47:05",
                  "deleted_at": null,
                  "estados": [
                    {
                      "id": 777408,
                      "pedido_id": 74859,
                      "paso": "por embarcar",
                      "created_at": "2019-08-27 16:33:13",
                      "updated_at": "2019-08-27 16:33:13"
                    },
                    {
                      "id": 777403,
                      "pedido_id": 74859,
                      "paso": "aceptado",
                      "created_at": "2019-08-27 16:29:19",
                      "updated_at": "2019-08-27 16:29:19"
                    },
                    {
                      "id": 777390,
                      "pedido_id": 74859,
                      "paso": "recibido",
                      "created_at": "2019-08-27 16:25:49",
                      "updated_at": "2019-08-27 16:25:49"
                    }
                  ],
                  "sucursal": [
                    {
                      "id": 40,
                      "user_id": 90,
                      "codigo": "42",
                      "nombre": "ZM",
                      "telefono": "7772576508",
                      "colonia_id": 20632,
                      "municipio_id": 835,
                      "estado_id": 12,
                      "zona_sucursal_id": 12,
                      "ciudad_cobertura_id": null,
                      "direccion": "CARR. NACIONAL IXTAPA ZIHUATANEJO MZ 7 SMZ XXII",
                      "direccion_numero": "L 6",
                      "codigo_postal": "40880",
                      "lon": "-101.5554594",
                      "lat": "17.6563731",
                      "ancla": 1,
                      "dias": "LUN, MAR, MIE, JUE, VIE, SAB, DOM",
                      "horario_inicio": "07:00:00",
                      "horario_final": "22:00:00",
                      "24_hrs": 0,
                      "base": 1,
                      "almacen": 1,
                      "created_at": "2017-03-16 17:50:05",
                      "updated_at": "2019-07-30 12:27:03",
                      "deleted_at": null,
                      "pivot": {
                        "pedido_id": 74859,
                        "sucursal_id": 40,
                        "created_at": null,
                        "updated_at": null,
                        "aceptado": 1,
                        "rechazado": 0,
                        "activo": 1
                      }
                    }
                  ]
                },
                {
                  "id": 74858,
                  "user_id": 2333,
                  "cliente_direccion_id": 8162,
                  "ciudad_cobertura_id": 6,
                  "asistencia": 0,
                  "alerta_cliente": 0,
                  "folio": "APP0074858",
                  "erp": 0,
                  "usuario_erp": "APP",
                  "codigo_confirmacion": null,
                  "visto_callcenter": 1,
                  "programado_at": null,
                  "taxi": 0,
                  "clon": 0,
                  "pedidos_juntos": null,
                  "cancelado_motivo": null,
                  "cancelado_user_id": null,
                  "observaciones": "LUCION HARTMANN DE LA ZE A LA ZG",
                  "created_at": "2019-08-27 16:25:08",
                  "updated_at": "2019-08-29 13:47:05",
                  "deleted_at": null,
                  "estados": [
                    {
                      "id": 777402,
                      "pedido_id": 74858,
                      "paso": "aceptado",
                      "created_at": "2019-08-27 16:29:06",
                      "updated_at": "2019-08-27 16:29:06"
                    },
                    {
                      "id": 777389,
                      "pedido_id": 74858,
                      "paso": "recibido",
                      "created_at": "2019-08-27 16:25:09",
                      "updated_at": "2019-08-27 16:25:09"
                    }
                  ],
                  "sucursal": [
                    {
                      "id": 40,
                      "user_id": 90,
                      "codigo": "42",
                      "nombre": "ZM",
                      "telefono": "7772576508",
                      "colonia_id": 20632,
                      "municipio_id": 835,
                      "estado_id": 12,
                      "zona_sucursal_id": 12,
                      "ciudad_cobertura_id": null,
                      "direccion": "CARR. NACIONAL IXTAPA ZIHUATANEJO MZ 7 SMZ XXII",
                      "direccion_numero": "L 6",
                      "codigo_postal": "40880",
                      "lon": "-101.5554594",
                      "lat": "17.6563731",
                      "ancla": 1,
                      "dias": "LUN, MAR, MIE, JUE, VIE, SAB, DOM",
                      "horario_inicio": "07:00:00",
                      "horario_final": "22:00:00",
                      "24_hrs": 0,
                      "base": 1,
                      "almacen": 1,
                      "created_at": "2017-03-16 17:50:05",
                      "updated_at": "2019-07-30 12:27:03",
                      "deleted_at": null,
                      "pivot": {
                        "pedido_id": 74858,
                        "sucursal_id": 40,
                        "created_at": null,
                        "updated_at": null,
                        "aceptado": 1,
                        "rechazado": 0,
                        "activo": 1
                      }
                    }
                  ]
                },
                {
                  "id": 74857,
                  "user_id": 14458,
                  "cliente_direccion_id": 65762,
                  "ciudad_cobertura_id": null,
                  "asistencia": 0,
                  "alerta_cliente": 0,
                  "folio": "ERP0074857",
                  "erp": 1,
                  "usuario_erp": "VHERNANDEZ",
                  "codigo_confirmacion": null,
                  "visto_callcenter": 1,
                  "programado_at": null,
                  "taxi": 0,
                  "clon": 0,
                  "pedidos_juntos": null,
                  "cancelado_motivo": null,
                  "cancelado_user_id": null,
                  "observaciones": null,
                  "created_at": "2019-08-27 16:21:52",
                  "updated_at": "2019-08-29 13:47:07",
                  "deleted_at": null,
                  "estados": [
                    {
                      "id": 777391,
                      "pedido_id": 74857,
                      "paso": "aceptado",
                      "created_at": "2019-08-27 16:26:06",
                      "updated_at": "2019-08-27 16:26:06"
                    },
                    {
                      "id": 777381,
                      "pedido_id": 74857,
                      "paso": "recibido",
                      "created_at": "2019-08-27 16:21:52",
                      "updated_at": "2019-08-27 16:21:52"
                    }
                  ],
                  "sucursal": [
                    {
                      "id": 62,
                      "user_id": 111,
                      "codigo": "86",
                      "nombre": "Q",
                      "telefono": "7772575913",
                      "colonia_id": 34754,
                      "municipio_id": 502,
                      "estado_id": 17,
                      "zona_sucursal_id": 5,
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
                      "base": 1,
                      "almacen": 1,
                      "created_at": "2017-07-05 13:45:09",
                      "updated_at": "2019-07-30 12:28:41",
                      "deleted_at": null,
                      "pivot": {
                        "pedido_id": 74857,
                        "sucursal_id": 62,
                        "created_at": null,
                        "updated_at": null,
                        "aceptado": 1,
                        "rechazado": 0,
                        "activo": 1
                      }
                    }
                  ]
                },
                {
                  "id": 74853,
                  "user_id": 18169,
                  "cliente_direccion_id": 65759,
                  "ciudad_cobertura_id": null,
                  "asistencia": 0,
                  "alerta_cliente": 0,
                  "folio": "ERP0074853",
                  "erp": 1,
                  "usuario_erp": "FMADRIGAL",
                  "codigo_confirmacion": null,
                  "visto_callcenter": 0,
                  "programado_at": null,
                  "taxi": 0,
                  "clon": 0,
                  "pedidos_juntos": null,
                  "cancelado_motivo": null,
                  "cancelado_user_id": null,
                  "observaciones": null,
                  "created_at": "2019-08-27 16:14:09",
                  "updated_at": "2019-08-27 16:14:09",
                  "deleted_at": null,
                  "estados": [
                    {
                      "id": 777363,
                      "pedido_id": 74853,
                      "paso": "por embarcar",
                      "created_at": "2019-08-27 16:16:43",
                      "updated_at": "2019-08-27 16:16:43"
                    },
                    {
                      "id": 777360,
                      "pedido_id": 74853,
                      "paso": "aceptado",
                      "created_at": "2019-08-27 16:15:11",
                      "updated_at": "2019-08-27 16:15:11"
                    },
                    {
                      "id": 777357,
                      "pedido_id": 74853,
                      "paso": "recibido",
                      "created_at": "2019-08-27 16:14:10",
                      "updated_at": "2019-08-27 16:14:10"
                    }
                  ],
                  "sucursal": [
                    {
                      "id": 23,
                      "user_id": 73,
                      "codigo": "25",
                      "nombre": "ZZ",
                      "telefono": "7772575981",
                      "colonia_id": 34739,
                      "municipio_id": 502,
                      "estado_id": 17,
                      "zona_sucursal_id": 3,
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
                      "base": 1,
                      "almacen": 1,
                      "created_at": "2017-03-16 17:50:05",
                      "updated_at": "2019-08-13 17:56:03",
                      "deleted_at": null,
                      "pivot": {
                        "pedido_id": 74853,
                        "sucursal_id": 23,
                        "created_at": null,
                        "updated_at": null,
                        "aceptado": 1,
                        "rechazado": 0,
                        "activo": 1
                      }
                    }
                  ]
                },
                {
                  "id": 74852,
                  "user_id": 1956,
                  "cliente_direccion_id": 65758,
                  "ciudad_cobertura_id": null,
                  "asistencia": 0,
                  "alerta_cliente": 0,
                  "folio": "ERP0074852",
                  "erp": 1,
                  "usuario_erp": "JCORTES",
                  "codigo_confirmacion": null,
                  "visto_callcenter": 1,
                  "programado_at": null,
                  "taxi": 0,
                  "clon": 0,
                  "pedidos_juntos": null,
                  "cancelado_motivo": null,
                  "cancelado_user_id": null,
                  "observaciones": null,
                  "created_at": "2019-08-27 16:10:59",
                  "updated_at": "2019-08-27 17:20:34",
                  "deleted_at": null,
                  "estados": [
                    {
                      "id": 777362,
                      "pedido_id": 74852,
                      "paso": "por embarcar",
                      "created_at": "2019-08-27 16:16:29",
                      "updated_at": "2019-08-27 16:16:29"
                    },
                    {
                      "id": 777359,
                      "pedido_id": 74852,
                      "paso": "aceptado",
                      "created_at": "2019-08-27 16:14:56",
                      "updated_at": "2019-08-27 16:14:56"
                    },
                    {
                      "id": 777354,
                      "pedido_id": 74852,
                      "paso": "recibido",
                      "created_at": "2019-08-27 16:10:59",
                      "updated_at": "2019-08-27 16:10:59"
                    }
                  ],
                  "sucursal": [
                    {
                      "id": 62,
                      "user_id": 111,
                      "codigo": "86",
                      "nombre": "Q",
                      "telefono": "7772575913",
                      "colonia_id": 34754,
                      "municipio_id": 502,
                      "estado_id": 17,
                      "zona_sucursal_id": 5,
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
                      "base": 1,
                      "almacen": 1,
                      "created_at": "2017-07-05 13:45:09",
                      "updated_at": "2019-07-30 12:28:41",
                      "deleted_at": null,
                      "pivot": {
                        "pedido_id": 74852,
                        "sucursal_id": 62,
                        "created_at": null,
                        "updated_at": null,
                        "aceptado": 1,
                        "rechazado": 0,
                        "activo": 1
                      }
                    }
                  ]
                },
                {
                  "id": 74851,
                  "user_id": 524,
                  "cliente_direccion_id": 65757,
                  "ciudad_cobertura_id": null,
                  "asistencia": 0,
                  "alerta_cliente": 0,
                  "folio": "ERP0074851",
                  "erp": 1,
                  "usuario_erp": "FMADRIGAL",
                  "codigo_confirmacion": null,
                  "visto_callcenter": 1,
                  "programado_at": null,
                  "taxi": 0,
                  "clon": 0,
                  "pedidos_juntos": null,
                  "cancelado_motivo": null,
                  "cancelado_user_id": null,
                  "observaciones": null,
                  "created_at": "2019-08-27 16:10:50",
                  "updated_at": "2019-08-27 17:20:34",
                  "deleted_at": null,
                  "estados": [
                    {
                      "id": 777353,
                      "pedido_id": 74851,
                      "paso": "recibido",
                      "created_at": "2019-08-27 16:10:50",
                      "updated_at": "2019-08-27 16:10:50"
                    }
                  ],
                  "sucursal": []
                },
                {
                  "id": 74850,
                  "user_id": 3736,
                  "cliente_direccion_id": 65756,
                  "ciudad_cobertura_id": null,
                  "asistencia": 0,
                  "alerta_cliente": 0,
                  "folio": "ERP0074850",
                  "erp": 1,
                  "usuario_erp": "LDIAZ",
                  "codigo_confirmacion": null,
                  "visto_callcenter": 0,
                  "programado_at": null,
                  "taxi": 0,
                  "clon": 0,
                  "pedidos_juntos": null,
                  "cancelado_motivo": null,
                  "cancelado_user_id": null,
                  "observaciones": null,
                  "created_at": "2019-08-27 16:08:44",
                  "updated_at": "2019-08-27 16:08:45",
                  "deleted_at": null,
                  "estados": [
                    {
                      "id": 777356,
                      "pedido_id": 74850,
                      "paso": "por embarcar",
                      "created_at": "2019-08-27 16:14:00",
                      "updated_at": "2019-08-27 16:14:00"
                    },
                    {
                      "id": 777355,
                      "pedido_id": 74850,
                      "paso": "aceptado",
                      "created_at": "2019-08-27 16:12:28",
                      "updated_at": "2019-08-27 16:12:28"
                    },
                    {
                      "id": 777352,
                      "pedido_id": 74850,
                      "paso": "recibido",
                      "created_at": "2019-08-27 16:08:45",
                      "updated_at": "2019-08-27 16:08:45"
                    }
                  ],
                  "sucursal": [
                    {
                      "id": 23,
                      "user_id": 73,
                      "codigo": "25",
                      "nombre": "ZZ",
                      "telefono": "7772575981",
                      "colonia_id": 34739,
                      "municipio_id": 502,
                      "estado_id": 17,
                      "zona_sucursal_id": 3,
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
                      "base": 1,
                      "almacen": 1,
                      "created_at": "2017-03-16 17:50:05",
                      "updated_at": "2019-08-13 17:56:03",
                      "deleted_at": null,
                      "pivot": {
                        "pedido_id": 74850,
                        "sucursal_id": 23,
                        "created_at": null,
                        "updated_at": null,
                        "aceptado": 1,
                        "rechazado": 0,
                        "activo": 1
                      }
                    }
                  ]
                },
                {
                  "id": 74840,
                  "user_id": 2357,
                  "cliente_direccion_id": 7118,
                  "ciudad_cobertura_id": 1,
                  "asistencia": 0,
                  "alerta_cliente": 0,
                  "folio": "APP0074840",
                  "erp": 0,
                  "usuario_erp": "APP",
                  "codigo_confirmacion": null,
                  "visto_callcenter": 1,
                  "programado_at": null,
                  "taxi": 0,
                  "clon": 0,
                  "pedidos_juntos": null,
                  "cancelado_motivo": null,
                  "cancelado_user_id": null,
                  "observaciones": "traspaso de la suc ZZ a la suc J 002167 bredelin 500mg tabletas c\/7",
                  "created_at": "2019-08-27 14:53:04",
                  "updated_at": "2019-08-27 15:25:05",
                  "deleted_at": null,
                  "estados": [
                    {
                      "id": 777283,
                      "pedido_id": 74840,
                      "paso": "aceptado",
                      "created_at": "2019-08-27 15:25:02",
                      "updated_at": "2019-08-27 15:25:02"
                    },
                    {
                      "id": 777282,
                      "pedido_id": 74840,
                      "paso": "aceptado",
                      "created_at": "2019-08-27 15:25:01",
                      "updated_at": "2019-08-27 15:25:01"
                    },
                    {
                      "id": 777281,
                      "pedido_id": 74840,
                      "paso": "callcenter",
                      "created_at": "2019-08-27 15:24:41",
                      "updated_at": "2019-08-27 15:24:41"
                    },
                    {
                      "id": 777205,
                      "pedido_id": 74840,
                      "paso": "recibido",
                      "created_at": "2019-08-27 14:53:04",
                      "updated_at": "2019-08-27 14:53:04"
                    }
                  ],
                  "sucursal": [
                    {
                      "id": 23,
                      "user_id": 73,
                      "codigo": "25",
                      "nombre": "ZZ",
                      "telefono": "7772575981",
                      "colonia_id": 34739,
                      "municipio_id": 502,
                      "estado_id": 17,
                      "zona_sucursal_id": 3,
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
                      "base": 1,
                      "almacen": 1,
                      "created_at": "2017-03-16 17:50:05",
                      "updated_at": "2019-08-13 17:56:03",
                      "deleted_at": null,
                      "pivot": {
                        "pedido_id": 74840,
                        "sucursal_id": 23,
                        "created_at": null,
                        "updated_at": null,
                        "aceptado": 1,
                        "rechazado": 0,
                        "activo": 1
                      }
                    }
                  ]
                },
                {
                  "id": 74824,
                  "user_id": 234,
                  "cliente_direccion_id": 65734,
                  "ciudad_cobertura_id": null,
                  "asistencia": 0,
                  "alerta_cliente": 0,
                  "folio": "ERP0074824",
                  "erp": 1,
                  "usuario_erp": "GRUIZ",
                  "codigo_confirmacion": null,
                  "visto_callcenter": 1,
                  "programado_at": null,
                  "taxi": 0,
                  "clon": 0,
                  "pedidos_juntos": null,
                  "cancelado_motivo": null,
                  "cancelado_user_id": null,
                  "observaciones": null,
                  "created_at": "2019-08-27 13:18:50",
                  "updated_at": "2019-08-27 17:36:15",
                  "deleted_at": null,
                  "estados": [
                    {
                      "id": 777228,
                      "pedido_id": 74824,
                      "paso": "por embarcar",
                      "created_at": "2019-08-27 15:01:45",
                      "updated_at": "2019-08-27 15:01:45"
                    },
                    {
                      "id": 777095,
                      "pedido_id": 74824,
                      "paso": "aceptado",
                      "created_at": "2019-08-27 13:48:31",
                      "updated_at": "2019-08-27 13:48:31"
                    },
                    {
                      "id": 777045,
                      "pedido_id": 74824,
                      "paso": "recibido",
                      "created_at": "2019-08-27 13:18:50",
                      "updated_at": "2019-08-27 13:18:50"
                    }
                  ],
                  "sucursal": [
                    {
                      "id": 23,
                      "user_id": 73,
                      "codigo": "25",
                      "nombre": "ZZ",
                      "telefono": "7772575981",
                      "colonia_id": 34739,
                      "municipio_id": 502,
                      "estado_id": 17,
                      "zona_sucursal_id": 3,
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
                      "base": 1,
                      "almacen": 1,
                      "created_at": "2017-03-16 17:50:05",
                      "updated_at": "2019-08-13 17:56:03",
                      "deleted_at": null,
                      "pivot": {
                        "pedido_id": 74824,
                        "sucursal_id": 23,
                        "created_at": null,
                        "updated_at": null,
                        "aceptado": 1,
                        "rechazado": 0,
                        "activo": 1
                      }
                    }
                  ]
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
          "fecha_inicio": [
            "El campo fecha inicio no es una fecha válida.",
            "El campo fecha inicio debe ser una fecha anterior a fecha fin."
          ],
          "fecha_fin": [
            "El campo fecha fin no es una fecha válida.",
            "El campo fecha fin debe ser una fecha posterior a fecha inicio."
          ],
          "sucursal_id": [
            "El campo sucursal id es inválido."
          ]
        }
        
        
        
        
## Listado de pedidos que tiene más de 10 mins y no han sido surtidos
Regresa el listado de todos los pedidos que tiene más de 10 mins y no han sido surtidos

 **URL**

  /api/gerentes/pedidos/sin_surtir

 **Method:**

  `GET`
  
 **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      
      
 **Data Params**
    
     'fecha_inicio' => 'nullable|date|before:fecha_fin',
     'fecha_fin' => 'nullable|date|after:fecha_inicio',
     'sucursal_id' => 'nullable|exists:sucursales,id',

****Catalogo de sucursales base**** [/api/catalogos/sucursales-base](https://github.com/csagency/farmapronto/blob/develop/resources/docs/catalogos/sucursales.md)

**URL Params**

  - includes[]= sucursal, agente, estados, estado  <br><br>
  Ejemplo URI: `api/gerentes/pedidos/sin_surtir?includes[]=estados`


**Filtro por fechas**

  Ejemplo URI: `api/gerentes/pedidos/sin_surtir?fecha_inicio=2019-08-27&fecha_fin=2019-08-30`<br>
  

**Success Response:**

* **Code:** 200 <br />
  **Content:** 
  
      {
            "pedidos": [
                {
                  "id": 74858,
                  "user_id": 2333,
                  "cliente_direccion_id": 8162,
                  "ciudad_cobertura_id": 6,
                  "asistencia": 0,
                  "alerta_cliente": 0,
                  "folio": "APP0074858",
                  "erp": 0,
                  "usuario_erp": "APP",
                  "codigo_confirmacion": null,
                  "visto_callcenter": 1,
                  "programado_at": null,
                  "taxi": 0,
                  "clon": 0,
                  "pedidos_juntos": null,
                  "cancelado_motivo": null,
                  "cancelado_user_id": null,
                  "observaciones": "LUCION HARTMANN DE LA ZE A LA ZG",
                  "created_at": "2019-08-27 16:25:08",
                  "updated_at": "2019-08-29 13:47:05",
                  "deleted_at": null,
                  "agente": [],
                  "estados": [
                    {
                      "id": 777402,
                      "pedido_id": 74858,
                      "paso": "aceptado",
                      "created_at": "2019-08-27 16:29:06",
                      "updated_at": "2019-08-27 16:29:06"
                    },
                    {
                      "id": 777389,
                      "pedido_id": 74858,
                      "paso": "recibido",
                      "created_at": "2019-08-27 16:25:09",
                      "updated_at": "2019-08-27 16:25:09"
                    }
                  ],
                  "sucursal": [
                    {
                      "id": 40,
                      "user_id": 90,
                      "codigo": "42",
                      "nombre": "ZM",
                      "telefono": "7772576508",
                      "colonia_id": 20632,
                      "municipio_id": 835,
                      "estado_id": 12,
                      "zona_sucursal_id": 12,
                      "ciudad_cobertura_id": null,
                      "direccion": "CARR. NACIONAL IXTAPA ZIHUATANEJO MZ 7 SMZ XXII",
                      "direccion_numero": "L 6",
                      "codigo_postal": "40880",
                      "lon": "-101.5554594",
                      "lat": "17.6563731",
                      "ancla": 1,
                      "dias": "LUN, MAR, MIE, JUE, VIE, SAB, DOM",
                      "horario_inicio": "07:00:00",
                      "horario_final": "22:00:00",
                      "24_hrs": 0,
                      "base": 1,
                      "almacen": 1,
                      "created_at": "2017-03-16 17:50:05",
                      "updated_at": "2019-07-30 12:27:03",
                      "deleted_at": null,
                      "pivot": {
                        "pedido_id": 74858,
                        "sucursal_id": 40,
                        "created_at": null,
                        "updated_at": null,
                        "aceptado": 1,
                        "rechazado": 0,
                        "activo": 1
                      }
                    }
                  ]
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
          "fecha_inicio": [
            "El campo fecha inicio no es una fecha válida.",
            "El campo fecha inicio debe ser una fecha anterior a fecha fin."
          ],
          "fecha_fin": [
            "El campo fecha fin no es una fecha válida.",
            "El campo fecha fin debe ser una fecha posterior a fecha inicio."
          ],
          "sucursal_id": [
            "El campo sucursal id es inválido."
          ]
        }
        
        
                
## Enviar alerta para pedidos
Regresa el detalle del pedido sobre el cual se envió mensaje

 **URL**

  /api/gerentes/pedidos/ID/enviar_alerta

 **Method:**

  `POST`
  
 **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      
      
 **Data Params**
    
     'mensaje' => 'required'

**Success Response:**

* **Code:** 200 <br />
  **Content:** 
  
      {
            "pedido": {
                "id": 74859,
                "user_id": 2333,
                "cliente_direccion_id": 8162,
                "ciudad_cobertura_id": 6,
                "asistencia": 0,
                "alerta_cliente": 0,
                "folio": "APP0074859",
                "erp": 0,
                "usuario_erp": "APP",
                "codigo_confirmacion": null,
                "visto_callcenter": 1,
                "programado_at": null,
                "taxi": 0,
                "clon": 0,
                "pedidos_juntos": null,
                "cancelado_motivo": null,
                "cancelado_user_id": null,
                "observaciones": "SOLUCION HARTMANN DE LA ZA A LA ZG",
                "created_at": "2019-08-27 16:25:48",
                "updated_at": "2019-08-29 13:47:05",
                "deleted_at": null,
                "envio": {
                  "id": 73385,
                  "pedido_id": 74859,
                  "sucursal_id": 40,
                  "agente_id": null,
                  "vehiculo_id": null,
                  "codigo_verificacion": "7705",
                  "aceptado": 0,
                  "created_at": "2019-08-27 16:29:19",
                  "updated_at": "2019-08-30 10:02:35",
                  "delivery_at": null,
                  "estimated_at": null,
                  "outoftime": 0,
                  "outoftime_notified": null,
                  "tiempo_recoleccion": null,
                  "tiempo_entrega": null,
                  "taxi_cp_id": null,
                  "km_entrega": null,
                  "km_anterior": null,
                  "lat": "17.6506804",
                  "lon": "-101.54663",
                  "sucursal": {
                    "id": 40,
                    "user_id": 90,
                    "codigo": "42",
                    "nombre": "ZM",
                    "telefono": "7772576508",
                    "colonia_id": 20632,
                    "municipio_id": 835,
                    "estado_id": 12,
                    "zona_sucursal_id": 12,
                    "ciudad_cobertura_id": null,
                    "direccion": "CARR. NACIONAL IXTAPA ZIHUATANEJO MZ 7 SMZ XXII",
                    "direccion_numero": "L 6",
                    "codigo_postal": "40880",
                    "lon": "-101.5554594",
                    "lat": "17.6563731",
                    "ancla": 1,
                    "dias": "LUN, MAR, MIE, JUE, VIE, SAB, DOM",
                    "horario_inicio": "07:00:00",
                    "horario_final": "22:00:00",
                    "24_hrs": 0,
                    "base": 1,
                    "almacen": 1,
                    "created_at": "2017-03-16 17:50:05",
                    "updated_at": "2019-07-30 12:27:03",
                    "deleted_at": null,
                    "user": {
                      "id": 90,
                      "name": "Sucursal 42",
                      "last_name": "ZM",
                      "second_last_name": "40880",
                      "telephone": "0000000000",
                      "clave": null,
                      "email": "sucursal42@grupofarmapronto.com",
                      "player_id": "7c8ca7f4-97ff-432b-a94c-5262e5c4eb3e",
                      "tipo_usuario": "sucursal",
                      "activo": 1,
                      "baja": 0,
                      "fb_id": null,
                      "webhook_url": null,
                      "created_at": "2017-07-05 13:45:06",
                      "updated_at": "2019-08-27 07:13:32",
                      "deleted_at": null,
                      "last_login": "2019-08-27 07:13:32"
                    }
                  }
                },
                "call_center": [
                  {
                    "id": 17124,
                    "name": "Luis Angel",
                    "last_name": "Diaz",
                    "second_last_name": "Flores",
                    "telephone": "7771121618",
                    "clave": null,
                    "email": "Luis@grupofarmapronto.com",
                    "player_id": null,
                    "tipo_usuario": null,
                    "activo": 1,
                    "baja": 0,
                    "fb_id": null,
                    "webhook_url": null,
                    "created_at": "2019-07-15 17:24:54",
                    "updated_at": "2019-08-27 16:12:44",
                    "deleted_at": null,
                    "last_login": "2019-08-27 16:12:44",
                    "pivot": {
                      "pedido_id": 74859,
                      "user_id": 17124,
                      "atendido": 0,
                      "comentarios": null,
                      "atendido_at": null,
                      "created_at": "2019-08-27 16:26:16",
                      "updated_at": "2019-08-27 16:26:16"
                    }
                  }
                ],
                "estado": {
                  "id": 777408,
                  "pedido_id": 74859,
                  "paso": "por embarcar",
                  "created_at": "2019-08-27 16:33:13",
                  "updated_at": "2019-08-27 16:33:13"
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
            "mensaje": [
              "El campo mensaje es obligatorio."
            ]
        }