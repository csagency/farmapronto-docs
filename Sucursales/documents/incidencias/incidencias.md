## Listado de incidencias
Regresa el listado de las incidencias realizados por el usuario logueado

 **URL**

    /api/incidencias

 **Method:**

  `GET`
  
 **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data
      
       
 **Data Params**
    
    'motivo_id' => 'nullable|exists:catalogo_motivos_incidencias,id'
     
 **URL Params**

      - motivo_id = 4
        Devuelve todos los registros de tipo gasolina
        Ejemplo URI: `api/incidencias?motivo_id=4`
     

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
          "error": "El usuario no cuenta con perfil de Supervisor."
        }
             
            
                    
## Detalle de incidencia
Regresa el registro de un incidencia

 **URL**

    /api/incidencias/{ID}

 **Method:**

  `GET`
  
 **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data
     
 **URL Params**

      - includes[] = vehiculo, user.perfilSupervisor, motivo, incidenciaGasto.estatus, proveedor, check
        Ejemplo URI: `api/incidencias/1?includes[]=vehiculo`

**Success Response:**

* **Code:** 200 <br />
  **Content:** 
  
      {
           "incidencia": {
               "id": 2,
               "folio": "GA002",
               "vehiculo_id": 2,
               "user_id": 17,
               "motivo_id": 4,
               "proveedor_id": null,
               "check_id": 4,
               "kilometraje": 1010,
               "fecha": "2019-10-01",
               "observaciones": null,
               "tipo_creacion": "dashboard_checkin",
               "created_at": "2019-10-01 19:02:42",
               "updated_at": "2019-10-01 19:02:43",
               "deleted_at": null,
               "kilometraje_evidencia": "images\/noimage.png",
               "problema_evidencia": "images\/noimage.png",
               "check": {
                 "id": 4,
                 "user_id": 17,
                 "vehiculo_id": 2,
                 "check_id": null,
                 "turno": "intermedio",
                 "tipo": "checkin",
                 "kilometraje": 1010,
                 "estado_vehiculo": 1,
                 "estado_llantas": 1,
                 "licencia_vigencia": "2023-12-23",
                 "observaciones": null,
                 "lat": null,
                 "lon": null,
                 "aprobado": 1,
                 "created_at": "2019-08-12 18:21:45",
                 "updated_at": "2019-10-01 19:02:42",
                 "deleted_at": null,
                 "kilometraje_evidencia": "\/storage\/checks\/kilometrajes\/53\/35888217_2095034594077590_1878407717886885888_n.png",
                 "estado_vehiculo_evidencia": "images\/noimage.png",
                 "estado_llantas_evidencia": "images\/noimage.png",
                 "nivel_gasolina": "\/storage\/checks\/niveles_gasolina\/54\/35888217_2095034594077590_1878407717886885888_n.png",
                 "licencia": "\/storage\/checks\/licencias\/55\/35888217_2095034594077590_1878407717886885888_n.png",
                 "tarjeta_circulacion": "\/storage\/checks\/tarjetas_circulacion\/56\/35888217_2095034594077590_1878407717886885888_n.png",
                 "poliza_seguro": "\/storage\/checks\/polizas_seguro\/57\/35888217_2095034594077590_1878407717886885888_n.png",
                 "frontal": "\/storage\/checks\/frontales\/58\/35888217_2095034594077590_1878407717886885888_n.png",
                 "lateral_derecho": "\/storage\/checks\/laterales_derechos\/59\/35888217_2095034594077590_1878407717886885888_n.png",
                 "lateral_izquierdo": "\/storage\/checks\/laterales_izquierdos\/60\/35888217_2095034594077590_1878407717886885888_n.png",
                 "trasera": "\/storage\/checks\/traseras\/61\/35888217_2095034594077590_1878407717886885888_n.png",
                 "llanta_delantera_derecha": "images\/noimage.png",
                 "llanta_delantera_izquierda": "images\/noimage.png",
                 "llanta_trasera_derecha": "images\/noimage.png",
                 "llanta_trasera_izquierda": "images\/noimage.png",
                 "permiso_carga": "\/storage\/checks\/permisos_carga\/62\/35888217_2095034594077590_1878407717886885888_n.png",
                 "gato": "images\/noimage.png",
                 "cruceta": "images\/noimage.png",
                 "llanta_refaccion": "images\/noimage.png",
                 "luces_delanteras": "images\/noimage.png",
                 "luces_traseras": "images\/noimage.png",
                 "media": [
                   {
                     "id": 53,
                     "model_type": "App\\Entities\\Checks\\Check",
                     "model_id": 4,
                     "collection_name": "kilometraje_evidencia",
                     "name": "35888217_2095034594077590_1878407717886885888_n",
                     "file_name": "35888217_2095034594077590_1878407717886885888_n.png",
                     "mime_type": "image\/png",
                     "disk": "checks_kilometrajes",
                     "size": 652647,
                     "manipulations": [],
                     "custom_properties": [],
                     "responsive_images": [],
                     "order_column": 53,
                     "created_at": "2019-08-12 18:21:45",
                     "updated_at": "2019-08-12 18:21:45"
                   },
                   {
                     "id": 54,
                     "model_type": "App\\Entities\\Checks\\Check",
                     "model_id": 4,
                     "collection_name": "nivel_gasolina",
                     "name": "35888217_2095034594077590_1878407717886885888_n",
                     "file_name": "35888217_2095034594077590_1878407717886885888_n.png",
                     "mime_type": "image\/png",
                     "disk": "checks_niveles_gasolina",
                     "size": 652647,
                     "manipulations": [],
                     "custom_properties": [],
                     "responsive_images": [],
                     "order_column": 54,
                     "created_at": "2019-08-12 18:21:45",
                     "updated_at": "2019-08-12 18:21:45"
                   },
                   {
                     "id": 55,
                     "model_type": "App\\Entities\\Checks\\Check",
                     "model_id": 4,
                     "collection_name": "licencia",
                     "name": "35888217_2095034594077590_1878407717886885888_n",
                     "file_name": "35888217_2095034594077590_1878407717886885888_n.png",
                     "mime_type": "image\/png",
                     "disk": "checks_licencias",
                     "size": 652647,
                     "manipulations": [],
                     "custom_properties": [],
                     "responsive_images": [],
                     "order_column": 55,
                     "created_at": "2019-08-12 18:21:45",
                     "updated_at": "2019-08-12 18:21:45"
                   },
                   {
                     "id": 56,
                     "model_type": "App\\Entities\\Checks\\Check",
                     "model_id": 4,
                     "collection_name": "tarjeta_circulacion",
                     "name": "35888217_2095034594077590_1878407717886885888_n",
                     "file_name": "35888217_2095034594077590_1878407717886885888_n.png",
                     "mime_type": "image\/png",
                     "disk": "checks_tarjetas_circulacion",
                     "size": 652647,
                     "manipulations": [],
                     "custom_properties": [],
                     "responsive_images": [],
                     "order_column": 56,
                     "created_at": "2019-08-12 18:21:46",
                     "updated_at": "2019-08-12 18:21:46"
                   },
                   {
                     "id": 57,
                     "model_type": "App\\Entities\\Checks\\Check",
                     "model_id": 4,
                     "collection_name": "poliza_seguro",
                     "name": "35888217_2095034594077590_1878407717886885888_n",
                     "file_name": "35888217_2095034594077590_1878407717886885888_n.png",
                     "mime_type": "image\/png",
                     "disk": "checks_polizas_seguro",
                     "size": 652647,
                     "manipulations": [],
                     "custom_properties": [],
                     "responsive_images": [],
                     "order_column": 57,
                     "created_at": "2019-08-12 18:21:46",
                     "updated_at": "2019-08-12 18:21:46"
                   },
                   {
                     "id": 58,
                     "model_type": "App\\Entities\\Checks\\Check",
                     "model_id": 4,
                     "collection_name": "frontal",
                     "name": "35888217_2095034594077590_1878407717886885888_n",
                     "file_name": "35888217_2095034594077590_1878407717886885888_n.png",
                     "mime_type": "image\/png",
                     "disk": "checks_frontales",
                     "size": 652647,
                     "manipulations": [],
                     "custom_properties": [],
                     "responsive_images": [],
                     "order_column": 58,
                     "created_at": "2019-08-12 18:21:46",
                     "updated_at": "2019-08-12 18:21:46"
                   },
                   {
                     "id": 59,
                     "model_type": "App\\Entities\\Checks\\Check",
                     "model_id": 4,
                     "collection_name": "lateral_derecho",
                     "name": "35888217_2095034594077590_1878407717886885888_n",
                     "file_name": "35888217_2095034594077590_1878407717886885888_n.png",
                     "mime_type": "image\/png",
                     "disk": "checks_laterales_derechos",
                     "size": 652647,
                     "manipulations": [],
                     "custom_properties": [],
                     "responsive_images": [],
                     "order_column": 59,
                     "created_at": "2019-08-12 18:21:46",
                     "updated_at": "2019-08-12 18:21:46"
                   },
                   {
                     "id": 60,
                     "model_type": "App\\Entities\\Checks\\Check",
                     "model_id": 4,
                     "collection_name": "lateral_izquierdo",
                     "name": "35888217_2095034594077590_1878407717886885888_n",
                     "file_name": "35888217_2095034594077590_1878407717886885888_n.png",
                     "mime_type": "image\/png",
                     "disk": "checks_laterales_izquierdos",
                     "size": 652647,
                     "manipulations": [],
                     "custom_properties": [],
                     "responsive_images": [],
                     "order_column": 60,
                     "created_at": "2019-08-12 18:21:46",
                     "updated_at": "2019-08-12 18:21:46"
                   },
                   {
                     "id": 61,
                     "model_type": "App\\Entities\\Checks\\Check",
                     "model_id": 4,
                     "collection_name": "trasera",
                     "name": "35888217_2095034594077590_1878407717886885888_n",
                     "file_name": "35888217_2095034594077590_1878407717886885888_n.png",
                     "mime_type": "image\/png",
                     "disk": "checks_traseras",
                     "size": 652647,
                     "manipulations": [],
                     "custom_properties": [],
                     "responsive_images": [],
                     "order_column": 61,
                     "created_at": "2019-08-12 18:21:46",
                     "updated_at": "2019-08-12 18:21:46"
                   },
                   {
                     "id": 62,
                     "model_type": "App\\Entities\\Checks\\Check",
                     "model_id": 4,
                     "collection_name": "permiso_carga",
                     "name": "35888217_2095034594077590_1878407717886885888_n",
                     "file_name": "35888217_2095034594077590_1878407717886885888_n.png",
                     "mime_type": "image\/png",
                     "disk": "checks_permisos_carga",
                     "size": 652647,
                     "manipulations": [],
                     "custom_properties": [],
                     "responsive_images": [],
                     "order_column": 62,
                     "created_at": "2019-08-12 18:21:46",
                     "updated_at": "2019-08-12 18:21:46"
                   }
                 ]
               },
               "media": [
                 {
                   "id": 99,
                   "model_type": "App\\Entities\\Incidencias\\Incidencia",
                   "model_id": 2,
                   "collection_name": "ticket_evidencia",
                   "name": "45188042-7f447a00-b1f8-11e8-9737-4fcdf046c05a",
                   "file_name": "45188042-7f447a00-b1f8-11e8-9737-4fcdf046c05a.png",
                   "mime_type": "image\/png",
                   "disk": "public",
                   "size": 378090,
                   "manipulations": [],
                   "custom_properties": [],
                   "responsive_images": [],
                   "order_column": 99,
                   "created_at": "2019-10-02 11:07:43",
                   "updated_at": "2019-10-02 11:07:43"
                 },
                 {
                   "id": 100,
                   "model_type": "App\\Entities\\Incidencias\\Incidencia",
                   "model_id": 2,
                   "collection_name": "ticket_evidencia",
                   "name": "45188042-7f447a00-b1f8-11e8-9737-4fcdf046c05a",
                   "file_name": "45188042-7f447a00-b1f8-11e8-9737-4fcdf046c05a.png",
                   "mime_type": "image\/png",
                   "disk": "public",
                   "size": 378090,
                   "manipulations": [],
                   "custom_properties": [],
                   "responsive_images": [],
                   "order_column": 100,
                   "created_at": "2019-10-02 11:09:14",
                   "updated_at": "2019-10-02 11:09:14"
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

 
**Registro de incidencia**
----
  Regresa la información del registro en formato json

 **URL**

    /api/incidencias

 **Method:**

  `POST`
  
  **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data

 
 **Data Params**
    
     'fecha' => 'required|date',
     'motivo_id' => 'required|exists:catalogo_motivos_incidencias,id',
     'vehiculo_id' => 'required|exists:vehiculos,id',
     'observaciones' => 'nullable',
     'kilometraje' => 'required',
     'km_evidencia' => 'nullable|image',
     'evidencia' => 'nullable|image',
     'proveedor_id' => 'nullable',
     'gastos_ids' => 'nullable|array',
     'montos' => 'nullable|array',
     'tipo_creacion' => 'nullable|in:api_checkin,api_checkout,api_store',
     'check_id' => 'nullable|exists:checks,id'


 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
            "incidencia": {
                "fecha": "2019-10-01",
                "vehiculo_id": "3",
                "motivo_id": "4",
                "kilometraje": "1000",
                "user_id": 17,
                "tipo_creacion": "api_store",
                "proveedor_id": null,
                "check_id": null,
                "updated_at": "2019-10-02 13:44:23",
                "created_at": "2019-10-02 13:44:22",
                "id": 5,
                "folio": "GA005",
                "kilometraje_evidencia": "images\/noimage.png",
                "problema_evidencia": "images\/noimage.png",
                "motivo": {
                  "id": 4,
                  "nombre": "Por gasolina",
                  "key": "gasolina",
                  "prefix": "GA",
                  "created_at": "2019-10-01 18:40:43",
                  "updated_at": "2019-10-01 18:40:43",
                  "deleted_at": null
                },
                "user": {
                  "id": 17,
                  "nombre": "Supervisor",
                  "apellido_paterno": "Prueba",
                  "apellido_materno": null,
                  "telefono": "Farma",
                  "player_id": null,
                  "email": "supervisor@farmapronto-sucursales.com",
                  "old_email": null,
                  "email_verified_at": null,
                  "created_at": "2019-07-03 18:55:53",
                  "updated_at": "2019-08-26 13:32:43",
                  "deleted_at": null,
                  "perfil_supervisor": {
                    "id": 1,
                    "user_id": 17,
                    "ext": "1",
                    "telefono_asignado": null,
                    "celular_personal": null,
                    "numero_seguro_social": null,
                    "contacto_emergencia": null,
                    "contacto_emergencia_telefono": null,
                    "grupo_sanguineo": null,
                    "alergias": null,
                    "created_at": "2019-07-03 18:55:53",
                    "updated_at": "2019-07-03 18:55:53",
                    "deleted_at": null
                  }
                },
                "vehiculo": {
                  "id": 3,
                  "user_id": 17,
                  "matriz": 0,
                  "placas": "PRUEBA111",
                  "marca": "Yamaha",
                  "modelo": "YBR125C Express",
                  "color": "Negro",
                  "num_serie": "1234567890",
                  "num_poliza": "0987654321",
                  "ultimo_servicio": null,
                  "created_at": "2019-08-23 18:12:50",
                  "updated_at": "2019-08-26 13:59:15",
                  "deleted_at": null
                },
                "incidencia_gasto": {
                  "id": 5,
                  "incidencia_id": 5,
                  "num_ticket": null,
                  "factura": 0,
                  "monto": null,
                  "pagado": null,
                  "litros_cargados": null,
                  "litros_aprobados": null,
                  "created_at": "2019-10-02 13:44:23",
                  "updated_at": "2019-10-02 13:44:23",
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
                        "created_at": "2019-10-02 13:44:23",
                        "updated_at": "2019-10-02 13:44:23"
                      }
                    }
                  ],
                  "media": []
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
            "vehiculo_id": [
              "El campo vehiculo id es obligatorio."
            ]
            "kilometraje": [
              "El campo kilometraje es obligatorio."
            ]
        } 

           
  * **Code:** 409 Conflict <br />
  **Content:** 

        {
          "error": "El kilometraje no coincide. Favor de verificar."
        } 
        
  * **Code:** 410 Gone <br />
  **Content:** 

        {
          "error": "No se ha realizado checkin del vehículo."
        } 
        
  * **Code:** 411 Length Required <br />
      **Content:** 
    
        {
          "error": "¡ERROR! Se debe agregar otro gasto adicional a Mano de obra."
        } 
        
       
                 
## Marcar como cotizada
Regresa la información de la incidencia actualizada

**URL**
  
    /api/incidencias/{ID}/cotizar
  
**Method:**

`POST`

**Headers**

      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data

**Data Params**
    
    'proveedor_id' => 'nullable',
    'gastos_ids' => 'required|array',
    'montos' => 'required|array',
    'monto' => 'required',
    'litros_cargados' => 'nullable',
    
    
**Success Response:**

* **Code:** 200 <br />
  **Content:**
      
      {
         "incidencia": {
             "id": 6,
             "folio": "MT006",
             "vehiculo_id": 3,
             "user_id": 17,
             "motivo_id": 2,
             "proveedor_id": null,
             "check_id": null,
             "kilometraje": 1000,
             "fecha": "2019-10-01",
             "observaciones": null,
             "tipo_creacion": "api_store",
             "created_at": "2019-10-02 17:53:26",
             "updated_at": "2019-10-02 17:53:26",
             "deleted_at": null,
             "kilometraje_evidencia": "images\/noimage.png",
             "problema_evidencia": "images\/noimage.png",
             "vehiculo": {
               "id": 3,
               "user_id": 17,
               "matriz": 0,
               "placas": "PRUEBA111",
               "marca": "Yamaha",
               "modelo": "YBR125C Express",
               "color": "Negro",
               "num_serie": "1234567890",
               "num_poliza": "0987654321",
               "ultimo_servicio": null,
               "created_at": "2019-08-23 18:12:50",
               "updated_at": "2019-08-26 13:59:15",
               "deleted_at": null
             },
             "user": {
               "id": 17,
               "nombre": "Supervisor",
               "apellido_paterno": "Prueba",
               "apellido_materno": null,
               "telefono": "Farma",
               "player_id": null,
               "email": "supervisor@farmapronto-sucursales.com",
               "old_email": null,
               "email_verified_at": null,
               "created_at": "2019-07-03 18:55:53",
               "updated_at": "2019-08-26 13:32:43",
               "deleted_at": null,
               "perfil_supervisor": {
                 "id": 1,
                 "user_id": 17,
                 "ext": "1",
                 "telefono_asignado": null,
                 "celular_personal": null,
                 "numero_seguro_social": null,
                 "contacto_emergencia": null,
                 "contacto_emergencia_telefono": null,
                 "grupo_sanguineo": null,
                 "alergias": null,
                 "created_at": "2019-07-03 18:55:53",
                 "updated_at": "2019-07-03 18:55:53",
                 "deleted_at": null
               }
             },
             "motivo": {
               "id": 2,
               "nombre": "Mantenimiento de la moto",
               "key": "mantenimiento",
               "prefix": "MT",
               "created_at": "2019-10-01 18:40:43",
               "updated_at": "2019-10-01 18:40:43",
               "deleted_at": null
             },
             "incidencia_gasto": {
               "id": 6,
               "incidencia_id": 6,
               "num_ticket": null,
               "factura": 0,
               "monto": 10000,
               "pagado": null,
               "litros_cargados": null,
               "litros_aprobados": null,
               "created_at": "2019-10-02 17:53:26",
               "updated_at": "2019-10-02 18:05:05",
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
                     "incidencia_gasto_id": 6,
                     "estatus_id": 1,
                     "user_id": 17,
                     "created_at": "2019-10-02 17:53:26",
                     "updated_at": "2019-10-02 17:53:26"
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
                     "incidencia_gasto_id": 6,
                     "estatus_id": 2,
                     "user_id": 17,
                     "created_at": "2019-10-02 17:53:26",
                     "updated_at": "2019-10-02 17:53:26"
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
                     "incidencia_gasto_id": 6,
                     "estatus_id": 4,
                     "user_id": 17,
                     "created_at": "2019-10-02 18:05:05",
                     "updated_at": "2019-10-02 18:05:05"
                   }
                 }
               ],
               "gastos": [
                 {
                   "id": 1,
                   "incidencia_gasto_id": 6,
                   "gasto_id": 1,
                   "monto": 100000,
                   "created_at": "2019-10-02 18:05:05",
                   "updated_at": "2019-10-02 18:05:05",
                   "deleted_at": null,
                   "gasto": {
                     "id": 1,
                     "motivo_id": 2,
                     "nombre": "Filtro Aceite",
                     "tiempo_vida": null,
                     "uso_promedio": null,
                     "tiempo_reparacion": null,
                     "created_at": "2019-10-02 16:25:40",
                     "updated_at": "2019-10-02 16:25:40",
                     "deleted_at": null
                   }
                 }
               ],
               "media": []
             },
             "proveedor": null,
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
            "gastos_ids": [
              "El campo gastos ids es obligatorio."
            ],
            "montos": [
              "El campo montos es obligatorio."
            ],
            "monto": [
              "El campo monto es obligatorio."
            ]
        }
        
          
* **Code:** 406 Not Acceptable <br />
**Content:** 

      {
        "error": "El usuario no cuenta con perfil de Supervisor"
      }
     
           
  * **Code:** 409 Conflict <br />
  **Content:** 

        {
          "error": "El monto del gasto NOMBRE excede el límite, favor de verificarlo o comunicarse con un supervisor."
        } 
        
        
          
## Marcar como reparada / confirmada
Regresa la información de la incidencia actualizada

**URL**
  
    /api/incidencias/{ID}/reparar
  
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
    'archivo_km' => 'nullable|image',
    'litros_cargados' => 'nullable',
    'kilometraje' => 'required',
    'evidencias' => 'nullable|array'
    
    
**Success Response:**

* **Code:** 200 <br />
  **Content:**
      
      {
         "incidencia": {
             "id": 2,
             "folio": "GA002",
             "vehiculo_id": 2,
             "user_id": 17,
             "motivo_id": 4,
             "proveedor_id": null,
             "check_id": 4,
             "kilometraje": 1010,
             "fecha": "2019-10-01",
             "observaciones": null,
             "tipo_creacion": "dashboard_checkin",
             "created_at": "2019-10-01 19:02:42",
             "updated_at": "2019-10-01 19:02:43",
             "deleted_at": null,
             "kilometraje_evidencia": "images\/noimage.png",
             "problema_evidencia": "images\/noimage.png",
             "user": {
               "id": 17,
               "nombre": "Supervisor",
               "apellido_paterno": "Prueba",
               "apellido_materno": null,
               "telefono": "Farma",
               "player_id": null,
               "email": "supervisor@farmapronto-sucursales.com",
               "old_email": null,
               "email_verified_at": null,
               "created_at": "2019-07-03 18:55:53",
               "updated_at": "2019-08-26 13:32:43",
               "deleted_at": null,
               "perfil_supervisor": {
                 "id": 1,
                 "user_id": 17,
                 "ext": "1",
                 "telefono_asignado": null,
                 "celular_personal": null,
                 "numero_seguro_social": null,
                 "contacto_emergencia": null,
                 "contacto_emergencia_telefono": null,
                 "grupo_sanguineo": null,
                 "alergias": null,
                 "created_at": "2019-07-03 18:55:53",
                 "updated_at": "2019-07-03 18:55:53",
                 "deleted_at": null
               }
             },
             "motivo": {
               "id": 4,
               "nombre": "Por gasolina",
               "key": "gasolina",
               "prefix": "GA",
               "created_at": "2019-10-01 18:40:43",
               "updated_at": "2019-10-01 18:40:43",
               "deleted_at": null
             },
             "vehiculo": {
               "id": 2,
               "user_id": 23,
               "matriz": 0,
               "placas": "ABCDE123",
               "marca": "Yamaha",
               "modelo": "YBR125C Express",
               "color": "Negro",
               "num_serie": "GFDSG3465336",
               "num_poliza": "34646436",
               "ultimo_servicio": null,
               "created_at": "2019-08-08 19:00:47",
               "updated_at": "2019-08-26 13:59:15",
               "deleted_at": null
             },
             "incidencia_gasto": {
               "id": 2,
               "incidencia_id": 2,
               "num_ticket": null,
               "factura": 0,
               "monto": 5000,
               "pagado": null,
               "litros_cargados": null,
               "litros_aprobados": 5,
               "created_at": "2019-10-01 19:02:42",
               "updated_at": "2019-10-02 11:07:43",
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
                     "incidencia_gasto_id": 2,
                     "estatus_id": 1,
                     "user_id": 1,
                     "created_at": "2019-10-01 19:02:42",
                     "updated_at": "2019-10-01 19:02:42"
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
                     "incidencia_gasto_id": 2,
                     "estatus_id": 2,
                     "user_id": 1,
                     "created_at": "2019-10-01 19:02:53",
                     "updated_at": "2019-10-01 19:02:43"
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
                     "incidencia_gasto_id": 2,
                     "estatus_id": 5,
                     "user_id": 17,
                     "created_at": "2019-10-02 11:07:43",
                     "updated_at": "2019-10-02 11:07:43"
                   }
                 }
               ],
               "media": []
             },
             "media": [
               {
                 "id": 99,
                 "model_type": "App\\Entities\\Incidencias\\Incidencia",
                 "model_id": 2,
                 "collection_name": "ticket_evidencia",
                 "name": "45188042-7f447a00-b1f8-11e8-9737-4fcdf046c05a",
                 "file_name": "45188042-7f447a00-b1f8-11e8-9737-4fcdf046c05a.png",
                 "mime_type": "image\/png",
                 "disk": "public",
                 "size": 378090,
                 "manipulations": [],
                 "custom_properties": [],
                 "responsive_images": [],
                 "order_column": 99,
                 "created_at": "2019-10-02 11:07:43",
                 "updated_at": "2019-10-02 11:07:43"
               },
               {
                 "id": 100,
                 "model_type": "App\\Entities\\Incidencias\\Incidencia",
                 "model_id": 2,
                 "collection_name": "ticket_evidencia",
                 "name": "45188042-7f447a00-b1f8-11e8-9737-4fcdf046c05a",
                 "file_name": "45188042-7f447a00-b1f8-11e8-9737-4fcdf046c05a.png",
                 "mime_type": "image\/png",
                 "disk": "public",
                 "size": 378090,
                 "manipulations": [],
                 "custom_properties": [],
                 "responsive_images": [],
                 "order_column": 100,
                 "created_at": "2019-10-02 11:09:14",
                 "updated_at": "2019-10-02 11:09:14"
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

   
**Verificar errores operativos**
----
  Verificar si existen incidencias que puedan generar errores operativos

 **URL**

  /api/incidencias/verificar-errores-operativos

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
            "incidencia": null,
            "num_error": 0
        }

 **Error Responses:**

  * **Code:** 401 Unauthorized <br />
    **Content:** 
    
        {
          "error": "Unauthenticated."
        }