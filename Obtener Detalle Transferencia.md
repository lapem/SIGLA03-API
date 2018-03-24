**Obtener detalle de transferencia**
----
  Regresa una transferencia con toda la información de detalle en función del folio, el cual fue realizada por la empresa. El formato es json. 

* **URL**

  *baseUrl*/api/transferencia/folio/:id

* **Method:**

  `GET`
  
*  **URL Params**

   **Required:** Folio de la transferencia, que es requerido para ver solo el detalle de la transferencia con el folio indicado

   `folio=[integer]`

* **Data Params** (header)

````
Accept: application/json
Content-Type: application/json
Authorization: Bearer 1CIPn1wHHhhyas.....
````

* **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    ````
    [
      {
      "Folio": 00000,
      "FechaHora": "2018-03-15T12:26:57",
      "User": 000,
      "EmpresaOrigen": 00000,
      "StatusTransferencia": "ENVIADA",
      "Material": [
          {
              "IdDetalle": 9999999,
              "Transferencia": null,
              "AvisoPrueba": 99999,
              "Cantidad": 00,
              "Upis": "S",
              "NumerosSerie": null,
              "Aviso": {
                  "NoAviso": 000000,
                  "Descripcion": "Descripción del Aviso de prueba",
                  "CantidadAprobada": 0,
                  "Unidad": "pz",
                  "Tipo": "FALO",
                  "CveFabricante": 00000,
                  "FechaLiberacion": "2018-02-12T00:00:00"
              }
          }
        ],
        "TipoTransferencia": "TERCERO",
        "Destino": "EMPRESA, S.A. DE C.V. - FACTURA: 9999"
        }]
    ````
 
* **Error Response:**

  * **Code:** 500 Internal Server Error <br />

  OR

  * **Code:** 401 UNAUTHORIZED <br />
    **Content:** `{ error : "You are unauthorized to make this request." }`

* **Ejemplo:**

  ```javascript
    $.ajax({
      url: "/transferencia/folio/0",
      dataType: "json",
      type : "GET",
      success : function(r) {
        console.log(r);
      }
    });
  ```
