System:
  Kernel: 6.11.0-21-generic arch: x86_64 bits: 64 compiler: gcc v: 13.3.0
  Desktop: Unity v: N/A Distro: Ubuntu 24.04.2 LTS (Noble Numbat)
Machine:
  Type: Laptop System: ASUSTeK product: N56VB v: 1.0
    serial: <superuser required>
  Mobo: ASUSTeK model: N56VB v: 1.0 serial: <superuser required>
    BIOS: American Megatrends v: N56VB.202 date: 01/21/2013
CPU:
  Info: dual core model: Intel(R) Core(TM) i3-3120M CPU @ 2.50GHz bits: 64 type: MT MCP
    arch: Ivy Bridge rev: 9 cache: L1: 128 KiB L2: 512 KiB L3: 3 MiB
  Speed (MHz): avg: 1298 high: 1593 min/max: 1200/2500 cores: 1: 1200
    2: 1200 3: 1200 4: 1593 bogomips: 19954
  Flags: avx ht lm nx pae sse sse2 sse3 sse4_1 sse4_2 ssse3 vmx
Graphics:
  Device-1: Intel 3rd Gen Core processor Graphics vendor: ASUSTeK
    driver: i915 v: kernel arch: Gen-7 bus-ID: 00:02.0
  Device-2: NVIDIA GK107M [GeForce GT 740M] vendor: ASUSTeK
    driver: nouveau v: kernel arch: Kepler bus-ID: 01:00.0 temp: 43.0 C
  Device-3: Sunplus Innovation Asus Webcam driver: uvcvideo type: USB
    bus-ID: 1-1.3:4

Resumen Configuracion de hardware y tiempos de función:
configuración: Intel(R) Core(TM) i3-3120M CPU @ 2.50GHz - ssd 240GB - ram 8GB
tiempo total: 19.86 s
tiempo main: 0.66 s
tiempo en func1: 11.12 s
tiempo en func2: 7.41 s
tiempo en newfunc: 0.67 s
grupo: NullPointerException
compiler gcc version: 13.3.0

Análisis de Rendimiento mediante gprof
1. Análisis de los tiempos en el sistema

    Hardware y entorno:
    El sistema analizado corresponde a una laptop equipada con un procesador Intel® Core™ i3-3120M (arquitectura Ivy Bridge) con una frecuencia nominal de 2.50 GHz. No obstante, se observa que la velocidad promedio reportada es de aproximadamente 1.3 GHz, lo que puede indicar que el procesador opera en modo de ahorro de energía o que el rendimiento real en cargas sencillas es inferior a la frecuencia nominal.

    Distribución de tiempos:

        Tiempo total: 19.86 s

        main(): 0.66 s (≈3.3% del total)

        func1(): 11.12 s (≈56% del total)

        func2(): 7.41 s (≈37% del total)

        new_func1(): 0.67 s (≈3.4% del total)

    Se constata que las funciones con bucles intensivos (func1 y func2) son las responsables del mayor consumo de tiempo. Por otro lado, las funciones main y new_func1 consumen una proporción mínima del tiempo total, lo que evidencia que la carga computacional reside principalmente en los bucles iterativos.

2. Comparativa con otras configuraciones

La comparación con datos de otros sistemas permite destacar los siguientes puntos:

    Sistemas de mayor rendimiento (por ejemplo, i7 o Ryzen 7/9):

        Se observa que sistemas modernos de alta gama presentan tiempos totales considerablemente inferiores (incluso por debajo de 5 s en algunos casos).

        La reducción en los tiempos de ejecución se refleja igualmente en las funciones evaluadas, dado que bucles con iteraciones similares se ejecutan de forma mucho más rápida gracias a arquitecturas avanzadas, mayor cantidad de núcleos y frecuencias de operación elevadas.

    Sistemas con características similares (i3 o i5 de generaciones anteriores):

        Diversos sistemas equipados con procesadores i3 o algunos i5 muestran tiempos totales en el rango de 18–21 s, con una distribución similar en la que las funciones auxiliares consumen muy poco tiempo en comparación con las secciones de código intensivas en iteraciones.

        El sistema en análisis, con un tiempo total de 19.86 s, se encuentra dentro de este rango, lo que es coherente con el rendimiento esperado de un Intel® Core™ i3 de la generación Ivy Bridge, teniendo en cuenta la diferencia entre la frecuencia nominal y la frecuencia de operación en condiciones reales.

    Aspectos específicos de cada función:

        Comparación entre func1 y new_func1:
        Aunque ambas funciones contienen bucles con un alto número de iteraciones, se observa que new_func1 consume significativamente menos tiempo (0.67 s) en comparación con func1 (11.12 s). Esta diferencia podría atribuirse tanto a la cantidad efectiva de iteraciones como a las optimizaciones aplicadas por el compilador (por ejemplo, posibles decisiones de inlineación o diferencias en la evaluación de los límites de los bucles).

        Análisis de func2:
        El tiempo medido para func2 (7.41 s) es comparable con el observado en sistemas de características similares, lo cual refuerza la relación proporcional entre el número de iteraciones en los bucles y el tiempo de ejecución registrado.

3. Conclusiones Finales sobre el Rendimiento

    Predominio de la carga en bucles intensivos:
    Los resultados indican que la mayor parte del tiempo de ejecución se concentra en las funciones que ejecutan bucles con numerosas iteraciones (func1 y func2). Este hallazgo subraya la importancia de optimizar dichos algoritmos o considerar técnicas de paralelización y ajustes en la lógica, especialmente en aplicaciones con secciones de código altamente demandantes.

    Comparación acorde a la generación del hardware:
    Los tiempos obtenidos en el sistema se ajustan a lo esperado para un equipo con un Intel® Core™ i3 de generación Ivy Bridge, en particular cuando se toma en cuenta que la frecuencia de operación en uso real es inferior a la nominal. Mientras que equipos de alta gama presentan tiempos de ejecución significativamente menores, el desempeño del sistema analizado resulta coherente con sus especificaciones técnicas.

    Influencia del compilador y las optimizaciones:
    El uso de GCC 13.3.0 y las configuraciones de compilación empleadas pueden influir en la optimización de los bucles. Las diferencias en el tiempo de ejecución entre funciones aparentemente similares (como entre func1 y new_func1) pueden explicarse en parte por decisiones específicas del compilador relacionadas con la optimización de código.

    Utilidad de gprof en la identificación de cuellos de botella:
    La herramienta gprof se revela como un recurso valioso para identificar las secciones del código que requieren optimización. En este caso, la concentración de tiempo de ejecución en las funciones que realizan bucles intensivos invita a enfocar esfuerzos en la mejora de estas secciones para lograr un rendimiento global superior.

Resumen

En conclusión, el análisis del rendimiento del sistema mediante gprof muestra que las funciones encargadas de ejecutar bucles intensivos (func1 y func2) consumen la mayor parte del tiempo total de ejecución, lo cual es consistente con las expectativas para un sistema basado en un Intel® Core™ i3 de generación Ivy Bridge en condiciones de operación reales. La comparación con otras configuraciones evidencia que, si bien equipos de alta gama logran tiempos de ejecución significativamente inferiores, el desempeño del sistema en análisis se ajusta a las características de hardware y configuración empleadas. Finalmente, el uso de herramientas de perfilado como gprof resulta fundamental para identificar áreas de mejora y optimizar aplicaciones con alta demanda computacional.

