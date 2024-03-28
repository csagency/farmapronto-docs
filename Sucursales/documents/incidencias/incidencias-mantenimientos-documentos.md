## Listado de documentos de una incidencia mantenimiento

Regresa el listado de los documentos que tiene una incidencia de mantenimiento

**URL**

    /api/incidencia-mantenimiento/documentos/{incidenciaMantimientoId}

**Method:**

`GET`

**Headers**

      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data

**URL Params**

      - {incidenciaMantimientoId} id de la incidencias de mantenimiento   

**Success Response:**

* **Code:** 200 <br />
  **Content:**

        {
            "incidenciaMantenimientoDocumentos": [
                {
                    "id": 2,
                    "fileName": "dummyxml.xml",
                    "url": "http://localhost:50132/storage/incidencias-mantenimientos/documentos/2/dummyxml.xml"
                }
            ]
        }

**Error Response:**

* **Code:** 401 Unauthorized <br />
  **Content:**

        {
          "error": "Unauthenticated."
        }

## Inserta un documento a una incidencia mantenimiento

Registra un documento nuevo en una incidencia de mantenimiento

**URL**

    /api/incidencia-mantenimiento/store-documentos/{incidenciaMantimientoId}

**Method:**

`POST`

**Headers**

      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data

**URL Params**

      - {incidenciaMantimientoId} id de la incidencias de mantenimiento

**BODY Params**

      - 'documento' => 'required|file'

**Success Response:**

* **Code:** 200 <br />
  **Content:**

            {
                "incidenciaMantenimiento": {
                    "id": 142,
                    "sucursal_id": 85,
                    "folio": "MTO000142",
                    "created_at": "2023-08-22 13:20:01",
                    "updated_at": "2023-08-22 13:20:01",
                    "concepto_mantenimiento_id": 86,
                    "comentario": "pruebas de telefono oppo a17",
                    "evidencia_entrega": "https://sfo2.digitaloceanspaces.com/farmapronto-sucursales/incidencias-mantenimientos/entrega/evidencias/1303112/1692731996698.jpg",
                    "evidencia_cotizacion": "https://sfo2.digitaloceanspaces.com/farmapronto-sucursales/incidencias-mantenimientos/cotizacion/evidencias/1303121/1692732042954.jpg",
                    "evidencia_reparacion": "https://sfo2.digitaloceanspaces.com/farmapronto-sucursales/incidencias-mantenimientos/reparacion/evidencias/1303129/1692732321903.jpg",
                    "evidencia_pago": "https://sfo2.digitaloceanspaces.com/farmapronto-sucursales/incidencias-mantenimientos/pago/evidencias/1303131/1692732404472.jpg",
                    "media": [
                        {
                            "id": 1303112,
                            "model_type": "App\\Entities\\IncidenciasMantenimientos\\IncidenciaMantenimiento",
                            "model_id": 142,
                            "collection_name": "evidencia_entrega",
                            "name": "1692731996698",
                            "file_name": "1692731996698.jpg",
                            "mime_type": "image/jpeg",
                            "disk": "evidencias_incidencias_mantenimientos_entrega",
                            "size": 119943,
                            "manipulations": [],
                            "custom_properties": [],
                            "responsive_images": [],
                            "order_column": 1199982,
                            "created_at": "2023-08-22 13:20:06",
                            "updated_at": "2023-08-22 13:20:06"
                        },
                        {
                            "id": 1303121,
                            "model_type": "App\\Entities\\IncidenciasMantenimientos\\IncidenciaMantenimiento",
                            "model_id": 142,
                            "collection_name": "evidencia_cotizacion",
                            "name": "1692732042954",
                            "file_name": "1692732042954.jpg",
                            "mime_type": "image/jpeg",
                            "disk": "evidencias_incidencias_mantenimientos_cotizacion",
                            "size": 173506,
                            "manipulations": [],
                            "custom_properties": [],
                            "responsive_images": [],
                            "order_column": 1199988,
                            "created_at": "2023-08-22 13:21:51",
                            "updated_at": "2023-08-22 13:21:51"
                        },
                        {
                            "id": 1303129,
                            "model_type": "App\\Entities\\IncidenciasMantenimientos\\IncidenciaMantenimiento",
                            "model_id": 142,
                            "collection_name": "evidencia_reparacion",
                            "name": "1692732321903",
                            "file_name": "1692732321903.jpg",
                            "mime_type": "image/jpeg",
                            "disk": "evidencias_incidencias_mantenimientos_reparacion",
                            "size": 170602,
                            "manipulations": [],
                            "custom_properties": [],
                            "responsive_images": [],
                            "order_column": 1199994,
                            "created_at": "2023-08-22 13:25:28",
                            "updated_at": "2023-08-22 13:25:28"
                        },
                        {
                            "id": 1303131,
                            "model_type": "App\\Entities\\IncidenciasMantenimientos\\IncidenciaMantenimiento",
                            "model_id": 142,
                            "collection_name": "evidencia_pago",
                            "name": "1692732404472",
                            "file_name": "1692732404472.jpg",
                            "mime_type": "image/jpeg",
                            "disk": "evidencias_incidencias_mantenimientos_pago",
                            "size": 127664,
                            "manipulations": [],
                            "custom_properties": [],
                            "responsive_images": [],
                            "order_column": 1199996,
                            "created_at": "2023-08-22 13:26:55",
                            "updated_at": "2023-08-22 13:26:55"
                        },
                        {
                            "id": 2,
                            "model_type": "App\\Entities\\IncidenciasMantenimientos\\IncidenciaMantenimiento",
                            "model_id": 142,
                            "collection_name": "docuemtentos",
                            "name": "dummyxml",
                            "file_name": "dummyxml.xml",
                            "mime_type": "text/xml",
                            "disk": "incidencias_mantenimientos_documentos",
                            "size": 164,
                            "manipulations": [],
                            "custom_properties": [],
                            "responsive_images": [],
                            "order_column": 1200861,
                            "created_at": "2023-09-13 12:07:32",
                            "updated_at": "2023-09-13 12:07:32"
                        },
                        {
                            "id": 3,
                            "model_type": "App\\Entities\\IncidenciasMantenimientos\\IncidenciaMantenimiento",
                            "model_id": 142,
                            "collection_name": "docuemtentos",
                            "name": "dummy",
                            "file_name": "dummy.pdf",
                            "mime_type": "application/pdf",
                            "disk": "incidencias_mantenimientos_documentos",
                            "size": 13264,
                            "manipulations": [],
                            "custom_properties": [],
                            "responsive_images": [],
                            "order_column": 1200862,
                            "created_at": "2023-09-14 12:45:42",
                            "updated_at": "2023-09-14 12:45:42"
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

## Eliminar documento de una incidencia mantenimiento

Eliminar el regsitro de un documento que tiene una incidencia de mantenimiento

**URL**

    /api/incidencia-mantenimiento/delete-documentos/{documentoId}

**Method:**

`DELETE`

**Headers**

      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data

**URL Params**

      - {documentoId} id del documento, se encunetra en la respuesta del primer endpoint documentado aquí.

**Success Response:**

* **Code:** 200 <br />
  **Content:**

            {
                "Message": "Documento eliminado correctamente"
            }

**Error Response:**

* **Code:** 401 Unauthorized <br />
  **Content:**

        {
          "error": "Unauthenticated."
        }
