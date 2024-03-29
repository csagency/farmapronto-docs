      
## Listado de vehículos
Regresa el listado del catálogo de Vehículos

 **URL**

  /api/catalogos/vehiculos

 **Method:**

  `GET`
        
  **URL Params**

  - filtrado=true <br><br>
  Ejemplo URI: `api/catalogos/vehiculos?filtrado=true&includes[]=sucursal`

**Success Response:**

* **Code:** 200 <br />
  **Content:** 
      
      {
          "vehiculos": [
              {
                  "id": 2,
                  "placas": "fgbfdgb",
                  "modelo": "fghfgh",
                  "marca": "Fiat",
                  "created_at": "2017-07-13 14:09:35",
                  "updated_at": "2017-07-13 16:41:28",
                  "deleted_at": null
              },
              {
                  "id": 3,
                  "placas": "fdgfd",
                  "modelo": "fdf",
                  "marca": "Nissan",
                  "created_at": "2017-07-13 16:39:53",
                  "updated_at": "2017-07-13 16:39:53",
                  "deleted_at": null
              }
          ]
      }



## Listado de vehículos por sucursal

Regresa el listado del catálogo de Vehículos por sucursal

 **URL**

  /api/catalogos/vehiculos/sucursal/{sucursal_id}

 **Method:**

  `GET`
        
  **URL Params**

  - filtrado=true <br><br>
  Ejemplo URI: `api/catalogos/vehiculos/sucursal/40?filtrado=true`

**Success Response:**

* **Code:** 200 <br />
  **Content:**


      {
      	"vehiculos": [
            {
              "id": 21,
              "sucursal_id": 40,
              "placas": "N2BN4",
              "modelo": "2017",
              "marca": "BAJAJ BOXER",
              "num_serie": "MD2A21BZ4HWC85064",
              "color": "NEGRO",
              "num_poliza": "280228032",
              "ultimo_servicio": "2018-08-22",
              "bloqueado": 0,
              "created_at": "2018-04-25 10:06:44",
              "updated_at": "2018-08-27 19:46:21",
              "deleted_at": null
            },
            {
              "id": 22,
              "sucursal_id": 40,
              "placas": "M6ZU2",
              "modelo": "Boxer 150 2015",
              "marca": "BAJAJ",
              "num_serie": "",
              "color": "",
              "num_poliza": "",
              "ultimo_servicio": "0000-00-00",
              "bloqueado": 0,
              "created_at": "2018-04-25 10:07:05",
              "updated_at": "2018-07-13 18:12:48",
              "deleted_at": null
            },
            {
              "id": 23,
              "sucursal_id": 40,
              "placas": "M6ZU2",
              "modelo": "2017",
              "marca": "BAJAJ BOXER",
              "num_serie": "MD2A21BZ4HWC85050",
              "color": "NEGRO",
              "num_poliza": "28027943",
              "ultimo_servicio": "2018-08-22",
              "bloqueado": 0,
              "created_at": "2018-04-25 10:07:06",
              "updated_at": "2019-01-23 11:19:28",
              "deleted_at": null
            },
            {
              "id": 24,
              "sucursal_id": 40,
              "placas": "WLM5H",
              "modelo": "2015",
              "marca": "BAJAJ BOXER",
              "num_serie": "MD2A21BZ2WA59070",
              "color": "BLANCO",
              "num_poliza": "280227877",
              "ultimo_servicio": "2018-08-22",
              "bloqueado": 0,
              "created_at": "2018-04-25 10:07:31",
              "updated_at": "2018-08-27 19:42:34",
              "deleted_at": null
            },
            {
              "id": 25,
              "sucursal_id": 40,
              "placas": "N7BW6",
              "modelo": "2017",
              "marca": "BAJAJ BOXER",
              "num_serie": "MD2A21BZ6HWM51839",
              "color": "ROJO",
              "num_poliza": "280228149",
              "ultimo_servicio": "2018-08-22",
              "bloqueado": 0,
              "created_at": "2018-04-25 10:07:50",
              "updated_at": "2018-08-27 19:47:55",
              "deleted_at": null
            }
        ]
      }


## Listado de vehículos con check-in por sucursal sin repartidor aceptado (agentes)

Regresa el listado del catálogo de Vehículos por sucursal con check-in que aún no son asignados a otro repartidor (Previo a Checkin agente)

 **URL**

    /api/catalogos/vehiculos/check-in/sucursal/{sucursal_id}/sin-repartidor

 **Method:**

    `GET`
  
 **URL Params**
    
      - turno= Matutino, Vespertino, Intermedio
      - Ejemplo URI: `/api/catalogos/vehiculos/check-in/sucursal/22/sin-repartidor?turno=Matutino`
      
    
 **Body**
 
    'turno' => 'required|in:Matutino,Vespertino,Intermedio'
    
**Success Response:**

* **Code:** 200 <br />
  **Content:**


      {
      	"vehiculos": [
            {
              "id": 21,
              "sucursal_id": 40,
              "placas": "N2BN4",
              "modelo": "2017",
              "marca": "BAJAJ BOXER",
              "num_serie": "MD2A21BZ4HWC85064",
              "color": "NEGRO",
              "num_poliza": "280228032",
              "ultimo_servicio": "2018-08-22",
              "created_at": "2018-04-25 10:06:44",
              "updated_at": "2018-08-27 19:46:21",
              "deleted_at": null
            }
        ]
      }

        
* **Code:** 422 Unproccesable Entity <br />
    **Content:** 
    
        {
            "turno": [
                "El campo turno es obligatorio."
            ]
        }
        

## Listado de vehículos con check-in por sucursal (sucursal)

Regresa el listado del catálogo de Vehículos por sucursal con check-in (Previo a checkout de Sucursal)

 **URL**

    /api/catalogos/vehiculos/check-in/sucursal/{sucursal_id}

 **Method:**

    `GET`
  
 **URL Params**
    
      - turno= Matutino, Vespertino, Intermedio
      - Ejemplo URI: `/api/catalogos/vehiculos/check-in/sucursal/22?turno=Matutino`
      
    
 **Body**
 
    'turno' => 'required|in:Matutino,Vespertino,Intermedio'

**Success Response:**

* **Code:** 200 <br />
  **Content:**


      {
      	"vehiculos": [
            {
              "id": 8,
              "sucursal_id": 23,
              "placas": "N4BG5",
              "modelo": "Boxer 150 2017",
              "marca": "Bajaj",
              "num_serie": "",
              "color": "",
              "num_poliza": "",
              "ultimo_servicio": "0000-00-00",
              "bloqueado": 0,
              "created_at": "2018-04-05 10:53:54",
              "updated_at": "2018-07-13 18:09:42",
              "deleted_at": null
            },
            {
              "id": 13,
              "sucursal_id": 22,
              "placas": "NEY2D",
              "modelo": "2017",
              "marca": "HONDA CARGO",
              "num_serie": "3H1KA4177HD415751",
              "color": "ROJO",
              "num_poliza": "280227927",
              "ultimo_servicio": "2018-08-03",
              "bloqueado": 0,
              "created_at": "2018-04-11 20:35:17",
              "updated_at": "2018-08-27 19:34:36",
              "deleted_at": null
            }
        ]
      }

        
* **Code:** 422 Unproccesable Entity <br />
    **Content:** 
    
        {
            "turno": [
                "El campo turno es obligatorio."
            ]
        }


## Listado de vehículos sin check-in por sucursal (sucursal)

Regresa el listado del catálogo de Vehículos por sucursal sin check-in (previo a Checkin sucursal)

 **URL**

    /api/catalogos/vehiculos/sin-check-in//sucursal/{sucursal_id}

 **Method:**

     `GET`
  
 **URL Params**
    
      - turno= Matutino, Vespertino, Intermedio
      - Ejemplo URI: `/api/catalogos/vehiculos/sin-check-in/sucursal/22?turno=Matutino`
      
    
 **Body**
 
    'turno' => 'required|in:Matutino,Vespertino,Intermedio'

**Success Response:**

* **Code:** 200 <br />
  **Content:**


      {
      	"vehiculos": [
            {
              "id": 22,
              "sucursal_id": 40,
              "placas": "M6ZU2",
              "modelo": "Boxer 150 2015",
              "marca": "BAJAJ",
              "num_serie": "",
              "color": "",
              "num_poliza": "",
              "ultimo_servicio": "0000-00-00",
              "created_at": "2018-04-25 10:07:05",
              "updated_at": "2018-07-13 18:12:48",
              "deleted_at": null
            },
            {
              "id": 23,
              "sucursal_id": 40,
              "placas": "M6ZU2",
              "modelo": "2017",
              "marca": "BAJAJ BOXER",
              "num_serie": "MD2A21BZ4HWC85050",
              "color": "NEGRO",
              "num_poliza": "28027943",
              "ultimo_servicio": "2018-08-22",
              "created_at": "2018-04-25 10:07:06",
              "updated_at": "2018-08-27 19:44:54",
              "deleted_at": null
            },
            {
              "id": 24,
              "sucursal_id": 40,
              "placas": "WLM5H",
              "modelo": "2015",
              "marca": "BAJAJ BOXER",
              "num_serie": "MD2A21BZ2WA59070",
              "color": "BLANCO",
              "num_poliza": "280227877",
              "ultimo_servicio": "2018-08-22",
              "created_at": "2018-04-25 10:07:31",
              "updated_at": "2018-08-27 19:42:34",
              "deleted_at": null
            },
            {
              "id": 25,
              "sucursal_id": 40,
              "placas": "N7BW6",
              "modelo": "2017",
              "marca": "BAJAJ BOXER",
              "num_serie": "MD2A21BZ6HWM51839",
              "color": "ROJO",
              "num_poliza": "280228149",
              "ultimo_servicio": "2018-08-22",
              "created_at": "2018-04-25 10:07:50",
              "updated_at": "2018-08-27 19:47:55",
              "deleted_at": null
            }
        ]
      }


        
* **Code:** 422 Unproccesable Entity <br />
    **Content:** 
    
        {
            "turno": [
                "El campo turno es obligatorio."
            ]
        }
 
**Datos de un vehículo**
----
  Regresa la información de un vehículo en específico y sus relaciones

 **URL**

  /api/catalogos/vehiculos/ID

 **Method:**

  `GET`
      
  **URL Params**

  - includes[]=agente, agente.user <br><br>
  Ejemplo URI: `api/catalogos/vehiculos/3?includes[]=agente.user`
  

 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 


     {
        "vehiculos": {
            "id": 3,
            "placas": "fdgfd",
            "modelo": "fdf",
            "marca": "Nissan",
            "created_at": "2017-07-13 16:39:53",
            "updated_at": "2017-07-13 16:39:53",
            "deleted_at": null,
            "agente": {
                "id": 12,
                "user_id": 138,
                "numero_control": "4564545",
                "estatus": 1,
                "created_at": "2017-07-13 18:39:54",
                "updated_at": "2017-07-13 18:39:54",
                "deleted_at": null,
                "lat": null,
                "lon": null,
                "imagen": null,
                "imagen_path": null,
                "vehiculo_id": 3,
                "user": {
                    "id": 138,
                    "name": "gfhdfghfh",
                    "last_name": "gfhdfhg",
                    "second_last_name": "gfdhgh",
                    "telephone": "",
                    "email": "jeeeeed34@hotmail.com",
                    "player_id": null,
                    "activo": 1,
                    "created_at": "2017-07-13 18:39:53",
                    "updated_at": "2017-07-13 18:39:53",
                    "deleted_at": null
                }
            }
        }
     }
        
 
        
**Registro de vehículo**
----
  Regresa la información del registro en formato json

 **URL**

  /api/catalogos/vehiculos

 **Method:**

  `POST`
  
  **URL Params**

  None
 
 **Data Params**

 ***Required:***
    
     placas=[required]
     marca=[required]
     modelo=[required]


 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
          "vehiculo": {
              "placas": "PXK1234",
              "marca": "Nissan",
              "modelo": "2013-D",
              "updated_at": "2017-07-14 12:45:40",
              "created_at": "2017-07-14 12:45:40",
              "id": 4
          }
        }
 
 **Error Response:**

  * **Code:** 422 Unprocessable Entity <br />
    **Content:** 
    
        {
          "placas": [
              "El campo placas es obligatorio."
          ],
          "marca": [
              "El campo marca es obligatorio."
          ],
          "modelo": [
              "El campo modelo es obligatorio."
          ]
        }

 
**Actualización del vehículo**
----
  Actualiza la información del vehículo

 **URL**

  /api/catalogos/vehiculos/ID

 **Method:**

  `PUT`
    
 **Multipart**
 
    placas:
    marca:
    modelo:
    
 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
          "vehiculo": {
              "id": 2,
              "placas": "PXK1234",
              "modelo": "2013-A",
              "marca": "Nissan",
              "created_at": "2017-07-13 14:09:35",
              "updated_at": "2017-07-14 12:50:35",
              "deleted_at": null
          }
        }
