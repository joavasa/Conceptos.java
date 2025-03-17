🔹 **javax pertenece a Java EE (Enterprise Edition), que era mantenido por Oracle hasta la versión Java EE 8.**  
🔹 **jakarta pertenece a Jakarta EE, que es la evolución de Java EE tras ser transferida a la Eclipse Foundation.**

## Comparación entre Java EE y Jakarta EE

| Característica      | Java EE (javax)         | Jakarta EE (jakarta)       |
|--------------------|-----------------------|--------------------------|
| **Organización**   | Oracle                | Eclipse Foundation       |
| **Última versión** | Java EE 8             | Jakarta EE 10+          |
| **Paquete principal** | `javax.*` (ej. `javax.servlet.*`) | `jakarta.*` (ej. `jakarta.servlet.*`) |
| **Compatibilidad** | Usado en Java EE 8 y anteriores | A partir de Jakarta EE 9 |
| **Cambios clave**  | Estático, sin evolución | Migración y mejoras en APIs |

📌 **¿Qué significa para ti?**
- Si usas Spring Boot, probablemente no notarás muchas diferencias, ya que Spring administra sus dependencias.  
- Si trabajas con servlets, JSP o JPA, los paquetes han cambiado de javax.* a jakarta.*.  
- A partir de Jakarta EE 9, todas las librerías que usaban javax han sido renombradas a jakarta.

## 📌 Ejemplo: Cambio en Servlet  
🔴 Antes (Java EE 8 - javax)
    
    import javax.servlet.http.HttpServlet;
    import javax.servlet.http.HttpServletRequest;
    import javax.servlet.http.HttpServletResponse;
🟢 Ahora (Jakarta EE 9+ - jakarta)

    import jakarta.servlet.http.HttpServlet;
    import jakarta.servlet.http.HttpServletRequest;
    import jakarta.servlet.http.HttpServletResponse;
