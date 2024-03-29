## Listado de registros repartidores v2

Regresa el listado de registros de repartidores de la sucursal

 **URL**

    /api-v2/sucursales/repartidores

 **Method:**

  `GET`
  
 **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json

**Success Response:**

* **Code:** 200 <br />
  **Content:** 
  
      {
           "repartidores": [
             {
               "id": 1,
               "nombre": "Repartidor",
               "apellido_paterno": "Prueba",
               "apellido_materno": "V2",
               "sucursal_id": 22,
               "created_at": "2020-05-08 18:10:53",
               "updated_at": "2020-05-08 18:10:53",
               "deleted_at": null
             }
           ]
      }

**Error Response:**

* **Code:** 401 Unauthorized <br />
  **Content:** 
  
      {
        "error": "Unauthenticated."
      }
       
       
       
** Crear registro de repartidores **
----
  Regresa la información del registro en formato json

 **URL**

    /api-v2/sucursales/repartidores


  **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: application/x-www-form-urlencoded

 **Method:**

  `POST`
  
  **URL Params**

  None
 
 **Data Params**
    
    'nombre' => 'required',
    'apellido_paterno' => 'nullable',
    'apellido_materno' => 'nullable',
    'sucursal_id' => 'required|exists:sucursales,id',


 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
              "repartidor": {
                "nombre": "Repartidor",
                "apellido_paterno": "Prueba",
                "apellido_materno": "V2",
                "sucursal_id": "22",
                "updated_at": "2020-05-08 18:10:53",
                "created_at": "2020-05-08 18:10:53",
                "id": 1
              }
        }
 **Error Response:**

  * **Code:** 422 Unprocessable Entity <br />
    **Content:** 
    
        {
                "nombre": [
                  "El campo nombre es obligatorio."
                ],
                "sucursal_id": [
                  "El campo sucursal id es obligatorio."
                ]
        }
        
  * **Code:** 401 Unauthorized <br />
      **Content:** 
      
          {
            "error": "Unauthenticated."
          }
 
 
**Datos del repartidor**
----
  Regresa la información del repartidor

 **URL**

    /api-v2/sucursales/repartidores/ID

 **Method:**

  `GET`
  
  **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
    

 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
        	  "repartidor": {
                "id": 1,
                "nombre": "Repartidor",
                "apellido_paterno": "Prueba",
                "apellido_materno": "V2",
                "sucursal_id": 22,
                "created_at": "2020-05-08 18:10:53",
                "updated_at": "2020-05-08 18:10:53",
                "deleted_at": null,
                "sucursal": {
                  "id": 22,
                  "user_id": 133,
                  "codigo": "24",
                  "nombre": "YY",
                  "telefono": "7772575916",
                  "colonia_id": 34661,
                  "municipio_id": 502,
                  "estado_id": 17,
                  "zona_sucursal_id": 4,
                  "ciudad_cobertura_id": 1,
                  "direccion": "AV.MORELOS SUR",
                  "direccion_numero": "157",
                  "codigo_postal": "62050",
                  "lon": "-99.23195740395204",
                  "lat": "18.90517509983967",
                  "ancla": 0,
                  "checkin": 1,
                  "dias": "LUN, MAR, MIE, JUE, VIE, SAB, DOM",
                  "horario_inicio": "07:00:00",
                  "horario_final": "23:00:00",
                  "24_hrs": 0,
                  "base": 0,
                  "almacen": 1,
                  "comercializadora": 1,
                  "pickup": 0,
                  "domicilio_propios": 1,
                  "domicilio_terceros": 0,
                  "disponible": 0,
                  "created_at": "2017-03-16 17:50:05",
                  "updated_at": "2020-05-08 16:28:10",
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

**Actualización repartidor**
----
  Actualiza la información de repartidores

 **URL**

    /api-v2/sucursales/repartidores/ID

 **Method:**

  `PUT`
    
 **Headers**
 
    Authorization: Bearer access_token
    Accept: application/json
    Content-Type: application/x-www-form-urlencoded
    
**Data Params**
    
    'nombre' => 'required',
    'apellido_paterno' => 'nullable',
    'apellido_materno' => 'nullable',
    'sucursal_id' => 'required|exists:sucursales,id',
    
 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
        	  "repartidor": {
                "id": 1,
                "nombre": "Repartidor",
                "apellido_paterno": "Prueba",
                "apellido_materno": "V2",
                "sucursal_id": "22",
                "created_at": "2020-05-08 18:10:53",
                "updated_at": "2020-05-08 18:10:53",
                "deleted_at": null
              }
        }
        
 **Error Response:**

  * **Code:** 422 Unprocessable Entity <br />
      **Content:** 
      
          {
                  "nombre": [
                    "El campo nombre es obligatorio."
                  ],
                  "sucursal_id": [
                    "El campo sucursal id es obligatorio."
                  ]
          }
          
  * **Code:** 401 Unauthorized <br />
      **Content:** 
      
          {
            "error": "Unauthenticated."
          }

**Eliminar repartidor**
----
  Elimina un repartidor

 **URL**

    /api-v2/sucursales/repartidores/ID

 **Method:**

  `DELETE`
    
 **Headers**
  
     Authorization: Bearer access_token
     Accept: application/json
    
    
 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
            "repartidor": {
                "id": 1,
                "nombre": "Repartidor",
                "apellido_paterno": "Prueba",
                "apellido_materno": "V2",
                "sucursal_id": 22,
                "created_at": "2020-05-08 18:10:53",
                "updated_at": "2020-05-08 18:14:27",
                "deleted_at": "2020-05-08 18:14:27"
            }
        }

 **Error Responses:**

  * **Code:** 401 Unauthorized <br />
    **Content:** 
    
        {
          "error": "Unauthenticated."
        }