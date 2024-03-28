## Registro de arqueos de cajas

Registro un arqueo de caja nuevo.

**URL**

    /api/arqueos/arqueos-cajas

**Method:**

`POST`

**Headers**

      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data

**Data Params**

    'arqueoGeneralId' => 'required|numeric|exists:arqueos_generales,id',
    'numeroCaja' => 'required|string|max:255',
    'nombreCajero' => 'required|string|max:255',
    'fondoCaja' => 'required|numeric',
    'ventaMtc' => 'required|numeric',
    'remesas' => 'required|numeric',
    'recolecciones' => 'required|numeric',
    'corteCaja' => 'required|numeric',
    'tipoDiferencia' => 'required|string|max:255',
    'cantidadDiferencia' => 'required|numeric',
    'evidencia' => 'required|image',

**URL Params**

      N/A     

**Success Response:**

* **Code:** 200 <br />
  **Content:**

        {
            "arqueoCaja": {
                "arqueo_general_id": "1",
                "numero_caja": "1",
                "nombre_cajero": "Tester Cajero",
                "fondo_caja": "100",
                "venta_mtc": "1200",
                "remesas": "200",
                "recolecciones": "500",
                "corte_caja": "200",
                "tipo_diferencia": "test",
                "cantidad_diferencia": "1300.25",
                "updated_at": "2023-05-11 11:34:40",
                "created_at": "2023-05-11 11:34:40",
                "id": 2
            }
        }

**Error Response:**

* **Code:** 401 Unauthorized <br />
  **Content:**

        {
          "error": "Unauthenticated."
        }
