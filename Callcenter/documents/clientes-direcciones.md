      
## Listado de direcciones
Regresa el listado de todas las direcciones del cliente

 **URL**

  /api/clientes/direcciones/

 **Method:**

  `GET`
  
 **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data

**Success Response:**

* **Code:** 200 <br />
  **Content:** 
  
      {
        "direcciones": [
            {
              "id": 1,
              "cliente_id": 1,
              "estado_id": 2,
              "municipio_id": 996,
              "colonia_id": 3343,
              "calle": "Flores",
              "numero_interior": "12",
              "numero_exterior": "A",
              "codigo_postal": 62020,
              "referencia": "",
              "tipo": "casa",
              "created_at": null,
              "updated_at": "2017-05-10 17:08:34"
            }
          ]
      }

**Error Response:**

* **Code:** 401 Unauthorized <br />
  **Content:** 
  
      {
        "error": "Unauthenticated."
      }
       
       
**Registro de dirección**
----
  Regresa la información del registro en formato json

 **URL**

  /api/clientes/direcciones/

 **Method:**

  `POST`
  
  **URL Params**

  None
 
 **Data Params**

 ***Required:***
    
 `estado_id=[required|exists:catalogo_estados,id]`
 `municipio_id=[required|exists:catalogo_municipios,id]`
 `colonia_id=[required|exists:catalogo_colonias,id]`
 `calle=[required]`
 `numero_interiorl=[required]`
 `codigo_postal=[required]`
 `referencia=[optional]`
 `tipo=[required|in:casa,oficina]`


 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
          "direccion": {
              "user_id": "4",
              "estado_id": "9",
              "municipio_id": "84",
              "colonia_id": "1",
              "calle": "Las Flores",
              "numero_interior": "1",
              "codigo_postal": "00000",
              "tipo": "casa",
              "updated_at": "2017-05-17 17:39:59",
              "created_at": "2017-05-17 17:39:59",
              "id": 1
            }
        }
 
 **Error Response:**

  * **Code:** 422 Unprocessable Entity <br />
    **Content:** 
    
        {
            "estado_id": [
              "El campo estado es obligatorio."
            ],
            "municipio_id": [
              "El campo municipio es obligatorio."
            ],
            "colonia_id": [
              "El campo colonia es obligatorio."
            ],
            "calle": [
              "El campo calle es obligatorio."
            ],
            "numero_interior": [
              "El campo numero interior es obligatorio."
            ],
            "codigo_postal": [
              "El campo codigo postal es obligatorio."
            ],
            "tipo": [
              "El campo tipo es obligatorio."
            ]
        }
        
  * **Code:** 401 Unauthorized <br />
      **Content:** 
      
          {
            "error": "Unauthenticated."
          }
 
**Datos de la dirección**
----
  Regresa la información de una dirección en específica del cliente y sus relaciones ejemplo: estado, municipio y colonia

 **URL**

  /api/clientes/direcciones/ID

 **Method:**

  `GET`
  
  **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data
      
  **URL Params**

  - includes[]=estado, municipio, colonia  <br><br>
  Ejemplo URI: `api/clientes/direcciones/1?includes[]=estado&includes[]=municipio&includes[]=colonia&includes[]=cliente`
  

 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
          "direccion": {
              "id": 1,
              "user_id": 4,
              "estado_id": 9,
              "municipio_id": 84,
              "colonia_id": 1,
              "calle": "Las Flores",
              "numero_interior": "1",
              "numero_exterior": null,
              "codigo_postal": 0,
              "tipo": "casa",
              "created_at": "2017-05-17 17:39:59",
              "updated_at": "2017-05-17 17:39:59",
              "estado": {
                "id": 9,
                "nombre": "DISTRITO FEDERAL",
                "created_at": "2017-05-17 17:14:30",
                "updated_at": "2017-05-17 17:14:30"
              },
              "municipio": {
                "id": 84,
                "estado_id": 9,
                "nombre": "ALVARO OBREGON",
                "created_at": "2017-05-17 17:14:30",
                "updated_at": "2017-05-17 17:14:30"
              },
              "colonia": {
                "id": 1,
                "municipio_id": 84,
                "codigo_postal": "1000",
                "nombre": "SAN ANGEL",
                "created_at": "2017-05-17 17:14:44",
                "updated_at": "2017-05-17 17:14:44"
              }
              "cliente": {
                "id": 4,
                "name": "Cliente",
                "last_name": "CS",
                "second_last_name": "Group",
                "telephone": "7777777778",
                "email": "test@csgroup.mx",
                "created_at": "2017-05-18 11:29:10",
                "updated_at": "2017-05-18 11:29:10",
                "deleted_at": null
              }
            }
        }
 
 **Error Response:**

  * **Code:** 401 Unauthorized <br />
    **Content:** 
    
        {
          "error": "Unauthenticated."
        }



**Actualización de dirección**
----
  Actualiza la información de una dirección en específica del cliente

 **URL**

  /api/clientes/direcciones/ID

 **Method:**

  `PUT`
    
 **Headers**
 
    Authorization: Bearer access_token
    Accept: application/json
    Content-Type: multipart/form-data
    
**Data Params**

 ***Required:***
    
 `estado_id=[required|exists:catalogo_estados,id]`
 `municipio_id=[required|exists:catalogo_municipios,id]`
 `colonia_id=[required|exists:catalogo_colonias,id]`
 `calle=[required]`
 `numero_interiorl=[required]`
 `referencia=[optional]`
 `codigo_postal=[required]`
 `tipo=[required|in:casa,oficina]`
 `lat=[optional]`
 `lon=[optional]`
    
 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
          "direccion": {
              "id": 1,
              "user_id": "4",
              "estado_id": "9",
              "municipio_id": "84",
              "colonia_id": "3",
              "calle": "Las Flores",
              "numero_interior": "12",
              "numero_exterior": null,
              "codigo_postal": "00000",
              "tipo": "casa",
              "created_at": "2017-05-17 17:39:59",
              "updated_at": "2017-05-17 17:55:54"
            }
        }

 **Error Response:**

  * **Code:** 422 Unprocessable Entity <br />
      **Content:** 
      
          {
              "estado_id": [
                "El campo estado es obligatorio."
              ],
              "municipio_id": [
                "El campo municipio es obligatorio."
              ],
              "colonia_id": [
                "El campo colonia es obligatorio."
              ],
              "calle": [
                "El campo calle es obligatorio."
              ],
              "numero_interior": [
                "El campo numero interior es obligatorio."
              ],
              "codigo_postal": [
                "El campo codigo postal es obligatorio."
              ],
              "tipo": [
                "El campo tipo es obligatorio."
              ]
          }
          
  * **Code:** 401 Unauthorized <br />
      **Content:** 
      
          {
            "error": "Unauthenticated."
          }


**Eliminar dirección**
----
  Elimina una dirección en específica del cliente

 **URL**

  /api/clientes/direcciones/ID

 **Method:**

  `DELETE`
    
 **Headers**
  
     Authorization: Bearer access_token
     Accept: application/json
     Content-Type: multipart/form-data
    
    
 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
        	"direccion": null
        }

 **Error Responses:**

  * **Code:** 401 Unauthorized <br />
    **Content:** 
    
        {
          "error": "Unauthenticated."
        }