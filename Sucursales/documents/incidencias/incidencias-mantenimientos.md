## Listado de incidencias mantenimientos

Regresa el listado de las incidencias de mantenimientos

**URL**

    /api/incidencia-mantenimiento

**Method:**

`GET`

**Headers**

      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data

**Data Params**

    show_history=1 'Para mostrar incidencias pagadas'

**URL Params**

      - fecha_inicio = 2023-01-20
      - fecha_fin = 2023-01-31
      Ejemplo URI: `api/incidencias-mantenimiento?fecha_inicio=2022-11-01&fecha_fin=2022-11-30`     

**Success Response:**

* **Code:** 200 <br />
  **Content:**

      {
            "listIncidenciasMantenimientos": []
      }

**Error Response:**

* **Code:** 401 Unauthorized <br />
  **Content:**

        {
          "error": "Unauthenticated."
        }

## Listado de incidencias mantenimientos por sucursal

Regresa el listado de las incidencias de mantenimientos por el id de una sucursal

**URL**

    /api/incidencia-mantenimiento/getListIncidenciasMantenimientosBySucursalId/{sucursal_id}

**Method:**

`GET`

**Headers**

      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data

**Data Params**

     - fecha_inicio = 2023-01-20
      - fecha_fin = 2023-01-31
      Ejemplo URI: `api/incidencia-mantenimiento/getListIncidenciasMantenimientosBySucursalId/91?fecha_inicio=2022-11-01&fecha_fin=2022-11-30` 

**URL Params**

    sucursal_id

**Success Response:**

* **Code:** 200 <br />
  **Content:**

      {
            "listIncidenciasMantenimientos": []
      }

**Error Response:**

* **Code:** 401 Unauthorized <br />
  **Content:**

        {
          "error": "Unauthenticated."
        }

## Detalle de incidencia de mantenimiento

Regresa el registro de un incidencia de mantenimiento

**URL**

    /api/incidencia-mantenimiento/{id}

**Method:**

`GET`

**Headers**

      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data

**URL Params**

      N/A

**Success Response:**

* **Code:** 200 <br />
  **Content:**

      {
        "incidenciaMantenimiento": {
            "id": 2,
            "concepto_mantenimiento_id": 1,
            "sucursal_id": 91,
            "folio": "MTO000002",
            "created_at": "2021-10-29 16:41:07",
            "updated_at": "2021-10-29 16:41:07",
            "evidencia_entrega": "/storage/incidencias-mantenimientos/entrega/evidencias/588231/monedas.jpeg",
            "evidencia_cotizacion": "/storage/incidencias-mantenimientos/cotizacion/evidencias/588233/monedas.jpeg",
            "evidencia_reparacion": "/storage/incidencias-mantenimientos/reparacion/evidencias/588236/monedas.jpeg",
            "evidencia_pago": "/storage/incidencias-mantenimientos/pago/evidencias/588237/monedas.jpeg",
            "concepto_mantenimiento": {
                "id": 1,
                "concepto": "Pintura",
                "precio_material": "250.5",
                "unidad_medida": "MT2",
                "costo_mano_obra": "1500",
                "created_at": "2021-10-29 16:12:27",
                "updated_at": "2021-10-29 16:12:27"
            },
            "sucursal": {
                "id": 91,
                "nombre": "CS",
                "codigo": "CS",
                "direccion": "Ahuatepec 307 A, Lomas de la Selva",
                "lat": "18.892008",
                "lon": "-99.231818",
                "meta_encargadas": 1,
                "meta_auxiliares": 1,
                "meta_cajeras": 0,
                "fondo_venta_mensual": "0",
                "matutino": true,
                "vespertino": true,
                "intermedio": false,
                "created_at": "2020-11-25 15:53:49",
                "updated_at": "2021-05-06 12:52:15",
                "deleted_at": null,
                "fondo_asignado": "0",
                "fondo_callcenter": "1000",
                "tipo_sucursal": "CS",
                "fecha_calibracion": null,
                "correo_enviado_calibracion": false
            },
            "incidencia_mantenimiento_status": [
                {
                    "id": 1,
                    "nombre": "Registrada",
                    "key": "registrada",
                    "created_at": "2021-10-29 16:32:48",
                    "updated_at": "2021-10-29 16:32:48",
                    "pivot": {
                        "incidencia_mantenimiento_id": 2,
                        "status_id": 1,
                        "user_id": 159,
                        "comentario": "testing",
                        "created_at": "2021-10-29 16:41:07",
                        "updated_at": "2021-10-29 16:41:07"
                    }
                },
                {
                    "id": 2,
                    "nombre": "Cotizada",
                    "key": "cotizada",
                    "created_at": "2021-10-29 16:32:48",
                    "updated_at": "2021-10-29 16:32:48",
                    "pivot": {
                        "incidencia_mantenimiento_id": 2,
                        "status_id": 2,
                        "user_id": 159,
                        "comentario": "testing cotización",
                        "created_at": "2021-10-29 16:47:08",
                        "updated_at": "2021-10-29 16:47:08"
                    }
                },
                {
                    "id": 3,
                    "nombre": "Aprobada",
                    "key": "cotizacion_aprobada",
                    "created_at": "2021-10-29 16:32:48",
                    "updated_at": "2021-10-29 16:32:48",
                    "pivot": {
                        "incidencia_mantenimiento_id": 2,
                        "status_id": 3,
                        "user_id": 159,
                        "comentario": "testing aprobada",
                        "created_at": "2021-10-29 16:49:19",
                        "updated_at": "2021-10-29 16:49:19"
                    }
                },
                {
                    "id": 5,
                    "nombre": "Reparada",
                    "key": "reparada",
                    "created_at": "2021-10-29 16:32:48",
                    "updated_at": "2021-10-29 16:32:48",
                    "pivot": {
                        "incidencia_mantenimiento_id": 2,
                        "status_id": 5,
                        "user_id": 159,
                        "comentario": "testing reparación",
                        "created_at": "2021-10-29 16:57:21",
                        "updated_at": "2021-10-29 16:57:21"
                    }
                },
                {
                    "id": 6,
                    "nombre": "Pago aprobado",
                    "key": "pago_aprobado",
                    "created_at": "2021-10-29 16:32:48",
                    "updated_at": "2021-10-29 16:32:48",
                    "pivot": {
                        "incidencia_mantenimiento_id": 2,
                        "status_id": 6,
                        "user_id": 159,
                        "comentario": "testing pago aprobado",
                        "created_at": "2021-10-29 17:02:21",
                        "updated_at": "2021-10-29 17:02:21"
                    }
                },
                {
                    "id": 8,
                    "nombre": "Pagada",
                    "key": "pagada",
                    "created_at": "2021-10-29 16:32:48",
                    "updated_at": "2021-10-29 16:32:48",
                    "pivot": {
                        "incidencia_mantenimiento_id": 2,
                        "status_id": 8,
                        "user_id": 159,
                        "comentario": "testing pagado",
                        "created_at": "2021-10-29 17:04:33",
                        "updated_at": "2021-10-29 17:04:33"
                    }
                }
            ],
            "cotizacion_incidencia_mantenimiento": {
                "id": 2,
                "incidencia_mantenimiento_id": 2,
                "metodo_pago": "efectivo",
                "cantidad": "2MT",
                "precio_total": "3500.5",
                "requiere_factura": false,
                "created_at": "2021-10-29 16:47:08",
                "updated_at": "2021-10-29 16:47:08"
            },
            "media": [
                {
                    "id": 588237,
                    "model_type": "App\\Entities\\IncidenciasMantenimientos\\IncidenciaMantenimiento",
                    "model_id": 2,
                    "collection_name": "evidencia_pago",
                    "name": "monedas",
                    "file_name": "monedas.jpeg",
                    "mime_type": "image/jpeg",
                    "disk": "evidencias_incidencias_mantenimientos_pago",
                    "size": 122361,
                    "manipulations": [],
                    "custom_properties": [],
                    "responsive_images": [],
                    "order_column": 575019,
                    "created_at": "2021-10-29 17:04:33",
                    "updated_at": "2021-10-29 17:04:33"
                },
                {
                    "id": 588236,
                    "model_type": "App\\Entities\\IncidenciasMantenimientos\\IncidenciaMantenimiento",
                    "model_id": 2,
                    "collection_name": "evidencia_reparacion",
                    "name": "monedas",
                    "file_name": "monedas.jpeg",
                    "mime_type": "image/jpeg",
                    "disk": "evidencias_incidencias_mantenimientos_reparacion",
                    "size": 122361,
                    "manipulations": [],
                    "custom_properties": [],
                    "responsive_images": [],
                    "order_column": 575018,
                    "created_at": "2021-10-29 16:57:21",
                    "updated_at": "2021-10-29 16:57:21"
                },
                {
                    "id": 588233,
                    "model_type": "App\\Entities\\IncidenciasMantenimientos\\IncidenciaMantenimiento",
                    "model_id": 2,
                    "collection_name": "evidencia_cotizacion",
                    "name": "monedas",
                    "file_name": "monedas.jpeg",
                    "mime_type": "image/jpeg",
                    "disk": "evidencias_incidencias_mantenimientos_cotizacion",
                    "size": 122361,
                    "manipulations": [],
                    "custom_properties": [],
                    "responsive_images": [],
                    "order_column": 575017,
                    "created_at": "2021-10-29 16:47:08",
                    "updated_at": "2021-10-29 16:47:08"
                },
                {
                    "id": 588231,
                    "model_type": "App\\Entities\\IncidenciasMantenimientos\\IncidenciaMantenimiento",
                    "model_id": 2,
                    "collection_name": "evidencia_entrega",
                    "name": "monedas",
                    "file_name": "monedas.jpeg",
                    "mime_type": "image/jpeg",
                    "disk": "evidencias_incidencias_mantenimientos_entrega",
                    "size": 122361,
                    "manipulations": [],
                    "custom_properties": [],
                    "responsive_images": [],
                    "order_column": 575016,
                    "created_at": "2021-10-29 16:41:07",
                    "updated_at": "2021-10-29 16:41:07"
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

**Registro de incidencia de mantenimiento**

**URL**

    /api/incidencia-mantenimiento

**Method:**

`POST`

**Headers**

      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data

**Data Params**

    'concepto_mantenimiento_id' => 'required|exists:conceptos_mantenimientos,id',
    'sucursal_id' => 'required|exists:sucursales,id',
    'comentario' => 'nullable|max:255',
    'evidencia_imagen' => 'required|image',

**Success Response:**

* **Code:** 200 <br />
  **Content:**

  Igual que en el detalle de incidencia de mantenimiento

**Error Response:**

* **Code:** 401 Unauthorized <br />
  **Content:**

        {
          "error": "Unauthenticated."
        }

    * **Code:** 408 Error <br />
      **Content:**

          {
            "message": "Error al registrar incidencia de mantenimiento"
          }

## Registrar cotización de incidencia de mantenimiento

**URL**

    /api/incidencia-mantenimiento/storeCotizacion

**Method:**

`POST`

**Headers**

      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data

**Data Params**

    'incidencia_mantenimiento_id' => 'required|exists:incidencias_mantenimientos,id',
    'cantidad' => 'required',
    'precio_total' => 'required',
    'requiere_factura' => 'required',
    'evidencia_imagen_cotizacion' => 'required|image',
    'comentario' => 'nullable|max:255',
    'require_mano_obra' => 'required|boolean',
    'require_anticipo' => 'required|boolean',
    'mano_obra_precio' => 'numeric',
    'mano_obra_comentario' => 'max:255',
    'mano_obra_requiere_factura' => 'required|boolean',
    'mano_obra_evidencia' => 'image',
    'anticipo_precio' => 'numeric',
    'anticipo_comentario' => 'max:255',
    'anticipo_requiere_factura' => 'required|boolean',
    'anticipo_evidencia' => 'image',
    
**Success Response:**

* **Code:** 200 <br />
  **Content:**
  Igual que en el detalle de incidencia de mantenimiento

**Error Response:**

* **Code:** 401 Unauthorized <br />
  **Content:**

      {
          "error": "Unauthenticated."
      }        


* **Code:** 408 Error <br />
  **Content:**

          {
            "message": "Error al registrar la cotizacion de la incidencia de mantenimiento"
          }

## Aprobar o rechazar la cotización

**URL**

    /api/incidencia-mantenimiento/approveOrRejectCotizacion

**Method:**

`POST`

**Headers**

      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data

**Data Params**

    'cotizacion_aprobada' => 'required|exists:catalogo_status_incidencias_mantenimientos,key',
    'incidencia_mantenimiento_id' => 'required|exists:incidencias_mantenimientos,id',
    'comentario' => 'nullable|max:255',
    'metodo_pago' => 'string' [opciones: efectivo, cheque, tarjeta],

**Success Response:**

* **Code:** 200 <br />
  **Content:**
  Igual que en el detalle de incidencia de mantenimiento

**Error Response:**

* **Code:** 401 Unauthorized <br />
  **Content:**

      {
          "error": "Unauthenticated."
      }        


* **Code:** 408 Error <br />
  **Content:**

          {
            "message": "Error al aprobar o rechazar la cotizacion de la incidencia de mantenimiento"
          }

## Actualizar la cotización

**URL**

    /api/incidencia-mantenimiento/updateCotizacion/{cotizacionIncidencia_id}

**Method:**

`POST`

**Headers**

      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data

**Data Params**

    'incidencia_mantenimiento_id' => 'required|exists:incidencias_mantenimientos,id',
    'cantidad' => 'required',
    'precio_total' => 'required',
    'requiere_factura' => 'required',
    'evidencia_imagen_cotizacion' => 'required|image',
    'comentario' => 'nullable|max:255',
    'require_mano_obra' => 'required|boolean',
    'require_anticipo' => 'required|boolean',
    'mano_obra_precio' => 'numeric',
    'mano_obra_comentario' => 'max:255',
    'mano_obra_requiere_factura' => 'required|boolean',
    'mano_obra_evidencia' => 'image',
    'anticipo_precio' => 'numeric',
    'anticipo_comentario' => 'max:255',
    'anticipo_requiere_factura' => 'required|boolean',
    'anticipo_evidencia' => 'image',

**URL Params**

    cotizacionIncidencia_id

**Success Response:**

* **Code:** 200 <br />
  **Content:**
  Igual que en el detalle de incidencia de mantenimiento

**Error Response:**

* **Code:** 401 Unauthorized <br />
  **Content:**

      {
          "error": "Unauthenticated."
      }        


* **Code:** 408 Error <br />
  **Content:**

          {
            "message": "Error al registrar la cotizacion de la incidencia de mantenimiento"
          }

## Registrar la reparación de la incidencia de mantenimiento

También sirve para actualizarla.

**URL**

    /api/incidencia-mantenimiento/storeReparacion

**Method:**

`POST`

**Headers**

      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data

**Data Params**

    'incidencia_mantenimiento_id' => 'required|exists:incidencias_mantenimientos,id',
    'evidencia_imagen_reparacion' => 'required|image',
    'comentario' => 'nullable|max:255',

**URL Params**

    N/A

**Success Response:**

* **Code:** 200 <br />
  **Content:**
  Igual que en el detalle de incidencia de mantenimiento

**Error Response:**

* **Code:** 401 Unauthorized <br />
  **Content:**

      {
          "error": "Unauthenticated."
      }        


* **Code:** 408 Error <br />
  **Content:**

          {
            "message": "Error al registrar la reparación de la incidencia de mantenimiento"
          }

## Autorizar el pago

**URL**

    /api/incidencia-mantenimiento/autorizarPago

**Method:**

`POST`

**Headers**

      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data

**Data Params**

    'pago_aprobado' => 'required|boolean',
    'incidencia_mantenimiento_id' => 'required|exists:incidencias_mantenimientos,id',
    'comentario' => 'nullable|max:255',

**URL Params**

    N/A

**Success Response:**

* **Code:** 200 <br />
  **Content:**
  Igual que en el detalle de incidencia de mantenimiento

**Error Response:**

* **Code:** 401 Unauthorized <br />
  **Content:**

      {
          "error": "Unauthenticated."
      }        


* **Code:** 408 Error <br />
  **Content:**

          {
            "message": "Error al autorizar pago de la incidencia de mantenimiento"
          }

## Registrar pago

**URL**

    /api/incidencia-mantenimiento/storePago

**Method:**

`POST`

**Headers**

      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data

**Data Params**

    'incidencia_mantenimiento_id' => 'required|exists:incidencias_mantenimientos,id',
    'evidencia_imagen_pago' => 'required|image',
    'comentario' => 'nullable|max:255',

**URL Params**

    N/A

**Success Response:**

* **Code:** 200 <br />
  **Content:**
  Igual que en el detalle de incidencia de mantenimiento

**Error Response:**

* **Code:** 401 Unauthorized <br />
  **Content:**

      {
          "error": "Unauthenticated."
      }        


* **Code:** 408 Error <br />
  **Content:**

          {
            "message": "Error al registrar el pago de la incidencia de mantenimiento"
          }

## Registrar status no cotización.

**URL**

    /api/incidencia-mantenimiento/setNoCotizacionStatus/{incidenciaMantenimientoId}

**Method:**

`POST`

**Headers**

      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data

**Data Params**

    N/A

**URL Params**

    {incidenciaMantenimientoId}

**Success Response:**

* **Code:** 200 <br />
  **Content:**
  Igual que en el detalle de incidencia de mantenimiento

**Error Response:**

* **Code:** 401 Unauthorized <br />
  **Content:**

      {
          "error": "Unauthenticated."
      }        


## Obtener incidencia anterior

**URL**

    /api/incidencia-mantenimiento/getLastIncidenciaMantenimiento/{incidenciaMantenimientoId}

**Method:**

`POST`

**Headers**

      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data

**Data Params**

    N/A

**URL Params**

    {incidenciaMantenimientoId}

**Success Response:**

* **Code:** 200 <br />
  **Content:**

        {
            "respuesta": {
                "fecha_creacion": "2023-08-01 17:03:33",
                "fecha_finalizacion": "Sin información",
                "sucursal": "CS"
            }
        }

**Error Response:**

* **Code:** 401 Unauthorized <br />
  **Content:**

      {
          "error": "Unauthenticated."
      }
