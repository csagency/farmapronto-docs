## Listado de gastos incidencias
Regresa el listado de los gastos de incidencias

 **URL**

    /api/catalogos/gastos-incidencias-sucursales

 **Method:**

  `GET`
  
 **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data
      
       
 **Data Params**
    
    'motivo_id' => 'nullable|exists:catalogo_motivos_incidencias_sucursales,id'
     
 **URL Params**

      - motivo_id = 1
        Devuelve todos los registros de tipo llantas
        Ejemplo URI: `api/catalogos/gastos-incidencias-sucursales?motivo_id=1`
     

**Success Response:**

* **Code:** 200 <br />
  **Content:** 
  
      {
           "gastos": [
               {
                 "id": 1,
                 "motivo_id": 1,
                 "nombre": "Prueba",
                 "monto_max": "1",
                 "monto_min": null,
                 "tiempo_reparacion_tipo": null,
                 "tiempo_reparacion": null,
                 "created_at": "2020-06-24 20:11:02",
                 "updated_at": "2020-06-24 20:48:26",
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
            "motivo_id": [
              "El campo motivo id es inválido."
            ]
        }
            
                    
## Detalle de gasto incidencia
Regresa el registro de un gasto de incidencia

 **URL**

    /api/catalogos/gastos-incidencias-sucursales/{ID}

 **Method:**

  `GET`
  
 **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data
     
 **URL Params**

      - includes[] = motivo
        Ejemplo URI: `api/catalogos/gastos-incidencias-sucursales/1?includes[]=motivo`

**Success Response:**

* **Code:** 200 <br />
  **Content:** 
  
      {
           "gasto": {
               "id": 1,
               "motivo_id": 1,
               "nombre": "Prueba",
               "monto_max": "1",
               "monto_min": null,
               "tiempo_reparacion_tipo": null,
               "tiempo_reparacion": null,
               "created_at": "2020-06-24 20:11:02",
               "updated_at": "2020-06-24 20:48:26",
               "deleted_at": null
             }
      }

**Error Response:**

  * **Code:** 401 Unauthorized <br />
    **Content:** 
  
          {
            "error": "Unauthenticated."
          }  
