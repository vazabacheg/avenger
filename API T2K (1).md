

|![](Aspose.Words.125bf686-d791-46b2-8e48-9d876558f272.001.png)|<p></p><p></p><p>RENDIMIENTO E </p><p>INNOVACIÓN DIGITAL</p>|<p></p><p></p><p></p><p>**API**</p>|
| :- | :- | -: |







|<p></p><p>`     `**API - Tok2kit**</p><p>**\_\_\_\_\_**</p><p></p><p>**Objetivo:**  Esta documentación está diseñada para analizar  los servicios públicos de la API de Tok2kit.</p><p></p><p></p>|
| -: |








**ÍNDICE**

[**Generalidades](#_heading=h.822nvjmt35bl)	**3****

[Objetivo alcance](#_heading=h.7bm3er3nqbdi)	3

[**Gestión de Servicio](#_heading=h.ha7xxivpiia4)	**3****

[**Crear Interfaz para la generación de órdenes](#_heading=h.l4ap15n2bw8n)	**4****

[Crear interfaz para Crear Orden](#_heading=h.7qh1x3f87mkx)	4

[Crear interfaz para status de la orden](#_heading=h.820823u7qbvg)	12

[Obtener el listado de órdenes pendientes](#_heading=h.yi4kr556ubtr)	14

[**Crear Interfaz para cliente](#_heading=h.3s10c0xsi7v7)	**15****

[Crear interfaz para cliente nuevo](#_heading=h.oapm3vk7metn)	15

[Modificar el recurso creado](#_heading=h.2yk9emnxb7pt)	18

[**Crear interfaz para crear dirección del cliente](#_heading=h.pgmnsag6p8y9)	**19****

[Crear interfaz una dirección para un cliente](#_heading=h.vn6gvyf3vv6d)	19

[Modificar el recurso creado](#_heading=h.uqsh5sig9wtd)	22

[**Crear interfaz para crear Productos](#_heading=h.29bijecq1n1)	**23****

[Crear interfaz para crear un producto bundle](#_heading=h.1sqnbka1xmoz)	23


1. # **Generalidades**

Los Web Services tipo REST trabajan de forma sincrónica y están diseñados y optimizados para atender las consultas como por ejemplo: ingresar/cancelar una orden, ver las órdenes pendientes, creación de productos, etc.
1. ## ` `**Objetivo alcance**

El objetivo del documento es brindarle al desarrollador una descripción detallada de los métodos disponibles en la API en la gestión de creación de órdenes, productos y clientes para Tok2kit.

Se da una breve explicación de la información que devuelve cada método, los parámetros que acepta, un ejemplo de cómo utilizarlo y la respuesta que devuelve la API. 

Por último, se agregó una lista de errores posibles que pueden ocurrir al utilizar la API.

El alcance general del proyecto abarca:

- Creación de servicios web REST para el registro de órdenes, clientes y productos; y la validación de estos.
1. # **Gestión de Servicio**
**
Este documento está dirigido a quienes necesiten utilizar y probar los métodos web implementados.


|**API\_URL**|https://l5e4cmgl06.execute-api.us-east-1.amazonaws.com/devel/api|
| :-: | :- |

Respecto a la Autenticación, para poder realizar consultas hacia el WS que se pondrá a disposición se debe enviar los siguientes datos:



|**Key**|**Value**|
| :-: | :-: |
|UserName|aeazt6z33t3srm39daua|
|Password|pbiikeiyrmkwshf85vus|
|xapikeys|uEQg3wmfpeafKexaAhY0K52ypXAhjs54865WZlyK|

1. ## **Crear Interfaz para la generación de órdenes**
   1. ### **Crear interfaz para Crear Orden**

A continuación, se detalla la URL y el tipo de llamado que se debe de usar para acceder a la funcionalidad:

|**Ruta**|**Tipo de llamado**|**Datos Leídos de**|
| :-: | :- | :- |
|{{Tok2kitHost}}/public/2/orders|POST|Body|

- **Parámetros de Entrada**

Request esperado:

|<p>**{**</p><p>`  `**"origin":** string**,**</p><p>`  `**"status":** string**,**</p><p>`  `**"weight":** number**,**</p><p>`  `**"channel":** string**,**</p><p>`  `**"coupons": [],**</p><p>`  `**"user\_id": null,**</p><p>`  `**"store\_id":** number**,**</p><p>`  `**"subtotal":**number**,**</p><p>`  `**"order\_ruc": "",**</p><p>`  `**"pos\_store":** string**,**</p><p>`  `**"pre\_order": boolean,**</p><p>`  `**"account\_id":** number**,**</p><p>`  `**"cluster\_id": 1,**</p><p>`  `**"email\_sent": boolean,**</p><p>`  `**"order\_type":** number**,**</p><p>`  `**"pos\_status": "",**</p><p>`  `**"tax\_amount":** number**,**</p><p>`  `**"total\_paid":** number**,**</p><p>`  `**"coupon\_code": "",**</p><p>`  `**"customer\_id": null,**</p><p>`  `**"grand\_total":** number**,**</p><p>`  `**"number\_auth": "",**</p><p>`  `**"wallet\_name": "",**</p><p>`  `**"increment\_id": "",**</p><p>`  `**"total\_change":** number**,**</p><p>`  `**"notifications": boolean,**</p><p>`  `**"order\_comment": "",**</p><p>`  `**"order\_details": [ Array de objetos ],**</p><p>`  `**"tracking\_code": "",**</p><p>`  `**"customer\_email":** string**,**</p><p>`  `**"external\_store": "",**</p><p>`  `**"payment\_method":**string**,**</p><p>`  `**"renueve\_center":** number**,**</p><p>`  `**"tax\_percentage":** number**,**</p><p>`  `**"billing\_address": {  },**</p><p>`  `**"discount\_amount":** number**,**</p><p>`  `**"discount\_coupon":** number**,**</p><p>`  `**"shipping\_amount":** number**,**</p><p>`  `**"shipping\_method":** string**,**</p><p>`  `**"last\_four\_digits": "",**</p><p>`  `**"shipping\_address": { Array de objetos },**</p><p>`  `**"terms\_conditions": boolean,**</p><p>`  `**"customer\_group\_id":**number**,**</p><p>`  `**"customer\_is\_guest": boolean,**</p><p>`  `**"customer\_lastname":** string**,**</p><p>`  `**"delivery\_date\_max": null,**</p><p>`  `**"delivery\_date\_min": null,**</p><p>`  `**"total\_qty\_ordered":** number**,**</p><p>`  `**"customer\_firstname":** string**,**</p><p>`  `**"order\_razon\_social": "",**</p><p>`  `**"external\_code\_store":** number**,**</p><p>`  `**"external\_order\_code":** string**,**</p><p>`  `**"order\_currency\_code": "",**</p><p>`  `**"discount\_description": "",**</p><p>`  `**"pedidos\_ya\_discounts": null,**</p><p>`  `**"sales\_order\_payments": [ Array de objetos ],**</p><p>`  `**"shipping\_is\_delivery": boolean,**</p><p>`  `**"is\_order\_with\_invoice": boolean,**</p><p>`  `**"shipping\_address\_name": "",**</p><p>`  `**"customer\_document\_type":** string**,**</p><p>`  `**"shipping\_address\_coord": "",**</p><p>`  `**"shipping\_address\_place": "",**</p><p>`  `**"user\_commission\_amount":** number**,**</p><p>`  `**"shipping\_address\_number": "",**</p><p>`  `**"store\_commission\_amount":** number**,**</p><p>`  `**"customer\_document\_number":** string**,**</p><p>`  `**"shipping\_discount\_amount":** number**,**</p><p>`  `**"shipping\_address\_reference": ""**</p><p>**}**</p><p></p>|
| :- |
**			

- **Estructura de la descripción de servicio**

|**Campo** |**Detalle**|
| :-: | :-: |
|status|El estado que se enviará la orden en “pending”|
|channel|<p>El canal desde que se envía:</p><p>- call\_center</p><p>- rappi</p><p>- web\_ecommerce</p><p>- pedidosya</p>|
|coupons|Es un array de cupones|
|store\_id |El id código externo de la tienda|
|order ruc|Es el caso de que el cliente desee factura|
|pos\_store|Es el tipo de tienda al que se envía |
|cluster\_id|Es el cluster que se ha configurado, en este caso es el 1 que le pertenece a “Rokys”|
|total\_paid|Es el monto que el usuario ha pagado|
|customer\_id|Es el id del cliente, en caso sea null es porque el cliente es anónimo|
|customer\_email|Datos del cliente|
|payment\_method|<p>El método de pago:</p><p>- pago\_online	</p><p>- efectivo		</p>|
|tax\_percentange|Qué porcentaje de impuestos va a pagar y se calcula con el tax\_amout|
|billing\_addres|Es un objeto que define la dirección para la facturación|
|address\_name|Dirección del delivery o el de recojo en tienda|
|customer\_name|Nombre del cliente|
|customer\_documente\_number|El número de documento del cliente|
|discount\_amount|Descuento manual que se le da a un cliente especial|
|discount\_coupon|Descuento por cupón|
|Shiping\_amount|El monto por el el delivery |
|shiping\_method|<p>Es el método de envío:</p><p>- Delivery</p><p>- Recojo en tienda	</p>|
|customer\_phone|número de celular del cliente|
|order\_razon\_social|En caso de que sea factura se asigna la razon social de la empresa|
|external\_order\_code|El código de la creación external de la orden|
|sales\_order\_payment|El array de objeto del los métodos de pago utilizados en la orden|
|card\_mask|La tarjeta enmascarada |
|four\_digits|Los últimos dígitos de la tarjeta|
|number\_auth|El número de autentificación de pago|
|pay\_method|El método de pago|
**		

`    `**Ejemplo**

|<p>**{**</p><p>`  `**"origin": "web",**</p><p>`  `**"status": "pending",**</p><p>`  `**"weight": 0,**</p><p>`  `**"channel": "web\_ecommerce",**</p><p>`  `**"coupons": [],**</p><p>`  `**"user\_id": null,**</p><p>`  `**"store\_id": 376,**</p><p>`  `**"subtotal": 0,**</p><p>`  `**"order\_ruc": "",**</p><p>`  `**"pos\_store": "FRANQUICIA",**</p><p>`  `**"pre\_order": false,**</p><p>`  `**"account\_id": 0,**</p><p>`  `**"cluster\_id": 1,**</p><p>`  `**"email\_sent": false,**</p><p>`  `**"order\_type": 0,**</p><p>`  `**"pos\_status": "",**</p><p>`  `**"tax\_amount": 0,**</p><p>`  `**"total\_paid": 68.9,**</p><p>`  `**"coupon\_code": "",**</p><p>`  `**"customer\_id": null,**</p><p>`  `**"grand\_total": 0,**</p><p>`  `**"number\_auth": "",**</p><p>`  `**"wallet\_name": "",**</p><p>`  `**"increment\_id": "",**</p><p>`  `**"total\_change": 0,**</p><p>`  `**"notifications": true,**</p><p>`  `**"order\_comment": "",**</p><p>`  `**"order\_details": [**</p><p>`    `**{**</p><p>`      `**"id": 0,**</p><p>`      `**"sku": "",**</p><p>`      `**"name": "OFERTA 1",**</p><p>`      `**"price": 68.9,**</p><p>`      `**"weight": 0,**</p><p>`      `**"comment": "",**</p><p>`      `**"product": null,**</p><p>`      `**"childrens": [],**</p><p>`      `**"parent\_id": null,**</p><p>`      `**"row\_total": 68.9,**</p><p>`      `**"account\_id": null,**</p><p>`      `**"created\_at": "0001-01-01T00:00:00Z",**</p><p>`      `**"deleted\_at": null,**</p><p>`      `**"opt\_change": "",**</p><p>`      `**"row\_weight": 0,**</p><p>`      `**"updated\_at": "0001-01-01T00:00:00Z",**</p><p>`      `**"description": "",**</p><p>`      `**"qty\_ordered": 1,**</p><p>`      `**"modify\_price": false,**</p><p>`      `**"product\_type": "bundle",**</p><p>`      `**"original\_price": 68.9,**</p><p>`      `**"sales\_order\_id": null,**</p><p>`      `**"discount\_amount": 0,**</p><p>`      `**"product\_options": "[]",**</p><p>`      `**"discount\_percent": 0,**</p><p>`      `**"catalog\_product\_id": 0,**</p><p>`      `**"product\_id\_external": "70"**</p><p>`    `**}**</p><p>`  `**],**</p><p>`  `**"tracking\_code": "",**</p><p>`  `**"customer\_email": "yonja2199@gmail.com",**</p><p>`  `**"external\_store": "",**</p><p>`  `**"payment\_method": "pago\_online",**</p><p>`  `**"renueve\_center": 0,**</p><p>`  `**"tax\_percentage": 18,**</p><p>`  `**"billing\_address": {**</p><p>`    `**"ubigeo\_id": 0,**</p><p>`    `**"account\_id": 0,**</p><p>`    `**"address\_name": "Av. La Marina Nº 3191 Urb. Maranga, SAN MIGUEL - LIMA",**</p><p>`    `**"address\_type": "",**</p><p>`    `**"address\_coord": "-12,075,256,-77,098,517",**</p><p>`    `**"address\_place": "",**</p><p>`    `**"customer\_name": "jhon",**</p><p>`    `**"address\_number": "",**</p><p>`    `**"customer\_email": "",**</p><p>`    `**"customer\_phone": "",**</p><p>`    `**"address\_reference": "",**</p><p>`    `**"customer\_lastname": "sánchez",**</p><p>`    `**"customer\_telephone": "",**</p><p>`    `**"customer\_address\_id": null,**</p><p>`    `**"address\_extra\_fields": null,**</p><p>`    `**"customer\_document\_type": "dni",**</p><p>`    `**"customer\_document\_number": "72266242"**</p><p>`  `**},**</p><p>`  `**"discount\_amount": 0,**</p><p>`  `**"discount\_coupon": 0,**</p><p>`  `**"shipping\_amount": 0,**</p><p>`  `**"shipping\_method": "recojo\_en\_tienda",**</p><p>`  `**"last\_four\_digits": "",**</p><p>`  `**"shipping\_address": {**</p><p>`    `**"ubigeo\_id": 0,**</p><p>`    `**"account\_id": 0,**</p><p>`    `**"address\_name": "Av. La Marina Nº 3191 Urb. Maranga, SAN MIGUEL - LIMA",**</p><p>`    `**"address\_type": "",**</p><p>`    `**"address\_coord": "-12,075,256,-77,098,517",**</p><p>`    `**"address\_place": "",**</p><p>`    `**"customer\_name": "",**</p><p>`    `**"address\_number": "",**</p><p>`    `**"customer\_email": "",**</p><p>`    `**"customer\_phone": "949339096",**</p><p>`    `**"address\_reference": "",**</p><p>`    `**"customer\_lastname": "",**</p><p>`    `**"customer\_telephone": "949339096",**</p><p>`    `**"customer\_address\_id": null,**</p><p>`    `**"address\_extra\_fields": null,**</p><p>`    `**"customer\_document\_type": "",**</p><p>`    `**"customer\_document\_number": ""**</p><p>`  `**},**</p><p>`  `**"terms\_conditions": true,**</p><p>`  `**"customer\_group\_id": 1,**</p><p>`  `**"customer\_is\_guest": false,**</p><p>`  `**"customer\_lastname": "sánchez",**</p><p>`  `**"delivery\_date\_max": null,**</p><p>`  `**"delivery\_date\_min": null,**</p><p>`  `**"total\_qty\_ordered": 0,**</p><p>`  `**"customer\_firstname": "jhon",**</p><p>`  `**"order\_razon\_social": "",**</p><p>`  `**"external\_code\_store": 2,**</p><p>`  `**"external\_order\_code": "100234731",**</p><p>`  `**"order\_currency\_code": "",**</p><p>`  `**"discount\_description": "",**</p><p>`  `**"pedidos\_ya\_discounts": null,**</p><p>`  `**"sales\_order\_payments": [**</p><p>`    `**{**</p><p>`      `**"id": 0,**</p><p>`      `**"amount": 68.9,**</p><p>`      `**"card\_mask": "451751\*\*\*\*\*\*0087",**</p><p>`      `**"four\_digits": "0087",**</p><p>`      `**"number\_auth": "994221170112322",**</p><p>`      `**"external\_code": "",**</p><p>`      `**"payment\_method": "pago\_online",**</p><p>`      `**"sales\_order\_id": 0**</p><p>`    `**}**</p><p>`  `**],**</p><p>`  `**"shipping\_is\_delivery": false,**</p><p>`  `**"is\_order\_with\_invoice": false,**</p><p>`  `**"shipping\_address\_name": "",**</p><p>`  `**"customer\_document\_type": "dni",**</p><p>`  `**"shipping\_address\_coord": "",**</p><p>`  `**"shipping\_address\_place": "",**</p><p>`  `**"user\_commission\_amount": 0,**</p><p>`  `**"shipping\_address\_number": "",**</p><p>`  `**"store\_commission\_amount": 0,**</p><p>`  `**"customer\_document\_number": "72266242",**</p><p>`  `**"shipping\_discount\_amount": 0,**</p><p>`  `**"shipping\_address\_reference": ""**</p><p>**}**</p><p></p>|
| :- |

- **Parámetro de salidas**

|**Escenario**|**Code**|**Body**|
| :-: | :-: | :-: |
|Registro exitoso|200|<p>{</p><p>`    `"status": true,</p><p>`    `"error\_code": null,</p><p>`    `"errors": null,</p><p>`    `"data": {</p><p>`        `"id": 58836,</p><p>`        `"account\_id": 2,</p><p>`        `"increment\_id": "200050396",</p><p>`        `"pos": "POLLITO",</p><p>`        `"is\_external": true,</p><p>`        `"data\_sent": "{},</p><p>`        `"data\_result": null,</p><p>`        `"status": "pending",</p><p>`        `"created\_at": "2022-08-17T17:50:14.799929963-05:00",</p><p>`        `"updated\_at": "2022-08-17T17:50:14.799929963-05:00"</p><p>`    `}</p><p>}</p>|
|No se encontró el store id de la tienda|400|<p>{</p><p>`    `"status": **false**,</p><p>`    `"error\_code": 400,</p><p>`    `"errors": {</p><p>`        `"error": "store not found"</p><p>`    `},"data": **null**</p><p>}</p>|
|Solo acepta Rappi o pedidosya|400|<p>{</p><p>`    `"status": **false**,</p><p>`    `"error\_code": 400,</p><p>`    `"errors": {</p><p>`        `"error": "external\_store solo puede ser 'pedidos\_ya'"</p><p>`    `},"data": **null**</p><p>}</p>|
|Error en la sintaxis|400|<p>{</p><p>`    `"status": **false**,</p><p>`    `"error\_code": 400,</p><p>`    `"errors": {</p><p>`        `"error": "bad request"</p><p>`    `},</p><p>`    `"data": **null**</p><p>}</p><p></p>|
1. ### **Crear interfaz para status de la orden**
A continuación, se detalla la URL y el tipo de llamado que se debe de usar para acceder a la funcionalidad:

|Ruta|Tipo de llamado|Datos Leídos de|
| :-: | :- | :- |
|{{Tok2kitHost}}/public/2/order-history|POST|Body|

- **Parámetros de Entrada**

Request esperado:

|<p>**{**</p><p>`    `**"status":"string",**</p><p>`    `**"increment\_id":"string",**</p><p>`    `**"comment":""**</p><p>**}**</p><p></p>|
| :- |


|Campo|Detalle|
| :-: | :-: |
|status|canceled, pending, invoiced,|
|increment\_id|orden de pedido|
|comment|Comentario|

**Ejemplo**

|<p>**{**</p><p>`    `**"status":"canceled",**</p><p>`    `**"increment\_id":"200050371",**</p><p>`    `**"comment":""**</p><p>**}**</p>|
| :- |
- **Parámetro de salidas**

|**Escenario**|**Code**|**Body**|
| :-: | :-: | :-: |
|Registro exitoso|200|<p>{</p><p>`    `"status": **true**,</p><p>`    `"error\_code": **null**,</p><p>`    `"errors": **null**,</p><p>`    `"data": {</p><p>`        `"id": 124325,</p><p>`        `"order\_id": 52587,</p><p>`        `"status": "canceled",</p><p>`        `"comment": "",</p><p>`        `"prev\_status": "can",</p><p>`        `"reason\_id": **null**,</p><p>`        `"user\_id": **null**,</p><p>`        `"created\_at": "2022-08-17T23:41:25.090029737Z",</p><p>`        `"updated\_at": "2022-08-17T23:41:25.090029737Z",</p><p>`        `"deleted\_at": **null**</p><p>`    `}</p><p>}</p><p></p><p></p>|
|Orden no encontrada|400|<p>{</p><p>`    `"status": **false**,</p><p>`    `"error\_code": 400,</p><p>`    `"errors": {</p><p>`        `"error": "order not found"</p><p>`    `},</p><p>`    `"data": **null**</p><p>}</p>|
|Error en la sintaxis|400|<p>{</p><p>`    `"status": **false**,</p><p>`    `"error\_code": 400,</p><p>`    `"errors": {</p><p>`        `"error": "bad request"</p><p>`    `},</p><p>`    `"data": **null**</p><p>}</p>|


1. ### **Obtener el listado de órdenes pendientes**
A continuación, se detalla la URL y el tipo de llamado que se debe de usar para acceder a la funcionalidad:

|**Ruta**|**Tipo de llamado**|**Datos Leídos de**|
| :-: | :- | :- |
|{{Tok2kitHost}}/public/2/order/{POS}|GET||


|**Parámetro**|**Descripción**|
| :-: | :- |
|POS|<p>Se envía como parámetro el tipo de pos que se está consultando:</p><p>- POLLITO</p><p>- FRANQUICIA</p><p>- SYMPHONY</p>|


|**Query**|**Descripción**|
| :-: | :- |
|limit|El límite de las órdenes a listar, por defecto si es que no se envía, el valor a tomar es 100|
|order|El orden del listado por la fecha de creación, estos pueden ser “asc” y “desc”, por defecto es “desc”, si se envía otra cosa, tomará “desc”|

**Nota**: En este caso trabajaremos con “Pollito”, aquí obtendremos todos los órdenes pendiente del pos pollito

- **Parámetro de salidas**

|**Escenario**|**Code**|**Body**|
| :-: | :-: | :-: |
|Registro exitoso|200|<p>{</p><p>`    `"status": **true**,</p><p>`    `"error\_code": **null**,</p><p>`    `"errors": **null**,</p><p>`    `"data": {Array de objetos</p><p>`    `}</p><p>}</p><p></p><p></p>|
|Error al ingresar mal la cuenta|400|<p>{</p><p>`    `"status": **true**,</p><p>`    `"error\_code": **null**,</p><p>`    `"errors": **null**,</p><p>`    `"data": **null**</p><p>}</p><p></p>|



1. ## ` `**Crear Interfaz para cliente**
   1. ### **Crear interfaz para cliente nuevo**
A continuación, se detalla la URL y el tipo de llamado que se debe de usar para acceder a la funcionalidad:

|**Ruta**|**Tipo de llamado**|**Datos Leídos de**|
| :-: | :- | :- |
|{{Tok2kitHost}}/public/2/customer|POST|Body|

- **Parámetros de Entrada**

Request esperado:

|<p>**{**</p><p>`    `**"customer\_name":** string**,**</p><p>`    `**"customer\_last\_name": "**string**",**</p><p>`    `**"customer\_email":**string**,**</p><p>`    `**"notification":**boolean**,**</p><p>`    `**"customer\_group\_id":int,**</p><p>`    `**"phone":**string**,**</p><p>`    `**"customer\_password":"",**</p><p>`    `**"external\_code":""**</p><p>**}**</p>|
| :- |


|Campo|Detalle|
| :-: | :-: |
|customer\_name|Nombre |
|customer\_last\_name|Apellidos|
|customer\_email|correo|
|phone|número móvil|



`                           `**Ejemplo**

|<p>**{**</p><p>`    `**"customer\_name": "Juan",**</p><p>`    `**"customer\_last\_name": "Perez Rodriguez",**</p><p>`    `**"customer\_email":"mail11@mail.com",**</p><p>`    `**"notification":false,**</p><p>`    `**"customer\_group\_id":1,**</p><p>`    `**"phone":"999999999",**</p><p>`    `**"customer\_password":"",**</p><p>`    `**"external\_code":""**</p><p>**}**</p>|
| :- |

- **Parámetro de Salida**

|**Escenario**|**Code**|**Body**|
| :-: | :-: | :-: |
|Registro exitoso|200|<p>{</p><p>`    `"status": **true**,</p><p>`    `"error\_code": **null**,</p><p>`    `"errors": **null**,</p><p>`    `"data": {</p><p>`        `"id": 915221,</p><p>`        `"account\_id": 2,</p><p>`        `"customer\_group\_id": 1,</p><p>`        `"customer\_name": "javier",</p><p>`        `"customer\_lastname": "granda Rodriguez",</p><p>`        `"customer\_email": "mail111@mail.com",</p><p>`        `"customer\_password": "",</p><p>`        `"total\_sales\_invoiced": 0,</p><p>`        `"orders\_qty": 0,</p><p>`        `"calls\_qty": 0,</p><p>`        `"extra\_fields": **null**,</p><p>`        `"is\_active": **true**,</p><p>`        `"user\_id": 0,</p><p>`        `"notification": **true**,</p><p>`        `"phone": "999999999",</p><p>`        `"image": "",</p><p>`        `"external\_code": "",</p><p>`        `"customer\_addresses": **null**,</p><p>`        `"customer\_calls": **null**,</p><p>`        `"customer\_phones": [</p><p>`            `{</p><p>`                `"id": 915219,</p><p>`                `"customer\_id": 915221,</p><p>`                `"country\_code": "",</p><p>`                `"code\_number": "",</p><p>`                `"number": "999999999",</p><p>`                `"main": **false**,</p><p>`                `"have\_whatsapp": **false**,</p><p>`                `"have\_telegram": **false**,</p><p>`                `"created\_at": "2022-08-18T15:25:03.131632725Z",</p><p>`                `"updated\_at": "2022-08-18T15:25:03.131632725Z",</p><p>`                `"deleted\_at": **null**</p><p>`            `}</p><p>`        `],</p><p>`        `"created\_at": "2022-08-18T10:25:03.123487851-05:00",</p><p>`        `"updated\_at": "2022-08-18T10:25:03.123487851-05:00",</p><p>`        `"deleted\_at": **null**</p><p>`    `}</p><p>}</p><p></p><p></p><p></p>|
|Ingreso mal de id del grupo del cliente(custuomer\_gruop\_id)|400|<p>{</p><p>`    `"status": **false**,</p><p>`    `"error\_code": 400,</p><p>`    `"errors": {</p><p>`        `"error": "ERROR: insert or update on table \"customer\" violates foreign key constraint \"fk\_customer\_group\_customers\" (SQLSTATE 23503)"</p><p>`    `},</p><p>`    `"data": **null**</p><p>}</p><p></p>|
|Error en la sintaxis|400|<p>{</p><p>`    `"status": **false**,</p><p>`    `"error\_code": 400,</p><p>`    `"errors": {</p><p>`        `"error": "bad request"</p><p>`    `},</p><p>`    `"data": **null**</p><p>}</p>|

1. ### **Modificar el recurso creado** 
A continuación, se detalla la URL y el tipo de llamado que se debe de usar para acceder a la funcionalidad:

|**Ruta**|**Tipo de llamado**|**Datos Leídos de**|
| :-: | :- | :- |
|{{Tok2kitHost}}/public/2/customer|PUT|Body|

- **Parámetros de Entrada**

Request esperado:

|<p>**{**</p><p>`    `**"customer\_name": string,**</p><p>`    `**"customer\_last\_name": string,**</p><p>`    `**"customer\_email":string,**</p><p>`    `**"notification":string,**</p><p>`    `**"customer\_group\_id":int,**</p><p>`    `**"phone":string,**</p><p>`    `**"external\_code":""**</p><p>**}**</p><p></p>|
| :- |

`			`**Ejemplo:**

|<p>{</p><p>`    `**"customer\_name": "Juan",**</p><p>`    `**"customer\_last\_name": "Perez Rodriguez",**</p><p>`    `**"customer\_email":"mail@mail.com",**</p><p>`    `**"notification":false,**</p><p>`    `**"customer\_group\_id":1,**</p><p>`    `**"phone":"999999999",**</p><p>`    `**"external\_code":""**</p><p>}</p>|
| :- |


1. ## **Crear interfaz para crear dirección del cliente**
   1. ### **Crear interfaz una dirección para un cliente**
A continuación, se detalla la URL y el tipo de llamado que se debe de usar para acceder a la funcionalidad:

|**Ruta**|**Tipo de llamado**|**Datos Leídos de**|
| :-: | :- | :- |
|{{Tok2kitHost}}/public/2/customer-address|POST|Body|

- **Parámetros de Entrada**

Request esperado:

|<p>{</p><p>`    `**"customer\_name": "**string**",**</p><p>`    `**"customer\_last\_name": "**string**",**</p><p>`    `**"customer\_email":"**string**",**</p><p>`    `**"customer\_document\_type":"**string**",**</p><p>`    `**"customer\_document\_number":"",**</p><p>`    `**"customer\_phone":"**string**",**</p><p>`    `**"customer\_telephone":"**string**",**</p><p>`    `**"address\_name":"**string**",**</p><p>`    `**"address\_number":"**string**",**</p><p>`    `**"address\_place":"**string**",**</p><p>`    `**"is\_favorite":false,**</p><p>`    `**"address\_reference":"",**</p><p>`    `**"address\_coord":"**string**"**</p><p>}</p><p></p>|
| :- |





|Campo|Detalle|
| :-: | :-: |
|customer\_document\_type|tipo de identificación|
|customer\_document\_number|número de identificación|
|addres\_name|Dirección|
|addres\_place|lugar |
|addres\_coord|coordenadas de ubicación|

**Ejemplo:**

|<p>**{**</p><p>`    `**"customer\_name": "Juan",**</p><p>`    `**"customer\_last\_name": "Perez Rodriguez",**</p><p>`    `**"customer\_email":"mail@mail.com",**</p><p>`    `**"customer\_document\_type":"dni",**</p><p>`    `**"customer\_document\_number":"",**</p><p>`    `**"customer\_phone":"949339096",**</p><p>`    `**"customer\_telephone":"2292122",**</p><p>`    `**"address\_name":"Av. america 21323 URB: San francisco",**</p><p>`    `**"address\_number":"10",**</p><p>`    `**"address\_place":"casa",**</p><p>`    `**"is\_favorite":false,**</p><p>`    `**"address\_reference":"",**</p><p>`    `**"address\_coord":"-12.088294926166935, -77.04856171343624"**</p><p>**}**</p>|
| :- |






**Parámetro de salidas**

|**Escenario**|**Code**|**Body**|
| :-: | :-: | :-: |
|Registro exitoso|200|<p>{</p><p>`    `"status": **true**,</p><p>`    `"error\_code": **null**,</p><p>`    `"errors": **null**,</p><p>`    `"data": {</p><p>`        `"id": 1599546,</p><p>`        `"customer\_id": 636720,</p><p>`        `"ubigeo\_id": 0,</p><p>`        `"customer\_name": "Juan",</p><p>`        `"customer\_last\_name": "Perez Rodriguez",</p><p>`        `"customer\_email": "mail@mail.com",</p><p>`        `"customer\_document\_type": "dni",</p><p>`        `"customer\_document\_number": "",</p><p>`        `"customer\_phone": "949339096",</p><p>`        `"customer\_telephone": "2292122",</p><p>`        `"address\_name": "Av. america 21323 URB: San francisco",</p><p>`        `"address\_number": "10",</p><p>`        `"address\_place": "casa",</p><p>`        `"is\_favorite": **false**,</p><p>`        `"address\_reference": "",</p><p>`        `"address\_coord": "-12.088294926166935, -77.04856171343624",</p><p>`        `"sales\_order\_addresses": **null**,</p><p>`        `"created\_at": "2022-08-18T10:41:02.827076348-05:00",</p><p>`        `"updated\_at": "2022-08-18T10:41:02.827076348-05:00",</p><p>`        `"deleted\_at": **null**</p><p>}</p>|
|Error en la sintaxis|400|<p>{ "status": **false**,</p><p>`    `"error\_code": 400,</p><p>`    `"errors": {</p><p>`        `"error": "bad request"</p><p>`    `},</p><p>`    `"data": **null**</p><p>}</p><p></p>|
1. ### **Modificar el recurso creado**
A continuación, se detalla la URL y el tipo de llamado que se debe de usar para acceder a la funcionalidad:

|**Ruta**|**Tipo de llamado**|**Datos Leídos de**|
| :-: | :- | :- |
|{{Tok2kitHost}}/public/2/customer-address/1|PUT|Body|

- **Parámetros de Entrada**

Request esperado:

|<p>{</p><p>`    `"customer\_name": "string",</p><p>`    `"customer\_last\_name": "string",</p><p>`    `"customer\_email":"string",</p><p>`    `"customer\_document\_type":"string",</p><p>`    `"customer\_document\_number":"",</p><p>`    `"customer\_phone":"string",</p><p>`    `"customer\_telephone":"string",</p><p>`    `"address\_name":"string",</p><p>`    `"address\_number":"string",</p><p>`    `"address\_place":"string",</p><p>`    `"is\_favorite":**false**,</p><p>`    `"address\_reference":"",</p><p>`    `"address\_coord":"string"</p><p>}</p>|
| :- |

Ejemplo:

|<p>**{**</p><p>`    `**"customer\_name": "Anderson",**</p><p>`    `**"customer\_last\_name": "Perez Rodriguez",**</p><p>`    `**"customer\_email":"mail11@mail.com",**</p><p>`    `**"customer\_document\_type":"dni",**</p><p>`    `**"customer\_document\_number":"",**</p><p>`    `**"customer\_phone":"999999999",**</p><p>`    `**"customer\_telephone":"2292122",**</p><p>`    `**"address\_name":"Av. america 21323 URB: San francisco",**</p><p>`    `**"address\_number":"10",**</p><p>`    `**"address\_place":"casa",**</p><p>`    `**"is\_favorite":false,**</p><p>`    `**"address\_reference":"",**</p><p>`    `**"address\_coord":"-12.088294926166935, -77.04856171343624"**</p><p>**}**</p>|
| :- |

1. ## **Crear interfaz para administrar productos**
   1. ### **Crear interfaz para crear un producto**
A continuación, se detalla la URL y el tipo de llamado que se debe de usar para acceder a la funcionalidad:

|**Ruta**|**Tipo de llamado**|**Datos Leídos de**|
| :-: | :- | :- |
|{{Tok2kitHost}}/public/2/product|POST|Body|

`		`**Parámetros de Entrada**

Request esperado:

|<p>{</p><p>`    `"category": Array de strings,</p><p>`    `"cluster": Array de strings,</p><p>`    `"type":string,</p><p>`    `"sku":string,</p><p>`    `"external\_code\_pollito":string,</p><p>`    `"external\_code\_sf":string,</p><p>`    `"have\_comments":**boolean**,</p><p>`    `"has\_options":**boolean**,</p><p>`    `"name":string,</p><p>`    `"price\_view":string,</p><p>`    `"description:":string,</p><p>`    `"short\_description":string,</p><p>`    `"price":number,</p><p>`    `"weight":number,</p><p>`    `"type\_weight":string,</p><p>`    `"special\_price":number,</p><p>`    `"special\_price\_from": **date || null**,</p><p>`    `"special\_price\_at":**date || null**,</p><p>`    `"visibility":number,</p><p>`    `"related\_products":Array de strings,</p><p>`    `"image":string,</p><p>`    `"terms\_and\_conditions":string,</p><p>`    `"pedidos\_ya\_integration\_code":number,</p><p>`    `"pedidos\_ya\_integration\_name":string,</p><p>`    `"options": Array de objetos</p><p>}</p><p></p>|
| :- |


|**Campo**|**Detalle**|
| :-: | :-: |
|cluster|Array de cadenas con los nombres de los clusters|
|category: |Array de cadenas con nombre de las categorías|
|type:|<p>- bundle</p><p>- simple</p>|
|related\_products: |array de cadenas del SKU de productos|
|image: |el url de la imagen a cargar|
|visibility:|<p>- 1: "not\_visible\_individually"</p><p>- 2: "catalog"</p><p>- 3: "search"</p><p>- 4: "catalog\_search"</p><p></p>|
|price\_view:|<p>- AS\_LOW\_AS</p><p>- RANGE\_PRICE</p><p></p>|
|type\_weight:|<p>- kg</p><p>- g</p><p>- lb</p><p>- {vacío}</p>|
|options\_type:|<p>- radio</p><p>- select</p><p>- minmax</p><p>- mult</p>|
|selection\_price\_type:|<p>- 0: dinamico</p><p>- 1: fijo</p>|
|selection\_price\_value: |valor precio de la seleccion|


|<p>**{**</p><p>`    `**"category": [],**</p><p>`    `**"cluster": ["default R.cluster"],**</p><p>`    `**"type":"bundle",**</p><p>`    `**"sku":"SKU\_COMBO\_DESAYUNO\_MIXTO\_ESPECIAL\_6354\_200",**</p><p>`    `**"external\_code\_pollito":"3718",**</p><p>`    `**"external\_code\_sf":"3718",**</p><p>`    `**"have\_comments":true,**</p><p>`    `**"has\_options":false,**</p><p>`    `**"name":"DESAYUNO MIXTO ESPECIAL",**</p><p>`    `**"description:":"",**</p><p>`    `**"price\_view":"AS\_LOW\_AS",**</p><p>`    `**"short\_description":"",**</p><p>`    `**"price":0,**</p><p>`    `**"weight":0,**</p><p>`    `**"type\_weight":"",**</p><p>`    `**"special\_price":0,**</p><p>`    `**"special\_price\_from":null,**</p><p>`    `**"special\_price\_at":null,**</p><p>`    `**"visibility":1,**</p><p>`    `**"related\_products":[],**</p><p>`    `**"image":"",**</p><p>`    `**"terms\_and\_conditions":"",**</p><p>`    `**"pedidos\_ya\_integration\_code":0,**</p><p>`    `**"pedidos\_ya\_integration\_name":"",**</p><p>`    `**"options":[**</p><p>`        `**{**</p><p>`            `**"title":"Producto base",**</p><p>`            `**"required":true,**</p><p>`            `**"position":1,**</p><p>`            `**"type":"radio",**</p><p>`            `**"is\_recipe":true,**</p><p>`            `**"opt\_change":false,**</p><p>`            `**"qty\_min":1,**</p><p>`            `**"qty\_max":1,**</p><p>`            `**"selections":[**</p><p>`                `**{**</p><p>`                    `**"sku":"SKU\_DESAYUNO\_TIENDA\_CAFE\_ORGANICO\_3718\_200",**</p><p>`                    `**"position":1,**</p><p>`                    `**"title":"Desayuno orgánico",**</p><p>`                    `**"is\_default":true,**</p><p>`                    `**"selection\_price\_type":1,**</p><p>`                    `**"selection\_price\_value":0,**</p><p>`                    `**"selection\_qty":1,**</p><p>`                    `**"modify\_price":false**</p><p>`                `**}**</p><p>`            `**]**</p><p>`        `**}**</p><p>`    `**]**</p><p>**}**</p><p></p><p></p>|
| :- |

- **Parámetro de salidas**

|**Escenario**|**Code**|**Body**|
| :-: | :-: | :-: |
|Registro exitoso|200|<p>{</p><p>`    `"status": **true**,</p><p>`    `"error\_code": **null**,</p><p>`    `"errors": **null**,</p><p>`    `"data": {</p><p>`        `"category": [],</p><p>`        `"cluster": [</p><p>`            `"default R.cluster"</p><p>`        `],</p><p>`        `"type": "simple",</p><p>`        `"sku": "SKU\_DESAYUNO\_TIENDA\_CAFE\_ORGANICO\_3718\_200",</p><p>`        `"external\_code\_pollito": "3718",</p><p>`        `"external\_code\_sf": "3718",</p><p>`        `"have\_comments": **true**,</p><p>`        `"has\_options": **false**,</p><p>`        `"name": "DESAYUNO TIENDA - CAFE ORGANICO",</p><p>`        `"description": "",</p><p>`        `"short\_description": "",</p><p>`        `"price": 0,</p><p>`        `"price\_view": "AS\_LOW\_AS",</p><p>`        `"weight": 0,</p><p>`        `"type\_weight": "",</p><p>`        `"special\_price": 0,</p><p>`        `"special\_price\_from": **null**,</p><p>`        `"special\_price\_at": **null**,</p><p>`        `"visibility": 1,</p><p>`        `"store\_by\_cluster\_deactivated": "",</p><p>`        `"related\_products": [ "SKU\_HELADO\_MELONA\_MELON\_3129"</p><p>`        `],</p><p>`        `"image": "https://www.ensure.abbott/content/ani/ensure/countries/mx/es/pages/blog/la-importancia-de-desayunar-para-tener-energia-cada-maniana/\_jcr\_content/par/image.img.png/1614273942249.png",</p><p>`        `"terms\_and\_conditions": "",</p><p>`        `"pedidos\_ya\_integration\_code": 0,</p><p>`        `"pedidos\_ya\_integration\_name": "",</p><p>`        `"options": []</p><p>`    `}</p><p>}</p><p></p>|
|Error en la sintaxis|400|<p>{ "status": **false**,</p><p>`    `"error\_code": 400,</p><p>`    `"errors": {</p><p>`        `"error": "bad request"</p><p>`    `},</p><p>`    `"data": **null**</p><p>}</p><p></p>|

1. ### **Crear interfaz para modificar un producto**
Esta funcionalidad tiene como objetivo la edición de un producto buscándolo por su SKU enviado en el JSON. A continuación, se detalla la URL y el tipo de llamado que se debe de usar para acceder a la funcionalidad:

|**Ruta**|**Tipo de llamado**|**Datos Leídos de**|
| :-: | :- | :- |
|{{Tok2kitHost}}/public/2/product|PUT|Body|

`		`**Parámetros de Entrada**

Request esperado:

|<p>{</p><p>`    `"category": Array de strings,</p><p>`    `"cluster": Array de strings,</p><p>`    `"type":string,</p><p>`    `"sku":string,</p><p>`    `"external\_code\_pollito":string,</p><p>`    `"external\_code\_sf":string,</p><p>`    `"have\_comments":**boolean**,</p><p>`    `"has\_options":**boolean**,</p><p>`    `"name":string,</p><p>`    `"price\_view":string,</p><p>`    `"description:":string,</p><p>`    `"short\_description":string,</p><p>`    `"price":number,</p><p>`    `"weight":number,</p><p>`    `"type\_weight":string,</p><p>`    `"special\_price":number,</p><p>`    `"special\_price\_from": **date || null**,</p><p>`    `"special\_price\_at":**date || null**,</p><p>`    `"visibility":number,</p><p>`    `"related\_products":Array de strings,</p><p>`    `"image":string,</p><p>`    `"terms\_and\_conditions":string,</p><p>`    `"pedidos\_ya\_integration\_code":number,</p><p>`    `"pedidos\_ya\_integration\_name":string,</p><p>`    `"options": Array de objetos</p><p>}</p><p></p>|
| :- |


|**Campo**|**Detalle**|
| :-: | :-: |
|cluster|Array de cadenas con los nombres de los clusters|
|category: |Array de cadenas con nombre de las categorías|
|type:|<p>- bundle</p><p>- simple</p>|
|image: |el url de la imagen a cargar, esta actualizará el que tenga anteriormente|
|visibility:|<p>- 1: "not\_visible\_individually"</p><p>- 2: "catalog"</p><p>- 3: "search"</p><p>- 4: "catalog\_search"</p><p></p>|
|price\_view:|<p>- AS\_LOW\_AS</p><p>- RANGE\_PRICE</p>|
|type\_weight:|<p>- kg</p><p>- g</p><p>- lb</p><p>- {vacío}</p>|
|options\_type:|<p>- radio</p><p>- select</p><p>- minmax</p><p>- mult</p>|
|selection\_price\_type:|<p>- 0: dinamico</p><p>- 1: fijo</p>|
|selection\_price\_value: |valor del precio de la selección|


|<p>**{**</p><p>`    `**"category": [],**</p><p>`    `**"cluster": ["default R.cluster"],**</p><p>`    `**"type":"bundle",**</p><p>`    `**"sku":"SKU\_COMBO\_DESAYUNO\_MIXTO\_ESPECIAL\_6354\_200",**</p><p>`    `**"external\_code\_pollito":"3718",**</p><p>`    `**"external\_code\_sf":"3718",**</p><p>`    `**"have\_comments":true,**</p><p>`    `**"has\_options":false,**</p><p>`    `**"name":"DESAYUNO MIXTO ESPECIAL",**</p><p>`    `**"description:":"",**</p><p>`    `**"price\_view":"AS\_LOW\_AS",**</p><p>`    `**"short\_description":"",**</p><p>`    `**"price":0,**</p><p>`    `**"weight":0,**</p><p>`    `**"type\_weight":"",**</p><p>`    `**"special\_price":0,**</p><p>`    `**"special\_price\_from":null,**</p><p>`    `**"special\_price\_at":null,**</p><p>`    `**"visibility":1,**</p><p>`    `**"related\_products":[],**</p><p>`    `**"image":"",**</p><p>`    `**"terms\_and\_conditions":"",**</p><p>`    `**"pedidos\_ya\_integration\_code":0,**</p><p>`    `**"pedidos\_ya\_integration\_name":"",**</p><p>`    `**"options":[**</p><p>`        `**{**</p><p>`            `**"title":"Producto base",**</p><p>`            `**"required":true,**</p><p>`            `**"position":1,**</p><p>`            `**"type":"radio",**</p><p>`            `**"is\_recipe":true,**</p><p>`            `**"opt\_change":false,**</p><p>`            `**"qty\_min":1,**</p><p>`            `**"qty\_max":1,**</p><p>`            `**"selections":[**</p><p>`                `**{**</p><p>`                    `**"sku":"SKU\_DESAYUNO\_TIENDA\_CAFE\_ORGANICO\_3718\_200",**</p><p>`                    `**"position":1,**</p><p>`                    `**"title":"Desayuno orgánico",**</p><p>`                    `**"is\_default":true,**</p><p>`                    `**"selection\_price\_type":1,**</p><p>`                    `**"selection\_price\_value":0,**</p><p>`                    `**"selection\_qty":1,**</p><p>`                    `**"modify\_price":false**</p><p>`                `**}**</p><p>`            `**]**</p><p>`        `**}**</p><p>`    `**]**</p><p>**}**</p><p></p><p></p>|
| :- |

- **Parámetro de salidas**

|**Escenario**|**Code**|**Body**|
| :-: | :-: | :-: |
|Actualización exitosa|200|<p>{</p><p>`    `"status": **true**,</p><p>`    `"error\_code": **null**,</p><p>`    `"errors": **null**,</p><p>`    `"data": {</p><p>`        `"category": [],</p><p>`        `"cluster": [</p><p>`            `"default R.cluster"</p><p>`        `],</p><p>`        `"type": "simple",</p><p>`        `"sku": "SKU\_DESAYUNO\_TIENDA\_CAFE\_ORGANICO\_3718\_200",</p><p>`        `"external\_code\_pollito": "3718",</p><p>`        `"external\_code\_sf": "3718",</p><p>`        `"have\_comments": **true**,</p><p>`        `"has\_options": **false**,</p><p>`        `"name": "DESAYUNO TIENDA - CAFE ORGANICO",</p><p>`        `"description": "",</p><p>`        `"short\_description": "",</p><p>`        `"price": 0,</p><p>`        `"price\_view": "AS\_LOW\_AS",</p><p>`        `"weight": 0,</p><p>`        `"type\_weight": "",</p><p>`        `"special\_price": 0,</p><p>`        `"special\_price\_from": **null**,</p><p>`        `"special\_price\_at": **null**,</p><p>`        `"visibility": 1,</p><p>`        `"store\_by\_cluster\_deactivated": "",</p><p>`        `"related\_products": [ "SKU\_HELADO\_MELONA\_MELON\_3129"</p><p>`        `],</p><p>`        `"image": "https://www.ensure.abbott/content/ani/ensure/countries/mx/es/pages/blog/la-importancia-de-desayunar-para-tener-energia-cada-maniana/\_jcr\_content/par/image.img.png/1614273942249.png",</p><p>`        `"terms\_and\_conditions": "",</p><p>`        `"pedidos\_ya\_integration\_code": 0,</p><p>`        `"pedidos\_ya\_integration\_name": "",</p><p>`        `"options": []</p><p>`    `}</p><p>}</p><p></p>|
|Error en la sintaxis|400|<p>{ "status": **false**,</p><p>`    `"error\_code": 400,</p><p>`    `"errors": {</p><p>`        `"error": "bad request"</p><p>`    `},</p><p>`    `"data": **null**</p><p>}</p><p></p>|
|Producto no encontrado|400|<p>{ "status": **false**,</p><p>`    `"error\_code": 400,</p><p>`    `"errors": {</p><p>`        `"error": "product not found"</p><p>`    `},</p><p>`    `"data": **null**</p><p>}</p><p></p>|

1. ### **Crear interfaz para eliminar un producto**
Esta funcionalidad tiene como objetivo la eliminiación de un producto buscándolo por su SKU como parámetro. A continuación, se detalla la URL y el tipo de llamado que se debe de usar para acceder a la funcionalidad:

|**Ruta**|**Tipo de llamado**|**Datos Leídos de**|
| :-: | :- | :- |
|{{Tok2kitHost}}/public/2/product/{sku}|DELETE|Body|

- **Parámetro de salidas**

|**Escenario**|**Code**|**Body**|
| :-: | :-: | :-: |
|Eliminación exitosa|200|<p>{</p><p>`    `"status": **true**,</p><p>`    `"error\_code": **null**,</p><p>`    `"errors": **null**,</p><p>`    `"data": {</p><p>`        `"category": [],</p><p>`        `"cluster": [</p><p>`            `"default R.cluster"</p><p>`        `],</p><p>`        `"type": "simple",</p><p>`        `"sku": "SKU\_DESAYUNO\_TIENDA\_CAFE\_ORGANICO\_3718\_200",</p><p>`        `"external\_code\_pollito": "3718",</p><p>`        `"external\_code\_sf": "3718",</p><p>`        `"have\_comments": **true**,</p><p>`        `"has\_options": **false**,</p><p>`        `"name": "DESAYUNO TIENDA - CAFE ORGANICO",</p><p>`        `"description": "",</p><p>`        `"short\_description": "",</p><p>`        `"price": 0,</p><p>`        `"price\_view": "AS\_LOW\_AS",</p><p>`        `"weight": 0,</p><p>`        `"type\_weight": "",</p><p>`        `"special\_price": 0,</p><p>`        `"special\_price\_from": **null**,</p><p>`        `"special\_price\_at": **null**,</p><p>`        `"visibility": 1,</p><p>`        `"store\_by\_cluster\_deactivated": "",</p><p>`        `"related\_products": [ "SKU\_HELADO\_MELONA\_MELON\_3129"</p><p>`        `],</p><p>`        `"image": "https://www.ensure.abbott/content/ani/ensure/countries/mx/es/pages/blog/la-importancia-de-desayunar-para-tener-energia-cada-maniana/\_jcr\_content/par/image.img.png/1614273942249.png",</p><p>`        `"terms\_and\_conditions": "",</p><p>`        `"pedidos\_ya\_integration\_code": 0,</p><p>`        `"pedidos\_ya\_integration\_name": "",</p><p>`        `"options": []</p><p>`    `}</p><p>}</p><p></p>|
|Producto no encontrado|400|<p>{ "status": **false**,</p><p>`    `"error\_code": 400,</p><p>`    `"errors": {</p><p>`        `"error": "product not found"</p><p>`    `},</p><p>`    `"data": **null**</p><p>}</p>|



|[www.janaq.com](http://www.janaq.com) ||
| :- | -: |

