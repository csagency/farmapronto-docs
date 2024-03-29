      
## Listado de todas las promociones

Regresa el listado de registros de promociones nacionales y de sucursal

 **URL**

    /api-v2/promociones
  
 **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      
      
 **Method:**

  `POST`
  
 **Data Params**
    
    'sucursal_id' => 'nullable|exists:pedidos,id',

**Success Response:**

* **Code:** 200 <br />
  **Content:** 
  
      {
             "nacionales": [
               {
                 "id": 1,
                 "nombre": "Prueba1",
                 "imagen": "uploads\/images\/promociones\/4RDhtVGiOo1hjzhUdzR9rDeHVYL7HZzYD7y5Acod.jpeg",
                 "activa": 1,
                 "started_at": "2020-05-01 00:00:00",
                 "finished_at": "2020-05-31 00:00:00",
                 "created_at": "2020-05-15 18:18:23",
                 "updated_at": "2020-05-19 14:58:51",
                 "deleted_at": null
               }
             ],
             "sucursales": [
               {
                 "id": 1,
                 "sucursal_id": 96,
                 "nombre": "Prueba",
                 "imagen": "uploads\/images\/promociones\/78umprG5J2IAqJbCYFamMBoXSGHZZRdFTQuvymYO.jpeg",
                 "activa": 1,
                 "started_at": null,
                 "finished_at": null,
                 "created_at": "2020-05-15 18:33:02",
                 "updated_at": "2020-05-15 18:33:02",
                 "deleted_at": null
               },
               {
                 "id": 2,
                 "sucursal_id": 96,
                 "nombre": "gfdggfg",
                 "imagen": "uploads\/images\/promociones\/TK1u1V45mOtsC5b0RAF65DjOnlRn1qcvsT3NApa4.jpeg",
                 "activa": 1,
                 "started_at": "2020-05-01 00:00:00",
                 "finished_at": "2020-05-31 00:00:00",
                 "created_at": "2020-05-19 14:24:50",
                 "updated_at": "2020-05-19 14:27:44",
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
       
* **Code:** 422 Unprocessable Entity <br />
  **Content:** 
  
      {
            "sucursal_id": [
               "El campo sucursal id es inválido."
            ]
      }
      
      
## Detalle de promoción

Regresa el detalle de una promoción (por defecto busca en promociones nacionales)

 **URL**

    /api-v2/promociones/ID
  
 **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      
      
 **Method:**

  `POST`
  
 **Data Params**
    
    'tipo' => 'nullable|in:nacional,sucursal',

**Success Response:**

* **Code:** 200 <br />
  **Content:** 
  
      {
          "promocion": {
              "id": 2,
              "sucursal_id": 96,
              "nombre": "gfdggfg",
              "imagen": "uploads\/images\/promociones\/TK1u1V45mOtsC5b0RAF65DjOnlRn1qcvsT3NApa4.jpeg",
              "activa": 1,
              "started_at": "2020-05-01 00:00:00",
              "finished_at": "2020-05-31 00:00:00",
              "created_at": "2020-05-19 14:24:50",
              "updated_at": "2020-05-19 14:27:44",
              "deleted_at": null,
              "sucursal": {
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
                "disponible": 0,
                "created_at": "2019-09-03 10:14:53",
                "updated_at": "2019-12-20 18:11:49",
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
       
* **Code:** 422 Unprocessable Entity <br />
  **Content:** 
  
      {
          "tipo": [
            "El campo tipo es inválido."
          ]
      }



      
## Registrar promoción de sucursal

Regresa el detalle de una promoción de sucursal registrada

 **URL**

    /api-v2/promociones/crear
  
 **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      
      
 **Method:**

  `POST`
  
 **Data Params**
    
    'nombre' => 'required',
    'imagen' => 'required|image',
    'started_at' => 'required|date|before:finished_at',
    'finished_at' => 'required|date|after:started_at'

**Success Response:**

* **Code:** 200 <br />
  **Content:** 
  
      {
          "promocion": {
              "nombre": "Promo sucursal API",
              "imagen": "uploads\/images\/promociones\/Kh7Xz6xlJ9GKZBFomTmUHwj55k04QAPrGN2xBUvN.jpeg",
              "activa": true,
              "sucursal_id": 22,
              "started_at": "2020-05-11 00:00:00",
              "finished_at": "2020-05-21 23:59:59",
              "updated_at": "2020-05-19 15:30:16",
              "created_at": "2020-05-19 15:30:16",
              "id": 3,
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
                "updated_at": "2020-04-30 14:07:48",
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
      
* **Code:** 404 Not Found <br />
  **Content:** 
  
      {
        "error": "Sucursal no disponible."
      }
       
* **Code:** 422 Unprocessable Entity <br />
  **Content:** 
  
      {
           "nombre": [
             "El campo nombre es obligatorio."
           ],
           "imagen": [
             "El campo imagen es obligatorio."
           ],
           "started_at": [
             "El campo fecha inicio es obligatorio.",
             "El campo fecha inicio no es una fecha válida.",
             "El campo fecha inicio debe ser una fecha anterior a fecha fin.",
           ],
           "finished_at": [
             "El campo fecha fin es obligatorio.",
             "El campo fecha fin no es una fecha válida.",
             "El campo fecha fin debe ser una fecha posterior a fecha inicio."
           ]
      }
      
 ### Promos random     
  
 **URL**

    /api-v2/promociones-random

 **Descripción**
 Devuelve random 10 promociones

 **Method:**

  `GET`
  
  + Response 200 (application/json) Ejemplo:
  

        {
          "promociones": [
             {
                  "id": 1931,
                  "activo": 0,
                  "nombre": "Compra 4 y recibe 25% de descuento",
                  "descripcion": "* METFORMINA\/GLIBENCLAMIDA (MILEFAR-C) 500\/5 MG C\/60 TAB",
                  "modo": "combinados",
                  "grupo": "GENERICOS",
                  "fabricante": "ARLEX",
                  "started_at": "2020-05-25",
                  "finished_at": "2021-05-25",
                  "tipo_id": 7,
                  "created_at": "2020-05-25 13:58:11",
                  "updated_at": "2020-05-25 13:58:11",
                  "deleted_at": null,
                  "productos": [
                    {
                      "id": 1932,
                      "promocion_id": 1931,
                      "producto_id": 47028,
                      "cantidad": 4,
                      "monto": "25.00",
                      "created_at": "2020-05-25 13:58:11",
                      "updated_at": "2020-05-25 13:58:11",
                      "deleted_at": null,
                      "producto": {
                        "id": 47028,
                        "farmapronto_id": "052790",
                        "sku": "7501672602163",
                        "nombre": " METFORMINA\/GLIBENCLAMIDA (MILEFAR-C) 500\/5 MG C\/60 TAB",
                        "descripcion": " METFORMINA\/GLIBENCLAMIDA (MILEFAR-C) 500\/5 MG C\/60 TAB",
                        "categoria": "DIGESTIVO Y METABOLISMO",
                        "categoria_id": null,
                        "laboratorio": "Bayer",
                        "receta": 0,
                        "clave": "SUJETO A DISPONIBILIDAD",
                        "tipo": 0,
                        "activos": "METFORMINA \/ GLIBENCLAMIDA",
                        "keywords": null,
                        "frecuencia": null,
                        "contenido": null,
                        "dosis": null,
                        "tipoempaque": null,
                        "temporada": null,
                        "destacado": 0,
                        "archivo": null,
                        "created_at": "2017-03-16 11:50:03",
                        "updated_at": "2018-07-04 01:29:46",
                        "activo": 0,
                        "despliega": 0
                      }
                    }
                  ],
                  "tipo": {
                    "id": 7,
                    "nombre": "% Descuento",
                    "created_at": "2020-05-20 17:31:56",
                    "updated_at": "2020-05-20 17:31:56"
                  }
                },...
          ]
        }
