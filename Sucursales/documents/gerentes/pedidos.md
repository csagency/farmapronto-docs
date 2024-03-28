## Listado de pedidos sin repartidor (V2)
Regresa el listado de los pedidos sin repartidor

 **URL**

    /api/gerentes/pedidos/sin_repartidor-v2

 **Method:**

  `GET`
  
 **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data
     
     
 **Data Params**
    
    'fecha_inicio' => 'nullable|date|before_or_equal:fecha_fin',
    'fecha_fin' => 'nullable|date|after_or_equal:fecha_inicio',
    'sucursal_id' => 'nullable',
    
**Success Response:**

* **Code:** 200 <br />
  **Content:** 
  
      {
        "pedidos": [
          {
            "id": 132115,
            "user_id": 23058,
            "cliente_direccion_id": 106921,
            "ciudad_cobertura_id": null,
            "asistencia": 0,
            "alerta_cliente": 0,
            "folio": "ERP0135267",
            "erp": 1,
            "traspaso": 0,
            "usuario_erp": "INTELISIS",
            "codigo_confirmacion": null,
            "visto_callcenter": 0,
            "programado_at": null,
            "taxi": 0,
            "clon": 0,
            "pedidos_juntos": null,
            "cancelado_motivo": null,
            "cancelado_user_id": null,
            "observaciones": null,
            "liberado": null,
            "created_at": "2020-07-09 19:24:04",
            "updated_at": "2020-07-09 19:25:09",
            "deleted_at": null,
            "origen": null,
            "pedido_id": 135267,
            "paso": "recibido",
            "nomicash": null,
            "sucursal_id": 85,
            "agente_id": null,
            "vehiculo_id": null,
            "repartidor_id": null,
            "placas": null,
            "tipo_envio": "domicilio_propios",
            "costo_envio": null,
            "codigo_verificacion": "2993",
            "aceptado": 0,
            "delivery_at": null,
            "estimated_at": null,
            "outoftime": 0,
            "outoftime_notified": null,
            "tiempo_recoleccion": null,
            "tiempo_entrega": null,
            "taxi_cp_id": null,
            "km_entrega": null,
            "km_anterior": null,
            "lat": "18.909447",
            "lon": "-98.9515354",
            "en_ruta": 0,
            "en_ruta_at": null,
            "id_pedido": 135267
          },
          {
            "id": 132114,
            "user_id": 23058,
            "cliente_direccion_id": 106920,
            "ciudad_cobertura_id": null,
            "asistencia": 0,
            "alerta_cliente": 0,
            "folio": "ERP0135266",
            "erp": 1,
            "traspaso": 0,
            "usuario_erp": "INTELISIS",
            "codigo_confirmacion": null,
            "visto_callcenter": 0,
            "programado_at": null,
            "taxi": 0,
            "clon": 0,
            "pedidos_juntos": null,
            "cancelado_motivo": null,
            "cancelado_user_id": null,
            "observaciones": null,
            "liberado": null,
            "created_at": "2020-07-09 19:22:20",
            "updated_at": "2020-07-09 19:25:09",
            "deleted_at": null,
            "origen": null,
            "pedido_id": 135266,
            "paso": "recibido",
            "nomicash": null,
            "sucursal_id": 85,
            "agente_id": null,
            "vehiculo_id": null,
            "repartidor_id": null,
            "placas": null,
            "tipo_envio": "domicilio_propios",
            "costo_envio": null,
            "codigo_verificacion": "5530",
            "aceptado": 0,
            "delivery_at": null,
            "estimated_at": null,
            "outoftime": 0,
            "outoftime_notified": null,
            "tiempo_recoleccion": null,
            "tiempo_entrega": null,
            "taxi_cp_id": null,
            "km_entrega": null,
            "km_anterior": null,
            "lat": "18.909447",
            "lon": "-98.9515354",
            "en_ruta": 0,
            "en_ruta_at": null,
            "id_pedido": 135266
          },
          {
            "id": 132117,
            "user_id": 13814,
            "cliente_direccion_id": 106919,
            "ciudad_cobertura_id": null,
            "asistencia": 0,
            "alerta_cliente": 0,
            "folio": "ERP0135265",
            "erp": 1,
            "traspaso": 0,
            "usuario_erp": "MROSETTE",
            "codigo_confirmacion": null,
            "visto_callcenter": 1,
            "programado_at": null,
            "taxi": 0,
            "clon": 0,
            "pedidos_juntos": null,
            "cancelado_motivo": null,
            "cancelado_user_id": null,
            "observaciones": null,
            "liberado": null,
            "created_at": "2020-07-09 19:30:58",
            "updated_at": "2020-07-09 19:30:58",
            "deleted_at": null,
            "origen": null,
            "pedido_id": 135265,
            "paso": "recibido",
            "nomicash": null,
            "sucursal_id": 18,
            "agente_id": null,
            "vehiculo_id": null,
            "repartidor_id": null,
            "placas": null,
            "tipo_envio": "domicilio_propios",
            "costo_envio": null,
            "codigo_verificacion": "6399",
            "aceptado": 0,
            "delivery_at": null,
            "estimated_at": null,
            "outoftime": 0,
            "outoftime_notified": null,
            "tiempo_recoleccion": null,
            "tiempo_entrega": null,
            "taxi_cp_id": null,
            "km_entrega": null,
            "km_anterior": null,
            "lat": null,
            "lon": null,
            "en_ruta": 0,
            "en_ruta_at": null,
            "id_pedido": 135265
          },
          {
            "id": 132113,
            "user_id": 24927,
            "cliente_direccion_id": 106918,
            "ciudad_cobertura_id": null,
            "asistencia": 0,
            "alerta_cliente": 0,
            "folio": "ERP0135264",
            "erp": 1,
            "traspaso": 0,
            "usuario_erp": "MROSETTE",
            "codigo_confirmacion": null,
            "visto_callcenter": 1,
            "programado_at": null,
            "taxi": 0,
            "clon": 0,
            "pedidos_juntos": null,
            "cancelado_motivo": null,
            "cancelado_user_id": null,
            "observaciones": null,
            "liberado": null,
            "created_at": "2020-07-09 19:21:14",
            "updated_at": "2020-07-09 19:25:09",
            "deleted_at": null,
            "origen": null,
            "pedido_id": 135264,
            "paso": "recibido",
            "nomicash": null,
            "sucursal_id": 62,
            "agente_id": null,
            "vehiculo_id": null,
            "repartidor_id": null,
            "placas": null,
            "tipo_envio": "domicilio_propios",
            "costo_envio": null,
            "codigo_verificacion": "4266",
            "aceptado": 0,
            "delivery_at": null,
            "estimated_at": null,
            "outoftime": 0,
            "outoftime_notified": null,
            "tiempo_recoleccion": null,
            "tiempo_entrega": null,
            "taxi_cp_id": null,
            "km_entrega": null,
            "km_anterior": null,
            "lat": "18.8915694",
            "lon": "-99.1781383",
            "en_ruta": 0,
            "en_ruta_at": null,
            "id_pedido": 135264
          }
        ]
      }

**Error Response:**

  * **Code:** 406 Not Acceptable <br />
  **Content:** 
  
        {
          "error": "Ocurrió un error al conectar con el servidor"
        } 
          

## Listado de pedidos sin surtir (V2)
Regresa el listado de los pedidos sin surtir

 **URL**

    /api/gerentes/pedidos/sin_surtir-v2

 **Method:**

  `GET`
  
 **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data
      
 **Data Params**
    
    'fecha_inicio' => 'nullable|date|before_or_equal:fecha_fin',
    'fecha_fin' => 'nullable|date|after_or_equal:fecha_inicio',
    'sucursal_id' => 'nullable',

**Success Response:**

* **Code:** 200 <br />
  **Content:** 
  
      {
        "pedidos": {
          "4": {
            "id": 1386599,
            "user_id": 24116,
            "cliente_direccion_id": 91034,
            "ciudad_cobertura_id": null,
            "asistencia": 0,
            "alerta_cliente": 0,
            "folio": "APP0135272",
            "erp": 0,
            "traspaso": 0,
            "usuario_erp": "APP",
            "codigo_confirmacion": null,
            "visto_callcenter": 1,
            "programado_at": null,
            "taxi": 0,
            "clon": 0,
            "pedidos_juntos": null,
            "cancelado_motivo": null,
            "cancelado_user_id": null,
            "observaciones": null,
            "liberado": null,
            "created_at": "2020-07-09 19:49:01",
            "updated_at": "2020-07-09 19:49:01",
            "deleted_at": null,
            "origen": null,
            "pedido_id": 135272,
            "paso": "aceptado",
            "nomicash": null,
            "id_pedido": 135272
          }
        }
      }

**Error Response:**

  * **Code:** 406 Not Acceptable <br />
  **Content:** 
  
        {
          "error": "Ocurrió un error al conectar con el servidor"
        } 
          
