**Obtener Saldo Material**
----
  Regresa el material disponible de la empresas por los distintos avisos de prueba en el SIGLA03 en formato json. 
  El método tiene una forma de filtrar por el aviso de prueba o su descripción.

* **URL**

  *baseUrl*/api/saldomaterial/ajax/:id

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
* **Data Params** (body)
Debe indicarse un criterio de búsqueda para devolver una lista de materiales disponibles.
````
{ "Descripcion": 764683 }
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
      url: "baseUrl/saldomaterial/ajax/0",
      dataType: "json",
      data: { "Descripcion": 764683 },
      type : "GET",
      success : function(r) {
        console.log(r);
      }
    });
  ```
