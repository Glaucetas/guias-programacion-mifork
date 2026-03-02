1. Respuesta: En C se suele recurrir a códigos de retorno o variables globales.

Opción A (Valor centinela): Devolver un valor imposible.
float raiz(float n) {
    if (n < 0) return -1.0; // Código de error
    return sqrt(n);
}

Opción B (Puntero de estado): Modificar una variable externa.
float raiz(float n, int *error) {
    if (n < 0) { *error = 1; return 0; }
    *error = 0; return sqrt(n);
}

2. Respuesta: Una excepción es un evento que interrumpe el flujo normal de las instrucciones de un programa. El objetivo es separar el código de la lógica de negocio del código de 
gestión de errores, permitiendo que el error sea manejado en el nivel jerárquico más adecuado.

---clase---
Excepción: es una situación atípica 
-Errores.
    --De entrada de usuarios (de validación)
    --De programación.
    --De entorno (E/S).
-Al implementar una funcion, puedo lanzarla.
-Al llamar a funciones puedo capturarlas.


3.Respuesta:
public class Calculadora {
    public double raiz(double n) {
        if (n < 0) throw new IllegalArgumentException("Número negativo");
        return Math.sqrt(n);
    }
    public static void main(String[] args) {
        try {
            Calculadora calc = new Calculadora();
            System.out.println(calc.raiz(-5));
        } catch (IllegalArgumentException e) {
            System.out.println("Error: " + e.getMessage());
        }
    }
}

4. Respuesta: * Lanzar (throw): Notificar que ha ocurrido un error creando un objeto excepción.

Controlar/Capturar (catch): Detener la propagación y ejecutar código para sanear el error.

Propagar: Si una función no captura la excepción, esta "salta" a la función anterior en la pila.

Pila de llamadas: Las funciones se van cerrando abruptamente. No se reanudan; una vez que la excepción sale de la función, esa ejecución se pierde a menos que se capture.

5. Respuesta: Evita el "ruido" en el código. En C, cada nivel intermedio debe comprobar manualmente si la función llamada devolvió un error. En Java, los niveles intermedios pueden 
ignorar la excepción y esta subirá automáticamente hasta encontrar un catch.

6. Respuesta: Sí, son objetos. Ventaja: Permite usar herencia para categorizar errores (ej: capturar Exception para cualquier error o IOException para algo específico). 
Sí, podemos crear nuestras propias clases extendiendo de Exception o RuntimeException.

7. Respuesta: Información como el mensaje de error descriptivo, el StackTrace (traza de la pila que indica exactamente en qué línea y fichero ocurrió el fallo) y, opcionalmente, 
la causa (otra excepción anidada).

---clase---
Tres elementos tienen un objeto Excepción
-Un mensaje.
-Una traza de llamadas.
-Opcionalmente, otra excepción causa...

8. Respuesta: Sí, se pueden tener múltiples bloques catch. Sin embargo, solo se ejecuta uno: el primero cuyo tipo de excepción coincida con la lanzada.

9. Respuesta: Se usa el bloque finally.
// Con catch
try { /* abrir recurso */ } catch (Exception e) { /* error */ } finally { /* cerrar recurso */ }
// Sin catch (solo limpieza)
try { /* abrir recurso */ } finally { /* cerrar recurso */ }

10. Respuesta: Sí, puede ir sin catch. Se ejecuta siempre, pase lo que pase. Incluso si hay un return en el try, el código del finally se ejecuta justo antes de que el método devuelva efectivamente el control.

11. Respuesta: * Controladas (Checked): Heredan de Exception. El compilador obliga a capturarlas o declararlas (ej: IOException, SQLException).
* Uso: Errores externos recuperables (archivo no encontrado, red caída).

No controladas (Unchecked): Heredan de RuntimeException. No es obligatorio capturarlas (ej: NullPointerException, IndexOutOfBoundsException).

Uso: Errores de programación (bugs) o fallos lógicos irrecuperables.

12. Respuesta: Es una cláusula en la firma del método que indica que dicho método puede lanzar ciertas excepciones. Se usa para delegar la responsabilidad de captura al método que lo llame.

13. Respuesta:
public void abrirFichero(String ruta) throws IOException {
    try {
        // Lógica de apertura
    } finally {
        System.out.println("Limpieza finalizada.");
    }
}

14. Respuesta: Se puede, pero es innecesario y no se recomienda, ya que las RuntimeException se propagan implícitamente. El llamador no está obligado a poner try-catch. 
Solo tendría sentido como documentación para advertir al programador.

15. Respuesta: Se recomiendan controladas para errores que un usuario podría corregir (ej: reintentar una conexión). No controladas para errores que indican que el programador 
cometió un error (ej: pasar un argumento inválido). En lenguajes como C# o Python solo existen las no controladas (es la tendencia moderna).

16. Respuesta: Sí. Se puede relanzar la misma o una nueva.

Relanzar la misma: Para registrar el error (log) y que el nivel superior lo maneje: catch(E e) { log(e); throw e; }.

Lanzar nueva: Para cambiar el tipo de excepción a uno más genérico o adecuado al dominio: catch(IOException e) { throw new MiExcepcionPersonalizada("Fallo de disco"); }.

17. Respuesta: Consiste en envolver una excepción original dentro de otra.
try { ... } catch (SQLException e) {
    throw new ServiceException("Error de base de datos", e); // 'e' es la causa
}
