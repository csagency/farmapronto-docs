## Registrar nuevo balance
Registra un nuevo balance y lo retorna<br>

 **URL**

    /api/balances

 **Method:**

  `POST`
  
 **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data
     
     
 **Params**
    
    sucursal_id: 'required|exists:sucursales,id'
    grupo: 'required|string'
         
         

**Success Response:**

**Code:** 200 <br />
  **Content:** 

    {
        "balance": {
            "sucursal_id": "91",
            "user_id": 707,
            "grupo": "CONTROLADOS FRACCION 2",
            "diferencia": false,
            "comentario": null,
            "updated_at": "2022-05-26 11:02:45",
            "created_at": "2022-05-26 11:02:45",
            "id": 2,
            "folio": "BC000002"
        }
    }

**Error Response:**

  * **Code:** 401 Unauthorized <br />
    **Content:** 
  
          {
            "error": "Unauthenticated."
          }

  * **Code:** 500 Internal Server Error <br />
    **Content:**

        {
          "message": "Error al registrar balance"
        }

## Listado de balances por sucursales, fecha inicio y fecha fin
Retorna un listado de balances filtrados por sucursales, fecha inicio y fecha fin<br>

**URL**

    /api/balances/getBalancesByRequest

**Method:**

`GET`

**Headers**

      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data


**Params**

    'sucursales_ids' => 'required|array',
    'fecha_inicio' => 'required|string',
    'fecha_fin' => 'required|string',

    Ejemplo URL con los params: /api/balances/getBalancesByRequest?sucursales_ids[0]=91&fecha_inicio=2022-05-26&fecha_fin=2022-05-26



**Success Response:**

**Code:** 200 <br />
**Content:**

        {
            "balances": [
                {
                    "id": 4,
                    "sucursal_id": 91,
                    "user_id": 707,
                    "folio": "BC000004",
                    "grupo": "CONTROLADOS FRACCION 2",
                    "diferencia": false,
                    "created_at": "2022-05-26 11:44:01",
                    "updated_at": "2022-05-26 11:44:01",
                    "deleted_at": null,
                    "comentario": null,
                    "balance_status": [
                        {
                            "id": 7,
                            "key": "registrado",
                            "created_at": "2022-05-24 15:44:14",
                            "updated_at": "2022-05-24 15:44:14",
                            "name": "Registrado",
                            "pivot": {
                                "balance_id": 4,
                                "balance_status_id": 7,
                                "user_id": 707,
                                "created_at": "2022-05-26 11:44:01",
                                "updated_at": "2022-05-26 11:44:01"
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

* **Code:** 500 Internal Server Error <br />
  **Content:**

      {
        "message": "Error al consultar balances"
      }

## Listado de productos por grupo
Retorna un listado de productos filtrados por grupo<br>

**URL**

    /api/balances/getProductosByGrupo/{grupo}

**Method:**

`GET`

**Headers**

      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data


**Params**

    'grupo'

    Ejemplo URL con el param: /api/balances/getProductosByGrupo/CONTROLADOS FRACCION 2



**Success Response:**

**Code:** 200 <br />
**Content:**

        {
           "productos":[
              {
                 "id":34,
                 "farmapronto_id":"005557",
                 "nombre":"DORMICUM 15 MG/3 ML C/5 SOLUCION INYECTABLE",
                 "grupo":"CONTROLADOS FRACCION 2",
                 "created_at":"2022-05-20 12:45:00",
                 "updated_at":"2022-05-20 12:45:00",
                 "deleted_at":null
              }
           ]
        }

**Error Response:**

* **Code:** 401 Unauthorized <br />
  **Content:**

        {
          "error": "Unauthenticated."
        }

* **Code:** 500 Internal Server Error <br />
  **Content:**

      {
        "message": "Error al consultar productos"
      }

## Registro del detalle de balance y producto
Retorna el balance con el detalle del producto y los estatus del balance<br>

**URL**

    /api/balances/storeBalanceProducto/{balance_id}

**Method:**

`POST`

**Headers**

      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data


**Params**

    'balance_id'

    Ejemplo URL con el param: /api/balances/storeBalanceProducto/1

**Request**

    'producto_id' => 'required|exists:productos,id',
    'ext_ant' => 'required|integer',
    'cant_adq' => 'required|integer',
    'total' => 'required|integer',
    'diferencia' => 'required|integer',
    'salidas' => 'required|integer',
    'saldo' => 'required|integer',
    'existencias' => 'required|integer',
    'folio_receta' => 'required|integer',
    'folio_libro_de' => 'required|integer',
    'folio_libro_a' => 'required|integer',
    'evidencia' => 'required|image',

**Success Response:**

**Code:** 200 <br />
**Content:**

        {
            "balance": {
                "id": 6,
                "sucursal_id": 91,
                "user_id": 707,
                "folio": "BC000006",
                "grupo": "CONTROLADOS FRACCION 3",
                "diferencia": true,
                "comentario": null,
                "created_at": "2022-06-09 11:06:09",
                "updated_at": "2022-06-09 11:10:40",
                "deleted_at": null,
                "balance_productos": [
                    {
                        "id": 15,
                        "balance_id": 6,
                        "producto_id": 241,
                        "ext_ant": 1,
                        "cant_adq": 1,
                        "total": 1,
                        "diferencia": 1,
                        "salidas": 1,
                        "saldo": 1,
                        "existencias": 1,
                        "folio_receta": 1,
                        "folio_libro_de": 1,
                        "folio_libro_a": 1,
                        "created_at": "2022-06-09 11:10:40",
                        "updated_at": "2022-06-09 11:10:40",
                        "deleted_at": null,
                        "evidencia": "/storage/balances/balanceProducto/evidencias/786361/Balance_icon.png",
                        "producto": {
                            "id": 241,
                            "farmapronto_id": "001015",
                            "nombre": "ANAPSIQUE 25 MG TABLETAS C/50",
                            "grupo": "CONTROLADOS FRACCION 3",
                            "created_at": "2022-05-20 12:45:01",
                            "updated_at": "2022-05-20 12:45:01",
                            "deleted_at": null
                        },
                        "media": [
                            {
                                "id": 786361,
                                "model_type": "App\\Entities\\Balances\\BalanceProducto",
                                "model_id": 15,
                                "collection_name": "evidencia",
                                "name": "Balance_icon",
                                "file_name": "Balance_icon.png",
                                "mime_type": "image/png",
                                "disk": "evidencias_balance_producto",
                                "size": 304174,
                                "manipulations": [],
                                "custom_properties": [],
                                "responsive_images": [],
                                "order_column": 760021,
                                "created_at": "2022-06-09 11:10:40",
                                "updated_at": "2022-06-09 11:10:40"
                            }
                        ]
                    }
                ],
                "balance_status": [
                    {
                        "id": 2,
                        "name": "En proceso",
                        "key": "en_proceso",
                        "created_at": "2022-05-26 16:01:34",
                        "updated_at": "2022-05-26 16:01:34",
                        "pivot": {
                            "balance_id": 6,
                            "balance_status_id": 2,
                            "user_id": 707,
                            "created_at": "2022-06-09 11:10:41",
                            "updated_at": "2022-06-09 11:10:41"
                        }
                    },
                    {
                        "id": 1,
                        "name": "Registrado",
                        "key": "registrado",
                        "created_at": "2022-05-26 16:01:34",
                        "updated_at": "2022-05-26 16:01:34",
                        "pivot": {
                            "balance_id": 6,
                            "balance_status_id": 1,
                            "user_id": 707,
                            "created_at": "2022-06-09 11:06:09",
                            "updated_at": "2022-06-09 11:06:09"
                        }
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

* **Code:** 500 Internal Server Error <br />
  **Content:**

      {
        "message": "Error al registrar el detalle del balance del producto"
      }
* 
## Actualizar registro de producto registrado 
Permite la actualización de la información de un producto registrado en un balance. 

**URL**

    /api/balances/updateBalanceProducto/{$balanceProductoId}

**Method:**

`POST`

**Headers**

      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data


**Params**

    'balance_producto_id'

    Ejemplo URL con el param: /api/balances/updateBalanceProducto/1

**Request**

    'ext_ant' => 'required|integer',
    'cant_adq' => 'required|integer',
    'total' => 'required|integer',
    'diferencia' => 'required|integer',
    'salidas' => 'required|integer',
    'saldo' => 'required|integer',
    'existencias' => 'required|integer',
    'folio_receta' => 'required|integer',
    'folio_libro_de' => 'required|integer',
    'folio_libro_a' => 'required|integer',
    'evidencia' => 'required|image',

**Success Response:**

**Code:** 200 <br />
**Content:**

        {
            "producto": {
                "id": 10,
                "balance_id": 2,
                "producto_id": 239,
                "ext_ant": "100",
                "cant_adq": "200",
                "total": "100",
                "diferencia": "100",
                "salidas": "1000",
                "saldo": "100",
                "existencias": "100",
                "folio_receta": "100",
                "folio_libro_de": "100",
                "folio_libro_a": "100",
                "created_at": "2022-07-06 17:25:25",
                "updated_at": "2022-07-06 17:26:13",
                "deleted_at": null,
                "evidencia": "\/\/storage\/balances\/balanceProducto\/evidencias\/13\/img_capture.png",
                "media": [
                    {
                        "id": 13,
                        "model_type": "App\\Entities\\Balances\\BalanceProducto",
                        "model_id": 10,
                        "collection_name": "evidencia",
                        "name": "img_capture",
                        "file_name": "img_capture.png",
                        "mime_type": "image\/png",
                        "disk": "evidencias_balance_producto",
                        "size": 12405,
                        "manipulations": [],
                        "custom_properties": [],
                        "responsive_images": [],
                        "order_column": 435817,
                        "created_at": "2022-07-06 17:26:13",
                        "updated_at": "2022-07-06 17:26:13"
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

* **Code:** 500 Internal Server Error <br />
  **Content:**

      {
        "message": "Error al registrar el detalle del balance del producto"
      }

## Listado de productos por balance
Retorna Los productos registrados en un balance<br>

**URL**

    /api/balances/getProductosBalances/{balance_id}

**Method:**

`GET`

**Headers**

      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data


**Params**

    'balance_id'

    Ejemplo URL con el param: /api/balances/storeBalanceProducto/1

**Request**

    N/A

**Success Response:**

**Code:** 200 <br />
**Content:**

        {
           "productos":[
              {
                 "id":34,
                 "farmapronto_id":"005557",
                 "nombre":"DORMICUM 15 MG/3 ML C/5 SOLUCION INYECTABLE",
                 "grupo":"CONTROLADOS FRACCION 2",
                 "created_at":"2022-05-20 12:45:00",
                 "updated_at":"2022-05-20 12:45:00",
                 "deleted_at":null,
                 "balance_producto_id":4,
                 "balance_id":1,
                 "ext_ant":1,
                 "cant_adq":1,
                 "total":1,
                 "diferencia":1,
                 "salidas":1,
                 "saldo":1,
                 "existencias":1,
                 "folio_receta":1,
                 "folio_libro_de":1,
                 "folio_libro_a":1
              },
              {
                 "id":2,
                 "farmapronto_id":"000360",
                 "nombre":"ADEPSIQUE 10MG/3MG/2MG TABLETAS C/90",
                 "grupo":"CONTROLADOS FRACCION 2",
                 "created_at":"2022-05-20 12:45:00",
                 "updated_at":"2022-05-20 12:45:00",
                 "deleted_at":null,
                 "balance_producto_id":null,
                 "balance_id":null,
                 "ext_ant":null,
                 "cant_adq":null,
                 "total":null,
                 "diferencia":null,
                 "salidas":null,
                 "saldo":null,
                 "existencias":null,
                 "folio_receta":null,
                 "folio_libro_de":null,
                 "folio_libro_a":null
              }
           ]
        }

**Error Response:**

* **Code:** 401 Unauthorized <br />
  **Content:**

        {
          "error": "Unauthenticated."
        }

* **Code:** 500 Internal Server Error <br />
  **Content:**

      {
        "message": "Error al consultar productos con balance"
      }

## Completar registro de balance
Retorna el balance con el detalle del producto y los estatus del balance<br>

**URL**

    /api/balances/completarBalance

**Method:**

`POST`

**Headers**

      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data


**Params**

    N/A

**Request**

    'balance_id' => 'required|exists:balances,id',
    'comentario' => 'required|string',

**Success Response:**

**Code:** 200 <br />
**Content:**

        {
            "balance": {
                "id": 6,
                "sucursal_id": 91,
                "user_id": 707,
                "folio": "BC000006",
                "grupo": "CONTROLADOS FRACCION 3",
                "diferencia": true,
                "comentario": "balance completado",
                "created_at": "2022-06-09 11:06:09",
                "updated_at": "2022-06-09 11:14:55",
                "deleted_at": null,
                "balance_productos": [
                    {
                        "id": 15,
                        "balance_id": 6,
                        "producto_id": 241,
                        "ext_ant": 1,
                        "cant_adq": 1,
                        "total": 1,
                        "diferencia": 1,
                        "salidas": 1,
                        "saldo": 1,
                        "existencias": 1,
                        "folio_receta": 1,
                        "folio_libro_de": 1,
                        "folio_libro_a": 1,
                        "created_at": "2022-06-09 11:10:40",
                        "updated_at": "2022-06-09 11:10:40",
                        "deleted_at": null,
                        "evidencia": "/storage/balances/balanceProducto/evidencias/786361/Balance_icon.png",
                        "media": [
                            {
                                "id": 786361,
                                "model_type": "App\\Entities\\Balances\\BalanceProducto",
                                "model_id": 15,
                                "collection_name": "evidencia",
                                "name": "Balance_icon",
                                "file_name": "Balance_icon.png",
                                "mime_type": "image/png",
                                "disk": "evidencias_balance_producto",
                                "size": 304174,
                                "manipulations": [],
                                "custom_properties": [],
                                "responsive_images": [],
                                "order_column": 760021,
                                "created_at": "2022-06-09 11:10:40",
                                "updated_at": "2022-06-09 11:10:40"
                            }
                        ]
                    }
                ],
                "balance_status": [
                    {
                        "id": 3,
                        "name": "Completado",
                        "key": "completado",
                        "created_at": "2022-05-26 16:01:34",
                        "updated_at": "2022-05-26 16:01:34",
                        "pivot": {
                            "balance_id": 6,
                            "balance_status_id": 3,
                            "user_id": 707,
                            "created_at": "2022-06-09 11:14:55",
                            "updated_at": "2022-06-09 11:14:55"
                        }
                    },
                    {
                        "id": 2,
                        "name": "En proceso",
                        "key": "en_proceso",
                        "created_at": "2022-05-26 16:01:34",
                        "updated_at": "2022-05-26 16:01:34",
                        "pivot": {
                            "balance_id": 6,
                            "balance_status_id": 2,
                            "user_id": 707,
                            "created_at": "2022-06-09 11:10:41",
                            "updated_at": "2022-06-09 11:10:41"
                        }
                    },
                    {
                        "id": 1,
                        "name": "Registrado",
                        "key": "registrado",
                        "created_at": "2022-05-26 16:01:34",
                        "updated_at": "2022-05-26 16:01:34",
                        "pivot": {
                            "balance_id": 6,
                            "balance_status_id": 1,
                            "user_id": 707,
                            "created_at": "2022-06-09 11:06:09",
                            "updated_at": "2022-06-09 11:06:09"
                        }
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

* **Code:** 500 Internal Server Error <br />
  **Content:**

      {
        "message": "Error al completar el balance"
      }

## Último balance por sucursal
Retorna el último balance con el detalle del balance, la sucursal y los datos del usuario que registro el balance<br>

**URL**

    /api/balances/getLastBalanceBySucursal/{sucursal_id}

**Method:**

`GET`

**Headers**

      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data


**Params**

    N/A

**Request**

    N/A

**Success Response:**

**Code:** 200 <br />
**Content:**

        {
            "balance": {
                "id": 6,
                "sucursal_id": 91,
                "user_id": 707,
                "folio": "BC000006",
                "grupo": "CONTROLADOS FRACCION 3",
                "diferencia": true,
                "comentario": "balance completado",
                "created_at": "2022-06-09 11:06:09",
                "updated_at": "2022-06-09 11:14:55",
                "deleted_at": null,
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
                "user": {
                    "id": 707,
                    "nombre": "Tester",
                    "apellido_paterno": "Normatividad",
                    "telefono": "77712345678",
                    "player_id": null,
                    "email": "normatividadcs@farmapronto.com",
                    "email_verified_at": null,
                    "created_at": "2022-05-26 16:03:13",
                    "updated_at": "2022-05-26 16:03:13",
                    "deleted_at": null,
                    "apellido_materno": "CS",
                    "old_email": null,
                    "cant_errores_actuales": 0
                },
                "balance_productos": [
                    {
                        "id": 15,
                        "balance_id": 6,
                        "producto_id": 241,
                        "ext_ant": 1,
                        "cant_adq": 1,
                        "total": 1,
                        "diferencia": 1,
                        "salidas": 1,
                        "saldo": 1,
                        "existencias": 1,
                        "folio_receta": 1,
                        "folio_libro_de": 1,
                        "folio_libro_a": 1,
                        "created_at": "2022-06-09 11:10:40",
                        "updated_at": "2022-06-09 11:10:40",
                        "deleted_at": null,
                        "evidencia": "/storage/balances/balanceProducto/evidencias/786361/Balance_icon.png",
                        "producto": {
                            "id": 241,
                            "farmapronto_id": "001015",
                            "nombre": "ANAPSIQUE 25 MG TABLETAS C/50",
                            "grupo": "CONTROLADOS FRACCION 3",
                            "created_at": "2022-05-20 12:45:01",
                            "updated_at": "2022-05-20 12:45:01",
                            "deleted_at": null
                        },
                        "media": [
                            {
                                "id": 786361,
                                "model_type": "App\\Entities\\Balances\\BalanceProducto",
                                "model_id": 15,
                                "collection_name": "evidencia",
                                "name": "Balance_icon",
                                "file_name": "Balance_icon.png",
                                "mime_type": "image/png",
                                "disk": "evidencias_balance_producto",
                                "size": 304174,
                                "manipulations": [],
                                "custom_properties": [],
                                "responsive_images": [],
                                "order_column": 760021,
                                "created_at": "2022-06-09 11:10:40",
                                "updated_at": "2022-06-09 11:10:40"
                            }
                        ]
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

* **Code:** 500 Internal Server Error <br />
  **Content:**

      {
        "message": "Error al obtener el último balance de la sucursal"
      }

## Enviar Balances controlados
Envia un reporte con balances controlados<br>

**URL**

    /api/balances/sendBalancesControlados

**Method:**

`POST`

**Headers**

      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data


**Params**

    N/A

**Request**

    'balances_ids' => 'required|array',
    'fecha_inicio' => 'required|string',
    'fecha_fin' => 'required|string',

**Success Response:**

**Code:** 200 <br />
**Content:**

        {
            "message": "Reporte balances controlados enviado con éxito"
        }

**Error Response:**

* **Code:** 401 Unauthorized <br />
  **Content:**

        {
          "error": "Unauthenticated."
        }

* **Code:** 500 Internal Server Error <br />
  **Content:**

      {
        "message": "Error al enviar Reporte balances controlados"
      }
