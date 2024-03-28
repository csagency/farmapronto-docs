## Registro de arqueos generales

Registro un arqueo general nuevo.

**URL**

    /api/arqueos

**Method:**

`POST`

**Headers**

      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data

**Data Params**

    'sucursalId' => 'required|exists:sucursales,id',
    'encargada' => 'required|string|max:255',
    'turno' => 'required|string|max:255',
    'fondoTotal' => 'required|numeric',
    'efectivoCajaFuerte' => 'required|numeric',
    'fondoSucursal' => 'required|numeric',
    'fondoCajasAbiertas' => 'required|numeric',
    'gastosAPagar' => 'required|numeric',
    'conceptoGastosAPagar' => 'required|string',
    'faltante_fondo_sucursal' => 'required|numeric',
    'conceptoDiferencia' => 'required|string',
    'remesas' => 'required|numeric',
    'recolecciones' => 'required|numeric',
    'hasVentasMatutinas' => 'required|boolean',

**URL Params**

      N/A     

**Success Response:**

* **Code:** 200 <br />
  **Content:**

        {
            "arqueoGeneral": {
                "user_id": 1,
                "sucursal_id": "91",
                "encargada": "Encargada test",
                "turno": "matutino",
                "fondo_total": "1000.95",
                "efectivo_caja_fuerte": "955.00",
                "fondo_sucursal": "895",
                "fondo_cajas_abiertas": "845.65",
                "gastos_a_pagar": "435.02",
                "concepto_gastos_a_pagar": "Concepto test",
                "faltante_fondo_sucursal": "100.99",
                "concepto_diferencia": "Concepto diferencia test",
                "remesas": "100.80",
                "recolecciones": "99.99",
                "comentario": null,
                "updated_at": "2023-05-11 11:28:39",
                "created_at": "2023-05-11 11:28:39",
                "id": 4
            }
        }

**Error Response:**

* **Code:** 401 Unauthorized <br />
  **Content:**

        {
          "error": "Unauthenticated."
        }

## Registrar comentario de arqueo general

Registrar el comentario del arqueo general.

**URL**

    /api/arqueos/agregar-comentario/{arqueoGeneralId}

**Method:**

`POST`

**Headers**

      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data

**Data Params**

    'comentario' => 'required|string',

**URL Params**

      {arqueoGeneralId}     

**Success Response:**

* **Code:** 200 <br />
  **Content:**

        {
            "arqueoGeneral": {
                "id": 2,
                "user_id": 1,
                "sucursal_id": 91,
                "encargada": "Encargada test",
                "turno": "matutino",
                "fondo_total": "1000.95",
                "efectivo_caja_fuerte": "955",
                "fondo_sucursal": "895",
                "fondo_cajas_abiertas": "845.65",
                "gastos_a_pagar": "435.02",
                "concepto_gastos_a_pagar": "Concepto test",
                "faltante_fondo_sucursal": "99.10"
                "concepto_diferencia": "Concepto diferencia test",
                "remesas": "100.8",
                "recolecciones": "99.99",
                "comentario": "testing",
                "created_at": "2023-05-11 10:45:47",
                "updated_at": "2023-05-11 11:26:52"
            }
        }

**Error Response:**

* **Code:** 401 Unauthorized <br />
  **Content:**

        {
          "error": "Unauthenticated."
        }
