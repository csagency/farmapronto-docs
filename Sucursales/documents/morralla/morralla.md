## Listado que solicitudes de morralla
Regresa un listado de solicitudes de morra que no tengan el estatus recibido.

**URL**

    /api/sucursales/morralla/getListSolicitudMorrallaBySucursal/{sucursal_id}

**Method:**

`GET`

**Headers**

      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data


**Data Params**

     N/A

**URL Params**

      N/A

**Success Response:**

* **Code:** 200 <br />
  **Content:**

      {
        "list_solicitudes_morralla": []
      }

**Error Response:**

* **Code:** 401 Unauthorized <br />
  **Content:**

        {
          "error": "Unauthenticated."
        }
