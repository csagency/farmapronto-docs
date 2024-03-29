**Repartidores de la sucursal**
----
  Regresa la información a detalle de un pedido y sus relaciones

 **URL**

  /api/sucursales/me/repartidores

 **Method:**

  `GET`

  **Headers**

      Authorization: Bearer access_token
      Accept: application/json

  **URL Params**

  - includes[]=user, etc...   <br><br>


 **Success Response:**

  * **Code:** 200 <br />
    **Content:**


           {
            "agentes": [
                {
                    "id": 45,
                    "user_id": 326,
                    "numero_control": "3560",
                    "estatus": 1,
                    "puesto": null,
                    "created_at": "2018-04-10 12:59:42",
                    "updated_at": "2018-06-12 16:53:27",
                    "deleted_at": null,
                    "lat": "18.9052061",
                    "lon": "-99.2318339",
                    "imagen": null,
                    "imagen_path": null,
                    "vehiculo_id": 2,
                    "supervisor": 0,
                    "user": {
                        "id": 326,
                        "name": "CARLOS DAVID",
                        "last_name": "SOLIS",
                        "second_last_name": "GUADARRAMA",
                        "telephone": "7775637779",
                        "email": "repartidor23@grupofarmapronto.com",
                        "player_id": "31e04b46-cdc3-4f59-85bb-f8611b3a31e8",
                        "activo": 0,
                        "slack_webhook_url": null,
                        "created_at": "2018-04-10 12:59:42",
                        "updated_at": "2018-06-03 13:04:01",
                        "deleted_at": null,
                        "last_login": null
                    }
                },
                {
                    "id": 46,
                    "user_id": 327,
                    "numero_control": "3422",
                    "estatus": 1,
                    "puesto": null,
                    "created_at": "2018-04-10 13:02:26",
                    "updated_at": "2018-06-12 17:19:44",
                    "deleted_at": null,
                    "lat": "18.9068398",
                    "lon": "-99.2322437",
                    "imagen": null,
                    "imagen_path": null,
                    "vehiculo_id": 2,
                    "supervisor": 0,
                    "user": {
                        "id": 327,
                        "name": "CARLOS SALVADOR",
                        "last_name": "CASTAÑEDA",
                        "second_last_name": "SANCHEZ",
                        "telephone": "7771043708",
                        "email": "repartidor22@grupofarmapronto.com",
                        "player_id": "bb2d8e75-8430-4868-88b2-96c840d65a08",
                        "activo": 0,
                        "slack_webhook_url": null,
                        "created_at": "2018-04-10 13:02:26",
                        "updated_at": "2018-06-12 15:01:36",
                        "deleted_at": null,
                        "last_login": null
                    }
                },
                {
                    "id": 48,
                    "user_id": 329,
                    "numero_control": "3447",
                    "estatus": 1,
                    "puesto": null,
                    "created_at": "2018-04-10 13:21:52",
                    "updated_at": "2018-06-10 17:48:26",
                    "deleted_at": null,
                    "lat": "18.9052045",
                    "lon": "-99.2318063",
                    "imagen": null,
                    "imagen_path": null,
                    "vehiculo_id": 2,
                    "supervisor": 0,
                    "user": {
                        "id": 329,
                        "name": "EDGAR ABIMAEL",
                        "last_name": "CARRIZOSA",
                        "second_last_name": "AGUILAR",
                        "telephone": "7775084523",
                        "email": "repartidor19@grupofarmapronto.com",
                        "player_id": "bb2d8e75-8430-4868-88b2-96c840d65a08",
                        "activo": 0,
                        "slack_webhook_url": null,
                        "created_at": "2018-04-10 13:21:52",
                        "updated_at": "2018-06-10 12:02:08",
                        "deleted_at": null,
                        "last_login": null
                    }
                },
                {
                    "id": 64,
                    "user_id": 716,
                    "numero_control": "3901",
                    "estatus": 1,
                    "puesto": null,
                    "created_at": "2018-04-20 17:10:02",
                    "updated_at": "2018-06-11 22:54:43",
                    "deleted_at": null,
                    "lat": "18.9052104",
                    "lon": "-99.2318295",
                    "imagen": null,
                    "imagen_path": null,
                    "vehiculo_id": 2,
                    "supervisor": 0,
                    "user": {
                        "id": 716,
                        "name": "Ivan Sebastian",
                        "last_name": "Tellez",
                        "second_last_name": "Dominguez",
                        "telephone": "5522169166",
                        "email": "repartidor21@grupofarmapronto.com",
                        "player_id": "efae4b23-643f-4608-ad99-e4eb0b025970",
                        "activo": 0,
                        "slack_webhook_url": null,
                        "created_at": "2018-04-20 17:10:02",
                        "updated_at": "2018-06-05 11:27:09",
                        "deleted_at": null,
                        "last_login": null
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

  * **Code:** 404 Not Found <br />
    **Content:**

        {
          "error": "Model not found."
        }



**Repartidor de la sucursal detalle**
----
  Regresa el detalle del repartidor

 **URL**

  /api/sucursales/me/repartidores/{id}

 **Method:**

  `GET`

  **Headers**

      Authorization: Bearer access_token
      Accept: application/json

  **URL Params**

  - includes[]=user, etc...   <br><br>


 **Success Response:**

  * **Code:** 200 <br />
    **Content:**


           {
           	"agente": {
           		"id": 44,
           		"user_id": 324,
           		"numero_control": "2471",
           		"estatus": 1,
           		"puesto": null,
           		"created_at": "2018-04-10 12:55:57",
           		"updated_at": "2018-06-13 12:29:23",
           		"deleted_at": null,
           		"lat": "18.9052033",
           		"lon": "-99.2318248",
           		"imagen": null,
           		"imagen_path": null,
           		"vehiculo_id": 2,
           		"supervisor": 0
           	}
           }


 **Error Response:**

  * **Code:** 401 Unauthorized <br />
    **Content:**

        {
          "error": "Unauthenticated."
        }

  * **Code:** 404 Not Found <br />
    **Content:**

        {
          "error": "Model not found."
        }
        

**Checkouts asignados a la sucursal**
----
  Regresa la información de los checkouts del día asignados a la sucursal

 **URL**

    /api/sucursales/me/repartidores/checkouts

 **Method:**

  `GET`

  **Headers**

      Authorization: Bearer access_token
      Accept: application/json

  **URL Params**

    - includes[]=agente.user, vehiculo.sucursal, mantenimientoAlertas, checkIn, estatus, log


 **Success Response:**

  * **Code:** 200 <br />
    **Content:**


          {
            "checkouts": []
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
          "error": "El usuario no cuenta con perfil de sucursal."
        }



**Aprobar/rechaza checkout**
----
  Regresa el detalle del checkout aprobado/rechazado

 **URL**

    /api/sucursales/me/repartidores/checkouts/{id}

 **Method:**

  `POST`

  **Headers**

      Authorization: Bearer access_token
      Accept: application/json

   
 **Data Params**
     
        'estatus' => 'required|in:aprobado,rechazado',
        'motivos_rechazo' => 'required_if:estatus,rechazado|array',
        'comentarios_rechazo' => 'required_if:estatus,rechazado'

 **Type Params**

  - motivos_rechazo[]=km, gasolina, celular, licencia, tarjeta_circulacion, poliza_seguro, casco, impermeable, frontal_moto, derecho_moto, izquierdo_moto, trasera_moto, llaves_moto, estado_moto, estado_llantas, agente_sonriendo

 **Success Response:**

  * **Code:** 200 <br />
    **Content:**


         {
           	"checkout": {
                "id": 50131,
                "agente_id": 288,
                "vehiculo_id": 73,
                "checkin_id": 50130,
                "llaves_moto_foto": "uploads\/images\/mantenimiento\/x2wlgM2fhRnLOVfEaPvrJ0UNvQigeyN5CvwQRC77.jpeg",
                "celular_foto": null,
                "turno": "Matutino",
                "tipo": "checkout",
                "estado_moto": 1,
                "moto_inconveniente": "uploads\/images\/mantenimiento\/eLbZpiogv3gTXP5xomFBhExpyiYA5n9JjfE6nPCX.jpeg",
                "estado_llantas": 1,
                "llanta_ponchada": null,
                "encendido_moto": 1,
                "kilometraje": 20712,
                "kilometraje_evidencia": "uploads\/images\/mantenimiento\/IPRyIrkbWxvVDaFqjuudAcjmZ5yuZixeXETX1aEl.jpeg",
                "nivel_gasolina": "uploads\/images\/mantenimiento\/MMrxiI8ems3qoDRZtLYtTOEXV1LSHHX0FVsrf1DU.jpeg",
                "nivel_aceite": null,
                "licencia": null,
                "licencia_dd": null,
                "licencia_mm": null,
                "licencia_aa": null,
                "lateral_izquierda_moto": "uploads\/images\/mantenimiento\/VyI9ZfPdcfa42gAmGY1FIbQ7IiMUHSDDGfeqQodp.jpeg",
                "lateral_derecha_moto": "uploads\/images\/mantenimiento\/bpt17rGFWAN8BONvktPf1FTZ1SLvRZ1UDidq2iOh.jpeg",
                "frontal_moto": "uploads\/images\/mantenimiento\/zquO43kBcKJA03h8stznURL3m5Lt4aDbL7dF62oo.jpeg",
                "trasera_moto": "uploads\/images\/mantenimiento\/Zj7nKrIeAWgkpX0X77HnJzVPEC10wq58NLbLM313.jpeg",
                "tarjeta_circulacion": "uploads\/images\/mantenimiento\/0gd56WdSvlJD14lsc8mhSx4E87Mo6UFzyT4Hpyrw.jpeg",
                "poliza_seguro": null,
                "casco": null,
                "impermeable": null,
                "agente_sonriendo": null,
                "observaciones": null,
                "aprobado": true,
                "created_at": "2020-07-16 08:36:10",
                "updated_at": "2020-08-04 09:48:27",
                "deleted_at": null,
                "agente": {
                  "id": 288,
                  "user_id": 23715,
                  "numero_control": "5330",
                  "estatus": 1,
                  "puesto": null,
                  "created_at": "2020-03-23 12:09:12",
                  "updated_at": "2020-07-16 09:38:06",
                  "deleted_at": null,
                  "lat": "18.9301095",
                  "lon": "-99.210378",
                  "imagen": null,
                  "imagen_path": null,
                  "vehiculo_id": 31,
                  "sucursal_base_id": 62,
                  "supervisor": 0,
                  "cant_errores_actuales": 3,
                  "user": {
                    "id": 23715,
                    "name": "CARLOS LEVI ",
                    "last_name": "SILVA ",
                    "second_last_name": "LEDESMA",
                    "telephone": "7775954109",
                    "clave": null,
                    "email": "repartidor5330@grupofarmapronto.com",
                    "player_id": "50fe1adc-ad45-41b7-b593-8bede724c11b",
                    "tipo_usuario": null,
                    "activo": 1,
                    "baja": 0,
                    "fb_id": null,
                    "webhook_url": null,
                    "created_at": "2020-03-23 12:09:12",
                    "updated_at": "2020-07-16 08:12:25",
                    "deleted_at": null,
                    "last_login": null,
                    "nombre_completo": "CARLOS LEVI  SILVA "
                  }
                }
            }
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
          "error": "El usuario no cuenta con perfil de sucursal."
        }
        
  * **Code:** 422 Unprocessable Entity <br />
    **Content:** 
    
        {
            "estatus": [
              "El campo estatus es obligatorio."
            ]
            "motivos_rechazo": [
              "El campo motivos rechazo es obligatorio cuando estatus es rechazado."
            ],
            "comentarios_rechazo": [
              "El campo comentarios rechazo es obligatorio cuando estatus es rechazado."
            ]
        }
