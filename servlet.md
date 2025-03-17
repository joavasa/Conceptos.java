SERVELET 
🚀 ¿Qué es un Servlet?
Un Servlet es una clase en Java que se ejecuta en un servidor web y permite manejar peticiones HTTP (como GET y POST). 
Es una parte fundamental de Java EE (ahora Jakarta EE) para crear aplicaciones web dinámicas.

¿Para qué sirve un Servlet?
Procesar solicitudes HTTP de los clientes (navegador, aplicaciones, etc.).
Generar respuestas dinámicas, como páginas HTML o datos en JSON/XML.
Manejar sesiones de usuarios y autenticación.
Conectar con bases de datos y otras APIs en el backend.

Este Servlet responde con un simple "Hola, mundo!" cuando accedes a http://localhost:8080/hola.
 Código con javax.servlet (Java EE 8 y anteriores)
  
        import java.io.IOException;
        import java.io.PrintWriter;
        import javax.servlet.ServletException;
        import javax.servlet.annotation.WebServlet;
        import javax.servlet.http.HttpServlet;
        import javax.servlet.http.HttpServletRequest;
        import javax.servlet.http.HttpServletResponse;
        
        @WebServlet("/hola")
        public class HolaMundoServlet extends HttpServlet {
            @Override
            protected void doGet(HttpServletRequest request, HttpServletResponse response) 
                    throws ServletException, IOException {
                response.setContentType("text/html");
                PrintWriter out = response.getWriter();
                out.println("<h1>¡Hola, mundo desde un Servlet!</h1>");
            }
        }

📌 Código con jakarta.servlet (Jakarta EE 9 en adelante)
Si usas Jakarta EE 9+, debes cambiar javax.servlet por jakarta.servlet:

      import java.io.IOException;
      import java.io.PrintWriter;
      import jakarta.servlet.ServletException;
      import jakarta.servlet.annotation.WebServlet;
      import jakarta.servlet.http.HttpServlet;
      import jakarta.servlet.http.HttpServletRequest;
      import jakarta.servlet.http.HttpServletResponse;
      
      @WebServlet("/hola")
      public class HolaMundoServlet extends HttpServlet {
          @Override
          protected void doGet(HttpServletRequest request, HttpServletResponse response) 
                  throws ServletException, IOException {
              response.setContentType("text/html");
              PrintWriter out = response.getWriter();
              out.println("<h1>¡Hola, mundo desde un Servlet!</h1>");
          }
      }

🔹 ¿Cómo funciona un Servlet?
1️⃣ El usuario accede a la URL del servlet en su navegador (http://localhost:8080/hola).
2️⃣ El servidor de aplicaciones (Tomcat, Jetty, etc.) recibe la petición y la envía al servlet.
3️⃣ El servlet ejecuta la lógica (consulta BD, procesa datos, etc.).
4️⃣ Genera y devuelve la respuesta al usuario (HTML, JSON, etc.).

🔹 Ciclo de Vida de un Servlet
Un servlet sigue este ciclo:

1️⃣ Instanciación → El servidor crea una instancia del servlet.
2️⃣ Inicialización (init()) → Se ejecuta una vez cuando se carga el servlet.
3️⃣ Procesamiento (doGet() / doPost()) → Se ejecuta en cada solicitud.
4️⃣ Destrucción (destroy()) → Se ejecuta antes de eliminar el servlet.
        
        @Override
        public void init() throws ServletException {
            System.out.println("Servlet iniciado");
        }
        
        @Override
        public void destroy() {
            System.out.println("Servlet destruido");
        }

🚀 ¿Por qué usar Servlets hoy en día?
✅ Son la base de tecnologías como JSP, JSF y Spring MVC.
✅ Se usan para manejar peticiones HTTP en backend Java.
✅ Permiten crear APIs REST si se combinan con JAX-RS o frameworks modernos.

📌 Alternativa moderna: Hoy en día, Spring Boot es más popular para manejar peticiones HTTP en Java, usando Spring MVC y RestControllers en lugar de Servlets puros.
