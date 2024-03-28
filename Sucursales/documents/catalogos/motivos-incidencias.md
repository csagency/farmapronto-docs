## Listado de motivos incidencias
Regresa el listado de los motivos de incidencias

 **URL**

    /api/catalogos/motivos-incidencias

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
            "motivos": [
                {
                  "id": 1,
                  "nombre": "Llantas",
                  "key": "llantas",
                  "prefix": "LL",
                  "created_at": "2019-10-01 18:40:43",
                  "updated_at": "2019-10-01 18:40:43",
                  "deleted_at": null
                },
                {
                  "id": 2,
                  "nombre": "Mantenimiento de la moto",
                  "key": "mantenimiento",
                  "prefix": "MT",
                  "created_at": "2019-10-01 18:40:43",
                  "updated_at": "2019-10-01 18:40:43",
                  "deleted_at": null
                },
                {
                  "id": 6,
                  "nombre": "Reparación",
                  "key": "reparacion",
                  "prefix": "RE",
                  "created_at": "2019-10-01 18:40:43",
                  "updated_at": "2019-10-01 18:40:43",
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
          
            
                    
## Detalle de motivo incidencia
Regresa el registro de un motivo incidencia

 **URL**

    /api/catalogos/motivos-incidencias/{ID}

 **Method:**

  `GET`
  
 **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data
     
 **URL Params**

      - includes[] = gastos
        Ejemplo URI: `api/catalogos/motivos-incidencias/2?includes[]=gastos`

**Success Response:**

* **Code:** 200 <br />
  **Content:** 
  
      {
           "motivo": {
               "id": 2,
               "nombre": "Mantenimiento de la moto",
               "key": "mantenimiento",
               "prefix": "MT",
               "created_at": "2019-10-01 18:40:43",
               "updated_at": "2019-10-01 18:40:43",
               "deleted_at": null,
               "gastos": []
           }
      }

**Error Response:**

  * **Code:** 401 Unauthorized <br />
    **Content:** 
  
          {
            "error": "Unauthenticated."
          }  

## Listado de motivos incidencias (V2)
Regresa el listado de los motivos de incidencias

 **URL**

    /api/catalogos/motivos-incidencias-v2

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
            "motivos": [
                {
                  "id": 1,
                  "nombre": "Llantas",
                  "key": "llantas",
                  "prefix": "LL",
                  "created_at": "2019-05-21 13:28:24",
                  "updated_at": "2019-08-02 17:05:13"
                },
                {
                  "id": 2,
                  "nombre": "Mantenimiento de la moto",
                  "key": "mantenimiento",
                  "prefix": "MT",
                  "created_at": "2019-05-21 13:28:24",
                  "updated_at": "2019-08-02 17:05:13"
                },
                {
                  "id": 3,
                  "nombre": "Otro",
                  "key": "otro",
                  "prefix": "OT",
                  "created_at": "2019-05-21 13:28:24",
                  "updated_at": "2019-08-02 17:05:13"
                },
                {
                  "id": 4,
                  "nombre": "Por gasolina",
                  "key": "gasolina",
                  "prefix": "GA",
                  "created_at": "2019-05-21 13:28:24",
                  "updated_at": "2019-08-02 17:05:13"
                },
                {
                  "id": 5,
                  "nombre": "Gastos generales",
                  "key": "generales",
                  "prefix": "GG",
                  "created_at": "2019-05-21 13:28:24",
                  "updated_at": "2019-08-02 17:05:13"
                },
                {
                  "id": 6,
                  "nombre": "Reparación",
                  "key": "reparacion",
                  "prefix": "RE",
                  "created_at": "2019-05-21 13:28:24",
                  "updated_at": "2019-08-02 17:05:13"
                }
            ]
      }

**Error Response:**

  * **Code:** 406 Not Acceptable <br />
  **Content:** 
  
        {
          "error": "Ocurrió un error al conectar con el servidor"
        } 
          
