## Listado de checks
Regresa el listado de los checks realizados por el usuario logueado

 **URL**

    /api/checks-capacitadoras

 **Method:**

  `GET`
  
 **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data
      
       
 **Data Params**
    
    'tipo' => 'nullable|in:checkin,checkout'
     
 **URL Params**

      - tipo = checkin
        Devuelve todos los registros de tipo checkin
        Ejemplo URI: `api/checks?tipo=checkin`
        
      - includes[] = sucursal, user.perfilCapacitadora, checkout, checkin, plantillas
        Ejemplo URI: `api/checks-capacitadoras/1?includes[]=sucursal`
     

**Success Response:**

* **Code:** 200 <br />
  **Content:** 
  
      {
            "checks": {}
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
            ]
        }
        
          
  * **Code:** 406 Not Acceptable <br />
     **Content:** 
    
        {
            "message": "El usuario no cuenta con perfil de Capacitadora."
        }
             
            
                    
## Detalle de check
Regresa el registro de un check

 **URL**

    /api/checks-capacitadoras/{ID}

 **Method:**

  `GET`
  
 **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data
     
 **URL Params**

      - includes[] = sucursal, user.perfilCapacitadora, checkout, checkin, plantillas
        Ejemplo URI: `api/checks-capacitadoras/1?includes[]=sucursal`

**Success Response:**

* **Code:** 200 <br />
  **Content:** 
  
      {
            "check": {
                "id": 1,
                "user_id": 17,
                "sucursal_id": 3,
                "check_id": null,
                "turno": "matutino",
                "tipo": "checkin",
                "created_at": "2019-08-27 11:37:34",
                "updated_at": "2019-08-27 11:37:34",
                "deleted_at": null,
                "uniforme": "\/storage\/checks\/uniformes\/75\/35888217_2095034594077590_1878407717886885888_n.png",
                "sucursal": {
                  "id": 3,
                  "nombre": "Prueba",
                  "codigo": "PRUEBA",
                  "direccion": "CUERNAVACA, MORELOS",
                  "lat": "19.72314007415394",
                  "lon": "-98.924396",
                  "meta_encargadas": 10,
                  "meta_auxiliares": 10,
                  "meta_cajeras": 4,
                  "fondo_venta_mensual": 100000,
                  "fondo_callcenter": 100000,
                  "matutino": 1,
                  "vespertino": 0,
                  "intermedio": 0,
                  "fondo_asignado": 100000,
                  "created_at": "2019-06-25 17:30:10",
                  "updated_at": "2019-06-25 18:04:09",
                  "deleted_at": null
                },
                "media": [
                  {
                    "id": 75,
                    "model_type": "App\\Entities\\Checks\\CheckCapacitadora",
                    "model_id": 1,
                    "collection_name": "uniforme",
                    "name": "35888217_2095034594077590_1878407717886885888_n",
                    "file_name": "35888217_2095034594077590_1878407717886885888_n.png",
                    "mime_type": "image\/png",
                    "disk": "checks_uniformes",
                    "size": 652647,
                    "manipulations": [],
                    "custom_properties": [],
                    "responsive_images": [],
                    "order_column": 75,
                    "created_at": "2019-08-27 11:37:34",
                    "updated_at": "2019-08-27 11:37:34"
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

            
    
**Registro de checkin/checkout**
----
  Regresa la información del registro en formato json

 **URL**

    /api/checks-capacitadoras

 **Method:**

  `POST`
  
  **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data

 
 **Data Params**
    
     'sucursal_id' => 'required|exists:sucursales,id',
     'turno' => 'required|in:matutino,vespertino,intermedio',
     'tipo' => 'required|in:checkin,checkout',
     'uniforme' => 'nullable|image',
     'plantillas' => 'nullable|array',


****Verificación ubicación con sucursal**** [/api/sucursales/evaluar/sucursal](https://github.com/csagency/farmapronto-sucursales/blob/FS-33/documents/sucursales/sucursales.md#envío-de-coordenadas-para-saber-si-se-encuentra-dentro-del-rango-de-la-sucursal)

****Catálogo de plantilla de la sucursal**** [/api/sucursales/sucursales-plantillas](https://github.com/csagency/farmapronto-sucursales/blob/FS-33/documents/sucursales/sucursales-plantillas.md#listado-de-plantilla)


 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
            "check": {
                "user_id": 17,
                "sucursal_id": 3,
                "check_id": null,
                "turno": "matutino",
                "tipo": "checkin",
                "updated_at": "2019-08-27 11:37:34",
                "created_at": "2019-08-27 11:37:34",
                "id": 1,
                "uniforme": "\/storage\/checks\/uniformes\/75\/35888217_2095034594077590_1878407717886885888_n.png",
                "media": [
                  {
                    "id": 75,
                    "model_type": "App\\Entities\\Checks\\CheckCapacitadora",
                    "model_id": 1,
                    "collection_name": "uniforme",
                    "name": "35888217_2095034594077590_1878407717886885888_n",
                    "file_name": "35888217_2095034594077590_1878407717886885888_n.png",
                    "mime_type": "image\/png",
                    "disk": "checks_uniformes",
                    "size": 652647,
                    "manipulations": [],
                    "custom_properties": [],
                    "responsive_images": [],
                    "order_column": 75,
                    "created_at": "2019-08-27 11:37:34",
                    "updated_at": "2019-08-27 11:37:34"
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
            "turno": [
              "El campo turno es obligatorio."
            ],
            "tipo": [
              "El campo tipo es obligatorio."
            ],
            "uniforme": [
              "uniforme debe ser una imagen."
            ]
            "plantillas": [
              "El campo plantillas debe ser un conjunto."
            ]
        }

           
  * **Code:** 409 Conflict <br />
  **Content:** 

        {
          "message": "Lo sentimos, aún no puedes realizar check in en la misma sucursal. Ponte en contacto con tu supervisor."
        } 
        
        
        
          
**Editar información de checkin/checkout**
----
  Regresa la información del registro actualizado en formato json

 **URL**

    /api/checks-capacitadoras/ID

 **Method:**

  `PUT`
  
  **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data

 
 **Data Params**
    
     'sucursal_id' => 'required|exists:sucursales,id',
     'turno' => 'required|in:matutino,vespertino,intermedio',
     'tipo' => 'required|in:checkin,checkout',
     'uniforme' => 'nullable|image',
     'plantillas' => 'nullable|array',


 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
            "check": {
                "id": 1,
                "user_id": 17,
                "sucursal_id": "3",
                "check_id": null,
                "turno": "matutino",
                "tipo": "checkin",
                "created_at": "2019-08-27 11:37:34",
                "updated_at": "2019-08-27 11:37:34",
                "deleted_at": null,
                "uniforme": "\/storage\/checks\/uniformes\/75\/35888217_2095034594077590_1878407717886885888_n.png",
                "media": [
                  {
                    "id": 75,
                    "model_type": "App\\Entities\\Checks\\CheckCapacitadora",
                    "model_id": 1,
                    "collection_name": "uniforme",
                    "name": "35888217_2095034594077590_1878407717886885888_n",
                    "file_name": "35888217_2095034594077590_1878407717886885888_n.png",
                    "mime_type": "image\/png",
                    "disk": "checks_uniformes",
                    "size": 652647,
                    "manipulations": [],
                    "custom_properties": [],
                    "responsive_images": [],
                    "order_column": 75,
                    "created_at": "2019-08-27 11:37:34",
                    "updated_at": "2019-08-27 11:37:34"
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
            "turno": [
              "El campo turno es obligatorio."
            ],
            "tipo": [
              "El campo tipo es obligatorio."
            ],
            "uniforme": [
              "uniforme debe ser una imagen."
            ]
            "plantillas": [
              "El campo plantillas debe ser un conjunto."
            ]
        }
          
          
                  
        
        
## Último checkin activo de Capacitadora
Regresa el último checkin que aún no cuenta con un checkout realizado por el usuario capacitadora logueado 

**URL**
    
    /api/me/checkin-capacitadora-activo
    
**Method:**

 `GET`

**Headers**

    Authorization: Bearer access_token
    Accept: application/json
    Content-Type: multipart/form-data
 
 **URL Params**
         
       - includes[] = sucursal, user.perfilCapacitadora, checkout, checkin, plantillas.plantilla
         Ejemplo URI: `api/me/checkin-capacitadora-activo?includes[]=sucursal`
         
**Success Response:**

* **Code:** 200 <br />
    **Content:**
        
        {
           "check": {
               "id": 6,
               "user_id": 18,
               "sucursal_id": 3,
               "check_id": null,
               "turno": "matutino",
               "tipo": "checkin",
               "created_at": "2019-08-27 13:36:31",
               "updated_at": "2019-08-27 13:36:31",
               "deleted_at": null,
               "uniforme": "\/storage\/checks\/uniformes\/80\/35888217_2095034594077590_1878407717886885888_n.png",
               "sucursal": {
                 "id": 3,
                 "nombre": "Prueba",
                 "codigo": "PRUEBA",
                 "direccion": "CUERNAVACA, MORELOS",
                 "lat": "19.72314007415394",
                 "lon": "-98.924396",
                 "meta_encargadas": 10,
                 "meta_auxiliares": 10,
                 "meta_cajeras": 4,
                 "fondo_venta_mensual": 100000,
                 "fondo_callcenter": 100000,
                 "matutino": 1,
                 "vespertino": 0,
                 "intermedio": 0,
                 "fondo_asignado": 100000,
                 "created_at": "2019-06-25 17:30:10",
                 "updated_at": "2019-06-25 18:04:09",
                 "deleted_at": null
               },
               "plantillas": [
                 {
                   "id": 2,
                   "check_id": 6,
                   "plantilla_id": 3,
                   "created_at": "2019-08-27 13:36:31",
                   "updated_at": "2019-08-27 13:36:31",
                   "plantilla": {
                     "id": 3,
                     "sucursal_id": 3,
                     "user_id": 12,
                     "tipo": "auxiliar",
                     "turno": "vespertino",
                     "nombre": "Prueba",
                     "apellido_paterno": "Auxiliar",
                     "apellido_materno": null,
                     "telefono": "7771234567",
                     "email": "admin@csgroup.mx",
                     "fecha_contratacion": "2019-06-19",
                     "fecha_vacaciones": "2019-09-19",
                     "created_at": "2019-06-26 12:18:16",
                     "updated_at": "2019-06-27 18:56:21",
                     "deleted_at": null
                   }
                 }
               ],
               "media": [
                 {
                   "id": 80,
                   "model_type": "App\\Entities\\Checks\\CheckCapacitadora",
                   "model_id": 6,
                   "collection_name": "uniforme",
                   "name": "35888217_2095034594077590_1878407717886885888_n",
                   "file_name": "35888217_2095034594077590_1878407717886885888_n.png",
                   "mime_type": "image\/png",
                   "disk": "checks_uniformes",
                   "size": 652647,
                   "manipulations": [],
                   "custom_properties": [],
                   "responsive_images": [],
                   "order_column": 80,
                   "created_at": "2019-08-27 13:36:31",
                   "updated_at": "2019-08-27 13:36:31"
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
        
            
* **Code:** 406 Not Acceptable <br />
  **Content:** 

        {
          "message": "El usuario no cuenta con perfil de Capacitadora"
        }


## Monitoreo
Monitorea ubicación de capacitadora para generar alerta

 **URL**

    /api/checks-capacitadoras/monitoreo

 **Method:**

  `GET`
  
 **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data
      
       
 **Data Params**
    
    'check_id' => 'required',
    'lat' => 'required',
    'lon' => 'required'

**Success Response:**

* **Code:** 200 <br />
  **Content:** 
  
      {
            "respuesta": true
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
            "check_id": [
              "El campo check id es requerido."
            ],
            "lat": [
              "El campo lat es requerido."
            ],
            "lon": [
              "El campo lon es requerido"
            ]
        }
        
          
  * **Code:** 406 Not Acceptable <br />
     **Content:** 
    
        {
            "message": "El usuario no cuenta con perfil de Capacitadora."
        }
           
