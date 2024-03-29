
## Beneficios Pendientes WS MTCENTER
Obtiene los beneficios pendientes  del cliente por tarjeta


 **URL**

  /ws/plan-lealtad/beneficios-pendientes/{tarjeta}

 **Method:**

  `GET`

 **Headers*

      Accept: application/json
      Content-Type: multipart/form-data

          
       
       {
          "numero_tarjeta": "9988888888888",
          "codigo_error": 0,
          "beneficios": [
            {
              "compras_mecanica": "3",
              "beneficios_mecanica": "1",
              "compras_realizadas": "3",
              "compras_pendientes": "0",
              "sku": "7501089802033",
              "producto": {
                "id": 896,
                "farmapronto_id": "001040",
                "sku": "7501089802033",
                "nombre": "ANGIOTROFIN-A-P 90MG TABLETAS C\/20",
                "descripcion": "",
                "categoria": "SISTEMA CARDIOVASCULAR",
                "categoria_id": 138,
                "laboratorio": "ARMSTRONG",
                "receta": 0,
                "clave": "SUJETO A DISPONIBILIDAD",
                "tipo": 60,
                "activos": "DILTIAZEM",
                "keywords": "",
                "frecuencia": "0",
                "contenido": "0",
                "dosis": "0",
                "tipoempaque": "90 MG",
                "temporada": "TABLETAS",
                "destacado": 0,
                "archivo": null,
                "created_at": "2017-03-16 11:49:20",
                "updated_at": "2020-06-11 16:36:13",
                "activo": 1,
                "despliega": 1,
                "precio": {
                  "id": 646,
                  "zona_id": 22,
                  "producto_id": 896,
                  "precio": 300,
                  "created_at": "2017-06-22 11:56:21",
                  "updated_at": "2020-06-04 13:59:51"
                }
              },
              "beneficio_producto": {
                "id": 305,
                "sku_compra": "7501089802033",
                "referencia": "MTCL_ARM",
                "producto_compra_nombre": "ANGIOTROFIN-A-P 90MG TABLETAS C\/20",
                "cantidad_compra": 3,
                "sku_beneficio": "7501089802033",
                "producto_beneficio_nombre": "ANGIOTROFIN-A-P 90MG TABLETAS C\/20",
                "cantidad_beneficio": 1,
                "vigencia_inicio": "2020-02-10",
                "vigencia_fin": "2020-12-31",
                "porcentaje_descuento": 0,
                "tipo_porcentaje_descuento": 0,
                "activo": 1,
                "created_at": "2020-06-04 20:54:11",
                "updated_at": "2020-06-11 18:02:48",
                "periodo_num_regalos": 10,
                "periodo_dias": 30,
                "periodo": "MENSUALES",
                "tarjeta_tipo_id": 56,
                "promocion_tipo_id": 2,
                "descripcion": "3+1 T.Farmapronto, Canjes Permitidos: 10 Mensuales, Vigencia: 31\/12\/2020, APLICAN RESTRICCIONES",
                "producto_beneficio_id": 896,
                "producto_id": 896,
                "tarjeta_farmapronto": 1,
                "sustituto": 0,
                "acumula": "1",
                "proveedor": null,
                "producto_compra": {
                  "id": 896,
                  "farmapronto_id": "001040",
                  "sku": "7501089802033",
                  "nombre": "ANGIOTROFIN-A-P 90MG TABLETAS C\/20",
                  "descripcion": "",
                  "categoria": "SISTEMA CARDIOVASCULAR",
                  "categoria_id": 138,
                  "laboratorio": "ARMSTRONG",
                  "receta": 0,
                  "clave": "SUJETO A DISPONIBILIDAD",
                  "tipo": 60,
                  "activos": "DILTIAZEM",
                  "keywords": "",
                  "frecuencia": "0",
                  "contenido": "0",
                  "dosis": "0",
                  "tipoempaque": "90 MG",
                  "temporada": "TABLETAS",
                  "destacado": 0,
                  "archivo": null,
                  "created_at": "2017-03-16 11:49:20",
                  "updated_at": "2020-06-11 16:36:13",
                  "activo": 1,
                  "despliega": 1
                },
                "producto_beneficio": {
                  "id": 896,
                  "farmapronto_id": "001040",
                  "sku": "7501089802033",
                  "nombre": "ANGIOTROFIN-A-P 90MG TABLETAS C\/20",
                  "descripcion": "",
                  "categoria": "SISTEMA CARDIOVASCULAR",
                  "categoria_id": 138,
                  "laboratorio": "ARMSTRONG",
                  "receta": 0,
                  "clave": "SUJETO A DISPONIBILIDAD",
                  "tipo": 60,
                  "activos": "DILTIAZEM",
                  "keywords": "",
                  "frecuencia": "0",
                  "contenido": "0",
                  "dosis": "0",
                  "tipoempaque": "90 MG",
                  "temporada": "TABLETAS",
                  "destacado": 0,
                  "archivo": null,
                  "created_at": "2017-03-16 11:49:20",
                  "updated_at": "2020-06-11 16:36:13",
                  "activo": 1,
                  "despliega": 1
                },
                "promocion_tipo": {
                  "id": 2,
                  "nombre": "compra_con_producto_gratis",
                  "created_at": "2019-11-08 08:57:04",
                  "updated_at": "2019-11-08 08:57:04"
                },
                "tarjeta_tipo": {
                  "id": 56,
                  "nombre": "MTCL_ARM",
                  "descripcion": "TARJETA FARMAPRONTO",
                  "created_at": "2019-11-13 05:21:00",
                  "updated_at": "2019-11-13 05:21:00"
                }
              },
              "historial_compras": {
                "mtcid": "5000",
                "idsucursal": "11678",
                "sucursal": "CYBER MI PC",
                "cajero": "Usuario WS Test",
                "idterminal": "32424",
                "fecha_hora": "2020-06-03T09:46:37",
                "sku": "7501089802033",
                "cantidad": "3",
                "tipo_movimiento": "VT:Compra",
                "numero_sesion": "68336",
                "numero_confirmacion": "",
                "referencia": "MTCL_ARM",
                "tarjetaafiliacion": "1004600003"
              },
              "referencia": "MTCL_ARM",
              "vigencia": "2020-12-31",
              "restricciones": "2",
              "beneficios_por_otorgar": "2"
            },
            {
              "compras_mecanica": "3",
              "beneficios_mecanica": "1",
              "compras_realizadas": "2",
              "compras_pendientes": "1",
              "sku": "7501124103248",
              "producto": {
                "id": 9938,
                "farmapronto_id": "011195",
                "sku": "7501124103248",
                "nombre": "PRAMIGEL 180ML SUSPENSION",
                "descripcion": "",
                "categoria": "DIGESTIVO Y METABOLISMO",
                "categoria_id": 122,
                "laboratorio": "CARNOT",
                "receta": 0,
                "clave": "DISPONIBLE",
                "tipo": 190,
                "activos": "METOCLOPRAMIDA \/ ALUMINIO \/ MAGNESIO \/ SIMETICONA",
                "keywords": "",
                "frecuencia": "6",
                "contenido": "180",
                "dosis": "30",
                "tipoempaque": "",
                "temporada": "",
                "destacado": 0,
                "archivo": "uploads\/images\/productos\/7501124103248.png",
                "created_at": "2017-03-16 11:49:28",
                "updated_at": "2020-06-11 16:36:43",
                "activo": 1,
                "despliega": 1,
                "precio": {
                  "id": 7136,
                  "zona_id": 22,
                  "producto_id": 9938,
                  "precio": 263.5,
                  "created_at": "2017-06-22 13:02:16",
                  "updated_at": "2020-05-25 22:11:26"
                }
              },
              "beneficio_producto": {
                "id": 405,
                "sku_compra": "7501124103248",
                "referencia": "MTCL_CRT",
                "producto_compra_nombre": "PRAMIGEL 180ML SUSPENSION",
                "cantidad_compra": 3,
                "sku_beneficio": "7501124103248",
                "producto_beneficio_nombre": "PRAMIGEL 180ML SUSPENSION",
                "cantidad_beneficio": 1,
                "vigencia_inicio": "2019-07-16",
                "vigencia_fin": "2020-07-31",
                "porcentaje_descuento": 0,
                "tipo_porcentaje_descuento": 0,
                "activo": 1,
                "created_at": "2020-06-04 20:54:11",
                "updated_at": "2020-06-11 18:02:48",
                "periodo_num_regalos": 3,
                "periodo_dias": 365,
                "periodo": "ANUALES",
                "tarjeta_tipo_id": 16,
                "promocion_tipo_id": 2,
                "descripcion": "3+1 T.FARMAPRONTO. CANJES PERMITIDOS: 3 ANUALES. VIGENCIA 31\/07\/2020. APLICAN RESTRICCIONES",
                "producto_beneficio_id": 9938,
                "producto_id": 9938,
                "tarjeta_farmapronto": 1,
                "sustituto": 0,
                "acumula": "1",
                "proveedor": null,
                "producto_compra": {
                  "id": 9938,
                  "farmapronto_id": "011195",
                  "sku": "7501124103248",
                  "nombre": "PRAMIGEL 180ML SUSPENSION",
                  "descripcion": "",
                  "categoria": "DIGESTIVO Y METABOLISMO",
                  "categoria_id": 122,
                  "laboratorio": "CARNOT",
                  "receta": 0,
                  "clave": "DISPONIBLE",
                  "tipo": 190,
                  "activos": "METOCLOPRAMIDA \/ ALUMINIO \/ MAGNESIO \/ SIMETICONA",
                  "keywords": "",
                  "frecuencia": "6",
                  "contenido": "180",
                  "dosis": "30",
                  "tipoempaque": "",
                  "temporada": "",
                  "destacado": 0,
                  "archivo": "uploads\/images\/productos\/7501124103248.png",
                  "created_at": "2017-03-16 11:49:28",
                  "updated_at": "2020-06-11 16:36:43",
                  "activo": 1,
                  "despliega": 1
                },
                "producto_beneficio": {
                  "id": 9938,
                  "farmapronto_id": "011195",
                  "sku": "7501124103248",
                  "nombre": "PRAMIGEL 180ML SUSPENSION",
                  "descripcion": "",
                  "categoria": "DIGESTIVO Y METABOLISMO",
                  "categoria_id": 122,
                  "laboratorio": "CARNOT",
                  "receta": 0,
                  "clave": "DISPONIBLE",
                  "tipo": 190,
                  "activos": "METOCLOPRAMIDA \/ ALUMINIO \/ MAGNESIO \/ SIMETICONA",
                  "keywords": "",
                  "frecuencia": "6",
                  "contenido": "180",
                  "dosis": "30",
                  "tipoempaque": "",
                  "temporada": "",
                  "destacado": 0,
                  "archivo": "uploads\/images\/productos\/7501124103248.png",
                  "created_at": "2017-03-16 11:49:28",
                  "updated_at": "2020-06-11 16:36:43",
                  "activo": 1,
                  "despliega": 1
                },
                "promocion_tipo": {
                  "id": 2,
                  "nombre": "compra_con_producto_gratis",
                  "created_at": "2019-11-08 08:57:04",
                  "updated_at": "2019-11-08 08:57:04"
                },
                "tarjeta_tipo": {
                  "id": 16,
                  "nombre": "MTCL_CRT",
                  "descripcion": "TARJETA FARMAPRONTO",
                  "created_at": "2019-11-13 05:20:18",
                  "updated_at": "2019-11-13 05:20:18"
                }
              },
              "historial_compras": {
                "mtcid": "5000",
                "idsucursal": "11678",
                "sucursal": "CYBER MI PC",
                "cajero": "Usuario WS Test",
                "idterminal": "32424",
                "fecha_hora": "2020-06-17T23:52:00",
                "sku": "7501124103248",
                "cantidad": "2",
                "tipo_movimiento": "VT:Compra",
                "numero_sesion": "69280",
                "numero_confirmacion": "",
                "referencia": "MTCL_CRT",
                "tarjetaafiliacion": "3800000005"
              },
              "referencia": "MTCL_CRT",
              "vigencia": "2020-07-31",
              "restricciones": "3",
              "beneficios_por_otorgar": "2"
            },
            {
              "compras_mecanica": "5",
              "beneficios_mecanica": "1",
              "compras_realizadas": "5",
              "compras_pendientes": "0",
              "sku": "7501125158773",
              "producto": {
                "id": 65539,
                "farmapronto_id": "037398",
                "sku": "7501125158773",
                "nombre": "TEINEMIA 10 MG C\/30 TABLETAS",
                "descripcion": "",
                "categoria": "SISTEMA CARDIOVASCULAR",
                "categoria_id": null,
                "laboratorio": "PISA",
                "receta": 0,
                "clave": "DISPONIBLE",
                "tipo": 0,
                "activos": "ATORVASTATINA",
                "keywords": "",
                "frecuencia": null,
                "contenido": null,
                "dosis": null,
                "tipoempaque": null,
                "temporada": null,
                "destacado": 0,
                "archivo": null,
                "created_at": "2019-12-22 00:01:20",
                "updated_at": "2020-03-04 00:01:12",
                "activo": 0,
                "despliega": 0,
                "precio": {
                  "id": 35006,
                  "zona_id": 22,
                  "producto_id": 65539,
                  "precio": 289.5,
                  "created_at": "2019-12-22 00:01:59",
                  "updated_at": "2020-02-06 00:02:03"
                }
              },
              "beneficio_producto": {
                "id": 772,
                "sku_compra": "7501125158773",
                "referencia": "MTCL_PSA",
                "producto_compra_nombre": "TEINEMIA 10 MG C\/30 TABLETAS",
                "cantidad_compra": 5,
                "sku_beneficio": "7501125158773",
                "producto_beneficio_nombre": "TEINEMIA 10 MG C\/30 TABLETAS",
                "cantidad_beneficio": 1,
                "vigencia_inicio": "2020-01-30",
                "vigencia_fin": "2021-01-31",
                "porcentaje_descuento": 0,
                "tipo_porcentaje_descuento": 0,
                "activo": 1,
                "created_at": "2020-06-04 20:54:12",
                "updated_at": "2020-06-11 18:02:50",
                "periodo_num_regalos": 2,
                "periodo_dias": 30,
                "periodo": "MENSUALES",
                "tarjeta_tipo_id": 28,
                "promocion_tipo_id": 2,
                "descripcion": "5+1 T. FARMAPRONTO, CANJES PERMITIDOS: 2 MENSUALES. VIGENCIA 31\/01\/2021 APLICAN RESTRICCIONES",
                "producto_beneficio_id": 65539,
                "producto_id": 65539,
                "tarjeta_farmapronto": 1,
                "sustituto": 0,
                "acumula": "0",
                "proveedor": null,
                "producto_compra": {
                  "id": 65539,
                  "farmapronto_id": "037398",
                  "sku": "7501125158773",
                  "nombre": "TEINEMIA 10 MG C\/30 TABLETAS",
                  "descripcion": "",
                  "categoria": "SISTEMA CARDIOVASCULAR",
                  "categoria_id": null,
                  "laboratorio": "PISA",
                  "receta": 0,
                  "clave": "DISPONIBLE",
                  "tipo": 0,
                  "activos": "ATORVASTATINA",
                  "keywords": "",
                  "frecuencia": null,
                  "contenido": null,
                  "dosis": null,
                  "tipoempaque": null,
                  "temporada": null,
                  "destacado": 0,
                  "archivo": null,
                  "created_at": "2019-12-22 00:01:20",
                  "updated_at": "2020-03-04 00:01:12",
                  "activo": 0,
                  "despliega": 0
                },
                "producto_beneficio": {
                  "id": 65539,
                  "farmapronto_id": "037398",
                  "sku": "7501125158773",
                  "nombre": "TEINEMIA 10 MG C\/30 TABLETAS",
                  "descripcion": "",
                  "categoria": "SISTEMA CARDIOVASCULAR",
                  "categoria_id": null,
                  "laboratorio": "PISA",
                  "receta": 0,
                  "clave": "DISPONIBLE",
                  "tipo": 0,
                  "activos": "ATORVASTATINA",
                  "keywords": "",
                  "frecuencia": null,
                  "contenido": null,
                  "dosis": null,
                  "tipoempaque": null,
                  "temporada": null,
                  "destacado": 0,
                  "archivo": null,
                  "created_at": "2019-12-22 00:01:20",
                  "updated_at": "2020-03-04 00:01:12",
                  "activo": 0,
                  "despliega": 0
                },
                "promocion_tipo": {
                  "id": 2,
                  "nombre": "compra_con_producto_gratis",
                  "created_at": "2019-11-08 08:57:04",
                  "updated_at": "2019-11-08 08:57:04"
                },
                "tarjeta_tipo": {
                  "id": 28,
                  "nombre": "MTCL_PSA",
                  "descripcion": "TARJETA FARMAPRONTO",
                  "created_at": "2019-11-13 05:20:21",
                  "updated_at": "2019-11-13 05:20:21"
                }
              },
              "historial_compras": {
                "mtcid": "5000",
                "idsucursal": "11678",
                "sucursal": "CYBER MI PC",
                "cajero": "fp fp fp",
                "idterminal": "32424",
                "fecha_hora": "2020-02-13T12:02:04",
                "sku": "7501125158773",
                "cantidad": "5",
                "tipo_movimiento": "VT:Compra",
                "numero_sesion": "64090",
                "numero_confirmacion": "",
                "referencia": "MTCL_PSA",
                "tarjetaafiliacion": "1107000011"
              },
              "referencia": "MTCL_PSA",
              "vigencia": "2021-01-31",
              "restricciones": "2",
              "beneficios_por_otorgar": "2"
            },
            {
              "compras_mecanica": "5",
              "beneficios_mecanica": "1",
              "compras_realizadas": "5",
              "compras_pendientes": "0",
              "sku": "7501125167218",
              "producto": {
                "id": 46098,
                "farmapronto_id": "051849",
                "sku": "7501125167218",
                "nombre": "GALACTUS 100 UI AMP 1X10 ML",
                "descripcion": "Diabetes mellitus Tipo I",
                "categoria": "DIGESTIVO Y METABOLISMO",
                "categoria_id": 151,
                "laboratorio": "PISA",
                "receta": 0,
                "clave": "DISPONIBLE",
                "tipo": 18,
                "activos": "INSULINA HUMANA",
                "keywords": "Insulina, glargina, tecnologia, adn, recombinante, diabetes, mellitus, tipo 1, tipo 2",
                "frecuencia": "0",
                "contenido": "0",
                "dosis": "0",
                "tipoempaque": "",
                "temporada": "",
                "destacado": 0,
                "archivo": "uploads\/images\/productos\/7501125167218.png",
                "created_at": "2017-03-16 11:50:02",
                "updated_at": "2020-06-04 13:59:24",
                "activo": 0,
                "despliega": 0,
                "precio": {
                  "id": 28595,
                  "zona_id": 22,
                  "producto_id": 46098,
                  "precio": 725,
                  "created_at": "2017-07-05 12:42:10",
                  "updated_at": "2020-05-25 22:11:43"
                }
              },
              "beneficio_producto": {
                "id": 743,
                "sku_compra": "7501125167218",
                "referencia": "MTCL_PSA",
                "producto_compra_nombre": "GALACTUS 100 UI AMP 1X10 ML",
                "cantidad_compra": 5,
                "sku_beneficio": "7501125167218",
                "producto_beneficio_nombre": "GALACTUS 100 UI AMP 1X10 ML",
                "cantidad_beneficio": 1,
                "vigencia_inicio": "2020-01-30",
                "vigencia_fin": "2021-01-31",
                "porcentaje_descuento": 0,
                "tipo_porcentaje_descuento": 0,
                "activo": 1,
                "created_at": "2020-06-04 20:54:12",
                "updated_at": "2020-06-11 18:02:50",
                "periodo_num_regalos": 2,
                "periodo_dias": 30,
                "periodo": "MENSUALES",
                "tarjeta_tipo_id": 28,
                "promocion_tipo_id": 2,
                "descripcion": "5+1 T. FARMAPRONTO, CANJES PERMITIDOS: 2 MENSUALES. VIGENCIA 31\/01\/2021 APLICAN RESTRICCIONES",
                "producto_beneficio_id": 46098,
                "producto_id": 46098,
                "tarjeta_farmapronto": 1,
                "sustituto": 0,
                "acumula": "0",
                "proveedor": null,
                "producto_compra": {
                  "id": 46098,
                  "farmapronto_id": "051849",
                  "sku": "7501125167218",
                  "nombre": "GALACTUS 100 UI AMP 1X10 ML",
                  "descripcion": "Diabetes mellitus Tipo I",
                  "categoria": "DIGESTIVO Y METABOLISMO",
                  "categoria_id": 151,
                  "laboratorio": "PISA",
                  "receta": 0,
                  "clave": "DISPONIBLE",
                  "tipo": 18,
                  "activos": "INSULINA HUMANA",
                  "keywords": "Insulina, glargina, tecnologia, adn, recombinante, diabetes, mellitus, tipo 1, tipo 2",
                  "frecuencia": "0",
                  "contenido": "0",
                  "dosis": "0",
                  "tipoempaque": "",
                  "temporada": "",
                  "destacado": 0,
                  "archivo": "uploads\/images\/productos\/7501125167218.png",
                  "created_at": "2017-03-16 11:50:02",
                  "updated_at": "2020-06-04 13:59:24",
                  "activo": 0,
                  "despliega": 0
                },
                "producto_beneficio": {
                  "id": 46098,
                  "farmapronto_id": "051849",
                  "sku": "7501125167218",
                  "nombre": "GALACTUS 100 UI AMP 1X10 ML",
                  "descripcion": "Diabetes mellitus Tipo I",
                  "categoria": "DIGESTIVO Y METABOLISMO",
                  "categoria_id": 151,
                  "laboratorio": "PISA",
                  "receta": 0,
                  "clave": "DISPONIBLE",
                  "tipo": 18,
                  "activos": "INSULINA HUMANA",
                  "keywords": "Insulina, glargina, tecnologia, adn, recombinante, diabetes, mellitus, tipo 1, tipo 2",
                  "frecuencia": "0",
                  "contenido": "0",
                  "dosis": "0",
                  "tipoempaque": "",
                  "temporada": "",
                  "destacado": 0,
                  "archivo": "uploads\/images\/productos\/7501125167218.png",
                  "created_at": "2017-03-16 11:50:02",
                  "updated_at": "2020-06-04 13:59:24",
                  "activo": 0,
                  "despliega": 0
                },
                "promocion_tipo": {
                  "id": 2,
                  "nombre": "compra_con_producto_gratis",
                  "created_at": "2019-11-08 08:57:04",
                  "updated_at": "2019-11-08 08:57:04"
                },
                "tarjeta_tipo": {
                  "id": 28,
                  "nombre": "MTCL_PSA",
                  "descripcion": "TARJETA FARMAPRONTO",
                  "created_at": "2019-11-13 05:20:21",
                  "updated_at": "2019-11-13 05:20:21"
                }
              },
              "historial_compras": {
                "mtcid": "5000",
                "idsucursal": "11678",
                "sucursal": "CYBER MI PC",
                "cajero": "fp fp fp",
                "idterminal": "32424",
                "fecha_hora": "2020-02-13T12:03:39",
                "sku": "7501125167218",
                "cantidad": "5",
                "tipo_movimiento": "VT:Compra",
                "numero_sesion": "64091",
                "numero_confirmacion": "",
                "referencia": "MTCL_PSA",
                "tarjetaafiliacion": "1107000011"
              },
              "referencia": "MTCL_PSA",
              "vigencia": "2021-01-31",
              "restricciones": "2",
              "beneficios_por_otorgar": "2"
            }
          ]
        }
            
        
        
## Tarjeta Plan de lealtad WS MTCENTER
Obtiene los beneficios pendientes  del cliente por tarjeta


 **URL**

  /ws/plan-lealtad/tarjetas/{tarjeta}

 **Method:**

  `GET`

 **Headers**

      Accept: application/json
      Content-Type: multipart/form-data
          
        {
          "cliente": {
            "nombre": "Rocío Parada Morán",
            "apellidoPaterno": "a",
            "apellidoMaterno": "Ap Materno",
            "fechaNacimiento": "01\/01\/1994",
            "sexo": "f",
            "email": "rocio.parmor@gmail.com",
            "telefono": "3111401382",
            "calle": "diaz hordaz",
            "numeroExterior": "869",
            "numeroInterior": "",
            "colonia": "santa cecilia",
            "cp": "63089",
            "nip": "9047",
            "idCatalogoCiudad": "2099"
          },
          "tarjeta": "7771997882"
        }
        
        

## Reenviar NIP [/monedero/renviar-nip/{tarjeta}]

### Reenviar NIP por SMS [POST]

Parsing WS de MTCenter

    + Headers
        Authorization: Bearer {TOKEN}


+ Attributes (application/json)
   + tarjeta (string) - 7773274199

+ Response 200 (application/json)

    + Body
            
            {
              "descripcion": "Se reenvió correctamente el NIP.",
              "codigoRespuesta": 0,
              "tarjeta": "7773274199"
            }
            
            
+ Reponse 401 (application/json)
    
    + Body
    
        {
          "error": "Unauthenticated."
        }


+ Response 404 (application/json)
    
    + Body
        
        {
          "error": "Model not found."
        }