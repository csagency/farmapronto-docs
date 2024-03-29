
      
      
## Listado de productos favoritos del usuario

 **URL**

  /api/clientes/favoritos

 **Method:**

  `GET`
  
 **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json

**URL Params**



**Success Response:**

* **Code:** 200 <br />
  **Content:** 
  
      {
      	"productos": [
      		{
      			"id": 512,
      			"farmapronto_id": "000572",
      			"sku": "748499001077",
      			"nombre": "AKTUFOAM 1.0% ESPUMA 30GR",
      			"descripcion": "AKTUFOAM 1.0% ESPUMA 30GR",
      			"categoria": "DERMATOLOGICOS",
      			"categoria_id": 0,
      			"laboratorio": "Bayer",
      			"receta": 0,
      			"clave": "DISPONIBLE",
      			"tipo": 6,
      			"activos": "CLINDAMICINA",
      			"destacado": 0,
      			"archivo": null,
      			"created_at": "2017-03-16 17:49:19",
      			"updated_at": "2017-10-27 06:31:22",
      			"activo": 1,
      			"lista_precios": [
      				{
      					"id": 18572,
      					"zona_id": 22,
      					"producto_id": 512,
      					"precio": 323,
      					"created_at": "2017-07-05 17:16:40",
      					"updated_at": "2017-10-26 06:43:01"
      				}
      			]
      		}
      	]
      }

**Error Response:**

* **Code:** 401 Unauthorized <br />
  **Content:** 
  
      {
        "error": "Unauthenticated."
      }
       
       
## Attach / Detach de productos favoritos del usuario

 **URL**

  /api/clientes/favoritos/{producto_id}

 **Method:**

  `POST`
  
 **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json

**URL Params**



**Success Response: Attach**

* **Code:** 200 <br />
  **Content:** 
  
      {
      	"estatus": "attach",
      	"producto": {
      		"id": 512,
      		"farmapronto_id": "000572",
      		"sku": "748499001077",
      		"nombre": "AKTUFOAM 1.0% ESPUMA 30GR",
      		"descripcion": "AKTUFOAM 1.0% ESPUMA 30GR",
      		"categoria": "DERMATOLOGICOS",
      		"categoria_id": 0,
      		"laboratorio": "Bayer",
      		"receta": 0,
      		"clave": "DISPONIBLE",
      		"tipo": 6,
      		"activos": "CLINDAMICINA",
      		"destacado": 0,
      		"archivo": null,
      		"created_at": "2017-03-16 17:49:19",
      		"updated_at": "2017-10-27 06:31:22",
      		"activo": 1
      	}
      }
      
      
**Success Response: Detach**

* **Code:** 200 <br />
  **Content:** 
  
      {
      	"estatus": "detached",
      	"producto": {
      		"id": 512,
      		"farmapronto_id": "000572",
      		"sku": "748499001077",
      		"nombre": "AKTUFOAM 1.0% ESPUMA 30GR",
      		"descripcion": "AKTUFOAM 1.0% ESPUMA 30GR",
      		"categoria": "DERMATOLOGICOS",
      		"categoria_id": 0,
      		"laboratorio": "Bayer",
      		"receta": 0,
      		"clave": "DISPONIBLE",
      		"tipo": 6,
      		"activos": "CLINDAMICINA",
      		"destacado": 0,
      		"archivo": null,
      		"created_at": "2017-03-16 17:49:19",
      		"updated_at": "2017-10-27 06:31:22",
      		"activo": 1
      	}
      }
      
**Error Response: Not Found**

* **Code:** 404 <br />
  **Content:** 
  
      {
      	"error": "Model not found."
      }
      
* **Code:** 401 Unauthorized <br />
**Content:** 

    {
      "error": "Unauthenticated."
    }