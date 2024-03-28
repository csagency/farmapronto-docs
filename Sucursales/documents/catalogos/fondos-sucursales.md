## Listado de fondos sucursales
Regresa el listado de los fondos de sucursales<br>
*NOTA: Las cantidades vienen multiplicadas por 100*

 **URL**

    /api/catalogos/fondos-sucursales

 **Method:**

  `GET`
  
 **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data
     
     
 **Params**
 
        
         'tipo' => 'nullable|in:ultimo,dia,fecha',
         'fecha' => 'date|required_if:tipo,fecha|nullable',
         'sucursal_id' => 'nullable',
         'horario' => 'nullable|in:7:30,14:30,21,20',
         'pendientes' => 'nullable|boolean',
         
         

**Success Response:**

* **Code:** 200 <br />
  **Content:** 
  
      {
         "fondos_sucursales": [
             {
               "id": 1,
               "sucursal_id": 10,
               "cincuenta_centavos": 10000,
               "un_peso": 10000,
               "dos_pesos": 10000,
               "cinco_pesos": 10000,
               "diez_pesos": 10000,
               "veinte_pesos": 10000,
               "cincuenta_pesos": 10000,
               "cien_pesos": 10000,
               "doscientos_pesos": 10000,
               "quinientos_pesos": 10000,
               "mil_pesos": 10000,
               "vale": 10000,
               "gasto": 10000,
               "total": 110000,
               "ultimo_horario": "21:00:00",
               "created_at": null,
               "updated_at": null,
               "deleted_at": null
             },
             {
               "id": 2,
               "sucursal_id": 30,
               "cincuenta_centavos": 10000,
               "un_peso": 20000,
               "dos_pesos": 20000,
               "cinco_pesos": 20000,
               "diez_pesos": 20000,
               "veinte_pesos": 30000,
               "cincuenta_pesos": 20000,
               "cien_pesos": 100000,
               "doscientos_pesos": 100000,
               "quinientos_pesos": 500000,
               "mil_pesos": 1000000,
               "vale": 100000,
               "gasto": 100000,
               "total": 1840000,
               "ultimo_horario": "21:00:00",
               "created_at": "2019-10-16 18:58:24",
               "updated_at": "2019-10-16 19:05:51",
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
          
            
                    
## Detalle de fondos incidencia
Regresa el registro de un fondos incidencia<br>
*NOTA: Las cantidades vienen multiplicadas por 100*

 **URL**

    /api/catalogos/fondos-sucursales/{IDsucursal}

 **Method:**

  `GET`
  
 **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data
     
 **URL Params**

      - includes[] = sucursal
        Ejemplo URI: `api/catalogos/fondos-sucursales/10?includes[]=sucursal`

**Success Response:**

* **Code:** 200 <br />
  **Content:** 
  
      {
           "fondo_sucursal": [
               {
                 "id": 1,
                 "sucursal_id": 10,
                 "cincuenta_centavos": 10000,
                 "un_peso": 10000,
                 "dos_pesos": 10000,
                 "cinco_pesos": 10000,
                 "diez_pesos": 10000,
                 "veinte_pesos": 10000,
                 "cincuenta_pesos": 10000,
                 "cien_pesos": 10000,
                 "doscientos_pesos": 10000,
                 "quinientos_pesos": 10000,
                 "mil_pesos": 10000,
                 "vale": 10000,
                 "gasto": 10000,
                 "total": 110000,
                 "ultimo_horario": "21:00:00",
                 "created_at": null,
                 "updated_at": null,
                 "deleted_at": null,
                 "sucursal": {
                   "id": 10,
                   "tipo_sucursal": null,
                   "nombre": "L",
                   "codigo": "7",
                   "direccion": "CAMINO A ZUMPANGO",
                   "lat": "17.6059991",
                   "lon": "-99.5228515",
                   "meta_encargadas": 0,
                   "meta_auxiliares": 0,
                   "meta_cajeras": 0,
                   "fondo_venta_mensual": 0,
                   "fondo_callcenter": 0,
                   "matutino": 1,
                   "vespertino": 1,
                   "intermedio": 0,
                   "fondo_asignado": 0,
                   "created_at": "2019-09-23 05:22:31",
                   "updated_at": "2019-09-23 05:22:31",
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
