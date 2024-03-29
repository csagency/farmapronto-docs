# API CR Productos


## Carga delta de productos.

Carga delta para activar productos.


### Requesting Token [POST]

+ Request (application/json)

      {
        "productos":[
            {
                "farmapronto_id":"005934",
                "sku":"7501086800018",
                "nombre":"EPURA AGUA C/CHUPON 1 LITRO",
                "descripcion":"",
                "categoria":"AGUAS",
                "laboratorio":"PEPSI",
                "receta":"0"
            }
        ]
      }

+ Response 200 (application/json)

    + Body

            {
                "messageSucces": "proceso de carga delta de productos ejecutado con éxito"
            }

+ Response 422 (application/json)
    + Body


            {
                  "errors": {
                    "productos.0.farmapronto_id": [
                        "El campo productos.0.farmapronto_id es obligatorio."
                    ],
                    "productos.0.sku": [
                        "El campo productos.0.sku es obligatorio."
                    ],
                    "productos.0.nombre": [
                        "El campo productos.0.nombre es obligatorio."
                    ],
                    "productos.0.receta": [
                        "El campo productos.0.receta es obligatorio."
                    ]
                }
            }


+ Response 406 (application/json)
    + Body


            {
              "error": "Formato json invalido"
            }
+ 
+ Response 500 (application/json)
    + Body


            {
              "message": "Error de proceso de carga delta de productos"
            }
            

