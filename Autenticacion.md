**Autenticación**
----
  Para poder utilizar los métodos de la API de SIGLA, es necesario estar autenticado.
  El API de SIGLA cuenta con una forma de autenticación basada en tokens y el estandar OAuth.

* **URL**

  /baseURL/token

* **Method:**

  `POST`
  
*  **URL Params**

    Ninguno

*  **Data Params Header**

   **Requerido:**
 
   `Accept = application/json`
   `ContentType = application/www-form-urlencoded`

*  **Data Params Body**

   **Requerido:**
 
   `grant_type = password`
   `username = <usuario>`
   `password = <password>`

* **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    ````
    {
      "access_token": "iyqwtertqweiuyrtqwiefgkajsdkfdvjM-plnPar90iVZRYkGwkN8_jSEsmlALR0bcKakSkPVnXwVbFiTvkGrcevwjjv_6_4tIysf03csv83jzBWBakfWwPP_2CYzz4OOBXaTgwS61ZFBFQ939OTPqWRfb0ZfahMOwpss-d6QlXR5xIWia6n17vYgxc1IacO5kX5Xa0NkwsbpBLTPqxgjNUdMeYERbZwX66AhUXU4bHOeD05XIJRaTP2YH7rlcS-akz2_3Eb9Ne6N04XHVuo9V_rkOA83w6f9_9RLXvhPcLdYymCRFQ_IqWE8mF3tZc5x5hAFVxBuTMC7UoSSj2dcu90hmvOABxW58UrnzWqiAbuP5eyLxYdtvrRedmwXGmrv_vnGRlnXcgQCKjR4LW0fX45ZJRE8Ux8iLqQw4DYOY7YeS_Y65odWYWONquWvP8i48Q",
      "token_type": "bearer",
      "expires_in": 86399
    }
    ````
 
* **Error Response:**

  * **Code:** 400 BAD REQUEST <br />
    **Content:** 
    ````
    {
      "error": "invalid_grant",
      "error_description": "El usuario o el password son incorrectos."
    }
    ````
