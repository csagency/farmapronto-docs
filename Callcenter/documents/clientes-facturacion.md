      
## Listado de registros facturación

Regresa el listado de registros de facturación

 **URL**

  /api/clientes/facturaciones/

 **Method:**

  `GET`
  
 **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json

**Success Response:**

* **Code:** 200 <br />
  **Content:** 
  
      {
      	"facturaciones": [
      		{
      			"id": 4,
      			"rfc": "BIAE881014QV6",
      			"cliente_direccion_id": 2,
      			"created_at": "2017-06-21 13:47:17",
      			"updated_at": "2017-06-21 13:47:17",
      			"estado_id": null,
      			"municipio_id": null,
      			"calle": null,
      			"numero": null,
      			"colonia": null,
      			"codigo_postal": null,
      			"user_id": 16,
      			"uso_cfdi_id": null,
      		},
      		{
      			"id": 5,
      			"rfc": "BIAE881014QV6",
      			"cliente_direccion_id": null,
      			"created_at": "2017-06-21 13:47:54",
      			"updated_at": "2017-06-21 13:47:54",
      			"estado_id": 2,
      			"municipio_id": 1,
      			"calle": "Avenida",
      			"numero": "23",
      			"colonia": "Chamilpa",
      			"codigo_postal": "62210",
      			"user_id": 16,
      			"uso_cfdi_id": null,
      		}
      	]
      }

**Error Response:**

* **Code:** 401 Unauthorized <br />
  **Content:** 
  
      {
        "error": "Unauthenticated."
      }
       
       
** Crear registro de facturacion **
----
  Regresa la información del registro en formato json

 **URL**

  /api/clientes/facturaciones/


  **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: application/x-www-form-urlencoded

 **Method:**

  `POST`
  
  **URL Params**

  None
 
 **Data Params**

 ***Required:***
 ***Required if empty:***
    
            'rfc' => 'required|max:13',
            'cliente_direccion_id' => 'nullable',
            'estado_id' => 'required_if:cliente_direccion_id,|exists:catalogo_estados,id',
            'municipio_id' => 'required_if:cliente_direccion_id,|exists:catalogo_municipios,id',
            'calle' => 'required_if:cliente_direccion_id,',
            'numero' => 'required_if:cliente_direccion_id,',
            'colonia' => 'required_if:cliente_direccion_id,',
            'codigo_postal' => 'required_if:cliente_direccion_id,',
            'uso_cfdi_id' => 'nullable|exists:catalogo_usos_cfdi,id,',


 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
        	"facturacion": {
        		"rfc": "BIAE881014QV6",
        		"estado_id": "2",
        		"municipio_id": "1",
        		"calle": "Avenida",
        		"numero": "23",
        		"colonia": "Chamilpa",
        		"codigo_postal": "62210",
        		"user_id": 16,
        		"updated_at": "2017-06-21 13:47:54",
        		"created_at": "2017-06-21 13:47:54",
        		"id": 5,
        		"uso_cfdi_id": null,
        	}
        }
 **Error Response:**

  * **Code:** 422 Unprocessable Entity <br />
    **Content:** 
    
        {
            "rfc": [
                "El campo rfc es obligatorio."
            ],
            "estado_id": [
                "El campo estado es obligatorio cuando cliente direccion id es ."
            ],
            "municipio_id": [
                "El campo municipio es obligatorio cuando cliente direccion id es ."
            ],
            "calle": [
                "El campo calle es obligatorio cuando cliente direccion id es ."
            ],
            "numero": [
                "El campo numero es obligatorio cuando cliente direccion id es ."
            ],
            "colonia": [
                "El campo colonia es obligatorio cuando cliente direccion id es ."
            ],
            "codigo_postal": [
                "El campo codigo postal es obligatorio cuando cliente direccion id es ."
            ]
        }
        
  * **Code:** 401 Unauthorized <br />
      **Content:** 
      
          {
            "error": "Unauthenticated."
          }
 
**Datos de la factura**
----
  Regresa la información de la factura  y sus relaciones ejemplo: estado, municipio y cliente

 **URL**

  /api/clientes/facturaciones/ID

 **Method:**

  `GET`
  
  **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      
  **URL Params**

  - includes[]=estado, municipio, direccion, cliente   <br><br>
  Ejemplo URI: `api/clientes/facturaciones/5?includes[]=estado&includes[]=municipio&includes[]=direccion&includes[]=cliente`
  

 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
        	"facturacion": {
        		"id": 5,
        		"rfc": "BIAE881014QV6",
        		"cliente_direccion_id": null,
        		"created_at": "2017-06-21 13:47:54",
        		"updated_at": "2017-06-21 13:47:54",
        		"estado_id": 2,
        		"municipio_id": 1,
        		"calle": "Avenida",
        		"numero": "23",
        		"colonia": "Chamilpa",
        		"codigo_postal": "62210",
        		"user_id": 16,
        		"uso_cfdi_id": null,
        		"estado": {
        			"id": 2,
        			"nombre": "BAJA CALIFORNIA",
        			"created_at": "2017-03-16 17:47:54",
        			"updated_at": "2017-03-16 17:47:54"
        		},
        		"municipio": {
        			"id": 1,
        			"estado_id": 31,
        			"nombre": "ABALA",
        			"created_at": "2017-03-16 17:47:55",
        			"updated_at": "2017-03-16 17:47:55"
        		},
        		"direccion": null,
        		"cliente": {
                    "id": 16,
                    "name": "Erick 2",
                    "last_name": "AAA",
                    "second_last_name": "A",
                    "telephone": "527773274199",
                    "email": null,
                    "created_at": "2017-06-13 19:11:42",
                    "updated_at": "2017-06-13 19:13:18",
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



**Actualización**
----
  Actualiza la información de facturación

 **URL**

  /api/clientes/facturaciones/ID

 **Method:**

  `PUT`
    
 **Headers**
 
    Authorization: Bearer access_token
    Accept: application/json
    Content-Type: application/x-www-form-urlencoded
    
**Data Params**

 ***Required:***
    
            'rfc' => 'required|max:13',
            'cliente_direccion_id' => 'nullable',
            'estado_id' => 'required_if:cliente_direccion_id,|exists:catalogo_estados,id',
            'municipio_id' => 'required_if:cliente_direccion_id,|exists:catalogo_municipios,id',
            'calle' => 'required_if:cliente_direccion_id,',
            'numero' => 'required_if:cliente_direccion_id,',
            'colonia' => 'required_if:cliente_direccion_id,',
            'codigo_postal' => 'required_if:cliente_direccion_id,',
            'uso_cfdi_id' => 'nullable|exists:catalogo_usos_cfdi,id,',
    
 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
        	"facturacion": {
        		"id": 5,
        		"rfc": "BIAE881014QV6",
        		"cliente_direccion_id": null,
        		"created_at": "2017-06-21 13:47:54",
        		"updated_at": "2017-06-21 13:53:02",
        		"estado_id": "4",
        		"municipio_id": "5",
        		"calle": "Avenida",
        		"numero": "32",
        		"colonia": "Chamilpa",
        		"codigo_postal": "62213",
        		"user_id": 16,
        		"uso_cfdi_id": null,
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


**Eliminar**
----
  Elimina una factura en específica del usuario

 **URL**

  /api/clientes/facturaciones/ID

 **Method:**

  `DELETE`
    
 **Headers**
  
     Authorization: Bearer access_token
     Accept: application/json
    
    
 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
        	"facturacion": null
        }

 **Error Responses:**

  * **Code:** 401 Unauthorized <br />
    **Content:** 
    
        {
          "error": "Unauthenticated."
        }