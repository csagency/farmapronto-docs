      
**Mostrar indicadores de productividad**
----

Metodo que muestra la productividad de un agente.

 **URL**

   `/api/agentes/indicadores-productividad/show`

 **Method:**

  `GET`

 **Data Params**

    N/A


**Success Response:**

* **Code:** 200 <br />
  **Content:** 

        {
          "agenteProductividad": {
            "dias_trabajados_repartidor": 15,
            "horas_trabajadas_repartidor": 113,
            "mantenimientos_sin_checkout": 0,
            "rendimiento": 27.604189113476707,
            "pedidos_entregados_porcentaje": 95,
            "promedio_confirmacion": "00:09:50",
            "fecha_inicio": "2022-01-01",
            "fecha_fin": "2022-01-31"
          }
        }
            

**Error Response:**

  * **Code:** 401 Unauthorized <br />
    **Content:** 
  
          {
            "error": "Unauthorized."
          }

**Error Response:**

* **Code:** 500 Internal Server Error <br />
  **Content:**

        {
          "message": "Error al mostrar el indicador de productividad del agente"
        }
