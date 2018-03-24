**Registra una transferencia a tercero**
----
  Registra una transferencia a otra empresa en la modalidad **Transferencia tercero**. El cliente debe contar con un Alias en la BD de SIGLA03 para la empresa que va a realizar la transferencia.7
  El API devuelve el folio de la transferencia.

* **URL**

  *baseUrl*/api/transferenciatercero/

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
        "FechaHora" = "02/02/2018",
        "NombreEmpresa":"EMPRESA S.A. DE C.V."
        "EmpresaDestino":"99999",
                  "EmpresaOrigen" = "00000",
                  "User" = "11111",
                  "StatusTransferencia" = "ENVIADA",
                  "Factura"="factura",
                  "TipoTransferencia" = "TERCERO",
        "Material": {
          "Aviso":{"Unidad": "pz"}
          "AvisoPrueba":"22222"
          "Cantidad":"2"
          "NumerosSerie":
            {"IdSerie": "0", "NoSerie": "123456", "AvisoPrueba": "999999", "CveEmpresa": "0"}
            {"IdSerie": "0", "NoSerie": "234567", "AvisoPrueba": "888888", "CveEmpresa": "0"}
          }
        }
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
      url: "baseurl/api/transferenciatercero/",
      dataType: "json",
      data: {				
        "FechaHora" = "02/02/2018",
        "NombreEmpresa":"EMPRESA S.A. DE C.V."
        "EmpresaDestino":"99999",
                  "EmpresaOrigen" = "00000",
                  "User" = "11111",
                  "StatusTransferencia" = "ENVIADA",
                  "Factura"="factura",
                  "TipoTransferencia" = "TERCERO",
        "Material": {
          "Aviso":{"Unidad": "pz"}
          "AvisoPrueba":"22222"
          "Cantidad":"2"
          "NumerosSerie":
            {"IdSerie": "0", "NoSerie": "123456", "AvisoPrueba": "999999", "CveEmpresa": "0"}
            {"IdSerie": "0", "NoSerie": "234567", "AvisoPrueba": "888888", "CveEmpresa": "0"}
          }
        }
      }
      type : "POST",
      success : function(r) {
        console.log(r);
      }
    });
  ```
