# Análisis de Rendimiento en la Compilación del Kernel de Linux

## Datos de Evaluación

| **Componente**                   | **Tiempo Promedio (segundos)** | **Error** | **Percentil Rank** | **# Resultados Públicos** |
|----------------------------------|-------------------------------|-----------|--------------------|-------------------------|
| **Intel Core i5-13600K**         | 83                            | ± 3 s     | 53°                | 8                       |
| **AMD Ryzen 9 5900X 12-Core**    | 97                            | ± 6 s     | 48°                | 36                      |
| **AMD Ryzen 9 7950X 16-Core**    | 53                            | ± 3 s     | 70°                | 31                      |

---

## Análisis del Rendimiento

- **Intel Core i5-13600K:**  
  La compilación se completa en un promedio de **83 segundos**. Aunque tiene un rendimiento competitivo, presenta tiempos de compilación mayores comparado con los procesadores AMD evaluados.

- **AMD Ryzen 9 5900X 12-Core:**  
  Con un tiempo promedio de **97 segundos**, este procesador muestra un rendimiento inferior tanto respecto al Intel Core i5-13600K como al Ryzen 9 7950X, lo que indica menor eficiencia global en la tarea de compilación.

- **AMD Ryzen 9 7950X 16-Core:**  
  El tiempo de compilación promedio es de **53 segundos**, siendo el más rápido de los tres. Su **percentil rank** del **70°** destaca su rendimiento superior en esta prueba.

---

## Cálculo de la Aceleración

La aceleración se expresa como el factor de mejora al usar el **AMD Ryzen 9 7950X** comparado con otros procesadores:

- **Respecto al Intel Core i5-13600K:**  
  \[
  \text{Factor de aceleración} = \frac{83 \text{ s}}{53 \text{ s}} \approx 1.57
  \]
  El **Ryzen 9 7950X** es aproximadamente **1.57 veces más rápido** que el **i5-13600K**.

- **Respecto al AMD Ryzen 9 5900X 12-Core:**  
  \[
  \text{Factor de aceleración} = \frac{97 \text{ s}}{53 \text{ s}} \approx 1.83
  \]
  El **Ryzen 9 7950X** es aproximadamente **1.83 veces más rápido** que el **Ryzen 9 5900X**.

---

## Conclusiones Finales

1. **Rendimiento General:**  
   El **AMD Ryzen 9 7950X 16-Core** ofrece el mejor rendimiento, con un tiempo de compilación promedio de **53 segundos**, superando al **Intel Core i5-13600K** (83 s) y al **AMD Ryzen 9 5900X 12-Core** (97 s).

2. **Aceleración:**  
   El **Ryzen 9 7950X** mejora el tiempo de compilación en aproximadamente un **57%** comparado con el **i5-13600K** y un **83%** respecto al **Ryzen 9 5900X**. Esto equivale a factores de aceleración de **1.57x** y **1.83x**, respectivamente.

3. **Implicaciones:**  
   Este resultado evidencia que la arquitectura y los núcleos del **Ryzen 9 7950X** permiten una reducción significativa en los tiempos de compilación. Esto lo convierte en una opción ideal para tareas intensivas donde la eficiencia y el tiempo de respuesta son críticos.