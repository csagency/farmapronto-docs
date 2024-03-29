**Obtiene todas las campañas del día**
----

 **URL**

    /api/monetizaciones

 **Method:**

  `GET`
  
  + Response 200 (application/json) Ejemplo:
  

    {
    	"monetizaciones": [
    		{
    			"id": 3,
    			"nombre": "Prueba campaña",
    			"tipo": "producto",
    			"fecha_inicio": "2018-10-19",
    			"fecha_fin": "2018-10-26",
    			"imagen_url": "uploads\/images\/monetizaciones\/8NuUss4YsGpi7cRM798326V3WFaLn24RBUsYQIEf.png",
    			"producto_id": 46373,
    			"producto_precio": 66,
    			"producto_descripcion": "CUYULID COMP 70MG\/5600 UI  4 COMP",
    			"created_at": "2018-10-17 18:48:10",
    			"updated_at": "2018-10-19 12:57:34",
    			"estados": [
    				{
    					"id": 19,
    					"monetizacion_id": 3,
    					"estado": "activo",
    					"created_at": "2018-10-19 12:57:35",
    					"updated_at": "2018-10-19 12:57:34"
    				},
    				{
    					"id": 18,
    					"monetizacion_id": 3,
    					"estado": "activo",
    					"created_at": "2018-10-19 12:57:01",
    					"updated_at": "2018-10-19 12:57:00"
    				},
    				{
    					"id": 17,
    					"monetizacion_id": 3,
    					"estado": "activo",
    					"created_at": "2018-10-19 12:56:41",
    					"updated_at": "2018-10-19 12:56:40"
    				},
    				{
    					"id": 1,
    					"monetizacion_id": 3,
    					"estado": "pendiente",
    					"created_at": "2018-10-17 18:48:10",
    					"updated_at": "2018-10-17 18:48:10"
    				}
    			],
    			"producto": {
    				"id": 46373,
    				"farmapronto_id": "052129",
    				"sku": "7502216934474",
    				"nombre": "CUYULID COMP 70MG\/5600 UI  4 COMP",
    				"descripcion": "",
    				"categoria": "SISTEMA MUSCULOESQUELETICO",
    				"categoria_id": 0,
    				"laboratorio": "ARMSTRONG",
    				"receta": 0,
    				"clave": "SUJETO A DISPONIBILIDAD",
    				"tipo": 30,
    				"activos": "ALENDRONICO ACIDO",
    				"keywords": "Osteoporosis, Fracturas,Osteopenia",
    				"destacado": 0,
    				"archivo": null,
    				"created_at": "2017-03-16 17:50:03",
    				"updated_at": "2018-10-15 05:04:40",
    				"activo": 1,
    				"despliega": 1
    			},
                            "imagenes": []
    		}
    	]
    }
    
    
**Obtiene todas las campañas del día de un tipo en específico**
----

 **URL**

    /api/monetizaciones/TIPO
    
 **URL Params**
    
      TIPO = banner/ inicio/ carousel/ producto/ categorias

 **Method:**

  `GET`
  
  + Response 200 (application/json) Ejemplo:
  

    {
    	"monetizaciones": []
    }