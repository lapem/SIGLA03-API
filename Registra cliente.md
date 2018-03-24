**Registrar cliente**
----
  Registra el cliente de una empresa con un Alias en la BD de SIGLA03 para posteriormente realizar una transferencia por el Alias a dicho cliente. 

* **URL**

  *baseUrl*/api/cliente/

* **Method:**

  `POST`
  
*  **URL Params**

  Ninguno

* **Data Params** (header)

````
Accept: application/json
Content-Type: application/json
Authorization: Bearer 1CIPn1wHHhhyas.....
````

* **Data Params** (body)
````
{
	"AliasCliente": "Alias Empresa",
	"EmailCliente": "alias@hotmail.com",
	"EstatusCliente": "ACTIVADO",
	"TelefonoCliente": "5566556655",
	"CveSerlaCliente": "999999",
	"CveSerlaProveedor": "000000"
}
````

* **Success Response:** Devuelve un identificador folio del número de cliente registrado como Alias en la BD de SIGLA03

  * **Code:** 200 <br />
    **Content:** `99999`
 
* **Error Response:**

  * **Code:** 500 Internal Server Error <br />

  OR

  * **Code:** 401 UNAUTHORIZED <br />
    **Content:** `{ error : "You are unauthorized to make this request." }`

* **Ejemplo:**

  ```javascript
    $.ajax({
      url: "baseurl/api/cliente/",
      dataType: "json",
      data: {{
            "AliasCliente": "Alias Empresa",
            "EmailCliente": "alias@hotmail.com",
            "EstatusCliente": "ACTIVADO",
            "TelefonoCliente": "5566556655",
            "CveSerlaCliente": "99999",
            "CveSerlaProveedor": "00000"
          }}
      type : "POST",
      success : function(r) {
        console.log(r);
      }
    });
  ```
