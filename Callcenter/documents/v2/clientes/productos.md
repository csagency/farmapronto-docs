## Listado de productos favoritos del usuario

 **URL**

    /api-v2/clientes/favoritos

 **Method:**

  `GET`
  
 **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json


**URL Params**

  - includes[]=categoriaProducto, categoriaFP, skus  <br><br>
  Ejemplo URI: `api-v2/clientes/favoritos?includes[]=skus`



**Success Response:**

* **Code:** 200 <br />
  **Content:** 
  
      {
      	"productos": [
            {
              "id": 1,
              "farmapronto_id": "000001",
              "sku": "736085400892",
              "nombre": "3-A OFTENO 1MG GTS 5ML",
              "descripcion": "",
              "categoria": "ORGANOS DE LOS SENTIDOS",
              "categoria_id": 0,
              "laboratorio": "SOPHIA",
              "receta": 0,
              "clave": "DISPONIBLE",
              "tipo": 4,
              "activos": "DICLOFENACO SODICO",
              "keywords": "",
              "destacado": 0,
              "archivo": null,
              "created_at": "2017-03-16 17:49:19",
              "updated_at": "2020-03-18 06:00:46",
              "activo": 1,
              "despliega": 1,
              "skus": [
                {
                  "id": 1,
                  "farmapronto_id": "000001",
                  "sku": "736085400892"
                },
                {
                  "id": 2,
                  "farmapronto_id": "000001",
                  "sku": "736085445053"
                }
              ],
              "lista_precios": [
                {
                  "id": 1,
                  "zona_id": 22,
                  "producto_id": 1,
                  "precio": 540,
                  "created_at": null,
                  "updated_at": "2020-03-03 06:01:44"
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

    /api-v2/clientes/favoritos/{producto_id}

 **Method:**

  `POST`
  
 **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json


**Success Response: Attach**

* **Code:** 200 <br />
  **Content:** 
  
      {
      	"estatus": "attach",
          "producto": {
            "id": 1,
            "farmapronto_id": "000001",
            "sku": "736085400892",
            "nombre": "3-A OFTENO 1MG GTS 5ML",
            "descripcion": "",
            "categoria": "ORGANOS DE LOS SENTIDOS",
            "categoria_id": 0,
            "laboratorio": "SOPHIA",
            "receta": 0,
            "clave": "DISPONIBLE",
            "tipo": 4,
            "activos": "DICLOFENACO SODICO",
            "keywords": "",
            "destacado": 0,
            "archivo": null,
            "created_at": "2017-03-16 17:49:19",
            "updated_at": "2020-03-18 06:00:46",
            "activo": 1,
            "despliega": 1
        }
      }
      
      
**Success Response: Detach**

* **Code:** 200 <br />
  **Content:** 
  
      {
      	  "estatus": "detached",
          "producto": {
            "id": 1,
            "farmapronto_id": "000001",
            "sku": "736085400892",
            "nombre": "3-A OFTENO 1MG GTS 5ML",
            "descripcion": "",
            "categoria": "ORGANOS DE LOS SENTIDOS",
            "categoria_id": 0,
            "laboratorio": "SOPHIA",
            "receta": 0,
            "clave": "DISPONIBLE",
            "tipo": 4,
            "activos": "DICLOFENACO SODICO",
            "keywords": "",
            "destacado": 0,
            "archivo": null,
            "created_at": "2017-03-16 17:49:19",
            "updated_at": "2020-03-18 06:00:46",
            "activo": 1,
            "despliega": 1
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