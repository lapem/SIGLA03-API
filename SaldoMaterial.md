**Obtener Saldo Material**
----
  Regresa el material disponible de la empresas por los distintos avisos de prueba en el SIGLA03 en formato json. 
  El método tiene una forma de filtrar por el aviso de prueba o su descripción.

* **URL**

  *baseUrl*/api/saldomaterial/ajax/1

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
Debe indicarse un criterio de búsqueda para devolver una lista de materiales disponibles.
````
{ "Descripcion": "poste" }
````

* **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    `
    [
    {
            "IDSaldo": 000000,
            "NoAviso": 111111,
            "Saldo": 115,
            "CveEmpresa": 00000,
            "Descripcion": "Descripcion del Material en el aviso de prueba",
            "Tipo": "FALO",
            "Unidad": "pz",
            "FechaLiberacion": "2018-02-12T00:00:00"
        }
    ]
    `
 
* **Error Response:**

  * **Code:** 500 Internal Server Error <br />

  OR

  * **Code:** 401 UNAUTHORIZED <br />
    **Content:** `{ error : "You are unauthorized to make this request." }`

* **Ejemplo:**

  ```javascript
    $.ajax({
      url: "baseUrl/saldomaterial/ajax/1",
      dataType: "json",
      data: { "Descripcion": "poste" },
      type : "POST",
      success : function(r) {
        console.log(r);
      }
    });
  ```
