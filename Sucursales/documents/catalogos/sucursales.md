## Listado de fondos sucursales
Regresa el listado de sucursales por el perfil del usuario<br>

 **URL**

    /api/catalogos/sucursales/getSucursalesByPerfil

 **Method:**

  `GET`
  
 **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data
     
     
 **Params**
    N/A
         
         

**Success Response:**

**Code:** 200 <br />
  **Content:** 
  
      {
           "sucursales":[
              {
                 "id":91,
                 "nombre":"CS",
                 "codigo":"CS",
                 "direccion":"Ahuatepec 307 A, Lomas de la Selva",
                 "lat":"18.892008",
                 "lon":"-99.231818",
                 "meta_encargadas":1,
                 "meta_auxiliares":1,
                 "meta_cajeras":0,
                 "fondo_venta_mensual":"0",
                 "matutino":true,
                 "vespertino":true,
                 "intermedio":false,
                 "created_at":"2020-11-25 15:53:49",
                 "updated_at":"2021-05-06 12:52:15",
                 "deleted_at":null,
                 "fondo_asignado":"0",
                 "fondo_callcenter":"1000",
                 "tipo_sucursal":"CS",
                 "fecha_calibracion":null,
                 "correo_enviado_calibracion":false
              }
           ]
        }

**Error Response:**

  * **Code:** 401 Unauthorized <br />
    **Content:** 
  
          {
            "error": "Unauthenticated."
          }

## Listado de sucursales v2
Regresa el listado de sucursales<br>

**URL**

    /api/catalogos/sucursales-v2

**Method:**

`GET`

**Headers**

      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data

**Params**
N/A

**Success Response:**

**Code:** 200 <br />
**Content:**

        {
            "sucursales": [
                {
                    "id": 1,
                    "user_id": 152,
                    "codigo": "1",
                    "nombre": "AA",
                    "telefono": "5217772575993",
                    "email_oficial": "comer_aa1@grupofarmapronto.com",
                    "colonia_id": 34733,
                    "municipio_id": 502,
                    "estado_id": 17,
                    "zona_sucursal_id": 3,
                    "ciudad_cobertura_id": 1,
                    "direccion": "AV. VICENTE GUERRERO",
                    "direccion_numero": "107",
                    "codigo_postal": "62230",
                    "lon": "-99.23085095421447",
                    "lat": "18.95742636448077",
                    "ancla": 1,
                    "checkin": 0,
                    "dias": "LUN, MAR, MIE, JUE, VIE, SAB, DOM",
                    "horario_inicio": "07:00:00",
                    "horario_final": "23:00:00",
                    "24_hrs": 0,
                    "base": 1,
                    "almacen": 0,
                    "comercializadora": 1,
                    "pickup": 1,
                    "domicilio_propios": 0,
                    "domicilio_terceros": 0,
                    "disponible": 0,
                    "km_cobertura": 10,
                    "created_at": "2017-03-16 17:50:05",
                    "updated_at": "2021-12-22 15:23:48",
                    "deleted_at": null,
                    "rappi_id": "FPAA1"
                },
                {
                    "id": 2,
                    "user_id": 53,
                    "codigo": "2",
                    "nombre": "BB",
                    "telefono": "5217772575645",
                    "email_oficial": "",
                    "colonia_id": 18491,
                    "municipio_id": 365,
                    "estado_id": 12,
                    "zona_sucursal_id": 1,
                    "ciudad_cobertura_id": 4,
                    "direccion": "AV. INSURGENTES",
                    "direccion_numero": "28",
                    "codigo_postal": "39010",
                    "lon": "-99.5080652",
                    "lat": "17.5628592",
                    "ancla": 0,
                    "checkin": 0,
                    "dias": "LUN, MAR, MIE, JUE, VIE, SAB, DOM",
                    "horario_inicio": "07:00:00",
                    "horario_final": "23:00:00",
                    "24_hrs": 0,
                    "base": 0,
                    "almacen": 0,
                    "comercializadora": 1,
                    "pickup": 0,
                    "domicilio_propios": 0,
                    "domicilio_terceros": 0,
                    "disponible": 0,
                    "km_cobertura": 10,
                    "created_at": "2017-03-16 17:50:05",
                    "updated_at": "2020-11-21 12:11:46",
                    "deleted_at": null,
                    "rappi_id": null
                },
                {
                    "id": 3,
                    "user_id": 54,
                    "codigo": "3",
                    "nombre": "CC",
                    "telefono": "5217772575704",
                    "email_oficial": "",
                    "colonia_id": 18485,
                    "municipio_id": 365,
                    "estado_id": 12,
                    "zona_sucursal_id": 1,
                    "ciudad_cobertura_id": 4,
                    "direccion": "FRANCISCO I. MADERO",
                    "direccion_numero": "11",
                    "codigo_postal": "39000",
                    "lon": "-99.502184",
                    "lat": "17.552922",
                    "ancla": 0,
                    "checkin": 0,
                    "dias": "LUN, MAR, MIE, JUE, VIE, SAB, DOM",
                    "horario_inicio": "07:00:00",
                    "horario_final": "23:00:00",
                    "24_hrs": 0,
                    "base": 0,
                    "almacen": 0,
                    "comercializadora": 1,
                    "pickup": 0,
                    "domicilio_propios": 0,
                    "domicilio_terceros": 0,
                    "disponible": 0,
                    "km_cobertura": 10,
                    "created_at": "2017-03-16 17:50:05",
                    "updated_at": "2020-11-21 12:20:52",
                    "deleted_at": null,
                    "rappi_id": null
                },
                {
                    "id": 4,
                    "user_id": 55,
                    "codigo": "4",
                    "nombre": "D",
                    "telefono": "5217772576379",
                    "email_oficial": "",
                    "colonia_id": 35225,
                    "municipio_id": 828,
                    "estado_id": 17,
                    "zona_sucursal_id": 0,
                    "ciudad_cobertura_id": 0,
                    "direccion": "ALTAMIRANO LOCAL",
                    "direccion_numero": "10",
                    "codigo_postal": "62900",
                    "lon": "-99.177816",
                    "lat": "18.61430176",
                    "ancla": 0,
                    "checkin": 0,
                    "dias": "LUN, MAR, MIE, JUE, VIE, SAB, DOM",
                    "horario_inicio": "07:00:00",
                    "horario_final": "23:00:00",
                    "24_hrs": 0,
                    "base": 0,
                    "almacen": 0,
                    "comercializadora": 1,
                    "pickup": 0,
                    "domicilio_propios": 0,
                    "domicilio_terceros": 0,
                    "disponible": 0,
                    "km_cobertura": 10,
                    "created_at": "2017-03-16 17:50:05",
                    "updated_at": "2020-11-21 13:07:59",
                    "deleted_at": null,
                    "rappi_id": null
                },...
            ]
        }

**Error Response:**

* **Code:** 401 Unauthorized <br />
  **Content:**

        {
          "error": "Unauthenticated."
        }

