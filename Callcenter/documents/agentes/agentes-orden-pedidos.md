## Orden de los pedidos de un agente
Guarda el orden de los pedidos de una ruta de un agente.

**URL**

 /api/agentes/pedidos/orden-pedidos

**Method:**

 `POST`

**Headers**

    Authorization: Bearer access_token
    Accept: application/json
    Content-Type: multipart/form-data

**URL Params**

 N/A

 **Data Params**

  ***Required:***

     `peididos=[required|array]`
     `agente_id=[required|exists:agentes,id]`

**Success Response:**

 * **Code:** 200 <br />
   **Content:**

   {
       "ruta": {
          "id": 62092,
          "created_at": "2022-10-04 10:25:24",
          "updated_at": "2022-10-04 10:25:24"
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
          "pedidos": [
              "El campo pedidos es obligatorio."
          ],
          "agente_id": [
              "El campo agente id es obligatorio."
          ]
      }

      {
          "agente_id": [
              "El campo agente id es inválido."
          ]
      }

* **Code:** 404 Not Found <br />
  **Content:**

      {
        "message": "Error, algunos pedidos no existen, favor de validarlos"
      }


## Muestra los pedidos pendientes a entregar.
Muestra los pedidos pendientes a entregar de una ruta.

**URL**

/api/agentes/getPedidosByRuta/{rutaId}

**Method:**

`GET`

**Headers**

    Authorization: Bearer access_token
    Accept: application/json
    Content-Type: multipart/form-data

**URL Params**

{rutaId}

**Data Params**

***Required:***

N/A

**Success Response:**

* **Code:** 200 <br />
  **Content:**


      {
          "ordenPedidos": [
              {
                  "id": 101476,
                  "ruta_id": 63059,
                  "agente_id": 458,
                  "pedido_id": 329353,
                  "created_at": "2022-09-13 16:25:18",
                  "updated_at": "2022-09-13 16:25:18",
                  "pedido": {
                      "id": 329353,
                      "user_id": 73480,
                      "cliente_direccion_id": 208705,
                      "ciudad_cobertura_id": null,
                      "asistencia": 0,
                      "alerta_cliente": 0,
                      "folio": "ERP0329353",
                      "erp": 1,
                      "traspaso": 0,
                      "usuario_erp": "XMENDEZ",
                      "codigo_confirmacion": null,
                      "visto_callcenter": 1,
                      "programado_at": null,
                      "taxi": 0,
                      "clon": 0,
                      "pedidos_juntos": "329353",
                      "cancelado_motivo": null,
                      "cancelado_user_id": null,
                      "cancelado_observaciones": null,
                      "observaciones": null,
                      "liberado": null,
                      "created_at": "2022-09-13 15:53:24",
                      "updated_at": "2022-09-13 16:20:14",
                      "deleted_at": null,
                      "origen": null,
                      "is_urgente": null,
                      "estado_entregado": {
                          "id": 3443619,
                          "pedido_id": 329353,
                          "paso": "entregado",
                          "nomicash": null,
                          "created_at": "2022-09-29 17:20:24",
                          "updated_at": "2022-09-29 17:20:24"
                      }
                  }
              },
              {
                  "id": 101477,
                  "ruta_id": 63059,
                  "agente_id": 458,
                  "pedido_id": 329365,
                  "created_at": "2022-09-13 16:25:18",
                  "updated_at": "2022-09-13 16:25:18",
                  "pedido": {
                      "id": 329365,
                      "user_id": 15009,
                      "cliente_direccion_id": 138470,
                      "ciudad_cobertura_id": null,
                      "asistencia": 0,
                      "alerta_cliente": 0,
                      "folio": "APP0329365",
                      "erp": 0,
                      "traspaso": 1,
                      "usuario_erp": "APP",
                      "codigo_confirmacion": null,
                      "visto_callcenter": 1,
                      "programado_at": "2022-09-13 18:00:29",
                      "taxi": 0,
                      "clon": 0,
                      "pedidos_juntos": "329353,329365",
                      "cancelado_motivo": null,
                      "cancelado_user_id": null,
                      "cancelado_observaciones": null,
                      "observaciones": "servicio de traspaso de sucursal MD para sucursal MF 4 piezas de depend toallas con 8 piezas ",
                      "liberado": null,
                      "created_at": "2022-09-13 16:16:07",
                      "updated_at": "2022-09-13 16:22:39",
                      "deleted_at": null,
                      "origen": "android",
                      "is_urgente": null,
                      "estado_entregado": null
                  }
              }
          ]
      }


## Si no hay pedidos pendientes de entrega.
  * **Code:** 200 <br />
    **Content:**
  

    {
        "ordenPedidos": []
    }


**Error Response:**

* **Code:** 401 Unauthorized <br />
  **Content:**

      {
        "error": "Unauthenticated."
      }

