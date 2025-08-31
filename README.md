# tarea-2-risc-cisc-arqui-I
Tarea 2 - RISC vs CISC del curso Arquitectura de Computadores I, IIS 2025

### ¿Por qué las arquitecturas RISC suelen ser más predecibles en sus tiempos de ejecución que las arquitecturas CISC?

Las instrucciones RISC tienen un formato fijo y al ejecutarse haciendolo pocos ciclos de reloj, el tiempo de ejecución es más regular y fácil de saber con anticipación. En cambio, las instrucciones CISC pueden variar mucho en complejidad y duración, algunas requieren de pocos ciclos y otras muchos ciclos, lo cual dificulta realizar la predicción.
También, la uniformidad de las instrucciones RISC permite la implementación de pipelines más predecibles y eficientes, ya que cada etapa puede estar optimizada para un conjunto reducido y regular de operaciones; mientras que en CISC, la variabilidad de las instrucciones complica el diseño del pipeline y su predictibilidad. Además, en RISC se utiliza una lógica de control más sencilla, mientras que en CISC hay una dependencia de programas micro internos para ejecutar instrucciones complejas, introduciendo latencias variables y menos predictibles.

---

### ¿En qué situaciones es importante la predictibilidad?

La predictibilidad de los tiempos de ejecución es fundamental en:

- **Sistemas embebidos críticos:**  
  Por ejemplo, en la industria automotriz, la aeroespacial o equipos médicos, donde garantizar tiempos máximos de respuesta es vital para la seguridad y confiabilidad.

- **Sistemas en tiempo real:**  
  Donde se deben cumplir plazos estrictos para la ejecución de ciertas tareas. Un sistema impredecible puede causar fallos críticos.

- **Aplicaciones concurrentes o que utilizan paralelismo:**  
  En estos casos, la sincronización y el balanceo de carga requieren que las operaciones tengan duraciones predecibles para evitar cuellos de botella y bloqueos.

---
### Resultados de ejecución del programa de Python sobre el comportamiento de RISC y CISC

Los vectores iniciales utilizados para la simulación son:

- **Vector A**: `[1, 2, 3, 4, 5, 6, 7, 8, 9, 10]`
- **Vector B**: `[11, 12, 13, 14, 15, 16, 17, 18, 19, 20]`

La siguiente imagen muestra la salida del programa ejecutando la suma de los dos vectores para comportamiento en CISC y RISC:

![Resultados de la suma de vectores en CISC y RISC](https://media.discordapp.net/attachments/751659039133270056/1411234870646013992/image.png?ex=68b3ea64&is=68b298e4&hm=c873ff974956e4261c6ca4b44e741e1caf63a21f5deaa3000b512c6d617eb810&=&format=webp&quality=lossless&width=910&height=420)

- **Resultado del vector suma** (para ambas arquitecturas):  
  `[12, 14, 16, 18, 20, 22, 24, 26, 28, 30]`

- **CISC**  
  - Instrucciones ejecutadas: **10** (una instrucción SUMMEM por elemento)
  - Ciclos totales: **30** (cada instrucción SUMMEM tarda 3 ciclos)

- **RISC**  
  - Instrucciones ejecutadas: **40** (4 instrucciones por elemento: LOAD, LOAD, ADD, STORE)
  - Ciclos totales: **40** (cada instrucción RISC tarda 1 ciclo)

A partir de estos resultados se muestra cómo, aunque RISC ejecuta más instrucciones para lograr la misma tarea, el tiempo por instrucción es uniforme y predecible, mientras que CISC puede ser más eficiente en cantidad de instrucciones pero con instrucciones individuales más complejas y costosas en ciclos.

### Referencias

1. [¿Qué es la arquitectura RISC? - IBM Documentation](https://www.ibm.com/docs/es/aix/7.2?topic=architectures-risc-architecture)
2. [David A. Patterson, John L. Hennessy. Digital Design and Computer Architecture: RISC-V Edition](https://mrce.in/ebooks/Digital%20Design%20&%20Computer%20Architecture%20RISC-V%20Edition.pdf)
3. [RISC vs. CISC Architectures - GeeksforGeeks](https://www.geeksforgeeks.org/difference-between-risc-and-cisc-architecture/)
5. [Why is RISC architecture more predictable than CISC in execution time? (Stack Overflow)](https://stackoverflow.com/questions/76721312/why-is-risc-architecture-more-predictable-than-cisc-in-execution-time) 
---
