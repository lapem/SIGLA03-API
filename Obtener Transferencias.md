**Obtener transferencias**
----
  Regresa todas las transferencias realizadas por la empresa en formato json. 

* **URL**

  *baseUrl*/api/transferencia/lista/:id

* **Method:**

  `GET`
  
*  **URL Params**

   **Required:** Identificador de idEmpresa, que es requerido pero está obsoleto, es decir no tiene efecto sobre el resultado

   `id=[integer]`

* **Data Params** (header)

````
Accept: application/json
Content-Type: application/json
Authorization: Bearer 1CIPn1wHHhhyas.....
````

* **Success Response:**

  * **Code:** 200 <br />
    **Content:** `[
    {
        "Folio": 000000,
        "FechaHora": "2018-03-15T12:26:57",
        "StatusTransferencia": "ENVIADA",
        "TipoTransferencia": "TERCERO",
        "Destino": "EMPRESA S.A. DE C.V. - FACTURA: 9999"
    }]`
 
* **Error Response:**

  * **Code:** 500 Internal Server Error <br />

  OR

  * **Code:** 401 UNAUTHORIZED <br />
    **Content:** `{ error : "You are unauthorized to make this request." }`

* **Ejemplo:**

  ```javascript
    $.ajax({
      url: "/transferencia/lista/0",
      dataType: "json",
      type : "GET",
      success : function(r) {
        console.log(r);
      }
    });
  ```
