# Práctica Validación de Formularios

Se realiza una página web para una empresa que vende servicios de Internet a otras compañías.
La empresa nos solicita un un formulario de contacto en el que recogeremos no sólo los datos de contacto, sino también los datos para facturación o acceso por Internet.

**Información de Contacto:**
- Nombre* 		
- Apellidos* 	
- Teléfono*
- email* 	
- repetir email 		
- ¿Cómo nos has conocido? (Prefiero no contestar, Publicidad, Profesionales del 	sector, Internet, A través de un amigo o conocido )

Datos de facturación:
Demandante 	(Particular o Empresa)*
CIF/NIF*
Nombre/Empresa*
Dirección*
CP*
Localidad*
Provincia*
País*
Código IBAN* 		
Forma de pago: Mensual, Trimestral, Anual* 	

Datos de acceso:
usuario* 		
contraseña* 	
repetir 	contraseña 	


Debemos hacer la siguiente validación en cliente antes de hacer el envío del formulario:
Todos los campos con * son requeridos	
Comprobaremos que el usuario no exista previamente en la bbdd (NIF o email, el CIF no es necesario).
Teléfono contendrá solo dígitos y un total de 9.	
CP tendrán que ser 5 digitos. Si son menos se completará con 0 a la izquierda.
email debe ser un correo electrónico válido (al menos en apariencia)
Por defecto estará marcado como demandante Particular y como Nombre (apartado 	Datos de facturación) la combinación de los campos Nombre y Apellidos de la información de contacto. Si el usuario selecciona como demandante Empresa, se borrará el contenido del campo “Nombre”, que pasará a llamarse “Empresa” para que el usuario lo rellene. 	
Los campos CIF/NIF y Nombre/Empresa adecuarán su label en función del 	demandante seleccionado.
Una vez insertado el código postal, se debe seleccionar la provincia y la localidad de forma automática. La localidad se rellenará con criterio libre.
El código IBAN debe ser válido.
El usuario debe tener al menos 4 caracteres, se rellenará de modo automático 	con el correo electrónico y no podrá ser modificado.
La contraseña se debe forzar a que sea compleja.
Una vez pulsemos enviar en el formulario se mostrará un aviso al usuario de que se va a dar de alta y que se le pasará la primera cuota de 50€, 140€ o 550€ según corresponda (forma de pago). El usuario podrá cancelar la operación.

Ayuda: Te recomiendo que te bases en la práctica ya solucionada de validación.

Datos de test: 
El usuario con email juandacorreo@gmail.com y DNI 25456737S deberá estar dado de alta en la base de datos. 
El CIF que probaré es el siguiente: A28017895 (El Corte Inglés).
El código IBAN: ES91 2085 0166 69 0330150871

	
Requerimientos adicionales:
Uso de al menos un plugin adicional, por ejemplo:
jquery Complexify para la complejidad de la contraseña.
http://harvesthq.github.io/chosen/ para los select

Diseño css propio o basado en un framework css tipo Bootstrap o Foundation (nada de “reciclar” el de la práctica demo).  Si utilizas Bootstrap y no lo conoces, puedes apoyarte en bootsnipp.

La práctica se debe colgar en github y debe partir de un fork de mi repositorio, para su seguimiento por mi parte. De cualquier manera en vuestro formulario deberá haber un enlace visible a vuestro repositorio en GitHub. Serán necesarios al menos 5 commits en 3 días diferentes.

El código html, css y js deberá ir en sus propios ficheros. Se debe disponer de dos versiones del código, una de desarrollo y otra de producción que tendrá todos los ficheros minified y concatenados, de modo que haya un único js para todo el código que no sea nuestro (jQuery, Validate…), un único css para todo el código que no sea nuestro (Bootstrap por ej.), y un único css o js para el código que hayamos hecho nosotros. Para realizar todo este proceso, se recomienda encarecidamente el uso de Yeoman. Para facilitar y “forzar” a ello, ya os proporciono la estructura de la aplicación con Yeoman (yo webapp). 
