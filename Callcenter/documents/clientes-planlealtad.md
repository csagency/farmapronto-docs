## Beneficios
Obtener el listados de beneficios de un cliente.

Los beneficios se procesaran de manera automática en la siguiente compra del cliente.

 **URL**

  /api/clientes/me?includes[]=beneficios.promocion.producto_beneficio

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
        "cliente": {
          "id": 14846,
          "name": "Erick",
          "last_name": "Brito",
          "second_last_name": null,
          "telephone": "527773274199",
          "clave": "ERBRLQUQ",
          "email": "erick.dbrito@gmail.com",
          "player_id": null,
          "activo": 1,
          "baja": 0,
          "fb_id": null,
          "webhook_url": null,
          "created_at": "2019-07-11 11:44:35",
          "updated_at": "2019-07-11 11:44:35",
          "deleted_at": null,
          "last_login": null,
          "beneficios": [
            {
              "id": 11,
              "user_id": 14846,
              "producto_id": 32217,
              "clientes_beneficios_producto_id": 14,
              "pedido_id": 52359,
              "cotizacion_id": "60186",
              "compras": 2,
              "beneficios": 1,
              "sugeridos": 0,
              "precio_beneficio": 0,
              "precio_fijo": 0,
              "tipo_precio_descuento": "0",
              "canjeado": 0,
              "cancelado": 0,
              "cerrado": "15523340",
              "descripcion": "Transacción aprobada",
              "codigo_error": 0,
              "referencia": "MTCL_BAY",
              "created_at": "2019-07-19 18:18:52",
              "updated_at": "2019-07-19 18:19:38",
              "deleted_at": null,
              "promocion": {
                "id": 14,
                "sku_compra": "7501303442601",
                "referencia": "MTCL_BAY",
                "producto_compra_nombre": "QLAIRA TAB C\/28",
                "cantidad_compra": 3,
                "sku_beneficio": "7501303442601",
                "producto_beneficio_nombre": "QLAIRA TAB C\/28",
                "cantidad_beneficio": 1,
                "vigencia_inicio": "2018-09-01",
                "vigencia_fin": "2019-08-31",
                "porcentaje_descuento": 0,
                "tipo_porcentaje_descuento": 0,
                "activo": 0,
                "created_at": null,
                "updated_at": null,
                "producto_beneficio": {
                  "id": 32217,
                  "farmapronto_id": "034769",
                  "sku": "7501303442601",
                  "nombre": "QLAIRA TAB C\/28",
                  "descripcion": "",
                  "categoria": "APARATO GENITOURINARIO Y H SEXUALES",
                  "categoria_id": 0,
                  "laboratorio": "BAYER",
                  "receta": 0,
                  "clave": "SUJETO A DISPONIBILIDAD",
                  "tipo": 75,
                  "activos": "VALERATO DE ESTRADIOL",
                  "keywords": "Anticoncepcion, pastillas anticonceptivas, anticonceptivo, sintomas mestruacion, mestruacion, eficacia anticonceptiva, irregularidad menstrual,¶ÿ retencion liquidos, dolor ovario, sandgrado, sangrado abundante,¶ÿ menstruaciones largas, dolor menstrual, estradiol, dienogest, comprimido anticonceptivo, embarazo, anticonceptivo oral combinado, anticonceptivo oral, anticonceptivo natural, cefalea, dolor pelvico, estrogeno natural.",
                  "destacado": 0,
                  "archivo": "uploads\/images\/productos\/7501303442601.png",
                  "created_at": "2017-03-16 17:49:48",
                  "updated_at": "2019-07-04 17:51:00",
                  "activo": 1,
                  "despliega": 1
                }
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

## Beneficios Pendientes
Obtiene los beneficios pendientes  del cliente por tarjeta


 **URL**

  /ws/plan-lealtad/beneficios-pendientes


 **Method:**

  `GET`

 **Headers**

      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data
          


        
        [
          {
            "id": 802,
            "user_id": 20162,
            "folio": null,
            "descripcion": null,
            "numero_tarjeta": "7773274199",
            "vigente": 1,
            "expiracion": null,
            "created_at": "2019-11-13 11:44:43",
            "updated_at": "2019-11-13 11:44:43",
            "deleted_at": null,
            "tipo_tarjeta_id": null,
            "nip": null,
            "codigo_error": 0,
            "beneficios": {
              "id": 34978,
              "farmapronto_id": "037995",
              "sku": "7501300407122",
              "nombre": "LERK 100 MG C\/1 COMPRIMIDOS",
              "descripcion": "",
              "categoria": "APARATO GENITOURINARIO Y H SEXUALES",
              "categoria_id": 0,
              "laboratorio": "WESER PHARMA",
              "receta": 0,
              "clave": "SUJETO A DISPONIBILIDAD",
              "tipo": 119,
              "activos": "SILDENAFIL",
              "keywords": "Lerc, lerq, lark, lirk, sildenafilo, urologico, disfuncion erectil, hormonas sexuales, hipertension arterial pulmonar",
              "destacado": 0,
              "archivo": "uploads\/images\/productos\/7501300407122.png",
              "created_at": "2017-03-16 17:49:50",
              "updated_at": "2019-11-07 06:01:50",
              "activo": 0,
              "despliega": 0,
              "precio": {
                "id": 17733,
                "zona_id": 22,
                "producto_id": 34978,
                "precio": 55.5,
                "created_at": "2017-06-22 19:53:15",
                "updated_at": "2019-10-10 06:02:04"
              },
              "historial_compras": {
                "mtcid": "5000",
                "idsucursal": "11678",
                "sucursal": "CYBER MI PC",
                "cajero": "Usuario WS Test",
                "idterminal": "32424",
                "fecha_hora": "2019-07-19T18:31:40",
                "sku": "7501300407122",
                "cantidad": "3",
                "tipo_movimiento": "VT:Compra",
                "numero_sesion": "60187",
                "numero_confirmacion": "",
                "referencia": "MTCL_SIG",
                "tarjetaafiliacion": "5043000010"
              },
              "beneficios_pendientes": {
                "compras_mecanica": "3",
                "beneficios_mecanica": "1",
                "compras_realizadas": "3",
                "compras_pendientes": "0",
                "sku": "7501300407122",
                "referencia": "MTCL_SIG",
                "vigencia": "2019-12-31"
              }
            },
            "tipo_tarjeta": null
          },
          {
            "id": 803,
            "user_id": 20162,
            "folio": null,
            "descripcion": null,
            "numero_tarjeta": "7041040842",
            "vigente": 1,
            "expiracion": null,
            "created_at": "2019-11-13 11:44:43",
            "updated_at": "2019-11-13 11:44:43",
            "deleted_at": null,
            "tipo_tarjeta_id": 54,
            "nip": null,
            "codigo_error": -1,
            "beneficios": null,
            "tipo_tarjeta": {
              "id": 54,
              "nombre": "PFIZER",
              "descripcion": "TARJETA PFIZER CONMIGO ",
              "created_at": "2019-11-11 17:20:37",
              "updated_at": "2019-11-11 17:20:37"
            }
          }
        ]
