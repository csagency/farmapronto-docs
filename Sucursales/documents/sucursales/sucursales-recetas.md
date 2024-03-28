## Listado de recetas registradas (encargada/auxiliar)
Regresa el listado de las recetas registradas por la sucursal

 **URL**

    /api/sucursales/sucursales-recetas

 **Method:**

  `GET`
  
 **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data
      
      
 **Data Params**
    
     'tipo' => 'nullable|in:ultimo,dia',
     'horario' => 'nullable|in:8:30,15:30',
     'categoria' => 'nullable|in:controlados,antibioticos'
     
 **URL Params**

      - includes[] = sucursal, user
        Devuelve todos los registros de su sucursal asignada
        Ejemplo URI: `api/sucursales/sucursales-recetas?includes[]=sucursal`

      - tipo = dia
        Devuelve todos los registros del día de su sucursal asignada
        Ejemplo URI: `api/sucursales/sucursales-recetas?tipo=dia`
        
      - tipo = ultimo
        Devuelve el último registro de su sucursal asignada
        Ejemplo URI: `api/sucursales/sucursales-recetas?tipo=ultimo`
        
      - horario = 15:30
        Devuelve todos los registros del horario indicado de su sucursal asignada
        Ejemplo URI: `api/sucursales/sucursales-recetas?horario=15:30`

**Success Response:**

* **Code:** 200 <br />
  **Content:** 
  
      {
      	"recetas": [
            {
              "id": 1,
              "sucursal_id": 10,
              "user_id": 13,
              "horario": "15:30:00",
              "categoria": "antibioticos",
              "recetas": 10,
              "facturas": null,
              "folios": 7,
              "created_at": "2019-11-20 18:37:41",
              "updated_at": "2019-11-20 18:40:45",
              "deleted_at": null,
              "evidencia": "\/storage\/sucursales\/recetas\/evidencias\/1\/Farma3.jpg",
              "media": [
                {
                  "id": 1,
                  "model_type": "App\\Entities\\Sucursal\\SucursalReceta",
                  "model_id": 1,
                  "collection_name": "evidencia",
                  "name": "Farma3",
                  "file_name": "Farma3.jpg",
                  "mime_type": "image\/jpeg",
                  "disk": "evidencias_recetas",
                  "size": 183092,
                  "manipulations": [],
                  "custom_properties": [],
                  "responsive_images": [],
                  "order_column": 1,
                  "created_at": "2019-11-20 18:37:41",
                  "updated_at": "2019-11-20 18:37:41"
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
          
          
  * **Code:** 422 Unprocessable Entity <br />
    **Content:** 
    
        {
            "tipo": [
              "El campo tipo es inválido."
            ],
            "horario": [
              "El campo horario es inválido."
            ],
            "categoria": [
              "El campo categoria es inválido."
            ]
        }
        
          
   * **Code:** 406 Not Acceptable <br />
      **Content:** 
    
            {
              "error": "El usuario no cuenta con perfil de Encargada/Auxiliar o Supervisor."
            }
            
            
## Listado de recetas registradas (supervisor)
Regresa el listado de los recetas registradas

 **URL**

    /api/sucursales/sucursales-recetas

 **Method:**

  `GET`
  
 **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data
      
       
 **Data Params**
    
    'tipo' => 'nullable|in:dia',
    'sucursal_id' => 'nullable',
    'horario' => 'nullable|in:8:30,15:30',
    'categoria' => 'nullable|in:controlados,antibioticos'
     
 **URL Params**

      - includes[] = sucursal, user
        Devuelve todos los registros del mes de todas las sucursales asignadas
        Ejemplo URI: `api/sucursales/sucursales-recetas?includes[]=sucursal`

      - sucursal_id = ID
        Devuelve todos los registros del mes de una sucursal en específico
        Ejemplo URI: `api/sucursales/sucursales-recetas?sucursal_id=4`
     
      - tipo = dia
        Devuelve todos los registros del día de todas las sucursales asignadas
        Ejemplo URI: `api/sucursales/sucursales-recetas?tipo=dia`
        
      - horario = 15:30
        Devuelve todos los registros del horario indicado
        Ejemplo URI: `api/sucursales/sucursales-recetas?horario=15:30`
        
      - categoria = controlados
        Devuelve todos los registros de la categoría "controlados" de todas las sucursales asignadas
        Ejemplo URI: `api/sucursales/sucursales-recetas?categoria=controlados`
        
        
      Registros del día en una sucursal y horario en específico
        api/sucursales/sucursales-recetas?sucursal_id=10&tipo=dia&horario=15:30&includes[]=sucursal
          

**Success Response:**

* **Code:** 200 <br />
  **Content:** 
  
      {
        "recetas": [
            {
              "id": 1,
              "sucursal_id": 10,
              "user_id": 13,
              "horario": "15:30:00",
              "categoria": "antibioticos",
              "recetas": 10,
              "facturas": null,
              "folios": 7,
              "created_at": "2019-11-20 18:37:41",
              "updated_at": "2019-11-20 18:40:45",
              "deleted_at": null,
              "evidencia": "\/storage\/sucursales\/recetas\/evidencias\/1\/Farma3.jpg",
              "sucursal": {
                "id": 10,
                "tipo_sucursal": null,
                "nombre": "L",
                "codigo": "7",
                "direccion": "CAMINO A ZUMPANGO",
                "lat": "17.6059991",
                "lon": "-99.5228515",
                "meta_encargadas": 0,
                "meta_auxiliares": 0,
                "meta_cajeras": 0,
                "fondo_venta_mensual": 0,
                "fondo_callcenter": 0,
                "matutino": 1,
                "vespertino": 1,
                "intermedio": 0,
                "fondo_asignado": 0,
                "created_at": "2019-09-23 05:22:31",
                "updated_at": "2019-09-23 05:22:31",
                "deleted_at": null
              },
              "media": [
                {
                  "id": 1,
                  "model_type": "App\\Entities\\Sucursal\\SucursalReceta",
                  "model_id": 1,
                  "collection_name": "evidencia",
                  "name": "Farma3",
                  "file_name": "Farma3.jpg",
                  "mime_type": "image\/jpeg",
                  "disk": "evidencias_recetas",
                  "size": 183092,
                  "manipulations": [],
                  "custom_properties": [],
                  "responsive_images": [],
                  "order_column": 1,
                  "created_at": "2019-11-20 18:37:41",
                  "updated_at": "2019-11-20 18:37:41"
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
          
               
  * **Code:** 422 Unprocessable Entity <br />
    **Content:** 
    
        {
            "tipo": [
              "El campo tipo es inválido."
            ],
            "horario": [
              "El campo horario es inválido."
            ],
            "categoria": [
              "El campo categoria es inválido."
            ]
        }
        
        
   * **Code:** 406 Not Acceptable <br />
      **Content:** 
    
            {
              "error": "El usuario no cuenta con perfil de Encargada/Auxiliar o Supervisor."
            }
             
            
                    
## Detalle de registro de recetas
Regresa el registro de una receta

 **URL**

    /api/sucursales/sucursales-recetas/{ID}

 **Method:**

  `GET`
  
 **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data
     
 **URL Params**

      - includes[] = sucursal, user
        Ejemplo URI: `api/sucursales/sucursales-recetas/3?includes[]=sucursal`

**Success Response:**

* **Code:** 200 <br />
  **Content:** 
  
      {
         "receta": {
             "id": 1,
             "sucursal_id": 10,
             "user_id": 13,
             "horario": "15:30:00",
             "categoria": "antibioticos",
             "recetas": 10,
             "facturas": null,
             "folios": 10,
             "created_at": "2019-11-20 18:37:41",
             "updated_at": "2019-11-20 18:37:41",
             "deleted_at": null,
             "evidencia": "\/storage\/sucursales\/recetas\/evidencias\/1\/Farma3.jpg",
             "sucursal": {
               "id": 10,
               "tipo_sucursal": null,
               "nombre": "L",
               "codigo": "7",
               "direccion": "CAMINO A ZUMPANGO",
               "lat": "17.6059991",
               "lon": "-99.5228515",
               "meta_encargadas": 0,
               "meta_auxiliares": 0,
               "meta_cajeras": 0,
               "fondo_venta_mensual": 0,
               "fondo_callcenter": 0,
               "matutino": 1,
               "vespertino": 1,
               "intermedio": 0,
               "fondo_asignado": 0,
               "created_at": "2019-09-23 05:22:31",
               "updated_at": "2019-09-23 05:22:31",
               "deleted_at": null,
               "encargada": {
                 "id": 2,
                 "user_id": 13,
                 "sucursal_id": 10,
                 "created_at": "2019-06-27 17:59:19",
                 "updated_at": "2019-11-12 13:43:09",
                 "deleted_at": null
               }
             },
             "media": [
               {
                 "id": 1,
                 "model_type": "App\\Entities\\Sucursal\\SucursalReceta",
                 "model_id": 1,
                 "collection_name": "evidencia",
                 "name": "Farma3",
                 "file_name": "Farma3.jpg",
                 "mime_type": "image\/jpeg",
                 "disk": "evidencias_recetas",
                 "size": 183092,
                 "manipulations": [],
                 "custom_properties": [],
                 "responsive_images": [],
                 "order_column": 1,
                 "created_at": "2019-11-20 18:37:41",
                 "updated_at": "2019-11-20 18:37:41"
               }
             ]
         }
      }

**Error Response:**

  * **Code:** 401 Unauthorized <br />
    **Content:** 
  
          {
            "error": "Unauthenticated."
          }  

            
    
**Registro de recetas**
----
  Regresa la información del registro en formato json

 **URL**

    /api/sucursales/sucursales-recetas

 **Method:**

  `POST`
  
  **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data

 
 **Data Params**
    
     'sucursal_id' => 'required|exists:sucursales,id',
     'horario' => 'required|in:8:30,15:30',
     'evidencia' => 'required|image',
     'recetas' => 'required',
     'facturas' => 'required_if:categoria,controlados',
     'folios' => 'required_if:categoria,antibioticos',
     'categoria' => 'required|in:controlados,antibioticos'


 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
            "sucursal_receta": {
                "sucursal_id": 10,
                "user_id": 13,
                "horario": "15:30:00",
                "categoria": "antibioticos",
                "recetas": "10",
                "facturas": null,
                "folios": "10",
                "updated_at": "2019-11-20 18:37:41",
                "created_at": "2019-11-20 18:37:41",
                "id": 1,
                "evidencia": "\/storage\/sucursales\/recetas\/evidencias\/1\/Farma3.jpg",
                "media": [
                  {
                    "id": 1,
                    "model_type": "App\\Entities\\Sucursal\\SucursalReceta",
                    "model_id": 1,
                    "collection_name": "evidencia",
                    "name": "Farma3",
                    "file_name": "Farma3.jpg",
                    "mime_type": "image\/jpeg",
                    "disk": "evidencias_recetas",
                    "size": 183092,
                    "manipulations": [],
                    "custom_properties": [],
                    "responsive_images": [],
                    "order_column": 1,
                    "created_at": "2019-11-20 18:37:41",
                    "updated_at": "2019-11-20 18:37:41"
                  }
                ]
            }
        }
        
 
 **Error Response:**
 
  * **Code:** 401 Unauthorized <br />
    **Content:** 
  
          {
            "error": "Unauthenticated."
          }

  * **Code:** 422 Unprocessable Entity <br />
    **Content:** 
    
        {
            "sucursal_id": [
              "El campo sucursal id es obligatorio."
            ],
            "horario": [
              "El campo horario es obligatorio."
            ],
            "evidencia": [
              "El campo evidencia es obligatorio."
            ],
            "recetas": [
              "El campo recetas es obligatorio."
            ],
            "categoria": [
              "El campo categoria es obligatorio."
            ],
            "facturas": [
              "El campo facturas es obligatorio cuando categoria es controlados."
            ],
            "folios": [
              "El campo folios es obligatorio cuando categoria es antibioticos."
            ]                         
        }
          
    
**Editar registro de receta (supervisor)**
----
  Regresa la información del registro editado en formato json

 **URL**

    /api/sucursales/sucursales-recetas/{ID}

 **Method:**

  `PUT`
  
  **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data

 
 **Data Params**
    
     'horario' => 'nullable|in:8:30,15:30',
     'evidencia' => 'nullable|image',
     'recetas' => 'nullable',
     'facturas' => 'nullable',
     'folios' => 'nullable',
     'categoria' => 'nullable|in:controlados,antibioticos'


 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
          "sucursal_receta": {
              "id": 1,
              "sucursal_id": 10,
              "user_id": 13,
              "horario": "15:30:00",
              "categoria": "antibioticos",
              "recetas": 10,
              "facturas": null,
              "folios": "7",
              "created_at": "2019-11-20 18:37:41",
              "updated_at": "2019-11-20 18:40:45",
              "deleted_at": null,
              "evidencia": "\/storage\/sucursales\/recetas\/evidencias\/1\/Farma3.jpg",
              "media": [
                {
                  "id": 1,
                  "model_type": "App\\Entities\\Sucursal\\SucursalReceta",
                  "model_id": 1,
                  "collection_name": "evidencia",
                  "name": "Farma3",
                  "file_name": "Farma3.jpg",
                  "mime_type": "image\/jpeg",
                  "disk": "evidencias_recetas",
                  "size": 183092,
                  "manipulations": [],
                  "custom_properties": [],
                  "responsive_images": [],
                  "order_column": 1,
                  "created_at": "2019-11-20 18:37:41",
                  "updated_at": "2019-11-20 18:37:41"
                }
              ]
          }
        }
        
 
 **Error Response:**
 
  * **Code:** 401 Unauthorized <br />
    **Content:** 
  
          {
            "error": "Unauthenticated."
          }
        
        
  * **Code:** 422 Unprocessable Entity <br />
    **Content:** 
    
        {
            "horario": [
              "El campo horario es inválido."
            ],
            "evidencia": [
              "evidencia debe ser una imagen."
            ],
            "categoria": [
              "El campo categoria es inválido."
            ]
        }
          
          
  * **Code:** 406 Not Acceptable <br />
  **Content:** 

        {
          "error": "El usuario no cuenta con perfil de Supervisor."
        }
     
