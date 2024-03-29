
**Búsqueda de productos**
----
  Realiza busqueda de productos

 **URL**

  /api/productos

 **Method:**

  `GET`
  
  **URL Params**

  - includes[]=userCliente, userDirecciones, userPedidos, userPlanes  <br><br>
  - Ejemplo URI: 
       - `/api/productos?nombre=aspirina` - Mostrara los más relevantes 
  - Ejemplo URI: 
       - `/api/productos?nombre=aspirina&order=desc`  - Mostrara productos con precio desendente
  - Ejemplo URI: 
       - `/api/productos?nombre=aspirina&order=asc` - Mostrara productos con precio ascendente
  


 **- Añadir `user_id` al request para añadir la consulta del request al historico de búsquedas del usuarios**


     
        Ej.  api/productos?nombre=Paracetamol 500&user_id=6022
     

**- Añadir `sucursal_id` al request para añadir la consulta del request al historico de búsquedas de la sucursal**


     
        Ej.  api/productos?nombre=Paracetamol 500&user_id=6022&sucursal_id=24

**Filtro por cobertura de zonas**

   Añadir en el request el siguiente valor  `ciudad_cobertura_id` para obtener la cobertura en la zona del producto. Ej.

    `/api/productos?ciudad_cobertura_id=1&nombre=paracetamol`



   Para conocer la disponibilidad usar la  includes[]=ciudadesCobertura`



 **Success Response:**


  * **Code:** 200 <br />


   **Content:** 


  - Ejemplo URI: `/api/productos?nombre=aspirina` - Mostrara por defecto los productos más relevantes 


        {
          "productos": [
            {
              "id": 64400,
              "farmapronto_id": "057639",
              "sku": "7501109789306",
              "nombre": "MPO PARACETAMOL 500 MG C\/10 TAB",
              "descripcion": "",
              "categoria": "SISTEMA NERVIOSO",
              "categoria_id": 0,
              "laboratorio": "QUIFA",
              "receta": 0,
              "clave": "SUJETO A DISPONIBILIDAD",
              "tipo": 2405,
              "activos": "PARACETAMOL",
              "keywords": "",
              "destacado": 0,
              "archivo": "uploads\/images\/productos\/7501109789306.png",
              "created_at": "2018-12-25 05:08:18",
              "updated_at": "2019-09-02 06:01:42",
              "activo": 1,
              "despliega": 1,
              "user_busqueda_producto_count": 112,
              "user_busqueda_producto_interesado_count": 2,
              "lista_precios": [
                {
                  "id": 33738,
                  "zona_id": 22,
                  "producto_id": 64400,
                  "precio": 20,
                  "created_at": "2018-12-25 05:34:52",
                  "updated_at": "2018-12-28 05:30:05"
                }
              ]
            },
          "info": [
            {
              "search_id": 165309,
              "total": 175
            }
          ]
        }
 
   - Ejemplo URI: `/api/productos?nombre=aspirina&order=desc`  - Mostrara los productos con precio desendente


        {
            "productos": [
                {
                    "id": 56378,
                    "farmapronto_id": "017283",
                    "sku": "017283",
                    "nombre": "VS ASPIRINA EFERV TAB C\/2",
                    "descripcion": "VS ASPIRINA EFERV TAB C\/2",
                    "categoria": "SISTEMA NERVIOSO",
                    "categoria_id": 0,
                    "laboratorio": null,
                    "receta": 0,
                    "clave": "Disponible",
                    "tipo": 98,
                    "activos": "ACIDO ACETILSALICILICO",
                    "destacado": 0,
                    "archivo": null,
                    "created_at": "2017-07-05 15:24:59",
                    "updated_at": "2017-07-14 13:04:17",
                    "activo": 1,
                    "lista_precios": [
                        {
                            "id": 21312,
                            "zona_id": 22,
                            "producto_id": 56378,
                            "precio": 5,
                            "created_at": "2017-07-05 17:28:23",
                            "updated_at": "2017-07-05 17:28:23"
                        }
                    ]
                },
                {
                    "id": 15705,
                    "farmapronto_id": "017282",
                    "sku": "75031381",
                    "nombre": "VS ASPIRINA 500MG TAB C\/10",
                    "descripcion": "VS ASPIRINA 500MG TAB C\/10",
                    "categoria": "SISTEMA NERVIOSO",
                    "categoria_id": 0,
                    "laboratorio": "Bayer",
                    "receta": 0,
                    "clave": "Disponible",
                    "tipo": 49,
                    "activos": "ACIDO ACETILSALICILICO",
                    "destacado": 0,
                    "archivo": null,
                    "created_at": "2017-03-16 17:49:33",
                    "updated_at": "2017-07-14 13:04:17",
                    "activo": 1,
                    "lista_precios": [
                        {
                            "id": 21310,
                            "zona_id": 22,
                            "producto_id": 15705,
                            "precio": 8,
                            "created_at": "2017-07-05 17:28:23",
                            "updated_at": "2017-07-05 17:28:23"
                        }
                    ]
                },
                {
                    "id": 56380,
                    "farmapronto_id": "017285",
                    "sku": "017285",
                    "nombre": "VS CAFIASPIRINA TAB C\/10",
                    "descripcion": "VS CAFIASPIRINA TAB C\/10",
                    "categoria": "SISTEMA NERVIOSO",
                    "categoria_id": 0,
                    "laboratorio": null,
                    "receta": 0,
                    "clave": "Disponible",
                    "tipo": 36,
                    "activos": "ACIDO ACETILSALICILICO",
                    "destacado": 0,
                    "archivo": null,
                    "created_at": "2017-07-05 15:24:59",
                    "updated_at": "2017-07-14 13:04:17",
                    "activo": 1,
                    "lista_precios": [
                        {
                            "id": 21314,
                            "zona_id": 22,
                            "producto_id": 56380,
                            "precio": 10,
                            "created_at": "2017-07-05 17:28:23",
                            "updated_at": "2017-07-05 17:28:23"
                        }
                    ]
                }
            ],
            "info": [
                    {
                        "search_id": 39,
                        "total": 3
                    }
                ]
        }



 ## Detalle del producto


 **URL**

  /api/productos/{id}

 **Al solicitar el detalle del producto deberá mandar el search_id obtenido de la busqueda**

 Ej


     ```
     https://farmapronto.test/api/productos/9404?search_id=39
     ```


 **Method:**

  `GET`


**Success Response:**


* **Code:** 200 <br />



         {
         	"producto": {
         		"id": 63768,
         		"farmapronto_id": "056721",
         		"sku": "8470001822758",
         		"nombre": "CRA REP RADIOCARE CALENDULA 150 ML",
         		"descripcion": "",
         		"categoria": "DERMATOLOGICOS",
         		"categoria_id": 0,
         		"laboratorio": null,
         		"receta": 0,
         		"clave": "DISPONIBLE",
         		"tipo": 0,
         		"activos": "0",
         		"keywords": "",
         		"destacado": 0,
         		"archivo": "uploads\/images\/productos\/8470001822758.png",
         		"created_at": "2018-06-20 05:30:02",
         		"updated_at": "2018-09-18 17:55:41",
         		"activo": 1,
         		"despliega": 1,
         		"media": [
         			{
         				"id": 2,
         				"model_id": 63768,
         				"model_type": "fp\\Entities\\Producto",
         				"collection_name": "galeria",
         				"name": "8470001822758.2",
         				"file_name": "8470001822758.png",
         				"mime_type": "image\/png",
         				"disk": "media",
         				"size": 750694,
         				"manipulations": [],
         				"custom_properties": [],
         				"order_column": 2,
         				"created_at": "2018-09-18 17:28:23",
         				"updated_at": "2018-09-18 17:28:23",
         				"thumb": "http:\/\/farmapronto-multiples.csgroup.mx\/uploads\/media\/2\/conversions\/thumb.png",
         				"large": "http:\/\/farmapronto-multiples.csgroup.mx\/uploads\/media\/2\/conversions\/large.png",
         				"original_image": "http:\/\/farmapronto-multiples.csgroup.mx\/uploads\/media\/2\/8470001822758.png"
         			},
         			{
         				"id": 3,
         				"model_id": 63768,
         				"model_type": "fp\\Entities\\Producto",
         				"collection_name": "galeria",
         				"name": "8470001822758.4",
         				"file_name": "8470001822758.png",
         				"mime_type": "image\/png",
         				"disk": "media",
         				"size": 789720,
         				"manipulations": [],
         				"custom_properties": [],
         				"order_column": 3,
         				"created_at": "2018-09-18 17:28:24",
         				"updated_at": "2018-09-18 17:28:24",
         				"thumb": "http:\/\/farmapronto-multiples.csgroup.mx\/uploads\/media\/3\/conversions\/thumb.png",
         				"large": "http:\/\/farmapronto-multiples.csgroup.mx\/uploads\/media\/3\/conversions\/large.png",
         				"original_image": "http:\/\/farmapronto-multiples.csgroup.mx\/uploads\/media\/3\/8470001822758.png"
         			},
         			{
         				"id": 4,
         				"model_id": 63768,
         				"model_type": "fp\\Entities\\Producto",
         				"collection_name": "galeria",
         				"name": "8470001822758.3",
         				"file_name": "8470001822758.png",
         				"mime_type": "image\/png",
         				"disk": "media",
         				"size": 890105,
         				"manipulations": [],
         				"custom_properties": [],
         				"order_column": 4,
         				"created_at": "2018-09-18 17:31:37",
         				"updated_at": "2018-09-18 17:31:37",
         				"thumb": "http:\/\/farmapronto-multiples.csgroup.mx\/uploads\/media\/4\/conversions\/thumb.png",
         				"large": "http:\/\/farmapronto-multiples.csgroup.mx\/uploads\/media\/4\/conversions\/large.png",
         				"original_image": "http:\/\/farmapronto-multiples.csgroup.mx\/uploads\/media\/4\/8470001822758.png"
         			}
         		]
         	}
         }



**Error Response:**


 * **Code:** 404 <br />


    {
    	"error": "Model not found."
    }


## Include para obtener benficios

**Request**

EJ. 
        
        /api/productos?nombre=7501300408747&includes[]=beneficios
        
        
    
**Response**

        
        {
          "productos": [
            {
                  "id": 59,
                  "farmapronto_id": "000054",
                  "sku": "7501017372737",
                  "nombre": "ABSORSEC ETAPA MEDIANA UNISEX C\/ 40 PANALES",
                  "descripcion": "",
                  "categoria": "PANALES DESECHABLES",
                  "categoria_id": 0,
                  "laboratorio": "K CLARK",
                  "receta": 0,
                  "clave": "SUJETO A DISPONIBILIDAD",
                  "tipo": 419,
                  "activos": "0",
                  "keywords": "",
                  "destacado": 0,
                  "archivo": null,
                  "created_at": "2017-03-16 17:49:19",
                  "updated_at": "2019-11-07 06:01:05",
                  "activo": 1,
                  "despliega": 1,
                  "beneficios": [
                    {
                      "id": 5,
                      "sku_compra": "7501017372737",
                      "referencia": "MTCL_KMC",
                      "producto_compra_nombre": "ABSORSEC ETAPA MEDIANA UNISEX C\/ 40 PANALES",
                      "cantidad_compra": 1,
                      "sku_beneficio": "7501017372737",
                      "producto_beneficio_nombre": "ABSORSEC ETAPA MEDIANA UNISEX C\/ 40 PANALES",
                      "cantidad_beneficio": 0,
                      "vigencia_inicio": "2019-08-11",
                      "vigencia_fin": "2019-11-15",
                      "porcentaje_descuento": 0,
                      "tipo_porcentaje_descuento": 0,
                      "activo": 1,
                      "created_at": "2019-11-11 17:19:59",
                      "updated_at": "2019-11-11 17:19:59",
                      "periodo_num_regalos": 5,
                      "periodo_dias": null,
                      "periodo": 0,
                      "tarjeta_tipo_id": 1,
                      "promocion_tipo_id": 2,
                      "tarjeta_farmapronto": 1
                    }
                  ],
                  "lista_precios": [
                    {
                      "id": 36,
                      "zona_id": 22,
                      "producto_id": 59,
                      "precio": 95,
                      "created_at": "2017-06-22 16:50:20",
                      "updated_at": "2019-09-12 06:01:50"
                    }
                  ]
                },
          "info": [
            {
              "search_id": null,
              "total": 1
            }
          ]
        }    