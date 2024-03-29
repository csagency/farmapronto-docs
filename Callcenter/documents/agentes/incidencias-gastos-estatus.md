## Aprueba o Rechaza cotización
Regresa el gasto y sus estatus de la incidencia afecatada.

**URL**

`/api/agentes/incidencias/aprobar-o-rechazar-cotizacion/{incidenciaId}`

**Method:**

`POST`

**Headers**

      Authorization: Bearer access_token
      Accept: application/json

**Data Params**

    'estatusKey' => 'required|exists:incidencias_gastos_estatus,key|in:cotizacion-aprobada,cotizacion-rechazada',
    'comment' => 'required|in:cotizacion-rechazada'

**URL Params**

- 'incidenciaId' => 'Id de la incidencia' <br><br>
  Ejemplo URI: `/api/agentes/incidencias/aprobar-o-rechazar-cotizacion/28857`

**Success Response:**

* **Code:** 200 <br />
  **Content:**

        {
            "incidencia": {
                "id": 28857,
                "agente_id": 292,
                "folio": "GG28857",
                "fecha": "2023-06-29 00:00:00",
                "km": "37124",
                "km_evidencia": "uploads/images/incidencias/Hbqo0gQkw9htIHvpX7VpUAT7LmkjIZKbELXkEN0f.jpeg",
                "motivo_id": 5,
                "vehiculo_id": 21,
                "observaciones": "PRUEBA",
                "evidencia": "uploads/images/incidencias/fgaabFoh4gahA17F7hAN3Axzk69PkR1T6Vz88VXx.jpeg",
                "proveedor_id": null,
                "tipo_creacion": "dashboard_store",
                "mantenimiento_id": null,
                "created_at": "2023-06-29 10:34:43",
                "updated_at": "2023-06-29 10:34:44",
                "deleted_at": null,
                "deleted_user_id": null,
                "incidencia_gasto": {
                    "id": 28516,
                    "agente_incidencia_id": 28857,
                    "archivo_evidencia": null,
                    "archivo_ticket": null,
                    "archivo_factura": null,
                    "num_ticket": null,
                    "factura": 0,
                    "monto": 143400,
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
                    "created_at": "2023-06-29 10:34:44",
                    "updated_at": "2024-02-27 13:14:17",
                    "gastos_total_raw": "143400",
                    "estatus": [
                        {
                            "id": 1,
                            "nombre": "Pendiente",
                            "key": "pendiente",
                            "created_at": "2019-06-07 16:29:17",
                            "updated_at": "2019-06-07 16:29:17",
                            "deleted_at": null,
                            "pivot": {
                                "incidencia_gasto_id": 28516,
                                "estatus_id": 1,
                                "created_at": "2023-06-29 10:34:44",
                                "updated_at": "2023-06-29 10:34:44"
                            }
                        },
                        {
                            "id": 2,
                            "nombre": "Aprobada para cotizar",
                            "key": "aprobada",
                            "created_at": "2019-06-07 16:29:17",
                            "updated_at": "2019-08-02 17:05:13",
                            "deleted_at": null,
                            "pivot": {
                                "incidencia_gasto_id": 28516,
                                "estatus_id": 2,
                                "created_at": "2023-06-29 10:34:49",
                                "updated_at": "2023-06-29 10:34:44"
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
                                "incidencia_gasto_id": 28516,
                                "estatus_id": 10,
                                "created_at": "2023-06-29 10:35:04",
                                "updated_at": "2023-06-29 10:35:04"
                            }
                        },
                        {
                            "id": 43,
                            "nombre": "Cotización aprobada",
                            "key": "cotizacion-aprobada",
                            "created_at": "2024-02-27 11:05:57",
                            "updated_at": "2024-02-27 11:05:57",
                            "deleted_at": null,
                            "pivot": {
                                "incidencia_gasto_id": 28516,
                                "estatus_id": 43,
                                "created_at": "2024-02-27 12:04:50",
                                "updated_at": "2024-02-27 12:04:50"
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

* **Code:** 422 Unprocessable Entity <br />
  **Content:**


        {
            "estatusKey": [
                "El campo estatus key es obligatorio."
            ]
        }

ó

        {
            "estatusKey": [
                "El campo estatus key es inválido."
            ]
        }

## Aprueba o Rechaza reparación
Regresa el gasto y sus estatus de la incidencia afecatada.

**URL**

`/api/agentes/incidencias/aprobar-o-rechazar-reparacion/{incidenciaId}`

**Method:**

`POST`

**Headers**

      Authorization: Bearer access_token
      Accept: application/json

**Data Params**

    'estatusKey' => 'required|exists:incidencias_gastos_estatus,key|in:reparacion-aprobada,reparacion-rechazada'
    'comment' => 'required|in:reparacion-rechazada'
**URL Params**

- 'incidenciaId' => 'Id de la incidencia' <br><br>
  Ejemplo URI: `/api/agentes/incidencias/aprobar-o-rechazar-reparacion/30264`

**Success Response:**

* **Code:** 200 <br />
  **Content:**

        {
            "incidencia": {
                "id": 30264,
                "agente_id": 459,
                "folio": "GG30264",
                "fecha": "2023-12-04 00:00:00",
                "km": "70760",
                "km_evidencia": "uploads/images/incidencias/40N8A2S1X2iwv2xZmSYk8ghJlZAYuMNFsBcJHnYi.jpeg",
                "motivo_id": 5,
                "vehiculo_id": 3,
                "observaciones": "Se solicita apoyo por $100 de gasolina para el repartidor EDUARDO LEMUS DEL MONTE ya que de la semana del 27 de Noviembre al 3 de Diciembre estuvo al cierre.\r\n",
                "evidencia": "uploads/images/incidencias/qMxqsDXrqmieBerxlohR2O86u2ch6d2TLrqUN8r5.jpeg",
                "proveedor_id": 169,
                "tipo_creacion": "dashboard_store",
                "mantenimiento_id": null,
                "created_at": "2023-12-04 08:21:12",
                "updated_at": "2023-12-05 12:50:14",
                "deleted_at": null,
                "deleted_user_id": null,
                "incidencia_gasto": {
                    "id": 29923,
                    "agente_incidencia_id": 30264,
                    "archivo_evidencia": "uploads/images/incidencias/gastos//ux3WICMIdXLxG7oTUOgfKSEdFu1Yit991ddML3JR.jpeg",
                    "archivo_ticket": "uploads/images/incidencias/gastos//nwlHSfjTvOIhhiJsuyHD3TT9fuYI7RSO0wgLuhWo.pdf",
                    "archivo_factura": "uploads/images/incidencias/gastos//yaP6gXyh8tAeU1YjvEWhKuREA08EyDM634ZdYp6f.pdf",
                    "num_ticket": null,
                    "factura": 0,
                    "monto": 10000,
                    "pagado": "Gasto sucursal",
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
                    "created_at": "2023-12-04 08:21:12",
                    "updated_at": "2023-12-05 13:01:26",
                    "gastos_total_raw": "10000",
                    "estatus": [
                        {
                            "id": 1,
                            "nombre": "Pendiente",
                            "key": "pendiente",
                            "created_at": "2019-06-07 16:29:17",
                            "updated_at": "2019-06-07 16:29:17",
                            "deleted_at": null,
                            "pivot": {
                                "incidencia_gasto_id": 29923,
                                "estatus_id": 1,
                                "created_at": "2023-12-04 08:21:12",
                                "updated_at": "2023-12-04 08:21:12"
                            }
                        },
                        {
                            "id": 2,
                            "nombre": "Aprobada para cotizar",
                            "key": "aprobada",
                            "created_at": "2019-06-07 16:29:17",
                            "updated_at": "2019-08-02 17:05:13",
                            "deleted_at": null,
                            "pivot": {
                                "incidencia_gasto_id": 29923,
                                "estatus_id": 2,
                                "created_at": "2023-12-04 08:21:17",
                                "updated_at": "2023-12-04 08:21:12"
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
                                "incidencia_gasto_id": 29923,
                                "estatus_id": 10,
                                "created_at": "2023-12-05 12:55:28",
                                "updated_at": "2023-12-05 12:55:28"
                            }
                        },
                        {
                            "id": 7,
                            "nombre": "Confirmada",
                            "key": "confirmada",
                            "created_at": "2019-06-07 16:29:17",
                            "updated_at": "2019-06-07 16:29:17",
                            "deleted_at": null,
                            "pivot": {
                                "incidencia_gasto_id": 29923,
                                "estatus_id": 7,
                                "created_at": "2023-12-05 12:55:32",
                                "updated_at": "2023-12-05 12:55:32"
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
                                "incidencia_gasto_id": 29923,
                                "estatus_id": 15,
                                "created_at": "2023-12-05 12:56:20",
                                "updated_at": "2023-12-05 12:56:20"
                            }
                        },
                        {
                            "id": 18,
                            "nombre": "Lista para validar",
                            "key": "lista-validar",
                            "created_at": "2019-08-02 17:05:13",
                            "updated_at": "2019-08-02 17:05:13",
                            "deleted_at": null,
                            "pivot": {
                                "incidencia_gasto_id": 29923,
                                "estatus_id": 18,
                                "created_at": "2023-12-05 13:01:20",
                                "updated_at": "2023-12-05 13:01:20"
                            }
                        },
                        {
                            "id": 9,
                            "nombre": "Validada",
                            "key": "validada",
                            "created_at": "2019-06-07 16:29:17",
                            "updated_at": "2019-06-07 16:29:17",
                            "deleted_at": null,
                            "pivot": {
                                "incidencia_gasto_id": 29923,
                                "estatus_id": 9,
                                "created_at": "2023-12-05 13:01:26",
                                "updated_at": "2023-12-05 13:01:26"
                            }
                        },
                        {
                            "id": 53,
                            "nombre": "Reparación aprobada",
                            "key": "reparacion-aprobada",
                            "created_at": "2024-02-27 12:24:30",
                            "updated_at": "2024-02-27 12:24:30",
                            "deleted_at": null,
                            "pivot": {
                                "incidencia_gasto_id": 29923,
                                "estatus_id": 53,
                                "created_at": "2024-02-27 12:52:41",
                                "updated_at": "2024-02-27 12:52:41"
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

* **Code:** 422 Unprocessable Entity <br />
  **Content:**


        {
            "estatusKey": [
                "El campo estatus key es obligatorio."
            ]
        }

ó

        {
            "estatusKey": [
                "El campo estatus key es inválido."
            ]
        }

## Muesta una incidencia especifica
Regresa una incidencia especifica por id con varios detalles.

**URL**

`/api/agentes/incidencias/obtener-incidencia-para-gerente/{incidenciaId}`

**Method:**

`POST`

**Headers**

      Authorization: Bearer access_token
      Accept: application/json

**Data Params**

    N/A

**URL Params**

- 'incidenciaId' => 'Id de la incidencia' <br><br>
  Ejemplo URI: `/api/agentes/incidencias/obtener-incidencia-para-gerente/11195`

**Success Response:**

* **Code:** 200 <br />
  **Content:**

        {
            "incidencia": {
                "id": 11195,
                "agente_id": 141,
                "folio": "MT11195",
                "fecha": "2019-09-10 00:00:00",
                "km": "201",
                "km_evidencia": "uploads/images/incidencias/NTo9UGNWI3HBvGJcKLnZ26PcwQr9ieHn8lqXMWto.jpeg",
                "motivo_id": 2,
                "vehiculo_id": 42,
                "observaciones": "prueba",
                "evidencia": "uploads/images/incidencias/sTq5LcrYoO1cDvJBwsZHbDt2mrt3XDdToj3jmVXq.jpeg",
                "proveedor_id": 74,
                "tipo_creacion": "dashboard_store",
                "mantenimiento_id": null,
                "created_at": "2019-09-10 12:34:56",
                "updated_at": "2024-02-28 15:21:16",
                "deleted_at": null,
                "deleted_user_id": null,
                "incidencia_gasto": {
                    "id": 10857,
                    "agente_incidencia_id": 11195,
                    "archivo_evidencia": null,
                    "archivo_ticket": "uploads/images/incidencias/gastos//v4iflpkfpxoxcdthyMZTKgZC7W1ZGnHF564Wn4Jx.jpeg",
                    "archivo_factura": null,
                    "num_ticket": null,
                    "factura": 0,
                    "monto": 3100,
                    "pagado": "Gasto sucursal",
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
                    "created_at": "2019-09-10 12:34:57",
                    "updated_at": "2024-02-28 15:24:44",
                    "gastos_total_raw": "3100",
                    "gastos": [
                        {
                            "id": 5892,
                            "incidencia_gasto_id": 10857,
                            "catalogo_gasto_id": 169,
                            "monto": 1100,
                            "created_at": "2019-09-10 12:34:57",
                            "updated_at": "2024-02-27 13:51:34",
                            "evidencias": [
                                {
                                    "id": 14538,
                                    "incidencia_gasto_id": 10857,
                                    "incidencia_gasto_extra_id": 5892,
                                    "url_archivo": "uploads/images/incidencias/gastos//0oG3OZ5dz8qmc4PU4iOzhF1n0TgpFZ8xt6NPmK8O.jpeg",
                                    "created_at": "2024-02-28 15:25:15",
                                    "updated_at": "2024-02-28 15:25:15"
                                }
                            ]
                        },
                        {
                            "id": 5893,
                            "incidencia_gasto_id": 10857,
                            "catalogo_gasto_id": 175,
                            "monto": 2000,
                            "created_at": "2019-09-10 12:34:57",
                            "updated_at": "2024-02-27 13:51:38",
                            "evidencias": [
                                {
                                    "id": 14539,
                                    "incidencia_gasto_id": 10857,
                                    "incidencia_gasto_extra_id": 5893,
                                    "url_archivo": "uploads/images/incidencias/gastos//yg05OGyJCztq6BJvRqPrIdzIedL2bLwbUUjpVZYK.jpeg",
                                    "created_at": "2024-02-28 15:25:25",
                                    "updated_at": "2024-02-28 15:25:25"
                                }
                            ]
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
                    "updated_at": "2019-08-02 19:12:49",
                    "deleted_at": null
                },
                "agente": {
                    "id": 141,
                    "user_id": 10009,
                    "numero_control": "222222222",
                    "estatus": 1,
                    "puesto": null,
                    "created_at": "2018-11-30 13:32:24",
                    "updated_at": "2023-10-23 17:57:43",
                    "deleted_at": null,
                    "lat": "18.9121214",
                    "lon": "-99.1913653",
                    "imagen": null,
                    "imagen_path": null,
                    "vehiculo_id": null,
                    "sucursal_base_id": 84,
                    "supervisor": 0,
                    "cant_errores_actuales": 17,
                    "sucursal_pickgo_id": null,
                    "user": {
                        "id": 10009,
                        "name": "REPARTIDOR CS",
                        "last_name": "NO ELIMINAR",
                        "second_last_name": "NO ELIMINAR",
                        "telephone": "7777777777",
                        "clave": null,
                        "email": "repartidorcs3@grupofarmapronto.com",
                        "player_id": "1e90920c-8831-4534-9b56-2733891cd7d9",
                        "tipo_usuario": "repartidor",
                        "activo": 1,
                        "baja": 0,
                        "fb_id": null,
                        "webhook_url": null,
                        "created_at": "2018-11-30 13:32:24",
                        "updated_at": "2023-11-20 17:02:45",
                        "deleted_at": null,
                        "last_login": null,
                        "user_delete_account": null,
                        "nombre_completo": "REPARTIDOR CS NO ELIMINAR"
                    }
                },
                "motivo": {
                    "id": 2,
                    "nombre": "Mantenimiento de la moto",
                    "key": "mantenimiento",
                    "prefix": "MT",
                    "created_at": "2019-05-21 13:28:24",
                    "updated_at": "2019-08-02 17:05:13"
                },
                "proveedor": {
                    "id": 74,
                    "nombre": "V. Rodriguez",
                    "ciudad": "Cuernavaca",
                    "direccion": "Nueva Italia, Lomas de cortés",
                    "servicios": null,
                    "created_at": "2019-06-18 10:41:30",
                    "updated_at": "2019-06-18 10:41:30",
                    "deleted_at": null
                }
            },
            "ultimaIncidencia": {
                "id": 10090,
                "agente_id": 141,
                "folio": "GA10090",
                "fecha": "2019-08-05 00:00:00",
                "km": "158",
                "km_evidencia": "uploads/images/incidencias/yOwwAK8GruasKSA2lZQQaIQfoBAzDhZDB0aczFKX.png",
                "motivo_id": 4,
                "vehiculo_id": 42,
                "observaciones": "carga de gas",
                "evidencia": "uploads/images/incidencias/LggY8meqcnaXp8aTlLAhDBo1OPSrFChoUAuBCEtK.png",
                "proveedor_id": null,
                "tipo_creacion": "dashboard_store",
                "mantenimiento_id": null,
                "created_at": "2019-08-05 16:00:08",
                "updated_at": "2019-08-05 16:00:08",
                "deleted_at": null,
                "deleted_user_id": null
            },
            "comparativos": [
                {
                    "nombre_gasto": "SOLDADURA BASE DE PROTECCIÓN ",
                    "fecha_anterior": null,
                    "monto_anterior": null,
                    "km_anterior": null,
                    "proveedor_anterior": null,
                    "monto_actual": 11,
                    "tipo_gasto_id": 169
                },
                {
                    "nombre_gasto": "MANO DE OBRA CHICOTE ACELERADOR",
                    "fecha_anterior": null,
                    "monto_anterior": null,
                    "km_anterior": null,
                    "proveedor_anterior": null,
                    "monto_actual": 20,
                    "tipo_gasto_id": 175
                }
            ]
        }

**Error Response:**

* **Code:** 401 Unauthorized <br />
  **Content:**

        {
          "error": "Unauthenticated."
        }
