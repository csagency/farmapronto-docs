## Listado de checks
Regresa el listado de los checks realizados por el usuario logueado

 **URL**

    /api/checks

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
          
   * **Code:** 406 Not Acceptable <br />
      **Content:** 
    
            {
              "message": "El usuario no cuenta con perfil de Supervisor/Capacitadora."
            }
             
            
                    
## Detalle de check
Regresa el registro de un check

 **URL**

    /api/checks/{ID}

 **Method:**

  `GET`
  
 **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data
     
 **URL Params**

      - includes[] = vehiculo, user.perfilSupervisor, user.perfilCapacitadora
        Ejemplo URI: `api/checks/1?includes[]=vehiculo`

**Success Response:**

* **Code:** 200 <br />
  **Content:** 
  
      {
            "check": {
                "id": 1,
                "user_id": 17,
                "vehiculo_id": 2,
                "check_id": null,
                "turno": "vespertino",
                "tipo": "checkin",
                "kilometraje": 1000,
                "estado_vehiculo": 1,
                "estado_llantas": 1,
                "licencia_vigencia": "2020-10-20",
                "observaciones": null,
                "created_at": "2019-08-12 10:20:20",
                "updated_at": "2019-08-12 10:20:20",
                "deleted_at": null,
                "kilometraje_evidencia": "images\/noimage.png",
                "estado_vehiculo_evidencia": "images\/noimage.png",
                "estado_llantas_evidencia": "images\/noimage.png",
                "nivel_gasolina": "\/storage\/checks\/niveles_gasolina\/22\/conversions\/35888217_2095034594077590_1878407717886885888_n-normal.jpg",
                "licencia": "\/storage\/checks\/licencias\/23\/conversions\/35888217_2095034594077590_1878407717886885888_n-normal.jpg",
                "tarjeta_circulacion": "\/storage\/checks\/tarjetas_circulacion\/24\/conversions\/35888217_2095034594077590_1878407717886885888_n-normal.jpg",
                "poliza_seguro": "\/storage\/checks\/polizas_seguro\/25\/conversions\/35888217_2095034594077590_1878407717886885888_n-normal.jpg",
                "frontal": "images\/noimage.png",
                "lateral_derecho": "images\/noimage.png",
                "lateral_izquierdo": "images\/noimage.png",
                "trasera": "images\/noimage.png",
                "llanta_delantera_derecha": "images\/noimage.png",
                "llanta_delantera_izquierda": "images\/noimage.png",
                "llanta_trasera_derecha": "images\/noimage.png",
                "llanta_trasera_izquierda": "images\/noimage.png",
                "permiso_carga": "images\/noimage.png",
                "gato": "images\/noimage.png",
                "cruceta": "images\/noimage.png",
                "llanta_refaccion": "images\/noimage.png",
                "luces_delanteras": "images\/noimage.png",
                "luces_traseras": "images\/noimage.png",
                "vehiculo": {
                  "id": 2,
                  "user_id": 17,
                  "placas": "ABCDE123",
                  "marca": "Yamaha",
                  "modelo": "YBR125C Express",
                  "color": "Negro",
                  "num_serie": "GFDSG3465336",
                  "num_poliza": "34646436",
                  "ultimo_servicio": null,
                  "created_at": "2019-08-08 19:00:47",
                  "updated_at": "2019-08-08 19:00:47",
                  "deleted_at": null
                },
                "user": {
                  "id": 17,
                  "perfil_id": null,
                  "nombre": "Supervisor",
                  "apellido_paterno": "Prueba",
                  "apellido_materno": null,
                  "telefono": "Farma",
                  "player_id": null,
                  "email": "supervisor@farmapronto-sucursales.com",
                  "email_verified_at": null,
                  "created_at": "2019-07-03 18:55:53",
                  "updated_at": "2019-07-03 18:55:53",
                  "deleted_at": null,
                  "perfil_supervisor": {
                    "id": 1,
                    "user_id": 17,
                    "zona_id": 4,
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
                "media": [
                  {
                    "id": 21,
                    "model_type": "App\\Entities\\Checks\\Check",
                    "model_id": 1,
                    "collection_name": "kilometraje",
                    "name": "35888217_2095034594077590_1878407717886885888_n",
                    "file_name": "35888217_2095034594077590_1878407717886885888_n.png",
                    "mime_type": "image\/png",
                    "disk": "checks_kilometrajes",
                    "size": 652647,
                    "manipulations": [],
                    "custom_properties": [],
                    "responsive_images": [],
                    "order_column": 21,
                    "created_at": "2019-08-12 10:20:20",
                    "updated_at": "2019-08-12 10:20:20"
                  },
                  {
                    "id": 22,
                    "model_type": "App\\Entities\\Checks\\Check",
                    "model_id": 1,
                    "collection_name": "nivel_gasolina",
                    "name": "35888217_2095034594077590_1878407717886885888_n",
                    "file_name": "35888217_2095034594077590_1878407717886885888_n.png",
                    "mime_type": "image\/png",
                    "disk": "checks_niveles_gasolina",
                    "size": 652647,
                    "manipulations": [],
                    "custom_properties": [],
                    "responsive_images": [],
                    "order_column": 22,
                    "created_at": "2019-08-12 10:20:21",
                    "updated_at": "2019-08-12 10:20:21"
                  },
                  {
                    "id": 23,
                    "model_type": "App\\Entities\\Checks\\Check",
                    "model_id": 1,
                    "collection_name": "licencia",
                    "name": "35888217_2095034594077590_1878407717886885888_n",
                    "file_name": "35888217_2095034594077590_1878407717886885888_n.png",
                    "mime_type": "image\/png",
                    "disk": "checks_licencias",
                    "size": 652647,
                    "manipulations": [],
                    "custom_properties": [],
                    "responsive_images": [],
                    "order_column": 23,
                    "created_at": "2019-08-12 10:20:21",
                    "updated_at": "2019-08-12 10:20:21"
                  },
                  {
                    "id": 24,
                    "model_type": "App\\Entities\\Checks\\Check",
                    "model_id": 1,
                    "collection_name": "tarjeta_circulacion",
                    "name": "35888217_2095034594077590_1878407717886885888_n",
                    "file_name": "35888217_2095034594077590_1878407717886885888_n.png",
                    "mime_type": "image\/png",
                    "disk": "checks_tarjetas_circulacion",
                    "size": 652647,
                    "manipulations": [],
                    "custom_properties": [],
                    "responsive_images": [],
                    "order_column": 24,
                    "created_at": "2019-08-12 10:20:21",
                    "updated_at": "2019-08-12 10:20:21"
                  },
                  {
                    "id": 25,
                    "model_type": "App\\Entities\\Checks\\Check",
                    "model_id": 1,
                    "collection_name": "poliza_seguro",
                    "name": "35888217_2095034594077590_1878407717886885888_n",
                    "file_name": "35888217_2095034594077590_1878407717886885888_n.png",
                    "mime_type": "image\/png",
                    "disk": "checks_polizas_seguro",
                    "size": 652647,
                    "manipulations": [],
                    "custom_properties": [],
                    "responsive_images": [],
                    "order_column": 25,
                    "created_at": "2019-08-12 10:20:21",
                    "updated_at": "2019-08-12 10:20:21"
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

    /api/checks

 **Method:**

  `POST`
  
  **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data

 
 **Data Params**
    
     'vehiculo_id' => 'required|exists:vehiculos,id',
     'turno' => 'nullable|in:matutino,vespertino,intermedio',
     'tipo' => 'required|in:checkin,checkout',
     'kilometraje' => 'required',
     'estado_vehiculo' => 'required|boolean',
     'estado_llantas' => 'required|boolean',
     'licencia_vigencia' => 'required|date',
     'observaciones' => 'nullable',
     'kilometraje_evidencia' => 'required|image',
     'estado_vehiculo_evidencia' => 'required_if:estado_vehiculo,==,0|image',
     'estado_llantas_evidencia' => 'required_if:estado_llantas,==,0|image',
     'nivel_gasolina' => 'required|image',
     'licencia' => 'required|image',
     'tarjeta_circulacion' => 'nullable|image',
     'poliza_seguro' => 'nullable|image',
     'frontal' => 'nullable|image',
     'lateral_derecho' => 'nullable|image',
     'lateral_izquierdo' => 'nullable|image',
     'trasera' => 'nullable|image',
     'llanta_delantera_derecha' => 'nullable|image',
     'llanta_delantera_izquierda' => 'nullable|image',
     'llanta_trasera_derecha' => 'nullable|image',
     'llanta_trasera_izquierda' => 'nullable|image',
     'permiso_carga' => 'nullable|image',
     'gato' => 'nullable|image',
     'cruceta' => 'nullable|image',
     'llanta_refaccion' => 'nullable|image',
     'luces_delanteras' => 'nullable|image',
     'luces_traseras' => 'nullable|image',
     'lat' => 'nullable',
     'lon' => 'nullable',


 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
            "check": {
                "user_id": 17,
                "vehiculo_id": 2,
                "check_id": null,
                "turno": "matutino",
                "tipo": "checkin",
                "kilometraje": "1000",
                "estado_vehiculo": "1",
                "estado_llantas": "1",
                "licencia_vigencia": "2020-10-20",
                "observaciones": null,
                "updated_at": "2019-08-12 10:27:58",
                "created_at": "2019-08-12 10:27:58",
                "id": 2,
                "kilometraje_evidencia": "\/storage\/checks\/kilometrajes\/26\/conversions\/35888217_2095034594077590_1878407717886885888_n-normal.jpg",
                "estado_vehiculo_evidencia": "images\/noimage.png",
                "estado_llantas_evidencia": "images\/noimage.png",
                "nivel_gasolina": "\/storage\/checks\/niveles_gasolina\/27\/conversions\/35888217_2095034594077590_1878407717886885888_n-normal.jpg",
                "licencia": "\/storage\/checks\/licencias\/28\/conversions\/35888217_2095034594077590_1878407717886885888_n-normal.jpg",
                "tarjeta_circulacion": "\/storage\/checks\/tarjetas_circulacion\/29\/conversions\/35888217_2095034594077590_1878407717886885888_n-normal.jpg",
                "poliza_seguro": "\/storage\/checks\/polizas_seguro\/30\/conversions\/35888217_2095034594077590_1878407717886885888_n-normal.jpg",
                "frontal": "images\/noimage.png",
                "lateral_derecho": "images\/noimage.png",
                "lateral_izquierdo": "images\/noimage.png",
                "trasera": "images\/noimage.png",
                "llanta_delantera_derecha": "images\/noimage.png",
                "llanta_delantera_izquierda": "images\/noimage.png",
                "llanta_trasera_derecha": "images\/noimage.png",
                "llanta_trasera_izquierda": "images\/noimage.png",
                "permiso_carga": "images\/noimage.png",
                "gato": "images\/noimage.png",
                "cruceta": "images\/noimage.png",
                "llanta_refaccion": "images\/noimage.png",
                "luces_delanteras": "images\/noimage.png",
                "luces_traseras": "images\/noimage.png",
                "media": [
                  {
                    "id": 26,
                    "model_type": "App\\Entities\\Checks\\Check",
                    "model_id": 2,
                    "collection_name": "kilometraje_evidencia",
                    "name": "35888217_2095034594077590_1878407717886885888_n",
                    "file_name": "35888217_2095034594077590_1878407717886885888_n.png",
                    "mime_type": "image\/png",
                    "disk": "checks_kilometrajes",
                    "size": 652647,
                    "manipulations": [],
                    "custom_properties": [],
                    "responsive_images": [],
                    "order_column": 26,
                    "created_at": "2019-08-12 10:27:58",
                    "updated_at": "2019-08-12 10:27:58"
                  },
                  {
                    "id": 27,
                    "model_type": "App\\Entities\\Checks\\Check",
                    "model_id": 2,
                    "collection_name": "nivel_gasolina",
                    "name": "35888217_2095034594077590_1878407717886885888_n",
                    "file_name": "35888217_2095034594077590_1878407717886885888_n.png",
                    "mime_type": "image\/png",
                    "disk": "checks_niveles_gasolina",
                    "size": 652647,
                    "manipulations": [],
                    "custom_properties": [],
                    "responsive_images": [],
                    "order_column": 27,
                    "created_at": "2019-08-12 10:27:58",
                    "updated_at": "2019-08-12 10:27:58"
                  },
                  {
                    "id": 28,
                    "model_type": "App\\Entities\\Checks\\Check",
                    "model_id": 2,
                    "collection_name": "licencia",
                    "name": "35888217_2095034594077590_1878407717886885888_n",
                    "file_name": "35888217_2095034594077590_1878407717886885888_n.png",
                    "mime_type": "image\/png",
                    "disk": "checks_licencias",
                    "size": 652647,
                    "manipulations": [],
                    "custom_properties": [],
                    "responsive_images": [],
                    "order_column": 28,
                    "created_at": "2019-08-12 10:27:58",
                    "updated_at": "2019-08-12 10:27:58"
                  },
                  {
                    "id": 29,
                    "model_type": "App\\Entities\\Checks\\Check",
                    "model_id": 2,
                    "collection_name": "tarjeta_circulacion",
                    "name": "35888217_2095034594077590_1878407717886885888_n",
                    "file_name": "35888217_2095034594077590_1878407717886885888_n.png",
                    "mime_type": "image\/png",
                    "disk": "checks_tarjetas_circulacion",
                    "size": 652647,
                    "manipulations": [],
                    "custom_properties": [],
                    "responsive_images": [],
                    "order_column": 29,
                    "created_at": "2019-08-12 10:27:58",
                    "updated_at": "2019-08-12 10:27:58"
                  },
                  {
                    "id": 30,
                    "model_type": "App\\Entities\\Checks\\Check",
                    "model_id": 2,
                    "collection_name": "poliza_seguro",
                    "name": "35888217_2095034594077590_1878407717886885888_n",
                    "file_name": "35888217_2095034594077590_1878407717886885888_n.png",
                    "mime_type": "image\/png",
                    "disk": "checks_polizas_seguro",
                    "size": 652647,
                    "manipulations": [],
                    "custom_properties": [],
                    "responsive_images": [],
                    "order_column": 30,
                    "created_at": "2019-08-12 10:27:58",
                    "updated_at": "2019-08-12 10:27:58"
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
            "vehiculo_id": [
              "El campo vehiculo id es obligatorio."
            ]
            "tipo": [
              "El campo tipo es obligatorio."
            ],
            "kilometraje": [
              "El campo kilometraje es obligatorio."
            ],
            "estado_vehiculo": [
              "El campo estado vehiculo es obligatorio."
            ],
            "estado_llantas": [
              "El campo estado llantas es obligatorio."
            ],
            "licencia_vigencia": [
              "El campo licencia vigencia es obligatorio."
            ],
            "kilometraje_evidencia": [
              "El campo kilometraje evidencia es obligatorio."
            ],
            "nivel_gasolina": [
              "El campo nivel gasolina es obligatorio."
            ],
            "licencia": [
              "El campo licencia es obligatorio."
            ],
            "tarjeta_circulacion": [
              "El campo tarjeta circulacion es obligatorio."
            ],
            "poliza_seguro": [
              "El campo poliza seguro es obligatorio."
            ]
            "estado_vehiculo_evidencia": [
              "El campo estado vehiculo evidencia es obligatorio cuando estado vehiculo es 0."
            ]
        }
        

           
  * **Code:** 409 Conflict <br />
  **Content:** 

        {
          "message": "El usuario no cuenta con un vehículo asignado."
        } 
        
   * **Code:** 410 Gone <br />
    **Content:** 
  
         {
           "message": "El kilometraje ingresado es inválido. Es mínimo al anterior o excede el límite."
         }  
        
          
**Editar información de checkin/checkout**
----
  Regresa la información del registro actualizado en formato json

 **URL**

    /api/checks/ID

 **Method:**

  `PUT`
  
  **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data

 
 **Data Params**
    
     'turno' => 'nullable|in:matutino,vespertino,intermedio',
     'tipo' => 'required|in:checkin,checkout',
     'kilometraje' => 'required',
     'estado_vehiculo' => 'required|boolean',
     'estado_llantas' => 'required|boolean',
     'licencia_vigencia' => 'nullable|date',
     'observaciones' => 'nullable',
     'kilometraje_evidencia' => 'nullable|image',
     'estado_vehiculo_evidencia' => 'required_if:estado_vehiculo,==,0|image',
     'estado_llantas_evidencia' => 'required_if:estado_llantas,==,0|image',
     'nivel_gasolina' => 'nullable|image',
     'licencia' => 'nullable|image',
     'tarjeta_circulacion' => 'nullable|image',
     'poliza_seguro' => 'nullable|image',
     'frontal' => 'nullable|image',
     'lateral_derecho' => 'nullable|image',
     'lateral_izquierdo' => 'nullable|image',
     'trasera' => 'nullable|image',
     'llanta_delantera_derecha' => 'nullable|image',
     'llanta_delantera_izquierda' => 'nullable|image',
     'llanta_trasera_derecha' => 'nullable|image',
     'llanta_trasera_izquierda' => 'nullable|image',
     'permiso_carga' => 'nullable|image',
     'gato' => 'nullable|image',
     'cruceta' => 'nullable|image',
     'llanta_refaccion' => 'nullable|image',
     'luces_delanteras' => 'nullable|image',
     'luces_traseras' => 'nullable|image',
     'lat' => 'nullable',
     'lon' => 'nullable',


 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
            "check": {
                "id": 3,
                "user_id": 17,
                "vehiculo_id": 2,
                "check_id": null,
                "turno": "vespertino",
                "tipo": "checkin",
                "kilometraje": "1000",
                "estado_vehiculo": "1",
                "estado_llantas": "1",
                "licencia_vigencia": "2020-10-20",
                "observaciones": null,
                "created_at": "2019-08-12 10:35:17",
                "updated_at": "2019-08-12 10:50:15",
                "deleted_at": null,
                "kilometraje_evidencia": "\/storage\/checks\/kilometrajes\/31\/conversions\/35888217_2095034594077590_1878407717886885888_n-normal.jpg",
                "estado_vehiculo_evidencia": "images\/noimage.png",
                "estado_llantas_evidencia": "images\/noimage.png",
                "nivel_gasolina": "\/storage\/checks\/niveles_gasolina\/32\/conversions\/35888217_2095034594077590_1878407717886885888_n-normal.jpg",
                "licencia": "\/storage\/checks\/licencias\/33\/conversions\/35888217_2095034594077590_1878407717886885888_n-normal.jpg",
                "tarjeta_circulacion": "\/storage\/checks\/tarjetas_circulacion\/34\/conversions\/35888217_2095034594077590_1878407717886885888_n-normal.jpg",
                "poliza_seguro": "\/storage\/checks\/polizas_seguro\/35\/conversions\/35888217_2095034594077590_1878407717886885888_n-normal.jpg",
                "frontal": "images\/noimage.png",
                "lateral_derecho": "images\/noimage.png",
                "lateral_izquierdo": "images\/noimage.png",
                "trasera": "images\/noimage.png",
                "llanta_delantera_derecha": "images\/noimage.png",
                "llanta_delantera_izquierda": "images\/noimage.png",
                "llanta_trasera_derecha": "images\/noimage.png",
                "llanta_trasera_izquierda": "images\/noimage.png",
                "permiso_carga": "images\/noimage.png",
                "gato": "images\/noimage.png",
                "cruceta": "images\/noimage.png",
                "llanta_refaccion": "images\/noimage.png",
                "luces_delanteras": "images\/noimage.png",
                "luces_traseras": "images\/noimage.png",
                "media": [
                  {
                    "id": 31,
                    "model_type": "App\\Entities\\Checks\\Check",
                    "model_id": 3,
                    "collection_name": "kilometraje_evidencia",
                    "name": "35888217_2095034594077590_1878407717886885888_n",
                    "file_name": "35888217_2095034594077590_1878407717886885888_n.png",
                    "mime_type": "image\/png",
                    "disk": "checks_kilometrajes",
                    "size": 652647,
                    "manipulations": [],
                    "custom_properties": [],
                    "responsive_images": [],
                    "order_column": 31,
                    "created_at": "2019-08-12 10:35:17",
                    "updated_at": "2019-08-12 10:35:17"
                  },
                  {
                    "id": 32,
                    "model_type": "App\\Entities\\Checks\\Check",
                    "model_id": 3,
                    "collection_name": "nivel_gasolina",
                    "name": "35888217_2095034594077590_1878407717886885888_n",
                    "file_name": "35888217_2095034594077590_1878407717886885888_n.png",
                    "mime_type": "image\/png",
                    "disk": "checks_niveles_gasolina",
                    "size": 652647,
                    "manipulations": [],
                    "custom_properties": [],
                    "responsive_images": [],
                    "order_column": 32,
                    "created_at": "2019-08-12 10:35:17",
                    "updated_at": "2019-08-12 10:35:17"
                  },
                  {
                    "id": 33,
                    "model_type": "App\\Entities\\Checks\\Check",
                    "model_id": 3,
                    "collection_name": "licencia",
                    "name": "35888217_2095034594077590_1878407717886885888_n",
                    "file_name": "35888217_2095034594077590_1878407717886885888_n.png",
                    "mime_type": "image\/png",
                    "disk": "checks_licencias",
                    "size": 652647,
                    "manipulations": [],
                    "custom_properties": [],
                    "responsive_images": [],
                    "order_column": 33,
                    "created_at": "2019-08-12 10:35:17",
                    "updated_at": "2019-08-12 10:35:17"
                  },
                  {
                    "id": 34,
                    "model_type": "App\\Entities\\Checks\\Check",
                    "model_id": 3,
                    "collection_name": "tarjeta_circulacion",
                    "name": "35888217_2095034594077590_1878407717886885888_n",
                    "file_name": "35888217_2095034594077590_1878407717886885888_n.png",
                    "mime_type": "image\/png",
                    "disk": "checks_tarjetas_circulacion",
                    "size": 652647,
                    "manipulations": [],
                    "custom_properties": [],
                    "responsive_images": [],
                    "order_column": 34,
                    "created_at": "2019-08-12 10:35:17",
                    "updated_at": "2019-08-12 10:35:17"
                  },
                  {
                    "id": 35,
                    "model_type": "App\\Entities\\Checks\\Check",
                    "model_id": 3,
                    "collection_name": "poliza_seguro",
                    "name": "35888217_2095034594077590_1878407717886885888_n",
                    "file_name": "35888217_2095034594077590_1878407717886885888_n.png",
                    "mime_type": "image\/png",
                    "disk": "checks_polizas_seguro",
                    "size": 652647,
                    "manipulations": [],
                    "custom_properties": [],
                    "responsive_images": [],
                    "order_column": 35,
                    "created_at": "2019-08-12 10:35:17",
                    "updated_at": "2019-08-12 10:35:17"
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
            "tipo": [
              "El campo tipo es obligatorio."
            ],
            "kilometraje": [
              "El campo kilometraje es obligatorio."
            ],
            "estado_vehiculo": [
              "El campo estado vehiculo es obligatorio."
            ],
            "estado_llantas": [
              "El campo estado llantas es obligatorio."
            ]
        }
          
          
## Último checkin activo de Supervisor
Regresa el último checkin que aún no cuenta con un checkout realizado por el usuario logueado 

**URL**
  
  /api/me/checkin-activos
  
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
            "created_at": "2019-08-12 18:21:45",
            "updated_at": "2019-08-12 18:21:45",
            "deleted_at": null,
            "kilometraje_evidencia": "images\/noimage.png",
            "estado_vehiculo_evidencia": "images\/noimage.png",
            "estado_llantas_evidencia": "images\/noimage.png",
            "nivel_gasolina": "images\/noimage.png",
            "licencia": "images\/noimage.png",
            "tarjeta_circulacion": "images\/noimage.png",
            "poliza_seguro": "images\/noimage.png",
            "frontal": "images\/noimage.png",
            "lateral_derecho": "images\/noimage.png",
            "lateral_izquierdo": "images\/noimage.png",
            "trasera": "images\/noimage.png",
            "llanta_delantera_derecha": "images\/noimage.png",
            "llanta_delantera_izquierda": "images\/noimage.png",
            "llanta_trasera_derecha": "images\/noimage.png",
            "llanta_trasera_izquierda": "images\/noimage.png",
            "permiso_carga": "images\/noimage.png",
            "gato": "images\/noimage.png",
            "cruceta": "images\/noimage.png",
            "llanta_refaccion": "images\/noimage.png",
            "luces_delanteras": "images\/noimage.png",
            "luces_traseras": "images\/noimage.png",
            "media": []
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
        "message": "El usuario no cuenta con perfil de Supervisor"
      }
