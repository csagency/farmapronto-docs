**Almacena Carritos**
----
Almacena productos en carrito


 **URL**

    /api/carritos

 **Headers**

      Accept: application/json

 **Method:**

  `POST`

 ***Required:***

    'productos' => 'required|array',
    'cantidades' => 'required|array',
    'user_id'    => 'exists:users,id|nullable',
    'player_id'  => 'required'
    'pedido_id'  => 'exists:pedidos,id|nullable'
    'search_id'  => 'nullable'



  + Response 200 (application/json) Ejemplo:


        {
          "carrito": {
            "id": 20489,
            "user_id": 8843,
            "pedido_id": null,
            "player_id": "11211",
            "notificado": 0,
            "activo": 1,
            "created_at": "2019-11-12 19:26:20",
            "updated_at": "2019-11-12 19:26:20",
            "productos": [
              {
                "id": 78870,
                "carrito_id": 20489,
                "lista_precio_id": 32564,
                "cantidad": 3,
                "created_at": "2019-11-12 19:26:20",
                "updated_at": "2019-11-12 19:26:20",
                "promocion": 0,
                "beneficio_producto_id": 1138,
                "beneficio_cliente_id": null,
                "tarjeta_cliente_id": 1,
                "lista_precio": {
                  "id": 32564,
                  "zona_id": 22,
                  "producto_id": 63181,
                  "precio": 1195,
                  "created_at": "2018-04-26 07:35:51",
                  "updated_at": "2019-02-01 05:35:49",
                  "producto": {
                    "id": 63181,
                    "farmapronto_id": "056288",
                    "sku": "7501249601674",
                    "nombre": "MOVUREN 500 MG \/ 60",
                    "descripcion": "",
                    "categoria": "SISTEMA CARDIOVASCULAR",
                    "categoria_id": 0,
                    "laboratorio": "IFA",
                    "receta": 0,
                    "clave": "DISPONIBLE",
                    "tipo": 3,
                    "activos": "LEVETIRACETAM",
                    "keywords": "",
                    "destacado": 0,
                    "archivo": "uploads\/images\/productos\/7501249601674.png",
                    "created_at": "2018-04-26 06:57:37",
                    "updated_at": "2019-11-07 06:02:13",
                    "activo": 1,
                    "despliega": 1
                  }
                },
                "beneficio_promocion": {
                  "id": 1138,
                  "sku_compra": "7501249601674",
                  "referencia": "MTCL_IFA",
                  "producto_compra_nombre": "MOVUREN 500 MG \/ 60",
                  "cantidad_compra": 3,
                  "sku_beneficio": "7501249601674",
                  "producto_beneficio_nombre": "MOVUREN 500 MG \/ 60",
                  "cantidad_beneficio": 1,
                  "vigencia_inicio": "2018-06-30",
                  "vigencia_fin": "2019-12-31",
                  "porcentaje_descuento": 0,
                  "tipo_porcentaje_descuento": 0,
                  "activo": 1,
                  "created_at": "2019-11-11 17:20:47",
                  "updated_at": "2019-11-11 17:20:47",
                  "periodo_num_regalos": 10,
                  "periodo_dias": null,
                  "periodo": 0,
                  "tarjeta_tipo_id": 26,
                  "promocion_tipo_id": 2,
                  "tarjeta_farmapronto": 1
                },
                "beneficio_cliente": null
              }
            ],
            "user": {
              "id": 8843,
              "name": "PEDIDOS PRUEBA",
              "last_name": "NO HACER CASO No",
              "second_last_name": null,
              "telephone": "527773274199",
              "clave": "ERBRIPU6",
              "email": "erick.dbrito@gmail.com",
              "player_id": "de69c47d-67a4-4c58-8a34-2140577da7b4",
              "tipo_usuario": null,
              "activo": 1,
              "baja": 0,
              "fb_id": null,
              "webhook_url": null,
              "created_at": "2018-10-29 17:13:36",
              "updated_at": "2019-09-12 16:47:56",
              "deleted_at": null,
              "last_login": null,
              "cliente": {
                "id": 8650,
                "user_id": 8843,
                "active": 1,
                "deleted_at": null,
                "created_at": "2018-10-29 17:13:36",
                "updated_at": "2019-02-12 09:29:58",
                "sexo": null,
                "fecha_nacimiento": null,
                "edad": null,
                "imagen": null,
                "imagen_path": null,
                "zona_id": null,
                "especial": 0,
                "lat": "18.936158100000004",
                "lon": "-99.23029149999999",
                "categoria_id": null
              }
            },
            "pedido": null
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

    /api/carritos/{id}

 **Headers**

      Accept: application/json
      Content-Type: application/x-www-form-urlencoded

 **Method:**

  `PUT`

 ***Required:***

    'productos' => 'required|array',
    'cantidades' => 'required|array',
    'user_id'    => 'exists:users,id|nullable',
    'player_id'  => 'required'
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

    /api/carritos/{id}

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

 **URL**

    /api/carritos/

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