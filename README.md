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
TOMCAT (el gato Tom)

Lo dejamos en manual para dejar que lo controle Eclipse.
Problemas posibles de instalación:
- Autenticación -> CATALINA_BASE/conf/tomcat-users.xml. Se pone usuario/pass y roles que indican lo que puedo hacer.
- No están los ejemplos -> se copia la carpeta en CATALINA_BASE/webapps
Configuración -> CATALINA_HOME/conf
- server.xml -> configuración del servidor
	<Server> Vale para parar el servicio, con una palabra clave.
	<Engine><Realm><Host name appBase (dir base) unpackWARs (autoinstalar WAR) autoDeploy (autopublicar)>


CONCEPTOS
TomCat es un entorno de ejecución de servlets.
Servlet: Escucha una solicitud HTTP y genera una respuesta HTTP (HTML, json...).
	El código es más parecido a un java de toda la vida.
	Crea un objeto respuesta y le mete dentro etiquetas HTML.
¿Cómo genero con un servlet un holamundo?. Con "echos". Para mejorarlo:
JSP: tipo de programa que sirve para presentar salida a pantalla, generar HTML.
	El código es HTML enriquecido con etiquetas de JSP <% %>. 

MVC. "V" sería JSP. "C" serían los "servlets". "M" sería java sin más.
	Lo ideal para hacer un "hola mundo", sería que servlet recoja la petición,
	se lo pasa el JSP que genera la página y se la devuelve y luego el servlet
	se la devuelve al cliente.

USO 
- Server Status (curso/curso). Administración.
- Manager App. 
Para gestionar las aplicaciones Java, los servlets. Vemos las aplicaciones instaladas en el servidor. 
Tomcat nos  permitirá: arrancarlo, pararlo, replegarlo (desactivarlo y borrar la carpeta y el war si lo hay).
Probamos:
	- /docs. Documentación de esta versión.
	- /examples. Ejemplos de servlets, jsp y websockets. 
		Se puede ver la ejecución y el código y se puede aprender mucho.
	(estas "rutas" están mapeadas, no tienen por qué coincidir con carpetas reales)
Lo desplegado está en "CATALINA_BASE/webapps". 
	Si copiamos una nueva carpeta directamente en esta, es como si desplegáramos un nueva aplicación. 
	Si copiamos un .war, trata de descomprimirlo y publicarlo. (Instalación "a mano").
Podemos desplegar también a través de la propia herramienta de despliegue de Tom.

Ejercicio: El cliente pone http://.../app/ListadoEmpleado y quiere recibir el listado de Empleados.
El que lo recibe es un servlet(C). Servlet se lo pasa a un JSP(V). Servlet usará clases de java,
(por ejemplo AccesoBD, los pojos Empleado.java y Departamento.java) para pedir a la base de datos los
datos de los empleados, en un arraylist. El arraylist se lo pasa al JSP. El JSP crea un HTML enriquecido
y se lo devuelve al servlet, que es quien se lo pasaría al cliente.

CATALINA_BASE = directorio donde está instalado TomCat.
__________________________________________________________________________________________________
ECLIPSE

Vinculamos Eclipse con TomCat. Eclipse se crea una instancia propia de configuración de tomcat.
Tiene sus propios archivos y permite cambiarlos. Son dos instancias virtuales de tomcat. Por eso
preferimos apagar el otro y controlarlo desde aquí. En realidad, es un clon del instalado en la 
máquina.

En WebContent: todo lo del proyecto que no sean .java.

Código que empieza con @ -> pseudoinstrucciones.

---------------------------------------------------------------------------------------------------
CONCEPTOS GENERALES DEL CURSO
- FDBC es un API (conjunto de clases que trabajan en conjunto para hacer una tarea determinada). 
Hibernate es un ORM (traductor POO-MR).
- .war. Es como un .jar, pero para aplicación de servidor. Está comprimido. Si miramos dentro, 
podemos var las .class (que son servlets compilados, ya en bytecode). Para ver el código java,
necesitamos un DECOMPILADOR (o javap), que toma el .class y te da el .java.
- gestión de procesos en windows
	- tasklist. es como ps.
	- taskkill. es kill.
	- sc. es como services.msc
- XSTL. Hoja de transformaciones, que se aplican a otro documento de entrada. Es un XML que tiene
instrucciones para transformar la entrada en otra salida. Puede generar varios formatos de salida.
No es lo mismo que JSP.
___________________________________________________________________________________________________
ENLACES DEL CURSO
* JSR - es el equivalente en java de un un RFC de redes. - https://jcp.org/en/jsr/all. Cada API tiene
aquí un documento que las describe en profundidad. Aquí está toda la información PROFUNDA.
