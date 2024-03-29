FORMAT: 1A
HOST: https://test-callcenter.appsfarmapronto.com

# Farmapronto API



+ ENDPOINT PRODUCCIÓN

    https://callcenter.appsfarmapronto.com/api/mtcenter/notificacion-tarjetas
    
    

## Notificaciones [/api/mtcenter/notificacion-tarjetas]


### Eviar notificación [POST]

Realiza el envío de push notification al cliente que tenga relacionado 
el número de tarjeta plan de lealtad.

   + form-url-encoded)
     
        numero_tarjeta
        mensaje
     

+ Response 200 (application/json)

    + Headers

            Accept: application/json

    + Body

            {
              "estatus": "Mensaje entregado con éxito",
              "mensaje": "PEDIDO TEST",
              "tarjeta": {
                "id": 802,
                "user_id": 20162,
                "folio": null,
                "descripcion": null,
                "numero_tarjeta": "7773274199",
                "vigente": 1,
                "expiracion": null,
                "created_at": "2019-11-13 11:44:43",
                "updated_at": "2019-11-13 11:44:43",
                "deleted_at": null,
                "tipo_tarjeta_id": null,
                "nip": null,
                "cliente": {
                  "id": 20162,
                  "name": "Erick",
                  "last_name": "Brito",
                  "second_last_name": null,
                  "telephone": "527773274199",
                  "clave": "ERBRSIQ5",
                  "email": "erick.dbrito@gmail.com",
                  "player_id": "de69c47d-67a4-4c58-8a34-2140577da7b4",
                  "tipo_usuario": null,
                  "activo": 1,
                  "baja": 0,
                  "fb_id": null,
                  "webhook_url": null,
                  "created_at": "2019-11-13 10:59:46",
                  "updated_at": "2019-11-13 10:59:46",
                  "deleted_at": null,
                  "last_login": null
                }
              }
            }
        
    
+ Response 404 (application/json)
   
   + Body
   
   
            {
              "error": "Model not found."
            }
    

+ Response 422 (application/json)


   + Body

       
            {
              "numero_tarjeta": [
                "El campo numero tarjeta es obligatorio."
              ],
              "mensaje": [
                "El campo mensaje es obligatorio."
              ]
            }