FORMAT: 1A
HOST: https://callcenter.appsfarmapronto.com

# API CRT


## oAuth Token [/oauth/token]

El token generano en la respuesta `access_token` cuenta con 365 días para permancer valido.


### Requesting Token [POST]

+ Request (application/x-www-form-urlencoded)


+ Attributes
    + grant_type (string)
    + client_id (number) 
    + client_secret (string) - [CLIENT_SECRET]
    + username (string) - [EMAIL]
    + password (string) - [PASSWORD]

+ Response 200 (application/json)

    + Body
    
            {
                "token_type": "Bearer",
                "expires_in": 31535998,
                "access_token": "765e4A3OcJsVeQicCJvbGcieirSrtI1NiIsImp0aSI6ImY1ZTlmODU3YzFlMTEwNmJmYjE3OTIw MzI1MmMxNmYzYjAwYzM3NGI0ZTg2NDRmMjhhZTJjNDhmMjYxZDNjNzRlYmY3ZTA0M2NiNmQyYmJkI n0.eyJhdWQiOiIxIiwianRpIjoiZjVlOWY4NTdjMWUxMTA2YmZiMTc5MjAzMjUyYzE2ZjNiMDBjMz c0YjRlODY0NGYyOGFlMmM0OGYyNjFkM2M3NGViZjdlMDQzY2I2ZDJiYmQiLCJpYXQiOjE1MjA1Mzg 1MTQsIm5iZiI6MTUyMDUzODUxNCwiZXhwIjoxNTUyMDc0NTEyLCJzdWIiOiIxIiwic2NvcGVzIjpb XX0.kVumVGc9tClmu_IfufpxqOq82NjRrsX_6WPjzOHJqXnRbpUBjIAy3X3g2S5WUJGaVfDA5TlZ6 o10kuWzEYmQ6FJ0Gs7CCwQQ5M0TFqcGoNolOTpMR75dkADuxyh_hEYXEJzO1FVolbhTbLX793OBJT CbZQCGlqDFpzDTfuxpxyCd8AXNP2-mv-9qLoE0wt4MQU6wtbfd-oDNuVP8p1j5asfjlStwy0AMoC3 eqw7X_omgwYXypzTBGTH8xGIntQC17e4C_AIwhkcJIfHAgq0TmXYFnxCinnEzqdz4soWVU0zt4iho opN1lFDGjpHpxKnPYcPkt76uHnpkBrtUB9cKSU1VSXrzA3L3MqgUe0VR4vBwyefEDZThIeaFowT4N sSPLaYu-X2hF2hRTyw722HmbiQARCbtWATfQE3veOlsLpPES-_WzQEuMCC32dvZpIyBzZOiDrvqwq EUryvJg_hecIQFGNNE_fqO6D9LG5E08AbJ2U0EiOfd4pGaCF80N_7FPkB8P0wgZKqY6WJfpKPwHZj SMbgdW7noJyynwK5Ce3upMrK_9ASZkciPCzka9xdYuowcx2h7CNjjbkgUaHZFGxR7gDoBIW2qTChS 2LSrXEyn3hqYlBP4IOrb6EP3r79i6eGw0KXRtk6B5R5WAu_pwaErZq0dN43Gnz2cyaWnHNg",
            }
           

## Pedidos [/api/crt/pedidos]

### Registro de nuevo pedido [POST]


    + Headers
        Authorization: Bearer {TOKEN}


+ Request (application/json)
            
            {
                "cliente_nombre": "PEDIDO",
                "cliente_apellido_paterno": "PRUEBA",
                "cliente_apellido_materno": "PRUEBA",
                "cliente_telefono": "7773274199",
                "cliente_email": "email@cliente.com",
                "cliente_fecha_nacimiento": "",
                "estado": "MORELOS",
                "usuario_erp": "CRPRUEBA",
                "municipio": "CUERNAVACA",
                "colonia": "MORELOS",
                "calle": "Prolongacion Ahuatepec",
                "numero_interior": "",
                "numero_exterior": "307",
                "referencia_direccion": "M",
                "codigo_postal": "62270",
                "tipo_direccion": "Oficina",
                "monto_total": "352.00",
                "sucursales": [
                    {
                        "id": "901901901",
                        "sucursal_nombre": "Q",
                        "productos": [
                            {
                            "id": "057578",
                            "sku": "7506205811678",
                            "cantidad": 1.0,
                            "precio_unidad": 352.0,
                            "lista_precio_zona": "23",
                            "receta": false,
                            "traspaso": null
                            }
                        ]
                    }
                ],
                "metodo_pago": "efectivo",
                "monto_efectivo": 500,
                "tarjeta": null,
                "tarjeta_last4": null,
                "tarjeta_tipo": null,
                "recetas": false,
                "factura": false,
                "factura_rfc": "",
                "factura_estado": "",
                "factura_municipio": "",
                "factura_calle": "",
                "factura_numero": "",
                "factura_colonia": "",
                "factura_codigo_postal": ""
            }


+ Response 200 (application/json)

    + Body
            
            {
              "pedido": {
                "id": 151630,
                "cliente_direccion_id": 117933,
                "user_id": 171,
                "folio": "CRT0151630",
                "codigo_confirmacion": null,
                "created_at": "2020-10-16 19:29:09",
                "usuario_erp": "INTELISIS",
                "cliente": {
                  "id": 171,
                  "nombre": "PEDIDO",
                  "apellido_paterno": "PRUEBA",
                  "apellido_materno": "PRUEBA",
                  "email": "email@cliente.com",
                  "telefono": "7773274199",
                  "nombre_completo": " "
                },
                "direccion": {
                  "estado": "MORELOS",
                  "municipio": "CUERNAVACA",
                  "colonia": "MORELOS",
                  "colonia_str": "MORELOS",
                  "calle": "Prolongacion Ahuatepec",
                  "numero_interior": "",
                  "numero_exterior": "307",
                  "codigo_postal": "62270",
                  "referencia": "M",
                  "tipo": "Oficina"
                },
                "estado": {
                  "paso": "recibido"
                },
                "repartidor": null,
                "pago": {
                  "id": 151618,
                  "estado": "pendiente",
                  "metodo_pago": "efectivo",
                  "monto": "352.00",
                  "monto_efectivo": "500",
                  "total": "500",
                  "tarjeta": null,
                  "tarjeta_last4": null,
                  "tarjeta_tipo": null,
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
                  "codigo_verificacion": "1467",
                  "placas_com": null,
                  "placas_app": null
                },
                "sucursal": null,
                "pedidos_relacionados": null,
                "productos": [
                  {
                    "sku": "7506205811678",
                    "nombre": "ENFAGROW 3 PREMIUM 800 GR 2 PACK",
                    "receta": 0,
                    "receta_imagen": null,
                    "pedido_producto_id": 260486,
                    "cantidad_productos": 1,
                    "precio_suma_total": "352.00",
                    "pecio_unitario": "352.00",
                    "pecio_unitario_lista": "352.00",
                    "farmapronto_id": "057578",
                    "sucursal_lista_precio_id": "YY",
                    "sucursal_lista_precio_nombre": "YY",
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
            }

+ Response 422 (application/json)
    + Body
        
        
            {
              "errors": {
                "cliente_apellido_paterno": [
                  "El campo cliente apellido paterno es obligatorio."
                ],
                "cliente_apellido_materno": [
                  "El campo cliente apellido materno es obligatorio."
                ],
                "cliente_telefono": [
                  "El campo cliente telefono es obligatorio."
                ]
              }
            }
            

+ Response 406 (application/json)
    + Body
    
    
            {
              "error": "Formato json invalido"
            }
            

