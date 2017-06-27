# CursoJava2017
apuntes del curso de Java

DIA1
-------------------------------------------------------------------------------------------
Cuestiones curso - Director

Entregar una actividad pedegógica con fecha tope 2 semanas después. 
ORIGINAL
Se pueden consultar las del año pasado en la biblioteca virtual, en el curso del año pasado.

Entregar lo que sea necesario a través de la biblioteca virtual fp.
___________________________________________________________________________________________
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
	
Comprobamos lo instalado. Ponemos apache y mysql como servicios. Instalamos Tomcat.

