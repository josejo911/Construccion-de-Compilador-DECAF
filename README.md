IDEA INTELLIJO
==============

Plantilla para una aplicación Vaadin simple que solo requiere un contenedor Servlet 3.0 para ejecutarse.


Flujo de trabajo
========

Para compilar todo el proyecto, ejecute "mvn install".

Para ejecutar la aplicación, ejecute "mvn jetty: run" y abra http: // localhost: 8080 /.

Para producir un WAR en modo de producción desplegable:
- cambie productionMode a verdadero en la configuración de la clase de servlet (anidado en la clase de interfaz de usuario)
- ejecutar "mvn clean package"
- prueba el archivo war con "mvn jetty: run-war"

Compilación del lado del cliente
-------------------------

El proyecto maven generado utiliza un conjunto de widgets generado automáticamente de forma predeterminada.
Cuando agrega una dependencia que necesita compilación del lado del cliente, el complemento maven
generarlo automáticamente para usted. Sus propias personalizaciones del lado del cliente se pueden agregar a
paquete "cliente".

Depurar el código del lado del cliente
  - ejecutar "mvn vaadin: run-codeserver" en una consola separada mientras se ejecuta la aplicación
  - activar el modo Super Dev en la ventana de depuración de la aplicación

Desarrollar un tema usando el compilador en tiempo de ejecución
-------------------------

Al desarrollar el tema, Vaadin se puede configurar para compilar el SASS basado
tema en tiempo de ejecución en el servidor. De esta manera, puede modificar los archivos scss en
su IDE y vuelva a cargar el navegador para ver los cambios.

Para usar la compilación en tiempo de ejecución, abra pom.xml y comente el tema de compilación
objetivo de la configuración de vaadin-maven-plugin. Para eliminar una posible existencia
tema precompilado, ejecute "mvn clean package" una vez.

Cuando se usa el compilador en tiempo de ejecución, se ejecuta la aplicación en el modo "ejecutar"
(en lugar de en modo "depuración") puede acelerar las compilaciones de temas consecutivos
significativamente.

Se recomienda deshabilitar la compilación en tiempo de ejecución para los archivos WAR de producción.

Usando los prelanzamientos de Vaadin
-------------------------

Si las versiones preliminares de Vaadin no están habilitadas de forma predeterminada, use el parámetro Maven
"-P vaadin-prerelease" o cambie el valor predeterminado de activación del perfil en pom.xml.