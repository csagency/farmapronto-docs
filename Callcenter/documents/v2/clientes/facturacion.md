      
## Listado de registros facturación

Regresa el listado de registros de facturación

 **URL**

    /api-v2/clientes/facturaciones/

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
              "id": 5702,
              "rfc": "PRUEBA123",
              "alias": null,
              "cliente_direccion_id": null,
              "created_at": "2020-04-22 13:15:26",
              "updated_at": "2020-04-22 13:15:26",
              "estado_id": 17,
              "municipio_id": 502,
              "calle": "PROLONGACION AHUATEPEC",
              "numero": "307",
              "numero_interior": null,
              "colonia": "LOMAS DE LA SELVA",
              "codigo_postal": "62270",
              "user_id": 23516,
              "uso_cfdi_id": null
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

    /api-v2/clientes/facturaciones/


  **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: application/x-www-form-urlencoded

 **Method:**

  `POST`
  
  **URL Params**

  None
 
 **Data Params**
    
    'alias' => '',
    'rfc' => 'required|max:13',
    'cliente_direccion_id' => 'nullable',
    'estado_id' => 'required_if:cliente_direccion_id,|exists:catalogo_estados,id',
    'municipio_id' => 'required_if:cliente_direccion_id,|exists:catalogo_municipios,id',
    'calle' => 'required_if:cliente_direccion_id,',
    'numero' => 'required_if:cliente_direccion_id,',
    'numero_interior' => 'nullable',
    'colonia' => 'nullable',
    'codigo_postal' => 'required_if:cliente_direccion_id,',
    'uso_cfdi_id' => 'nullable|exists:catalogo_usos_cfdi,id',


 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
            "facturacion": {
                "estado_id": "17",
                "municipio_id": "502",
                "colonia": "LOMAS DE LA SELVA",
                "calle": "PROLONGACION AHUATEPEC",
                "codigo_postal": "62270",
                "numero": "307",
                "numero_interior": null,
                "rfc": "PRUEBA123",
                "user_id": 23516,
                "updated_at": "2020-04-22 13:15:26",
                "created_at": "2020-04-22 13:15:26",
                "id": 5702
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
                "El campo código postal es obligatorio cuando cliente direccion id es ."
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

    /api-v2/clientes/facturaciones/ID

 **Method:**

  `GET`
  
  **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      
  **URL Params**

  - includes[]=estado, municipio, direccion, cliente   <br><br>
  Ejemplo URI: `api-v2/clientes/facturaciones/5702?includes[]=estado&includes[]=municipio&includes[]=direccion&includes[]=cliente`
  

 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
        	"facturacion": {
                "id": 5702,
                "rfc": "PRUEBA123",
                "alias": null,
                "cliente_direccion_id": null,
                "created_at": "2020-04-22 13:15:26",
                "updated_at": "2020-04-22 13:15:26",
                "estado_id": 17,
                "municipio_id": 502,
                "calle": "PROLONGACION AHUATEPEC",
                "numero": "307",
                "numero_interior": null,
                "colonia": "LOMAS DE LA SELVA",
                "codigo_postal": "62270",
                "user_id": 23516,
                "uso_cfdi_id": null,
                "estado": {
                  "id": 17,
                  "nombre": "MORELOS",
                  "created_at": "2017-03-16 17:47:54",
                  "updated_at": "2017-03-16 17:47:54"
                },
                "municipio": {
                  "id": 502,
                  "estado_id": 17,
                  "nombre": "CUERNAVACA",
                  "created_at": "2017-03-16 17:47:55",
                  "updated_at": "2017-03-16 17:47:55"
                },
                "cliente": {
                  "id": 23516,
                  "name": "Abril",
                  "last_name": "Prueba",
                  "second_last_name": "V2",
                  "telephone": "527772273622",
                  "clave": "ABPRELSY",
                  "email": "jabrilmtz17@gmail.com",
                  "player_id": null,
                  "tipo_usuario": null,
                  "activo": 1,
                  "baja": 0,
                  "fb_id": null,
                  "webhook_url": null,
                  "created_at": "2020-04-20 22:22:55",
                  "updated_at": "2020-04-21 12:35:41",
                  "deleted_at": null,
                  "last_login": null
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

    /api-v2/clientes/facturaciones/ID

 **Method:**

  `PUT`
    
 **Headers**
 
    Authorization: Bearer access_token
    Accept: application/json
    Content-Type: application/x-www-form-urlencoded
    
**Data Params**
    
    'alias' => '',
    'rfc' => 'required|max:13',
    'cliente_direccion_id' => 'nullable',
    'estado_id' => 'required_if:cliente_direccion_id,|exists:catalogo_estados,id',
    'municipio_id' => 'required_if:cliente_direccion_id,|exists:catalogo_municipios,id',
    'calle' => 'required_if:cliente_direccion_id,',
    'numero' => 'required_if:cliente_direccion_id,',
    'numero_interior' => 'nullable',
    'colonia' => 'nullable',
    'codigo_postal' => 'required_if:cliente_direccion_id,',
    'uso_cfdi_id' => 'nullable|exists:catalogo_usos_cfdi,id',
    
 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
        	"facturacion": {
                "id": 5702,
                "rfc": "123PRUEBA",
                "alias": null,
                "cliente_direccion_id": null,
                "created_at": "2020-04-22 13:15:26",
                "updated_at": "2020-04-22 13:18:34",
                "estado_id": "17",
                "municipio_id": "502",
                "calle": "PROLONGACION AHUATEPEC",
                "numero": "307",
                "numero_interior": null,
                "colonia": "LOMAS DE LA SELVA",
                "codigo_postal": "62270",
                "user_id": 23516,
                "uso_cfdi_id": null
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
                  "El campo código postal es obligatorio cuando cliente direccion id es ."
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

    /api-v2/clientes/facturaciones/ID

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