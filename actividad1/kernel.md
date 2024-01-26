## Tipos de Kernel

### Kernel Monolítico
- Tipo de Kernel que es el responsable de la gestión de memoria y procesos, así como la comunicación de los procesos y proporciona funciones de soporte para el hardware y drivers.
- Facilita la abstracción del hardware subyacente sin tomar en cuenta el grado de potencia o variedad.
- Son núcleos complejos de manejar.
- Este tipo de kernel está programado de forma no modular y puede llegar a tener un tamaño demasiado grande.
- Todos los componentes funcionales del kernel tienen acceso a todas las estructuras de datos internas y sus rutinas.
- Al tener que incorporar códigos que operen con varios dispositivos, canales de interrupción y demás operadores del hardware, realizarle modificaciones requiere una compilación del núcleo y reinicio del sistema.

### MicroKernel
- Tiene un diseño pequeño para que en caso de fallo no se paralice todo el sistema operativo.
- Se encaraga de ofrecer las funciones básicas de los distintos dispositivos, administrando lo que tenga CPU, IPC y memoria.
- Al ser más compactos, brindan un conjunto reducido de abstracciones básicas del hardware.
- Todos los servicios que generalmente son provistos por el núcleo, se ejecutan como procesos servidores en espacio de usuario.
- Tiene la ventaja de facilitar la creación y depuración de controladores, descentralización de fallos y una reducción de complejidad.
- Al ser compilado con lo básico que necesita el sistema operativo, el resto de funcionalidades son añadidas mediante módulos externos al núcleo, lo cual proporciona flexibilidad y facilidad de ampliación.

### Kernel Híbrido
- Es una combinación de un Kernel Monolítico y un MicroKernel.
- Incluyen código extra para mejorar el rendimiento.
- El sistema puede seguir en funcionamiento al necesitar cargar controladores de dispositivos y extensiones del sistema.
- Los controladores pueden ser detenidos por unos momentos para actividades más importantes, bajo ciertas condiciones.
- Se considera una gran modificación del MicroKernel.

### ExoNúcleos
- Tiene la idea de permitir al desarrollador tomar las decisiones referentes al rendimiento del hardware.
- Los sistemas con este tipo de Núcleo son llamados sistemas operativos verticalmente estructurados.
- Son muy pequeños ya que se limitan a su funcionalidad de proteger y multiplexado de recursos.

---
# User vs Kernel Mode

| Criterio | Kernel Mode       | User Mode |
| -------- | ----------------- | --------- |
| Interrupciones | Puede parar el sistema operativo | Un proceso puede fallar si ocurre una interrupción |
| Acceso a recursos | El programa tiene acceso directo y sin restricciones | Para acceder a los recursos, debe de hacer una llada al sistema |
| Restricciones | No hay restricciones | No puede acceder directamente a los programas del kernel |
| Bit de modo | El bit en modo Kernel es 0 | El bit en modo usuario es 1 |
| Bloqueos del sistema | Un bloqueo es severo | Se puede recuperar un bloqueo reanudando la sesión |
| Funcionalidad | Puede referirse a cualquier bloque de memoria en el sistema, además de dirigir a la CPU en la ejecución de instrucciones | Implica que la información no puede ejecutarse por sí sola y no puede hacer referencia a un bloque de memoria, se necesita una API para lograrlo

---
# Interruptions vs Traps

| Interruption | Trap |
| -------- | ----------------- |
| Es una señal emitida por un disposito del hardware | Es emitida por un programa de usuario |
| No todas las interrupciones son traps | Todos los traps son interrupciones |
| Procesos Asincrónicos | Procesos Sincrónicos |
| Conocido también como una interrupción por hardware | Se conoce como una interrupción por sofware |
| Generado por un SO y una instrucción de un programa de usuario | Generado por una instrucción de un programa de usuario |
| Podría ocurrir desde los dispositivos de hardware y software | Puede ocurrir solo desde un dispositivo de software |

#### Referencias
- <https://www.ionos.es/digitalguide/servidores/know-how/que-es-el-kernel/>
- <https://keepcoding.io/blog/que-es-el-kernel/>
- <https://wizbyte.wordpress.com/2014/07/04/tipos-de-kernel/>
- <https://bligoo.com.ve/kernel/>
- <https://www.tutorialspoint.com/User-Mode-vs-Kernel-Mode>
- <https://www.geeksforgeeks.org/difference-between-user-mode-and-kernel-mode/>
- <https://www.baeldung.com/cs/os-trap-vs-interrupt>
- <https://www.javatpoint.com/trap-vs-interrupt-in-operating-system>