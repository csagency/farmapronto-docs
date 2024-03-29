**Listado de recetas del cliente**
----
  Recetas del cliente
   **URL**
  
    /api-v2/clientes/recetas
  
   **Method:**
  
    `GET`
      
   **Headers**
    
       Authorization: Bearer access_token
       Accept: application/json
      
 **Success Response:**
  
   * **Code:** 200 <br />
      **Content:** 
      
          {
          	 "recetas": [
                 {
                   "id": 18472,
                   "pedido_id": 109455,
                   "producto_id": 64432,
                   "user_id": 13829,
                   "tipo": "receta",
                   "archivo": null,
                   "motivo": null,
                   "aceptado": 0,
                   "created_at": "2020-03-18 12:46:32",
                   "updated_at": "2020-03-18 12:46:32",
                   "fisico": 0,
                   "estatus": "pendiente",
                   "prescrypto_prescription_id": null,
                   "producto": {
                     "id": 64432,
                     "farmapronto_id": "036570",
                     "sku": "7502001169296",
                     "nombre": "AMOXICILINA \/BROMHEXINA 250 MG\/8 MG SUSP 60 ML (ACROXIL-C)",
                     "descripcion": "",
                     "categoria": "ANTIBIOTICOS",
                     "categoria_id": 0,
                     "laboratorio": "SONSPHARMA",
                     "receta": 1,
                     "clave": "SUJETO A DISPONIBILIDAD",
                     "tipo": 8,
                     "activos": "AMOXICILINA \/ BROMHEXINA",
                     "keywords": "",
                     "destacado": 0,
                     "archivo": null,
                     "created_at": "2019-01-15 05:03:35",
                     "updated_at": "2020-03-18 06:01:21",
                     "activo": 1,
                     "despliega": 1
                   }
                 }
             ]
          }
              
  
   * **Code:** 401 Unauthorized <br />
      **Content:** 
      
          {
            "error": "Unauthenticated."
          }
          
     
      
      
**Mostrar receta por id**
----
  Recetas por id
   **URL**
  
    /api-v2/clientes/recetas/{IDReceta}?includes[]=producto
  
   **Method:**
  
    `GET`
      
   **Headers**
    
       Authorization: Bearer access_token
       Accept: application/json
      
 **Success Response:**
  
   * **Code:** 200 <br />
      **Content:** 
      
          {
             "receta": {
                "id": 18472,
                "pedido_id": 109455,
                "producto_id": 64432,
                "user_id": 13829,
                "tipo": "receta",
                "archivo": null,
                "motivo": null,
                "aceptado": 0,
                "created_at": "2020-03-18 12:46:32",
                "updated_at": "2020-03-18 12:46:32",
                "fisico": 0,
                "estatus": "pendiente",
                "prescrypto_prescription_id": null,
                "producto": {
                  "id": 64432,
                  "farmapronto_id": "036570",
                  "sku": "7502001169296",
                  "nombre": "AMOXICILINA \/BROMHEXINA 250 MG\/8 MG SUSP 60 ML (ACROXIL-C)",
                  "descripcion": "",
                  "categoria": "ANTIBIOTICOS",
                  "categoria_id": 0,
                  "laboratorio": "SONSPHARMA",
                  "receta": 1,
                  "clave": "SUJETO A DISPONIBILIDAD",
                  "tipo": 8,
                  "activos": "AMOXICILINA \/ BROMHEXINA",
                  "keywords": "",
                  "destacado": 0,
                  "archivo": null,
                  "created_at": "2019-01-15 05:03:35",
                  "updated_at": "2020-03-18 06:01:21",
                  "activo": 1,
                  "despliega": 1
                }
             }
          }
              
  
   * **Code:** 401 Unauthorized <br />
      **Content:** 
      
          {
            "error": "Unauthenticated."
          }
         
        
        
     
     
**Listado de recetas del cliente por pedido **
----
  Recetas del cliente
   **URL**
  
    api-v2/clientes/recetas/pedido/{IDPedido}?includes[]=producto&includes[]=pedido
    
   **Method:**
  
    `GET`
      
   **Headers**
    
       Authorization: Bearer access_token
       Accept: application/json
      
 **Success Response:**
  
   * **Code:** 200 <br />
      **Content:** 
      
          {
             "recetas": [
                 {
                   "id": 18472,
                   "pedido_id": 109455,
                   "producto_id": 64432,
                   "user_id": 13829,
                   "tipo": "receta",
                   "archivo": null,
                   "motivo": null,
                   "aceptado": 0,
                   "created_at": "2020-03-18 12:46:32",
                   "updated_at": "2020-03-18 12:46:32",
                   "fisico": 0,
                   "estatus": "pendiente",
                   "prescrypto_prescription_id": null,
                   "producto": {
                     "id": 64432,
                     "farmapronto_id": "036570",
                     "sku": "7502001169296",
                     "nombre": "AMOXICILINA \/BROMHEXINA 250 MG\/8 MG SUSP 60 ML (ACROXIL-C)",
                     "descripcion": "",
                     "categoria": "ANTIBIOTICOS",
                     "categoria_id": 0,
                     "laboratorio": "SONSPHARMA",
                     "receta": 1,
                     "clave": "SUJETO A DISPONIBILIDAD",
                     "tipo": 8,
                     "activos": "AMOXICILINA \/ BROMHEXINA",
                     "keywords": "",
                     "destacado": 0,
                     "archivo": null,
                     "created_at": "2019-01-15 05:03:35",
                     "updated_at": "2020-03-18 06:01:21",
                     "activo": 1,
                     "despliega": 1
                   },
                   "pedido": {
                     "id": 109455,
                     "user_id": 13829,
                     "cliente_direccion_id": 89163,
                     "ciudad_cobertura_id": null,
                     "asistencia": 0,
                     "alerta_cliente": 0,
                     "folio": "ERP0109455",
                     "erp": 1,
                     "usuario_erp": "NCULEBRO",
                     "codigo_confirmacion": null,
                     "visto_callcenter": 1,
                     "programado_at": null,
                     "taxi": 0,
                     "clon": 0,
                     "pedidos_juntos": "109420,109404,109422",
                     "cancelado_motivo": null,
                     "cancelado_user_id": null,
                     "observaciones": null,
                     "liberado": null,
                     "created_at": "2020-03-18 12:46:31",
                     "updated_at": "2020-03-19 17:11:54",
                     "deleted_at": null,
                     "origen": null
                   }
                 }
             ]
          }
              
  
   * **Code:** 401 Unauthorized <br />
      **Content:** 
      
          {
            "error": "Unauthenticated."
          }
          
          
**Agregar imagen de receta por producto **
----

  Agregar imagenes de receta por producto
  
   **URL**
  
    /api-v2/clientes/recetas
  
   **Method:**
  
    `POST`
      
   **Headers**
    
       Authorization: Bearer access_token
       Accept: application/json
       Content-Type: multipart/form-data
      
      
**Data Params**

 ***Required:***
    
    'producto_id' => 'required|exists:productos,id',
    'archivo' => 'required|image,
    
      
 **Success Response:**
  
   * **Code:** 200 <br />
      **Content:** 
      
          {
          	"user": {
          		"id": 131,
          		"name": "Erick 2",
          		"last_name": "OOOO",
          		"second_last_name": "A",
          		"telephone": "527773274199",
          		"email": "erick.dbrito@gmail.com",
          		"player_id": "123123123",
          		"activo": 1,
          		"created_at": "2017-07-18 17:59:03",
          		"updated_at": "2017-07-19 18:54:23",
          		"deleted_at": null
          	},
          	"receta": {
          		"producto_id": "1",
          		"tipo": "receta",
          		"archivo": "http:\/\/farmapronto.dev\/uploads\/recetas\/DXPIaQjEpfvgy0Xr3K0E7u7GBiaZTEYQoUVujqus.png",
          		"fisico": false,
          		"estatus": "pendiente",
          		"user_id": 131,
          		"updated_at": "2017-07-20 13:04:55",
          		"created_at": "2017-07-20 13:04:55",
          		"id": 21,
          		"producto": {
          			"id": 1,
          			"farmapronto_id": "000001",
          			"sku": "736085400892",
          			"nombre": "3-A OFTENO 1MG GTS 5ML",
          			"descripcion": "3-A OFTENO 1MG GTS 5ML",
          			"categoria": "ORGANOS DE LOS SENTIDOS",
          			"categoria_id": 0,
          			"laboratorio": "Bayer",
          			"receta": 0,
          			"clave": "Disponible",
          			"tipo": 38,
          			"activos": "DICLOFENACO SODICO",
          			"destacado": 0,
          			"archivo": null,
          			"created_at": "2017-03-16 17:49:19",
          			"updated_at": "2017-07-14 13:02:30",
          			"activo": 1
          		}
          	}
          }
  
   **Error Responses:**
    * **Code:** 422 Unprocessable Entity <br />
       **Content:** 
       
          {
          	  "producto_id": [
                "El campo producto id es obligatorio."
              ],
              "archivo": [
                "El campo archivo es obligatorio."
              ]
          }
              
  
   * **Code:** 401 Unauthorized <br />
      **Content:** 
      
          {
            "error": "Unauthenticated."
          }
        