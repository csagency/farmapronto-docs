## Registro de ventas matutinas

Registro una venta matutina nueva.

**URL**

    /api/arqueos/ventas-matutinas

**Method:**

`POST`

**Headers**

      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data

**Data Params**

    'arqueoGeneralId' => 'required|numeric|exists:arqueos_generales,id',
    'efectivo' => 'required|numeric',
    'fichasDeposito' => 'required|numeric',
    'ventaMtc' => 'required|numeric',

**URL Params**

      N/A     

**Success Response:**

* **Code:** 200 <br />
  **Content:**

        {
            "ventaMatutina": {
                "arqueo_general_id": "1",
                "efectivo": "250.89",
                "fichas_deposito": "345.08",
                "venta_mtc": "367.00",
                "updated_at": "2023-05-11 11:38:11",
                "created_at": "2023-05-11 11:38:11",
                "id": 2
            }
        }

**Error Response:**

* **Code:** 401 Unauthorized <br />
  **Content:**

        {
          "error": "Unauthenticated."
        }
