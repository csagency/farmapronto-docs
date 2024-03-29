## Consulta de pedidos ERP

Consulta un pedido ERP

**URL**

    /api/pedidos/{folio}

**Method:**

`GET`

**Headers**

      Accept: application/json
      Content-Type: multipart/form-data

**Data Params**

**URL Params**

      folio     
      codigoSucursal

**Success Response:**

* **Code:** 200 <br />
  **Content:**

        {
            "id": 295718,
            "cliente_direccion_id": 179729,
            "user_id": 1188,
            "folio": "ERP0295718",
            "codigo_confirmacion": null,
            "created_at": "2022-04-22 20:10:20",
            "usuario_erp": "COCAMPO",
            "cliente": {
                "id": 1188,
                "nombre": "GABRIELA",
                "apellido_paterno": "PERALTA",
                "apellido_materno": ".",
                "email": "comer_p1@grupofarmapronto.com",
                "telefono": "7351138173",
                "nombre_completo": " "
            },
            "direccion": {
                "estado": "MORELOS",
                "municipio": "ATLATLAHUCAN",
                "colonia": "lomas de cocoyoc",
                "colonia_str": "lomas de cocoyoc",
                "calle": "la tranca",
                "numero_interior": "",
                "numero_exterior": "1",
                "codigo_postal": "62840",
                "referencia": "casa con tres palmeras en la mera esquina tel 7353511152 preventa p",
                "lat": "18.9118941",
                "lon": "-98.9507071",
                "tipo": "CASA"
            },
            "estado": {
                "paso": "liberado"
            },
            "repartidor": {
                "id": 430,
                "numero_control": "6225",
                "nombre": "RODOLFO ROSENDO ",
                "apellido_paterno": "SALINAS ",
                "apellido_materno": "ZAVALA",
                "email": "repartidor6225@grupofarmapronto.com",
                "telefono": "5531482540",
                "pivot": {
                    "pedido_id": 295718,
                    "agente_id": 430,
                    "nip": "WGQW",
                    "created_at": null,
                    "updated_at": "2022-04-22 21:30:33"
                }
            },
            "pago": {
                "id": 295706,
                "estado": "pendiente",
                "metodo_pago": "tarjeta",
                "monto": "1561.15",
                "monto_efectivo": null,
                "total": "1561.15",
                "tarjeta": null,
                "tarjeta_last4": null,
                "tarjeta_tipo": "Tarjeta Credito",
                "facturacion_id": null,
                "factura_rfc": null,
                "factura_alias": null,
                "factura_calle": null,
                "factura_numero": null,
                "factura_colonia": null,
                "factura_cp": null,
                "factura_estado": null,
                "factura_municipio": null
            },
            "envio": {
                "tipo_envio": "domicilio_propios",
                "costo_envio": null,
                "codigo_verificacion": "7287",
                "placas_com": null,
                "placas_app": "81MRX7"
            },
            "sucursal": {
                "id": 13,
                "nombre": "P",
                "codigo": "13",
                "codigo_postal": "62738",
                "pivot": {
                    "pedido_id": 295718,
                    "sucursal_id": 13,
                    "created_at": "2022-04-22 20:10:20",
                    "updated_at": "2022-04-22 20:29:52",
                    "aceptado": 1,
                    "rechazado": 0,
                    "activo": 0,
                    "orden": 1
                }
            },
            "pedidos_relacionados": null,
            "productos": [
                {
                    "sku": "7501098605915",
                    "nombre": "CRESTOR 20MG TABLETAS C/30",
                    "imagen": "http://farmapronto.lndo.siteuploads/images/productos/7501098605915.png",
                    "receta": 0,
                    "receta_imagen": null,
                    "pedido_producto_id": 526231,
                    "cantidad_productos": 1,
                    "precio_suma_total": "1,006.65",
                    "pecio_unitario": "1,006.65",
                    "pecio_unitario_lista": 1006.65,
                    "farmapronto_id": "004230",
                    "sucursal_lista_precio_id": "P",
                    "sucursal_lista_precio_nombre": "P",
                    "traspaso_id": null,
                    "sucursal_traspaso_nombre": null,
                    "sucursal_traspaso_codigo": null,
                    "traspaso_entregado": null,
                    "cotizacion": null,
                    "folio_llave": null,
                    "resultado_descripcion": null,
                    "compras": null,
                    "beneficios": null,
                    "sugeridos": null,
                    "referencia": null,
                    "beneficio_descripcion": null,
                    "beneficio_sustituto": null,
                    "beneficio_porcentaje_descuento": null,
                    "beneficio_tipo_porcentaje_descuento": null,
                    "promocion_descripcion": null,
                    "promocion_modo": null,
                    "promocion_tipo": null,
                    "promocion_monto": null
                },
                {
                    "sku": "7501324403124",
                    "nombre": "ZESTRIL 10 MG C/28 TABLETAS",
                    "imagen": "http://farmapronto.lndo.siteuploads/images/productos/7501324403124.png",
                    "receta": 0,
                    "receta_imagen": null,
                    "pedido_producto_id": 526232,
                    "cantidad_productos": 1,
                    "precio_suma_total": "554.50",
                    "pecio_unitario": "554.50",
                    "pecio_unitario_lista": 554.5,
                    "farmapronto_id": "015202",
                    "sucursal_lista_precio_id": "P",
                    "sucursal_lista_precio_nombre": "P",
                    "traspaso_id": null,
                    "sucursal_traspaso_nombre": null,
                    "sucursal_traspaso_codigo": null,
                    "traspaso_entregado": null,
                    "cotizacion": null,
                    "folio_llave": null,
                    "resultado_descripcion": null,
                    "compras": null,
                    "beneficios": null,
                    "sugeridos": null,
                    "referencia": null,
                    "beneficio_descripcion": null,
                    "beneficio_sustituto": null,
                    "beneficio_porcentaje_descuento": null,
                    "beneficio_tipo_porcentaje_descuento": null,
                    "promocion_descripcion": null,
                    "promocion_modo": null,
                    "promocion_tipo": null,
                    "promocion_monto": null
                }
            ]
        }

**Error Response:**

* **Code:** 404 Unauthorized <br />
  **Content:**

        {
            "error": "El pedido no pertenece a esta sucursal"
        }

* **Code:** 404 Unauthorized <br />
  **Content:**

        {
            "error": "Pedido no encontrado"
        }

