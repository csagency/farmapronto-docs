**Promociones**
----

 **Endpoint: https://farmapronto-multiples.csgroup.mx/api/prescrypto/prescriptions**

 **URI**

    /api/prescrypto/prescriptions

**Headers**

    Accept: application/json
    Content-Type: application/json

 **Method:**
  `POST`
 

**Body**


    
     {
         "medications": [
             {  "presentation":"3-A OFTENO 1MG GTS 5ML",
                 "instructions": "Adulto",
                 "sku": 736085400892
             }
         ],
         "extras": "Indicaciones Extra Dude!",
         "patient": {
             "external_patient_file": 100
         }
     } 


     
 **Response 200**   Ok
 
         
         
         
         {
           "prescription": {
             "extras": "Indicaciones Extra Dude!",
             "external_patient_file": 100,
             "updated_at": "2019-11-21 16:48:46",
             "created_at": "2019-11-21 16:48:46",
             "id": 50,
             "medications": [
               {
                 "id": 90,
                 "prescrypto_prescription_id": 50,
                 "producto_id": 1,
                 "presentation": "3-A OFTENO 1MG GTS 5ML",
                 "sku": "736085400892",
                 "instructions": "Adulto",
                 "created_at": "2019-11-21 16:48:46",
                 "updated_at": "2019-11-21 16:48:46"
               }
             ]
           },
           "nomicash_response": {
             "prescription_id": 50,
             "mensaje": "Error al enviar el SMS al empleado",
             "token": "7PPC815tlLfkEAypnHZg79mFx5ejeIsx",
             "fecha_respuesta": "21\/11\/2019 16:48:45",
             "updated_at": "2019-11-21 16:48:46",
             "created_at": "2019-11-21 16:48:46",
             "id": 12
           }
         }



**Response 406** Not Acceptable



    {
      "error": "Formato json invalido"
    }