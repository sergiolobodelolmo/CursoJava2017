# CursoJava2017
apuntes del curso de Java

DIA1 - Cuestiones curso - VBOX
-------------------------------------------------------------------------------------------
COMENTARIOS DEL DIRECTOR (entrega de la actividad didáctica).

Entregar una actividad pedegógica con fecha tope 2 semanas después. ORIGINAL. 
Se pueden consultar las del año pasado en la biblioteca virtual, en el curso del año pasado.
Entregar lo que sea necesario a través de la biblioteca virtual fp.
___________________________________________________________________________________________
PLANTEAMIENTO
- Planteamiento del temario 
	Dejamos fuera GIT (a pesar de ello, hacer tarea) y Maven
	Incluimos servidor, Hibernate (traductor POO-MR), Spring, servicios web.
	3 plantillas de máquinas, w10, con media instalación, con toda la instalación.
- Cuestiones varias
	w10 host - curso/curso (fondo azul) - red por dhcp
		unidad D: carpeta DAJ. Copia de la máquina virtual y algo de software
	w10 virtual - curso/curso (fondo verde) - red por dhcp
		tiene:
			1. JDK (Java Standard Edition) - entorno básico de compilación y edición
				Incluye JRE (solo intérprete) + compilador.
			2. Notepad++
			3. Zoomit
			4. 7zip
			5. Adobe Reader
			6. XAMPP (apache, php, mysql, filezilla server, tomcat(servlets))
			7. Tomcat (una versión más moderna, no incluido en XAMPP)
			8. MySQL Workbench (permite ingeniería directa e inversa)
			9. Eclipse JEE (para la versión Enterprise de Java)
			10. Lightscreen (capturador de pantallas)
			
	red: 172.31.0.0/16 - gateway/dns server primario:172.31.0.5, dns secund:8.8.8.8
- Tareas
	crear proyecto en GitHub

___________________________________________________________________________________________
VBOX 
	Cuidado con el Identificador (clonar máquinas, no copiar sin más) y la MAC.
	archivo disco virtual: .vdi
	archivo de configuración de virtualbox: .vbox -> puedo cambiarlo a mano
___________________________________________________________________________________________
INSTALACIONES
Comprobamos lo instalado. 
Ponemos apache y mysql como servicios. 
Instalamos Tomcat con el instalador/wizard.


DIA2 - TomCat - GIT
-------------------------------------------------------------------------------------------
__________________________________________________________________________________________
TOMCAT

Lo dejamos en manual para dejar que lo controle Eclipse.

Servlet: Escucha una solicitud HTTP y genera una respuesta HTTP (HTML, json...).
¿Cómo genero con un servlet un holamundo?. Con "echos". Para mejorarlo:
JSP: tipo de programa que sirve para presentar salida a pantalla, generar HTML.

MVC. "V" sería JSP. "C" serían los "servlets". "M" sería java sin más.

TomCat es un entorno de ejecución de servlets. 
Botones:
	* Server Status (curso/curso). Administración.
	* Manager App. Para gestionar las aplicaciones Java, los servlets. Vemos las aplicaciones
	instaladas en el servidor. Podemos ver los ejemplos (examples)
	
Problemas posibles:
* Autenticación -> ./conf/tomcat-users.xml. Se pone usuario/pass y roles que indican lo que puedo hacer.
* No están los ejemplos -> se copia la carpeta en webapps

Probamos con "/docs" y "/examples".

Podemos tener algo instalado pero no desplegado. Lo desplegado está en "webapps". Si copiamos una
nueva carpeta directamente en esta, es como si desplegáramos un nueva aplicación. Tomcat nos 
permitirá arrancarlo.
