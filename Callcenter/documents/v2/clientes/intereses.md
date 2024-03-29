
## Catálogo de intereses [/api/catalogos/intereses]

### Obtener intereses [GET]


+ Request (application/json)


+ Response 200 (application/json)

    + Body
            
            {
              "intereses": [
                {
                  "id": 4,
                  "titulo": "Bebés",
                  "key": "bebes",
                  "created_at": "2018-08-17 07:51:38",
                  "updated_at": "2018-08-17 07:51:38",
                  "deleted_at": null
                },
                {
                  "id": 5,
                  "titulo": "Dermatológicos",
                  "key": "dermatologicos",
                  "created_at": "2018-08-17 07:52:09",
                  "updated_at": "2018-08-17 07:52:09",
                  "deleted_at": null
                },
                {
                  "id": 6,
                  "titulo": "Naturismo",
                  "key": "naturismo",
                  "created_at": "2018-08-17 07:55:57",
                  "updated_at": "2018-08-17 07:55:57",
                  "deleted_at": null
                },
                {
                  "id": 7,
                  "titulo": "Vitaminas y Suplementos",
                  "key": "vitaminas-y-suplementos",
                  "created_at": "2018-08-17 07:57:49",
                  "updated_at": "2018-08-17 07:57:49",
                  "deleted_at": null
                },
                {
                  "id": 8,
                  "titulo": "Diabetes",
                  "key": "diabetes",
                  "created_at": "2018-08-17 07:58:15",
                  "updated_at": "2018-08-17 07:58:15",
                  "deleted_at": null
                },
                {
                  "id": 9,
                  "titulo": "Hipertensión",
                  "key": "hipertension",
                  "created_at": "2018-08-17 07:58:32",
                  "updated_at": "2018-08-17 07:58:32",
                  "deleted_at": null
                },
                {
                  "id": 10,
                  "titulo": "Higiene Personal",
                  "key": "higiene-personal",
                  "created_at": "2018-08-17 07:59:05",
                  "updated_at": "2018-08-17 07:59:05",
                  "deleted_at": null
                },
                {
                  "id": 11,
                  "titulo": "Ortopedia",
                  "key": "ortopedia",
                  "created_at": "2018-08-17 07:59:19",
                  "updated_at": "2018-08-17 07:59:19",
                  "deleted_at": null
                }
              ],
              "intereses_farmatips": [
                {
                  "id": 1,
                  "nombre": "Diabetes",
                  "created_at": null,
                  "updated_at": null,
                  "deleted_at": null
                },
                {
                  "id": 2,
                  "nombre": "Hipertensión",
                  "created_at": null,
                  "updated_at": null,
                  "deleted_at": null
                },
                {
                  "id": 3,
                  "nombre": "Salud",
                  "created_at": null,
                  "updated_at": null,
                  "deleted_at": null
                }
              ]
            }


## Intereses clientes [/api-v2/clientes/me/intereses]

### Obtener intereses [GET]


    + Headers
        Authorization: Bearer {TOKEN}


+ Request (application/json)


+ Response 200 (application/json)

    + Body
            
            {
              "intereses": [
                {
                  "id": 5,
                  "titulo": "Dermatológicos",
                  "key": "dermatologicos",
                  "created_at": "2018-08-17 07:52:09",
                  "updated_at": "2018-08-17 07:52:09",
                  "deleted_at": null,
                  "pivot": {
                    "user_id": 8843,
                    "catalogo_interes_id": 5,
                    "type": "intereses",
                    "created_at": "2020-06-19 17:05:15",
                    "updated_at": "2020-06-19 17:05:15"
                  }
                }
              ],
              "intereses_farmatips": [
                {
                  "id": 1,
                  "nombre": "Diabetes",
                  "created_at": null,
                  "updated_at": null,
                  "deleted_at": null,
                  "pivot": {
                    "user_id": 8843,
                    "categoria_farmatip_id": 1,
                    "type": null,
                    "created_at": "2020-06-19 16:41:04",
                    "updated_at": "2020-06-19 16:41:04"
                  }
                },
                {
                  "id": 2,
                  "nombre": "Hipertensión",
                  "created_at": null,
                  "updated_at": null,
                  "deleted_at": null,
                  "pivot": {
                    "user_id": 8843,
                    "categoria_farmatip_id": 2,
                    "type": null,
                    "created_at": "2020-06-19 16:41:04",
                    "updated_at": "2020-06-19 16:41:04"
                  }
                }
              ]
            }


### Registrar intereses [POST]


    + Headers
        Authorization: Bearer {TOKEN}


+ Request (application/json)
    
    + Attributes
        - intereses(array) - 5
        - intereses_farmatips(array) - 1


+ Response 200 (application/json)

    + Body
            
            {
              "intereses": [
                {
                  "id": 5,
                  "titulo": "Dermatológicos",
                  "key": "dermatologicos",
                  "created_at": "2018-08-17 07:52:09",
                  "updated_at": "2018-08-17 07:52:09",
                  "deleted_at": null,
                  "pivot": {
                    "user_id": 8843,
                    "catalogo_interes_id": 5,
                    "type": "intereses",
                    "created_at": "2020-06-19 17:05:15",
                    "updated_at": "2020-06-19 17:05:15"
                  }
                }
              ],
              "intereses_farmatips": [
                {
                  "id": 1,
                  "nombre": "Diabetes",
                  "created_at": null,
                  "updated_at": null,
                  "deleted_at": null,
                  "pivot": {
                    "user_id": 8843,
                    "categoria_farmatip_id": 1,
                    "type": null,
                    "created_at": "2020-06-19 16:41:04",
                    "updated_at": "2020-06-19 16:41:04"
                  }
                },
                {
                  "id": 2,
                  "nombre": "Hipertensión",
                  "created_at": null,
                  "updated_at": null,
                  "deleted_at": null,
                  "pivot": {
                    "user_id": 8843,
                    "categoria_farmatip_id": 2,
                    "type": null,
                    "created_at": "2020-06-19 16:41:04",
                    "updated_at": "2020-06-19 16:41:04"
                  }
                }
              ]
            }
