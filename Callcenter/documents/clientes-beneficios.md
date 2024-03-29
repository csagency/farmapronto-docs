
**Datos del cliente con beneficios**
----


 **URL**

  /api/clientes/me?includes[]=beneficios.producto

 **Method:**

  `GET`
  

 **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
        
        {
          "cliente": {
            "id": 14846,
            "name": "Erick",
            "last_name": "Brito",
            "second_last_name": null,
            "telephone": "527773274199",
            "clave": "ERBRLQUQ",
            "email": "erick.dbrito@gmail.com",
            "player_id": null,
            "activo": 1,
            "baja": 0,
            "fb_id": null,
            "webhook_url": null,
            "created_at": "2019-07-11 11:44:35",
            "updated_at": "2019-07-11 11:44:35",
            "deleted_at": null,
            "last_login": null,
            "beneficios": [
              {
                "id": 11,
                "user_id": 14846,
                "producto_id": 32217,
                "clientes_beneficios_producto_id": 14,
                "pedido_id": 52359,
                "cotizacion_id": "60186",
                "compras": 2,
                "beneficios": 1,
                "sugeridos": 0,
                "precio_beneficio": 0,
                "precio_fijo": 0,
                "tipo_precio_descuento": "0",
                "canjeado": 0,
                "cancelado": 0,
                "cerrado": "15523340",
                "descripcion": "Transacción aprobada",
                "codigo_error": 0,
                "referencia": "MTCL_BAY",
                "created_at": "2019-07-19 18:18:52",
                "updated_at": "2019-07-25 18:54:49",
                "deleted_at": null,
                "producto": {
                  "id": 32217,
                  "farmapronto_id": "034769",
                  "sku": "7501303442601",
                  "nombre": "QLAIRA TAB C\/28",
                  "descripcion": "",
                  "categoria": "APARATO GENITOURINARIO Y H SEXUALES",
                  "categoria_id": 0,
                  "laboratorio": "BAYER",
                  "receta": 0,
                  "clave": "SUJETO A DISPONIBILIDAD",
                  "tipo": 75,
                  "activos": "VALERATO DE ESTRADIOL",
                  "keywords": "Anticoncepcion, pastillas anticonceptivas, anticonceptivo, sintomas mestruacion, mestruacion, eficacia anticonceptiva, irregularidad menstrual,¶ÿ retencion liquidos, dolor ovario, sandgrado, sangrado abundante,¶ÿ menstruaciones largas, dolor menstrual, estradiol, dienogest, comprimido anticonceptivo, embarazo, anticonceptivo oral combinado, anticonceptivo oral, anticonceptivo natural, cefalea, dolor pelvico, estrogeno natural.",
                  "destacado": 0,
                  "archivo": "uploads\/images\/productos\/7501303442601.png",
                  "created_at": "2017-03-16 17:49:48",
                  "updated_at": "2019-07-04 17:51:00",
                  "activo": 1,
                  "despliega": 1
                }
              }
            ]
          }
        }
        
 
  **URL**
 
   /api/clientes/me?includes[]=beneficiosCanjeados.producto
 
  **Method:**
 
   `GET`
   
   
         
         
         {
           "cliente": {
             "id": 14846,
             "name": "Erick",
             "last_name": "Brito",
             "second_last_name": null,
             "telephone": "527773274199",
             "clave": "ERBRLQUQ",
             "email": "erick.dbrito@gmail.com",
             "player_id": null,
             "activo": 1,
             "baja": 0,
             "fb_id": null,
             "webhook_url": null,
             "created_at": "2019-07-11 11:44:35",
             "updated_at": "2019-07-11 11:44:35",
             "deleted_at": null,
             "last_login": null,
             "beneficios_canjeados": [
               {
                 "id": 11,
                 "user_id": 14846,
                 "producto_id": 32217,
                 "clientes_beneficios_producto_id": 14,
                 "pedido_id": 52359,
                 "cotizacion_id": "60186",
                 "compras": 2,
                 "beneficios": 1,
                 "sugeridos": 0,
                 "precio_beneficio": 0,
                 "precio_fijo": 0,
                 "tipo_precio_descuento": "0",
                 "canjeado": 1,
                 "cancelado": 0,
                 "cerrado": "15523340",
                 "descripcion": "Transacción aprobada",
                 "codigo_error": 0,
                 "referencia": "MTCL_BAY",
                 "created_at": "2019-07-19 18:18:52",
                 "updated_at": "2019-07-25 18:54:49",
                 "deleted_at": null,
                 "producto": {
                   "id": 32217,
                   "farmapronto_id": "034769",
                   "sku": "7501303442601",
                   "nombre": "QLAIRA TAB C\/28",
                   "descripcion": "",
                   "categoria": "APARATO GENITOURINARIO Y H SEXUALES",
                   "categoria_id": 0,
                   "laboratorio": "BAYER",
                   "receta": 0,
                   "clave": "SUJETO A DISPONIBILIDAD",
                   "tipo": 75,
                   "activos": "VALERATO DE ESTRADIOL",
                   "keywords": "Anticoncepcion, pastillas anticonceptivas, anticonceptivo, sintomas mestruacion, mestruacion, eficacia anticonceptiva, irregularidad menstrual,¶ÿ retencion liquidos, dolor ovario, sandgrado, sangrado abundante,¶ÿ menstruaciones largas, dolor menstrual, estradiol, dienogest, comprimido anticonceptivo, embarazo, anticonceptivo oral combinado, anticonceptivo oral, anticonceptivo natural, cefalea, dolor pelvico, estrogeno natural.",
                   "destacado": 0,
                   "archivo": "uploads\/images\/productos\/7501303442601.png",
                   "created_at": "2017-03-16 17:49:48",
                   "updated_at": "2019-07-04 17:51:00",
                   "activo": 1,
                   "despliega": 1
                 }
               }
             ]
           }
         }