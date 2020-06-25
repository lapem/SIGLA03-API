**Obtener Cliente destino de la transferencia**
----
  De este método es importante obtener el dato: **CveSerlaCliente** de la empresa destino de la transferencia
  
  Regresa en formato json la información de todos los clientes registrados por la empresa que tengan el estatus de Activado y que contengan el texto especificado ya sea en la ciudad, el nombre, el alias o el domicilio.

* **URL**

  *baseUrl*/api/cliente/criterio/ajax

* **Método:**

  `POST`
  
*  **Parámetros de la URL**

   Ninguno
 
* **Parametros en el header**

  ````
  Accept: application/json
  Content-Type: application/json
  Authorization: Bearer 1CIPn1wHHhhyas.....
  ````
  * **Parametros en el body**

  ````
  { 
    'AliasCliente': "condumex"
  }
  ````
  
* **Respuesta exitosa:**

  * **Código:** 200 <br />
    **Content:** 
  ````Array 
      [
          {
              "IDCliente": 666666,
              "AliasCliente": "ELECTRO 1",
              "EmailCliente": "mail@yahoo.com.mx",
              "TelefonoCliente": "1212121212",
              "CveSerlaCliente": 99999,
              "InfoMinEmpresa": {
                  "NombreEmpresa": "ELECTRO ...., S.A. DE C.V.",
                  "EstadoEmpresa": "IRAPUATO",
                  "Domicilio": "CALLE ..... CP 99999  , IRAPUATO, GUANAJUATO. TEL. 462 1212121"
              }
          }
      ]
  ````
 
* **Respuesta no exitosa:**

  * **Código:** 500 Internal Server Error <br />

  O

  * **Código:** 401 UNAUTHORIZED <br />
    **Contenido:** `{ error : "No estás autorizado." }`

* **Ejemplo de Llamada:**
Buscará todos los clientes de la empresa que contengan el texto IRAPUATO

  ```javascript
    $.ajax({
      url: "baseUrl/api/cliente/criterio/ajax",
      data:   { "AliasCliente": "IRAPUATO" },
      dataType: "json",
      type : "GET",
      success : function(r) {
        console.log(r);
      }
    });
  ```
