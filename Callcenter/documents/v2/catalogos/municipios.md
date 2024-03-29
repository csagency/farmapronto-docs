      
## Listado de municipios
Regresa el listado del catálogo de Municipios

 **URL**

    /api-v2/catalogos/municipios

 **Method:**

  `GET`

**URL Params**

  - includes[]=estados <br><br>
  Ejemplo URI: `api-v2/catalogos/municipios?includes[]=estado&limit=10`

**Success Response:**

* **Code:** 200 <br />
  **Content:** 
  
      {
        "municipios": [
            {
              "id": 1,
              "estado_id": 31,
              "nombre": "ABALA",
              "created_at": "2017-03-16 17:47:55",
              "updated_at": "2017-03-16 17:47:55",
              "estado": {
                "id": 31,
                "nombre": "YUCATAN",
                "created_at": "2017-03-16 17:47:54",
                "updated_at": "2017-03-16 17:47:54"
              }
            },
            {
              "id": 2,
              "estado_id": 7,
              "nombre": "ABASOLO",
              "created_at": "2017-03-16 17:47:55",
              "updated_at": "2017-03-16 17:47:55",
              "estado": {
                "id": 7,
                "nombre": "COAHUILA",
                "created_at": "2017-03-16 17:47:54",
                "updated_at": "2017-03-16 17:47:54"
              }
            },
            {
              "id": 3,
              "estado_id": 11,
              "nombre": "ABASOLO",
              "created_at": "2017-03-16 17:47:55",
              "updated_at": "2017-03-16 17:47:55",
              "estado": {
                "id": 11,
                "nombre": "GUANAJUATO",
                "created_at": "2017-03-16 17:47:54",
                "updated_at": "2017-03-16 17:47:54"
              }
            },
            {
              "id": 4,
              "estado_id": 19,
              "nombre": "ABASOLO",
              "created_at": "2017-03-16 17:47:55",
              "updated_at": "2017-03-16 17:47:55",
              "estado": {
                "id": 19,
                "nombre": "NUEVO LEON",
                "created_at": "2017-03-16 17:47:54",
                "updated_at": "2017-03-16 17:47:54"
              }
            },
            {
              "id": 5,
              "estado_id": 28,
              "nombre": "ABASOLO",
              "created_at": "2017-03-16 17:47:55",
              "updated_at": "2017-03-16 17:47:55",
              "estado": {
                "id": 28,
                "nombre": "TAMAULIPAS",
                "created_at": "2017-03-16 17:47:54",
                "updated_at": "2017-03-16 17:47:54"
              }
            },
            {
              "id": 6,
              "estado_id": 20,
              "nombre": "ABEJONES",
              "created_at": "2017-03-16 17:47:55",
              "updated_at": "2017-03-16 17:47:55",
              "estado": {
                "id": 20,
                "nombre": "OAXACA",
                "created_at": "2017-03-16 17:47:54",
                "updated_at": "2017-03-16 17:47:54"
              }
            },
            {
              "id": 7,
              "estado_id": 5,
              "nombre": "ACACOYAGUA",
              "created_at": "2017-03-16 17:47:55",
              "updated_at": "2017-03-16 17:47:55",
              "estado": {
                "id": 5,
                "nombre": "CHIAPAS",
                "created_at": "2017-03-16 17:47:54",
                "updated_at": "2017-03-16 17:47:54"
              }
            },
            {
              "id": 8,
              "estado_id": 21,
              "nombre": "ACAJETE",
              "created_at": "2017-03-16 17:47:55",
              "updated_at": "2017-03-16 17:47:55",
              "estado": {
                "id": 21,
                "nombre": "PUEBLA",
                "created_at": "2017-03-16 17:47:54",
                "updated_at": "2017-03-16 17:47:54"
              }
            },
            {
              "id": 9,
              "estado_id": 30,
              "nombre": "ACAJETE",
              "created_at": "2017-03-16 17:47:55",
              "updated_at": "2017-03-16 17:47:55",
              "estado": {
                "id": 30,
                "nombre": "VERACRUZ",
                "created_at": "2017-03-16 17:47:54",
                "updated_at": "2017-03-16 17:47:54"
              }
            },
            {
              "id": 10,
              "estado_id": 5,
              "nombre": "ACALA",
              "created_at": "2017-03-16 17:47:55",
              "updated_at": "2017-03-16 17:47:55",
              "estado": {
                "id": 5,
                "nombre": "CHIAPAS",
                "created_at": "2017-03-16 17:47:54",
                "updated_at": "2017-03-16 17:47:54"
              }
            }
        ]
      }

 
**Datos de un municipio**
----
  Regresa la información de un municipio en específico y sus relaciones

 **URL**

    /api-v2/catalogos/municipios/ID

 **Method:**

  `GET`
      
  **URL Params**

  - includes[]=estado, ciudades <br><br>
  Ejemplo URI: `api-v2/catalogos/municipios/502?includes[]=estado&includes[]=ciudades`
  

 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 

        { 
            "municipios": {
                "id": 502,
                "estado_id": 17,
                "nombre": "CUERNAVACA",
                "created_at": "2017-03-16 17:47:55",
                "updated_at": "2017-03-16 17:47:55",
                "estado": {
                  "id": 17,
                  "nombre": "MORELOS",
                  "created_at": "2017-03-16 17:47:54",
                  "updated_at": "2017-03-16 17:47:54"
                },
                "ciudades": [
                  {
                    "id": 34641,
                    "municipio_id": 502,
                    "codigo_postal": "62000",
                    "nombre": "CUERNAVACA CENTRO",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34642,
                    "municipio_id": 502,
                    "codigo_postal": "62008",
                    "nombre": "SECRETARIA DE HACIENDA Y CREDITO PUBLICO",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34643,
                    "municipio_id": 502,
                    "codigo_postal": "62009",
                    "nombre": "PALACIO DE GOBIERNO DEL ESTADO DE MORELOS",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34644,
                    "municipio_id": 502,
                    "codigo_postal": "62010",
                    "nombre": "ALTAVISTA",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34645,
                    "municipio_id": 502,
                    "codigo_postal": "62017",
                    "nombre": "MARGARITA MAZA DE JUAREZ",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34646,
                    "municipio_id": 502,
                    "codigo_postal": "62018",
                    "nombre": "ALTAVISTA",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34647,
                    "municipio_id": 502,
                    "codigo_postal": "62019",
                    "nombre": "LOMA HERMOSA",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34648,
                    "municipio_id": 502,
                    "codigo_postal": "62020",
                    "nombre": "LOMAS DE SAN ANTON",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34649,
                    "municipio_id": 502,
                    "codigo_postal": "62020",
                    "nombre": "LOPEZ PORTILLO",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34650,
                    "municipio_id": 502,
                    "codigo_postal": "62020",
                    "nombre": "SACATIERRA",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34651,
                    "municipio_id": 502,
                    "codigo_postal": "62020",
                    "nombre": "SAN ANTON",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34652,
                    "municipio_id": 502,
                    "codigo_postal": "62029",
                    "nombre": "CHULA VISTA",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34653,
                    "municipio_id": 502,
                    "codigo_postal": "62030",
                    "nombre": "CLUB DE GOLF",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34654,
                    "municipio_id": 502,
                    "codigo_postal": "62030",
                    "nombre": "CUERNAVACA",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34655,
                    "municipio_id": 502,
                    "codigo_postal": "62037",
                    "nombre": "BENITO JUAREZ LAGUNILLA",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34656,
                    "municipio_id": 502,
                    "codigo_postal": "62038",
                    "nombre": "LAGUNILLA",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34657,
                    "municipio_id": 502,
                    "codigo_postal": "62039",
                    "nombre": "LAGUNILLA EL SALTO",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34658,
                    "municipio_id": 502,
                    "codigo_postal": "62040",
                    "nombre": "MAESTROS",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34659,
                    "municipio_id": 502,
                    "codigo_postal": "62040",
                    "nombre": "MIGUEL HIDALGO",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34660,
                    "municipio_id": 502,
                    "codigo_postal": "62050",
                    "nombre": "BENITO JUAREZ CENTRO",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34661,
                    "municipio_id": 502,
                    "codigo_postal": "62050",
                    "nombre": "LAS PALMAS SUR",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34662,
                    "municipio_id": 502,
                    "codigo_postal": "62057",
                    "nombre": "LOS PILARES",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34663,
                    "municipio_id": 502,
                    "codigo_postal": "62058",
                    "nombre": "MAIL BOXES CUERNAPOST SA DE CV",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34664,
                    "municipio_id": 502,
                    "codigo_postal": "62059",
                    "nombre": "BONDIES",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34665,
                    "municipio_id": 502,
                    "codigo_postal": "62060",
                    "nombre": "BUROCRATICA",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34666,
                    "municipio_id": 502,
                    "codigo_postal": "62060",
                    "nombre": "QUINTANA ROO",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34667,
                    "municipio_id": 502,
                    "codigo_postal": "62070",
                    "nombre": "CHIPITLAN",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34668,
                    "municipio_id": 502,
                    "codigo_postal": "62070",
                    "nombre": "MINAS",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34669,
                    "municipio_id": 502,
                    "codigo_postal": "62076",
                    "nombre": "ADOLFO LOPEZ MATEOS",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34670,
                    "municipio_id": 502,
                    "codigo_postal": "62076",
                    "nombre": "POLVORIN",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34671,
                    "municipio_id": 502,
                    "codigo_postal": "62080",
                    "nombre": "LAZARO CARDENAS",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34672,
                    "municipio_id": 502,
                    "codigo_postal": "62080",
                    "nombre": "LOMA BONITA",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34673,
                    "municipio_id": 502,
                    "codigo_postal": "62100",
                    "nombre": "SANTA MARIA AHUACATITLAN",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34674,
                    "municipio_id": 502,
                    "codigo_postal": "62103",
                    "nombre": "SANTA ELENA DE LA CRUZ",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34675,
                    "municipio_id": 502,
                    "codigo_postal": "62110",
                    "nombre": "RINCONADA FLORIDA",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34676,
                    "municipio_id": 502,
                    "codigo_postal": "62115",
                    "nombre": "INDEPENDENCIA",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34677,
                    "municipio_id": 502,
                    "codigo_postal": "62115",
                    "nombre": "OCOTERA",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34678,
                    "municipio_id": 502,
                    "codigo_postal": "62116",
                    "nombre": "BALCONES DE TEPUENTE",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34679,
                    "municipio_id": 502,
                    "codigo_postal": "62116",
                    "nombre": "CAMINERA",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34680,
                    "municipio_id": 502,
                    "codigo_postal": "62116",
                    "nombre": "MIRADOR UNIVERSIDAD",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34681,
                    "municipio_id": 502,
                    "codigo_postal": "62116",
                    "nombre": "TEPUENTE",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34682,
                    "municipio_id": 502,
                    "codigo_postal": "62116",
                    "nombre": "VALLE TEPUENTE",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34683,
                    "municipio_id": 502,
                    "codigo_postal": "62117",
                    "nombre": "PROVIDENCIAS DE JERUSALEN",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34684,
                    "municipio_id": 502,
                    "codigo_postal": "62120",
                    "nombre": "EL MONASTERIO",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34685,
                    "municipio_id": 502,
                    "codigo_postal": "62120",
                    "nombre": "RANCHO CORTES",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34686,
                    "municipio_id": 502,
                    "codigo_postal": "62123",
                    "nombre": "OCOTITLA",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34687,
                    "municipio_id": 502,
                    "codigo_postal": "62130",
                    "nombre": "BUENAVISTA",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34688,
                    "municipio_id": 502,
                    "codigo_postal": "62130",
                    "nombre": "TETELA DEL MONTE",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34689,
                    "municipio_id": 502,
                    "codigo_postal": "62133",
                    "nombre": "LOS TEPETATES",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34690,
                    "municipio_id": 502,
                    "codigo_postal": "62136",
                    "nombre": "JARDINES DE TETELA",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34691,
                    "municipio_id": 502,
                    "codigo_postal": "62137",
                    "nombre": "LA MOJONERA",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34692,
                    "municipio_id": 502,
                    "codigo_postal": "62137",
                    "nombre": "LIENZO CHARRO",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34693,
                    "municipio_id": 502,
                    "codigo_postal": "62138",
                    "nombre": "LAS PALMAS NORTE",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34694,
                    "municipio_id": 502,
                    "codigo_postal": "62139",
                    "nombre": "LOMA LINDA",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34695,
                    "municipio_id": 502,
                    "codigo_postal": "62140",
                    "nombre": "BELLAVISTA",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34696,
                    "municipio_id": 502,
                    "codigo_postal": "62140",
                    "nombre": "BUGAMBILIAS",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34697,
                    "municipio_id": 502,
                    "codigo_postal": "62150",
                    "nombre": "DEL BOSQUE",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34698,
                    "municipio_id": 502,
                    "codigo_postal": "62156",
                    "nombre": "LOMAS DE TETELA 1a SECC",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34699,
                    "municipio_id": 502,
                    "codigo_postal": "62157",
                    "nombre": "LOMAS DE TETELA 3a SECC",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34700,
                    "municipio_id": 502,
                    "codigo_postal": "62157",
                    "nombre": "LOMAS DE ZOMPANTLE",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34701,
                    "municipio_id": 502,
                    "codigo_postal": "62158",
                    "nombre": "LOMAS DE TETELA 2a SECC",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34702,
                    "municipio_id": 502,
                    "codigo_postal": "62159",
                    "nombre": "ADOLFO RUIZ CORTINES",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34703,
                    "municipio_id": 502,
                    "codigo_postal": "62160",
                    "nombre": "HACIENDA TETELA",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34704,
                    "municipio_id": 502,
                    "codigo_postal": "62160",
                    "nombre": "RANCHO TETELA",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34705,
                    "municipio_id": 502,
                    "codigo_postal": "62165",
                    "nombre": "LOMA DE COYUCA",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34706,
                    "municipio_id": 502,
                    "codigo_postal": "62166",
                    "nombre": "ANALCO",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34707,
                    "municipio_id": 502,
                    "codigo_postal": "62166",
                    "nombre": "LOMAS DE AHUATLAN",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34708,
                    "municipio_id": 502,
                    "codigo_postal": "62170",
                    "nombre": "JIQUILPAN",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34709,
                    "municipio_id": 502,
                    "codigo_postal": "62170",
                    "nombre": "LA PRADERA",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34710,
                    "municipio_id": 502,
                    "codigo_postal": "62170",
                    "nombre": "TLALTENANGO",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34711,
                    "municipio_id": 502,
                    "codigo_postal": "62179",
                    "nombre": "SAN JERONIMO",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34712,
                    "municipio_id": 502,
                    "codigo_postal": "62180",
                    "nombre": "LOMA DE ATZINGO",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34713,
                    "municipio_id": 502,
                    "codigo_postal": "62180",
                    "nombre": "PLAN DE AYALA",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34714,
                    "municipio_id": 502,
                    "codigo_postal": "62190",
                    "nombre": "CAROLINA",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34715,
                    "municipio_id": 502,
                    "codigo_postal": "62200",
                    "nombre": "CHAMIZAL",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34716,
                    "municipio_id": 502,
                    "codigo_postal": "62200",
                    "nombre": "INSURGENTES",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34717,
                    "municipio_id": 502,
                    "codigo_postal": "62209",
                    "nombre": "CHAMILPA",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34718,
                    "municipio_id": 502,
                    "codigo_postal": "62210",
                    "nombre": "CHAMILPA",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34719,
                    "municipio_id": 502,
                    "codigo_postal": "62210",
                    "nombre": "LOS AGUACATES",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34720,
                    "municipio_id": 502,
                    "codigo_postal": "62214",
                    "nombre": "BENITO JUAREZ",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34721,
                    "municipio_id": 502,
                    "codigo_postal": "62215",
                    "nombre": "BLANCA UNIVERSIDAD",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34722,
                    "municipio_id": 502,
                    "codigo_postal": "62215",
                    "nombre": "RIO BALSAS",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34723,
                    "municipio_id": 502,
                    "codigo_postal": "62215",
                    "nombre": "UNIVERSIDAD",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34724,
                    "municipio_id": 502,
                    "codigo_postal": "62217",
                    "nombre": "LOMAS DE CHAMILPA 2a SECC",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34725,
                    "municipio_id": 502,
                    "codigo_postal": "62218",
                    "nombre": "LOMAS DE CHAMILPA 1a SECC",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34726,
                    "municipio_id": 502,
                    "codigo_postal": "62219",
                    "nombre": "CENTRO SCT MORELOS",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34727,
                    "municipio_id": 502,
                    "codigo_postal": "62220",
                    "nombre": "OCOTEPEC",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34728,
                    "municipio_id": 502,
                    "codigo_postal": "62220",
                    "nombre": "XICAPAN",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34729,
                    "municipio_id": 502,
                    "codigo_postal": "62226",
                    "nombre": "TEXCALTEPEC",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34730,
                    "municipio_id": 502,
                    "codigo_postal": "62227",
                    "nombre": "OCOTEPEC",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34731,
                    "municipio_id": 502,
                    "codigo_postal": "62228",
                    "nombre": "ARIES",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34732,
                    "municipio_id": 502,
                    "codigo_postal": "62229",
                    "nombre": "NOGALES",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34733,
                    "municipio_id": 502,
                    "codigo_postal": "62230",
                    "nombre": "MARAVILLAS",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34734,
                    "municipio_id": 502,
                    "codigo_postal": "62230",
                    "nombre": "SAN CRISTOBAL",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34735,
                    "municipio_id": 502,
                    "codigo_postal": "62232",
                    "nombre": "MAIL BOXES POST SISTEM DE MORELOS SA DE CV",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34736,
                    "municipio_id": 502,
                    "codigo_postal": "62237",
                    "nombre": "LOS FAROLES",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34737,
                    "municipio_id": 502,
                    "codigo_postal": "62238",
                    "nombre": "EL CONQUISTADOR",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34738,
                    "municipio_id": 502,
                    "codigo_postal": "62239",
                    "nombre": "PRADOS DE CUERNAVACA",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34739,
                    "municipio_id": 502,
                    "codigo_postal": "62240",
                    "nombre": "LOMAS DE CORTES",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34740,
                    "municipio_id": 502,
                    "codigo_postal": "62240",
                    "nombre": "RINCON DEL VALLE",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34741,
                    "municipio_id": 502,
                    "codigo_postal": "62245",
                    "nombre": "RECURSOS HIDRAULICOS",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34742,
                    "municipio_id": 502,
                    "codigo_postal": "62247",
                    "nombre": "LOMAS DE CORTES INFONAVIT",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34743,
                    "municipio_id": 502,
                    "codigo_postal": "62249",
                    "nombre": "TECOMULCO",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34744,
                    "municipio_id": 502,
                    "codigo_postal": "62250",
                    "nombre": "BASE TRANQUILIDAD",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34745,
                    "municipio_id": 502,
                    "codigo_postal": "62250",
                    "nombre": "DEL EMPLEADO",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34746,
                    "municipio_id": 502,
                    "codigo_postal": "62250",
                    "nombre": "TEZONTEPEC",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34747,
                    "municipio_id": 502,
                    "codigo_postal": "62260",
                    "nombre": "CUAUHTEMOC",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34748,
                    "municipio_id": 502,
                    "codigo_postal": "62260",
                    "nombre": "REFORMA",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34749,
                    "municipio_id": 502,
                    "codigo_postal": "62268",
                    "nombre": "GRANJAS NORTE",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34750,
                    "municipio_id": 502,
                    "codigo_postal": "62269",
                    "nombre": "JARDINES DE REFORMA",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34751,
                    "municipio_id": 502,
                    "codigo_postal": "62270",
                    "nombre": "LOMAS DE LA SELVA",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34752,
                    "municipio_id": 502,
                    "codigo_postal": "62270",
                    "nombre": "MIRAVAL",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34753,
                    "municipio_id": 502,
                    "codigo_postal": "62280",
                    "nombre": "GUALUPITA",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34754,
                    "municipio_id": 502,
                    "codigo_postal": "62290",
                    "nombre": "VISTA HERMOSA",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34755,
                    "municipio_id": 502,
                    "codigo_postal": "62300",
                    "nombre": "AHUATEPEC",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34756,
                    "municipio_id": 502,
                    "codigo_postal": "62303",
                    "nombre": "LOMAS DE LA HERRADURA",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34757,
                    "municipio_id": 502,
                    "codigo_postal": "62304",
                    "nombre": "GLORIA ALMADA DE BEJARANO",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34758,
                    "municipio_id": 502,
                    "codigo_postal": "62305",
                    "nombre": "JARDINES DE AHUATEPEC",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34759,
                    "municipio_id": 502,
                    "codigo_postal": "62305",
                    "nombre": "LOS RAMOS",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34760,
                    "municipio_id": 502,
                    "codigo_postal": "62306",
                    "nombre": "VILLA SANTIAGO",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34761,
                    "municipio_id": 502,
                    "codigo_postal": "62309",
                    "nombre": "ALARCON ESTACION",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34762,
                    "municipio_id": 502,
                    "codigo_postal": "62310",
                    "nombre": "GRANJAS DE LA HUERTA",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34763,
                    "municipio_id": 502,
                    "codigo_postal": "62320",
                    "nombre": "ANTONIO BARONA",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34764,
                    "municipio_id": 502,
                    "codigo_postal": "62324",
                    "nombre": "AMPLIACIÓN LA CAÑADA",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34765,
                    "municipio_id": 502,
                    "codigo_postal": "62324",
                    "nombre": "La Cañada",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34766,
                    "municipio_id": 502,
                    "codigo_postal": "62325",
                    "nombre": "RANCHO ALEGRE",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34767,
                    "municipio_id": 502,
                    "codigo_postal": "62328",
                    "nombre": "ANTONIO BARONA 3a SECC",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34768,
                    "municipio_id": 502,
                    "codigo_postal": "62329",
                    "nombre": "ANTONIO BARONA 1a SECC",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34769,
                    "municipio_id": 502,
                    "codigo_postal": "62329",
                    "nombre": "ANTONIO BARONA 2a SECC",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34770,
                    "municipio_id": 502,
                    "codigo_postal": "62330",
                    "nombre": "DELICIAS",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34771,
                    "municipio_id": 502,
                    "codigo_postal": "62340",
                    "nombre": "BELLO HORIZONTE",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34772,
                    "municipio_id": 502,
                    "codigo_postal": "62340",
                    "nombre": "LOMAS DE CORTES ORIENTE",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34773,
                    "municipio_id": 502,
                    "codigo_postal": "62340",
                    "nombre": "PLUTARCO ELIAS CALLES",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34774,
                    "municipio_id": 502,
                    "codigo_postal": "62343",
                    "nombre": "JARDINES DE DELICIAS",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34775,
                    "municipio_id": 502,
                    "codigo_postal": "62345",
                    "nombre": "RINCONADA FLORIDA",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34776,
                    "municipio_id": 502,
                    "codigo_postal": "62350",
                    "nombre": "LOMAS DE LOS VOLCANES",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34777,
                    "municipio_id": 502,
                    "codigo_postal": "62350",
                    "nombre": "LOMAS DEL MIRADOR",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34778,
                    "municipio_id": 502,
                    "codigo_postal": "62350",
                    "nombre": "TEOPANZOLCO",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34779,
                    "municipio_id": 502,
                    "codigo_postal": "62360",
                    "nombre": "CHAPULTEPEC",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34780,
                    "municipio_id": 502,
                    "codigo_postal": "62360",
                    "nombre": "JARDINES DE CUERNAVACA",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34781,
                    "municipio_id": 502,
                    "codigo_postal": "62370",
                    "nombre": "RICARDO FLORES MAGON",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34782,
                    "municipio_id": 502,
                    "codigo_postal": "62377",
                    "nombre": "SAN AGUSTIN",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34783,
                    "municipio_id": 502,
                    "codigo_postal": "62380",
                    "nombre": "ZODIACO",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34784,
                    "municipio_id": 502,
                    "codigo_postal": "62382",
                    "nombre": "JOYAS DE LOS JILGUEROS",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34785,
                    "municipio_id": 502,
                    "codigo_postal": "62384",
                    "nombre": "MARTIRES DE RIO BLANCO",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34786,
                    "municipio_id": 502,
                    "codigo_postal": "62385",
                    "nombre": "RAMON HERNANDEZ NAVARRO",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34787,
                    "municipio_id": 502,
                    "codigo_postal": "62386",
                    "nombre": "OTILIO MONTAÑO",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34788,
                    "municipio_id": 502,
                    "codigo_postal": "62387",
                    "nombre": "SANTA MARTHA AHUATEPEC",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34789,
                    "municipio_id": 502,
                    "codigo_postal": "62388",
                    "nombre": "LOS TULIPANES",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34790,
                    "municipio_id": 502,
                    "codigo_postal": "62389",
                    "nombre": "JOSE MARIA MORELOS Y PAVON",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34791,
                    "municipio_id": 502,
                    "codigo_postal": "62390",
                    "nombre": "REVOLUCION",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34792,
                    "municipio_id": 502,
                    "codigo_postal": "62398",
                    "nombre": "CIUDAD CHAPULTEPEC",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34793,
                    "municipio_id": 502,
                    "codigo_postal": "62398",
                    "nombre": "EL PORVENIR",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34794,
                    "municipio_id": 502,
                    "codigo_postal": "62399",
                    "nombre": "CIUDAD CHAPULTEPEC",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34795,
                    "municipio_id": 502,
                    "codigo_postal": "62400",
                    "nombre": "VERGEL",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34796,
                    "municipio_id": 502,
                    "codigo_postal": "62409",
                    "nombre": "SANTA VERACRUZ",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34797,
                    "municipio_id": 502,
                    "codigo_postal": "62410",
                    "nombre": "AMATITLAN",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34798,
                    "municipio_id": 502,
                    "codigo_postal": "62420",
                    "nombre": "JACARANDAS",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34799,
                    "municipio_id": 502,
                    "codigo_postal": "62420",
                    "nombre": "LAS QUINTAS MARTHAS",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34800,
                    "municipio_id": 502,
                    "codigo_postal": "62428",
                    "nombre": "COPA DE ORO",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34801,
                    "municipio_id": 502,
                    "codigo_postal": "62429",
                    "nombre": "BUGAMBILIAS",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34802,
                    "municipio_id": 502,
                    "codigo_postal": "62430",
                    "nombre": "CUAUHNAHUAC",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34803,
                    "municipio_id": 502,
                    "codigo_postal": "62430",
                    "nombre": "VICENTE GUERRERO",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34804,
                    "municipio_id": 502,
                    "codigo_postal": "62440",
                    "nombre": "ACAPATZINGO",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34805,
                    "municipio_id": 502,
                    "codigo_postal": "62440",
                    "nombre": "LAS QUINTAS",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34806,
                    "municipio_id": 502,
                    "codigo_postal": "62445",
                    "nombre": "LOS CIZOS",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34807,
                    "municipio_id": 502,
                    "codigo_postal": "62446",
                    "nombre": "SAN MIGUEL ACAPANTZINGO",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34808,
                    "municipio_id": 502,
                    "codigo_postal": "62447",
                    "nombre": "JARDINES DE ACAPATZINGO",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34809,
                    "municipio_id": 502,
                    "codigo_postal": "62448",
                    "nombre": "CANTARRANAS",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34810,
                    "municipio_id": 502,
                    "codigo_postal": "62450",
                    "nombre": "CHAPULTEPEC",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34811,
                    "municipio_id": 502,
                    "codigo_postal": "62450",
                    "nombre": "MANANTIALES",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34812,
                    "municipio_id": 502,
                    "codigo_postal": "62460",
                    "nombre": "GRANJAS",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34813,
                    "municipio_id": 502,
                    "codigo_postal": "62460",
                    "nombre": "SATELITE",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34814,
                    "municipio_id": 502,
                    "codigo_postal": "62460",
                    "nombre": "VICENTE ESTRADA CAJIGAL",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34815,
                    "municipio_id": 502,
                    "codigo_postal": "62466",
                    "nombre": "EMILIANO ZAPATA",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34816,
                    "municipio_id": 502,
                    "codigo_postal": "62467",
                    "nombre": "TARIANES",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34817,
                    "municipio_id": 502,
                    "codigo_postal": "62468",
                    "nombre": "BUGAMBILIAS",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34818,
                    "municipio_id": 502,
                    "codigo_postal": "62469",
                    "nombre": "ALEGRIA",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34819,
                    "municipio_id": 502,
                    "codigo_postal": "62470",
                    "nombre": "DEL LAGO",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34820,
                    "municipio_id": 502,
                    "codigo_postal": "62470",
                    "nombre": "LAS AGUILAS",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34821,
                    "municipio_id": 502,
                    "codigo_postal": "62475",
                    "nombre": "CHAPULTEPEC FOVISSSTE",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34822,
                    "municipio_id": 502,
                    "codigo_postal": "62480",
                    "nombre": "CHAPULTEPEC",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34823,
                    "municipio_id": 502,
                    "codigo_postal": "62490",
                    "nombre": "PALMIRA TINGUINDIN",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34824,
                    "municipio_id": 502,
                    "codigo_postal": "62496",
                    "nombre": "EL PALMAR",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34825,
                    "municipio_id": 502,
                    "codigo_postal": "62497",
                    "nombre": "RINCONADA",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34826,
                    "municipio_id": 502,
                    "codigo_postal": "62498",
                    "nombre": "TABACHINES",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34827,
                    "municipio_id": 502,
                    "codigo_postal": "62499",
                    "nombre": "FLAMINGOS",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34828,
                    "municipio_id": 502,
                    "codigo_postal": "62499",
                    "nombre": "LAS GARZAS",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34829,
                    "municipio_id": 502,
                    "codigo_postal": "62500",
                    "nombre": "CIVAC",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34830,
                    "municipio_id": 502,
                    "codigo_postal": "62507",
                    "nombre": "PEDREGAL",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34831,
                    "municipio_id": 502,
                    "codigo_postal": "62508",
                    "nombre": "BUENAVISTA DEL MONTE",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34832,
                    "municipio_id": 502,
                    "codigo_postal": "62509",
                    "nombre": "CAMPO MILITAR 6",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34983,
                    "municipio_id": 502,
                    "codigo_postal": "62700",
                    "nombre": "BUENA VISTA",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  }
                ]
            }
        }
    
    

**Colonias de un municipios**
----
  Regresa la información de colonias de un municipio

 **URL**

    /api-v2/catalogos/municipios/ID/colonias

 **Method:**

  `GET`
     
 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 


           {
              "colonias": [
                  {
                    "id": 34641,
                    "municipio_id": 502,
                    "codigo_postal": "62000",
                    "nombre": "CUERNAVACA CENTRO",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34642,
                    "municipio_id": 502,
                    "codigo_postal": "62008",
                    "nombre": "SECRETARIA DE HACIENDA Y CREDITO PUBLICO",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34643,
                    "municipio_id": 502,
                    "codigo_postal": "62009",
                    "nombre": "PALACIO DE GOBIERNO DEL ESTADO DE MORELOS",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34644,
                    "municipio_id": 502,
                    "codigo_postal": "62010",
                    "nombre": "ALTAVISTA",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34645,
                    "municipio_id": 502,
                    "codigo_postal": "62017",
                    "nombre": "MARGARITA MAZA DE JUAREZ",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34646,
                    "municipio_id": 502,
                    "codigo_postal": "62018",
                    "nombre": "ALTAVISTA",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34647,
                    "municipio_id": 502,
                    "codigo_postal": "62019",
                    "nombre": "LOMA HERMOSA",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34648,
                    "municipio_id": 502,
                    "codigo_postal": "62020",
                    "nombre": "LOMAS DE SAN ANTON",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34649,
                    "municipio_id": 502,
                    "codigo_postal": "62020",
                    "nombre": "LOPEZ PORTILLO",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  },
                  {
                    "id": 34650,
                    "municipio_id": 502,
                    "codigo_postal": "62020",
                    "nombre": "SACATIERRA",
                    "created_at": "2017-03-16 17:48:42",
                    "updated_at": "2017-03-16 17:48:42"
                  }
              ]
           }
       