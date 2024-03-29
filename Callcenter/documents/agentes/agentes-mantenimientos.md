      
## Listado de mantenimiento del agente
Regresa el listado de los mantenimientos realizados por el agente

 **URL**

  /api/agentes/mantenimiento

 **Method:**

  `GET`
  
 **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json

**URL Params**

  - includes[]= agente, vehiculo  <br><br>
  Ejemplo URI: `api/agentes/mantenimiento?includes[]=agente`
  

**Success Response:**

* **Code:** 200 <br />
  **Content:** 
  
      {
      	"mantenimientos": [
            {
                "id": 1,
                "agente_id": 21,
                "vehiculo_id": 1,
                "turno": "Intermedio",
                "estado_moto": 0,
                "moto_inconveniente": null,
                "estado_llantas": 1,
                "llanta_ponchada": "fsdff",
                "encendido_moto": 1,
                "kilometraje": 200,
                "kilometraje_evidencia": "file",
                "nivel_gasolina": "sdff",
                "nivel_aceite": null,
                "casco": null,
                "impermeable": null,
                "observaciones": null,
                "created_at": "2017-11-29 12:05:52",
                "updated_at": "2017-11-29 12:14:01",
                "agente": {
                    "id": 21,
                    "user_id": 1,
                    "numero_control": "543635466",
                    "estatus": 0,
                    "puesto": null,
                    "created_at": "2017-11-06 18:57:53",
                    "updated_at": "2017-11-07 12:56:58",
                    "deleted_at": null,
                    "lat": null,
                    "lon": null,
                    "imagen": null,
                    "imagen_path": null,
                    "vehiculo_id": 1
                },
                "vehiculo": {
                    "id": 1,
                    "placas": "FGSFD43",
                    "modelo": "Nosé",
                    "marca": "Nosé",
                    "created_at": "2017-11-06 17:21:56",
                    "updated_at": "2017-11-06 17:21:56",
                    "deleted_at": null
                }
            }
        ]
      }

**Error Response:**

* **Code:** 401 Unauthorized <br />
  **Content:** 
  
      {
        "error": "Unauthenticated."
      }
      
* **Code:** 409 Conflict <br />
**Content:** 

        {
          "error": "El usuario no cuenta con perfil de agente."
        }

      
## Listado de mantenimientos del día del agente
Regresa el listado de los mantenimientos realizados en el día por el agente

 **URL**

  /api/agentes/mantenimiento/dia

 **Method:**

  `GET`
  
 **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json

**URL Params**

  - includes[]= agente, vehiculo  <br><br>
  Ejemplo URI: `api/agentes/mantenimiento/dia?includes[]=agente`
  

**Success Response:**

* **Code:** 200 <br />
  **Content:** 
  
      {
      	"mantenimientos": [
            {
                "id": 1,
                "agente_id": 21,
                "vehiculo_id": 1,
                "turno": "Intermedio",
                "estado_moto": 0,
                "moto_inconveniente": null,
                "estado_llantas": 1,
                "llanta_ponchada": "fsdff",
                "encendido_moto": 1,
                "kilometraje": 200,
                "kilometraje_evidencia": "file",
                "nivel_gasolina": "sdff",
                "nivel_aceite": null,
                "licencia": null,
                "lateral_izquierda_moto": null,
                "lateral_derecha_moto": null,
                "frontal_moto": null,
                "trasera_moto": null,
                "casco": null,
                "impermeable": null,
                "tarjeta_circulacion": null,
                "poliza_seguro": null,
                "agente_sonriendo": null,
                "observaciones": null,
                "aprobado": 0,
                "created_at": "2017-11-29 12:05:52",
                "updated_at": "2017-11-29 12:14:01",
                "agente": {
                    "id": 21,
                    "user_id": 1,
                    "numero_control": "543635466",
                    "estatus": 0,
                    "puesto": null,
                    "created_at": "2017-11-06 18:57:53",
                    "updated_at": "2017-11-07 12:56:58",
                    "deleted_at": null,
                    "lat": null,
                    "lon": null,
                    "imagen": null,
                    "imagen_path": null,
                    "vehiculo_id": 1
                },
                "vehiculo": {
                    "id": 1,
                    "placas": "FGSFD43",
                    "modelo": "Nosé",
                    "marca": "Nosé",
                    "created_at": "2017-11-06 17:21:56",
                    "updated_at": "2017-11-06 17:21:56",
                    "deleted_at": null
                }
            }
        ]
      }

**Error Response:**

* **Code:** 401 Unauthorized <br />
  **Content:** 
  
      {
        "error": "Unauthenticated."
      }
      
* **Code:** 409 Conflict <br />
**Content:** 

        {
          "error": "El usuario no cuenta con perfil de agente."
        }

      
      
**Registro de mantenimiento**
----
  Regresa la información del registro en formato json

 **URL**

  /api/agentes/mantenimiento/

 **Method:**

  `POST`
  
  **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data

 
 **Data Params**

 ***Required:***
    
     'vehiculo_id' => 'required|exists:vehiculos,id',
     'turno' => 'required',in:'Matutino', 'Intermedio', 'Vespertino',
     'estado_moto' => 'required|boolean',
     'checkin_id' => 'required_if:tipo,checkout',
     'moto_inconveniente' => 'required_if:estado_moto,==,1',
     'estado_llantas' => 'nullable|boolean',
     'llanta_ponchada' => 'required_if:estado_llantas,==,0',
     'encendido_moto' => 'nullable|boolean',
     'kilometraje' => 'nullable',
     'kilometraje_evidencia' => 'required',
     'nivel_gasolina' => 'nullable',
     'nivel_aceite' => 'nullable',
     'licencia' => 'nullable',
     'licencia_aa' => 'nullable|digits:2',
     'licencia_mm' => 'nullable|digits:2',
     'licencia_dd' => 'nullable|digits:2',
     'casco' => 'nullable',
     'impermeable' => 'nullable',
     'observaciones' => 'nullable',
     'tipo' => 'nullable|in:checkin,checkout',
     'poliza_seguro' => 'nullable|image',
     'tarjeta_circulacion' => 'nullable|image',
     'frontal_moto' => 'nullable|image',
     'trasera_moto' => 'nullable|image',
     'lateral_derecha_moto' => 'nullable|image',
     'lateral_izquierda_moto' => 'nullable|image',
     'celular_foto' => 'nullable|image',
     'llaves_moto_foto' => 'nullable|image',
     'agente_sonriendo' => 'nullable|image',



  **Success Response:**

  * **Code:** 200 <br />
    **Content**



    {
      "mantenimiento": {
        "id": 54185,
        "agente_id": 90,
        "vehiculo_id": 42,
        "checkin_id": null,
        "llaves_moto_foto": null,
        "celular_foto": null,
        "turno": "Matutino",
        "tipo": null,
        "estado_moto": 0,
        "moto_inconveniente": null,
        "estado_llantas": 1,
        "llanta_ponchada": null,
        "encendido_moto": 1,
        "kilometraje": 400,
        "kilometraje_evidencia": null,
        "nivel_gasolina": null,
        "nivel_aceite": null,
        "licencia": null,
        "licencia_dd": null,
        "licencia_mm": null,
        "licencia_aa": null,
        "lateral_izquierda_moto": null,
        "lateral_derecha_moto": null,
        "frontal_moto": null,
        "trasera_moto": null,
        "tarjeta_circulacion": null,
        "poliza_seguro": null,
        "casco": null,
        "impermeable": null,
        "agente_sonriendo": null,
        "observaciones": null,
        "aprobado": 0,
        "created_at": "2020-10-03 11:55:07",
        "updated_at": "2020-10-03 11:55:07",
        "deleted_at": null,
        "vehiculo": {
          "id": 42,
          "sucursal_id": 84,
          "placas": "CS-381",
          "modelo": "YBR125C Express",
          "marca": "Yamaha",
          "num_serie": "",
          "color": "",
          "num_poliza": "",
          "ultimo_servicio": "0000-00-00",
          "bloqueado": 0,
          "created_at": "2019-04-29 13:10:43",
          "updated_at": "2019-08-02 19:12:49",
          "deleted_at": null,
          "sucursal": {
            "id": 84,
            "user_id": 2429,
            "codigo": "cs-2",
            "nombre": "Sucursal CS NO ELIMINAR",
            "telefono": "7777771234",
            "email_oficial": null,
            "colonia_id": 34641,
            "municipio_id": 502,
            "estado_id": 17,
            "zona_sucursal_id": 3,
            "ciudad_cobertura_id": 1,
            "direccion": "Ahuatepec 307",
            "direccion_numero": "222222",
            "codigo_postal": "62000",
            "lon": "-99.228404",
            "lat": "18.938236",
            "ancla": 0,
            "checkin": 1,
            "dias": "LUN, MAR, MIE, JUE, VIE",
            "horario_inicio": "07:00:00",
            "horario_final": "20:00:00",
            "24_hrs": 0,
            "base": 1,
            "almacen": 0,
            "comercializadora": 1,
            "pickup": 0,
            "domicilio_propios": 1,
            "domicilio_terceros": 0,
            "disponible": 0,
            "km_cobertura": 10,
            "created_at": "2018-11-30 13:45:25",
            "updated_at": "2020-08-03 13:56:12",
            "deleted_at": null
          }
        },
        "estatus": [
          {
            "id": 92059,
            "mantenimiento_id": 54185,
            "nombre": "enviado",
            "user_id": 2290,
            "created_at": "2020-10-03 11:55:07",
            "updated_at": "2020-10-03 11:55:07"
          }
        ],
        "estado": {
          "id": 92059,
          "mantenimiento_id": 54185,
          "nombre": "enviado",
          "user_id": 2290,
          "created_at": "2020-10-03 11:55:07",
          "updated_at": "2020-10-03 11:55:07"
        },
        "estatus_historico": [
          {
            "id": 92059,
            "mantenimiento_id": 54185,
            "nombre": "enviado",
            "user_id": 2290,
            "created_at": "2020-10-03 11:55:07",
            "updated_at": "2020-10-03 11:55:07"
          }
        ],
        "agente": {
          "id": 90,
          "user_id": 2290,
          "numero_control": "0011",
          "estatus": 0,
          "puesto": null,
          "created_at": "2018-06-11 13:15:36",
          "updated_at": "2020-10-03 11:51:47",
          "deleted_at": null,
          "lat": "18.9361024",
          "lon": "-99.2303452",
          "imagen": null,
          "imagen_path": null,
          "vehiculo_id": 2,
          "sucursal_base_id": null,
          "supervisor": 0,
          "cant_errores_actuales": 0
        }
      }
    }




****Listado de Vehículos****
[Vehículos GET](https://github.com/csagency/farmapronto/blob/develop/resources/docs/catalogos/vehiculos.md#listado-de-vehículos)


 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
            "mantenimiento": {
                "id": 16,
                "agente_id": 21,
                "vehiculo_id": 1,
                "turno": "Matutino",
                "estado_moto": 0,
                "moto_inconveniente": null,
                "estado_llantas": 1,
                "llanta_ponchada": null,
                "encendido_moto": 1,
                "kilometraje": null,
                "kilometraje_evidencia": "mantenimiento\/cgGV5xKBdDRSRwyOpnmJZgiFMZHw4z7YTV7TdrZk.png",
                "nivel_gasolina": null,
                "nivel_aceite": null,
                "licencia": null,
                "casco": null,
                "impermeable": null,
                "observaciones": null,
                "created_at": "2017-11-30 11:52:47",
                "updated_at": "2017-11-30 11:52:47",
                "vehiculo": {
                    "id": 1,
                    "placas": "FGSFD43",
                    "modelo": "Nosé",
                    "marca": "Nosé",
                    "created_at": "2017-11-06 17:21:56",
                    "updated_at": "2017-11-06 17:21:56",
                    "deleted_at": null
                },
                "agente": {
                    "id": 21,
                    "user_id": 1,
                    "numero_control": "543635466",
                    "estatus": 0,
                    "puesto": null,
                    "created_at": "2017-11-06 18:57:53",
                    "updated_at": "2017-11-07 12:56:58",
                    "deleted_at": null,
                    "lat": null,
                    "lon": null,
                    "imagen": null,
                    "imagen_path": null,
                    "vehiculo_id": 1,
                    "user": {
                        "id": 1,
                        "name": "Desarrollo",
                        "last_name": "Farmapronto",
                        "second_last_name": " test",
                        "telephone": "7777777777",
                        "email": "server@csgroup.mx",
                        "player_id": null,
                        "activo": 1,
                        "slack_webhook_url": null,
                        "created_at": "2017-08-29 12:22:11",
                        "updated_at": "2017-08-29 12:22:11",
                        "deleted_at": null,
                        "last_login": null
                    }
                }
            }
        }
 
 **Error Response:**

  * **Code:** 422 Unprocessable Entity <br />
    **Content:** 
    
        {
            "vehiculo_id": [
                "El campo vehiculo id es obligatorio."
            ],
            "turno": [
                "El campo turno es inválido."
            ],
            "moto_inconveniente": [
                "El campo moto inconveniente es obligatorio cuando estado moto es 1."
            ],
            "estado_llantas": [
                "El campo estado llantas debe tener un valor verdadero o falso."
            ],
            "encendido_moto": [
                "El campo encendido moto debe tener un valor verdadero o falso."
            ],
            "kilometraje_evidencia": [
                "kilometraje evidencia debe ser una imagen."
            ]
            "nivel_gasolina": [
                "nivel gasolina debe ser una imagen."
            ]
            "nivel_aceite": [
                "nivel aceite debe ser una imagen."
            ]
            "licencia": [
                "licencia debe ser una imagen."
            ]
            "licencia_aa": [
               "El licencia aa debe tener 2 dígitos."
            ]
            "licencia_mm": [
               "El licencia mm debe tener 2 dígitos."
            ]
            "licencia_dd": [
               "El licencia dd debe tener 2 dígitos."
            ]
            "casco": [
                "casco debe ser una imagen."
            ]
            "impermeable": [
                "impermeable debe ser una imagen."
            ]
        }


  * **Code:** 409 Conflict <br />
    **Content:** 
    
        {
          "error": "El kilometraje ingresado es inválido. Es mínimo al anterior o excede el límite.."
        }
           


**Datos del mantenimiento**
----
  Regresa la información de un mantenimiento realizado por el agente

 **URL**

  /api/agentes/mantenimiento/ID

 **Method:**

  `GET`
  
  **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data
      
  **URL Params**

  - includes[]= agente, vehiculo <br><br>
  Ejemplo URI: `api/agentes/mantenimiento/1?includes[]=agente&&includes[]=vehiculo`
  

 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
        	"mantenimiento": {
                "id": 1,
                "agente_id": 21,
                "vehiculo_id": 1,
                "turno": "Matutino",
                "estado_moto": 0,
                "moto_inconveniente": null,
                "estado_llantas": 1,
                "llanta_ponchada": null,
                "encendido_moto": 1,
                "kilometraje": 111111,
                "kilometraje_evidencia": "file",
                "nivel_gasolina": "file",
                "nivel_aceite": null,
                "casco": null,
                "impermeable": null,
                "observaciones": null,
                "created_at": "2017-11-29 12:05:52",
                "updated_at": "2017-11-29 12:05:52",
                "agente": {
                    "id": 21,
                    "user_id": 1,
                    "numero_control": "543635466",
                    "estatus": 0,
                    "puesto": null,
                    "created_at": "2017-11-06 18:57:53",
                    "updated_at": "2017-11-07 12:56:58",
                    "deleted_at": null,
                    "lat": null,
                    "lon": null,
                    "imagen": null,
                    "imagen_path": null,
                    "vehiculo_id": 1
                },
                "vehiculo": {
                    "id": 1,
                    "placas": "FGSFD43",
                    "modelo": "NOSE",
                    "marca": "NOSE",
                    "created_at": "2017-11-06 17:21:56",
                    "updated_at": "2017-11-06 17:21:56",
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


**Eliminar mantenimiento**
----
  Elimina un mantenimiento en específico y sus imagenes almacenadas

 **URL**

  /api/agentes/mantenimiento/ID

 **Method:**

  `DELETE`
    
 **Headers**
  
     Authorization: Bearer access_token
     Accept: application/json
     Content-Type: multipart/form-data
    
    
 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
        	"mantenimiento": null
        }

 **Error Responses:**

  * **Code:** 401 Unauthorized <br />
    **Content:** 
    
        {
          "error": "Unauthenticated."
        }
           
      
**Editar mantenimiento**
----
  Regresa la información del registro editado en formato json

 **URL**

  /api/agentes/mantenimiento/{ID}

 **Method:**

  `PUT`
  
  **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data

 
 **Data Params**

 ***Required:***
    
     'vehiculo_id' => 'nullable|exists:vehiculos,id',
     'turno' => 'nullable|in:Matutino, Intermedio, Vespertino',
     'estado_moto' => 'nullable|boolean',
     'checkin_id' => 'nullable',
     'moto_inconveniente' => 'nullable|image',
     'estado_llantas' => 'nullable|boolean',
     'llanta_ponchada' => 'nullable|image',
     'encendido_moto' => 'nullable|boolean',
     'kilometraje' => 'nullable',
     'kilometraje_evidencia' => 'nullable|image',
     'nivel_gasolina' => 'nullable|image',
     'nivel_aceite' => 'nullable|image',
     'licencia' => 'nullable|image',
     'licencia_aa' => 'nullable|digits:2',
     'licencia_mm' => 'nullable|digits:2',
     'licencia_dd' => 'nullable|digits:2',
     'casco' => 'nullable',
     'impermeable' => 'nullable|image',
     'observaciones' => 'nullable',
     'tipo' => 'nullable|in:checkin,checkout',
     'poliza_seguro' => 'nullable|image',
     'tarjeta_circulacion' => 'nullable|image',
     'frontal_moto' => 'nullable|image',
     'trasera_moto' => 'nullable|image',
     'lateral_derecha_moto' => 'nullable|image',
     'lateral_izquierda_moto' => 'nullable|image',
     'celular_foto' => 'nullable|image',
     'llaves_moto_foto' => 'nullable|image',
     'agente_sonriendo' => 'nullable|image',


 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
            "mantenimiento": {
                "id": 9215,
                "agente_id": 132,
                "vehiculo_id": 12,
                "checkin_id": null,
                "llaves_moto_foto": null,
                "celular_foto": null,
                "turno": "Vespertino",
                "tipo": "checkin",
                "estado_moto": 0,
                "moto_inconveniente": null,
                "estado_llantas": 1,
                "llanta_ponchada": null,
                "encendido_moto": 1,
                "kilometraje": 48000,
                "kilometraje_evidencia": "uploads\/images\/mantenimiento\/NTPFYadThsAJQpy4UIMeIUoC2VYec3eACrAvB5Ou.jpeg",
                "nivel_gasolina": "uploads\/images\/mantenimiento\/Ho7M430pO11D6Thy9BUBVVOxMif2ybwHassvZysq.jpeg",
                "nivel_aceite": "uploads\/images\/mantenimiento\/nhemuYFeau5BpUgxWKwH2GxPc0ZmkPfP4wWK1Bgb.jpeg",
                "licencia": "uploads\/images\/mantenimiento\/V3uctiTVNATs2BQXRTQtIzj6e5AH88ZfQbokYP0X.jpeg",
                "lateral_izquierda_moto": null,
                "lateral_derecha_moto": null,
                "frontal_moto": null,
                "trasera_moto": null,
                "tarjeta_circulacion": "uploads\/images\/mantenimiento\/DcPHwVrRj8ITP7dDQKYkVEG5eniAxPqTGRqRUoDy.jpeg",
                "poliza_seguro": "uploads\/images\/mantenimiento\/oyyEaI3p70BoHTcCrQCVUWy8PjBkkulvWd2gcDr9.jpeg",
                "casco": "CSC01234CS",
                "impermeable": "uploads\/images\/mantenimiento\/zR6UoDczvUBeyGrhtYmGHMzFV3spOEn1fWZ791mo.jpeg",
                "agente_sonriendo": null,
                "observaciones": "ninguno",
                "aprobado": 0,
                "sucursal": 0,
                "user_id": null,
                "created_at": "2019-01-08 15:31:18",
                "updated_at": "2019-01-16 18:35:25",
                "vehiculo": {
                  "id": 12,
                  "sucursal_id": 22,
                  "placas": "M1UB9",
                  "modelo": "2016",
                  "marca": "YAMAHA 125 EXPRESS",
                  "num_serie": "LBPKE1245G0094407",
                  "color": "BLANCO",
                  "num_poliza": "280227885",
                  "ultimo_servicio": "2018-08-01",
                  "created_at": "2018-04-11 20:34:55",
                  "updated_at": "2018-08-27 19:33:23",
                  "deleted_at": null
                },
                "agente": {
                  "id": 132,
                  "user_id": 9370,
                  "numero_control": "4322",
                  "estatus": 1,
                  "puesto": null,
                  "created_at": "2018-11-12 11:05:56",
                  "updated_at": "2019-01-08 16:49:46",
                  "deleted_at": null,
                  "lat": "18.9037722",
                  "lon": "-99.2195713",
                  "imagen": null,
                  "imagen_path": null,
                  "vehiculo_id": 13,
                  "supervisor": 0,
                  "user": {
                    "id": 9370,
                    "name": "JOSE LUIS",
                    "last_name": "CONTRERAS",
                    "second_last_name": "MARTINEZ",
                    "telephone": "7774538729",
                    "clave": null,
                    "email": "repartidor4322@grupofarmapronto.com",
                    "player_id": "8fcc3277-95b9-40ee-aed4-fe00fefb5443",
                    "activo": 1,
                    "fb_id": null,
                    "slack_webhook_url": null,
                    "created_at": "2018-11-12 11:05:56",
                    "updated_at": "2019-01-08 15:46:17",
                    "deleted_at": null,
                    "last_login": null
                  }
                }
            }
        }
 
 **Error Response:**

  * **Code:** 422 Unprocessable Entity <br />
    **Content:** 
    
        {
            "turno": [
               "El campo turno es inválido."
            ],
            "estado_moto": [
              "El campo estado moto debe tener un valor verdadero o falso."
            ],
            "encendido_moto": [
              "El campo encendido moto debe tener un valor verdadero o falso."
            ],
            "kilometraje_evidencia": [
              "kilometraje evidencia debe ser una imagen."
            ]
            "licencia_aa": [
               "El licencia aa debe tener 2 dígitos."
            ]
            "licencia_mm": [
               "El licencia mm debe tener 2 dígitos."
            ]
            "licencia_dd": [
               "El licencia mm debe tener 2 dígitos."
            ]
        }



  * **Code:** 409 Conflict <br />
    **Content:** 
    
        {
          "error": "El kilometraje ingresado es inválido. Es mínimo al anterior o excede el límite.."
        }
         


     
**Validar checkout**
----
  Regresa los pedidos pendientes del repartidor

 **URL**

    /api/agentes/mantenimiento/validar-checkout

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
          "pedidos_pendientes": [
            {
              "agente_id": 28,
              "pedido_id": 137064,
              "aceptado": 1,
              "liberado": 0,
              "cancelado": 0,
              "activo": 0,
              "nip": "CTZY",
              "cancelado_motivo": null,
              "created_at": "2020-07-16 12:24:56",
              "updated_at": "2020-07-16 12:24:56",
              "eliminado": 0,
              "user_id": null
            }
          ]
        }
 
 **Error Response:**

* **Code:** 401 Unauthorized <br />
  **Content:** 
  
      {
        "error": "Unauthenticated."
      }
      
      
     
**Siguiente jornada**
----
  Regresa los pedidos pendientes del repartidor

 **URL**

    /api/agentes/mantenimiento/jornada

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
          "sig_jornada": {
              "id": 10,
              "user_id": 164,
              "sucursal_id": 23,
              "turno": "matutino",
              "entrada_at": "2020-07-30 07:00:00",
              "salida_at": "2020-07-30 15:00:00",
              "created_at": "2020-07-29 14:19:22",
              "updated_at": "2020-07-29 14:19:22",
              "deleted_at": null
          }
        }
 
 **Error Response:**

* **Code:** 401 Unauthorized <br />
  **Content:** 
  
      {
        "error": "Unauthenticated."
      }