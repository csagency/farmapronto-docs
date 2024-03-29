## Listado de incidencias
Regresa el listado de todas las incidencias que cumplan con los filtros

 **URL**

  /api/gerentes/incidencias

 **Method:**

  `GET`
  
 **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      
      
 **Data Params**
    
     'fecha_inicio' => 'nullable|date|before:fecha_fin',
     'fecha_fin' => 'nullable|date|after:fecha_inicio',
     'sucursal_id' => 'nullable|exists:sucursales,id',
     'motivo_id' => 'nullable|exists:catalogo_motivos_incidencias,id',


****Catalogo de sucursales base**** [/api/catalogos/sucursales-base](https://github.com/csagency/farmapronto/blob/develop/resources/docs/catalogos/sucursales.md)

**URL Params**

  - includes[]= incidenciaGasto.estatus, vehiculo.sucursal, agente.user, motivo, proveedor, callCenter, alertas  <br><br>
  Ejemplo URI: `api/gerentes/incidencias?includes[]=incidenciaGasto`


**Filtro por fechas**

  Ejemplo URI: `api/gerentes/incidencias?fecha_inicio=2019-08-27&fecha_fin=2019-09-02`<br>
  

**Success Response:**

* **Code:** 200 <br />
  **Content:** 
  
      {
           "incidencias": [
               {
                 "id": 10801,
                 "agente_id": 28,
                 "folio": "GA10801",
                 "fecha": "2019-08-30 15:00:00",
                 "km": "1000",
                 "km_evidencia": "uploads\/images\/incidencias\/Gb6tiGn2tARrJTT0TQcjenGHFbvx0sCQekEAExWK.png",
                 "motivo_id": 4,
                 "vehiculo_id": 42,
                 "observaciones": "Prueba prueba",
                 "evidencia": "uploads\/images\/incidencias\/1tk5ePmqxmNhpR9y6uGcjmn1IWP3WqLP1pNhpfZs.png",
                 "proveedor_id": null,
                 "tipo_creacion": "dashboard_store",
                 "mantenimiento_id": null,
                 "created_at": "2019-08-30 16:13:58",
                 "updated_at": "2019-08-30 16:13:59",
                 "deleted_at": null,
                 "motivo": {
                   "id": 4,
                   "nombre": "Por gasolina",
                   "key": "gasolina",
                   "prefix": "GA",
                   "created_at": "2019-05-21 13:28:24",
                   "updated_at": "2019-08-02 17:05:13"
                 },
                 "vehiculo": {
                   "id": 42,
                   "sucursal_id": 84,
                   "placas": "CS-381",
                   "modelo": "YBR125C Express",
                   "marca": "Yamaha",
                   "num_serie": "",
                   "color": "",
                   "num_poliza": "",
                   "ultimo_servicio": "0000-00-00",
                   "bloqueado": 0,
                   "created_at": "2019-04-29 13:10:43",
                   "updated_at": "2019-08-02 19:12:49",
                   "deleted_at": null,
                   "sucursal": {
                     "id": 84,
                     "user_id": 2429,
                     "codigo": "cs-2",
                     "nombre": "Sucursal CS NO ELIMINAR",
                     "telefono": "7777771234",
                     "colonia_id": 34641,
                     "municipio_id": 502,
                     "estado_id": 17,
                     "zona_sucursal_id": 3,
                     "ciudad_cobertura_id": null,
                     "direccion": "Ahuatepec 307",
                     "direccion_numero": "222222",
                     "codigo_postal": "62000",
                     "lon": "-99.228404",
                     "lat": "18.938236",
                     "ancla": 0,
                     "dias": "LUN, MAR, MIE, JUE, VIE",
                     "horario_inicio": "07:00:00",
                     "horario_final": "20:00:00",
                     "24_hrs": 0,
                     "base": 0,
                     "almacen": 0,
                     "created_at": "2018-11-30 13:45:25",
                     "updated_at": "2019-08-04 23:08:12",
                     "deleted_at": null
                   }
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
       
       
* **Code:** 422 Unprocessable Entity <br />
    **Content:** 

        {
          "fecha_inicio": [
            "El campo fecha inicio no es una fecha válida.",
            "El campo fecha inicio debe ser una fecha anterior a fecha fin."
          ],
          "fecha_fin": [
            "El campo fecha fin no es una fecha válida.",
            "El campo fecha fin debe ser una fecha posterior a fecha inicio."
          ],
          "sucursal_id": [
            "El campo sucursal id es inválido."
          ]
          "motivo_id": [
            "El campo motivo id es inválido."
          ]
        }
        
       