## Registro de equipo nuevo para incidencia de soporte

Registra un equipo nuevo para una incidencia de soprte especificada por medio de un id y lo retorna.<br>

**URL**

    /api/incidencias-soporte/{incidencia}/equipo-nuevo

**BODY PARAMS**

    'motivo_id' => 'nullable|exists:catalogo_motivos_incidencias_soporte,id',
    'sucursal_id' => 'nullable|exists:sucursales,id',
    'observaciones' => 'nullable',
    'catalogo_equipo_id' => 'required|exists:catalogo_equipos,id',
    'tipo' => 'nullable',
    'marca' => 'nullable',
    'num_serie' => 'nullable',
    'num_inventario' => 'nullable',
    'comentarios' => 'nullable',
    'evidencia' => 'image'

**REQUIRED URL PARAMS**

    {incidencia} => id de la incidencia de soporte

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
            "incidencia": {
                "id": 1427,
                "folio": "EQP001427",
                "sucursal_id": 7,
                "user_id": 641,
                "motivo_id": null,
                "fecha": "2022-05-10",
                "observaciones": "W7 no permite la configuración de las nuevas vaucheras",
                "tipo_creacion": "api_store",
                "created_at": "2022-05-10 10:38:43",
                "updated_at": "2022-05-10 10:38:43",
                "deleted_at": null,
                "razon_rechazo": null,
                "folio_activo": "REM001427"
            },
            "incidencia_equipo": {
                "incidencia_id": 1427,
                "tipo": "nuevo",
                "catalogo_equipo_id": "26",
                "marca": "test 2",
                "num_serie": "test 2",
                "num_inventario": "1",
                "comentarios": "test 2",
                "updated_at": "2024-02-08 10:19:38",
                "created_at": "2024-02-08 10:19:38",
                "id": 6183,
                "evidencia": "images/noimage.png",
                "evidencia_equipo_asignado": "images/noimage.png",
                "evidencia_confirmada": "images/noimage.png",
                "evidencia_equipo_nuevo_embarcado": "images/noimage.png",
                "evidencia_equipo_nuevo_en_transito": "images/noimage.png",
                "evidencia_confirmacion_entrega": "images/noimage.png",
                "evidencia_equipo_funcionando": "images/noimage.png",
                "evidencia_embarque_equipo_malo": "images/noimage.png",
                "evidencia_en_transito_equipo_malo": "images/noimage.png",
                "evidencia_diagnostico": "images/noimage.png",
                "evidencia_recepcion_equipo_malo": "images/noimage.png",
                "media": []
            }
        }

**Error Response:**

* **Code:** 200 <br/>
  **Content:**

        {
            "message": "Ya se registro un equipo nuevo para la incidencia: EQP001427"
        }

* **Code:** 401 Unauthorized <br />
  **Content:**

        {
          "error": "Unauthenticated."
        }

## Actualiza incidencia de soporte

Actualiza una incidencia de soprte especificada por medio de un id de incidencia-equipo y la retorna.<br>

**URL**

    /api/incidencias-soporte/equipos/{incidencia_equipo}

**BODY PARAMS**

    'motivo' => 'required|in:actualizar,confirma_sucursal,registra_evidencia_soporte,envio,confirmar_recepcion_equipo,sucursal_funcionando,embarque_equipo_malo,en_transito_equipo_malo,diagnostico,recepcion_equipo_malo,pendiente_destruccion,destruir',
    'accion' => 'nullable|in:aceptar,rechazar',
    'medio_envio' => 'nullable|required_if:motivo,metodo_envio|in:paquetería,supervisor,enlace',
    'evidencia' => 'nullable|image',
    'accion' => 'in:confirmar,rechazar',
    'sucursal_id' => 'nullable|exists:sucursales,id',
    'observaciones' => 'nullable',
    'catalogo_equipo_id' => 'nullable|exists:catalogo_equipos,id',
    'marca' => 'nullable',
    'num_serie' => 'nullable',
    'num_inventario' => 'nullable',
    'comentarios' => 'nullable',
    'pendiente_destruccion' => 'boolean|nullable',
    'confirmar_destruccion' => 'boolean|nullable',
    'equipo_malo' => 'boolean|nullable',
    'comentario_diagnostico' => 'nullable',
    'incidencias_equipos_ids' => 'array|nullable'

**REQUIRED URL PARAMS**

    {incidencia_equipo} => id del equipo de la incidencia

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
            "incidencia": {
                "id": 1427,
                "folio": "EQP001427",
                "sucursal_id": 7,
                "user_id": 641,
                "motivo_id": null,
                "fecha": "2022-05-10",
                "observaciones": "W7 no permite la configuración de las nuevas vaucheras",
                "tipo_creacion": "api_store",
                "created_at": "2022-05-10 10:38:43",
                "updated_at": "2022-05-10 10:38:43",
                "deleted_at": null,
                "razon_rechazo": null,
                "folio_activo": "REM001427",
                "estatus": [
                    {
                        "id": 1,
                        "nombre": "Registrada",
                        "key": "registrada",
                        "created_at": "2020-08-11 14:42:40",
                        "updated_at": "2020-08-11 14:42:40",
                        "deleted_at": null,
                        "pivot": {
                            "incidencia_id": 1427,
                            "estatus_id": 1,
                            "user_id": 641,
                            "incidencia_soporte_equipo_id": 2596,
                            "created_at": "2022-05-10 10:38:43",
                            "updated_at": "2022-05-10 10:38:43"
                        }
                    },
                    {
                        "id": 10,
                        "nombre": "Equipo nuevo embarcado",
                        "key": "equipo_nuevo_embarcado",
                        "created_at": "2020-11-03 20:40:14",
                        "updated_at": "2020-11-03 20:40:14",
                        "deleted_at": null,
                        "pivot": {
                            "incidencia_id": 1427,
                            "estatus_id": 10,
                            "user_id": 641,
                            "incidencia_soporte_equipo_id": 2612,
                            "created_at": "2022-05-16 10:59:36",
                            "updated_at": "2022-05-16 10:59:36"
                        }
                    },
                    {
                        "id": 11,
                        "nombre": "Equipo nuevo en transito",
                        "key": "equipo_nuevo_en_transito",
                        "created_at": "2020-11-04 11:09:35",
                        "updated_at": "2020-11-04 11:09:35",
                        "deleted_at": null,
                        "pivot": {
                            "incidencia_id": 1427,
                            "estatus_id": 11,
                            "user_id": 641,
                            "incidencia_soporte_equipo_id": 2612,
                            "created_at": "2022-05-16 11:04:04",
                            "updated_at": "2022-05-16 11:04:04"
                        }
                    },
                    {
                        "id": 12,
                        "nombre": "Recepción de equipo dañado",
                        "key": "recepcion_equipo_malo",
                        "created_at": "2020-11-04 11:47:04",
                        "updated_at": "2020-11-04 11:47:04",
                        "deleted_at": null,
                        "pivot": {
                            "incidencia_id": 1427,
                            "estatus_id": 12,
                            "user_id": 288,
                            "incidencia_soporte_equipo_id": 2596,
                            "created_at": "2022-07-25 15:31:05",
                            "updated_at": "2022-07-25 15:31:05"
                        }
                    },
                    {
                        "id": 13,
                        "nombre": "Confirmada Sucursal",
                        "key": "confirmada",
                        "created_at": "2020-11-04 12:00:14",
                        "updated_at": "2020-11-04 12:00:14",
                        "deleted_at": null,
                        "pivot": {
                            "incidencia_id": 1427,
                            "estatus_id": 13,
                            "user_id": 172,
                            "incidencia_soporte_equipo_id": 2596,
                            "created_at": "2022-05-10 10:41:28",
                            "updated_at": "2022-05-10 10:41:28"
                        }
                    },
                    {
                        "id": 14,
                        "nombre": "Confirmación de entrega",
                        "key": "confirmacion_entrega",
                        "created_at": "2020-11-04 12:00:37",
                        "updated_at": "2020-11-04 12:00:37",
                        "deleted_at": null,
                        "pivot": {
                            "incidencia_id": 1427,
                            "estatus_id": 14,
                            "user_id": 651,
                            "incidencia_soporte_equipo_id": 2612,
                            "created_at": "2022-05-26 17:22:13",
                            "updated_at": "2022-05-26 17:22:13"
                        }
                    },
                    {
                        "id": 15,
                        "nombre": "Equipo funcionando",
                        "key": "equipo_funcionando",
                        "created_at": "2020-11-04 12:00:47",
                        "updated_at": "2020-11-04 12:00:47",
                        "deleted_at": null,
                        "pivot": {
                            "incidencia_id": 1427,
                            "estatus_id": 15,
                            "user_id": 172,
                            "incidencia_soporte_equipo_id": 2612,
                            "created_at": "2022-05-30 18:54:56",
                            "updated_at": "2022-05-30 18:54:56"
                        }
                    },
                    {
                        "id": 16,
                        "nombre": "Embarque equipo dañado",
                        "key": "embarque_equipo_malo",
                        "created_at": "2020-11-04 12:00:58",
                        "updated_at": "2020-11-04 12:00:58",
                        "deleted_at": null,
                        "pivot": {
                            "incidencia_id": 1427,
                            "estatus_id": 16,
                            "user_id": 172,
                            "incidencia_soporte_equipo_id": 2596,
                            "created_at": "2022-05-22 11:28:40",
                            "updated_at": "2022-05-22 11:28:40"
                        }
                    },
                    {
                        "id": 17,
                        "nombre": "En transito equipo dañado",
                        "key": "en_transito_equipo_malo",
                        "created_at": "2020-11-04 12:01:10",
                        "updated_at": "2020-11-04 12:01:10",
                        "deleted_at": null,
                        "pivot": {
                            "incidencia_id": 1427,
                            "estatus_id": 17,
                            "user_id": 651,
                            "incidencia_soporte_equipo_id": 2596,
                            "created_at": "2022-05-26 17:17:52",
                            "updated_at": "2022-05-26 17:17:52"
                        }
                    },
                    {
                        "id": 18,
                        "nombre": "Diagnostico de equipo dañado",
                        "key": "diagnostico",
                        "created_at": "2020-11-04 12:01:24",
                        "updated_at": "2020-11-04 12:01:24",
                        "deleted_at": null,
                        "pivot": {
                            "incidencia_id": 1427,
                            "estatus_id": 18,
                            "user_id": 641,
                            "incidencia_soporte_equipo_id": 2596,
                            "created_at": "2022-08-10 11:31:03",
                            "updated_at": "2022-08-10 11:31:03"
                        }
                    },
                    {
                        "id": 19,
                        "nombre": "Equipo asignado",
                        "key": "equipo_asignado",
                        "created_at": "2020-11-04 12:12:52",
                        "updated_at": "2020-11-04 12:12:52",
                        "deleted_at": null,
                        "pivot": {
                            "incidencia_id": 1427,
                            "estatus_id": 19,
                            "user_id": 1,
                            "incidencia_soporte_equipo_id": 6183,
                            "created_at": "2022-05-14 11:10:10",
                            "updated_at": "2024-02-08 10:19:38"
                        }
                    },
                    {
                        "id": 21,
                        "nombre": "Destruir",
                        "key": "destruir",
                        "created_at": "2020-11-04 17:41:52",
                        "updated_at": "2020-11-04 17:41:52",
                        "deleted_at": null,
                        "pivot": {
                            "incidencia_id": 1427,
                            "estatus_id": 21,
                            "user_id": 1,
                            "incidencia_soporte_equipo_id": 6183,
                            "created_at": "2024-02-08 10:52:21",
                            "updated_at": "2024-02-08 10:52:21"
                        }
                    }
                ]
            },
            "incidencia_equipo": {
                "id": 6183,
                "incidencia_id": 1427,
                "tipo": "nuevo",
                "marca": "test 2",
                "num_serie": "test 2",
                "num_inventario": "1",
                "aprobado_por": null,
                "comentarios": "test 2",
                "created_at": "2024-02-08 10:19:38",
                "updated_at": "2024-02-08 10:19:38",
                "deleted_at": null,
                "catalogo_equipo_id": 26,
                "pendiente_destruccion": null,
                "confirmar_destruccion": null,
                "equipo_malo": null,
                "comentario_diagnostico": null,
                "medio_envio": null,
                "evidencia": "images/noimage.png",
                "evidencia_equipo_asignado": "images/noimage.png",
                "evidencia_confirmada": "images/noimage.png",
                "evidencia_equipo_nuevo_embarcado": "images/noimage.png",
                "evidencia_equipo_nuevo_en_transito": "images/noimage.png",
                "evidencia_confirmacion_entrega": "images/noimage.png",
                "evidencia_equipo_funcionando": "images/noimage.png",
                "evidencia_embarque_equipo_malo": "images/noimage.png",
                "evidencia_en_transito_equipo_malo": "images/noimage.png",
                "evidencia_diagnostico": "images/noimage.png",
                "evidencia_recepcion_equipo_malo": "images/noimage.png",
                "incidencia": {
                    "id": 1427,
                    "folio": "EQP001427",
                    "sucursal_id": 7,
                    "user_id": 641,
                    "motivo_id": null,
                    "fecha": "2022-05-10",
                    "observaciones": "W7 no permite la configuración de las nuevas vaucheras",
                    "tipo_creacion": "api_store",
                    "created_at": "2022-05-10 10:38:43",
                    "updated_at": "2022-05-10 10:38:43",
                    "deleted_at": null,
                    "razon_rechazo": null,
                    "folio_activo": "REM001427"
                },
                "estatus": [
                    {
                        "id": 21,
                        "nombre": "Destruir",
                        "key": "destruir",
                        "created_at": "2020-11-04 17:41:52",
                        "updated_at": "2020-11-04 17:41:52",
                        "deleted_at": null,
                        "pivot": {
                            "incidencia_soporte_equipo_id": 6183,
                            "estatus_id": 21,
                            "user_id": 1,
                            "incidencia_id": 1427,
                            "created_at": "2024-02-08 10:52:21",
                            "updated_at": "2024-02-08 10:52:21"
                        }
                    },
                    {
                        "id": 19,
                        "nombre": "Equipo asignado",
                        "key": "equipo_asignado",
                        "created_at": "2020-11-04 12:12:52",
                        "updated_at": "2020-11-04 12:12:52",
                        "deleted_at": null,
                        "pivot": {
                            "incidencia_soporte_equipo_id": 6183,
                            "estatus_id": 19,
                            "user_id": 1,
                            "incidencia_id": 1427,
                            "created_at": "2022-05-14 11:10:10",
                            "updated_at": "2024-02-08 10:19:38"
                        }
                    }
                ],
                "media": []
            },
            "estatus": {
                "id": 21,
                "nombre": "Destruir",
                "key": "destruir",
                "created_at": "2020-11-04 17:41:52",
                "updated_at": "2020-11-04 17:41:52",
                "deleted_at": null
            }
        }

**Error Response:**

* **Code:** 401 Unauthorized <br />
  **Content:**

        {
          "error": "Unauthenticated."
        }

## Lista equipos pendientes por destruir

Retorna una lista de equipos pendientes a destruir<br>

**URL**

    /api/incidencias-soporte/equipos/pendiente-destruccion

**BODY PARAMS**

    N/A

**REQUIRED URL PARAMS**

    N/A

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
            "incidencias_equipo": [
                {
                    "id": 5946,
                    "incidencia_id": 3253,
                    "tipo": "reemplazado",
                    "marca": "acteck",
                    "num_serie": "940233277214",
                    "num_inventario": "1",
                    "aprobado_por": null,
                    "comentarios": null,
                    "created_at": "2023-12-02 10:48:28",
                    "updated_at": "2024-01-08 18:59:58",
                    "deleted_at": null,
                    "catalogo_equipo_id": 23,
                    "pendiente_destruccion": true,
                    "confirmar_destruccion": null,
                    "equipo_malo": true,
                    "comentario_diagnostico": "fuente y tarjeta quemadas, se rescata disco y ram",
                    "medio_envio": null,
                    "evidencia": "images/noimage.png",
                    "evidencia_equipo_asignado": "images/noimage.png",
                    "evidencia_confirmada": "https://sfo2.digitaloceanspaces.com/farmapronto-sucursales/incidencias-soporte/1424585/1701535779375.jpg",
                    "evidencia_equipo_nuevo_embarcado": "images/noimage.png",
                    "evidencia_equipo_nuevo_en_transito": "images/noimage.png",
                    "evidencia_confirmacion_entrega": "images/noimage.png",
                    "evidencia_equipo_funcionando": "images/noimage.png",
                    "evidencia_embarque_equipo_malo": "https://sfo2.digitaloceanspaces.com/farmapronto-sucursales/incidencias-soporte/1429219/1701887530839.jpg",
                    "evidencia_en_transito_equipo_malo": "https://sfo2.digitaloceanspaces.com/farmapronto-sucursales/incidencias-soporte/1435340/1702331754849.jpg",
                    "evidencia_diagnostico": "images/noimage.png",
                    "evidencia_recepcion_equipo_malo": "https://sfo2.digitaloceanspaces.com/farmapronto-sucursales/incidencias-soporte/1456545/1703883407212.jpg",
                    "media": [
                        {
                            "id": 1456545,
                            "model_type": "App\\Entities\\IncidenciasSoporte\\IncidenciaSoporteEquipo",
                            "model_id": 5946,
                            "collection_name": "recepcion_equipo_malo",
                            "name": "1703883407212",
                            "file_name": "1703883407212.jpg",
                            "mime_type": "image/jpeg",
                            "disk": "evidencias",
                            "size": 99350,
                            "manipulations": [],
                            "custom_properties": [],
                            "responsive_images": [],
                            "order_column": 1328013,
                            "created_at": "2023-12-29 14:56:58",
                            "updated_at": "2023-12-29 14:56:58"
                        },
                        {
                            "id": 1435340,
                            "model_type": "App\\Entities\\IncidenciasSoporte\\IncidenciaSoporteEquipo",
                            "model_id": 5946,
                            "collection_name": "en_transito_equipo_malo",
                            "name": "1702331754849",
                            "file_name": "1702331754849.jpg",
                            "mime_type": "image/jpeg",
                            "disk": "evidencias",
                            "size": 90254,
                            "manipulations": [],
                            "custom_properties": [],
                            "responsive_images": [],
                            "order_column": 1310304,
                            "created_at": "2023-12-11 15:56:02",
                            "updated_at": "2023-12-11 15:56:02"
                        },
                        {
                            "id": 1424585,
                            "model_type": "App\\Entities\\IncidenciasSoporte\\IncidenciaSoporteEquipo",
                            "model_id": 5946,
                            "collection_name": "confirmada",
                            "name": "1701535779375",
                            "file_name": "1701535779375.jpg",
                            "mime_type": "image/jpeg",
                            "disk": "evidencias",
                            "size": 98187,
                            "manipulations": [],
                            "custom_properties": [],
                            "responsive_images": [],
                            "order_column": 1301216,
                            "created_at": "2023-12-02 10:49:07",
                            "updated_at": "2023-12-02 10:49:07"
                        },
                        {
                            "id": 1429219,
                            "model_type": "App\\Entities\\IncidenciasSoporte\\IncidenciaSoporteEquipo",
                            "model_id": 5946,
                            "collection_name": "embarque_equipo_malo",
                            "name": "1701887530839",
                            "file_name": "1701887530839.jpg",
                            "mime_type": "image/jpeg",
                            "disk": "evidencias",
                            "size": 93897,
                            "manipulations": [],
                            "custom_properties": [],
                            "responsive_images": [],
                            "order_column": 1305130,
                            "created_at": "2023-12-06 12:39:12",
                            "updated_at": "2023-12-06 12:39:12"
                        },
                        {
                            "id": 1468104,
                            "model_type": "App\\Entities\\IncidenciasSoporte\\IncidenciaSoporteEquipo",
                            "model_id": 5946,
                            "collection_name": "pendiente_destruccion",
                            "name": "1704761992785",
                            "file_name": "1704761992785.jpg",
                            "mime_type": "image/jpeg",
                            "disk": "evidencias",
                            "size": 142573,
                            "manipulations": [],
                            "custom_properties": [],
                            "responsive_images": [],
                            "order_column": 1337605,
                            "created_at": "2024-01-08 18:59:58",
                            "updated_at": "2024-01-08 18:59:58"
                        }
                    ]
                },
                {
                    "id": 6033,
                    "incidencia_id": 3314,
                    "tipo": "reemplazado",
                    "marca": "n/a",
                    "num_serie": "n/a",
                    "num_inventario": "1",
                    "aprobado_por": null,
                    "comentarios": "ya no enciende por un corto en entrada de corriente cpu",
                    "created_at": "2023-12-14 14:01:49",
                    "updated_at": "2024-01-08 17:51:27",
                    "deleted_at": null,
                    "catalogo_equipo_id": 27,
                    "pendiente_destruccion": true,
                    "confirmar_destruccion": null,
                    "equipo_malo": true,
                    "comentario_diagnostico": "tarjeta madre en corto",
                    "medio_envio": null,
                    "evidencia": "images/noimage.png",
                    "evidencia_equipo_asignado": "images/noimage.png",
                    "evidencia_confirmada": "https://sfo2.digitaloceanspaces.com/farmapronto-sucursales/incidencias-soporte/1440743/1702731921393.jpg",
                    "evidencia_equipo_nuevo_embarcado": "images/noimage.png",
                    "evidencia_equipo_nuevo_en_transito": "images/noimage.png",
                    "evidencia_confirmacion_entrega": "images/noimage.png",
                    "evidencia_equipo_funcionando": "images/noimage.png",
                    "evidencia_embarque_equipo_malo": "https://sfo2.digitaloceanspaces.com/farmapronto-sucursales/incidencias-soporte/1449547/1703363699986.jpg",
                    "evidencia_en_transito_equipo_malo": "https://sfo2.digitaloceanspaces.com/farmapronto-sucursales/incidencias-soporte/1452568/1703618523445.jpg",
                    "evidencia_diagnostico": "images/noimage.png",
                    "evidencia_recepcion_equipo_malo": "https://sfo2.digitaloceanspaces.com/farmapronto-sucursales/incidencias-soporte/1461878/1704313398568.jpg",
                    "media": [
                        {
                            "id": 1440743,
                            "model_type": "App\\Entities\\IncidenciasSoporte\\IncidenciaSoporteEquipo",
                            "model_id": 6033,
                            "collection_name": "confirmada",
                            "name": "1702731921393",
                            "file_name": "1702731921393.jpg",
                            "mime_type": "image/jpeg",
                            "disk": "evidencias",
                            "size": 78360,
                            "manipulations": [],
                            "custom_properties": [],
                            "responsive_images": [],
                            "order_column": 1314879,
                            "created_at": "2023-12-16 07:06:21",
                            "updated_at": "2023-12-16 07:06:21"
                        },
                        {
                            "id": 1449547,
                            "model_type": "App\\Entities\\IncidenciasSoporte\\IncidenciaSoporteEquipo",
                            "model_id": 6033,
                            "collection_name": "embarque_equipo_malo",
                            "name": "1703363699986",
                            "file_name": "1703363699986.jpg",
                            "mime_type": "image/jpeg",
                            "disk": "evidencias",
                            "size": 102034,
                            "manipulations": [],
                            "custom_properties": [],
                            "responsive_images": [],
                            "order_column": 1322266,
                            "created_at": "2023-12-23 14:35:08",
                            "updated_at": "2023-12-23 14:35:08"
                        },
                        {
                            "id": 1461878,
                            "model_type": "App\\Entities\\IncidenciasSoporte\\IncidenciaSoporteEquipo",
                            "model_id": 6033,
                            "collection_name": "recepcion_equipo_malo",
                            "name": "1704313398568",
                            "file_name": "1704313398568.jpg",
                            "mime_type": "image/jpeg",
                            "disk": "evidencias",
                            "size": 98686,
                            "manipulations": [],
                            "custom_properties": [],
                            "responsive_images": [],
                            "order_column": 1332410,
                            "created_at": "2024-01-03 14:23:30",
                            "updated_at": "2024-01-03 14:23:30"
                        },
                        {
                            "id": 1452568,
                            "model_type": "App\\Entities\\IncidenciasSoporte\\IncidenciaSoporteEquipo",
                            "model_id": 6033,
                            "collection_name": "en_transito_equipo_malo",
                            "name": "1703618523445",
                            "file_name": "1703618523445.jpg",
                            "mime_type": "image/jpeg",
                            "disk": "evidencias",
                            "size": 109346,
                            "manipulations": [],
                            "custom_properties": [],
                            "responsive_images": [],
                            "order_column": 1324738,
                            "created_at": "2023-12-26 13:22:25",
                            "updated_at": "2023-12-26 13:22:25"
                        },
                        {
                            "id": 1468093,
                            "model_type": "App\\Entities\\IncidenciasSoporte\\IncidenciaSoporteEquipo",
                            "model_id": 6033,
                            "collection_name": "pendiente_destruccion",
                            "name": "1704757880587",
                            "file_name": "1704757880587.jpg",
                            "mime_type": "image/jpeg",
                            "disk": "evidencias",
                            "size": 129189,
                            "manipulations": [],
                            "custom_properties": [],
                            "responsive_images": [],
                            "order_column": 1337594,
                            "created_at": "2024-01-08 17:51:27",
                            "updated_at": "2024-01-08 17:51:27"
                        }
                    ]
                },
                {
                    "id": 6038,
                    "incidencia_id": 3317,
                    "tipo": "reemplazado",
                    "marca": "asus",
                    "num_serie": "K9msac006535a9h",
                    "num_inventario": "0",
                    "aprobado_por": null,
                    "comentarios": null,
                    "created_at": "2023-12-14 18:46:30",
                    "updated_at": "2024-01-10 18:30:58",
                    "deleted_at": null,
                    "catalogo_equipo_id": 11,
                    "pendiente_destruccion": true,
                    "confirmar_destruccion": null,
                    "equipo_malo": true,
                    "comentario_diagnostico": "no enciende, se rescata ram y hdd",
                    "medio_envio": null,
                    "evidencia": "images/noimage.png",
                    "evidencia_equipo_asignado": "images/noimage.png",
                    "evidencia_confirmada": "https://sfo2.digitaloceanspaces.com/farmapronto-sucursales/incidencias-soporte/1439300/1702606772785.jpg",
                    "evidencia_equipo_nuevo_embarcado": "images/noimage.png",
                    "evidencia_equipo_nuevo_en_transito": "images/noimage.png",
                    "evidencia_confirmacion_entrega": "images/noimage.png",
                    "evidencia_equipo_funcionando": "images/noimage.png",
                    "evidencia_embarque_equipo_malo": "https://sfo2.digitaloceanspaces.com/farmapronto-sucursales/incidencias-soporte/1453778/1703703378071.jpg",
                    "evidencia_en_transito_equipo_malo": "https://sfo2.digitaloceanspaces.com/farmapronto-sucursales/incidencias-soporte/1456404/1703877351326.jpg",
                    "evidencia_diagnostico": "images/noimage.png",
                    "evidencia_recepcion_equipo_malo": "https://sfo2.digitaloceanspaces.com/farmapronto-sucursales/incidencias-soporte/1457436/1703958761820.jpg",
                    "media": [
                        {
                            "id": 1470579,
                            "model_type": "App\\Entities\\IncidenciasSoporte\\IncidenciaSoporteEquipo",
                            "model_id": 6038,
                            "collection_name": "pendiente_destruccion",
                            "name": "1704933050692",
                            "file_name": "1704933050692.jpg",
                            "mime_type": "image/jpeg",
                            "disk": "evidencias",
                            "size": 126828,
                            "manipulations": [],
                            "custom_properties": [],
                            "responsive_images": [],
                            "order_column": 1339726,
                            "created_at": "2024-01-10 18:30:58",
                            "updated_at": "2024-01-10 18:30:58"
                        },
                        {
                            "id": 1439300,
                            "model_type": "App\\Entities\\IncidenciasSoporte\\IncidenciaSoporteEquipo",
                            "model_id": 6038,
                            "collection_name": "confirmada",
                            "name": "1702606772785",
                            "file_name": "1702606772785.jpg",
                            "mime_type": "image/jpeg",
                            "disk": "evidencias",
                            "size": 80448,
                            "manipulations": [],
                            "custom_properties": [],
                            "responsive_images": [],
                            "order_column": 1313636,
                            "created_at": "2023-12-14 20:21:02",
                            "updated_at": "2023-12-14 20:21:02"
                        },
                        {
                            "id": 1453778,
                            "model_type": "App\\Entities\\IncidenciasSoporte\\IncidenciaSoporteEquipo",
                            "model_id": 6038,
                            "collection_name": "embarque_equipo_malo",
                            "name": "1703703378071",
                            "file_name": "1703703378071.jpg",
                            "mime_type": "image/jpeg",
                            "disk": "evidencias",
                            "size": 125753,
                            "manipulations": [],
                            "custom_properties": [],
                            "responsive_images": [],
                            "order_column": 1325764,
                            "created_at": "2023-12-27 12:57:40",
                            "updated_at": "2023-12-27 12:57:40"
                        },
                        {
                            "id": 1456404,
                            "model_type": "App\\Entities\\IncidenciasSoporte\\IncidenciaSoporteEquipo",
                            "model_id": 6038,
                            "collection_name": "en_transito_equipo_malo",
                            "name": "1703877351326",
                            "file_name": "1703877351326.jpg",
                            "mime_type": "image/jpeg",
                            "disk": "evidencias",
                            "size": 98344,
                            "manipulations": [],
                            "custom_properties": [],
                            "responsive_images": [],
                            "order_column": 1327881,
                            "created_at": "2023-12-29 13:16:46",
                            "updated_at": "2023-12-29 13:16:46"
                        },
                        {
                            "id": 1457436,
                            "model_type": "App\\Entities\\IncidenciasSoporte\\IncidenciaSoporteEquipo",
                            "model_id": 6038,
                            "collection_name": "recepcion_equipo_malo",
                            "name": "1703958761820",
                            "file_name": "1703958761820.jpg",
                            "mime_type": "image/jpeg",
                            "disk": "evidencias",
                            "size": 106800,
                            "manipulations": [],
                            "custom_properties": [],
                            "responsive_images": [],
                            "order_column": 1328760,
                            "created_at": "2023-12-30 11:52:52",
                            "updated_at": "2023-12-30 11:52:52"
                        }
                    ]
                },
                {
                    "id": 6061,
                    "incidencia_id": 3328,
                    "tipo": "reemplazado",
                    "marca": "ec80320",
                    "num_serie": "14060822",
                    "num_inventario": "1",
                    "aprobado_por": null,
                    "comentarios": null,
                    "created_at": "2023-12-20 15:06:32",
                    "updated_at": "2024-01-09 19:56:33",
                    "deleted_at": null,
                    "catalogo_equipo_id": 30,
                    "pendiente_destruccion": true,
                    "confirmar_destruccion": null,
                    "equipo_malo": true,
                    "comentario_diagnostico": "mecanismo de del cortar papel dañado,",
                    "medio_envio": null,
                    "evidencia": "images/noimage.png",
                    "evidencia_equipo_asignado": "images/noimage.png",
                    "evidencia_confirmada": "https://sfo2.digitaloceanspaces.com/farmapronto-sucursales/incidencias-soporte/1447026/1703189016706.jpg",
                    "evidencia_equipo_nuevo_embarcado": "images/noimage.png",
                    "evidencia_equipo_nuevo_en_transito": "images/noimage.png",
                    "evidencia_confirmacion_entrega": "images/noimage.png",
                    "evidencia_equipo_funcionando": "images/noimage.png",
                    "evidencia_embarque_equipo_malo": "https://sfo2.digitaloceanspaces.com/farmapronto-sucursales/incidencias-soporte/1459686/1704136837081.jpg",
                    "evidencia_en_transito_equipo_malo": "https://sfo2.digitaloceanspaces.com/farmapronto-sucursales/incidencias-soporte/1464352/1704485470591.jpg",
                    "evidencia_diagnostico": "images/noimage.png",
                    "evidencia_recepcion_equipo_malo": "https://sfo2.digitaloceanspaces.com/farmapronto-sucursales/incidencias-soporte/1468900/1704825283677.jpg",
                    "media": [
                        {
                            "id": 1447026,
                            "model_type": "App\\Entities\\IncidenciasSoporte\\IncidenciaSoporteEquipo",
                            "model_id": 6061,
                            "collection_name": "confirmada",
                            "name": "1703189016706",
                            "file_name": "1703189016706.jpg",
                            "mime_type": "image/jpeg",
                            "disk": "evidencias",
                            "size": 73656,
                            "manipulations": [],
                            "custom_properties": [],
                            "responsive_images": [],
                            "order_column": 1320139,
                            "created_at": "2023-12-21 14:04:36",
                            "updated_at": "2023-12-21 14:04:36"
                        },
                        {
                            "id": 1459686,
                            "model_type": "App\\Entities\\IncidenciasSoporte\\IncidenciaSoporteEquipo",
                            "model_id": 6061,
                            "collection_name": "embarque_equipo_malo",
                            "name": "1704136837081",
                            "file_name": "1704136837081.jpg",
                            "mime_type": "image/jpeg",
                            "disk": "evidencias",
                            "size": 101994,
                            "manipulations": [],
                            "custom_properties": [],
                            "responsive_images": [],
                            "order_column": 1330657,
                            "created_at": "2024-01-01 13:20:53",
                            "updated_at": "2024-01-01 13:20:53"
                        },
                        {
                            "id": 1464352,
                            "model_type": "App\\Entities\\IncidenciasSoporte\\IncidenciaSoporteEquipo",
                            "model_id": 6061,
                            "collection_name": "en_transito_equipo_malo",
                            "name": "1704485470591",
                            "file_name": "1704485470591.jpg",
                            "mime_type": "image/jpeg",
                            "disk": "evidencias",
                            "size": 76831,
                            "manipulations": [],
                            "custom_properties": [],
                            "responsive_images": [],
                            "order_column": 1334466,
                            "created_at": "2024-01-05 14:11:27",
                            "updated_at": "2024-01-05 14:11:27"
                        },
                        {
                            "id": 1468900,
                            "model_type": "App\\Entities\\IncidenciasSoporte\\IncidenciaSoporteEquipo",
                            "model_id": 6061,
                            "collection_name": "recepcion_equipo_malo",
                            "name": "1704825283677",
                            "file_name": "1704825283677.jpg",
                            "mime_type": "image/jpeg",
                            "disk": "evidencias",
                            "size": 77305,
                            "manipulations": [],
                            "custom_properties": [],
                            "responsive_images": [],
                            "order_column": 1338287,
                            "created_at": "2024-01-09 12:34:51",
                            "updated_at": "2024-01-09 12:34:51"
                        },
                        {
                            "id": 1469302,
                            "model_type": "App\\Entities\\IncidenciasSoporte\\IncidenciaSoporteEquipo",
                            "model_id": 6061,
                            "collection_name": "pendiente_destruccion",
                            "name": "1704851787572",
                            "file_name": "1704851787572.jpg",
                            "mime_type": "image/jpeg",
                            "disk": "evidencias",
                            "size": 83052,
                            "manipulations": [],
                            "custom_properties": [],
                            "responsive_images": [],
                            "order_column": 1338658,
                            "created_at": "2024-01-09 19:56:33",
                            "updated_at": "2024-01-09 19:56:33"
                        }
                    ]
                },
                {
                    "id": 6079,
                    "incidencia_id": 3337,
                    "tipo": "reemplazado",
                    "marca": "Posline",
                    "num_serie": "C47487",
                    "num_inventario": "1",
                    "aprobado_por": null,
                    "comentarios": "no escanea",
                    "created_at": "2023-12-22 13:33:11",
                    "updated_at": "2024-01-09 20:30:55",
                    "deleted_at": null,
                    "catalogo_equipo_id": 56,
                    "pendiente_destruccion": true,
                    "confirmar_destruccion": null,
                    "equipo_malo": true,
                    "comentario_diagnostico": "cable usb deteriorado, no transfiere datos",
                    "medio_envio": null,
                    "evidencia": "images/noimage.png",
                    "evidencia_equipo_asignado": "images/noimage.png",
                    "evidencia_confirmada": "https://sfo2.digitaloceanspaces.com/farmapronto-sucursales/incidencias-soporte/1448327/1703273646652.jpg",
                    "evidencia_equipo_nuevo_embarcado": "images/noimage.png",
                    "evidencia_equipo_nuevo_en_transito": "images/noimage.png",
                    "evidencia_confirmacion_entrega": "images/noimage.png",
                    "evidencia_equipo_funcionando": "images/noimage.png",
                    "evidencia_embarque_equipo_malo": "https://sfo2.digitaloceanspaces.com/farmapronto-sucursales/incidencias-soporte/1457427/1703956308392.jpg",
                    "evidencia_en_transito_equipo_malo": "https://sfo2.digitaloceanspaces.com/farmapronto-sucursales/incidencias-soporte/1462857/1704388819685.jpg",
                    "evidencia_diagnostico": "images/noimage.png",
                    "evidencia_recepcion_equipo_malo": "https://sfo2.digitaloceanspaces.com/farmapronto-sucursales/incidencias-soporte/1468897/1704825189034.jpg",
                    "media": [
                        {
                            "id": 1448327,
                            "model_type": "App\\Entities\\IncidenciasSoporte\\IncidenciaSoporteEquipo",
                            "model_id": 6079,
                            "collection_name": "confirmada",
                            "name": "1703273646652",
                            "file_name": "1703273646652.jpg",
                            "mime_type": "image/jpeg",
                            "disk": "evidencias",
                            "size": 57825,
                            "manipulations": [],
                            "custom_properties": [],
                            "responsive_images": [],
                            "order_column": 1321223,
                            "created_at": "2023-12-22 13:34:27",
                            "updated_at": "2023-12-22 13:34:27"
                        },
                        {
                            "id": 1457427,
                            "model_type": "App\\Entities\\IncidenciasSoporte\\IncidenciaSoporteEquipo",
                            "model_id": 6079,
                            "collection_name": "embarque_equipo_malo",
                            "name": "1703956308392",
                            "file_name": "1703956308392.jpg",
                            "mime_type": "image/jpeg",
                            "disk": "evidencias",
                            "size": 57496,
                            "manipulations": [],
                            "custom_properties": [],
                            "responsive_images": [],
                            "order_column": 1328751,
                            "created_at": "2023-12-30 11:11:54",
                            "updated_at": "2023-12-30 11:11:54"
                        },
                        {
                            "id": 1462857,
                            "model_type": "App\\Entities\\IncidenciasSoporte\\IncidenciaSoporteEquipo",
                            "model_id": 6079,
                            "collection_name": "en_transito_equipo_malo",
                            "name": "1704388819685",
                            "file_name": "1704388819685.jpg",
                            "mime_type": "image/jpeg",
                            "disk": "evidencias",
                            "size": 68999,
                            "manipulations": [],
                            "custom_properties": [],
                            "responsive_images": [],
                            "order_column": 1333228,
                            "created_at": "2024-01-04 11:20:26",
                            "updated_at": "2024-01-04 11:20:26"
                        },
                        {
                            "id": 1469488,
                            "model_type": "App\\Entities\\IncidenciasSoporte\\IncidenciaSoporteEquipo",
                            "model_id": 6079,
                            "collection_name": "pendiente_destruccion",
                            "name": "1704853841858",
                            "file_name": "1704853841858.jpg",
                            "mime_type": "image/jpeg",
                            "disk": "evidencias",
                            "size": 110126,
                            "manipulations": [],
                            "custom_properties": [],
                            "responsive_images": [],
                            "order_column": 1338809,
                            "created_at": "2024-01-09 20:30:55",
                            "updated_at": "2024-01-09 20:30:55"
                        },
                        {
                            "id": 1468897,
                            "model_type": "App\\Entities\\IncidenciasSoporte\\IncidenciaSoporteEquipo",
                            "model_id": 6079,
                            "collection_name": "recepcion_equipo_malo",
                            "name": "1704825189034",
                            "file_name": "1704825189034.jpg",
                            "mime_type": "image/jpeg",
                            "disk": "evidencias",
                            "size": 124916,
                            "manipulations": [],
                            "custom_properties": [],
                            "responsive_images": [],
                            "order_column": 1338284,
                            "created_at": "2024-01-09 12:33:14",
                            "updated_at": "2024-01-09 12:33:14"
                        }
                    ]
                },
                {
                    "id": 6105,
                    "incidencia_id": 3351,
                    "tipo": "reemplazado",
                    "marca": "Logitech",
                    "num_serie": "2230MR08BC08",
                    "num_inventario": "1",
                    "aprobado_por": null,
                    "comentarios": "el cable está cortado",
                    "created_at": "2023-12-29 08:54:34",
                    "updated_at": "2024-01-10 17:04:33",
                    "deleted_at": null,
                    "catalogo_equipo_id": 3,
                    "pendiente_destruccion": true,
                    "confirmar_destruccion": null,
                    "equipo_malo": true,
                    "comentario_diagnostico": "no lo detectan los equipos",
                    "medio_envio": null,
                    "evidencia": "images/noimage.png",
                    "evidencia_equipo_asignado": "images/noimage.png",
                    "evidencia_confirmada": "https://sfo2.digitaloceanspaces.com/farmapronto-sucursales/incidencias-soporte/1456069/1703862648745.jpg",
                    "evidencia_equipo_nuevo_embarcado": "images/noimage.png",
                    "evidencia_equipo_nuevo_en_transito": "images/noimage.png",
                    "evidencia_confirmacion_entrega": "images/noimage.png",
                    "evidencia_equipo_funcionando": "images/noimage.png",
                    "evidencia_embarque_equipo_malo": "https://sfo2.digitaloceanspaces.com/farmapronto-sucursales/incidencias-soporte/1463988/1704466688930.jpg",
                    "evidencia_en_transito_equipo_malo": "https://sfo2.digitaloceanspaces.com/farmapronto-sucursales/incidencias-soporte/1464335/1704485307961.jpg",
                    "evidencia_diagnostico": "images/noimage.png",
                    "evidencia_recepcion_equipo_malo": "https://sfo2.digitaloceanspaces.com/farmapronto-sucursales/incidencias-soporte/1464341/1704485364629.jpg",
                    "media": [
                        {
                            "id": 1463988,
                            "model_type": "App\\Entities\\IncidenciasSoporte\\IncidenciaSoporteEquipo",
                            "model_id": 6105,
                            "collection_name": "embarque_equipo_malo",
                            "name": "1704466688930",
                            "file_name": "1704466688930.jpg",
                            "mime_type": "image/jpeg",
                            "disk": "evidencias",
                            "size": 83979,
                            "manipulations": [],
                            "custom_properties": [],
                            "responsive_images": [],
                            "order_column": 1334153,
                            "created_at": "2024-01-05 09:00:12",
                            "updated_at": "2024-01-05 09:00:12"
                        },
                        {
                            "id": 1456069,
                            "model_type": "App\\Entities\\IncidenciasSoporte\\IncidenciaSoporteEquipo",
                            "model_id": 6105,
                            "collection_name": "confirmada",
                            "name": "1703862648745",
                            "file_name": "1703862648745.jpg",
                            "mime_type": "image/jpeg",
                            "disk": "evidencias",
                            "size": 84365,
                            "manipulations": [],
                            "custom_properties": [],
                            "responsive_images": [],
                            "order_column": 1327617,
                            "created_at": "2023-12-29 09:12:54",
                            "updated_at": "2023-12-29 09:12:54"
                        },
                        {
                            "id": 1470560,
                            "model_type": "App\\Entities\\IncidenciasSoporte\\IncidenciaSoporteEquipo",
                            "model_id": 6105,
                            "collection_name": "pendiente_destruccion",
                            "name": "1704927866570",
                            "file_name": "1704927866570.jpg",
                            "mime_type": "image/jpeg",
                            "disk": "evidencias",
                            "size": 142055,
                            "manipulations": [],
                            "custom_properties": [],
                            "responsive_images": [],
                            "order_column": 1339708,
                            "created_at": "2024-01-10 17:04:33",
                            "updated_at": "2024-01-10 17:04:33"
                        },
                        {
                            "id": 1464335,
                            "model_type": "App\\Entities\\IncidenciasSoporte\\IncidenciaSoporteEquipo",
                            "model_id": 6105,
                            "collection_name": "en_transito_equipo_malo",
                            "name": "1704485307961",
                            "file_name": "1704485307961.jpg",
                            "mime_type": "image/jpeg",
                            "disk": "evidencias",
                            "size": 124610,
                            "manipulations": [],
                            "custom_properties": [],
                            "responsive_images": [],
                            "order_column": 1334449,
                            "created_at": "2024-01-05 14:08:38",
                            "updated_at": "2024-01-05 14:08:38"
                        },
                        {
                            "id": 1464341,
                            "model_type": "App\\Entities\\IncidenciasSoporte\\IncidenciaSoporteEquipo",
                            "model_id": 6105,
                            "collection_name": "recepcion_equipo_malo",
                            "name": "1704485364629",
                            "file_name": "1704485364629.jpg",
                            "mime_type": "image/jpeg",
                            "disk": "evidencias",
                            "size": 111257,
                            "manipulations": [],
                            "custom_properties": [],
                            "responsive_images": [],
                            "order_column": 1334455,
                            "created_at": "2024-01-05 14:09:36",
                            "updated_at": "2024-01-05 14:09:36"
                        }
                    ]
                },
                {
                    "id": 6106,
                    "incidencia_id": 3352,
                    "tipo": "reemplazado",
                    "marca": "Smarbitt",
                    "num_serie": "no visible",
                    "num_inventario": "1",
                    "aprobado_por": null,
                    "comentarios": null,
                    "created_at": "2023-12-29 10:30:43",
                    "updated_at": "2024-01-09 22:26:20",
                    "deleted_at": null,
                    "catalogo_equipo_id": 20,
                    "pendiente_destruccion": true,
                    "confirmar_destruccion": null,
                    "equipo_malo": true,
                    "comentario_diagnostico": "tarjeta dañada, se probó otra batería y falla persiste",
                    "medio_envio": null,
                    "evidencia": "images/noimage.png",
                    "evidencia_equipo_asignado": "images/noimage.png",
                    "evidencia_confirmada": "https://sfo2.digitaloceanspaces.com/farmapronto-sucursales/incidencias-soporte/1456133/1703867495593.jpg",
                    "evidencia_equipo_nuevo_embarcado": "images/noimage.png",
                    "evidencia_equipo_nuevo_en_transito": "images/noimage.png",
                    "evidencia_confirmacion_entrega": "images/noimage.png",
                    "evidencia_equipo_funcionando": "images/noimage.png",
                    "evidencia_embarque_equipo_malo": "https://sfo2.digitaloceanspaces.com/farmapronto-sucursales/incidencias-soporte/1465344/1704563490706.jpg",
                    "evidencia_en_transito_equipo_malo": "https://sfo2.digitaloceanspaces.com/farmapronto-sucursales/incidencias-soporte/1466368/1704641024252.jpg",
                    "evidencia_diagnostico": "images/noimage.png",
                    "evidencia_recepcion_equipo_malo": "https://sfo2.digitaloceanspaces.com/farmapronto-sucursales/incidencias-soporte/1468985/1704832030439.jpg",
                    "media": [
                        {
                            "id": 1456133,
                            "model_type": "App\\Entities\\IncidenciasSoporte\\IncidenciaSoporteEquipo",
                            "model_id": 6106,
                            "collection_name": "confirmada",
                            "name": "1703867495593",
                            "file_name": "1703867495593.jpg",
                            "mime_type": "image/jpeg",
                            "disk": "evidencias",
                            "size": 61758,
                            "manipulations": [],
                            "custom_properties": [],
                            "responsive_images": [],
                            "order_column": 1327672,
                            "created_at": "2023-12-29 10:31:47",
                            "updated_at": "2023-12-29 10:31:47"
                        },
                        {
                            "id": 1465344,
                            "model_type": "App\\Entities\\IncidenciasSoporte\\IncidenciaSoporteEquipo",
                            "model_id": 6106,
                            "collection_name": "embarque_equipo_malo",
                            "name": "1704563490706",
                            "file_name": "1704563490706.jpg",
                            "mime_type": "image/jpeg",
                            "disk": "evidencias",
                            "size": 150925,
                            "manipulations": [],
                            "custom_properties": [],
                            "responsive_images": [],
                            "order_column": 1335315,
                            "created_at": "2024-01-06 11:51:51",
                            "updated_at": "2024-01-06 11:51:51"
                        },
                        {
                            "id": 1466368,
                            "model_type": "App\\Entities\\IncidenciasSoporte\\IncidenciaSoporteEquipo",
                            "model_id": 6106,
                            "collection_name": "en_transito_equipo_malo",
                            "name": "1704641024252",
                            "file_name": "1704641024252.jpg",
                            "mime_type": "image/jpeg",
                            "disk": "evidencias",
                            "size": 86010,
                            "manipulations": [],
                            "custom_properties": [],
                            "responsive_images": [],
                            "order_column": 1336152,
                            "created_at": "2024-01-07 09:24:53",
                            "updated_at": "2024-01-07 09:24:53"
                        },
                        {
                            "id": 1468985,
                            "model_type": "App\\Entities\\IncidenciasSoporte\\IncidenciaSoporteEquipo",
                            "model_id": 6106,
                            "collection_name": "recepcion_equipo_malo",
                            "name": "1704832030439",
                            "file_name": "1704832030439.jpg",
                            "mime_type": "image/jpeg",
                            "disk": "evidencias",
                            "size": 122249,
                            "manipulations": [],
                            "custom_properties": [],
                            "responsive_images": [],
                            "order_column": 1338369,
                            "created_at": "2024-01-09 14:27:16",
                            "updated_at": "2024-01-09 14:27:16"
                        },
                        {
                            "id": 1469612,
                            "model_type": "App\\Entities\\IncidenciasSoporte\\IncidenciaSoporteEquipo",
                            "model_id": 6106,
                            "collection_name": "pendiente_destruccion",
                            "name": "1704860772573",
                            "file_name": "1704860772573.jpg",
                            "mime_type": "image/jpeg",
                            "disk": "evidencias",
                            "size": 115650,
                            "manipulations": [],
                            "custom_properties": [],
                            "responsive_images": [],
                            "order_column": 1338927,
                            "created_at": "2024-01-09 22:26:20",
                            "updated_at": "2024-01-09 22:26:20"
                        }
                    ]
                },
                {
                    "id": 6114,
                    "incidencia_id": 3356,
                    "tipo": "reemplazado",
                    "marca": "smartbitt",
                    "num_serie": "221711502792",
                    "num_inventario": "1",
                    "aprobado_por": null,
                    "comentarios": "NO CARGA ENERGIA",
                    "created_at": "2023-12-29 15:00:46",
                    "updated_at": "2024-01-09 20:52:42",
                    "deleted_at": null,
                    "catalogo_equipo_id": 20,
                    "pendiente_destruccion": true,
                    "confirmar_destruccion": null,
                    "equipo_malo": true,
                    "comentario_diagnostico": "equipo roto y sin retener carga, se probó otra pila y falla persiste",
                    "medio_envio": null,
                    "evidencia": "images/noimage.png",
                    "evidencia_equipo_asignado": "images/noimage.png",
                    "evidencia_confirmada": "https://sfo2.digitaloceanspaces.com/farmapronto-sucursales/incidencias-soporte/1456556/1703884252752.jpg",
                    "evidencia_equipo_nuevo_embarcado": "images/noimage.png",
                    "evidencia_equipo_nuevo_en_transito": "images/noimage.png",
                    "evidencia_confirmacion_entrega": "images/noimage.png",
                    "evidencia_equipo_funcionando": "images/noimage.png",
                    "evidencia_embarque_equipo_malo": "https://sfo2.digitaloceanspaces.com/farmapronto-sucursales/incidencias-soporte/1465261/1704552001781.jpg",
                    "evidencia_en_transito_equipo_malo": "https://sfo2.digitaloceanspaces.com/farmapronto-sucursales/incidencias-soporte/1466137/1704599851041.jpg",
                    "evidencia_diagnostico": "images/noimage.png",
                    "evidencia_recepcion_equipo_malo": "https://sfo2.digitaloceanspaces.com/farmapronto-sucursales/incidencias-soporte/1468898/1704825219874.jpg",
                    "media": [
                        {
                            "id": 1456556,
                            "model_type": "App\\Entities\\IncidenciasSoporte\\IncidenciaSoporteEquipo",
                            "model_id": 6114,
                            "collection_name": "confirmada",
                            "name": "1703884252752",
                            "file_name": "1703884252752.jpg",
                            "mime_type": "image/jpeg",
                            "disk": "evidencias",
                            "size": 55125,
                            "manipulations": [],
                            "custom_properties": [],
                            "responsive_images": [],
                            "order_column": 1328024,
                            "created_at": "2023-12-29 15:11:21",
                            "updated_at": "2023-12-29 15:11:21"
                        },
                        {
                            "id": 1466137,
                            "model_type": "App\\Entities\\IncidenciasSoporte\\IncidenciaSoporteEquipo",
                            "model_id": 6114,
                            "collection_name": "en_transito_equipo_malo",
                            "name": "1704599851041",
                            "file_name": "1704599851041.jpg",
                            "mime_type": "image/jpeg",
                            "disk": "evidencias",
                            "size": 332322,
                            "manipulations": [],
                            "custom_properties": [],
                            "responsive_images": [],
                            "order_column": 1335965,
                            "created_at": "2024-01-06 21:57:37",
                            "updated_at": "2024-01-06 21:57:37"
                        },
                        {
                            "id": 1468898,
                            "model_type": "App\\Entities\\IncidenciasSoporte\\IncidenciaSoporteEquipo",
                            "model_id": 6114,
                            "collection_name": "recepcion_equipo_malo",
                            "name": "1704825219874",
                            "file_name": "1704825219874.jpg",
                            "mime_type": "image/jpeg",
                            "disk": "evidencias",
                            "size": 93438,
                            "manipulations": [],
                            "custom_properties": [],
                            "responsive_images": [],
                            "order_column": 1338285,
                            "created_at": "2024-01-09 12:33:45",
                            "updated_at": "2024-01-09 12:33:45"
                        },
                        {
                            "id": 1465261,
                            "model_type": "App\\Entities\\IncidenciasSoporte\\IncidenciaSoporteEquipo",
                            "model_id": 6114,
                            "collection_name": "embarque_equipo_malo",
                            "name": "1704552001781",
                            "file_name": "1704552001781.jpg",
                            "mime_type": "image/jpeg",
                            "disk": "evidencias",
                            "size": 94407,
                            "manipulations": [],
                            "custom_properties": [],
                            "responsive_images": [],
                            "order_column": 1335234,
                            "created_at": "2024-01-06 08:40:17",
                            "updated_at": "2024-01-06 08:40:17"
                        },
                        {
                            "id": 1469501,
                            "model_type": "App\\Entities\\IncidenciasSoporte\\IncidenciaSoporteEquipo",
                            "model_id": 6114,
                            "collection_name": "pendiente_destruccion",
                            "name": "1704855155559",
                            "file_name": "1704855155559.jpg",
                            "mime_type": "image/jpeg",
                            "disk": "evidencias",
                            "size": 108886,
                            "manipulations": [],
                            "custom_properties": [],
                            "responsive_images": [],
                            "order_column": 1338822,
                            "created_at": "2024-01-09 20:52:42",
                            "updated_at": "2024-01-09 20:52:42"
                        }
                    ]
                },
                {
                    "id": 6121,
                    "incidencia_id": 3361,
                    "tipo": "reemplazado",
                    "marca": "subarashi",
                    "num_serie": "20160720082",
                    "num_inventario": "1",
                    "aprobado_por": null,
                    "comentarios": null,
                    "created_at": "2024-01-02 13:18:24",
                    "updated_at": "2024-01-10 16:30:32",
                    "deleted_at": null,
                    "catalogo_equipo_id": 32,
                    "pendiente_destruccion": true,
                    "confirmar_destruccion": null,
                    "equipo_malo": true,
                    "comentario_diagnostico": "láser roto no lee códigos",
                    "medio_envio": null,
                    "evidencia": "images/noimage.png",
                    "evidencia_equipo_asignado": "images/noimage.png",
                    "evidencia_confirmada": "https://sfo2.digitaloceanspaces.com/farmapronto-sucursales/incidencias-soporte/1460696/1704223167066.jpg",
                    "evidencia_equipo_nuevo_embarcado": "images/noimage.png",
                    "evidencia_equipo_nuevo_en_transito": "images/noimage.png",
                    "evidencia_confirmacion_entrega": "images/noimage.png",
                    "evidencia_equipo_funcionando": "images/noimage.png",
                    "evidencia_embarque_equipo_malo": "https://sfo2.digitaloceanspaces.com/farmapronto-sucursales/incidencias-soporte/1467695/1704738615458.jpg",
                    "evidencia_en_transito_equipo_malo": "https://sfo2.digitaloceanspaces.com/farmapronto-sucursales/incidencias-soporte/1470277/1704919774401.jpg",
                    "evidencia_diagnostico": "images/noimage.png",
                    "evidencia_recepcion_equipo_malo": "https://sfo2.digitaloceanspaces.com/farmapronto-sucursales/incidencias-soporte/1470281/1704919829353.jpg",
                    "media": [
                        {
                            "id": 1467695,
                            "model_type": "App\\Entities\\IncidenciasSoporte\\IncidenciaSoporteEquipo",
                            "model_id": 6121,
                            "collection_name": "embarque_equipo_malo",
                            "name": "1704738615458",
                            "file_name": "1704738615458.jpg",
                            "mime_type": "image/jpeg",
                            "disk": "evidencias",
                            "size": 99840,
                            "manipulations": [],
                            "custom_properties": [],
                            "responsive_images": [],
                            "order_column": 1337235,
                            "created_at": "2024-01-08 12:30:39",
                            "updated_at": "2024-01-08 12:30:39"
                        },
                        {
                            "id": 1470277,
                            "model_type": "App\\Entities\\IncidenciasSoporte\\IncidenciaSoporteEquipo",
                            "model_id": 6121,
                            "collection_name": "en_transito_equipo_malo",
                            "name": "1704919774401",
                            "file_name": "1704919774401.jpg",
                            "mime_type": "image/jpeg",
                            "disk": "evidencias",
                            "size": 78395,
                            "manipulations": [],
                            "custom_properties": [],
                            "responsive_images": [],
                            "order_column": 1339468,
                            "created_at": "2024-01-10 14:49:46",
                            "updated_at": "2024-01-10 14:49:46"
                        },
                        {
                            "id": 1470281,
                            "model_type": "App\\Entities\\IncidenciasSoporte\\IncidenciaSoporteEquipo",
                            "model_id": 6121,
                            "collection_name": "recepcion_equipo_malo",
                            "name": "1704919829353",
                            "file_name": "1704919829353.jpg",
                            "mime_type": "image/jpeg",
                            "disk": "evidencias",
                            "size": 55988,
                            "manipulations": [],
                            "custom_properties": [],
                            "responsive_images": [],
                            "order_column": 1339472,
                            "created_at": "2024-01-10 14:50:40",
                            "updated_at": "2024-01-10 14:50:40"
                        },
                        {
                            "id": 1460696,
                            "model_type": "App\\Entities\\IncidenciasSoporte\\IncidenciaSoporteEquipo",
                            "model_id": 6121,
                            "collection_name": "confirmada",
                            "name": "1704223167066",
                            "file_name": "1704223167066.jpg",
                            "mime_type": "image/jpeg",
                            "disk": "evidencias",
                            "size": 70925,
                            "manipulations": [],
                            "custom_properties": [],
                            "responsive_images": [],
                            "order_column": 1331447,
                            "created_at": "2024-01-02 13:19:38",
                            "updated_at": "2024-01-02 13:19:38"
                        },
                        {
                            "id": 1470534,
                            "model_type": "App\\Entities\\IncidenciasSoporte\\IncidenciaSoporteEquipo",
                            "model_id": 6121,
                            "collection_name": "pendiente_destruccion",
                            "name": "1704925825939",
                            "file_name": "1704925825939.jpg",
                            "mime_type": "image/jpeg",
                            "disk": "evidencias",
                            "size": 100757,
                            "manipulations": [],
                            "custom_properties": [],
                            "responsive_images": [],
                            "order_column": 1339683,
                            "created_at": "2024-01-10 16:30:32",
                            "updated_at": "2024-01-10 16:30:32"
                        }
                    ]
                },
                {
                    "id": 6147,
                    "incidencia_id": 3372,
                    "tipo": "reemplazado",
                    "marca": "genius",
                    "num_serie": "FPOPO002",
                    "num_inventario": "1",
                    "aprobado_por": null,
                    "comentarios": null,
                    "created_at": "2024-01-06 09:37:40",
                    "updated_at": "2024-01-08 16:45:06",
                    "deleted_at": null,
                    "catalogo_equipo_id": 4,
                    "pendiente_destruccion": true,
                    "confirmar_destruccion": null,
                    "equipo_malo": true,
                    "comentario_diagnostico": "sin reparación, equipo dañado por uso",
                    "medio_envio": null,
                    "evidencia": "images/noimage.png",
                    "evidencia_equipo_asignado": "images/noimage.png",
                    "evidencia_confirmada": "https://sfo2.digitaloceanspaces.com/farmapronto-sucursales/incidencias-soporte/1465307/1704555680323.jpg",
                    "evidencia_equipo_nuevo_embarcado": "images/noimage.png",
                    "evidencia_equipo_nuevo_en_transito": "images/noimage.png",
                    "evidencia_confirmacion_entrega": "images/noimage.png",
                    "evidencia_equipo_funcionando": "images/noimage.png",
                    "evidencia_embarque_equipo_malo": "https://sfo2.digitaloceanspaces.com/farmapronto-sucursales/incidencias-soporte/1465500/1704566327908.jpg",
                    "evidencia_en_transito_equipo_malo": "https://sfo2.digitaloceanspaces.com/farmapronto-sucursales/incidencias-soporte/1465505/1704566461972.jpg",
                    "evidencia_diagnostico": "images/noimage.png",
                    "evidencia_recepcion_equipo_malo": "https://sfo2.digitaloceanspaces.com/farmapronto-sucursales/incidencias-soporte/1465539/1704571210402.jpg",
                    "media": [
                        {
                            "id": 1465500,
                            "model_type": "App\\Entities\\IncidenciasSoporte\\IncidenciaSoporteEquipo",
                            "model_id": 6147,
                            "collection_name": "embarque_equipo_malo",
                            "name": "1704566327908",
                            "file_name": "1704566327908.jpg",
                            "mime_type": "image/jpeg",
                            "disk": "evidencias",
                            "size": 260499,
                            "manipulations": [],
                            "custom_properties": [],
                            "responsive_images": [],
                            "order_column": 1335432,
                            "created_at": "2024-01-06 12:38:56",
                            "updated_at": "2024-01-06 12:38:56"
                        },
                        {
                            "id": 1465505,
                            "model_type": "App\\Entities\\IncidenciasSoporte\\IncidenciaSoporteEquipo",
                            "model_id": 6147,
                            "collection_name": "en_transito_equipo_malo",
                            "name": "1704566461972",
                            "file_name": "1704566461972.jpg",
                            "mime_type": "image/jpeg",
                            "disk": "evidencias",
                            "size": 253086,
                            "manipulations": [],
                            "custom_properties": [],
                            "responsive_images": [],
                            "order_column": 1335437,
                            "created_at": "2024-01-06 12:41:07",
                            "updated_at": "2024-01-06 12:41:07"
                        },
                        {
                            "id": 1465307,
                            "model_type": "App\\Entities\\IncidenciasSoporte\\IncidenciaSoporteEquipo",
                            "model_id": 6147,
                            "collection_name": "confirmada",
                            "name": "1704555680323",
                            "file_name": "1704555680323.jpg",
                            "mime_type": "image/jpeg",
                            "disk": "evidencias",
                            "size": 246695,
                            "manipulations": [],
                            "custom_properties": [],
                            "responsive_images": [],
                            "order_column": 1335279,
                            "created_at": "2024-01-06 09:41:29",
                            "updated_at": "2024-01-06 09:41:29"
                        },
                        {
                            "id": 1465539,
                            "model_type": "App\\Entities\\IncidenciasSoporte\\IncidenciaSoporteEquipo",
                            "model_id": 6147,
                            "collection_name": "recepcion_equipo_malo",
                            "name": "1704571210402",
                            "file_name": "1704571210402.jpg",
                            "mime_type": "image/jpeg",
                            "disk": "evidencias",
                            "size": 77597,
                            "manipulations": [],
                            "custom_properties": [],
                            "responsive_images": [],
                            "order_column": 1335471,
                            "created_at": "2024-01-06 14:00:18",
                            "updated_at": "2024-01-06 14:00:18"
                        },
                        {
                            "id": 1468070,
                            "model_type": "App\\Entities\\IncidenciasSoporte\\IncidenciaSoporteEquipo",
                            "model_id": 6147,
                            "collection_name": "pendiente_destruccion",
                            "name": "1704753898957",
                            "file_name": "1704753898957.jpg",
                            "mime_type": "image/jpeg",
                            "disk": "evidencias",
                            "size": 83193,
                            "manipulations": [],
                            "custom_properties": [],
                            "responsive_images": [],
                            "order_column": 1337571,
                            "created_at": "2024-01-08 16:45:06",
                            "updated_at": "2024-01-08 16:45:06"
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
