## Listado de todos los vehículos
Regresa el listado de todos los vehículos

**URL**
    
    /api/vehiculos
    
**Method:**

 `GET`

**Headers**

    Authorization: Bearer access_token
    Accept: application/json
    Content-Type: multipart/form-data
    
      
 **URL Params**

      - includes[] = user, checks, checkIns, checkOuts
        Ejemplo URI: `api/vehiculos?includes[]=user`
 
**Success Response:**

* **Code:** 200 <br />
    **Content:**
        
        {
           "vehiculos": [
               {
                 "id": 2,
                 "user_id": 23,
                 "placas": "ABCDE123",
                 "marca": "Yamaha",
                 "modelo": "YBR125C Express",
                 "color": "Negro",
                 "num_serie": "GFDSG3465336",
                 "num_poliza": "34646436",
                 "ultimo_servicio": null,
                 "created_at": "2019-08-08 19:00:47",
                 "updated_at": "2019-08-23 18:25:09",
                 "deleted_at": null,
                 "user": {
                   "id": 23,
                   "perfil_id": null,
                   "nombre": "Supervisor",
                   "apellido_paterno": "Matriz",
                   "apellido_materno": null,
                   "telefono": null,
                   "player_id": null,
                   "email": "matriz@farmapronto-sucursales.com",
                   "email_verified_at": null,
                   "created_at": "2019-08-23 18:12:00",
                   "updated_at": "2019-08-23 18:12:00",
                   "deleted_at": null
                 }
               },
               {
                 "id": 3,
                 "user_id": 23,
                 "placas": "PRUEBA111",
                 "marca": "Yamaha",
                 "modelo": "YBR125C Express",
                 "color": "Negro",
                 "num_serie": "1234567890",
                 "num_poliza": "0987654321",
                 "ultimo_servicio": null,
                 "created_at": "2019-08-23 18:12:50",
                 "updated_at": "2019-08-23 18:12:50",
                 "deleted_at": null,
                 "user": {
                   "id": 23,
                   "perfil_id": null,
                   "nombre": "Supervisor",
                   "apellido_paterno": "Matriz",
                   "apellido_materno": null,
                   "telefono": null,
                   "player_id": null,
                   "email": "matriz@farmapronto-sucursales.com",
                   "email_verified_at": null,
                   "created_at": "2019-08-23 18:12:00",
                   "updated_at": "2019-08-23 18:12:00",
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
        
        
        
## Listado de los vehículos de matriz
Regresa el listado de todos los vehículos de matriz

**URL**
    
    /api/vehiculos/matriz
    
**Method:**

 `GET`

**Headers**

    Authorization: Bearer access_token
    Accept: application/json
    Content-Type: multipart/form-data
    
      
 **URL Params**

      - includes[] = user, checks, checkIns, checkOuts
        Ejemplo URI: `api/vehiculos?includes[]=user`
 
**Success Response:**

* **Code:** 200 <br />
    **Content:**
        
        {
           "vehiculos": [
               {
                 "id": 2,
                 "user_id": 23,
                 "placas": "ABCDE123",
                 "marca": "Yamaha",
                 "modelo": "YBR125C Express",
                 "color": "Negro",
                 "num_serie": "GFDSG3465336",
                 "num_poliza": "34646436",
                 "ultimo_servicio": null,
                 "created_at": "2019-08-08 19:00:47",
                 "updated_at": "2019-08-23 18:25:09",
                 "deleted_at": null,
                 "user": {
                   "id": 23,
                   "perfil_id": null,
                   "nombre": "Supervisor",
                   "apellido_paterno": "Matriz",
                   "apellido_materno": null,
                   "telefono": null,
                   "player_id": null,
                   "email": "matriz@farmapronto-sucursales.com",
                   "email_verified_at": null,
                   "created_at": "2019-08-23 18:12:00",
                   "updated_at": "2019-08-23 18:12:00",
                   "deleted_at": null
                 }
               },
               {
                 "id": 3,
                 "user_id": 23,
                 "placas": "PRUEBA111",
                 "marca": "Yamaha",
                 "modelo": "YBR125C Express",
                 "color": "Negro",
                 "num_serie": "1234567890",
                 "num_poliza": "0987654321",
                 "ultimo_servicio": null,
                 "created_at": "2019-08-23 18:12:50",
                 "updated_at": "2019-08-23 18:12:50",
                 "deleted_at": null,
                 "user": {
                   "id": 23,
                   "perfil_id": null,
                   "nombre": "Supervisor",
                   "apellido_paterno": "Matriz",
                   "apellido_materno": null,
                   "telefono": null,
                   "player_id": null,
                   "email": "matriz@farmapronto-sucursales.com",
                   "email_verified_at": null,
                   "created_at": "2019-08-23 18:12:00",
                   "updated_at": "2019-08-23 18:12:00",
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
        
