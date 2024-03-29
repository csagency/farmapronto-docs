      
## Listado de categorias FP
Regresa el listado del catálogo de Categorías FP

 **URL**

  /api/catalogos/categoriasFP

 **Method:**

  `GET`

**Success Response:**

* **Code:** 200 <br />
  **Content:** 
  
      {
        "categoriasFP": [
            {
              "id": 1,
              "nombre": "Categoría especial",
              "descripcion": "Especial de primavera",
              "imagen": null,
              "activo": 1,
              "created_at": null,
              "updated_at": null,
              "deleted_at": null,
              "productos": [
                {
                  "id": 1,
                  "producto_id": 1,
                  "categoria_fp_id": 1,
                  "created_at": null,
                  "updated_at": null,
                  "deleted_at": null
                }
              ]
            }
        ]
      }

 
**Datos de una categoría FP**
----
  Regresa la información de una categoría FP en específico y sus relaciones

 **URL**

  /api/catalogos/categoriasFP/ID

 **Method:**

  `GET`
      
  **URL Params**

  Ejemplo URI: `api/catalogos/catalogos/categoriasFP/1
  

 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 

        {
        	"categoriaFP": {
        		"id": 2,
        		"nombre": "Botiquin",
        		"descripcion": "Botiquin",
        		"imagen": "uploads\/images\/imagen-categoria.png",
        		"activo": 1,
        		"created_at": "2017-06-09 13:54:47",
        		"updated_at": "2017-06-09 13:54:47",
        		"deleted_at": null,
        		"productos_fp": [
        			{
        				"id": 576,
        				"farmapronto_id": "000645",
        				"sku": "7501048620906",
        				"nombre": "ALGODON DEGASA PROT PLISADO 100GR",
        				"descripcion": "ALGODON DEGASA PROT PLISADO 100GR",
        				"categoria": "ALGODON,GASAS,VENDAS Y ADHESIVOS",
        				"categoria_id": 0,
        				"laboratorio": "Bayer",
        				"receta": 0,
        				"clave": "DISPONIBLE",
        				"tipo": 5,
        				"activos": "0",
        				"destacado": 0,
        				"archivo": null,
        				"created_at": "2017-03-16 17:49:20",
        				"updated_at": "2017-11-01 06:31:21",
        				"activo": 1,
        				"pivot": {
        					"categoria_fp_id": 2,
        					"producto_id": 576
        				},
        				"lista_precios": [
        					{
        						"id": 402,
        						"zona_id": 22,
        						"producto_id": 576,
        						"precio": 34,
        						"created_at": "2017-06-22 16:54:00",
        						"updated_at": "2017-07-21 12:58:16"
        					}
        				]
        			}
        		]
        	}
        }