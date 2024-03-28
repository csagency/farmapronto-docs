## Listado de fondos registrados (encargada/auxiliar)
Regresa el listado de los fondos registradas por la sucursal

 **URL**

    /api/sucursales/sucursales-fondos

 **Method:**

  `GET`
  
 **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data
      
      
 **Data Params**
    
     'tipo' => 'nullable|in:ultimo,dia',
     'horario' => 'nullable|in:7:30,14:30,21,20',
     'pendientes' => 'nullable|boolean',
     
 **URL Params**

      - includes[] = sucursal.fondo, estatus, estatus_registrado, estatus_entregado, estatus_confirmado
        Devuelve todos los registros de su sucursal asignada
        Ejemplo URI: `api/sucursales/sucursales-fondos?includes[]=sucursal`

      - tipo = dia
        Devuelve todos los registros del día de su sucursal asignada
        Ejemplo URI: `api/sucursales/sucursales-fondos?tipo=dia`
        
      - tipo = ultimo
        Devuelve el último registro de su sucursal asignada
        Ejemplo URI: `api/sucursales/sucursales-fondos?tipo=ultimo`
        
      - horario = 14:30
        Devuelve todos los registros del horario indicado de su sucursal asignada
        Ejemplo URI: `api/sucursales/sucursales-fondos?horario=14:30`

**Success Response:**

* **Code:** 200 <br />
  **Content:** 
  
      {
      	"fondos": []
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
            "pendientes": [
              "El campo pendientes debe tener un valor verdadero o falso."
            ]
        }
        
          
   * **Code:** 406 Not Acceptable <br />
      **Content:** 
    
            {
              "error": "El usuario no cuenta con perfil de Encargada/Auxiliar o Supervisor."
            }
            
            
## Listado de fondos sin entregar (supervisor)
Regresa el listado de los fondos registradas por entregar

 **URL**

    /api/sucursales/sucursales-fondos

 **Method:**

  `GET`
  
 **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data
      
       
 **Data Params**
    
    'tipo' => 'nullable|in:dia',
    'sucursal_id' => 'nullable',
    'horario' => 'nullable|in:7:30,14:30,21,20',
    'pendientes' => 'nullable|boolean',
     
 **URL Params**

      - includes[] = sucursal.fondo, estatus, estatus_registrado, estatus_entregado, estatus_confirmado
        Devuelve todos los registros del mes de todas las sucursales asignadas
        Ejemplo URI: `api/sucursales/sucursales-fondos?includes[]=sucursal`

      - sucursal_id = ID
        Devuelve todos los registros del mes de una sucursal en específico
        Ejemplo URI: `api/sucursales/sucursales-fondos?sucursal_id=4`
     
      - tipo = dia
        Devuelve todos los registros del día de todas las sucursales asignadas
        Ejemplo URI: `api/sucursales/sucursales-fondos?tipo=dia`
        
      - horario = 14:30
        Devuelve todos los registros del horario indicado
        Ejemplo URI: `api/sucursales/sucursales-fondos?horario=14:30`
        
        
      Registros del día en una sucursal y horario en específico
        api/sucursales/sucursales-fondos?sucursal_id=10&tipo=dia&horario=14:30&includes[]=sucursal.fondo
          

**Success Response:**

* **Code:** 200 <br />
  **Content:** 
  
      {
        "fondos": [
            {
              "id": 6,
              "sucursal_id": 10,
              "user_id": 13,
              "horario": "14:30:00",
              "cincuenta_centavos": 10000,
              "un_peso": 10000,
              "dos_pesos": 10000,
              "cinco_pesos": 10000,
              "diez_pesos": 10000,
              "veinte_pesos": 10000,
              "cincuenta_pesos": 10000,
              "cien_pesos": 10000,
              "doscientos_pesos": 10000,
              "quinientos_pesos": 10000,
              "mil_pesos": 10000,
              "vale": 10000,
              "gasto": 10000,
              "total": 110000,
              "error_operativo": 1,
              "created_at": "2019-11-12 14:35:28",
              "updated_at": "2019-11-12 13:35:28",
              "deleted_at": null,
              "evidencia": "\/storage\/sucursales\/fondos\/evidencias\/230\/35888217_2095034594077590_1878407717886885888_n.png",
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
                "fondo": {
                  "id": 1,
                  "sucursal_id": 10,
                  "cincuenta_centavos": 10000,
                  "un_peso": 10000,
                  "dos_pesos": 10000,
                  "cinco_pesos": 10000,
                  "diez_pesos": 10000,
                  "veinte_pesos": 10000,
                  "cincuenta_pesos": 10000,
                  "cien_pesos": 10000,
                  "doscientos_pesos": 10000,
                  "quinientos_pesos": 10000,
                  "mil_pesos": 10000,
                  "total": 110000,
                  "ultimo_horario": "21:00:00",
                  "created_at": null,
                  "updated_at": null,
                  "deleted_at": null
                }
              },
              "estatus": [],
              "media": [
                {
                  "id": 230,
                  "model_type": "App\\Entities\\Sucursal\\SucursalFondo",
                  "model_id": 6,
                  "collection_name": "evidencia",
                  "name": "35888217_2095034594077590_1878407717886885888_n",
                  "file_name": "35888217_2095034594077590_1878407717886885888_n.png",
                  "mime_type": "image\/png",
                  "disk": "evidencias_fondos",
                  "size": 652647,
                  "manipulations": [],
                  "custom_properties": [],
                  "responsive_images": [],
                  "order_column": 230,
                  "created_at": "2019-11-12 13:35:28",
                  "updated_at": "2019-11-12 13:35:28"
                }
              ]
            },
            {
              "id": 9,
              "sucursal_id": 5,
              "user_id": 13,
              "horario": "14:30:00",
              "cincuenta_centavos": 10000,
              "un_peso": 10000,
              "dos_pesos": 10000,
              "cinco_pesos": 10000,
              "diez_pesos": 10000,
              "veinte_pesos": 10000,
              "cincuenta_pesos": 10000,
              "cien_pesos": 10000,
              "doscientos_pesos": 10000,
              "quinientos_pesos": 10000,
              "mil_pesos": 10000,
              "vale": 10000,
              "gasto": 10000,
              "total": 110000,
              "error_operativo": 1,
              "created_at": "2019-11-12 18:57:58",
              "updated_at": "2019-11-12 18:57:58",
              "deleted_at": null,
              "evidencia": "\/storage\/sucursales\/fondos\/evidencias\/233\/35888217_2095034594077590_1878407717886885888_n.png",
              "sucursal": {
                "id": 5,
                "tipo_sucursal": null,
                "nombre": "BB",
                "codigo": "2",
                "direccion": "AV. INSURGENTES",
                "lat": "17.5628592",
                "lon": "-99.5080652",
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
                "fondo": null
              },
              "estatus": [],
              "media": [
                {
                  "id": 233,
                  "model_type": "App\\Entities\\Sucursal\\SucursalFondo",
                  "model_id": 9,
                  "collection_name": "evidencia",
                  "name": "35888217_2095034594077590_1878407717886885888_n",
                  "file_name": "35888217_2095034594077590_1878407717886885888_n.png",
                  "mime_type": "image\/png",
                  "disk": "evidencias_fondos",
                  "size": 652647,
                  "manipulations": [],
                  "custom_properties": [],
                  "responsive_images": [],
                  "order_column": 233,
                  "created_at": "2019-11-12 18:57:58",
                  "updated_at": "2019-11-12 18:57:58"
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
            "pendientes": [
              "El campo pendientes debe tener un valor verdadero o falso."
            ]
        }
        
        
   * **Code:** 406 Not Acceptable <br />
      **Content:** 
    
            {
              "error": "El usuario no cuenta con perfil de Encargada/Auxiliar o Supervisor."
            }
             
            
                    
## Detalle de registro de fondos
Regresa el registro de un fondo

 **URL**

    /api/sucursales/sucursales-fondos/{ID}

 **Method:**

  `GET`
  
 **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data
     
 **URL Params**

      - includes[] = sucursal.fondo, estatus, estatus_registrado, estatus_entregado, estatus_confirmado
        Ejemplo URI: `api/sucursales/sucursales-fondos/3?includes[]=sucursal`

**Success Response:**

* **Code:** 200 <br />
  **Content:** 
  
      {
         "fondo": {
             "id": 1,
             "sucursal_id": 10,
             "user_id": 13,
             "horario": "12:00:00",
             "cincuenta_centavos": 10000,
             "un_peso": 10000,
             "dos_pesos": 10000,
             "cinco_pesos": 10000,
             "diez_pesos": 10000,
             "veinte_pesos": 10000,
             "cincuenta_pesos": 10000,
             "cien_pesos": 10000,
             "doscientos_pesos": 10000,
             "quinientos_pesos": 10000,
             "mil_pesos": 10000,
             "vale": 10000,
             "gasto": 10000,
             "total": 110000,
             "error_operativo": 1,
             "created_at": "2019-10-15 18:05:32",
             "updated_at": "2019-11-06 12:20:25",
             "deleted_at": null,
             "evidencia": "\/storage\/sucursales\/fondos\/evidencias\/226\/45188042-7f447a00-b1f8-11e8-9737-4fcdf046c05a.png",
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
                 "id": 226,
                 "model_type": "App\\Entities\\Sucursal\\SucursalFondo",
                 "model_id": 1,
                 "collection_name": "evidencia",
                 "name": "45188042-7f447a00-b1f8-11e8-9737-4fcdf046c05a",
                 "file_name": "45188042-7f447a00-b1f8-11e8-9737-4fcdf046c05a.png",
                 "mime_type": "image\/png",
                 "disk": "evidencias_fondos",
                 "size": 378090,
                 "manipulations": [],
                 "custom_properties": [],
                 "responsive_images": [],
                 "order_column": 226,
                 "created_at": "2019-11-06 12:20:25",
                 "updated_at": "2019-11-06 12:20:25"
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

            
    
**Registro de fondo**
----
  Regresa la información del registro en formato json

 **URL**

    /api/sucursales/sucursales-fondos

 **Method:**

  `POST`
  
  **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data

 
 **Data Params**
    
     'sucursal_id' => 'required|exists:sucursales,id',
     'horario' => 'required|in:7:30,14:30,21,20',
     'evidencia' => 'required|image',
     'cincuenta_centavos' => 'required',
     'un_peso' => 'required',
     'dos_pesos' => 'required',
     'cinco_pesos' => 'required',
     'diez_pesos' => 'required',
     'veinte_pesos' => 'required',
     'cincuenta_pesos' => 'required',
     'cien_pesos' => 'required',
     'doscientos_pesos' => 'required',
     'quinientos_pesos' => 'required',
     'mil_pesos' => 'required',
     'vale' => 'required',
     'gasto' => 'required',
     'comentarios' => 'nullable',
     'tipo_fondo' 


 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
            "sucursal_fondo": {
                "sucursal_id": "10",
                "user_id": 13,
                "cincuenta_centavos": 10000,
                "un_peso": 10000,
                "dos_pesos": 10000,
                "cinco_pesos": 10000,
                "diez_pesos": 10000,
                "veinte_pesos": 10000,
                "cincuenta_pesos": 10000,
                "cien_pesos": 10000,
                "doscientos_pesos": 10000,
                "quinientos_pesos": 10000,
                "mil_pesos": 10000,
                "vale": 10000,
                "gasto": 10000,
                "updated_at": "2019-10-15 18:05:32",
                "created_at": "2019-10-15 18:05:32",
                "id": 1
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
            ]
            "cincuenta_centavos": [
              "El campo cincuenta centavos es obligatorio."
            ],
            "un_peso": [
              "El campo un peso es obligatorio."
            ],
            "dos_pesos": [
              "El campo dos pesos es obligatorio."
            ],
            "cinco_pesos": [
              "El campo cinco pesos es obligatorio."
            ],
            "diez_pesos": [
              "El campo diez pesos es obligatorio."
            ],
            "veinte_pesos": [
              "El campo veinte pesos es obligatorio."
            ],
            "cincuenta_pesos": [
              "El campo cincuenta pesos es obligatorio."
            ],
            "cien_pesos": [
              "El campo cien pesos es obligatorio."
            ],
            "doscientos_pesos": [
              "El campo doscientos pesos es obligatorio."
            ],
            "quinientos_pesos": [
              "El campo quinientos pesos es obligatorio."
            ],
            "mil_pesos": [
              "El campo mil pesos es obligatorio."
            ],
            "vale": [
              "El campo vale es obligatorio."
            ],
            "gasto": [
              "El campo gasto es obligatorio."
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
          "message": "Tu horario de último corte es incorrecto."
        }

           
  * **Code:** 410 Gone <br />
  **Content:** 

        {
          "message": "Ya fue generado este registro."
        }

    
**Editar registro de fondo (supervisor)**
----
  Regresa la información del registro editado en formato json

 **URL**

    /api/sucursales/sucursales-fondos/{ID}

 **Method:**

  `PUT`
  
  **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data

 
 **Data Params**
    
     'horario' => 'nullable|in:7:30,14:30,21,20',
     'evidencia' => 'nullable|image',
     'cincuenta_centavos' => 'nullable',
     'un_peso' => 'nullable',
     'dos_pesos' => 'nullable',
     'cinco_pesos' => 'nullable',
     'diez_pesos' => 'nullable',
     'veinte_pesos' => 'nullable',
     'cincuenta_pesos' => 'nullable',
     'cien_pesos' => 'nullable',
     'doscientos_pesos' => 'nullable',
     'quinientos_pesos' => 'nullable',
     'mil_pesos' => 'nullable',
     'vale' => 'nullable',
     'gasto' => 'nullable',
     'comentarios' => 'nullable',


 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
          "sucursal_fondo": {
              "id": 3,
              "sucursal_id": 10,
              "user_id": 13,
              "horario": "07:30:00",
              "cincuenta_centavos": 10000,
              "un_peso": 10000,
              "dos_pesos": 10000,
              "cinco_pesos": 10000,
              "diez_pesos": 10000,
              "veinte_pesos": 10000,
              "cincuenta_pesos": 10000,
              "cien_pesos": 10000,
              "doscientos_pesos": 10000,
              "quinientos_pesos": 10000,
              "mil_pesos": 10000,
              "vale": 10000,
              "gasto": 10000,
              "total": 110000,
              "error_operativo": 1,
              "created_at": "2019-11-06 11:42:07",
              "updated_at": "2019-11-06 12:20:40",
              "deleted_at": null,
              "evidencia": "\/storage\/sucursales\/fondos\/evidencias\/238\/45188042-7f447a00-b1f8-11e8-9737-4fcdf046c05a.png",
              "media": [
                {
                  "id": 238,
                  "model_type": "App\\Entities\\Sucursal\\SucursalFondo",
                  "model_id": 3,
                  "collection_name": "evidencia",
                  "name": "45188042-7f447a00-b1f8-11e8-9737-4fcdf046c05a",
                  "file_name": "45188042-7f447a00-b1f8-11e8-9737-4fcdf046c05a.png",
                  "mime_type": "image\/png",
                  "disk": "evidencias_fondos",
                  "size": 378090,
                  "manipulations": [],
                  "custom_properties": [],
                  "responsive_images": [],
                  "order_column": 238,
                  "created_at": "2019-11-14 17:15:47",
                  "updated_at": "2019-11-14 17:15:47"
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
            ]
        }
          
          
  * **Code:** 406 Not Acceptable <br />
  **Content:** 

        {
          "error": "El usuario no cuenta con perfil de Supervisor."
        }
        
          
**Realizar entrega de efectivo (supervisor)**
----
  Regresa la información del registro entregado en formato json

 **URL**

    /api/sucursales/sucursales-fondos/{ID}/entregar

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
            "sucursal_fondo": {
                "id": 12,
                "sucursal_id": 5,
                "user_id": 13,
                "horario": "14:30:00",
                "cincuenta_centavos": 10000,
                "un_peso": 10000,
                "dos_pesos": 10000,
                "cinco_pesos": 10000,
                "diez_pesos": 10000,
                "veinte_pesos": 10000,
                "cincuenta_pesos": 10000,
                "cien_pesos": 10000,
                "doscientos_pesos": 10000,
                "quinientos_pesos": 10000,
                "mil_pesos": 10000,
                "vale": 10000,
                "gasto": 10000,
                "total": 110000,
                "error_operativo": 1,
                "created_at": "2019-11-14 16:47:00",
                "updated_at": "2019-11-14 16:47:00",
                "deleted_at": null,
                "evidencia": "\/storage\/sucursales\/fondos\/evidencias\/236\/35888217_2095034594077590_1878407717886885888_n.png",
                "estatus": [
                  {
                    "id": 1,
                    "nombre": "Registrado",
                    "key": "registrado",
                    "created_at": "2019-11-14 16:45:43",
                    "updated_at": "2019-11-14 16:45:43",
                    "deleted_at": null,
                    "pivot": {
                      "fondo_id": 12,
                      "estatus_id": 1,
                      "user_id": 13,
                      "created_at": "2019-11-14 16:47:00",
                      "updated_at": "2019-11-14 16:47:00"
                    }
                  },
                  {
                    "id": 2,
                    "nombre": "Entregado",
                    "key": "entregado",
                    "created_at": "2019-11-14 16:45:43",
                    "updated_at": "2019-11-14 16:45:43",
                    "deleted_at": null,
                    "pivot": {
                      "fondo_id": 12,
                      "estatus_id": 2,
                      "user_id": 17,
                      "created_at": "2019-11-14 16:59:09",
                      "updated_at": "2019-11-14 16:59:09"
                    }
                  }
                ],
                "media": [
                  {
                    "id": 236,
                    "model_type": "App\\Entities\\Sucursal\\SucursalFondo",
                    "model_id": 12,
                    "collection_name": "evidencia",
                    "name": "35888217_2095034594077590_1878407717886885888_n",
                    "file_name": "35888217_2095034594077590_1878407717886885888_n.png",
                    "mime_type": "image\/png",
                    "disk": "evidencias_fondos",
                    "size": 652647,
                    "manipulations": [],
                    "custom_properties": [],
                    "responsive_images": [],
                    "order_column": 236,
                    "created_at": "2019-11-14 16:47:00",
                    "updated_at": "2019-11-14 16:47:00"
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
          "error": "El usuario no cuenta con perfil de Supervisor."
        }
       
          
**Confirmar entrega de efectivo (encargada/auxiliar)**
----
  Regresa la información del registro confirmado en formato json

 **URL**

    /api/sucursales/sucursales-fondos/{ID}/confirmar

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
            "sucursal_fondo": {
                "id": 12,
                "sucursal_id": 5,
                "user_id": 13,
                "horario": "14:30:00",
                "cincuenta_centavos": 10000,
                "un_peso": 10000,
                "dos_pesos": 10000,
                "cinco_pesos": 10000,
                "diez_pesos": 10000,
                "veinte_pesos": 10000,
                "cincuenta_pesos": 10000,
                "cien_pesos": 10000,
                "doscientos_pesos": 10000,
                "quinientos_pesos": 10000,
                "mil_pesos": 10000,
                "vale": 10000,
                "gasto": 10000,
                "total": 110000,
                "error_operativo": 1,
                "created_at": "2019-11-14 16:47:00",
                "updated_at": "2019-11-14 16:47:00",
                "deleted_at": null,
                "evidencia": "\/storage\/sucursales\/fondos\/evidencias\/236\/35888217_2095034594077590_1878407717886885888_n.png",
                "estatus": [
                  {
                    "id": 1,
                    "nombre": "Registrado",
                    "key": "registrado",
                    "created_at": "2019-11-14 16:45:43",
                    "updated_at": "2019-11-14 16:45:43",
                    "deleted_at": null,
                    "pivot": {
                      "fondo_id": 12,
                      "estatus_id": 1,
                      "user_id": 13,
                      "created_at": "2019-11-14 16:47:00",
                      "updated_at": "2019-11-14 16:47:00"
                    }
                  },
                  {
                    "id": 2,
                    "nombre": "Entregado",
                    "key": "entregado",
                    "created_at": "2019-11-14 16:45:43",
                    "updated_at": "2019-11-14 16:45:43",
                    "deleted_at": null,
                    "pivot": {
                      "fondo_id": 12,
                      "estatus_id": 2,
                      "user_id": 17,
                      "created_at": "2019-11-14 16:59:09",
                      "updated_at": "2019-11-14 16:59:09"
                    }
                  },
                  {
                    "id": 3,
                    "nombre": "Confirmado",
                    "key": "confirmado",
                    "created_at": "2019-11-14 16:45:43",
                    "updated_at": "2019-11-14 16:45:43",
                    "deleted_at": null,
                    "pivot": {
                      "fondo_id": 12,
                      "estatus_id": 3,
                      "user_id": 13,
                      "created_at": "2019-11-14 17:00:13",
                      "updated_at": "2019-11-14 17:00:13"
                    }
                  }
                ],
                "media": [
                  {
                    "id": 236,
                    "model_type": "App\\Entities\\Sucursal\\SucursalFondo",
                    "model_id": 12,
                    "collection_name": "evidencia",
                    "name": "35888217_2095034594077590_1878407717886885888_n",
                    "file_name": "35888217_2095034594077590_1878407717886885888_n.png",
                    "mime_type": "image\/png",
                    "disk": "evidencias_fondos",
                    "size": 652647,
                    "manipulations": [],
                    "custom_properties": [],
                    "responsive_images": [],
                    "order_column": 236,
                    "created_at": "2019-11-14 16:47:00",
                    "updated_at": "2019-11-14 16:47:00"
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
          "error": "El usuario no cuenta con perfil de Encargada/Auxiliar."
        }


## Es hora de hacer corte de fondo
Regresa una bandera para saber si ya es hora de hacer el corte de fondo

**URL**

    /api/sucursales/sucursales-fondos/registrarCorteFondo/{sucursal_id}

**Method:**

`GET`

**Headers**

      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data


**Data Params**

     N/A

**URL Params**

      N/A

**Success Response:**

* **Code:** 200 <br />
  **Content:**

      {
        "hora_fondo": {
          "registrar_corte_fondo": true,
          "tipo_corte_fondo": "informativo"
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
           "error": "Error, no se encuentra la configuración de corte de fondo de la sucursal con id: {sucursal_id}
         }


## Listado de cortes de fondo con diferencia y sin comentarios
Regresa un listado de cortes de fondo con una diferencia de $300 entre el total del corte y lo configurado y que no tenga comentarios.

**URL**

    /api/sucursales/sucursales-fondos/getListSucursalFondoWithDiferencia

**Method:**

`GET`

**Headers**

      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data


**Data Params**

     N/A

**URL Params**

      N/A

**Success Response:**

* **Code:** 200 <br />
  **Content:**

      {
        "listSucursalesFondo": []
      }

**Error Response:**

* **Code:** 401 Unauthorized <br />
  **Content:**

        {
          "error": "Unauthenticated."
        }


## Agregar comentario del supervisor
Agrega el comentario de un supervisor a un corte de fondo

**URL**

    /api/sucursales/sucursales-fondos/storeComentario

**Method:**

`POST`

**Headers**

      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data


**Data Params**

    'sucursal_fondo_id' => 'required|exists:sucursales_fondos,id',
    'user_id' => 'required|exists:users,id',
    'comentario' => 'required|max:255',

**URL Params**

      N/A

**Success Response:**

* **Code:** 200 <br />
  **Content:**

      {
        "mensaje": "comentarios actualizados con éxito"
      }

**Error Response:**

* **Code:** 401 Unauthorized <br />
  **Content:**

        {
          "error": "Unauthenticated."
        }


## Tiene corte de fondo del día
Regresa una bandera que indica la sucursal ya realizo su corte de fondo del día

**URL**

    /api/sucursales/sucursales-fondos/hasSucursalFondoToday/{sucursal_id}

**Method:**

`GET`

**Headers**

      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data


**Data Params**

     N/A

**URL Params**

      N/A

**Success Response:**

* **Code:** 200 <br />
  **Content:**

      {
        "sucursal_fondos_today": {
          "registrar_corte_fondo_real": true,
          "registrar_corte_fondo_informativo": true
        }
      }

**Error Response:**

* **Code:** 401 Unauthorized <br />
  **Content:**

        {
          "error": "Unauthenticated."
        }
