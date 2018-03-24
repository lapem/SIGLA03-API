**Obtener Números de Serie de Aviso de Prueba**
----
  Regresa en formato json los números de serie disponibles del aviso de prueba que se va a transferir.

* **URL**

  *baseUrl*/api/numeroserie/ap/:Aviso/cve/:id

* **Método:**

  `GET`
  
*  **Parámetros de la URL**

   **Required:** Identificador de Aviso de prueba del cual se desea transferir material. El aviso debe tener saldo disponible y los materiales deben identificarse por número de serie
   `Aviso=[integer]`
   
    **Required:** Identificador de idEmpresa, que es requerido pero está obsoleto, es decir no tiene efecto sobre el resultado
   `id=[integer]`
 
* **Parametros en el header**

  ````
  Accept: application/json
  Content-Type: application/json
  Authorization: Bearer 1CIPn1wHHhhyas.....
  ````
  
* **Respuesta exitosa:**

  * **Código:** 200 <br />
    **Content:** 
  ````Array 
    [
      {
          "IdSerie": 0000000,
          "NoSerie": "XXXX-88-XXX",
          "AvisoPrueba": 555555,
          "CveEmpresa": 00000,
          "NoTransferencia": 0
      },
      {
          "IdSerie": 0000000001,
          "NoSerie": "XXXX-99-XXX",
          "AvisoPrueba": 555555,
          "CveEmpresa": 00000,
          "NoTransferencia": 0
      }
    ]
            
  ````
 
* **Respuesta no exitosa:**

  * **Código:** 500 Internal Server Error <br />

  O

  * **Código:** 401 UNAUTHORIZED <br />
    **Contenido:** `{ error : "No estás autorizado." }`

* **Ejemplo de Llamada:**

  ```javascript
    $.ajax({
      url: "baseUrl//api/numeroserie/ap/55555/cve/0",
      dataType: "json",
      type : "GET",
      success : function(r) {
        console.log(r);
      }
    });
  ```
