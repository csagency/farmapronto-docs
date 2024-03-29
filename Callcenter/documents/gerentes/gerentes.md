**Acceso**
----

Metodo de autentificación y acceso con oAuth 2.0
Cada usuario debera solicitar su access token para realizar solicitudes a la API

 **URL**

   `/api/login/custom`

 **Method:**

  `POST`

 **Data Params**
    
     'email'        => 'required|string|email',
     'password'     => 'required|string',
     'tipo_usuario' => 'required|string|in:repartidor',

+ Request (application/json)
    + Body
        + FormParams
    
                [
                    'email' => 'gerente@grupofarmapronto.com',
                    'password' => 'secret',
                    'tipo_usuario' => 'gerente',
                ]

**Success Response:**

* **Code:** 200 <br />
  **Content:** 

        {
            "access_token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsImp0aSI6ImQwOGJhYjU2OWEzMGE3YWZhZWVhMGMzNGExMTUxYjUxMjdiMGY5YmJmNDhhMGJhNzkwNWVjZTVmYjFkMmU2Y2JiMDViNjkyMjFiNGI3NWMyIn0.eyJhdWQiOiIyIiwianRpIjoiZDA4YmFiNTY5YTMwYTdhZmFlZWEwYzM0YTExNTFiNTEyN2IwZjliYmY0OGEwYmE3OTA1ZWNlNWZiMWQyZTZjYmIwNWI2OTIyMWI0Yjc1YzIiLCJpYXQiOjE1NjQwMDc0OTQsIm5iZiI6MTU2NDAwNzQ5NCwiZXhwIjoxNTk1NjI5ODk0LCJzdWIiOiIxNjQiLCJzY29wZXMiOltdfQ.KMA_9TTvzWJrlvPvNNco77CpFHyOU9ZzMk0u7CECU8lgbN-oNwiQX7e1nZRTe8jmgGMoqI0oYyvaWlGogTd6_foP1E3yaOY2sm0b4zVkLHYQXuKh2yeSBt0ZwImWn5E33i5h-1HzcQBmPr7LsP_Ko00GOWgheCA07xa1nuzUYNDZVpqdd86l5Yv7k4zI55fBRp9WrjDF4dzPW_hOk5Nf4gy8RLxgdELUM6WnIkQCpv3aXaMj8jq2kF-4ufWrw7j0TxX_O2-vWVRCsFnVSAG0hSeiNNZPrkqp8hS66gkof7YbMDhhkva_cVlVcJX8Vkhnw9ix8i7XVNDgfGsARbN5OJAAmiGW_hKoFtVgyTTEGM0j9omR3OwhC3XAIQQmSA94315tPoZqFswpC-XdsXe4eK6VlR1GAS8kXIkVXwNKYt9cpra9GKGf4wdLJWC2LakrQGK9RjY_DobSnPSNHvITVi0KWW84lKnSskVECYR2jLdvDPNun-6jNFwuoxSOnht4zI1mh6QFav_vNuYvKBCrHWo--D2ezWJOKRywGgma3jfHHEf-F8aVbTjvOdTSA0KVF1niA1VZSpHhg2AVUGHU6JtRxLNy6kvehtTsxLZWF7DzWVikXCfSlffr6RViwSdHdh2oaNcCk-_pNojH_GVc6XJd_SThfMfDnW4S2dTqU-s",
            "token_type": "Bearer",
            "refresh_token": "",
            "expires_at": "2019-07-31 17:31:34"
        }
            

**Error Response:**

  * **Code:** 401 Unauthorized <br />
    **Content:** 
  
          {
            "error": "Unauthorized."
          }
    
                
**Logout**
----

Cerrar sesión y expira el token de acceso activo

**Headers**
 
    Authorization: Bearer access_token
    Accept: application/json

**Requesting Tokens [DELETE /api/logout]**

+ Response 200 (application/json) Ejemplo:
    + Body

            {
            	"token_deleted": "Token de acceso ha expirado"
            }
  
 