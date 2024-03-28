## Listado de incidencias (Supervisor y Gerentes)
- Regresa el listado de las incidencias realizados por el usuario logueado (Supervisor)<br>
- Regresa el listado de incidencias sin aprobar/rechazar (Gerentes)

 **URL**

    /api/incidencias-sucursales

 **Method:**

  `GET`
  
 **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data
      
       
 **Data Params**
    
    'motivo_id' => 'nullable|exists:catalogo_motivos_incidencias_sucursales,id'
     
 **URL Params**

      - motivo_id = 1
        Ejemplo URI: `api/incidencias-sucursales?motivo_id=1`
     

**Success Response:**

* **Code:** 200 <br />
  **Content:** 
  
      {
            "incidencias": {}
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
          "error": "El usuario no cuenta con perfil de Supervisor o Gerente."
        }
             
            
                    
## Detalle de incidencia
Regresa el registro de un incidencia

 **URL**

    /api/incidencias-sucursales/{ID}

 **Method:**

  `GET`
  
 **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data
     
 **URL Params**

      - includes[] = sucursal, user.perfilSupervisor, motivo, incidenciaGasto.estatus, proveedor
        Ejemplo URI: `api/incidencias-sucursales/1?includes[]=sucursal`

**Success Response:**

* **Code:** 200 <br />
  **Content:** 
  
      {
           "incidencia": {
               "id": 4,
               "folio": "GG004",
               "sucursal_id": 3,
               "user_id": 17,
               "motivo_id": 1,
               "proveedor_id": null,
               "fecha": "2020-06-25",
               "observaciones": null,
               "tipo_creacion": "api_store",
               "created_at": "2020-06-25 18:13:45",
               "updated_at": "2020-06-25 18:13:45",
               "deleted_at": null,
               "problema_evidencia": "images\/noimage.png",
               "incidencia_gasto": {
                 "id": 4,
                 "incidencia_id": 4,
                 "num_ticket": null,
                 "factura": 0,
                 "monto": 10000,
                 "pagado": null,
                 "rechazo_costos": 0,
                 "razon_rechazo": null,
                 "razon_improcedencia": null,
                 "created_at": "2020-06-25 18:13:45",
                 "updated_at": "2020-06-25 18:19:21",
                 "deleted_at": null,
                 "solucion_evidencia": "https:\/\/sfo2.digitaloceanspaces.com\/farmapronto-sucursales\/incidencias\/soluciones\/85908\/Farma3.jpg",
                 "ticket_evidencia": "https:\/\/sfo2.digitaloceanspaces.com\/farmapronto-sucursales\/incidencias\/tickets\/85909\/Farma3.jpg",
                 "factura_evidencia": "https:\/\/sfo2.digitaloceanspaces.com\/farmapronto-sucursales\/incidencias\/facturas\/85910\/Farma3.jpg",
                 "estatus": [
                   {
                     "id": 1,
                     "nombre": "Pendiente",
                     "key": "pendiente",
                     "created_at": "2019-10-01 18:40:57",
                     "updated_at": "2019-10-01 18:40:57",
                     "deleted_at": null,
                     "pivot": {
                       "incidencia_gasto_id": 4,
                       "estatus_id": 1,
                       "user_id": 17,
                       "created_at": "2020-06-25 18:13:45",
                       "updated_at": "2020-06-25 18:13:45"
                     }
                   },
                   {
                     "id": 2,
                     "nombre": "Aprobada para cotizar",
                     "key": "aprobada",
                     "created_at": "2019-10-01 18:40:57",
                     "updated_at": "2019-10-01 18:40:57",
                     "deleted_at": null,
                     "pivot": {
                       "incidencia_gasto_id": 4,
                       "estatus_id": 2,
                       "user_id": 1,
                       "created_at": "2020-06-25 18:15:11",
                       "updated_at": "2020-06-25 18:15:11"
                     }
                   },
                   {
                     "id": 4,
                     "nombre": "Cotizada",
                     "key": "cotizada",
                     "created_at": "2019-10-01 18:40:57",
                     "updated_at": "2019-10-01 18:40:57",
                     "deleted_at": null,
                     "pivot": {
                       "incidencia_gasto_id": 4,
                       "estatus_id": 4,
                       "user_id": 17,
                       "created_at": "2020-06-25 18:20:42",
                       "updated_at": "2020-06-25 18:20:42"
                     }
                   },
                   {
                     "id": 4,
                     "nombre": "Cotizada",
                     "key": "cotizada",
                     "created_at": "2019-10-01 18:40:57",
                     "updated_at": "2019-10-01 18:40:57",
                     "deleted_at": null,
                     "pivot": {
                       "incidencia_gasto_id": 4,
                       "estatus_id": 4,
                       "user_id": 17,
                       "created_at": "2020-06-25 18:21:39",
                       "updated_at": "2020-06-25 18:21:39"
                     }
                   },
                   {
                     "id": 5,
                     "nombre": "Confirmada",
                     "key": "confirmada",
                     "created_at": "2019-10-01 18:40:57",
                     "updated_at": "2019-10-01 18:40:57",
                     "deleted_at": null,
                     "pivot": {
                       "incidencia_gasto_id": 4,
                       "estatus_id": 5,
                       "user_id": 1,
                       "created_at": "2020-06-25 18:22:38",
                       "updated_at": "2020-06-25 18:22:38"
                     }
                   },
                   {
                     "id": 7,
                     "nombre": "Reparada",
                     "key": "reparada",
                     "created_at": "2019-10-01 18:40:57",
                     "updated_at": "2019-10-01 18:40:57",
                     "deleted_at": null,
                     "pivot": {
                       "incidencia_gasto_id": 4,
                       "estatus_id": 7,
                       "user_id": 17,
                       "created_at": "2020-06-25 18:24:19",
                       "updated_at": "2020-06-25 18:24:19"
                     }
                   }
                 ],
                 "media": [
                   {
                     "id": 85908,
                     "model_type": "App\\Entities\\IncidenciasSucursales\\IncidenciaSucursalGasto",
                     "model_id": 4,
                     "collection_name": "solucion_evidencia",
                     "name": "Farma3",
                     "file_name": "Farma3.jpg",
                     "mime_type": "image\/jpeg",
                     "disk": "incidencias_soluciones",
                     "size": 183092,
                     "manipulations": [],
                     "custom_properties": [],
                     "responsive_images": [],
                     "order_column": 85682,
                     "created_at": "2020-06-25 18:24:04",
                     "updated_at": "2020-06-25 18:24:04"
                   },
                   {
                     "id": 85909,
                     "model_type": "App\\Entities\\IncidenciasSucursales\\IncidenciaSucursalGasto",
                     "model_id": 4,
                     "collection_name": "ticket_evidencia",
                     "name": "Farma3",
                     "file_name": "Farma3.jpg",
                     "mime_type": "image\/jpeg",
                     "disk": "incidencias_tickets",
                     "size": 183092,
                     "manipulations": [],
                     "custom_properties": [],
                     "responsive_images": [],
                     "order_column": 85683,
                     "created_at": "2020-06-25 18:24:10",
                     "updated_at": "2020-06-25 18:24:10"
                   },
                   {
                     "id": 85910,
                     "model_type": "App\\Entities\\IncidenciasSucursales\\IncidenciaSucursalGasto",
                     "model_id": 4,
                     "collection_name": "factura_evidencia",
                     "name": "Farma3",
                     "file_name": "Farma3.jpg",
                     "mime_type": "image\/jpeg",
                     "disk": "incidencias_facturas",
                     "size": 183092,
                     "manipulations": [],
                     "custom_properties": [],
                     "responsive_images": [],
                     "order_column": 85684,
                     "created_at": "2020-06-25 18:24:11",
                     "updated_at": "2020-06-25 18:24:11"
                   }
                 ]
               },
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
               "media": []
           }
      }

**Error Response:**

  * **Code:** 401 Unauthorized <br />
    **Content:** 
  
          {
            "error": "Unauthenticated."
          }  

 
**Registro de incidencia (Supervisor)**
----
  Regresa la información del registro en formato json

 **URL**

    /api/incidencias-sucursales

 **Method:**

  `POST`
  
  **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data

 
 **Data Params**
    
     'fecha' => 'required|date',
     'motivo_id' => 'required|exists:catalogo_motivos_incidencias_sucursales,id',
     'sucursal_id' => 'required|exists:sucursales,id',
     'observaciones' => 'nullable',
     'evidencia' => 'nullable|image',
     'proveedor_id' => 'nullable',
     'pagado' => 'nullable|in:Cheque,Efectivo',
     'gastos_ids' => 'nullable|array',
     'montos' => 'nullable|array',


 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
            "incidencia": {
                "fecha": "2020-06-25",
                "sucursal_id": "3",
                "motivo_id": "1",
                "user_id": 17,
                "tipo_creacion": "api_store",
                "proveedor_id": null,
                "updated_at": "2020-06-25 18:51:35",
                "created_at": "2020-06-25 18:51:35",
                "id": 5,
                "folio": "GG005",
                "problema_evidencia": "images\/noimage.png",
                "motivo": {
                  "id": 1,
                  "nombre": "Gastos generales",
                  "key": "gastos-generales",
                  "prefix": "GG",
                  "created_at": "2020-06-24 19:19:05",
                  "updated_at": "2020-06-24 19:19:05",
                  "deleted_at": null
                },
                "user": {
                  "id": 17,
                  "nombre": "Supervisor",
                  "apellido_paterno": "Prueba",
                  "apellido_materno": null,
                  "telefono": "Farma",
                  "player_id": "2eaebf23-153d-4352-a1f9-70f0b63b40e5",
                  "email": "supervisor@farmapronto-sucursales.com",
                  "old_email": null,
                  "email_verified_at": null,
                  "cant_errores_actuales": 0,
                  "created_at": "2019-07-03 18:55:53",
                  "updated_at": "2019-11-12 12:56:57",
                  "deleted_at": null,
                  "perfil_supervisor": {
                    "id": 1,
                    "user_id": 17,
                    "clave": null,
                    "ext": "1",
                    "telefono_asignado": null,
                    "celular_personal": null,
                    "numero_seguro_social": null,
                    "contacto_emergencia": null,
                    "contacto_emergencia_telefono": null,
                    "grupo_sanguineo": null,
                    "alergias": null,
                    "focos": 0,
                    "created_at": "2019-07-03 18:55:53",
                    "updated_at": "2019-10-09 13:32:32",
                    "deleted_at": null
                  }
                },
                "incidencia_gasto": {
                  "id": 5,
                  "incidencia_id": 5,
                  "num_ticket": null,
                  "factura": 0,
                  "monto": null,
                  "pagado": null,
                  "rechazo_costos": 0,
                  "razon_rechazo": null,
                  "razon_improcedencia": null,
                  "created_at": "2020-06-25 18:51:35",
                  "updated_at": "2020-06-25 18:51:35",
                  "deleted_at": null,
                  "solucion_evidencia": "images\/noimage.png",
                  "ticket_evidencia": "images\/noimage.png",
                  "factura_evidencia": "images\/noimage.png",
                  "estatus": [
                    {
                      "id": 1,
                      "nombre": "Pendiente",
                      "key": "pendiente",
                      "created_at": "2019-10-01 18:40:57",
                      "updated_at": "2019-10-01 18:40:57",
                      "deleted_at": null,
                      "pivot": {
                        "incidencia_gasto_id": 5,
                        "estatus_id": 1,
                        "user_id": 17,
                        "created_at": "2020-06-25 18:51:35",
                        "updated_at": "2020-06-25 18:51:35"
                      }
                    }
                  ],
                  "gastos": [],
                  "media": []
                },
                "proveedor": null,
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
                "media": []
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
            "fecha": [
              "El campo fecha es obligatorio."
            ],
            "motivo_id": [
              "El campo motivo id es obligatorio."
            ],
            "sucursal_id": [
              "El campo sucursal id es obligatorio."
            ]
            "kilometraje": [
              "El campo kilometraje es obligatorio."
            ]
        } 
        
  * **Code:** 411 Length Required <br />
      **Content:** 
    
        {
          "error": "¡ERROR! Se debe agregar otro gasto adicional a Mano de obra."
        } 
                  
* **Code:** 406 Not Acceptable <br />
**Content:** 

      {
        "error": "El usuario no cuenta con perfil de Supervisor"
      } 
          
## Marcar como reparada (Supervisor)
Regresa la información de la incidencia actualizada

**URL**
  
    /api/incidencias-sucursales/{ID}/reparar
  
**Method:**

`POST`

**Headers**

      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data

**Data Params**
    
    'monto' => 'required',
    'archivo_ticket' => 'required|image',
    'archivo_factura' => 'nullable|image',
    'archivo_evidencia' => 'nullable|image',
    'evidencias' => 'nullable|array'
    
    
**Success Response:**

* **Code:** 200 <br />
  **Content:**
      
      {
         "incidencia": {
             "id": 4,
             "folio": "GG004",
             "sucursal_id": 3,
             "user_id": 17,
             "motivo_id": 1,
             "proveedor_id": null,
             "fecha": "2020-06-25",
             "observaciones": null,
             "tipo_creacion": "api_store",
             "created_at": "2020-06-25 18:13:45",
             "updated_at": "2020-06-25 18:13:45",
             "deleted_at": null,
             "problema_evidencia": "images\/noimage.png",
             "user": {
               "id": 17,
               "nombre": "Supervisor",
               "apellido_paterno": "Prueba",
               "apellido_materno": null,
               "telefono": "Farma",
               "player_id": "2eaebf23-153d-4352-a1f9-70f0b63b40e5",
               "email": "supervisor@farmapronto-sucursales.com",
               "old_email": null,
               "email_verified_at": null,
               "cant_errores_actuales": 0,
               "created_at": "2019-07-03 18:55:53",
               "updated_at": "2019-11-12 12:56:57",
               "deleted_at": null,
               "perfil_supervisor": {
                 "id": 1,
                 "user_id": 17,
                 "clave": null,
                 "ext": "1",
                 "telefono_asignado": null,
                 "celular_personal": null,
                 "numero_seguro_social": null,
                 "contacto_emergencia": null,
                 "contacto_emergencia_telefono": null,
                 "grupo_sanguineo": null,
                 "alergias": null,
                 "focos": 0,
                 "created_at": "2019-07-03 18:55:53",
                 "updated_at": "2019-10-09 13:32:32",
                 "deleted_at": null
               }
             },
             "motivo": {
               "id": 1,
               "nombre": "Gastos generales",
               "key": "gastos-generales",
               "prefix": "GG",
               "created_at": "2020-06-24 19:19:05",
               "updated_at": "2020-06-24 19:19:05",
               "deleted_at": null
             },
             "incidencia_gasto": {
               "id": 4,
               "incidencia_id": 4,
               "num_ticket": null,
               "factura": 0,
               "monto": 10000,
               "pagado": null,
               "rechazo_costos": 0,
               "razon_rechazo": null,
               "razon_improcedencia": null,
               "created_at": "2020-06-25 18:13:45",
               "updated_at": "2020-06-25 18:19:21",
               "deleted_at": null,
               "solucion_evidencia": "https:\/\/sfo2.digitaloceanspaces.com\/farmapronto-sucursales\/incidencias\/soluciones\/85908\/Farma3.jpg",
               "ticket_evidencia": "https:\/\/sfo2.digitaloceanspaces.com\/farmapronto-sucursales\/incidencias\/tickets\/85909\/Farma3.jpg",
               "factura_evidencia": "https:\/\/sfo2.digitaloceanspaces.com\/farmapronto-sucursales\/incidencias\/facturas\/85910\/Farma3.jpg",
               "estatus": [
                 {
                   "id": 1,
                   "nombre": "Pendiente",
                   "key": "pendiente",
                   "created_at": "2019-10-01 18:40:57",
                   "updated_at": "2019-10-01 18:40:57",
                   "deleted_at": null,
                   "pivot": {
                     "incidencia_gasto_id": 4,
                     "estatus_id": 1,
                     "user_id": 17,
                     "created_at": "2020-06-25 18:13:45",
                     "updated_at": "2020-06-25 18:13:45"
                   }
                 },
                 {
                   "id": 2,
                   "nombre": "Aprobada para cotizar",
                   "key": "aprobada",
                   "created_at": "2019-10-01 18:40:57",
                   "updated_at": "2019-10-01 18:40:57",
                   "deleted_at": null,
                   "pivot": {
                     "incidencia_gasto_id": 4,
                     "estatus_id": 2,
                     "user_id": 1,
                     "created_at": "2020-06-25 18:15:11",
                     "updated_at": "2020-06-25 18:15:11"
                   }
                 },
                 {
                   "id": 4,
                   "nombre": "Cotizada",
                   "key": "cotizada",
                   "created_at": "2019-10-01 18:40:57",
                   "updated_at": "2019-10-01 18:40:57",
                   "deleted_at": null,
                   "pivot": {
                     "incidencia_gasto_id": 4,
                     "estatus_id": 4,
                     "user_id": 17,
                     "created_at": "2020-06-25 18:20:42",
                     "updated_at": "2020-06-25 18:20:42"
                   }
                 },
                 {
                   "id": 4,
                   "nombre": "Cotizada",
                   "key": "cotizada",
                   "created_at": "2019-10-01 18:40:57",
                   "updated_at": "2019-10-01 18:40:57",
                   "deleted_at": null,
                   "pivot": {
                     "incidencia_gasto_id": 4,
                     "estatus_id": 4,
                     "user_id": 17,
                     "created_at": "2020-06-25 18:21:39",
                     "updated_at": "2020-06-25 18:21:39"
                   }
                 },
                 {
                   "id": 5,
                   "nombre": "Confirmada",
                   "key": "confirmada",
                   "created_at": "2019-10-01 18:40:57",
                   "updated_at": "2019-10-01 18:40:57",
                   "deleted_at": null,
                   "pivot": {
                     "incidencia_gasto_id": 4,
                     "estatus_id": 5,
                     "user_id": 1,
                     "created_at": "2020-06-25 18:22:38",
                     "updated_at": "2020-06-25 18:22:38"
                   }
                 },
                 {
                   "id": 7,
                   "nombre": "Reparada",
                   "key": "reparada",
                   "created_at": "2019-10-01 18:40:57",
                   "updated_at": "2019-10-01 18:40:57",
                   "deleted_at": null,
                   "pivot": {
                     "incidencia_gasto_id": 4,
                     "estatus_id": 7,
                     "user_id": 17,
                     "created_at": "2020-06-25 18:24:19",
                     "updated_at": "2020-06-25 18:24:19"
                   }
                 }
               ],
               "media": [
                 {
                   "id": 85908,
                   "model_type": "App\\Entities\\IncidenciasSucursales\\IncidenciaSucursalGasto",
                   "model_id": 4,
                   "collection_name": "solucion_evidencia",
                   "name": "Farma3",
                   "file_name": "Farma3.jpg",
                   "mime_type": "image\/jpeg",
                   "disk": "incidencias_soluciones",
                   "size": 183092,
                   "manipulations": [],
                   "custom_properties": [],
                   "responsive_images": [],
                   "order_column": 85682,
                   "created_at": "2020-06-25 18:24:04",
                   "updated_at": "2020-06-25 18:24:04"
                 },
                 {
                   "id": 85909,
                   "model_type": "App\\Entities\\IncidenciasSucursales\\IncidenciaSucursalGasto",
                   "model_id": 4,
                   "collection_name": "ticket_evidencia",
                   "name": "Farma3",
                   "file_name": "Farma3.jpg",
                   "mime_type": "image\/jpeg",
                   "disk": "incidencias_tickets",
                   "size": 183092,
                   "manipulations": [],
                   "custom_properties": [],
                   "responsive_images": [],
                   "order_column": 85683,
                   "created_at": "2020-06-25 18:24:10",
                   "updated_at": "2020-06-25 18:24:10"
                 },
                 {
                   "id": 85910,
                   "model_type": "App\\Entities\\IncidenciasSucursales\\IncidenciaSucursalGasto",
                   "model_id": 4,
                   "collection_name": "factura_evidencia",
                   "name": "Farma3",
                   "file_name": "Farma3.jpg",
                   "mime_type": "image\/jpeg",
                   "disk": "incidencias_facturas",
                   "size": 183092,
                   "manipulations": [],
                   "custom_properties": [],
                   "responsive_images": [],
                   "order_column": 85684,
                   "created_at": "2020-06-25 18:24:11",
                   "updated_at": "2020-06-25 18:24:11"
                 }
               ]
             },
             "media": []
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
            "monto": [
              "El campo monto es obligatorio."
            ],
            "archivo_ticket": [
              "El campo archivo ticket es obligatorio."
            ]
        }
        
          
* **Code:** 406 Not Acceptable <br />
**Content:** 

      {
        "error": "El usuario no cuenta con perfil de Supervisor"
      }

          
          
## Marcar como aprobada/rechazada (Gerente)
Regresa la información de la incidencia actualizada

**URL**
  
    /api/incidencias-sucursales/{ID}/aprobar
  
**Method:**

`POST`

**Headers**

      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data

**Data Params**
    
    'estatus' => 'required|in:aprobada,rechazada',
    'proveedor_id' => 'nullable|exists:catalogo_proveedores_incidencias_sucursales,id',
    'pagado' => 'required_if:estatus,aprobada|in:Cheque,Efectivo',
    'razon_rechazo' => 'required_if:estatus,rechazada',
    'costos' => 'nullable',
    
    
**Success Response:**

* **Code:** 200 <br />
  **Content:**
      
      {
         "incidencia": {
             "id": 9,
             "folio": "GG009",
             "sucursal_id": 3,
             "user_id": 17,
             "motivo_id": 1,
             "proveedor_id": null,
             "fecha": "2020-06-25",
             "observaciones": null,
             "tipo_creacion": "api_store",
             "created_at": "2020-07-08 13:25:28",
             "updated_at": "2020-07-08 13:25:28",
             "deleted_at": null,
             "problema_evidencia": "images\/noimage.png",
             "incidencia_gasto": {
               "id": 9,
               "incidencia_id": 9,
               "num_ticket": null,
               "factura": 0,
               "monto": null,
               "pagado": "Cheque",
               "rechazo_costos": 0,
               "razon_rechazo": null,
               "razon_improcedencia": null,
               "created_at": "2020-07-08 13:25:28",
               "updated_at": "2020-07-08 15:22:34",
               "deleted_at": null,
               "solucion_evidencia": "images\/noimage.png",
               "ticket_evidencia": "images\/noimage.png",
               "factura_evidencia": "images\/noimage.png",
               "estatus": [
                 {
                   "id": 1,
                   "nombre": "Pendiente",
                   "key": "pendiente",
                   "created_at": "2019-10-01 18:40:57",
                   "updated_at": "2019-10-01 18:40:57",
                   "deleted_at": null,
                   "pivot": {
                     "incidencia_gasto_id": 9,
                     "estatus_id": 1,
                     "user_id": 17,
                     "created_at": "2020-07-08 13:25:28",
                     "updated_at": "2020-07-08 13:25:28"
                   }
                 },
                 {
                   "id": 2,
                   "nombre": "Aprobada para cotizar",
                   "key": "aprobada",
                   "created_at": "2019-10-01 18:40:57",
                   "updated_at": "2019-10-01 18:40:57",
                   "deleted_at": null,
                   "pivot": {
                     "incidencia_gasto_id": 9,
                     "estatus_id": 2,
                     "user_id": 6,
                     "created_at": "2020-07-08 15:22:34",
                     "updated_at": "2020-07-08 15:22:34"
                   }
                 }
               ],
               "media": []
             },
             "user": {
               "id": 17,
               "nombre": "Supervisor",
               "apellido_paterno": "Prueba",
               "apellido_materno": null,
               "telefono": "Farma",
               "player_id": "2eaebf23-153d-4352-a1f9-70f0b63b40e5",
               "email": "supervisor@farmapronto-sucursales.com",
               "old_email": null,
               "email_verified_at": null,
               "cant_errores_actuales": 0,
               "created_at": "2019-07-03 18:55:53",
               "updated_at": "2019-11-12 12:56:57",
               "deleted_at": null
             },
             "motivo": {
               "id": 1,
               "nombre": "Gastos generales",
               "key": "gastos-generales",
               "prefix": "GG",
               "created_at": "2020-06-24 19:19:05",
               "updated_at": "2020-06-24 19:19:05",
               "deleted_at": null
             },
             "media": []
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
            "pagado": [
              "El campo pagado es obligatorio cuando estatus es aprobada."
            ],
            "razon_rechazo": [
              "El campo razon rechazo es obligatorio cuando estatus es rechazada."
            ]
        }
        
          
* **Code:** 406 Not Acceptable <br />
**Content:** 

      {
        "error": "El usuario no cuenta con perfil de Gerente"
      }
