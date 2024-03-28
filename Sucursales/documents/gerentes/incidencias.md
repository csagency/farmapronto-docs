## Listado de incidencias (V2)
Regresa el listado de las incidencias

 **URL**

    /api/gerentes/incidencias-v2

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
    'motivo_id' => 'nullable',

**Success Response:**

* **Code:** 200 <br />
  **Content:** 
  
      {
        "incidencias": [
          {
            "id": 1,
            "agente_id": 276,
            "folio": "MT16788",
            "fecha": "2020-07-09 08:32:35",
            "km": "62036",
            "km_evidencia": "uploads\/images\/incidencias\/5f071c765cff2.jpg",
            "motivo_id": 2,
            "vehiculo_id": 37,
            "observaciones": "la cadena está floja ",
            "evidencia": "uploads\/images\/incidencias\/5f071c760c1e7.jpg",
            "proveedor_id": null,
            "tipo_creacion": "api_store",
            "mantenimiento_id": null,
            "created_at": "2019-06-07 16:29:17",
            "updated_at": "2019-06-07 16:29:17",
            "deleted_at": null,
            "deleted_user_id": null,
            "agente_incidencia_id": 16788,
            "archivo_evidencia": null,
            "archivo_ticket": null,
            "archivo_factura": null,
            "num_ticket": null,
            "factura": 0,
            "monto": null,
            "pagado": null,
            "reposicion_datos": 0,
            "litros_cargados": null,
            "litros_aprobados": null,
            "descripcion_sucursal": null,
            "monto_sucursal": null,
            "archivo_evidencia_sucursal": null,
            "razon_improcedencia": null,
            "razon_rechazo": null,
            "rechazo_costos": 0,
            "tiempo_revision": null,
            "tiempo_revision_tipo": null,
            "tiempo_reparacion": null,
            "tiempo_reparacion_tipo": null,
            "incidencia_gasto_id": 16450,
            "estatus_id": 1,
            "user_id": 22588,
            "nombre": "Pendiente",
            "key": "pendiente",
            "id_incidencia": 16788
          },
          {
            "id": 1,
            "agente_id": 292,
            "folio": "GA16791",
            "fecha": "2020-07-09 08:47:17",
            "km": "47009",
            "km_evidencia": "uploads\/images\/incidencias\/\/R9aLSFV5MKStXFom650ZPeq2OW9xOK0RARskNy4n.jpeg",
            "motivo_id": 4,
            "vehiculo_id": 7,
            "observaciones": null,
            "evidencia": null,
            "proveedor_id": null,
            "tipo_creacion": "dashboard_checkin",
            "mantenimiento_id": 49643,
            "created_at": "2019-06-07 16:29:17",
            "updated_at": "2019-06-07 16:29:17",
            "deleted_at": null,
            "deleted_user_id": null,
            "agente_incidencia_id": 16791,
            "archivo_evidencia": "uploads\/images\/incidencias\/gastos\/\/UmdnO8r3SK3JXJkTdP6jCqSVFXFvaUw5j1QPy6c6.jpeg",
            "archivo_ticket": "uploads\/images\/incidencias\/gastos\/\/ut1g6B2lYMDr6yaGZWUCNva30OP9kMzlcDObTivC.jpeg",
            "archivo_factura": "uploads\/images\/incidencias\/gastos\/\/1NdOyhVYfTUO8iZSEJnnl1JbrKlBvxFqF0urcEqu.jpeg",
            "num_ticket": null,
            "factura": 0,
            "monto": 16397,
            "pagado": null,
            "reposicion_datos": 0,
            "litros_cargados": 9.034,
            "litros_aprobados": 9.34,
            "descripcion_sucursal": null,
            "monto_sucursal": null,
            "archivo_evidencia_sucursal": null,
            "razon_improcedencia": null,
            "razon_rechazo": null,
            "rechazo_costos": 0,
            "tiempo_revision": null,
            "tiempo_revision_tipo": null,
            "tiempo_reparacion": null,
            "tiempo_reparacion_tipo": null,
            "incidencia_gasto_id": 16453,
            "estatus_id": 1,
            "user_id": 1608,
            "nombre": "Pendiente",
            "key": "pendiente",
            "id_incidencia": 16791
          },
          {
            "id": 2,
            "agente_id": 288,
            "folio": "GA16793",
            "fecha": "2020-07-09 15:30:56",
            "km": "55032",
            "km_evidencia": "uploads\/images\/incidencias\/\/YUR4g8h8XqnX4qwvHh2h4LkRz53AG5fkctvWloBv.jpeg",
            "motivo_id": 4,
            "vehiculo_id": 36,
            "observaciones": null,
            "evidencia": null,
            "proveedor_id": null,
            "tipo_creacion": "dashboard_checkin",
            "mantenimiento_id": 49649,
            "created_at": "2019-06-07 16:29:17",
            "updated_at": "2019-08-02 17:05:13",
            "deleted_at": null,
            "deleted_user_id": null,
            "agente_incidencia_id": 16793,
            "archivo_evidencia": "uploads\/images\/incidencias\/gastos\/\/bMa0L4KziEdu9zOfCelEqvOLjMrBLdWTr7gK8Xbu.jpeg",
            "archivo_ticket": "uploads\/images\/incidencias\/gastos\/\/9yc9ozjGA8F33r9lbCpnLoYb3SOmPVnxUv1IB3aB.jpeg",
            "archivo_factura": null,
            "num_ticket": null,
            "factura": 0,
            "monto": 5005,
            "pagado": null,
            "reposicion_datos": 0,
            "litros_cargados": 2.735,
            "litros_aprobados": 2.735,
            "descripcion_sucursal": null,
            "monto_sucursal": null,
            "archivo_evidencia_sucursal": null,
            "razon_improcedencia": null,
            "razon_rechazo": null,
            "rechazo_costos": 0,
            "tiempo_revision": null,
            "tiempo_revision_tipo": null,
            "tiempo_reparacion": null,
            "tiempo_reparacion_tipo": null,
            "incidencia_gasto_id": 16455,
            "estatus_id": 2,
            "user_id": 1608,
            "nombre": "Aprobada para cotizar",
            "key": "aprobada",
            "id_incidencia": 16793
          },
          {
            "id": 7,
            "agente_id": 292,
            "folio": "GA16791",
            "fecha": "2020-07-09 08:47:17",
            "km": "47009",
            "km_evidencia": "uploads\/images\/incidencias\/\/R9aLSFV5MKStXFom650ZPeq2OW9xOK0RARskNy4n.jpeg",
            "motivo_id": 4,
            "vehiculo_id": 7,
            "observaciones": null,
            "evidencia": null,
            "proveedor_id": null,
            "tipo_creacion": "dashboard_checkin",
            "mantenimiento_id": 49643,
            "created_at": "2019-06-07 16:29:17",
            "updated_at": "2019-06-07 16:29:17",
            "deleted_at": null,
            "deleted_user_id": null,
            "agente_incidencia_id": 16791,
            "archivo_evidencia": "uploads\/images\/incidencias\/gastos\/\/UmdnO8r3SK3JXJkTdP6jCqSVFXFvaUw5j1QPy6c6.jpeg",
            "archivo_ticket": "uploads\/images\/incidencias\/gastos\/\/ut1g6B2lYMDr6yaGZWUCNva30OP9kMzlcDObTivC.jpeg",
            "archivo_factura": "uploads\/images\/incidencias\/gastos\/\/1NdOyhVYfTUO8iZSEJnnl1JbrKlBvxFqF0urcEqu.jpeg",
            "num_ticket": null,
            "factura": 0,
            "monto": 16397,
            "pagado": null,
            "reposicion_datos": 0,
            "litros_cargados": 9.034,
            "litros_aprobados": 9.34,
            "descripcion_sucursal": null,
            "monto_sucursal": null,
            "archivo_evidencia_sucursal": null,
            "razon_improcedencia": null,
            "razon_rechazo": null,
            "rechazo_costos": 0,
            "tiempo_revision": null,
            "tiempo_revision_tipo": null,
            "tiempo_reparacion": null,
            "tiempo_reparacion_tipo": null,
            "incidencia_gasto_id": 16453,
            "estatus_id": 7,
            "user_id": 24197,
            "nombre": "Confirmada",
            "key": "confirmada",
            "id_incidencia": 16791
          },
        ]
      }

**Error Response:**

  * **Code:** 406 Not Acceptable <br />
  **Content:** 
  
        {
          "error": "Ocurrió un error al conectar con el servidor"
        } 
          
