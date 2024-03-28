      
## Listado de temperaturas registradas (encargada/auxiliar)
Regresa el listado de las temperaturas registradas por la sucursal

 **URL**

    /api/sucursales/sucursales-temperaturas

 **Method:**

  `GET`
  
 **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data
      
      
 **Data Params**
    
     'tipo' => 'nullable|in:ultimo,dia',
     
 **URL Params**

      - includes[] = sucursal
        Ejemplo URI: `api/sucursales/sucursales-temperaturas?includes[]=sucursal`

      - tipo = dia
        Devuelve todos los registros del día
        Ejemplo URI: `api/sucursales/sucursales-temperaturas?tipo=dia`
        
      - tipo = ultimo
        Devuelve el último registro de la sucursal
        Ejemplo URI: `api/sucursales/sucursales-temperaturas?tipo=ultimo`

**Success Response:**

* **Code:** 200 <br />
  **Content:** 
  
      {
      	"temperaturas": []
      }

**Error Response:**

  * **Code:** 401 Unauthorized <br />
    **Content:** 
  
          {
            "message": "Unauthenticated."
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
              "message": "El usuario no cuenta con perfil de Encargada/Auxiliar o Supervisor."
            }
            
            
## Listado de temperaturas con alerta (supervisor)
Regresa el listado de las temperaturas registradas con alertas para editar/validar

 **URL**

    /api/sucursales/sucursales-temperaturas

 **Method:**

  `GET`
  
 **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data
      
       
 **Data Params**
    
    'tipo' => 'nullable|in:sucursal',
    'sucursal_id' => 'required_if:tipo,sucursal'
     
 **URL Params**

      - includes[] = sucursal
        Ejemplo URI: `api/sucursales/sucursales-temperaturas?includes[]=sucursal`

      - tipo = sucursal
        Devuelve todos los registros del mes de una sucursal
        Ejemplo URI: `api/sucursales/sucursales-temperaturas?tipo=sucursal&sucursal_id=4`
     

**Success Response:**

* **Code:** 200 <br />
  **Content:** 
  
      {
        "temperaturas": [
            {
              "id": 3,
              "sucursal_id": 4,
              "user_id": 13,
              "horario": 16,
              "temperatura_medio_ambiente": 10,
              "humedad_medio_ambiente": 20,
              "temperatura_refrigerador": 30,
              "alerta": 1,
              "alerta_campos": "temperatura_medio_ambiente",
              "alerta_at": "2019-07-02 18:34:15",
              "validado": 0,
              "validado_at": null,
              "error_operativo": true,
              "created_at": "2019-07-01 18:34:15",
              "updated_at": "2019-07-04 11:39:42",
              "deleted_at": null,
              "termometro_medio_ambiente": "\/storage\/sucursales\/termometros\/medio_ambiente\/2\/conversions\/45188042-7f447a00-b1f8-11e8-9737-4fcdf046c05a-normal.jpg",
              "termometro_refrigerador": "\/storage\/sucursales\/termometros\/refrigerador\/3\/conversions\/45188042-7f447a00-b1f8-11e8-9737-4fcdf046c05a-normal.jpg",
              "media": [
                {
                  "id": 2,
                  "model_type": "App\\Entities\\Sucursal\\SucursalTemperatura",
                  "model_id": 3,
                  "collection_name": "termometro_medio_ambiente",
                  "name": "45188042-7f447a00-b1f8-11e8-9737-4fcdf046c05a",
                  "file_name": "45188042-7f447a00-b1f8-11e8-9737-4fcdf046c05a.png",
                  "mime_type": "image\/png",
                  "disk": "termometros_medio_ambiente",
                  "size": 378090,
                  "manipulations": [],
                  "custom_properties": [],
                  "responsive_images": [],
                  "order_column": 2,
                  "created_at": "2019-07-02 18:34:15",
                  "updated_at": "2019-07-02 18:34:15"
                },
                {
                  "id": 3,
                  "model_type": "App\\Entities\\Sucursal\\SucursalTemperatura",
                  "model_id": 3,
                  "collection_name": "termometro_refrigerador",
                  "name": "45188042-7f447a00-b1f8-11e8-9737-4fcdf046c05a",
                  "file_name": "45188042-7f447a00-b1f8-11e8-9737-4fcdf046c05a.png",
                  "mime_type": "image\/png",
                  "disk": "termometros_refrigerador",
                  "size": 378090,
                  "manipulations": [],
                  "custom_properties": [],
                  "responsive_images": [],
                  "order_column": 3,
                  "created_at": "2019-07-02 18:34:15",
                  "updated_at": "2019-07-02 18:34:15"
                }
              ]
            }
        ]
      }

**Error Response:**

  * **Code:** 401 Unauthorized <br />
    **Content:** 
  
          {
            "message": "Unauthenticated."
          }  
          
   * **Code:** 406 Not Acceptable <br />
      **Content:** 
    
            {
              "message": "El usuario no cuenta con perfil de Encargada/Auxiliar o Supervisor."
            }
             
            
                    
## Detalle de temperatura
Regresa el registro de una temperatura

 **URL**

    /api/sucursales/sucursales-temperaturas/{ID}

 **Method:**

  `GET`
  
 **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data
     
 **URL Params**

      - includes[] = sucursal
        Ejemplo URI: `api/sucursales/sucursales-temperaturas/3?includes[]=sucursal`

**Success Response:**

* **Code:** 200 <br />
  **Content:** 
  
      {
        "temperatura": {
            "id": 3,
            "sucursal_id": 4,
            "user_id": 13,
            "horario": 16,
            "temperatura_medio_ambiente": 15,
            "humedad_medio_ambiente": 20,
            "temperatura_refrigerador": 30,
            "alerta": 1,
            "alerta_campos": "temperatura_medio_ambiente",
            "alerta_at": "2019-07-01 18:34:15",
            "validado": 1,
            "validado_at": "2019-07-04 12:27:17",
            "error_operativo": true,
            "created_at": "2019-07-01 18:34:15",
            "updated_at": "2019-07-04 12:27:17",
            "deleted_at": null,
            "termometro_medio_ambiente": "\/storage\/sucursales\/termometros\/medio_ambiente\/2\/conversions\/45188042-7f447a00-b1f8-11e8-9737-4fcdf046c05a-normal.jpg",
            "termometro_refrigerador": "\/storage\/sucursales\/termometros\/refrigerador\/3\/conversions\/45188042-7f447a00-b1f8-11e8-9737-4fcdf046c05a-normal.jpg",
            "sucursal": {
              "id": 4,
              "nombre": "gsdg",
              "codigo": "gdsfg",
              "direccion": "gfsdg",
              "lat": null,
              "lon": null,
              "meta_encargadas": 3,
              "meta_auxiliares": 3,
              "meta_cajeras": 3,
              "fondo_venta_mensual": null,
              "fondo_callcenter": 3,
              "matutino": 1,
              "vespertino": 1,
              "intermedio": 0,
              "fondo_asignado": 3333333,
              "created_at": "2019-06-25 18:07:37",
              "updated_at": "2019-06-25 18:07:37",
              "deleted_at": null
            },
            "media": [
              {
                "id": 2,
                "model_type": "App\\Entities\\Sucursal\\SucursalTemperatura",
                "model_id": 3,
                "collection_name": "termometro_medio_ambiente",
                "name": "45188042-7f447a00-b1f8-11e8-9737-4fcdf046c05a",
                "file_name": "45188042-7f447a00-b1f8-11e8-9737-4fcdf046c05a.png",
                "mime_type": "image\/png",
                "disk": "termometros_medio_ambiente",
                "size": 378090,
                "manipulations": [],
                "custom_properties": [],
                "responsive_images": [],
                "order_column": 2,
                "created_at": "2019-07-02 18:34:15",
                "updated_at": "2019-07-02 18:34:15"
              },
              {
                "id": 3,
                "model_type": "App\\Entities\\Sucursal\\SucursalTemperatura",
                "model_id": 3,
                "collection_name": "termometro_refrigerador",
                "name": "45188042-7f447a00-b1f8-11e8-9737-4fcdf046c05a",
                "file_name": "45188042-7f447a00-b1f8-11e8-9737-4fcdf046c05a.png",
                "mime_type": "image\/png",
                "disk": "termometros_refrigerador",
                "size": 378090,
                "manipulations": [],
                "custom_properties": [],
                "responsive_images": [],
                "order_column": 3,
                "created_at": "2019-07-02 18:34:15",
                "updated_at": "2019-07-02 18:34:15"
              }
            ]
        }
      }

**Error Response:**

  * **Code:** 401 Unauthorized <br />
    **Content:** 
  
          {
            "message": "Unauthenticated."
          }  

            
    
**Registro de temperatura**
----
  Regresa la información del registro en formato json

 **URL**

    /api/sucursales/sucursales-temperaturas

 **Method:**

  `POST`
  
  **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data

 
 **Data Params**
    
     'horario' => 'required|in:8,12,16,20',
     'sucursal_id' => 'required|exists:sucursales,id',
     'temperatura_medio_ambiente' => 'required|numeric|max:60',
     'humedad_medio_ambiente' => 'required|numeric|max:100',
     'temperatura_refrigerador' => 'required|numeric|max:50',
     'termometro_medio_ambiente' => 'required|image',
     'termometro_refrigerador' => 'required|image',
     'guardar' => 'required|boolean',


 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
            "sucursal_temperatura": {
                "sucursal_id": "4",
                "user_id": 13,
                "horario": "16",
                "temperatura_medio_ambiente": "10",
                "humedad_medio_ambiente": "20",
                "temperatura_refrigerador": "30",
                "alerta": true,
                "alerta_campos": "temperatura_medio_ambiente",
                "alerta_at": {
                  "date": "2019-07-02 18:34:15.440416",
                  "timezone_type": 3,
                  "timezone": "America\/Mexico_City"
                },
                "updated_at": "2019-07-02 18:34:15",
                "created_at": "2019-07-02 18:34:15",
                "id": 3,
                "error_operativo": true,
                "termometro_medio_ambiente": "\/storage\/sucursales\/termometros\/medio_ambiente\/2\/conversions\/45188042-7f447a00-b1f8-11e8-9737-4fcdf046c05a-normal.jpg",
                "termometro_refrigerador": "\/storage\/sucursales\/termometros\/refrigerador\/3\/conversions\/45188042-7f447a00-b1f8-11e8-9737-4fcdf046c05a-normal.jpg",
                "media": [
                  {
                    "id": 2,
                    "model_type": "App\\Entities\\Sucursal\\SucursalTemperatura",
                    "model_id": 3,
                    "collection_name": "termometro_medio_ambiente",
                    "name": "45188042-7f447a00-b1f8-11e8-9737-4fcdf046c05a",
                    "file_name": "45188042-7f447a00-b1f8-11e8-9737-4fcdf046c05a.png",
                    "mime_type": "image\/png",
                    "disk": "termometros_medio_ambiente",
                    "size": 378090,
                    "manipulations": [],
                    "custom_properties": [],
                    "responsive_images": [],
                    "order_column": 2,
                    "created_at": "2019-07-02 18:34:15",
                    "updated_at": "2019-07-02 18:34:15"
                  },
                  {
                    "id": 3,
                    "model_type": "App\\Entities\\Sucursal\\SucursalTemperatura",
                    "model_id": 3,
                    "collection_name": "termometro_refrigerador",
                    "name": "45188042-7f447a00-b1f8-11e8-9737-4fcdf046c05a",
                    "file_name": "45188042-7f447a00-b1f8-11e8-9737-4fcdf046c05a.png",
                    "mime_type": "image\/png",
                    "disk": "termometros_refrigerador",
                    "size": 378090,
                    "manipulations": [],
                    "custom_properties": [],
                    "responsive_images": [],
                    "order_column": 3,
                    "created_at": "2019-07-02 18:34:15",
                    "updated_at": "2019-07-02 18:34:15"
                  }
                ]
            }
        }
        
 
 **Error Response:**
 
  * **Code:** 401 Unauthorized <br />
    **Content:** 
  
          {
            "message": "Unauthenticated."
          }

  * **Code:** 422 Unprocessable Entity <br />
    **Content:** 
    
        {
            "horario": [
              "El campo horario es inválido."
            ]
            "sucursal_id": [
              "El campo sucursal id es obligatorio."
            ],
            "temperatura_medio_ambiente": [
              "El campo temperatura medio ambiente es obligatorio."
            ],
            "humedad_medio_ambiente": [
              "El campo humedad medio ambiente es obligatorio."
            ],
            "temperatura_refrigerador": [
              "El campo temperatura refrigerador es obligatorio."
            ],
            "termometro_medio_ambiente": [
              "El campo termometro medio ambiente es obligatorio."
            ],
            "termometro_refrigerador": [
              "El campo termometro refrigerador es obligatorio."
            ]
        }
        
  * **Code:** 408 Request Timeout <br />
  **Content:** 

        {
          "message": "Aún no es posible generar este registro."
        }

           
  * **Code:** 409 Conflict <br />
  **Content:** 

        {
          "message": "Algunos de los registros capturados está fuera de los rangos normales."
        }

           
  * **Code:** 410 Gone <br />
  **Content:** 

        {
          "message": "Ya fue generado este registro"
        }


          
    
**Editar registro de temperatura (supervisor)**
----
  Regresa la información del registro editado en formato json

 **URL**

    /api/sucursales/sucursales-temperaturas/{ID}

 **Method:**

  `PUT`
  
  **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data

 
 **Data Params**
    
     'horario' => 'required|in:8,12,16,20',
     'sucursal_id' => 'required|exists:sucursales,id',
     'temperatura_medio_ambiente' => 'required|numeric|max:60',
     'humedad_medio_ambiente' => 'required|numeric|max:100',
     'temperatura_refrigerador' => 'required|numeric|max:50',
     'termometro_medio_ambiente' => 'nullable|image',
     'termometro_refrigerador' => 'nullable|image',


 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
            "sucursal_temperatura": {
                "id": 3,
                "sucursal_id": "4",
                "user_id": 13,
                "horario": "16",
                "temperatura_medio_ambiente": "15",
                "humedad_medio_ambiente": "20",
                "temperatura_refrigerador": "30",
                "alerta": 1,
                "alerta_campos": "temperatura_medio_ambiente",
                "alerta_at": "2019-07-02 18:34:15",
                "validado": 0,
                "validado_at": null,
                "error_operativo": true,
                "created_at": "2019-07-01 18:34:15",
                "updated_at": "2019-07-04 11:39:42",
                "deleted_at": null,
                "termometro_medio_ambiente": "\/storage\/sucursales\/termometros\/medio_ambiente\/2\/conversions\/45188042-7f447a00-b1f8-11e8-9737-4fcdf046c05a-normal.jpg",
                "termometro_refrigerador": "\/storage\/sucursales\/termometros\/refrigerador\/3\/conversions\/45188042-7f447a00-b1f8-11e8-9737-4fcdf046c05a-normal.jpg",
                "media": [
                  {
                    "id": 2,
                    "model_type": "App\\Entities\\Sucursal\\SucursalTemperatura",
                    "model_id": 3,
                    "collection_name": "termometro_medio_ambiente",
                    "name": "45188042-7f447a00-b1f8-11e8-9737-4fcdf046c05a",
                    "file_name": "45188042-7f447a00-b1f8-11e8-9737-4fcdf046c05a.png",
                    "mime_type": "image\/png",
                    "disk": "termometros_medio_ambiente",
                    "size": 378090,
                    "manipulations": [],
                    "custom_properties": [],
                    "responsive_images": [],
                    "order_column": 2,
                    "created_at": "2019-07-02 18:34:15",
                    "updated_at": "2019-07-02 18:34:15"
                  },
                  {
                    "id": 3,
                    "model_type": "App\\Entities\\Sucursal\\SucursalTemperatura",
                    "model_id": 3,
                    "collection_name": "termometro_refrigerador",
                    "name": "45188042-7f447a00-b1f8-11e8-9737-4fcdf046c05a",
                    "file_name": "45188042-7f447a00-b1f8-11e8-9737-4fcdf046c05a.png",
                    "mime_type": "image\/png",
                    "disk": "termometros_refrigerador",
                    "size": 378090,
                    "manipulations": [],
                    "custom_properties": [],
                    "responsive_images": [],
                    "order_column": 3,
                    "created_at": "2019-07-02 18:34:15",
                    "updated_at": "2019-07-02 18:34:15"
                  }
                ]
            }
        }
        
 
 **Error Response:**
 
  * **Code:** 401 Unauthorized <br />
    **Content:** 
  
          {
            "message": "Unauthenticated."
          }

  * **Code:** 422 Unprocessable Entity <br />
    **Content:** 
    
        {
            "horario": [
              "El campo horario es inválido."
            ]
            "sucursal_id": [
              "El campo sucursal id es obligatorio."
            ],
            "temperatura_medio_ambiente": [
              "temperatura medio ambiente no debe ser mayor a 60."
            ]
            "humedad_medio_ambiente": [
              "El campo humedad medio ambiente es obligatorio."
            ],
            "temperatura_refrigerador": [
              "El campo temperatura refrigerador es obligatorio."
            ]
        }
        
  * **Code:** 406 Not Acceptable <br />
  **Content:** 

        {
          "message": "El usuario no cuenta con perfil de Supervisor."
        }

           
  * **Code:** 409 Conflict <br />
  **Content:** 

        {
          "message": "Algunos de los registros capturados está fuera de los rangos normales."
        }
        
        
          
**Validar registro de temperatura (supervisor)**
----
  Regresa la información del registro validado en formato json

 **URL**

    /api/sucursales/sucursales-temperaturas/{ID}/validar

 **Method:**

  `POST`
  
  **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data

 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
            "sucursal_temperatura": {
                "id": 3,
                "sucursal_id": 4,
                "user_id": 13,
                "horario": 16,
                "temperatura_medio_ambiente": 15,
                "humedad_medio_ambiente": 20,
                "temperatura_refrigerador": 30,
                "alerta": 1,
                "alerta_campos": "temperatura_medio_ambiente",
                "alerta_at": "2019-07-02 18:34:15",
                "validado": true,
                "validado_at": {
                  "date": "2019-07-04 12:26:29.443618",
                  "timezone_type": 3,
                  "timezone": "America\/Mexico_City"
                },
                "error_operativo": true,
                "created_at": "2019-07-01 18:34:15",
                "updated_at": "2019-07-04 12:26:29",
                "deleted_at": null,
                "termometro_medio_ambiente": "\/storage\/sucursales\/termometros\/medio_ambiente\/2\/conversions\/45188042-7f447a00-b1f8-11e8-9737-4fcdf046c05a-normal.jpg",
                "termometro_refrigerador": "\/storage\/sucursales\/termometros\/refrigerador\/3\/conversions\/45188042-7f447a00-b1f8-11e8-9737-4fcdf046c05a-normal.jpg",
                "media": [
                  {
                    "id": 2,
                    "model_type": "App\\Entities\\Sucursal\\SucursalTemperatura",
                    "model_id": 3,
                    "collection_name": "termometro_medio_ambiente",
                    "name": "45188042-7f447a00-b1f8-11e8-9737-4fcdf046c05a",
                    "file_name": "45188042-7f447a00-b1f8-11e8-9737-4fcdf046c05a.png",
                    "mime_type": "image\/png",
                    "disk": "termometros_medio_ambiente",
                    "size": 378090,
                    "manipulations": [],
                    "custom_properties": [],
                    "responsive_images": [],
                    "order_column": 2,
                    "created_at": "2019-07-02 18:34:15",
                    "updated_at": "2019-07-02 18:34:15"
                  },
                  {
                    "id": 3,
                    "model_type": "App\\Entities\\Sucursal\\SucursalTemperatura",
                    "model_id": 3,
                    "collection_name": "termometro_refrigerador",
                    "name": "45188042-7f447a00-b1f8-11e8-9737-4fcdf046c05a",
                    "file_name": "45188042-7f447a00-b1f8-11e8-9737-4fcdf046c05a.png",
                    "mime_type": "image\/png",
                    "disk": "termometros_refrigerador",
                    "size": 378090,
                    "manipulations": [],
                    "custom_properties": [],
                    "responsive_images": [],
                    "order_column": 3,
                    "created_at": "2019-07-02 18:34:15",
                    "updated_at": "2019-07-02 18:34:15"
                  }
                ]
            }
        }
        
 
 **Error Response:**
 
  * **Code:** 401 Unauthorized <br />
    **Content:** 
  
          {
            "message": "Unauthenticated."
          }

  * **Code:** 406 Not Acceptable <br />
  **Content:** 

        {
          "message": "El usuario no cuenta con perfil de Supervisor."
        }
        
        
           
**Generar reporte de registros de temperatura**
----
  Regresa la información de los registro enviados por mail en formato json

 **URL**

    /api/sucursales/sucursales-temperaturas/reporte

 **Method:**

  `POST`
  
  **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data
 
 **Data Params**
    
     'sucursal_id' => 'required|exists:sucursales,id',
     'fecha_inicio' => 'required|date|before:fecha_fin',
     'fecha_fin' => 'required|date|after:fecha_inicio',
     'enviar' => 'nullable|boolean',
     'tipo' => 'required|in:semana,quincena,mes,rango_fechas',


 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
            "sucursal_temperaturas": [
                {
                  "id": 3,
                  "sucursal_id": 4,
                  "user_id": 13,
                  "horario": 16,
                  "temperatura_medio_ambiente": 15,
                  "humedad_medio_ambiente": 20,
                  "temperatura_refrigerador": 30,
                  "alerta": 1,
                  "alerta_campos": "temperatura_medio_ambiente",
                  "alerta_at": "2019-07-01 18:34:15",
                  "validado": 1,
                  "validado_at": "2019-07-04 12:27:17",
                  "error_operativo": true,
                  "created_at": "2019-07-01 18:34:15",
                  "updated_at": "2019-07-04 12:27:17",
                  "deleted_at": null,
                  "termometro_medio_ambiente": "\/storage\/sucursales\/termometros\/medio_ambiente\/2\/conversions\/45188042-7f447a00-b1f8-11e8-9737-4fcdf046c05a-normal.jpg",
                  "termometro_refrigerador": "\/storage\/sucursales\/termometros\/refrigerador\/3\/conversions\/45188042-7f447a00-b1f8-11e8-9737-4fcdf046c05a-normal.jpg",
                  "sucursal": {
                    "id": 4,
                    "nombre": "gsdg",
                    "codigo": "gdsfg",
                    "direccion": "gfsdg",
                    "lat": null,
                    "lon": null,
                    "meta_encargadas": 3,
                    "meta_auxiliares": 3,
                    "meta_cajeras": 3,
                    "fondo_venta_mensual": null,
                    "fondo_callcenter": 3,
                    "matutino": 1,
                    "vespertino": 1,
                    "intermedio": 0,
                    "fondo_asignado": 3333333,
                    "created_at": "2019-06-25 18:07:37",
                    "updated_at": "2019-06-25 18:07:37",
                    "deleted_at": null
                  },
                  "user": {
                    "id": 13,
                    "nombre": "Encargada",
                    "apellidos": "Prueba",
                    "telefono": "5555555555",
                    "player_id": null,
                    "email": "encargada@farmapronto-sucursales.com",
                    "email_verified_at": null,
                    "created_at": "2019-06-27 17:59:19",
                    "updated_at": "2019-06-27 17:59:19",
                    "deleted_at": null
                  },
                  "media": [
                    {
                      "id": 2,
                      "model_type": "App\\Entities\\Sucursal\\SucursalTemperatura",
                      "model_id": 3,
                      "collection_name": "termometro_medio_ambiente",
                      "name": "45188042-7f447a00-b1f8-11e8-9737-4fcdf046c05a",
                      "file_name": "45188042-7f447a00-b1f8-11e8-9737-4fcdf046c05a.png",
                      "mime_type": "image\/png",
                      "disk": "termometros_medio_ambiente",
                      "size": 378090,
                      "manipulations": [],
                      "custom_properties": [],
                      "responsive_images": [],
                      "order_column": 2,
                      "created_at": "2019-07-02 18:34:15",
                      "updated_at": "2019-07-02 18:34:15"
                    },
                    {
                      "id": 3,
                      "model_type": "App\\Entities\\Sucursal\\SucursalTemperatura",
                      "model_id": 3,
                      "collection_name": "termometro_refrigerador",
                      "name": "45188042-7f447a00-b1f8-11e8-9737-4fcdf046c05a",
                      "file_name": "45188042-7f447a00-b1f8-11e8-9737-4fcdf046c05a.png",
                      "mime_type": "image\/png",
                      "disk": "termometros_refrigerador",
                      "size": 378090,
                      "manipulations": [],
                      "custom_properties": [],
                      "responsive_images": [],
                      "order_column": 3,
                      "created_at": "2019-07-02 18:34:15",
                      "updated_at": "2019-07-02 18:34:15"
                    }
                  ]
                },
                {
                  "id": 4,
                  "sucursal_id": 4,
                  "user_id": 13,
                  "horario": 12,
                  "temperatura_medio_ambiente": 10,
                  "humedad_medio_ambiente": 20,
                  "temperatura_refrigerador": 30,
                  "alerta": 1,
                  "alerta_campos": "temperatura_medio_ambiente",
                  "alerta_at": "2019-07-04 13:34:35",
                  "validado": 0,
                  "validado_at": null,
                  "error_operativo": true,
                  "created_at": "2019-07-04 13:34:35",
                  "updated_at": "2019-07-04 13:34:35",
                  "deleted_at": null,
                  "termometro_medio_ambiente": "\/storage\/sucursales\/termometros\/medio_ambiente\/4\/conversions\/45188042-7f447a00-b1f8-11e8-9737-4fcdf046c05a-normal.jpg",
                  "termometro_refrigerador": "\/storage\/sucursales\/termometros\/refrigerador\/5\/conversions\/45188042-7f447a00-b1f8-11e8-9737-4fcdf046c05a-normal.jpg",
                  "sucursal": {
                    "id": 4,
                    "nombre": "gsdg",
                    "codigo": "gdsfg",
                    "direccion": "gfsdg",
                    "lat": null,
                    "lon": null,
                    "meta_encargadas": 3,
                    "meta_auxiliares": 3,
                    "meta_cajeras": 3,
                    "fondo_venta_mensual": null,
                    "fondo_callcenter": 3,
                    "matutino": 1,
                    "vespertino": 1,
                    "intermedio": 0,
                    "fondo_asignado": 3333333,
                    "created_at": "2019-06-25 18:07:37",
                    "updated_at": "2019-06-25 18:07:37",
                    "deleted_at": null
                  },
                  "user": {
                    "id": 13,
                    "nombre": "Encargada",
                    "apellidos": "Prueba",
                    "telefono": "5555555555",
                    "player_id": null,
                    "email": "encargada@farmapronto-sucursales.com",
                    "email_verified_at": null,
                    "created_at": "2019-06-27 17:59:19",
                    "updated_at": "2019-06-27 17:59:19",
                    "deleted_at": null
                  },
                  "media": [
                    {
                      "id": 4,
                      "model_type": "App\\Entities\\Sucursal\\SucursalTemperatura",
                      "model_id": 4,
                      "collection_name": "termometro_medio_ambiente",
                      "name": "45188042-7f447a00-b1f8-11e8-9737-4fcdf046c05a",
                      "file_name": "45188042-7f447a00-b1f8-11e8-9737-4fcdf046c05a.png",
                      "mime_type": "image\/png",
                      "disk": "termometros_medio_ambiente",
                      "size": 378090,
                      "manipulations": [],
                      "custom_properties": [],
                      "responsive_images": [],
                      "order_column": 4,
                      "created_at": "2019-07-04 13:34:35",
                      "updated_at": "2019-07-04 13:34:35"
                    },
                    {
                      "id": 5,
                      "model_type": "App\\Entities\\Sucursal\\SucursalTemperatura",
                      "model_id": 4,
                      "collection_name": "termometro_refrigerador",
                      "name": "45188042-7f447a00-b1f8-11e8-9737-4fcdf046c05a",
                      "file_name": "45188042-7f447a00-b1f8-11e8-9737-4fcdf046c05a.png",
                      "mime_type": "image\/png",
                      "disk": "termometros_refrigerador",
                      "size": 378090,
                      "manipulations": [],
                      "custom_properties": [],
                      "responsive_images": [],
                      "order_column": 5,
                      "created_at": "2019-07-04 13:34:35",
                      "updated_at": "2019-07-04 13:34:35"
                    }
                  ]
                }
            ]
        }
        
 
 **Error Response:**
 
  * **Code:** 401 Unauthorized <br />
    **Content:** 
  
          {
            "message": "Unauthenticated."
          }

  * **Code:** 422 Unprocessable Entity <br />
    **Content:** 
    
        {
            "sucursal_id": [
              "El campo sucursal id es obligatorio."
            ],
            "fecha_inicio": [
               "El campo fecha inicio debe ser una fecha anterior a fecha fin."
            ],
            "fecha_fin": [
              "El campo fecha fin es obligatorio."
            ]
        }
        
        
               
**Obtiene rangos de fechas para generar reporte de registros de temperatura**
----
  Regresa las fechas para generar reportes de registros

 **URL**

    /api/sucursales/sucursales-temperaturas/reporte/fechas

 **Method:**

  `GET`
  
  **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data
 
 **Data Params**
    
     'tipo' => 'required|in:semana,quincena,mes'


 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
            "fechas": {
                "2019-07-01_2019-07-07": "Semana 27",
                "2019-07-08_2019-07-14": "Semana 28"
            }
        }
        
 
 **Error Response:**
 
  * **Code:** 401 Unauthorized <br />
    **Content:** 
  
          {
            "message": "Unauthenticated."
          }

  * **Code:** 422 Unprocessable Entity <br />
    **Content:** 
    
        {
            "tipo": [
              "El campo tipo es obligatorio."
            ]
        }
 
                 
                    
## Verifica registros de temperaturas pendientes
Usuarios *Encargada/Auxiliar* no podrán cerrar sesión hasta realizar todos los registros de temperaturas


 **URL**

    /api/sucursales/sucursales-temperaturas/pendientes

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
        "sucursal_temperaturas": []
      }

**Error Response:**

  * **Code:** 401 Unauthorized <br />
    **Content:** 
  
          {
            "message": "Unauthenticated."
          }  
          
     * **Code:** 409 Conflict <br />
     **Content:** 
   
           {
             "message": "¡Error! Hay registros de temperaturas pendientes, revisarlos."
           }
           
