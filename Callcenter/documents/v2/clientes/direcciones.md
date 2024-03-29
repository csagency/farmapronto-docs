      
## Listado de direcciones
Regresa el listado de todas las direcciones del cliente

 **URL**

    /api-v2/clientes/direcciones/

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
        "direcciones": [
            {
              "id": 89165,
              "user_id": 23516,
              "estado_id": 17,
              "municipio_id": 502,
              "colonia_id": null,
              "colonia_str": "LOMAS DE LA SELVA",
              "calle": "PROLONGACION AHUATEPEC",
              "numero_interior": null,
              "numero_exterior": "307",
              "codigo_postal": "62270",
              "referencia": "DIRECCIÓN PRUEBAS",
              "tipo": "OFICINA",
              "lon": "-99.2324802",
              "lat": "18.9361581",
              "created_at": "2020-04-21 15:42:07",
              "updated_at": "2020-04-21 15:42:07",
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
       
       
**Registro de dirección**
----
  Regresa la información del registro en formato json

 **URL**

    /api-v2/clientes/direcciones/

 **Method:**

  `POST`
 
 **Data Params**
    
    'estado_id' => 'required|exists:catalogo_estados,id',
    'municipio_id' => 'required|exists:catalogo_municipios,id',
    'colonia_id' => 'exists:catalogo_colonias,id',
    'colonia_str ' => 'nullable',
    'calle' => 'required',
    'numero_interior' => 'nullable',
    'numero_exterior' => 'nullable',
    'lat' => 'required',
    'lon' => 'required',
    'codigo_postal' => 'required',
    'tipo' => 'required',
    'referencia' => 'nullable'


 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
          "direccion": {
              "estado_id": "17",
              "municipio_id": "502",
              "colonia_str": "LOMAS DE LA SELVA",
              "calle": "PROLONGACION AHUATEPEC",
              "lat": "18.9361581",
              "lon": "-99.2324802",
              "codigo_postal": "62270",
              "tipo": "OFICINA",
              "referencia": "DIRECCIÓN PRUEBAS",
              "numero_exterior": "307",
              "user_id": 23516,
              "updated_at": "2020-04-21 15:42:07",
              "created_at": "2020-04-21 15:42:07",
              "id": 89165
          }
        }
 
 **Error Response:**

  * **Code:** 422 Unprocessable Entity <br />
    **Content:** 
    
        {
             "estado_id": [
                "El campo estado es obligatorio."
              ],
              "municipio_id": [
                "El campo municipio es obligatorio."
              ],
              "calle": [
                "El campo calle es obligatorio."
              ],
              "lat": [
                "El campo lat es obligatorio."
              ],
              "lon": [
                "El campo lon es obligatorio."
              ],
              "codigo_postal": [
                "El campo código postal es obligatorio."
              ],
              "tipo": [
                "El campo tipo es obligatorio."
              ]
        }
        
  * **Code:** 401 Unauthorized <br />
      **Content:** 
      
          {
            "error": "Unauthenticated."
          }
 
**Datos de la dirección**
----
  Regresa la información de una dirección en específica del cliente y sus relaciones ejemplo: estado, municipio y colonia

 **URL**

    /api-v2/clientes/direcciones/ID

 **Method:**

  `GET`
  
  **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data
      
  **URL Params**

  - includes[]=estado, municipio, colonia  <br><br>
  Ejemplo URI: `api-v2/clientes/direcciones/1?includes[]=estado&includes[]=municipio&includes[]=colonia&includes[]=cliente`
  

 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
          "direccion": {
              "id": 89165,
              "user_id": 23516,
              "estado_id": 17,
              "municipio_id": 502,
              "colonia_id": null,
              "colonia_str": "LOMAS DE LA SELVA",
              "calle": "PROLONGACION AHUATEPEC",
              "numero_interior": null,
              "numero_exterior": "307",
              "codigo_postal": "62270",
              "referencia": "DIRECCIÓN PRUEBAS",
              "tipo": "OFICINA",
              "lon": "-99.2324802",
              "lat": "18.9361581",
              "created_at": "2020-04-21 15:42:07",
              "updated_at": "2020-04-21 15:42:07",
              "deleted_at": null,
              "estado": {
                "id": 17,
                "nombre": "MORELOS",
                "created_at": "2017-03-16 17:47:54",
                "updated_at": "2017-03-16 17:47:54"
              },
              "municipio": {
                "id": 502,
                "estado_id": 17,
                "nombre": "CUERNAVACA",
                "created_at": "2017-03-16 17:47:55",
                "updated_at": "2017-03-16 17:47:55"
              },
              "colonia": null,
              "cliente": {
                "id": 23516,
                "name": "Abril",
                "last_name": "Prueba",
                "second_last_name": "V2",
                "telephone": "527772273622",
                "clave": "ABPRELSY",
                "email": "jabrilmtz17@gmail.com",
                "player_id": null,
                "tipo_usuario": null,
                "activo": 1,
                "baja": 0,
                "fb_id": null,
                "webhook_url": null,
                "created_at": "2020-04-20 22:22:55",
                "updated_at": "2020-04-21 12:35:41",
                "deleted_at": null,
                "last_login": null
              }
          }
        }
 
 **Error Response:**

  * **Code:** 401 Unauthorized <br />
    **Content:** 
    
        {
          "error": "Unauthenticated."
        }



**Actualización de dirección**
----
  Actualiza la información de una dirección en específica del cliente

 **URL**

    /api-v2/clientes/direcciones/ID

 **Method:**

  `PUT`
    
 **Headers**
 
    Authorization: Bearer access_token
    Accept: application/json
    Content-Type: multipart/form-data
    
**Data Params**

    'estado_id' => 'required|exists:catalogo_estados,id',
    'municipio_id' => 'required|exists:catalogo_municipios,id',
    'colonia_id' => 'exists:catalogo_colonias,id',
    'colonia_str ' => 'nullable',
    'calle' => 'required',
    'numero_interior' => 'nullable',
    'numero_exterior' => 'nullable',
    'lat' => 'required',
    'lon' => 'required',
    'codigo_postal' => 'required',
    'tipo' => 'required',
    'referencia' => 'nullable'
    
 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        {
          "direccion": {
              "id": 89165,
              "user_id": 23516,
              "estado_id": "17",
              "municipio_id": "502",
              "colonia_id": null,
              "colonia_str": "LOMAS DE LA SELVA",
              "calle": "PROLONGACION AHUATEPEC",
              "numero_interior": null,
              "numero_exterior": "307",
              "codigo_postal": "62270",
              "referencia": "DIRECCIÓN PRUEBAS",
              "tipo": "OFICINA",
              "lon": "-99.2324802",
              "lat": "18.9361581",
              "created_at": "2020-04-21 15:42:07",
              "updated_at": "2020-04-21 15:42:07",
              "deleted_at": null
          }
        }

 **Error Response:**

  * **Code:** 422 Unprocessable Entity <br />
      **Content:** 
      
          {
               "estado_id": [
                  "El campo estado es obligatorio."
                ],
                "municipio_id": [
                  "El campo municipio es obligatorio."
                ],
                "calle": [
                  "El campo calle es obligatorio."
                ],
                "lat": [
                  "El campo lat es obligatorio."
                ],
                "lon": [
                  "El campo lon es obligatorio."
                ],
                "codigo_postal": [
                  "El campo código postal es obligatorio."
                ],
                "tipo": [
                  "El campo tipo es obligatorio."
                ]
          }
          
  * **Code:** 401 Unauthorized <br />
      **Content:** 
      
          {
            "error": "Unauthenticated."
          }


**Eliminar dirección**
----
  Elimina una dirección en específica del cliente

 **URL**

    /api-v2/clientes/direcciones/ID

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
        	"direccion": null
        }

 **Error Responses:**

  * **Code:** 401 Unauthorized <br />
    **Content:** 
    
        {
          "error": "Unauthenticated."
        }
        
        
**Sucursales cercanas a dirección**
----
  Lista las direcciones cercanas a la dirección selecionada, ordenadas por distancia (5km)

 **URL**

    /api-v2/clientes/direcciones/ID/sucursales

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
            "min_envio_gratis": 200,
        	"sucursales": {
                "17": {
                  "id": 84,
                  "user_id": 2429,
                  "codigo": "cs-2",
                  "nombre": "Sucursal CS NO ELIMINAR",
                  "telefono": "7777771234",
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
                  "ancla": 1,
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
                  "created_at": "2018-11-30 13:45:25",
                  "updated_at": "2020-03-18 12:52:14",
                  "deleted_at": null,
                  "id_user": 2429,
                  "activo": 1,
                  "distancia": 0.4875631296056215,
                  "colonia": {
                    "id": 34641,
                    "municipio_id": 502,
                    "codigo_postal": "62000",
                    "nombre": "CUERNAVACA CENTRO",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  }
                },
                "21": {
                  "id": 95,
                  "user_id": 152,
                  "codigo": "111",
                  "nombre": "Matriz",
                  "telefono": "7773622560",
                  "colonia_id": 34733,
                  "municipio_id": 502,
                  "estado_id": 17,
                  "zona_sucursal_id": 3,
                  "ciudad_cobertura_id": null,
                  "direccion": "Vicente Guerrero",
                  "direccion_numero": "107",
                  "codigo_postal": "62230",
                  "lon": "-99.2355306",
                  "lat": "18.9519575",
                  "ancla": 0,
                  "checkin": 1,
                  "dias": "LUN, MAR, MIE, JUE, VIE, SAB, DOM",
                  "horario_inicio": "09:00:00",
                  "horario_final": "18:00:00",
                  "24_hrs": 0,
                  "base": 0,
                  "almacen": 0,
                  "comercializadora": 1,
                  "pickup": 0,
                  "domicilio_propios": 1,
                  "domicilio_terceros": 0,
                  "created_at": "2019-07-02 17:38:32",
                  "updated_at": "2019-12-20 18:11:49",
                  "deleted_at": null,
                  "id_user": 152,
                  "activo": 1,
                  "distancia": 1.7878659231336145,
                  "colonia": {
                    "id": 34733,
                    "municipio_id": 502,
                    "codigo_postal": "62230",
                    "nombre": "MARAVILLAS",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  }
                },
                "6": {
                  "id": 23,
                  "user_id": 73,
                  "codigo": "25",
                  "nombre": "ZZ",
                  "telefono": "7772575981",
                  "colonia_id": 34739,
                  "municipio_id": 502,
                  "estado_id": 17,
                  "zona_sucursal_id": 3,
                  "ciudad_cobertura_id": null,
                  "direccion": "NUEVA INGLATERRA",
                  "direccion_numero": "500",
                  "codigo_postal": "62240",
                  "lon": "-99.227994",
                  "lat": "18.951769",
                  "ancla": 0,
                  "checkin": 0,
                  "dias": "LUN, MAR, MIE, JUE, VIE, SAB, DOM",
                  "horario_inicio": "07:00:00",
                  "horario_final": "22:58:00",
                  "24_hrs": 0,
                  "base": 0,
                  "almacen": 1,
                  "comercializadora": 1,
                  "pickup": 0,
                  "domicilio_propios": 1,
                  "domicilio_terceros": 0,
                  "created_at": "2017-03-16 17:50:05",
                  "updated_at": "2019-10-22 15:29:47",
                  "deleted_at": null,
                  "id_user": 73,
                  "activo": 1,
                  "distancia": 1.8008485515410952,
                  "colonia": {
                    "id": 34739,
                    "municipio_id": 502,
                    "codigo_postal": "62240",
                    "nombre": "LOMAS DE CORTES",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  }
                },
                "0": {
                  "id": 1,
                  "user_id": 5396,
                  "codigo": "1",
                  "nombre": "AA",
                  "telefono": "7772575993",
                  "colonia_id": 34727,
                  "municipio_id": 502,
                  "estado_id": 17,
                  "zona_sucursal_id": 3,
                  "ciudad_cobertura_id": null,
                  "direccion": "AV. VICENTE GUERRERO",
                  "direccion_numero": "107",
                  "codigo_postal": "62230",
                  "lon": "-99.23085095421447",
                  "lat": "18.95742636448077",
                  "ancla": 0,
                  "checkin": 0,
                  "dias": "LUN, MAR, MIE, JUE, VIE, SAB, DOM",
                  "horario_inicio": "07:00:00",
                  "horario_final": "22:59:00",
                  "24_hrs": 0,
                  "base": 0,
                  "almacen": 0,
                  "comercializadora": 1,
                  "pickup": 0,
                  "domicilio_propios": 1,
                  "domicilio_terceros": 0,
                  "created_at": "2017-03-16 17:50:05",
                  "updated_at": "2019-10-22 11:25:11",
                  "deleted_at": null,
                  "id_user": 5396,
                  "activo": 1,
                  "distancia": 2.373778274251095,
                  "colonia": {
                    "id": 34727,
                    "municipio_id": 502,
                    "codigo_postal": "62220",
                    "nombre": "OCOTEPEC",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  }
                },
                "12": {
                  "id": 62,
                  "user_id": 111,
                  "codigo": "86",
                  "nombre": "Q",
                  "telefono": "7772575913",
                  "colonia_id": 34754,
                  "municipio_id": 502,
                  "estado_id": 17,
                  "zona_sucursal_id": 5,
                  "ciudad_cobertura_id": null,
                  "direccion": "LEÑEROS",
                  "direccion_numero": "68",
                  "codigo_postal": "62290",
                  "lon": "-99.21034696802599",
                  "lat": "18.930405497133883",
                  "ancla": 1,
                  "checkin": 1,
                  "dias": "LUN, MAR, MIE, JUE, VIE, SAB, DOM",
                  "horario_inicio": "07:00:00",
                  "horario_final": "22:00:00",
                  "24_hrs": 0,
                  "base": 1,
                  "almacen": 1,
                  "comercializadora": 1,
                  "pickup": 0,
                  "domicilio_propios": 1,
                  "domicilio_terceros": 0,
                  "created_at": "2017-07-05 13:45:09",
                  "updated_at": "2020-02-29 13:24:02",
                  "deleted_at": null,
                  "id_user": 111,
                  "activo": 1,
                  "distancia": 2.416936324885577,
                  "colonia": {
                    "id": 34754,
                    "municipio_id": 502,
                    "codigo_postal": "62290",
                    "nombre": "VISTA HERMOSA",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  }
                },
                "5": {
                  "id": 22,
                  "user_id": 133,
                  "codigo": "24",
                  "nombre": "YY",
                  "telefono": "7772575916",
                  "colonia_id": 34661,
                  "municipio_id": 502,
                  "estado_id": 17,
                  "zona_sucursal_id": 4,
                  "ciudad_cobertura_id": null,
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
                  "created_at": "2017-03-16 17:50:05",
                  "updated_at": "2019-12-21 12:33:40",
                  "deleted_at": null,
                  "id_user": 133,
                  "activo": 1,
                  "distancia": 3.4494506075869382,
                  "colonia": {
                    "id": 34661,
                    "municipio_id": 502,
                    "codigo_postal": "62050",
                    "nombre": "LAS PALMAS SUR",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  }
                },
                "22": {
                  "id": 96,
                  "user_id": 152,
                  "codigo": "200",
                  "nombre": "ENLACE",
                  "telefono": "7771010030",
                  "colonia_id": 34755,
                  "municipio_id": 502,
                  "estado_id": 17,
                  "zona_sucursal_id": 3,
                  "ciudad_cobertura_id": null,
                  "direccion": "AV. GASODUCTO",
                  "direccion_numero": "S\/N",
                  "codigo_postal": "62300",
                  "lon": "-99.2097",
                  "lat": "18.9598",
                  "ancla": 0,
                  "checkin": 1,
                  "dias": "LUN, MAR, MIE, JUE, VIE, SAB, DOM",
                  "horario_inicio": "06:00:00",
                  "horario_final": "17:00:00",
                  "24_hrs": 0,
                  "base": 1,
                  "almacen": 0,
                  "comercializadora": 1,
                  "pickup": 0,
                  "domicilio_propios": 1,
                  "domicilio_terceros": 0,
                  "created_at": "2019-09-03 10:14:53",
                  "updated_at": "2019-12-20 18:11:49",
                  "deleted_at": null,
                  "id_user": 152,
                  "activo": 1,
                  "distancia": 3.560765418195424,
                  "colonia": {
                    "id": 34755,
                    "municipio_id": 502,
                    "codigo_postal": "62300",
                    "nombre": "AHUATEPEC",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  }
                }
            }
        }

 **Error Responses:**

  * **Code:** 401 Unauthorized <br />
    **Content:** 
    
        {
          "error": "Unauthenticated."
        }