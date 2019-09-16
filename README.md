# Spring Boot 2.x

Repositorio que tiene el ejemplo de un proyecto con Spring Boot 2.x y manejo de freemaker

----------------------------------
Pasos para instalación de proyecto :neosuniversity-freemarker
----------------------------------
1.- Crear una carpeta neosuniversity-freemarker (omitir este paso si se cloana el repositorio)
2.- vi app.groovy (omitir este paso si se cloana el repositorio)
@Controller
@Grab('spring-boot-starter-freemarker')
class MyApp {

    @RequestMapping("/greet")
        String home(Model model, @RequestParam String name) {
		
		model.addAttribute("myname", name)
		return "hello"
	}
 }
 3.- crear una carpeta static y crear el archivo con contenido
 $ vi static\index.html
 
 <!DOCTYPE html>
<html> 
	<head>         <title>Home page</title>         <meta charset="UTF-8">     </head> 
<body>          
	<form action="/greet"> 
		<label>Enter your name:</label>            
		<input type="text" name="name"> 
		<button type="submit">Submit</button>
	</form>
</body> 
</html>

4.- crear una carpeta templates y crear archivo con el contenido
$ vi templates\hello.ftl

<!DOCTYPE html>
<html>
    <head>
            <title>Home page</title>
	            <meta charset="UTF-8">
		        </head>
			    <body>
			            <p>Hello ${myname}, today is a beautiful day!</p>
				        </body>
					</html>

5.- Ejecutar (en caso de ser varios los archivos groovy debera ejecutar *.groovy)
$ spring run app.groovy

6.- Abrir un browser y ejecutar
http://localhost:8080/
colocar el nombre: hugo click submit
http://localhost:8080/greet?name=hugo
Hello hugo, today is a beautiful day!

7.- Para empaquetar nuestra aplicacion ejecutar
$ spring jar neosuniversity-freemaker.jar *.groovy

spring run app.groovy  -- --server.port=9000
