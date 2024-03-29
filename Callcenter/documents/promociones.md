**Promociones**
----

 **URL**

    /api/promociones

 **Method:**

  `GET`
  
  + Response 200 (application/json) Ejemplo:
  

        {
            "promociones": [
                {
                    "id": 1,
                    "activo": 1,
                    "nombre": "Promoción tampones tampax",
                    "descripcion": "Gratis 12",
                    "tipo_id": 1,
                    "created_at": "2018-09-10 15:00:47",
                    "updated_at": "2018-09-10 15:00:47",
                    "deleted_at": null,
                    "productos": [
                        {
                            "id": 1,
                            "promocion_id": 1,
                            "producto_id": 56006,
                            "cantidad": 12,
                            "created_at": "2018-09-10 15:00:47",
                            "updated_at": "2018-09-10 15:00:47",
                            "deleted_at": null,
                            "producto": {
                                "id": 56006,
                                "farmapronto_id": "013260",
                                "sku": "020800600330",
                                "nombre": "TAMPONES TAMPAX SUPER C\/10",
                                "descripcion": "TAMPONES TAMPAX SUPER C\/10",
                                "categoria": "PROTECCION FEMENINA",
                                "categoria_id": 0,
                                "laboratorio": null,
                                "receta": 0,
                                "clave": "SUJETO A DISPONIBILIDAD",
                                "tipo": 9,
                                "activos": "0",
                                "keywords": "",
                                "destacado": 0,
                                "archivo": null,
                                "created_at": "2017-07-05 15:23:26",
                                "updated_at": "2018-09-10 05:01:50",
                                "activo": 1,
                                "despliega": 1
                            }
                        }
                    ],
                    "tipo": {
                        "id": 1,
                        "nombre": "gratis",
                        "created_at": "2018-09-10 15:00:47",
                        "updated_at": "2018-09-10 15:00:47"
                    }
                }
            ]
        }