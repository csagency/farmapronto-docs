      
## Listado de usos CFDI
Regresa el listado del catálogo de Usos CFDI

 **URL**

    /api-v2/catalogos/usos-cfdi

 **Method:**

  `GET`

**Success Response:**

* **Code:** 200 <br />
  **Content:** 
  
      {
        "usos": [
            {
              "id": 1,
              "clave": "G01",
              "nombre": "ADQUISICIÓN DE MERCANCIAS",
              "created_at": "2019-07-12 11:59:08",
              "updated_at": "2019-07-12 11:59:08"
            },
            {
              "id": 2,
              "clave": "G03",
              "nombre": "GASTOS EN GENERAL",
              "created_at": "2019-07-12 11:59:08",
              "updated_at": "2019-07-12 11:59:08"
            },
            {
              "id": 3,
              "clave": "P01",
              "nombre": "POR DEFINIR",
              "created_at": "2019-07-12 11:59:08",
              "updated_at": "2019-07-12 11:59:08"
            }
        ]
      }

 
**Datos de un uso CFDI**
----
  Regresa la información de una uso CFDI en específico y sus relaciones

 **URL**

    /api-v2/catalogos/usos-cfdi/ID

 **Method:**

  `GET`
      
  **URL Params**

  - includes[]=facturaciones <br><br>
  Ejemplo URI: `api-v2/catalogos/usos-cfdi/1?includes[]=facturaciones`
  


 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 

        {
            "uso": {
                "id": 1,
                "clave": "G01",
                "nombre": "ADQUISICIÓN DE MERCANCIAS",
                "created_at": "2019-07-12 11:59:08",
                "updated_at": "2019-07-12 11:59:08",
                "facturaciones": [
                  {
                    "id": 3920,
                    "rfc": "AAAAAAAAAAAAA",
                    "alias": "CFDI",
                    "cliente_direccion_id": null,
                    "created_at": "2019-07-12 16:33:44",
                    "updated_at": "2019-08-04 18:01:52",
                    "estado_id": 1,
                    "municipio_id": 145,
                    "calle": "Prueba ",
                    "numero": "prueba ",
                    "colonia": "Prueba ",
                    "codigo_postal": "62570",
                    "user_id": 14936,
                    "uso_cfdi_id": 1
                  },
                  {
                    "id": 3935,
                    "rfc": "cape761208ed3",
                    "alias": "Emilia Cárdenas Pedraza",
                    "cliente_direccion_id": null,
                    "created_at": "2019-07-14 16:12:51",
                    "updated_at": "2019-07-14 16:12:51",
                    "estado_id": 16,
                    "municipio_id": 1040,
                    "calle": "casa mata ",
                    "numero": "1153-9",
                    "colonia": "Chapultepec sur",
                    "codigo_postal": "58260",
                    "user_id": 17088,
                    "uso_cfdi_id": 1
                  },
                  {
                    "id": 4160,
                    "rfc": "RERJ8504101M3",
                    "alias": "jorge adan",
                    "cliente_direccion_id": null,
                    "created_at": "2019-08-11 19:35:00",
                    "updated_at": "2019-08-11 19:35:00",
                    "estado_id": 12,
                    "municipio_id": 2803,
                    "calle": "and. jade calle esmeralda",
                    "numero": "sn",
                    "colonia": "la joya",
                    "codigo_postal": "40894",
                    "user_id": 10191,
                    "uso_cfdi_id": 1
                  },
                  {
                    "id": 4161,
                    "rfc": "RERJ8504101M3",
                    "alias": "adan",
                    "cliente_direccion_id": null,
                    "created_at": "2019-08-11 19:48:59",
                    "updated_at": "2019-08-11 19:48:59",
                    "estado_id": 12,
                    "municipio_id": 2803,
                    "calle": "and jade calle esmeralda ",
                    "numero": "sn",
                    "colonia": "la joya",
                    "codigo_postal": "40894",
                    "user_id": 10191,
                    "uso_cfdi_id": 1
                  },
                  {
                    "id": 4228,
                    "rfc": "OIMP8310265P7",
                    "alias": "PABLO ESTEBAN ORTIZ DE LA MAZA ",
                    "cliente_direccion_id": null,
                    "created_at": "2019-08-19 13:01:36",
                    "updated_at": "2019-08-19 13:01:36",
                    "estado_id": 12,
                    "municipio_id": 16,
                    "calle": "AVENIDA COSTERA MIGUEL ALEMAN ",
                    "numero": "NO. EXT. 125 INT. M-21",
                    "colonia": "MAGALLANES",
                    "codigo_postal": "39670",
                    "user_id": 5154,
                    "uso_cfdi_id": 1
                  },
                  {
                    "id": 4410,
                    "rfc": "TECJ780121D1A",
                    "alias": "Facturas farmpronto",
                    "cliente_direccion_id": null,
                    "created_at": "2019-09-13 08:49:58",
                    "updated_at": "2019-09-13 08:51:15",
                    "estado_id": 9,
                    "municipio_id": 784,
                    "calle": "And. Cnel. E. Alarcón G. Mz.5 secc. B",
                    "numero": "8",
                    "colonia": "unidad la colmena",
                    "codigo_postal": "09170",
                    "user_id": 18181,
                    "uso_cfdi_id": 1
                  },
                  {
                    "id": 4683,
                    "rfc": "bzbsb",
                    "alias": "znd",
                    "cliente_direccion_id": null,
                    "created_at": "2019-10-23 18:59:36",
                    "updated_at": "2019-10-24 11:10:09",
                    "estado_id": 17,
                    "municipio_id": 727,
                    "calle": "bdbz",
                    "numero": "65",
                    "colonia": "dhdb",
                    "codigo_postal": "62010",
                    "user_id": 19090,
                    "uso_cfdi_id": 1
                  },
                  {
                    "id": 4731,
                    "rfc": "rffksksjs",
                    "alias": "alias 1",
                    "cliente_direccion_id": null,
                    "created_at": "2019-10-30 09:50:57",
                    "updated_at": "2019-10-30 09:50:57",
                    "estado_id": 17,
                    "municipio_id": 502,
                    "calle": "calle",
                    "numero": "123456",
                    "colonia": "colonia",
                    "codigo_postal": "62333",
                    "user_id": 19991,
                    "uso_cfdi_id": 1
                  },
                  {
                    "id": 4936,
                    "rfc": "aaa",
                    "alias": "gamacell",
                    "cliente_direccion_id": null,
                    "created_at": "2019-11-29 14:51:35",
                    "updated_at": "2019-11-29 14:51:35",
                    "estado_id": 12,
                    "municipio_id": 2803,
                    "calle": "calle ciruelos local #22",
                    "numero": "7555516150",
                    "colonia": "centro",
                    "codigo_postal": "40880",
                    "user_id": 20658,
                    "uso_cfdi_id": 1
                  },
                  {
                    "id": 5012,
                    "rfc": "bzbzb",
                    "alias": "bebd",
                    "cliente_direccion_id": null,
                    "created_at": "2019-12-10 13:24:33",
                    "updated_at": "2019-12-10 13:24:33",
                    "estado_id": 1,
                    "municipio_id": 42,
                    "calle": "bdbd",
                    "numero": "bzbd",
                    "colonia": "bxnd",
                    "codigo_postal": "62000",
                    "user_id": 19090,
                    "uso_cfdi_id": 1
                  },
                  {
                    "id": 5015,
                    "rfc": "bzbz",
                    "alias": "fjdn",
                    "cliente_direccion_id": null,
                    "created_at": "2019-12-10 18:05:20",
                    "updated_at": "2019-12-10 18:05:20",
                    "estado_id": 1,
                    "municipio_id": 42,
                    "calle": "hdd",
                    "numero": "bzbz",
                    "colonia": "djd",
                    "codigo_postal": "62000",
                    "user_id": 19090,
                    "uso_cfdi_id": 1
                  },
                  {
                    "id": 5067,
                    "rfc": "bdbz",
                    "alias": "dbz",
                    "cliente_direccion_id": null,
                    "created_at": "2019-12-16 11:57:22",
                    "updated_at": "2019-12-16 11:57:29",
                    "estado_id": 17,
                    "municipio_id": 87,
                    "calle": "zbz",
                    "numero": "bdbd",
                    "colonia": "bdx",
                    "codigo_postal": "62010",
                    "user_id": 19090,
                    "uso_cfdi_id": 1
                  },
                  {
                    "id": 5358,
                    "rfc": "COGC581029UV7",
                    "alias": "CARLOS ",
                    "cliente_direccion_id": null,
                    "created_at": "2020-01-25 14:04:53",
                    "updated_at": "2020-01-25 14:04:53",
                    "estado_id": 9,
                    "municipio_id": 875,
                    "calle": "CIPRÉS ",
                    "numero": "5 CASA 4",
                    "colonia": "LA CRUZ ",
                    "codigo_postal": "10800",
                    "user_id": 22094,
                    "uso_cfdi_id": 1
                  },
                  {
                    "id": 5470,
                    "rfc": "COAC7708102Y1",
                    "alias": "CHRISTIAN ",
                    "cliente_direccion_id": null,
                    "created_at": "2020-02-12 18:12:36",
                    "updated_at": "2020-02-12 18:12:36",
                    "estado_id": 9,
                    "municipio_id": 485,
                    "calle": "Rio Guadalquivir ",
                    "numero": "75",
                    "colonia": "CUAUHTÉMOC ",
                    "codigo_postal": "40880",
                    "user_id": 8773,
                    "uso_cfdi_id": 1
                  }
                ]
            }
        }