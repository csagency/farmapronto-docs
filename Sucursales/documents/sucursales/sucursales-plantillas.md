      
## Listado de plantilla
Regresa el listado de la plantilla registrada por la sucursal

 **URL**

    /api/sucursales/sucursales-plantillas

 **Method:**

  `GET`
  
 **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data
      
      
 **Data Params**
    
     'sucursal_id' => 'required|exists:sucursales,id',
     'turno' => 'nullable|in:matutino,vespertino,intermedio',
     'tipo' => 'nullable|in:auxiliar,encargada,cajera',
     
 **URL Params**

      - includes[] = sucursal, user
        Ejemplo URI: `api/sucursales/sucursales-plantillas?includes[]=sucursal`

      - turno = matutino
        Devuelve todos los registros del turno matutino
        Ejemplo URI: `api/sucursales/sucursales-plantillas?turno=matutino`
        
      - tipo = auxiliar
        Devuelve todo el personal de tipo auxiliar
        Ejemplo URI: `api/sucursales/sucursales-plantillas?tipo=auxiliar`

**Success Response:**

* **Code:** 200 <br />
  **Content:** 
  
      {
      	"plantillas": [
            {
              "id": 5,
              "sucursal_id": 4,
              "user_id": null,
              "tipo": "cajera",
              "turno": "matutino",
              "nombre": "fdgsdf",
              "apellido_paterno": "sgdfgsdf",
              "apellido_materno": null,
              "telefono": "7771234567",
              "email": "admin@farmapronto-sucursales.com",
              "fecha_contratacion": "2019-06-19",
              "fecha_vacaciones": null,
              "created_at": "2019-06-27 17:38:03",
              "updated_at": "2019-06-27 17:38:57",
              "deleted_at": null,
              "sucursal": {
                "id": 4,
                "nombre": "gsdg",
                "codigo": "gdsfg",
                "direccion": "gfsdg",
                "lat": null,
                "lon": null,
                "meta_encargadas": 3,
                "meta_auxiliares": 3,
                "meta_cajeras": 3,
                "fondo_venta_mensual": null,
                "fondo_callcenter": 3,
                "matutino": 1,
                "vespertino": 1,
                "intermedio": 0,
                "fondo_asignado": 3333333,
                "created_at": "2019-06-25 18:07:37",
                "updated_at": "2019-06-25 18:07:37",
                "deleted_at": null
              }
            },
            {
              "id": 6,
              "sucursal_id": 4,
              "user_id": 13,
              "tipo": "encargada",
              "turno": "matutino",
              "nombre": "Encargada",
              "apellido_paterno": "Prueba",
              "apellido_materno": null,
              "telefono": "5555555555",
              "email": "encargada@farmapronto-sucursales.com",
              "fecha_contratacion": "2019-06-19",
              "fecha_vacaciones": null,
              "created_at": "2019-06-27 17:59:19",
              "updated_at": "2019-06-27 17:59:19",
              "deleted_at": null,
              "sucursal": {
                "id": 4,
                "nombre": "gsdg",
                "codigo": "gdsfg",
                "direccion": "gfsdg",
                "lat": null,
                "lon": null,
                "meta_encargadas": 3,
                "meta_auxiliares": 3,
                "meta_cajeras": 3,
                "fondo_venta_mensual": null,
                "fondo_callcenter": 3,
                "matutino": 1,
                "vespertino": 1,
                "intermedio": 0,
                "fondo_asignado": 3333333,
                "created_at": "2019-06-25 18:07:37",
                "updated_at": "2019-06-25 18:07:37",
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
          
          
  * **Code:** 422 Unprocessable Entity <br />
    **Content:** 
    
        {
            "sucursal_id": [
              "El campo sucursal id es obligatorio."
            ]
            "turno": [
              "El campo turno es inválido."
            ]
            "tipo": [
              "El campo tipo es inválido."
            ]
        }
        