## Listado de incidencias
- Regresa el listado de las incidencias realizados por el usuario logueado (Encargada)<br>
- Regresa el listado de todas las incidencias registradas (Soporte y Supervisor)

 **URL**

    /api/incidencias-soporte

 **Method:**

  `GET`
  
 **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data
      
       
 **Data Params**
    
    'motivo_id' => 'nullable|exists:catalogo_motivos_incidencias_soporte,id'
     
 **URL Params**

      - motivo_id = 1
        Ejemplo URI: `api/incidencias-soporte?motivo_id=1`
     

**Success Response:**

* **Code:** 200 <br />
  **Content:** 
  
      {
            "incidencias": []
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
            "motivo_id": [
              "El campo motivo id es inválido."
            ]
        }
        
          
  * **Code:** 406 Not Acceptable <br />
    **Content:** 
    
        {
          "error": "El usuario no cuenta con perfil de Encargada, Supervisor o Soporte."
        }
             
            
                    
## Detalle de incidencia
Regresa el registro de un incidencia

 **URL**

    /api/incidencias-soporte/{ID}

 **Method:**

  `GET`
  
 **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data
     
 **URL Params**

      - includes[] = sucursal, user.perfilEncargada, motivo, estatus, equipos
        Ejemplo URI: `api/incidencias-soporte/1?includes[]=equipos`

**Success Response:**

* **Code:** 200 <br />
  **Content:** 
  
      {
           "incidencia": {
               "id": 1,
               "folio": "CS001",
               "sucursal_id": 3,
               "user_id": 13,
               "motivo_id": 1,
               "fecha": "2020-08-10",
               "observaciones": null,
               "tipo_creacion": "api_store",
               "created_at": "2020-08-10 19:06:41",
               "updated_at": "2020-08-10 19:06:43",
               "deleted_at": null,
               "equipos": [
                 {
                   "id": 1,
                   "incidencia_id": 1,
                   "tipo": "reemplazado",
                   "nombre_equipo": "Computadora",
                   "marca": "apple",
                   "num_serie": "1234567890",
                   "num_inventario": "1234567890",
                   "aprobado_por": "CS admin",
                   "comentarios": "pruebas",
                   "created_at": "2020-08-10 19:06:41",
                   "updated_at": "2020-08-10 19:06:41",
                   "deleted_at": null,
                   "evidencia": "https:\/\/sfo2.digitaloceanspaces.com\/farmapronto-sucursales\/incidencias\/equipos\/19\/Farma3.jpg",
                   "media": [
                     {
                       "id": 19,
                       "model_type": "App\\Entities\\IncidenciasSoporte\\IncidenciaSoporteEquipo",
                       "model_id": 1,
                       "collection_name": "evidencia",
                       "name": "Farma3",
                       "file_name": "Farma3.jpg",
                       "mime_type": "image\/jpeg",
                       "disk": "incidencias_equipos",
                       "size": 183092,
                       "manipulations": [],
                       "custom_properties": [],
                       "responsive_images": [],
                       "order_column": 19,
                       "created_at": "2020-08-10 19:06:41",
                       "updated_at": "2020-08-10 19:06:41"
                     }
                   ]
                 }
               ],
               "sucursal": {
                 "id": 3,
                 "tipo_sucursal": null,
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
               }
           }
      }

**Error Response:**

  * **Code:** 401 Unauthorized <br />
    **Content:** 
  
          {
            "error": "Unauthenticated."
          }  

 
**Registro de incidencia (Encargada)**
----
  Regresa la información del registro en formato json

 **URL**

    /api/incidencias-soporte

 **Method:**

  `POST`
  
  **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data

 
 **Data Params**
    
     'motivo_id' => 'required|exists:catalogo_motivos_incidencias_soporte,id',
     'sucursal_id' => 'required|exists:sucursales,id',
     'observaciones' => 'nullable',
     'evidencia' => 'required|image',
     'nombre_equipo' => 'required',
     'marca' => 'required',
     'num_serie' => 'required',
     'num_inventario' => 'required',
     'aprobado_por' => 'required',
     'comentarios' => 'nullable',


 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
            "incidencia": {
                "sucursal_id": "3",
                "motivo_id": "1",
                "fecha": "2020-08-10",
                "user_id": 13,
                "tipo_creacion": "api_store",
                "updated_at": "2020-08-10 19:28:24",
                "created_at": "2020-08-10 19:28:22",
                "id": 2,
                "folio": "CS002",
                "motivo": {
                  "id": 1,
                  "nombre": "Pruebas CS",
                  "key": "pruebas-cs",
                  "prefix": "CS",
                  "created_at": "2020-08-10 16:41:18",
                  "updated_at": "2020-08-10 16:41:18",
                  "deleted_at": null
                },
                "user": {
                  "id": 13,
                  "nombre": "Encargada",
                  "apellido_paterno": "Prueba",
                  "apellido_materno": "Prueba",
                  "telefono": "5555555555",
                  "player_id": null,
                  "email": "encargada@farmapronto-sucursales.com",
                  "old_email": null,
                  "email_verified_at": null,
                  "cant_errores_actuales": 0,
                  "created_at": "2019-06-27 17:59:19",
                  "updated_at": "2019-11-12 10:55:03",
                  "deleted_at": null,
                  "perfil_encargada": {
                    "id": 2,
                    "user_id": 13,
                    "sucursal_id": 10,
                    "created_at": "2019-06-27 17:59:19",
                    "updated_at": "2019-11-12 13:43:09",
                    "deleted_at": null
                  }
                },
                "estatus": [
                  {
                    "id": 1,
                    "nombre": "Registrada",
                    "key": "registrada",
                    "created_at": "2020-08-10 17:13:12",
                    "updated_at": "2020-08-10 17:13:12",
                    "deleted_at": null,
                    "pivot": {
                      "incidencia_id": 2,
                      "estatus_id": 1,
                      "user_id": 13,
                      "created_at": "2020-08-10 19:28:24",
                      "updated_at": "2020-08-10 19:28:24"
                    }
                  }
                ],
                "sucursal": {
                  "id": 3,
                  "tipo_sucursal": null,
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
                "equipos": [
                  {
                    "id": 3,
                    "incidencia_id": 2,
                    "tipo": "reemplazado",
                    "nombre_equipo": "Computadora",
                    "marca": "apple",
                    "num_serie": "1234567890",
                    "num_inventario": "1234567890",
                    "aprobado_por": "CS admin",
                    "comentarios": "pruebas",
                    "created_at": "2020-08-10 19:28:22",
                    "updated_at": "2020-08-10 19:28:22",
                    "deleted_at": null,
                    "evidencia": "https:\/\/sfo2.digitaloceanspaces.com\/farmapronto-sucursales\/incidencias\/equipos\/21\/Farma3.jpg",
                    "media": [
                      {
                        "id": 21,
                        "model_type": "App\\Entities\\IncidenciasSoporte\\IncidenciaSoporteEquipo",
                        "model_id": 3,
                        "collection_name": "evidencia",
                        "name": "Farma3",
                        "file_name": "Farma3.jpg",
                        "mime_type": "image\/jpeg",
                        "disk": "incidencias_equipos",
                        "size": 183092,
                        "manipulations": [],
                        "custom_properties": [],
                        "responsive_images": [],
                        "order_column": 21,
                        "created_at": "2020-08-10 19:28:22",
                        "updated_at": "2020-08-10 19:28:22"
                      }
                    ]
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
            "motivo_id": [
              "El campo motivo id es obligatorio."
            ],
            "sucursal_id": [
              "El campo sucursal id es obligatorio."
            ],
            "evidencia": [
              "El campo evidencia es obligatorio."
            ],
            "nombre_equipo": [
              "El campo nombre equipo es obligatorio."
            ],
            "marca": [
              "El campo marca es obligatorio."
            ],
            "num_serie": [
              "El campo num serie es obligatorio."
            ],
            "num_inventario": [
              "El campo num inventario es obligatorio."
            ],
            "aprobado_por": [
              "El campo aprobado por es obligatorio."
            ],
            "comentarios": [
              "El campo comentarios es obligatorio."
            ]
        } 
                  
* **Code:** 406 Not Acceptable <br />
**Content:** 

      {
        "error": "El usuario no cuenta con perfil de Encargada"
      } 
          
## Marcar como Aprobada/Rechazada (Soporte)
Regresa la información de la incidencia actualizada

**URL**
  
    /api/incidencias-soporte/{ID}/aprobar
  
**Method:**

`POST`

**Headers**

      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data

**Data Params**
    
    'estatus' => 'required|in:aprobada,rechazada',
    'razon_rechazo' => 'required_if:estatus,rechazada',
    'evidencia' => 'required_if:estatus,aprobada|image',
    'nombre_equipo' => 'required_if:estatus,aprobada',
    'marca' => 'required_if:estatus,aprobada',
    'num_serie' => 'required_if:estatus,aprobada',
    'num_inventario' => 'required_if:estatus,aprobada',
    'comentarios' => 'nullable',
    
    
**Success Response:**

* **Code:** 200 <br />
  **Content:**
      
      {
         "incidencia": {
             "id": 1,
             "folio": "CS001",
             "sucursal_id": 3,
             "user_id": 13,
             "motivo_id": 1,
             "fecha": "2020-08-10",
             "observaciones": null,
             "tipo_creacion": "api_store",
             "razon_rechazo": null,
             "created_at": "2020-08-10 19:06:41",
             "updated_at": "2020-08-10 19:06:43",
             "deleted_at": null,
             "estatus": [
               {
                 "id": 1,
                 "nombre": "Registrada",
                 "key": "registrada",
                 "created_at": "2020-08-10 17:13:12",
                 "updated_at": "2020-08-10 17:13:12",
                 "deleted_at": null,
                 "pivot": {
                   "incidencia_id": 1,
                   "estatus_id": 1,
                   "user_id": 13,
                   "created_at": "2020-08-10 19:06:43",
                   "updated_at": "2020-08-10 19:06:43"
                 }
               },
               {
                 "id": 2,
                 "nombre": "Aprobada",
                 "key": "aprobada",
                 "created_at": "2020-08-10 17:13:12",
                 "updated_at": "2020-08-10 17:13:12",
                 "deleted_at": null,
                 "pivot": {
                   "incidencia_id": 1,
                   "estatus_id": 2,
                   "user_id": 6,
                   "created_at": "2020-08-10 19:26:52",
                   "updated_at": "2020-08-10 19:26:52"
                 }
               },
               {
                   "id": 4,
                   "nombre": "Equipo asignado",
                   "key": "equipo-asignado",
                   "created_at": "2020-08-10 17:13:12",
                   "updated_at": "2020-08-10 17:13:12",
                   "deleted_at": null,
                   "pivot": {
                     "incidencia_id": 2,
                     "estatus_id": 4,
                     "user_id": 6,
                     "created_at": "2020-08-10 19:29:10",
                     "updated_at": "2020-08-10 19:29:10"
                   }
               }
             ],
             "user": {
               "id": 13,
               "nombre": "Encargada",
               "apellido_paterno": "Prueba",
               "apellido_materno": "Prueba",
               "telefono": "5555555555",
               "player_id": null,
               "email": "encargada@farmapronto-sucursales.com",
               "old_email": null,
               "email_verified_at": null,
               "cant_errores_actuales": 0,
               "created_at": "2019-06-27 17:59:19",
               "updated_at": "2019-11-12 10:55:03",
               "deleted_at": null
             },
             "motivo": {
               "id": 1,
               "nombre": "Pruebas CS",
               "key": "pruebas-cs",
               "prefix": "CS",
               "created_at": "2020-08-10 16:41:18",
               "updated_at": "2020-08-10 16:41:18",
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
      
         
  * **Code:** 422 Unprocessable Entity <br />
    **Content:** 
    
        {
            "estatus": [
              "El campo estatus es obligatorio."
            ],
            "evidencia": [
              "El campo evidencia es obligatorio cuando estatus es aprobada."
            ],
            "nombre_equipo": [
              "El campo nombre equipo es obligatorio cuando estatus es aprobada."
            ],
            "marca": [
              "El campo marca es obligatorio cuando estatus es aprobada."
            ],
            "num_serie": [
              "El campo num serie es obligatorio cuando estatus es aprobada."
            ],
            "num_inventario": [
              "El campo num inventario es obligatorio cuando estatus es aprobada."
            ],
            "comentarios": [
              "El campo comentarios es obligatorio cuando estatus es aprobada."
            ]
            "razon_rechazo": [
              "El campo razon rechazo es obligatorio cuando estatus es rechazada."
            ]
        }
        
          
* **Code:** 406 Not Acceptable <br />
**Content:** 

      {
        "error": "El usuario no cuenta con perfil de Soporte"
      }


   
## Marcar como En tránsito/ Entregado/ Devolución (Supervisor)
Regresa la información de la incidencia actualizada

**URL**
  
    /api/incidencias-soporte/{ID}/estatus
  
**Method:**

`POST`

**Headers**

      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data

**Data Params**
    
    'estatus' => 'required|in:en-transito,entregado,embarcado,devolucion,finalizado',
    
    
**Success Response:**

* **Code:** 200 <br />
  **Content:**
      
      {
         "incidencia": {
             "id": 2,
             "folio": "CS002",
             "sucursal_id": 3,
             "user_id": 13,
             "motivo_id": 1,
             "fecha": "2020-08-10",
             "observaciones": null,
             "tipo_creacion": "api_store",
             "razon_rechazo": null,
             "created_at": "2020-08-10 19:28:22",
             "updated_at": "2020-08-10 19:28:24",
             "deleted_at": null,
             "user": {
               "id": 13,
               "nombre": "Encargada",
               "apellido_paterno": "Prueba",
               "apellido_materno": "Prueba",
               "telefono": "5555555555",
               "player_id": null,
               "email": "encargada@farmapronto-sucursales.com",
               "old_email": null,
               "email_verified_at": null,
               "cant_errores_actuales": 0,
               "created_at": "2019-06-27 17:59:19",
               "updated_at": "2019-11-12 10:55:03",
               "deleted_at": null
             },
             "estatus": [
               {
                 "id": 1,
                 "nombre": "Registrada",
                 "key": "registrada",
                 "created_at": "2020-08-10 17:13:12",
                 "updated_at": "2020-08-10 17:13:12",
                 "deleted_at": null,
                 "pivot": {
                   "incidencia_id": 2,
                   "estatus_id": 1,
                   "user_id": 13,
                   "created_at": "2020-08-10 19:28:24",
                   "updated_at": "2020-08-10 19:28:24"
                 }
               },
               {
                 "id": 2,
                 "nombre": "Aprobada",
                 "key": "aprobada",
                 "created_at": "2020-08-10 17:13:12",
                 "updated_at": "2020-08-10 17:13:12",
                 "deleted_at": null,
                 "pivot": {
                   "incidencia_id": 2,
                   "estatus_id": 2,
                   "user_id": 6,
                   "created_at": "2020-08-10 19:33:00",
                   "updated_at": "2020-08-10 19:33:00"
                 }
               },
               {
                 "id": 4,
                 "nombre": "Equipo asignado",
                 "key": "equipo-asignado",
                 "created_at": "2020-08-10 17:13:12",
                 "updated_at": "2020-08-10 17:13:12",
                 "deleted_at": null,
                 "pivot": {
                   "incidencia_id": 2,
                   "estatus_id": 4,
                   "user_id": 6,
                   "created_at": "2020-08-10 19:33:38",
                   "updated_at": "2020-08-10 19:33:33"
                 }
               },
               {
                 "id": 5,
                 "nombre": "En tránsito",
                 "key": "en-transito",
                 "created_at": "2020-08-10 17:13:12",
                 "updated_at": "2020-08-10 17:13:12",
                 "deleted_at": null,
                 "pivot": {
                   "incidencia_id": 2,
                   "estatus_id": 5,
                   "user_id": 433,
                   "created_at": "2020-08-10 21:54:16",
                   "updated_at": "2020-08-10 21:54:16"
                 }
               }
             ],
             "motivo": {
               "id": 1,
               "nombre": "Pruebas CS",
               "key": "pruebas-cs",
               "prefix": "CS",
               "created_at": "2020-08-10 16:41:18",
               "updated_at": "2020-08-10 16:41:18",
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
      
         
  * **Code:** 422 Unprocessable Entity <br />
    **Content:** 
    
        {
            "estatus": [
              "El campo estatus es obligatorio."
            ]
        }
        
          
* **Code:** 406 Not Acceptable <br />
**Content:** 

      {
        "error": "El usuario no cuenta con perfil de Supervisor"
      }


   
## Marcar como Embarcado (Encargada)
Regresa la información de la incidencia actualizada

**URL**
  
    /api/incidencias-soporte/{ID}/estatus
  
**Method:**

`POST`

**Headers**

      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data

**Data Params**
    
    'estatus' => 'required|in:embarcado',
    
    
**Success Response:**

* **Code:** 200 <br />
  **Content:**
      
      {
         "incidencia": {
             "id": 2,
             "folio": "CS002",
             "sucursal_id": 3,
             "user_id": 13,
             "motivo_id": 1,
             "fecha": "2020-08-10",
             "observaciones": null,
             "tipo_creacion": "api_store",
             "razon_rechazo": null,
             "created_at": "2020-08-10 19:28:22",
             "updated_at": "2020-08-10 19:28:24",
             "deleted_at": null,
             "sucursal": {
               "id": 3,
               "tipo_sucursal": null,
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
             "estatus": [
               {
                 "id": 1,
                 "nombre": "Registrada",
                 "key": "registrada",
                 "created_at": "2020-08-10 17:13:12",
                 "updated_at": "2020-08-10 17:13:12",
                 "deleted_at": null,
                 "pivot": {
                   "incidencia_id": 2,
                   "estatus_id": 1,
                   "user_id": 13,
                   "created_at": "2020-08-10 19:28:24",
                   "updated_at": "2020-08-10 19:28:24"
                 }
               },
               {
                 "id": 2,
                 "nombre": "Aprobada",
                 "key": "aprobada",
                 "created_at": "2020-08-10 17:13:12",
                 "updated_at": "2020-08-10 17:13:12",
                 "deleted_at": null,
                 "pivot": {
                   "incidencia_id": 2,
                   "estatus_id": 2,
                   "user_id": 6,
                   "created_at": "2020-08-10 19:33:00",
                   "updated_at": "2020-08-10 19:33:00"
                 }
               },
               {
                 "id": 4,
                 "nombre": "Equipo asignado",
                 "key": "equipo-asignado",
                 "created_at": "2020-08-10 17:13:12",
                 "updated_at": "2020-08-10 17:13:12",
                 "deleted_at": null,
                 "pivot": {
                   "incidencia_id": 2,
                   "estatus_id": 4,
                   "user_id": 6,
                   "created_at": "2020-08-10 19:33:38",
                   "updated_at": "2020-08-10 19:33:33"
                 }
               },
               {
                 "id": 5,
                 "nombre": "En tránsito",
                 "key": "en-transito",
                 "created_at": "2020-08-10 17:13:12",
                 "updated_at": "2020-08-10 17:13:12",
                 "deleted_at": null,
                 "pivot": {
                   "incidencia_id": 2,
                   "estatus_id": 5,
                   "user_id": 433,
                   "created_at": "2020-08-10 21:54:16",
                   "updated_at": "2020-08-10 21:54:16"
                 }
               },
               {
                 "id": 6,
                 "nombre": "Entregado",
                 "key": "entregado",
                 "created_at": "2020-08-10 17:13:12",
                 "updated_at": "2020-08-10 17:13:12",
                 "deleted_at": null,
                 "pivot": {
                   "incidencia_id": 2,
                   "estatus_id": 6,
                   "user_id": 433,
                   "created_at": "2020-08-10 21:55:15",
                   "updated_at": "2020-08-10 21:55:15"
                 }
               },
               {
                 "id": 7,
                 "nombre": "Embarcado",
                 "key": "embarcado",
                 "created_at": "2020-08-10 17:13:12",
                 "updated_at": "2020-08-10 17:13:12",
                 "deleted_at": null,
                 "pivot": {
                   "incidencia_id": 2,
                   "estatus_id": 7,
                   "user_id": 13,
                   "created_at": "2020-08-10 21:55:56",
                   "updated_at": "2020-08-10 21:55:56"
                 }
               }
             ],
             "motivo": {
               "id": 1,
               "nombre": "Pruebas CS",
               "key": "pruebas-cs",
               "prefix": "CS",
               "created_at": "2020-08-10 16:41:18",
               "updated_at": "2020-08-10 16:41:18",
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
      
         
  * **Code:** 422 Unprocessable Entity <br />
    **Content:** 
    
        {
            "estatus": [
              "El campo estatus es obligatorio."
            ]
        }
        
          
* **Code:** 406 Not Acceptable <br />
**Content:** 

      {
        "error": "El usuario no cuenta con perfil de Encargada"
      }


   
## Marcar como Finalizado (Soporte)
Regresa la información de la incidencia actualizada

**URL**
  
    /api/incidencias-soporte/{ID}/estatus
  
**Method:**

`POST`

**Headers**

      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data

**Data Params**
    
    'estatus' => 'required|in:finalizado',
    
    
**Success Response:**

* **Code:** 200 <br />
  **Content:**
      
      {
         "incidencia": {
             "id": 2,
             "folio": "CS002",
             "sucursal_id": 3,
             "user_id": 13,
             "motivo_id": 1,
             "fecha": "2020-08-10",
             "observaciones": null,
             "tipo_creacion": "api_store",
             "razon_rechazo": null,
             "created_at": "2020-08-10 19:28:22",
             "updated_at": "2020-08-10 19:28:24",
             "deleted_at": null,
             "estatus": [
               {
                 "id": 1,
                 "nombre": "Registrada",
                 "key": "registrada",
                 "created_at": "2020-08-10 17:13:12",
                 "updated_at": "2020-08-10 17:13:12",
                 "deleted_at": null,
                 "pivot": {
                   "incidencia_id": 2,
                   "estatus_id": 1,
                   "user_id": 13,
                   "created_at": "2020-08-10 19:28:24",
                   "updated_at": "2020-08-10 19:28:24"
                 }
               },
               {
                 "id": 2,
                 "nombre": "Aprobada",
                 "key": "aprobada",
                 "created_at": "2020-08-10 17:13:12",
                 "updated_at": "2020-08-10 17:13:12",
                 "deleted_at": null,
                 "pivot": {
                   "incidencia_id": 2,
                   "estatus_id": 2,
                   "user_id": 6,
                   "created_at": "2020-08-10 19:33:00",
                   "updated_at": "2020-08-10 19:33:00"
                 }
               },
               {
                 "id": 4,
                 "nombre": "Equipo asignado",
                 "key": "equipo-asignado",
                 "created_at": "2020-08-10 17:13:12",
                 "updated_at": "2020-08-10 17:13:12",
                 "deleted_at": null,
                 "pivot": {
                   "incidencia_id": 2,
                   "estatus_id": 4,
                   "user_id": 6,
                   "created_at": "2020-08-10 19:33:38",
                   "updated_at": "2020-08-10 19:33:33"
                 }
               },
               {
                 "id": 5,
                 "nombre": "En tránsito",
                 "key": "en-transito",
                 "created_at": "2020-08-10 17:13:12",
                 "updated_at": "2020-08-10 17:13:12",
                 "deleted_at": null,
                 "pivot": {
                   "incidencia_id": 2,
                   "estatus_id": 5,
                   "user_id": 433,
                   "created_at": "2020-08-10 21:54:16",
                   "updated_at": "2020-08-10 21:54:16"
                 }
               },
               {
                 "id": 6,
                 "nombre": "Entregado",
                 "key": "entregado",
                 "created_at": "2020-08-10 17:13:12",
                 "updated_at": "2020-08-10 17:13:12",
                 "deleted_at": null,
                 "pivot": {
                   "incidencia_id": 2,
                   "estatus_id": 6,
                   "user_id": 433,
                   "created_at": "2020-08-10 21:55:15",
                   "updated_at": "2020-08-10 21:55:15"
                 }
               },
               {
                 "id": 7,
                 "nombre": "Embarcado",
                 "key": "embarcado",
                 "created_at": "2020-08-10 17:13:12",
                 "updated_at": "2020-08-10 17:13:12",
                 "deleted_at": null,
                 "pivot": {
                   "incidencia_id": 2,
                   "estatus_id": 7,
                   "user_id": 13,
                   "created_at": "2020-08-10 21:55:56",
                   "updated_at": "2020-08-10 21:55:56"
                 }
               },
               {
                 "id": 8,
                 "nombre": "Devolución",
                 "key": "devolucion",
                 "created_at": "2020-08-10 17:13:12",
                 "updated_at": "2020-08-10 17:13:12",
                 "deleted_at": null,
                 "pivot": {
                   "incidencia_id": 2,
                   "estatus_id": 8,
                   "user_id": 433,
                   "created_at": "2020-08-10 21:56:45",
                   "updated_at": "2020-08-10 21:56:45"
                 }
               },
               {
                 "id": 9,
                 "nombre": "Finalizado",
                 "key": "finalizado",
                 "created_at": "2020-08-10 17:13:12",
                 "updated_at": "2020-08-10 17:13:12",
                 "deleted_at": null,
                 "pivot": {
                   "incidencia_id": 2,
                   "estatus_id": 9,
                   "user_id": 6,
                   "created_at": "2020-08-10 21:56:54",
                   "updated_at": "2020-08-10 21:56:54"
                 }
               }
             ],
             "motivo": {
               "id": 1,
               "nombre": "Pruebas CS",
               "key": "pruebas-cs",
               "prefix": "CS",
               "created_at": "2020-08-10 16:41:18",
               "updated_at": "2020-08-10 16:41:18",
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
      
         
  * **Code:** 422 Unprocessable Entity <br />
    **Content:** 
    
        {
            "estatus": [
              "El campo estatus es obligatorio."
            ]
        }
        
          
* **Code:** 406 Not Acceptable <br />
**Content:** 

      {
        "error": "El usuario no cuenta con perfil de Soporte"
      }
