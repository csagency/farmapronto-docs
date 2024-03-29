**CheckIn activo**
----
Regresa la información del checkin activo

 **URL**

  `/api/sucursales/me/check`

 **Method:**

  `GET`

  **Headers**

      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data
      
  **URL Params**
  
    - includes[]= sucursal, estatus, estado, checkIn, checkOut, estadoAprobado <br><br>
    Ejemplo URI: `api/sucursales/me/check?includes[]=sucursal`
     

  **Success Response:**

  * **Code:** 200 <br />
    **Content**

        {
        	"check": {
                "id": 6,
                "sucursal_id": 22,
                "turno": "Vespertino",
                "tipo": "checkin",
                "check_id": null,
                "motos": 5,
                "telefonos": 4,
                "llaves": 5,
                "voucheras": 5,
                "impermeables": 5,
                "cascos": 5,
                "tarjetas": 5,
                "camaras": 5,
                "encargada": "CS PRUEBA",
                "observaciones": "Checkin de sucursal nuevo",
                "motos_foto": "uploads\/images\/sucursales\/checks\/6XKVTW6vhsvkGtpPcF0sWIim2XzyzbPIrS3TnDBV.jpeg",
                "telefonos_foto": "uploads\/images\/sucursales\/checks\/1zbfWgAXgMScw6qLuzs0b07XZIEWgeGXTn0qEQKS.jpeg",
                "llaves_foto": "uploads\/images\/sucursales\/checks\/1MuEA2iVom7NUh6W5JDXCJOyGgCWu1l9aFELy4Ej.jpeg",
                "cascos_foto": "uploads\/images\/sucursales\/checks\/E5yssFreDBofQZTOZ1Fstw16NNapBmGcoCT1CbUd.jpeg",
                "aceites_foto": "uploads\/images\/sucursales\/checks\/SU5gR3nSg5IjDcIJjxSCEwHkqsh3dN5mL1lknkWG.jpeg",
                "created_at": "2019-12-11 18:12:04",
                "updated_at": "2019-12-11 18:12:04",
                "deleted_at": null,
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
                  "ciudad_cobertura_id": null,
                  "direccion": "AV.MORELOS SUR",
                  "direccion_numero": "157",
                  "codigo_postal": "62050",
                  "lon": "-99.23195740395204",
                  "lat": "18.90517509983967",
                  "ancla": 0,
                  "dias": "LUN, MAR, MIE, JUE, VIE, SAB, DOM",
                  "horario_inicio": "07:00:00",
                  "horario_final": "23:00:00",
                  "24_hrs": 0,
                  "base": 0,
                  "almacen": 1,
                  "created_at": "2017-03-16 17:50:05",
                  "updated_at": "2019-10-22 15:29:34",
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

  * **Code:** 409 Conflict <br />
    **Content:**

        {
          "error": "El usuario no cuenta con perfil de sucursal."
        }


**CheckIn / CheckOut**
----
Almacena la información del check

 **URL**

  `/api/sucursales/me/check`

 **Method:**

  `POST`

  **Headers**

      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data


 **Data Params**

    'turno' => 'required|in:Matutino,Intermedio,Vespertino',
    'tipo' => 'required|in:checkin,checkout',
    'guardar' => 'nullable|boolean',
    'check_id' => 'nullable',
    'motos' => 'nullable',
    'telefonos' => 'nullable',
    'llaves' => 'nullable',
    'voucheras' => 'nullable',
    'impermeables' => 'nullable',
    'cascos' => 'nullable',
    'tarjetas' => 'nullable',
    'camaras' => 'nullable',
    'chalecos' => 'nullable',
    'encargada' => 'required',
    'observaciones' => 'nullable',
    'motos_foto' => 'nullable|image',
    'telefonos_foto' => 'nullable|image',
    'llaves_foto' => 'nullable|image',
    'cascos_foto' => 'nullable|image',
    'aceites_foto' => 'nullable|image',
    'chalecos_foto' => 'nullable|image',
     

  **Success Response:**

  * **Code:** 200 <br />
    **Content**

        {
        	"check": {
                "sucursal_id": 22,
                "turno": "Vespertino",
                "tipo": "checkin",
                "check_id": null,
                "motos": "5",
                "telefonos": "4",
                "llaves": "5",
                "voucheras": "5",
                "impermeables": "5",
                "cascos": "5",
                "tarjetas": "5",
                "camaras": "5",
                "encargada": "CS PRUEBA",
                "observaciones": "Checkin de sucursal nuevo",
                "motos_foto": "uploads\/images\/sucursales\/checks\/UeBS1s6uQDAwWNxiLOT8G82A9lG6eusu0FM06TkP.jpeg",
                "telefonos_foto": "uploads\/images\/sucursales\/checks\/0iYI394nECY87v6ZeTb2pcv8WKyXR9PP8NamkNAR.jpeg",
                "llaves_foto": "uploads\/images\/sucursales\/checks\/q94zH6y7KV61PFM7OhE9tLE5AjKlegQY4jxyVX15.jpeg",
                "cascos_foto": "uploads\/images\/sucursales\/checks\/sHAfGdAAN8ISivWia5JKeryCbHK0WGg7FceCUCnp.jpeg",
                "aceites_foto": "uploads\/images\/sucursales\/checks\/e43kHW2HC4MsogzbNmB1M7RB2YxQVH5xcT6ZgbNY.jpeg",
                "updated_at": "2019-11-26 17:17:43",
                "created_at": "2019-11-26 17:17:43",
                "id": 6,
                "estatus": [
                  {
                    "id": 6,
                    "check_id": 6,
                    "user_id": 133,
                    "nombre": "enviado",
                    "created_at": "2019-11-26 17:17:43",
                    "updated_at": "2019-11-26 17:17:43",
                    "deleted_at": null,
                    "user": {
                      "id": 133,
                      "name": "Sucursal 24",
                      "last_name": "YY",
                      "second_last_name": "62742",
                      "telephone": "0000000000",
                      "clave": "SUYYCTPD",
                      "email": "sucursal24@grupofarmapronto.com",
                      "player_id": "7a7fb3ed-c171-442c-9295-adee9e7ed0a5",
                      "tipo_usuario": "sucursal",
                      "activo": 1,
                      "baja": 0,
                      "fb_id": null,
                      "webhook_url": null,
                      "created_at": "2017-07-05 13:45:03",
                      "updated_at": "2019-11-21 08:14:29",
                      "deleted_at": null,
                      "last_login": "2019-09-26 18:21:37"
                    }
                  }
                ]
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

  * **Code:** 411 Length Required <br />
    **Content:**

        {
          "message": "El inventario no corresponde a los reportado en tu check in."
        }

  * **Code:** 412 Precondition Failed <br />
    **Content:**

        {
          "message": "Acción no autorizada. Debe ser sucursal base."
        }

  * **Code:** 422 Unprocessable entity <br />
    **Content:**

        {
              "turno": [
                "El campo turno es obligatorio."
              ],
              "tipo": [
                "El campo tipo es obligatorio."
              ],
              "encargada": [
                "El campo encargada es obligatorio."
              ],
              "guardar": [
                "El campo guardar debe tener un valor verdadero o falso."
              ]
        }

