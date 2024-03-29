**Almacena Carritos**
----
Almacena productos en carrito

 **URL**

    /api-v2/carritos

 **Headers**

      Accept: application/json

 **Method:**

  `POST`

 ***Required:***

    'productos' => 'required|array',
    'cantidades' => 'required|array',
    'user_id'    => 'exists:users,id|nullable',
    'player_id'  => 'required',
    'search_id'  => 'nullable',
    'pedido_id'  => 'exists:pedidos,id|nullable'
    'zona_id'    => 'nullable' **Requerido para conocer el precio de la zona**
    'beneficios_producto_id' => 'nullable|array'


  + Response 200 (application/json) Ejemplo:


        {
          "carrito": {
            "id": 34192,
            "user_id": 17945,
            "pedido_id": null,
            "player_id": "34c1a047-9ad0-493e-b09d-30050b0cef30",
            "notificado": 0,
            "activo": 1,
            "created_at": "2020-05-25 23:27:02",
            "updated_at": "2020-05-25 23:27:02",
            "user": null,
            "pedido": null,
            "date_now": "2020-06-02 09:06:52",
            "productos": [
              {
                "id": 144586,
                "carrito_id": 34192,
                "lista_precio_id": 573,
                "cantidad": 5,
                "total": "131.25",
                "created_at": "2020-05-25 23:27:02",
                "updated_at": "2020-05-25 23:27:02",
                "promocion": 0,
                "promocion_producto_id": null,
                "beneficio_producto_id": null,
                "beneficio_cliente_id": null,
                "tarjeta_cliente_id": null,
                "lista_precio": {
                  "id": 573,
                  "zona_id": 22,
                  "producto_id": 815,
                  "precio": 35,
                  "created_at": "2017-06-22 11:55:39",
                  "updated_at": "2019-12-31 00:01:42",
                  "producto": {
                    "id": 815,
                    "farmapronto_id": "000929",
                    "sku": "7501349021068",
                    "nombre": " 0001-4 AMOXILINA 500 MG C\/12 CAP",
                    "descripcion": "",
                    "categoria": "ANTIBIOTICOS",
                    "categoria_id": null,
                    "laboratorio": "AMSA GI",
                    "receta": 1,
                    "clave": "SUJETO A DISPONIBILIDAD",
                    "tipo": 0,
                    "activos": "AMOXICILINA",
                    "keywords": "",
                    "frecuencia": null,
                    "contenido": null,
                    "dosis": null,
                    "tipoempaque": null,
                    "temporada": null,
                    "destacado": 0,
                    "archivo": null,
                    "created_at": "2017-03-16 11:49:20",
                    "updated_at": "2020-01-05 00:00:56",
                    "activo": 1,
                    "despliega": 1
                  }
                },
                "beneficio_promocion": null,
                "beneficio_cliente": null,
                "promociones": [
                  {
                    "id": 11,
                    "carrito_producto_id": 144586,
                    "promocion_producto_id": 1140,
                    "tipo_nombre": "% Descuento",
                    "created_at": "2020-05-25 23:27:02",
                    "updated_at": "2020-05-25 23:27:02",
                    "promocion_producto": {
                      "id": 1140,
                      "promocion_id": 1140,
                      "producto_id": 815,
                      "cantidad": 4,
                      "monto": "25.00",
                      "created_at": "2020-05-25 15:49:05",
                      "updated_at": "2020-05-25 15:49:05",
                      "deleted_at": null,
                      "promocion": {
                        "id": 1140,
                        "activo": 1,
                        "nombre": "Compra 4 y recibe 25% de descuento",
                        "descripcion": "* 0001-4 AMOXILINA 500 MG C\/12 CAPSULAS",
                        "modo": "combinados",
                        "grupo": "G I FARMA",
                        "fabricante": "AMSA GI",
                        "started_at": "2020-05-25",
                        "finished_at": "2021-05-25",
                        "tipo_id": 7,
                        "created_at": "2020-05-25 15:49:05",
                        "updated_at": "2020-05-25 15:51:33",
                        "deleted_at": null
                      }
                    }
                  }
                ]
              }
            ]
          }
        }
        

  + Response 422 Unproccessable Entity


      {
        "productos": [
            "El campo productos es obligatorio."
        ],
        "cantidades": [
            "El campo cantidades es obligatorio."
        ],
        "player_id": [
            "El campo player id es obligatorio."
        ]
      }

**Actualiza Carritos**
----
Actualiza productos en carrito o añade elementos como user_id o pedido_id

 **URL**

    /api-v2/carritos/{id}

 **Headers**

      Accept: application/json
      Content-Type: application/x-www-form-urlencoded

 **Method:**

  `POST`

 ***Required:***

    'productos' => 'required|array',
    'cantidades' => 'required|array',
    'user_id'    => 'exists:users,id|nullable',
    'player_id'  => 'required',
    'search_id'  => 'nullable',
    'pedido_id'  => 'exists:pedidos,id|nullable'


  + Response 200 (application/json) Ejemplo:


         {
                  "carrito": {
                    "id": 14451,
                    "user_id": 17945,
                    "pedido_id": null,
                    "player_id": "11211",
                    "notificado": 0,
                    "activo": 1,
                    "created_at": "2019-08-20 11:33:44",
                    "updated_at": "2019-08-20 11:33:44",
                    "date_now": "2020-06-02 09:06:52",
                    "user": {
                      "id": 17945,
                      "name": "Pedido Prueba",
                      "last_name": "Omitir",
                      "second_last_name": null,
                      "telephone": "527772137826",
                      "clave": "PEOMYAZG",
                      "email": "luis@csgroup.mx",
                      "player_id": "45cbb662-097f-402f-afe2-47a072311d5b",
                      "tipo_usuario": null,
                      "activo": 1,
                      "baja": 0,
                      "fb_id": null,
                      "webhook_url": null,
                      "created_at": "2019-08-15 06:26:21",
                      "updated_at": "2019-08-16 06:34:21",
                      "deleted_at": null,
                      "last_login": null,
                      "cliente": {
                        "id": 17608,
                        "user_id": 17945,
                        "active": 1,
                        "deleted_at": null,
                        "created_at": "2019-08-15 06:26:21",
                        "updated_at": "2019-08-15 06:26:21",
                        "sexo": null,
                        "fecha_nacimiento": null,
                        "edad": null,
                        "imagen": null,
                        "imagen_path": null,
                        "zona_id": null,
                        "especial": 0,
                        "lat": null,
                        "lon": null,
                        "categoria_id": null
                      }
                    },
                    "productos": [
                      {
                        "id": 53736,
                        "carrito_id": 14451,
                        "lista_precio_id": 2878,
                        "cantidad": 2,
                        "created_at": "2019-08-20 11:33:44",
                        "updated_at": "2019-08-20 11:33:44",
                        "promocion": 0,
                        "beneficio_producto_id": null,
                        "lista_precio": {
                          "id": 2878,
                          "zona_id": 22,
                          "producto_id": 3967,
                          "precio": 325,
                          "created_at": "2017-06-22 12:18:52",
                          "updated_at": "2019-08-16 01:02:08",
                          "producto": {
                            "id": 3967,
                            "farmapronto_id": "004483",
                            "sku": "7501300408754",
                            "nombre": "DAXON 500MG C\/6 TABLETAS",
                            "descripcion": "",
                            "categoria": "ANTIPARASITOS",
                            "categoria_id": 0,
                            "laboratorio": "SIEGFRIED",
                            "receta": 0,
                            "clave": "DISPONIBLE",
                            "tipo": 299,
                            "activos": "NITAZOXANIDA",
                            "keywords": "Dacson, baxon, nitazoxanida, antiparasitos, amebiasis intestinal, disentiria amebiana, nematodos, cestodos, trematodos, tricominisis, antiparasitiario",
                            "destacado": 0,
                            "archivo": "uploads\/images\/productos\/7501300408754.png",
                            "created_at": "2017-03-16 11:49:23",
                            "updated_at": "2019-08-16 01:00:59",
                            "activo": 1,
                            "despliega": 1
                          }
                        },
                        "beneficio_promocion": null
                      },
                      {
                        "id": 53737,
                        "carrito_id": 14451,
                        "lista_precio_id": 2878,
                        "cantidad": 1,
                        "created_at": "2019-08-20 11:33:44",
                        "updated_at": "2019-08-20 11:33:44",
                        "promocion": 1,
                        "beneficio_producto_id": 3,
                        "lista_precio": {
                          "id": 2878,
                          "zona_id": 22,
                          "producto_id": 3967,
                          "precio": 325,
                          "created_at": "2017-06-22 12:18:52",
                          "updated_at": "2019-08-16 01:02:08",
                          "producto": {
                            "id": 3967,
                            "farmapronto_id": "004483",
                            "sku": "7501300408754",
                            "nombre": "DAXON 500MG C\/6 TABLETAS",
                            "descripcion": "",
                            "categoria": "ANTIPARASITOS",
                            "categoria_id": 0,
                            "laboratorio": "SIEGFRIED",
                            "receta": 0,
                            "clave": "DISPONIBLE",
                            "tipo": 299,
                            "activos": "NITAZOXANIDA",
                            "keywords": "Dacson, baxon, nitazoxanida, antiparasitos, amebiasis intestinal, disentiria amebiana, nematodos, cestodos, trematodos, tricominisis, antiparasitiario",
                            "destacado": 0,
                            "archivo": "uploads\/images\/productos\/7501300408754.png",
                            "created_at": "2017-03-16 11:49:23",
                            "updated_at": "2019-08-16 01:00:59",
                            "activo": 1,
                            "despliega": 1
                          }
                        },
                        "beneficio_promocion": {
                          "id": 3,
                          "sku_compra": "7501300408754",
                          "referencia": "MTCL_SIG",
                          "producto_compra_nombre": "DAXON 500MG GRAG C\/6",
                          "cantidad_compra": 3,
                          "sku_beneficio": "7501300408754",
                          "producto_beneficio_nombre": "DAXON 500MG GRAG C\/6",
                          "cantidad_beneficio": 1,
                          "vigencia_inicio": "2019-03-01",
                          "vigencia_fin": "2019-08-31",
                          "porcentaje_descuento": 0,
                          "tipo_porcentaje_descuento": 0,
                          "activo": 1,
                          "created_at": null,
                          "updated_at": null
                        }
                      }
                    ],
                    "pedido": null,
                    "productos_beneficios": [
                      {
                        "id": 53737,
                        "carrito_id": 14451,
                        "lista_precio_id": 2878,
                        "cantidad": 1,
                        "created_at": "2019-08-20 11:33:44",
                        "updated_at": "2019-08-20 11:33:44",
                        "promocion": 1,
                        "beneficio_producto_id": 3,
                        "lista_precio": {
                          "id": 2878,
                          "zona_id": 22,
                          "producto_id": 3967,
                          "precio": 325,
                          "created_at": "2017-06-22 12:18:52",
                          "updated_at": "2019-08-16 01:02:08",
                          "producto": {
                            "id": 3967,
                            "farmapronto_id": "004483",
                            "sku": "7501300408754",
                            "nombre": "DAXON 500MG C\/6 TABLETAS",
                            "descripcion": "",
                            "categoria": "ANTIPARASITOS",
                            "categoria_id": 0,
                            "laboratorio": "SIEGFRIED",
                            "receta": 0,
                            "clave": "DISPONIBLE",
                            "tipo": 299,
                            "activos": "NITAZOXANIDA",
                            "keywords": "Dacson, baxon, nitazoxanida, antiparasitos, amebiasis intestinal, disentiria amebiana, nematodos, cestodos, trematodos, tricominisis, antiparasitiario",
                            "destacado": 0,
                            "archivo": "uploads\/images\/productos\/7501300408754.png",
                            "created_at": "2017-03-16 11:49:23",
                            "updated_at": "2019-08-16 01:00:59",
                            "activo": 1,
                            "despliega": 1
                          }
                        }
                      }
                    ],
                    "productos_sin_beneficios": [
                      {
                        "id": 53736,
                        "carrito_id": 14451,
                        "lista_precio_id": 2878,
                        "cantidad": 2,
                        "created_at": "2019-08-20 11:33:44",
                        "updated_at": "2019-08-20 11:33:44",
                        "promocion": 0,
                        "beneficio_producto_id": null,
                        "lista_precio": {
                          "id": 2878,
                          "zona_id": 22,
                          "producto_id": 3967,
                          "precio": 325,
                          "created_at": "2017-06-22 12:18:52",
                          "updated_at": "2019-08-16 01:02:08",
                          "producto": {
                            "id": 3967,
                            "farmapronto_id": "004483",
                            "sku": "7501300408754",
                            "nombre": "DAXON 500MG C\/6 TABLETAS",
                            "descripcion": "",
                            "categoria": "ANTIPARASITOS",
                            "categoria_id": 0,
                            "laboratorio": "SIEGFRIED",
                            "receta": 0,
                            "clave": "DISPONIBLE",
                            "tipo": 299,
                            "activos": "NITAZOXANIDA",
                            "keywords": "Dacson, baxon, nitazoxanida, antiparasitos, amebiasis intestinal, disentiria amebiana, nematodos, cestodos, trematodos, tricominisis, antiparasitiario",
                            "destacado": 0,
                            "archivo": "uploads\/images\/productos\/7501300408754.png",
                            "created_at": "2017-03-16 11:49:23",
                            "updated_at": "2019-08-16 01:00:59",
                            "activo": 1,
                            "despliega": 1
                          }
                        }
                      }
                    ]
                  }
                }
                
                


  + Response 422 Unproccessable Entity


      {
        "productos": [
            "El campo productos es obligatorio."
        ],
        "cantidades": [
            "El campo cantidades es obligatorio."
        ],
        "player_id": [
            "El campo player id es obligatorio."
        ]
      }

**Detalle del Carrito**
----

 **URL**

    /api-v2/carritos/{id}

 **Headers**

      Accept: application/json

 **Method:**

  `GET`


  + Response 200 (application/json) Ejemplo:


        {
        	"carrito": {
        		"id": 3,
        		"user_id": 331,
        		"pedido_id": 2321,
        		"player_id": "PLAYER1",
        		"notificado": 0,
        		"activo": 1,
        		"created_at": "2018-09-20 16:26:16",
        		"updated_at": "2018-09-20 16:33:36",
        		"date_now": "2018-09-20 16:33:36",     
        		"user": {
        			"id": 331,
        			"name": "MINERVA",
        			"last_name": "JIMENEZ VIVEROS",
        			"second_last_name": "VIVEROS",
        			"telephone": "7774207068",
        			"email": "uno@uno.com",
        			"player_id": null,
        			"activo": 1,
        			"slack_webhook_url": null,
        			"created_at": "2018-04-10 14:37:31",
        			"updated_at": "2018-08-03 11:31:03",
        			"deleted_at": null,
        			"last_login": null,
        			"cliente": {
        				"id": 254,
        				"user_id": 331,
        				"active": 1,
        				"deleted_at": null,
        				"created_at": "2018-04-10 14:37:31",
        				"updated_at": "2018-04-10 14:37:31",
        				"sexo": null,
        				"fecha_nacimiento": null,
        				"edad": null,
        				"imagen": null,
        				"imagen_path": null,
        				"zona_id": null
        			}
        		},
        		"pedido": {
        			"id": 2321,
        			"user_id": 382,
        			"cliente_direccion_id": 2697,
        			"asistencia": 0,
        			"alerta_cliente": 0,
        			"folio": "ERP0002321",
        			"erp": 1,
        			"codigo_confirmacion": null,
        			"visto_callcenter": 1,
        			"created_at": "2018-04-30 19:55:22",
        			"updated_at": "2018-04-30 20:56:50",
        			"deleted_at": null
        		},
        		"productos": [
        			{
        				"id": 19,
        				"carrito_id": 3,
        				"lista_precio_id": 18498,
        				"cantidad": 2,
        				"created_at": "2018-09-20 16:35:28",
        				"updated_at": "2018-09-20 16:35:28",
        				"lista_precio": {
        					"id": 18498,
        					"zona_id": 22,
        					"producto_id": 45,
        					"precio": 46.5,
        					"created_at": "2017-07-05 17:16:18",
        					"updated_at": "2018-08-02 05:11:52",
        					"producto": {
        						"id": 45,
        						"farmapronto_id": "000046",
        						"sku": "7501017367962",
        						"nombre": "ABSORSEC ET G UNISEX C\/14",
        						"descripcion": "",
        						"categoria": "PANALES DESECHABLES",
        						"categoria_id": 0,
        						"laboratorio": "Bayer",
        						"receta": 0,
        						"clave": "SUJETO A DISPONIBILIDAD",
        						"tipo": 510,
        						"activos": "0",
        						"keywords": "",
        						"destacado": 0,
        						"archivo": null,
        						"created_at": "2017-03-16 17:49:19",
        						"updated_at": "2018-09-13 18:17:10",
        						"activo": 1,
        						"despliega": 1
        					}
        				}
        			}
        		]
        	}
        }

**Último carrito del usuario**
----
Regresa la información del último carrito del usuario logueado

 **URL**

    /api-v2/carritos/

 **Headers**

      Accept: application/json
      Autorization: Bearer TOKEN

 **Method:**

  `GET`


  + Response 200 (application/json) Ejemplo:


    {
        "carrito": {
            "id": 15,
            "user_id": 1934,
            "pedido_id": 2326,
            "player_id": "PLAYER1",
            "notificado": 0,
            "activo": 1,
            "created_at": "2018-09-20 18:58:04",
            "updated_at": "2018-09-20 18:58:04",
            "date_now": "2020-06-02 09:06:52",
            "user": {
                "id": 1934,
                "name": "Erick ",
                "last_name": "Brito",
                "second_last_name": "",
                "telephone": "527773274199",
                "email": "erick.dbrito@gmail.com",
                "player_id": "fb6c9eb3-4c9d-4774-aeca-0096f2613326",
                "activo": 0,
                "slack_webhook_url": null,
                "created_at": "2018-05-31 12:19:28",
                "updated_at": "2018-09-19 19:08:14",
                "deleted_at": null,
                "last_login": null,
                "cliente": {
                    "id": 1811,
                    "user_id": 1934,
                    "active": 1,
                    "deleted_at": null,
                    "created_at": "2018-05-31 12:19:28",
                    "updated_at": "2018-08-01 11:18:02",
                    "sexo": "masculino",
                    "fecha_nacimiento": "14\/10\/1988",
                    "edad": null,
                    "imagen": null,
                    "imagen_path": null,
                    "zona_id": null
                }
            },
            "pedido": {
                "id": 2326,
                "user_id": 229,
                "cliente_direccion_id": 2702,
                "asistencia": 0,
                "alerta_cliente": 0,
                "folio": "ERP0002326",
                "erp": 1,
                "codigo_confirmacion": null,
                "visto_callcenter": 1,
                "created_at": "2018-04-30 20:14:17",
                "updated_at": "2018-04-30 21:24:03",
                "deleted_at": null
            },
            "productos": [
                {
                    "id": 25,
                    "carrito_id": 15,
                    "lista_precio_id": 24,
                    "cantidad": 2,
                    "created_at": "2018-09-20 18:58:04",
                    "updated_at": "2018-09-20 18:58:04",
                    "lista_precio": {
                        "id": 24,
                        "zona_id": 22,
                        "producto_id": 30,
                        "precio": 35.5,
                        "created_at": "2017-06-22 16:50:09",
                        "updated_at": "2018-09-01 05:16:45",
                        "producto": {
                            "id": 30,
                            "farmapronto_id": "000034",
                            "sku": "7503001624693",
                            "nombre": "ABRILLANTADOR JAYLI SEDA LEMON 60ML",
                            "descripcion": "",
                            "categoria": "FIJADORES CABELLO",
                            "categoria_id": 0,
                            "laboratorio": "Bayer",
                            "receta": 0,
                            "clave": "SUJETO A DISPONIBILIDAD",
                            "tipo": 4,
                            "activos": "0",
                            "keywords": "",
                            "destacado": 0,
                            "archivo": null,
                            "created_at": "2017-03-16 17:49:19",
                            "updated_at": "2018-09-13 18:17:10",
                            "activo": 1,
                            "despliega": 1
                        }
                    }
                }
            ]
        }
    }
    
    
### Respuesta de plan de lealtad

#### Promocion producto gratis


```
ABSORSEC ETAPA JUMBO UNISEX C\/ 40 PANALES
producto_id: 54
cantidades: 1
```

**Response**


       {
          "carrito": {
            "id": 34424,
            "user_id": null,
            "pedido_id": null,
            "player_id": "34c1a047-9ad0-493e-b09d-30050b0cef30",
            "notificado": 0,
            "activo": 1,
            "created_at": "2020-06-04 23:40:21",
            "updated_at": "2020-06-04 23:40:21",
            "date_now": "2020-06-04 23:40:22",
            "productos": [
              {
                "id": 145044,
                "carrito_id": 34424,
                "lista_precio_id": 35800,
                "cantidad": 1,
                "total": "120.00",
                "created_at": "2020-06-04 23:40:22",
                "updated_at": "2020-06-04 23:40:22",
                "promocion": 0,
                "promocion_producto_id": null,
                "beneficio_producto_id": null,
                "beneficio_cliente_id": null,
                "tarjeta_cliente_id": null,
                "lista_precio": {
                  "id": 35800,
                  "zona_id": 165,
                  "producto_id": 54,
                  "precio": 120,
                  "created_at": "2020-05-18 14:22:28",
                  "updated_at": "2020-05-25 21:45:08",
                  "producto": {
                    "id": 54,
                    "farmapronto_id": "000051",
                    "sku": "7501017372775",
                    "nombre": "ABSORSEC ETAPA JUMBO UNISEX C\/ 40 PANALES",
                    "descripcion": "",
                    "categoria": "PANALES DESECHABLES",
                    "categoria_id": 123,
                    "laboratorio": "K CLARK",
                    "receta": 0,
                    "clave": "DISPONIBLE",
                    "tipo": 884,
                    "activos": "0",
                    "keywords": "",
                    "frecuencia": "0",
                    "contenido": "0",
                    "dosis": "0",
                    "tipoempaque": "JUMBO",
                    "temporada": "PANALES",
                    "destacado": 0,
                    "archivo": "uploads\/images\/productos\/7501017372775.png",
                    "created_at": "2017-03-16 11:49:19",
                    "updated_at": "2020-06-04 13:58:07",
                    "activo": 1,
                    "despliega": 1
                  }
                },
                "beneficio_promocion": null,
                "beneficio_cliente": null,
                "promociones": []
              },
              {
                "id": 145045,
                "carrito_id": 34424,
                "lista_precio_id": 30307,
                "cantidad": 0,
                "total": "0.01",
                "created_at": "2020-06-04 23:40:22",
                "updated_at": "2020-06-04 23:40:22",
                "promocion": 1,
                "promocion_producto_id": null,
                "beneficio_producto_id": 502,
                "beneficio_cliente_id": null,
                "tarjeta_cliente_id": null,
                "lista_precio": {
                  "id": 30307,
                  "zona_id": 22,
                  "producto_id": 60784,
                  "precio": 139.5,
                  "created_at": "2017-07-05 12:44:00",
                  "updated_at": "2020-05-25 22:11:45",
                  "producto": {
                    "id": 60784,
                    "farmapronto_id": "054083",
                    "sku": "054083",
                    "nombre": "PROMOCIONAL KIMBERLY CANJE",
                    "descripcion": "",
                    "categoria": "ACCESORIOS BEBES",
                    "categoria_id": 127,
                    "laboratorio": "K CLARK",
                    "receta": 0,
                    "clave": "SUJETO A DISPONIBILIDAD",
                    "tipo": 2416,
                    "activos": "0",
                    "keywords": "",
                    "frecuencia": "0",
                    "contenido": "0",
                    "dosis": "0",
                    "tipoempaque": "",
                    "temporada": "",
                    "destacado": 0,
                    "archivo": null,
                    "created_at": "2017-07-05 10:49:23",
                    "updated_at": "2020-06-04 13:59:30",
                    "activo": 1,
                    "despliega": 1
                  }
                },
                "beneficio_promocion": {
                  "id": 502,
                  "sku_compra": "7501017372775",
                  "referencia": "MTCL_KMC",
                  "producto_compra_nombre": "ABSORSEC ETAPA JUMBO UNISEX C\/ 40 PANALES",
                  "cantidad_compra": 1,
                  "sku_beneficio": "054083",
                  "producto_beneficio_nombre": "PROMOCIONAL KIMBERLY CANJE",
                  "cantidad_beneficio": 0,
                  "vigencia_inicio": "2019-06-10",
                  "vigencia_fin": "2020-07-31",
                  "porcentaje_descuento": 0,
                  "tipo_porcentaje_descuento": 0,
                  "activo": 1,
                  "created_at": "2020-06-04 20:54:12",
                  "updated_at": "2020-06-04 20:54:12",
                  "periodo_num_regalos": 5,
                  "periodo_dias": 30,
                  "periodo": "MENSUALES",
                  "tarjeta_tipo_id": 1,
                  "promocion_tipo_id": 2,
                  "descripcion": "Compra este producto + $20.00 y llevate promocional Kimberly Hasta Agotar existencias Max.5  APLICA RESTRICCIONES",
                  "producto_beneficio_id": 60784,
                  "producto_id": 54,
                  "tarjeta_farmapronto": 1,
                  "sustituto": 0,
                  "acumula": "1",
                  "proveedor": null
                },
                "beneficio_cliente": null,
                "promociones": []
              }
            ],
            "user": null,
            "pedido": null
          }
        }
        


```
ALEVIAN DUO 100 MG / 300 MG CAPS C/64
producto_id: 564
cantidades: 3

3+1 T.FARMAPRONTO. CANJES PERMITIDOS: 3 ANUALES. VIGENCIA 31/07/2020. APLICAN RESTRICCIONES
```



        {
          "carrito": {
            "id": 34425,
            "user_id": null,
            "pedido_id": null,
            "player_id": "34c1a047-9ad0-493e-b09d-30050b0cef30",
            "notificado": 0,
            "activo": 1,
            "created_at": "2020-06-04 23:41:18",
            "updated_at": "2020-06-04 23:41:18",
            "date_now": "2020-06-04 23:41:19",
            "productos": [
              {
                "id": 145046,
                "carrito_id": 34425,
                "lista_precio_id": 84720,
                "cantidad": 3,
                "total": "2848.50",
                "created_at": "2020-06-04 23:41:19",
                "updated_at": "2020-06-04 23:41:19",
                "promocion": 0,
                "promocion_producto_id": null,
                "beneficio_producto_id": null,
                "beneficio_cliente_id": null,
                "tarjeta_cliente_id": null,
                "lista_precio": {
                  "id": 84720,
                  "zona_id": 165,
                  "producto_id": 564,
                  "precio": 949.5,
                  "created_at": "2020-05-18 14:24:05",
                  "updated_at": "2020-05-25 21:45:09",
                  "producto": {
                    "id": 564,
                    "farmapronto_id": "000629",
                    "sku": "7501092777229",
                    "nombre": "ALEVIAN DUO 100 MG \/ 300 MG CAPS C\/64",
                    "descripcion": "",
                    "categoria": "DIGESTIVO Y METABOLISMO",
                    "categoria_id": 122,
                    "laboratorio": "TAKEDA NYC",
                    "receta": 0,
                    "clave": "SUJETO A DISPONIBILIDAD",
                    "tipo": 28,
                    "activos": "BROMURO DE PINAVERIO \/ DIMETICONA",
                    "keywords": "",
                    "frecuencia": "21",
                    "contenido": "64",
                    "dosis": "3",
                    "tipoempaque": "",
                    "temporada": "",
                    "destacado": 0,
                    "archivo": null,
                    "created_at": "2017-03-16 11:49:20",
                    "updated_at": "2020-06-04 13:58:08",
                    "activo": 0,
                    "despliega": 0
                  }
                },
                "beneficio_promocion": null,
                "beneficio_cliente": null,
                "promociones": []
              },
              {
                "id": 145047,
                "carrito_id": 34425,
                "lista_precio_id": 393,
                "cantidad": 1,
                "total": "0.01",
                "created_at": "2020-06-04 23:41:19",
                "updated_at": "2020-06-04 23:41:19",
                "promocion": 1,
                "promocion_producto_id": null,
                "beneficio_producto_id": 106,
                "beneficio_cliente_id": null,
                "tarjeta_cliente_id": null,
                "lista_precio": {
                  "id": 393,
                  "zona_id": 22,
                  "producto_id": 564,
                  "precio": 876.5,
                  "created_at": "2017-06-22 11:53:55",
                  "updated_at": "2020-06-04 13:59:51",
                  "producto": {
                    "id": 564,
                    "farmapronto_id": "000629",
                    "sku": "7501092777229",
                    "nombre": "ALEVIAN DUO 100 MG \/ 300 MG CAPS C\/64",
                    "descripcion": "",
                    "categoria": "DIGESTIVO Y METABOLISMO",
                    "categoria_id": 122,
                    "laboratorio": "TAKEDA NYC",
                    "receta": 0,
                    "clave": "SUJETO A DISPONIBILIDAD",
                    "tipo": 28,
                    "activos": "BROMURO DE PINAVERIO \/ DIMETICONA",
                    "keywords": "",
                    "frecuencia": "21",
                    "contenido": "64",
                    "dosis": "3",
                    "tipoempaque": "",
                    "temporada": "",
                    "destacado": 0,
                    "archivo": null,
                    "created_at": "2017-03-16 11:49:20",
                    "updated_at": "2020-06-04 13:58:08",
                    "activo": 0,
                    "despliega": 0
                  }
                },
                "beneficio_promocion": {
                  "id": 106,
                  "sku_compra": "7501092777229",
                  "referencia": "CDSORO",
                  "producto_compra_nombre": "ALEVIAN DUO 100 MG \/ 300 MG CAPS C\/64",
                  "cantidad_compra": 3,
                  "sku_beneficio": "7501092777229",
                  "producto_beneficio_nombre": "ALEVIAN DUO 100 MG \/ 300 MG CAPS C\/64",
                  "cantidad_beneficio": 1,
                  "vigencia_inicio": "2020-02-03",
                  "vigencia_fin": "2020-07-31",
                  "porcentaje_descuento": 0,
                  "tipo_porcentaje_descuento": 0,
                  "activo": 1,
                  "created_at": "2020-06-04 20:54:10",
                  "updated_at": "2020-06-04 20:54:10",
                  "periodo_num_regalos": 3,
                  "periodo_dias": 365,
                  "periodo": "ANUALES",
                  "tarjeta_tipo_id": 2,
                  "promocion_tipo_id": 2,
                  "descripcion": "3+1 T.FARMAPRONTO. CANJES PERMITIDOS: 3 ANUALES. VIGENCIA 31\/07\/2020. APLICAN RESTRICCIONES",
                  "producto_beneficio_id": 564,
                  "producto_id": 564,
                  "tarjeta_farmapronto": 0,
                  "sustituto": 0,
                  "acumula": "1",
                  "proveedor": null
                },
                "beneficio_cliente": null,
                "promociones": []
              }
            ],
            "user": null,
            "pedido": null
          }
        }
        
        


```
AVENE TOQUE SECO C\/ COLOR 50 ML FPS 50 BLOQUEADOproducto_id: 564
cantidades: 1
producto_id: 40917

Politica de Precio: 25% desc. + T.Farmapronto y  gratis AGUA THERMAL AVENE SPRAY 50 ML (3282770505320) Vigencia: 31\/07\/2020, Canjes: 10 Mensuales, APLICAN RESTRICCIONE
```



       {
          "carrito": {
            "id": 34439,
            "user_id": null,
            "pedido_id": null,
            "player_id": "34c1a047-9ad0-493e-b09d-30050b0cef30",
            "notificado": 0,
            "activo": 1,
            "created_at": "2020-06-05 00:04:01",
            "updated_at": "2020-06-05 00:04:01",
            "date_now": "2020-06-05 00:04:01",
            "productos": [
              {
                "id": 145071,
                "carrito_id": 34439,
                "lista_precio_id": 122778,
                "cantidad": 1,
                "total": "245.25",
                "created_at": "2020-06-05 00:04:01",
                "updated_at": "2020-06-05 00:04:01",
                "promocion": 1,
                "promocion_producto_id": null,
                "beneficio_producto_id": 715,
                "beneficio_cliente_id": null,
                "tarjeta_cliente_id": null,
                "lista_precio": {
                  "id": 122778,
                  "zona_id": 165,
                  "producto_id": 40917,
                  "precio": 327,
                  "created_at": "2020-05-18 14:25:30",
                  "updated_at": "2020-05-25 21:46:54",
                  "producto": {
                    "id": 40917,
                    "farmapronto_id": "044412",
                    "sku": "3282779391580",
                    "nombre": "AVENE TOQUE SECO C\/ COLOR 50 ML FPS 50 BLOQUEADOR",
                    "descripcion": "",
                    "categoria": "BRONCEADORES Y BLOQUEADORES PIEL",
                    "categoria_id": 154,
                    "laboratorio": "FABRE",
                    "receta": 0,
                    "clave": "DISPONIBLE",
                    "tipo": 48,
                    "activos": "0",
                    "keywords": "",
                    "frecuencia": "0",
                    "contenido": "0",
                    "dosis": "0",
                    "tipoempaque": "",
                    "temporada": "BLOQUEADOR",
                    "destacado": 0,
                    "archivo": null,
                    "created_at": "2017-03-16 11:49:57",
                    "updated_at": "2020-06-04 13:59:14",
                    "activo": 1,
                    "despliega": 1
                  }
                },
                "beneficio_promocion": {
                  "id": 715,
                  "sku_compra": "3282779391580",
                  "referencia": "MTCL_PFB",
                  "producto_compra_nombre": "AVENE TOQUE SECO C\/ COLOR 50 ML FPS 50 BLOQUEADOR",
                  "cantidad_compra": 1,
                  "sku_beneficio": "3282770505320",
                  "producto_beneficio_nombre": "AVENE SPRAY 50 ML AGUA TERMAL",
                  "cantidad_beneficio": 0,
                  "vigencia_inicio": "2020-06-01",
                  "vigencia_fin": "2020-07-31",
                  "porcentaje_descuento": 25,
                  "tipo_porcentaje_descuento": 1,
                  "activo": 1,
                  "created_at": "2020-06-04 20:54:12",
                  "updated_at": "2020-06-04 23:51:20",
                  "periodo_num_regalos": 10,
                  "periodo_dias": 30,
                  "periodo": "MENSUALES",
                  "tarjeta_tipo_id": 96,
                  "promocion_tipo_id": 5,
                  "descripcion": "Politica de Precio: 25% desc. + T.Farmapronto y  gratis AGUA THERMAL AVENE SPRAY 50 ML (3282770505320) Vigencia: 31\/07\/2020, Canjes: 10 Mensuales, APLICAN RESTRICCIONES",
                  "producto_beneficio_id": 1258,
                  "producto_id": 40917,
                  "tarjeta_farmapronto": 0,
                  "sustituto": 1,
                  "acumula": "1",
                  "proveedor": null
                },
                "beneficio_cliente": null,
                "promociones": []
              },
              {
                "id": 145072,
                "carrito_id": 34439,
                "lista_precio_id": 903,
                "cantidad": 0,
                "total": "0.01",
                "created_at": "2020-06-05 00:04:01",
                "updated_at": "2020-06-05 00:04:01",
                "promocion": 1,
                "promocion_producto_id": null,
                "beneficio_producto_id": 715,
                "beneficio_cliente_id": null,
                "tarjeta_cliente_id": null,
                "lista_precio": {
                  "id": 903,
                  "zona_id": 22,
                  "producto_id": 1258,
                  "precio": 88,
                  "created_at": "2017-06-22 11:59:01",
                  "updated_at": "2020-06-04 13:59:51",
                  "producto": {
                    "id": 1258,
                    "farmapronto_id": "001427",
                    "sku": "3282770505320",
                    "nombre": "AVENE SPRAY 50 ML AGUA TERMAL",
                    "descripcion": "",
                    "categoria": "DERMATOLOGICOS",
                    "categoria_id": 124,
                    "laboratorio": "FABRE",
                    "receta": 0,
                    "clave": "DISPONIBLE",
                    "tipo": 38,
                    "activos": "AGUA TERMAL",
                    "keywords": "",
                    "frecuencia": "0",
                    "contenido": "0",
                    "dosis": "0",
                    "tipoempaque": "",
                    "temporada": "AGUA THERMAL",
                    "destacado": 0,
                    "archivo": null,
                    "created_at": "2017-03-16 11:49:20",
                    "updated_at": "2020-06-04 13:58:11",
                    "activo": 1,
                    "despliega": 1
                  }
                },
                "beneficio_promocion": {
                  "id": 715,
                  "sku_compra": "3282779391580",
                  "referencia": "MTCL_PFB",
                  "producto_compra_nombre": "AVENE TOQUE SECO C\/ COLOR 50 ML FPS 50 BLOQUEADOR",
                  "cantidad_compra": 1,
                  "sku_beneficio": "3282770505320",
                  "producto_beneficio_nombre": "AVENE SPRAY 50 ML AGUA TERMAL",
                  "cantidad_beneficio": 0,
                  "vigencia_inicio": "2020-06-01",
                  "vigencia_fin": "2020-07-31",
                  "porcentaje_descuento": 25,
                  "tipo_porcentaje_descuento": 1,
                  "activo": 1,
                  "created_at": "2020-06-04 20:54:12",
                  "updated_at": "2020-06-04 23:51:20",
                  "periodo_num_regalos": 10,
                  "periodo_dias": 30,
                  "periodo": "MENSUALES",
                  "tarjeta_tipo_id": 96,
                  "promocion_tipo_id": 5,
                  "descripcion": "Politica de Precio: 25% desc. + T.Farmapronto y  gratis AGUA THERMAL AVENE SPRAY 50 ML (3282770505320) Vigencia: 31\/07\/2020, Canjes: 10 Mensuales, APLICAN RESTRICCIONES",
                  "producto_beneficio_id": 1258,
                  "producto_id": 40917,
                  "tarjeta_farmapronto": 0,
                  "sustituto": 1,
                  "acumula": "1",
                  "proveedor": null
                },
                "beneficio_cliente": null,
                "promociones": []
              }
            ],
            "user": null,
            "pedido": null
          }
        }