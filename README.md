# SIGLA-API
Implementación del Web API de SIGLA LAPEM

Esta aplicación, es una API bajo el protocolo http, mejor conocida como WEB API. El presente documento, está creado especialmente en la realización de transferencias a Terceros.

A continuación, se describen los principales métodos del API de SIGLA03 para realizar una transferencia de materiales a terceros.

## Implementación del API

1. Base url 
	https://lapem.cfe.gob.mx/develSIGLA03API/
	
2. Metodos. Las principales funciones de la web api de SIGLA03, se enlistan a continuación. En cada una de las rutas de este webapi, se incluye una breve descripción y un ejemplo de su uso. Se detallan los datos de entrada y salida:

	1. [Autenticación](https://github.com/lapem/SIGLA03-API/blob/master/Autenticacion.md).
	Se detalla la forma en que debes autenticarte y obtener un token para invocar el resto de los métodos de la web api.
	2. [Obtener Saldo Material](https://github.com/lapem/SIGLA03-API/blob/master/SaldoMaterial.md).
	La primer operación que se deberá realizar es la consulta del material disponible, ya sea por aviso de prueba o por descripción.
	3. [Obtener Numeros de Serie](https://github.com/lapem/SIGLA03-API/blob/master/Obtener%20Series.md).
	El segundo paso es la consulta de los números de serie a transferir, esto solo es necesario si los materiales a transferir son identificador por número de serie. Si los materiales están identificados por lote de fabricación, no es necesario realizar este paso.
	4. [Obtener el cliente destino](https://github.com/lapem/SIGLA03-API/blob/master/Obtener%20Cliente.md).
	Es necesario para completar la transferencia, indicar el cliente destino de la transferencia, el cliente es seleccionado de todos los clientes de la empresa filtrando por un criterio de búsqueda especificado.
	5. [Registrar Transferencia](https://github.com/lapem/SIGLA03-API/blob/master/Transferencia%20Tercero.md).
	En este método de la API, se establece el origen y destino de la transferencia, la cantidad de material, la factura y en su caso los números de serie de los materiales o equipos. El método devolverá el folio de la transferencia.
	6. [Consulta de transferencia](https://github.com/lapem/SIGLA03-API/blob/master/Obtener%20Detalle%20Transferencia.md).
	Si se desea verificar que el movimiento ha sido correcto, basta con utilizar este método del API, en la respuesta se obtendrá toda la información de dicha transferencia.
	7. [Agregar Cliente](https://github.com/lapem/SIGLA03-API/blob/master/Registra%20cliente.md).
	Adicionalmente es posible agregar un cliente nuevo a la lista de clientes de la empresa. Esto es muy útil si ya tenemos todo listo para la transferencia, pero se trata de un cliente nuevo el cual tal vez no tenga un alias.

Para mayor información, por favor póngase en contacto con la Oficina de Ingeniería de Software del LAPEM [carlos.solis@cfe.mx](mailto:carlos.solis@cfe.mx)
