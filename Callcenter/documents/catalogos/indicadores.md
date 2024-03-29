## Indicadores de inicio

 **URL**

  /api/indicadores

 **Method:**

  `GET`


 **Headers**

   Accept: application/json
   Content-Type: application/x-www-form-urlencoded



**Success Response:**

* **Code:** 200 <br />
  **Content:**


           {
              "indicadores": {
                "tiempo_promedio": "15 min.",
                "num_pedidos": 7,
                "ranking": 8
              }
           }


* **Code:** 406 <br />
  **Content:**


      {
      	"error": "Usuario sin perfil de sucursal/repartidor"
      }
