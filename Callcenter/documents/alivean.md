FORMAT: 1A
HOST: https://callcenter.appsfarmapronto.com

# API ALIVEAN


## oAuth Token [/oauth/token]

El token generano en la respuesta `access_token` cuenta con 365 días para permancer valido.


### Requesting Token [POST]

+ Request (application/x-www-form-urlencoded)


+ Attributes
    + grant_type (string) - password
    + client_id (number) - 1
    + client_secret (string) - GNqBUGJIRLv5gTf7D6RdE3uPwUT1zmFPNkXhRZSF
    + username (string) - alivean@grupofarmapronto.com
    + password (string) - $alivean-creacion-pedidos@

+ Response 200 (application/json)

    + Body
    
            {
                "token_type": "Bearer",
                "expires_in": 31535998,
                "access_token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsImp0aSI6ImY1ZTlmODU3YzFlMTEwNmJmYjE3OTIw MzI1MmMxNmYzYjAwYzM3NGI0ZTg2NDRmMjhhZTJjNDhmMjYxZDNjNzRlYmY3ZTA0M2NiNmQyYmJkI n0.eyJhdWQiOiIxIiwianRpIjoiZjVlOWY4NTdjMWUxMTA2YmZiMTc5MjAzMjUyYzE2ZjNiMDBjMz c0YjRlODY0NGYyOGFlMmM0OGYyNjFkM2M3NGViZjdlMDQzY2I2ZDJiYmQiLCJpYXQiOjE1MjA1Mzg 1MTQsIm5iZiI6MTUyMDUzODUxNCwiZXhwIjoxNTUyMDc0NTEyLCJzdWIiOiIxIiwic2NvcGVzIjpb XX0.kVumVGc9tClmu_IfufpxqOq82NjRrsX_6WPjzOHJqXnRbpUBjIAy3X3g2S5WUJGaVfDA5TlZ6 o10kuWzEYmQ6FJ0Gs7CCwQQ5M0TFqcGoNolOTpMR75dkADuxyh_hEYXEJzO1FVolbhTbLX793OBJT CbZQCGlqDFpzDTfuxpxyCd8AXNP2-mv-9qLoE0wt4MQU6wtbfd-oDNuVP8p1j5asfjlStwy0AMoC3 eqw7X_omgwYXypzTBGTH8xGIntQC17e4C_AIwhkcJIfHAgq0TmXYFnxCinnEzqdz4soWVU0zt4iho opN1lFDGjpHpxKnPYcPkt76uHnpkBrtUB9cKSU1VSXrzA3L3MqgUe0VR4vBwyefEDZThIeaFowT4N sSPLaYu-X2hF2hRTyw722HmbiQARCbtWATfQE3veOlsLpPES-_WzQEuMCC32dvZpIyBzZOiDrvqwq EUryvJg_hecIQFGNNE_fqO6D9LG5E08AbJ2U0EiOfd4pGaCF80N_7FPkB8P0wgZKqY6WJfpKPwHZj SMbgdW7noJyynwK5Ce3upMrK_9ASZkciPCzka9xdYuowcx2h7CNjjbkgUaHZFGxR7gDoBIW2qTChS 2LSrXEyn3hqYlBP4IOrb6EP3r79i6eGw0KXRtk6B5R5WAu_pwaErZq0dN43Gnz2cyaWnHNg",
            }
           

## Pedidos [/api/alivean/pedidos]

### Registro de nuevo pedido [POST]


    + Headers
        Authorization: Bearer {TOKEN}


+ Request (application/json)

            {
                "cliente_nombre" : "Erick",
                "cliente_apellido_paterno" : "Brito",
                "cliente_apellido_materno" : "A",
                "cliente_telefono" : "527773274199",
                "cliente_email" : "erick@creativesociety.mx",
                "lat" : "18.935832",
                 "lon" : "-99.2322367",
                "estado_id" : 17,
                "municipio_id" : 502,
                "colonia" : "Lomas de la selva",
                "calle" : "Prolongación Ahuatepec",
                "numero_interior" : null,
                "numero_exterior" : "307",
                "referencia_direccion" : null,
                "codigo_postal" : "62270",
                "tipo_direccion" : null,
                "monto_total" : 70.5,
                "productos" : [
                    {
                    "id" :  "016959",
                    "sku" :  "7501086801053",
                    "cantidad" :  1,
                    "precio_unidad" :  "6.5",
                    "receta" :  false
                    },
                    {
                        "id" :  "005603",
                        "sku" :  "7501836003393",
                        "cantidad" :  "1",
                        "precio_unidad" :  "64.0",
                        "receta" :  false
                    }
                ],
              "metodo_pago" : "efectivo",
              "monto_efectivo" : 500,
              "recetas" : false,
              "ciudad_cobertura_id" : 1,
              "factura": false
            }

+ Response 200 (application/json)

    + Body
            
            {
              "pedido": {
                "id": 112303,
                "cliente_direccion_id": 91073,
                "user_id": 8843,
                "folio": "ALI0112303",
                "codigo_confirmacion": null,
                "created_at": "2020-03-31 18:30:44",
                "usuario_erp": "ALIVEAN",
                "cliente": {
                  "id": 8843,
                  "nombre": "Erick",
                  "apellido_paterno": "Brito",
                  "apellido_materno": "A",
                  "email": "erick@creativesociety.mx",
                  "telefono": "527773274199"
                },
                "direccion": {
                  "estado": "MORELOS",
                  "municipio": "CUERNAVACA",
                  "colonia": "Lomas de la selva",
                  "colonia_str": "Lomas de la selva",
                  "calle": "Prolongación Ahuatepec",
                  "numero_interior": null,
                  "numero_exterior": "307",
                  "codigo_postal": "62270",
                  "referencia": null,
                  "tipo": "casa"
                },
                "estado": {
                  "paso": "recibido"
                },
                "repartidor": null,
                "pago": {
                  "id": 112293,
                  "estado": "pendiente",
                  "metodo_pago": "efectivo",
                  "monto": "70.5",
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
                "sucursal": null,
                "productos": [
                  {
                    "sku": "7501836003393",
                    "nombre": "PARACETAMOL \/IBUPROFENO 325\/200 MG  C\/20 TABLETAS (DUALGOS)",
                    "receta": 0,
                    "receta_imagen": "http:\/\/farmapronto-multiples.csgroup.mx\/uploads\/recetas\/8AgdqoZSJOANcrZObeNyaKEf7MTOMVCUtiR7Iwo0.png",
                    "pedido_producto_id": 192456,
                    "precio_suma_total": 64,
                    "cantidad_productos": 1,
                    "pecio_unitario": 64,
                    "farmapronto_id": "005603",
                    "sucursal_lista_precio_id": "YY",
                    "sucursal_lista_precio_nombre": "YY",
                    "traspaso_id": null,
                    "sucursal_traspaso_nombre": null,
                    "sucursal_traspaso_codigo": null,
                    "traspaso_entregado": null
                  },
                  {
                    "sku": "7501086801053",
                    "nombre": "AGUA ELECTROPURA 20LT",
                    "receta": 0,
                    "receta_imagen": null,
                    "pedido_producto_id": 192455,
                    "precio_suma_total": 6.5,
                    "cantidad_productos": 1,
                    "pecio_unitario": 6.5,
                    "farmapronto_id": "016959",
                    "sucursal_lista_precio_id": "YY",
                    "sucursal_lista_precio_nombre": "YY",
                    "traspaso_id": null,
                    "sucursal_traspaso_nombre": null,
                    "sucursal_traspaso_codigo": null,
                    "traspaso_entregado": null
                  }
                ],
                "sucursales": [
                  {
                    "id": 62,
                    "user_id": 111,
                    "codigo": "86",
                    "nombre": "Q",
                    "telefono": "7772575913",
                    "colonia_id": 34754,
                    "municipio_id": 502,
                    "estado_id": 17,
                    "zona_sucursal_id": 5,
                    "ciudad_cobertura_id": null,
                    "direccion": "LEÑEROS",
                    "direccion_numero": "68",
                    "codigo_postal": "62290",
                    "lon": "-99.21034696802599",
                    "lat": "18.930405497133883",
                    "ancla": 1,
                    "checkin": 1,
                    "dias": "LUN, MAR, MIE, JUE, VIE, SAB, DOM",
                    "horario_inicio": "07:00:00",
                    "horario_final": "22:00:00",
                    "24_hrs": 0,
                    "base": 1,
                    "almacen": 1,
                    "created_at": "2017-07-05 13:45:09",
                    "updated_at": "2020-02-29 13:24:02",
                    "deleted_at": null,
                    "pivot": {
                      "pedido_id": 112303,
                      "sucursal_id": 62,
                      "aceptado": 0,
                      "rechazado": 0,
                      "activo": 0,
                      "orden": 1,
                      "created_at": "2020-03-31 18:30:44",
                      "updated_at": "2020-03-31 18:30:44"
                    },
                    "colonia": {
                      "id": 34754,
                      "municipio_id": 502,
                      "codigo_postal": "62290",
                      "nombre": "VISTA HERMOSA",
                      "created_at": "2017-03-16 17:48:42",
                      "updated_at": "2017-03-16 17:48:42"
                    },
                    "municipio": {
                      "id": 502,
                      "estado_id": 17,
                      "nombre": "CUERNAVACA",
                      "created_at": "2017-03-16 17:47:55",
                      "updated_at": "2017-03-16 17:47:55"
                    },
                    "estado": {
                      "id": 17,
                      "nombre": "MORELOS",
                      "created_at": "2017-03-16 17:47:54",
                      "updated_at": "2017-03-16 17:47:54"
                    }
                  }
                ]
              }
            }

## Validar cobertura [/api/alivean/validar-cobertura]
Verificar cobertura de sucursales comercializadora farmapronto por lat,lon devolviendo cobertura

### Validar cobertura [POST]

+ Attributes
    + lat (string) - Lat
    + lon (string) - Long
        
     
+ Response 200 (application/json)

    + Body
    
            {
              "ciudades_cobertura_verificada": [
                {
                  "id": 1,
                  "estado_id": 17,
                  "municipio_id": 502,
                  "lat": "18.92421",
                  "lon": "-99.221566",
                  "nombre": "CUERNAVACA",
                  "horario_final": "22:30",
                  "horario_inicio": "7:00",
                  "_24_hrs": 1,
                  "validada": 1,
                  "zona_horaria": null,
                  "created_at": "2018-09-03 11:57:19",
                  "updated_at": "2018-12-05 05:13:57",
                  "distancia": 1.5931149831132918,
                  "estado": {
                    "id": 17,
                    "nombre": "MORELOS",
                    "created_at": "2017-03-16 11:47:54",
                    "updated_at": "2017-03-16 11:47:54"
                  },
                  "municipio": {
                    "id": 502,
                    "estado_id": 17,
                    "nombre": "CUERNAVACA",
                    "created_at": "2017-03-16 11:47:55",
                    "updated_at": "2017-03-16 11:47:55"
                  },
                  "sucursales": [
                    {
                      "id": 1,
                      "user_id": 5396,
                      "codigo": "1",
                      "nombre": "AA",
                      "telefono": "7772575993",
                      "email_oficial": null,
                      "colonia_id": 34727,
                      "municipio_id": 502,
                      "estado_id": 17,
                      "zona_sucursal_id": 3,
                      "ciudad_cobertura_id": null,
                      "direccion": "AV. VICENTE GUERRERO",
                      "direccion_numero": "107",
                      "codigo_postal": "62230",
                      "lon": "-99.23085095421447",
                      "lat": "18.95742636448077",
                      "ancla": 0,
                      "checkin": 0,
                      "dias": "LUN, MAR, MIE, JUE, VIE, SAB, DOM",
                      "horario_inicio": "07:00:00",
                      "horario_final": "22:59:00",
                      "24_hrs": 0,
                      "base": 0,
                      "almacen": 0,
                      "comercializadora": 1,
                      "pickup": 0,
                      "domicilio_propios": 1,
                      "domicilio_terceros": 0,
                      "disponible": 0,
                      "km_cobertura": 10,
                      "created_at": "2017-03-16 11:50:05",
                      "updated_at": "2019-10-22 06:25:11",
                      "deleted_at": null
                    },
                    {
                      "id": 22,
                      "user_id": 133,
                      "codigo": "24",
                      "nombre": "YY",
                      "telefono": "7772575916",
                      "email_oficial": null,
                      "colonia_id": 34661,
                      "municipio_id": 502,
                      "estado_id": 17,
                      "zona_sucursal_id": 4,
                      "ciudad_cobertura_id": null,
                      "direccion": "AV.MORELOS SUR",
                      "direccion_numero": "157",
                      "codigo_postal": "62050",
                      "lon": "-99.23195740395204",
                      "lat": "18.90517509983967",
                      "ancla": 0,
                      "checkin": 1,
                      "dias": "LUN, MAR, MIE, JUE, VIE, SAB, DOM",
                      "horario_inicio": "07:00:00",
                      "horario_final": "23:00:00",
                      "24_hrs": 0,
                      "base": 0,
                      "almacen": 1,
                      "comercializadora": 1,
                      "pickup": 0,
                      "domicilio_propios": 1,
                      "domicilio_terceros": 0,
                      "disponible": 0,
                      "km_cobertura": 10,
                      "created_at": "2017-03-16 11:50:05",
                      "updated_at": "2019-12-21 06:33:40",
                      "deleted_at": null
                    },
                    {
                      "id": 23,
                      "user_id": 73,
                      "codigo": "25",
                      "nombre": "ZZ",
                      "telefono": "7772575981",
                      "email_oficial": null,
                      "colonia_id": 34739,
                      "municipio_id": 502,
                      "estado_id": 17,
                      "zona_sucursal_id": 3,
                      "ciudad_cobertura_id": null,
                      "direccion": "NUEVA INGLATERRA",
                      "direccion_numero": "500",
                      "codigo_postal": "62240",
                      "lon": "-99.227994",
                      "lat": "18.951769",
                      "ancla": 0,
                      "checkin": 0,
                      "dias": "LUN, MAR, MIE, JUE, VIE, SAB, DOM",
                      "horario_inicio": "07:00:00",
                      "horario_final": "22:58:00",
                      "24_hrs": 0,
                      "base": 0,
                      "almacen": 1,
                      "comercializadora": 1,
                      "pickup": 0,
                      "domicilio_propios": 1,
                      "domicilio_terceros": 0,
                      "disponible": 0,
                      "km_cobertura": 10,
                      "created_at": "2017-03-16 11:50:05",
                      "updated_at": "2019-10-22 10:29:47",
                      "deleted_at": null
                    },
                    {
                      "id": 27,
                      "user_id": 53,
                      "codigo": "29",
                      "nombre": "A",
                      "telefono": "7772576155",
                      "email_oficial": null,
                      "colonia_id": 34727,
                      "municipio_id": 502,
                      "estado_id": 17,
                      "zona_sucursal_id": 3,
                      "ciudad_cobertura_id": null,
                      "direccion": "MIGUEL HIDALGO",
                      "direccion_numero": "402",
                      "codigo_postal": "62220",
                      "lon": "-99.22617803093567",
                      "lat": "18.969818477006346",
                      "ancla": 0,
                      "checkin": 0,
                      "dias": "LUN, MAR, MIE, JUE, VIE, SAB, DOM",
                      "horario_inicio": "07:00:00",
                      "horario_final": "22:59:00",
                      "24_hrs": 0,
                      "base": 0,
                      "almacen": 0,
                      "comercializadora": 1,
                      "pickup": 0,
                      "domicilio_propios": 1,
                      "domicilio_terceros": 0,
                      "disponible": 0,
                      "km_cobertura": 10,
                      "created_at": "2017-03-16 11:50:05",
                      "updated_at": "2019-10-02 16:09:31",
                      "deleted_at": null
                    },
                    {
                      "id": 28,
                      "user_id": 53,
                      "codigo": "30",
                      "nombre": "B",
                      "telefono": "7772576416",
                      "email_oficial": null,
                      "colonia_id": 34755,
                      "municipio_id": 502,
                      "estado_id": 17,
                      "zona_sucursal_id": 3,
                      "ciudad_cobertura_id": null,
                      "direccion": "CARRETERA CUERNAVACA-TEPOZTLAN",
                      "direccion_numero": "20",
                      "codigo_postal": "62300",
                      "lon": "-99.2125484",
                      "lat": "18.9696297",
                      "ancla": 0,
                      "checkin": 0,
                      "dias": "LUN, MAR, MIE, JUE, VIE, SAB, DOM",
                      "horario_inicio": "07:00:00",
                      "horario_final": "22:59:00",
                      "24_hrs": 0,
                      "base": 0,
                      "almacen": 0,
                      "comercializadora": 1,
                      "pickup": 0,
                      "domicilio_propios": 1,
                      "domicilio_terceros": 0,
                      "disponible": 0,
                      "km_cobertura": 10,
                      "created_at": "2017-03-16 11:50:05",
                      "updated_at": "2019-09-20 05:17:02",
                      "deleted_at": null
                    },
                    {
                      "id": 47,
                      "user_id": 53,
                      "codigo": "53",
                      "nombre": "G",
                      "telefono": "7771032342",
                      "email_oficial": null,
                      "colonia_id": 34807,
                      "municipio_id": 502,
                      "estado_id": 17,
                      "zona_sucursal_id": 4,
                      "ciudad_cobertura_id": null,
                      "direccion": "RUIZ CORTINEZ",
                      "direccion_numero": "101",
                      "codigo_postal": "62446",
                      "lon": "-99.2193291",
                      "lat": "18.9058946",
                      "ancla": 0,
                      "checkin": 0,
                      "dias": "LUN, MAR, MIE, JUE, VIE, SAB, DOM",
                      "horario_inicio": "07:00:00",
                      "horario_final": "22:59:00",
                      "24_hrs": 0,
                      "base": 0,
                      "almacen": 0,
                      "comercializadora": 1,
                      "pickup": 0,
                      "domicilio_propios": 1,
                      "domicilio_terceros": 0,
                      "disponible": 0,
                      "km_cobertura": 10,
                      "created_at": "2017-03-16 11:50:05",
                      "updated_at": "2019-10-22 10:28:44",
                      "deleted_at": null
                    },
                    {
                      "id": 50,
                      "user_id": 53,
                      "codigo": "56",
                      "nombre": "J",
                      "telefono": "7772679481",
                      "email_oficial": null,
                      "colonia_id": 34717,
                      "municipio_id": 502,
                      "estado_id": 17,
                      "zona_sucursal_id": 3,
                      "ciudad_cobertura_id": null,
                      "direccion": "UNIVERSIDAD",
                      "direccion_numero": "1001",
                      "codigo_postal": "62209",
                      "lon": "-99.23575924351655",
                      "lat": "18.977791656967813",
                      "ancla": 0,
                      "checkin": 0,
                      "dias": "LUN, MAR, MIE, JUE, VIE, SAB, DOM",
                      "horario_inicio": "07:00:00",
                      "horario_final": "22:59:00",
                      "24_hrs": 0,
                      "base": 0,
                      "almacen": 0,
                      "comercializadora": 1,
                      "pickup": 0,
                      "domicilio_propios": 1,
                      "domicilio_terceros": 0,
                      "disponible": 0,
                      "km_cobertura": 10,
                      "created_at": "2017-03-16 11:50:05",
                      "updated_at": "2019-09-20 05:17:40",
                      "deleted_at": null
                    },
                    {
                      "id": 62,
                      "user_id": 111,
                      "codigo": "86",
                      "nombre": "Q",
                      "telefono": "7772575913",
                      "email_oficial": null,
                      "colonia_id": 34754,
                      "municipio_id": 502,
                      "estado_id": 17,
                      "zona_sucursal_id": 5,
                      "ciudad_cobertura_id": null,
                      "direccion": "LEÑEROS",
                      "direccion_numero": "68",
                      "codigo_postal": "62290",
                      "lon": "-99.21034696802599",
                      "lat": "18.930405497133883",
                      "ancla": 1,
                      "checkin": 1,
                      "dias": "LUN, MAR, MIE, JUE, VIE, SAB, DOM",
                      "horario_inicio": "07:00:00",
                      "horario_final": "22:00:00",
                      "24_hrs": 0,
                      "base": 1,
                      "almacen": 1,
                      "comercializadora": 1,
                      "pickup": 0,
                      "domicilio_propios": 1,
                      "domicilio_terceros": 0,
                      "disponible": 0,
                      "km_cobertura": 10,
                      "created_at": "2017-07-05 08:45:09",
                      "updated_at": "2020-04-07 13:58:09",
                      "deleted_at": null
                    },
                    {
                      "id": 86,
                      "user_id": 10598,
                      "codigo": "901901901",
                      "nombre": "Sucursal CS 2",
                      "telefono": "0180090900",
                      "email_oficial": null,
                      "colonia_id": 34751,
                      "municipio_id": 502,
                      "estado_id": 17,
                      "zona_sucursal_id": 3,
                      "ciudad_cobertura_id": null,
                      "direccion": "Prol. Ahuatepec",
                      "direccion_numero": "308",
                      "codigo_postal": "62270",
                      "lon": "-99.228404",
                      "lat": "18.938236",
                      "ancla": 0,
                      "checkin": 0,
                      "dias": "LUN, MAR, MIE, JUE, VIE",
                      "horario_inicio": "07:00:00",
                      "horario_final": "20:00:00",
                      "24_hrs": 0,
                      "base": 0,
                      "almacen": 0,
                      "comercializadora": 1,
                      "pickup": 0,
                      "domicilio_propios": 1,
                      "domicilio_terceros": 0,
                      "disponible": 0,
                      "km_cobertura": 10,
                      "created_at": "2018-12-19 07:22:02",
                      "updated_at": "2020-05-05 09:24:42",
                      "deleted_at": null
                    },
                    {
                      "id": 95,
                      "user_id": 152,
                      "codigo": "111",
                      "nombre": "Matriz",
                      "telefono": "7773622560",
                      "email_oficial": null,
                      "colonia_id": 34733,
                      "municipio_id": 502,
                      "estado_id": 17,
                      "zona_sucursal_id": 3,
                      "ciudad_cobertura_id": null,
                      "direccion": "Vicente Guerrero",
                      "direccion_numero": "107",
                      "codigo_postal": "62230",
                      "lon": "-99.2355306",
                      "lat": "18.9519575",
                      "ancla": 0,
                      "checkin": 1,
                      "dias": "LUN, MAR, MIE, JUE, VIE, SAB, DOM",
                      "horario_inicio": "09:00:00",
                      "horario_final": "18:00:00",
                      "24_hrs": 0,
                      "base": 0,
                      "almacen": 0,
                      "comercializadora": 1,
                      "pickup": 0,
                      "domicilio_propios": 1,
                      "domicilio_terceros": 0,
                      "disponible": 0,
                      "km_cobertura": 10,
                      "created_at": "2019-07-02 12:38:32",
                      "updated_at": "2019-12-20 12:11:49",
                      "deleted_at": null
                    },
                    {
                      "id": 96,
                      "user_id": 152,
                      "codigo": "200",
                      "nombre": "ENLACE",
                      "telefono": "7771010030",
                      "email_oficial": null,
                      "colonia_id": 34755,
                      "municipio_id": 502,
                      "estado_id": 17,
                      "zona_sucursal_id": 3,
                      "ciudad_cobertura_id": null,
                      "direccion": "AV. GASODUCTO",
                      "direccion_numero": "S\/N",
                      "codigo_postal": "62300",
                      "lon": "-99.2097",
                      "lat": "18.9598",
                      "ancla": 0,
                      "checkin": 1,
                      "dias": "LUN, MAR, MIE, JUE, VIE, SAB, DOM",
                      "horario_inicio": "06:00:00",
                      "horario_final": "17:00:00",
                      "24_hrs": 0,
                      "base": 1,
                      "almacen": 0,
                      "comercializadora": 1,
                      "pickup": 0,
                      "domicilio_propios": 1,
                      "domicilio_terceros": 0,
                      "disponible": 0,
                      "km_cobertura": 10,
                      "created_at": "2019-09-03 05:14:53",
                      "updated_at": "2019-12-20 12:11:49",
                      "deleted_at": null
                    }
                  ]
                },
                {
                  "id": 9,
                  "estado_id": 17,
                  "municipio_id": 568,
                  "lat": "18.837106",
                  "lon": "-99.182553",
                  "nombre": "EMILIANO ZAPATA",
                  "horario_final": "22:30",
                  "horario_inicio": "7:00",
                  "_24_hrs": 0,
                  "validada": 1,
                  "zona_horaria": null,
                  "created_at": null,
                  "updated_at": "2018-12-05 05:13:57",
                  "distancia": 12.108805182849466,
                  "estado": {
                    "id": 17,
                    "nombre": "MORELOS",
                    "created_at": "2017-03-16 11:47:54",
                    "updated_at": "2017-03-16 11:47:54"
                  },
                  "municipio": {
                    "id": 568,
                    "estado_id": 17,
                    "nombre": "EMILIANO ZAPATA",
                    "created_at": "2017-03-16 11:47:55",
                    "updated_at": "2017-03-16 11:47:55"
                  },
                  "sucursales": []
                },
                {
                  "id": 17,
                  "estado_id": 17,
                  "municipio_id": 1999,
                  "lat": "18.824675",
                  "lon": "-99.230203",
                  "nombre": "TEMIXCO",
                  "horario_final": "22:30",
                  "horario_inicio": "7:00",
                  "_24_hrs": 0,
                  "validada": 1,
                  "zona_horaria": null,
                  "created_at": null,
                  "updated_at": "2018-12-05 05:13:57",
                  "distancia": 12.438067919474776,
                  "estado": {
                    "id": 17,
                    "nombre": "MORELOS",
                    "created_at": "2017-03-16 11:47:54",
                    "updated_at": "2017-03-16 11:47:54"
                  },
                  "municipio": {
                    "id": 1999,
                    "estado_id": 17,
                    "nombre": "TEMIXCO",
                    "created_at": "2017-03-16 11:47:57",
                    "updated_at": "2017-03-16 11:47:57"
                  },
                  "sucursales": [
                    {
                      "id": 18,
                      "user_id": 69,
                      "codigo": "19",
                      "nombre": "OO",
                      "telefono": "7772576001",
                      "email_oficial": null,
                      "colonia_id": 34904,
                      "municipio_id": 1999,
                      "estado_id": 17,
                      "zona_sucursal_id": 11,
                      "ciudad_cobertura_id": null,
                      "direccion": "ACCESO AL DIEZ PARCELA",
                      "direccion_numero": "8",
                      "codigo_postal": "62580",
                      "lon": "-99.2090393",
                      "lat": "18.8374951",
                      "ancla": 1,
                      "checkin": 1,
                      "dias": "LUN, MAR, MIE, JUE, VIE, SAB, DOM",
                      "horario_inicio": "07:00:00",
                      "horario_final": "22:00:00",
                      "24_hrs": 0,
                      "base": 1,
                      "almacen": 1,
                      "comercializadora": 1,
                      "pickup": 0,
                      "domicilio_propios": 1,
                      "domicilio_terceros": 0,
                      "disponible": 0,
                      "km_cobertura": 10,
                      "created_at": "2017-03-16 11:50:05",
                      "updated_at": "2019-12-20 12:11:49",
                      "deleted_at": null
                    },
                    {
                      "id": 26,
                      "user_id": 53,
                      "codigo": "28",
                      "nombre": "CCC",
                      "telefono": "1193",
                      "email_oficial": null,
                      "colonia_id": 34918,
                      "municipio_id": 1999,
                      "estado_id": 17,
                      "zona_sucursal_id": 11,
                      "ciudad_cobertura_id": null,
                      "direccion": "MIGUEL HIDALGO",
                      "direccion_numero": "4",
                      "codigo_postal": "62590",
                      "lon": "-99.2475845",
                      "lat": "18.824585",
                      "ancla": 0,
                      "checkin": 0,
                      "dias": "LUN, MAR, MIE, JUE, VIE, SAB, DOM",
                      "horario_inicio": "07:00:00",
                      "horario_final": "22:59:00",
                      "24_hrs": 0,
                      "base": 0,
                      "almacen": 0,
                      "comercializadora": 1,
                      "pickup": 0,
                      "domicilio_propios": 1,
                      "domicilio_terceros": 0,
                      "disponible": 0,
                      "km_cobertura": 10,
                      "created_at": "2017-03-16 11:50:05",
                      "updated_at": "2019-10-22 06:30:18",
                      "deleted_at": null
                    },
                    {
                      "id": 49,
                      "user_id": 53,
                      "codigo": "55",
                      "nombre": "I",
                      "telefono": "7772679617",
                      "email_oficial": null,
                      "colonia_id": 34907,
                      "municipio_id": 1999,
                      "estado_id": 17,
                      "zona_sucursal_id": 11,
                      "ciudad_cobertura_id": null,
                      "direccion": "PASEO BURGOS",
                      "direccion_numero": "S\/N-M-154 Z-3",
                      "codigo_postal": "62584",
                      "lon": "-99.2210992865082",
                      "lat": "18.860623483326954",
                      "ancla": 0,
                      "checkin": 0,
                      "dias": "LUN, MAR, MIE, JUE, VIE, SAB, DOM",
                      "horario_inicio": "07:00:00",
                      "horario_final": "22:59:00",
                      "24_hrs": 0,
                      "base": 0,
                      "almacen": 0,
                      "comercializadora": 1,
                      "pickup": 0,
                      "domicilio_propios": 1,
                      "domicilio_terceros": 0,
                      "disponible": 0,
                      "km_cobertura": 10,
                      "created_at": "2017-03-16 11:50:05",
                      "updated_at": "2019-10-22 06:37:09",
                      "deleted_at": null
                    }
                  ]
                }
              ]
            }
        
        
+ Response 406 (application/json)

        Zona sin cobertura
    
    
    
+ Response 410 (application/json)
    
        Zona sin cobertura de horario