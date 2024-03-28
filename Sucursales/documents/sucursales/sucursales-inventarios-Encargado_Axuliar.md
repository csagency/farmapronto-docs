## Obtener los insumos de la sucursal
Regresa el listado de las temperaturas registradas por la sucursal

 **URL**

    api/insumos/registrados/sucursal/{id_sucursal}
    
 **Method:**

  `GET`
  
 **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data
      X-Requested-With: XMLHttpRequest
      
 **Data Params**
    
     
 **URL Params**

       - sucursal_id":  'uid de la sucursal'
       
**Success Response:**

* **Code:** 200 <br />
  **Content:** 
  
      {
        "sucursal_id": "3",
        "insumos_sucursal": [
          {
            "id": 5,
            "nombre": "Test1"
          },
          {
            "id": 9,
            "nombre": "papel de baño"
          },
          {
            "id": 10,
            "nombre": "Pastillas de baño"
          },
          {
            "id": 11,
            "nombre": "Escobas"
          }
        ]
      }

**Error Response:**

  * **Code:** 401 Unauthorized <br />
    **Content:** 
  
          {
            "error": "Unauthenticated."
          }
          
          
## Registrar el inventario
Regresa un mensaje si es que fue exitoso el registro del inventario

 **URL**

    api/insumos/store/sucursal
    
 **Method:**

  `POST`
  
 **Headers**
   
      Authorization: Bearer access_token
      Accept: application/json
      Content-Type: multipart/form-data
      X-Requested-With: XMLHttpRequest
      
 **Data Params**

    - sucursal_id: 'Es el id de la sucursal'
 	- saltar_agotado: 'Es un booleano que su valor tiene que ser false 
 	    a menos que que quieran saltar el error de agotado',
 	- saltar_inconsistencia: 'Es un booleano que su valor tiene que ser false 
        a menos que que quieran saltar el error de inconsistencia',
    - insumos_sucursal[]: 'Son los insumos obtenidos y enviados con la nueva cantidad ' 
 
 **JSON params**
 
    {
      "sucursal_id": "3",
    	"saltar_agotado": true,
    	"saltar_inconsistencia": false,
      "insumos_sucursal": [
        {
          "id": 5,
          "nombre": "Test1",
    			"cantidad": 0
        },
        {
          "id": 9,
          "nombre": "papel de baño",
    			"cantidad": 4
        },
        {
          "id": 10,
          "nombre": "Pastillas de baño",
    			"cantidad": 2
        },
        {
          "id": 11,
          "nombre": "Escobas",
    			"cantidad": 2
        }
      ]
    }
   
 **URL Params**


**Success Response:**

* **Code:** 200 <br />
  **Content:** 
  
      {
        "mensaje": "Registro de insumos exitoso"
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
          "message": "The given data was invalid.",
          "errors": {
            "sucursal_id": [
              "El id de la sucursal es requerido"
            ],
            "saltar_agotado": [
              "El campo saltar agotado es obligatorio."
            ],
            "saltar_inconsistencia": [
              "El campo saltar inconsistencia es obligatorio."
            ],
            "insumos_sucursal": [
              "Los insumos son requeridos"
            ]
          }
        }
        
