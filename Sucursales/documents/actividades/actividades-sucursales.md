
## Listado de sucursales asignadas por zona del usuario
Regresa el listado de las sucursales que pertenecen a la zona donde el capacitador/supervisor ha sido asignado

**URL**

	/api/sucursales/actividades/sucursales

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
            "sucursales": [
                {
                "id": 3,
                "nombre": "Sucursal 3",
                "codigo": "S-03",
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
                "updated_at": "2019-06-28 14:00:06",
                "deleted_at": null
                },
                {
                "id": 4,
                "nombre": "Sucursal 4",
                "codigo": "S-04",
                "direccion": "Sucursal 4",
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
                "updated_at": "2019-06-28 14:00:14",
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

* **Code:** 406 <br />

    **Content:**

		
		{
			"message": "El usuario no cuenta con perfil de Capacitador / Supervisor."
		}


## Listado de actividades pendientes en determinada sucursal
Regresa el listado de actividades (catalogo) de las actividades que no se han realizado en la sucursal en el tiempo previamente establecido
  
**URL**

	/api/sucursales/actividades/sucursal/actividades-pendientes

**Method:**

	`POST`

**Headers**
	
	Authorization: Bearer access_token
	Accept: application/json
	Content-Type: multipart/form-data


**Data Params**
	
	'sucursal_id' => 'required|exist:sucursales,id'

**Success Response:**

* **Code:** 200 <br />
	
	**Content:**

	
        {
            "actividades_pendientes": [
                {
                    "id": 2,
                    "nombre": "actividad 2 CAP",
                    "key": "act-2",
                    "tipo_responsable": "capacitador",
                    "periodo_cantidad": 1,
                    "periodo_frecuencia": "semanas",
                    "tiempo_aproximado": 60,
                    "created_at": "2019-07-09 11:17:59",
                    "updated_at": "2019-07-09 11:17:59",
                    "deleted_at": null,
                    "actividades": [
                        {
                        "id": 2,
                        "tipo_actividad_id": 2,
                        "sucursal_id": 3,
                        "user_id": 12,
                        "inicio_at": "2019-07-08 18:14:17",
                        "termino_at": "2019-07-10 18:14:17",
                        "created_at": "2019-07-05 18:14:17",
                        "updated_at": "2019-07-10 18:14:17",
                        "deleted_at": null
                        }
                    ]
                },
                {
                    "id": 4,
                    "nombre": "actividad 4 CAP",
                    "key": "act-4",
                    "tipo_responsable": "capacitador",
                    "periodo_cantidad": 2,
                    "periodo_frecuencia": "meses",
                    "tiempo_aproximado": 3600,
                    "created_at": "2019-07-09 11:18:27",
                    "updated_at": "2019-07-09 11:18:27",
                    "deleted_at": null,
                    "actividades": []
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
            "message": "The given data was invalid.",
            "errors": {
                "sucursal_id": [
                    "El campo sucursal id es obligatorio."
                ]
            }
        }
        
* **Code:** 406 <br />
	
	**Content:**
	
	
        {
            "message": "El usuario no cuenta con perfil de Capacitador / Supervisor."
        }


                
