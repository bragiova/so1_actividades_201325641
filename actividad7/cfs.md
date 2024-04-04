## Completely Fair Scheduler (CFS)

### Funcionamiento y Características Principales
- **Scheduling sin previsión** CFS no requiere alguna predicción sobre la duración de las tareas ya que utiliza información en tiempo real de la utilización del CPU en cada proceso para así tomar decisiones de planificación.
- **Prioridades Dinámicas** Utiliza una prioridad dinámica basada en el tiempo de ejecución de los procesos. Cuando los procesos han utilizado un tiempo menor de CPU, reciben una prioridad más alta en comparación a aquellos que han utilizado un mayor tiempo de CPU, los cuales recibirán una prioridad baja.  
    * Este lo hace en función de su comportamiento pasado, lo cual indica que si un proceso ha consumido menos tiempo de CPU, recibirá una prioridad alta en su próxima ejecución.
    * Utiliza el quantum de tiempo virtual para determinar cuánto tiempo de CPU debe recibir un proceso en relación con otros.
- **Quantum de Tiempo Virtual** CFS asigna un quantum de tiempo virtual a cada proceso en base a su prioridad y tiempo de CPU utilizado, lo cual ayuda a mantener una justicia relativa en la distribución del tiempo de CPU.
    * Cuanto menor sea el tiempo de CPU utilizado por un proceso, mayor será su quantum de tiempo virtual, lo que significa que obtendrá más tiempo de CPU en su futura ejecución.
    * Esto distribución de tiempo garantiza que los procesos más eficientes reciban más tiempo de CPU en comparación con aquellos que consumen más recursos.
- **Justicia** Se intenta garantizar una distribución justa del tiempo de CPU entre todos los procesos en ejecución.
    * Los procesos no se interrumpen abruptamente mientras se ejecutan, sino que esperan a que su quantum de tiempo virtual expire antes de ser reevaluados para su ejecución.
- **Balanceo de Carga** El CFS utiliza un balanceo de carga dinámico que busca distribuir la carga de trabajo en todos los núcleos del CPU, incrementando la eficiencia y rendimiento del sistema.
    * Esta distribución de carga se logra mediante la asignación de procesos en ejecución en función de la carga de trabajo actual de cada núcleo.

#### Referencias
- <https://1library.co/document/zkxj9d1y-planificador-de-linux-scheduler.html>
- <https://en.wikipedia.org/wiki/Completely_Fair_Scheduler>
- <https://opensource.com/article/19/2/fair-scheduling-linux>