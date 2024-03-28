## Registro de arqueos de cajas

Recuperar arqueo incompleto.

**URL**

    /api/arqueos/arqueo-pendiente

**Method:**

`GET`

**Headers**

      Authorization: Bearer access_token
      Accept: application/json

**Data Params**

      N/A

**URL Params**

      N/A     

**Success Response:**

* **Code:** 200 <br />
  **Content:**

        {
          "lastArqueo": {
            "id": 15,
            "user_id": 676,
            "sucursal_id": 91,
            "encargada": "test",
            "turno": "vespertino",
            "fondo_total": "2000",
            "efectivo_caja_fuerte": "3000",
            "fondo_sucursal": "300",
            "fondo_cajas_abiertas": "300",
            "gastos_a_pagar": "300",
            "concepto_gastos_a_pagar": "test",
            "concepto_diferencia": "test",
            "remesas": "200",
            "recolecciones": "200",
            "comentario": null,
            "created_at": "2023-05-24 17:06:09",
            "updated_at": "2023-05-24 17:06:09",
            "faltante_fondo_sucursal": 200,
            "venta_matutina": {
              "id": 7,
              "arqueo_general_id": 15,
              "efectivo": "500",
              "fichas_deposito": "200",
              "venta_mtc": "200",
              "created_at": "2023-05-24 17:06:24",
              "updated_at": "2023-05-24 17:06:24"
            },
            "arqueos_cajas": []
          }
        }

**Error Response:**

* **Code:** 401 Unauthorized <br />
  **Content:**

        {
          "error": "Unauthenticated."
        }
