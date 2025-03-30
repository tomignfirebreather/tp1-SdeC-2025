# Análisis de Rendimiento del Sistema

## **Información del Sistema**

**System:**  
- **Kernel:** 6.11.0-21-generic  
- **Arquitectura:** x86_64 (64 bits)  
- **Compilador:** GCC v13.3.0  
- **Escritorio:** Unity  
- **Distribución:** Ubuntu 24.04.2 LTS (Noble Numbat)  

**Machine:**  
- **Tipo:** Laptop  
- **Modelo:** ASUSTeK N56VB v1.0  
- **Placa Madre:** ASUSTeK N56VB v1.0  
- **BIOS:** American Megatrends vN56VB.202 (21/01/2013)  

**CPU:**  
- **Modelo:** Intel® Core™ i3-3120M CPU @ 2.50GHz (Ivy Bridge)  
- **Núcleos:** 2 físicos / 4 lógicos  
- **Frecuencia:** Promedio: 1.3 GHz (Máximo: 2.5 GHz)  
- **Flags:** AVX, HT, LM, NX, PAE, SSE, SSE2, SSE3, SSE4.1, SSE4.2, SSSE3, VMX  

**Gráficos:**  
- **Intel 3rd Gen Core Processor Graphics**  
  - **Driver:** i915 (kernel)  
- **NVIDIA GeForce GT 740M**  
  - **Driver:** nouveau (kernel)  
  - **Temperatura:** 43°C  
- **Webcam:** Sunplus Innovation Asus Webcam (USB)  

---

## **Resumen de Configuración y Tiempos de Función**

- **Configuración de Hardware:**  
  - CPU: Intel® Core™ i3-3120M @ 2.50GHz  
  - SSD: 240 GB  
  - RAM: 8 GB  

- **Tiempos de Ejecución:**  
  - **Tiempo Total:** 19.86 s  
  - **Tiempo de main():** 0.66 s (≈3.3% del total)  
  - **Tiempo de func1():** 11.12 s (≈56% del total)  
  - **Tiempo de func2():** 7.41 s (≈37% del total)  
  - **Tiempo de newfunc():** 0.67 s (≈3.4% del total)  

- **Compilador:** GCC v13.3.0  
- **Grupo:** NullPointerException  

---

## **Análisis de Rendimiento mediante gprof**

### 1. **Análisis de los Tiempos en el Sistema**

#### **Hardware y Entorno:**
El sistema analizado es una laptop con un Intel® Core™ i3-3120M de arquitectura Ivy Bridge con frecuencia nominal de 2.50 GHz. Sin embargo, la velocidad promedio medida es de 1.3 GHz, lo que podría indicar:  
- Modo de ahorro de energía activo.  
- Rendimiento reducido en cargas ligeras.  

#### **Distribución de Tiempos de Ejecución:**
- **main():** 0.66 s (≈3.3% del total)  
- **func1():** 11.12 s (≈56% del total)  
- **func2():** 7.41 s (≈37% del total)  
- **new_func1():** 0.67 s (≈3.4% del total)  

🔍 **Conclusión:**  
Las funciones `func1` y `func2`, con bucles intensivos, concentran el mayor consumo de tiempo. En contraste, `main` y `new_func1` tienen un impacto mínimo, indicando que la carga computacional reside principalmente en las iteraciones de los bucles.

---

### 2. **Comparativa con Otras Configuraciones**

#### **Sistemas de Mayor Rendimiento (i7 o Ryzen 7/9):**
- Tiempos totales mucho menores (a veces inferiores a 5 s).  
- Arquitecturas avanzadas, más núcleos y frecuencias elevadas permiten una reducción significativa de tiempos en bucles iterativos.  

#### **Sistemas Similares (i3 o i5 de Generaciones Anteriores):**
- Rangos de tiempo total entre **18-21 s**, con una distribución similar.  
- El sistema analizado, con **19.86 s**, se ajusta a este rango, consistente con su generación de hardware.  

#### **Análisis Específico de Funciones:**
- **Comparación entre func1 y new_func1:**  
  `new_func1` consume **0.67 s**, mucho menos que `func1` con **11.12 s**.  
  Esto puede atribuirse a:  
  - Diferencias en el número de iteraciones.  
  - Optimizaciones del compilador (ej. inlineación o manejo de bucles).  

- **Análisis de func2:**  
  El tiempo de **7.41 s** es coherente con sistemas similares, reforzando la relación entre iteraciones de bucles y tiempo de ejecución.

---

### 3. **Conclusiones Finales sobre el Rendimiento**

- **Predominio de la Carga en Bucles Intensivos:**  
  La mayor parte del tiempo de ejecución se concentra en funciones con bucles iterativos intensivos (`func1` y `func2`). Se recomienda:  
  - Optimización de algoritmos.  
  - Paralelización y mejoras lógicas en el código.  

- **Comparación Acorde a la Generación del Hardware:**  
  Los tiempos obtenidos son esperados para un **Intel® Core™ i3 de Ivy Bridge**, considerando la frecuencia de operación real frente a la nominal.  

- **Influencia del Compilador y Optimización:**  
  El uso de **GCC 13.3.0** y las opciones de compilación afectan el rendimiento. La diferencia entre `func1` y `new_func1` puede explicarse por optimizaciones del compilador.  

- **Utilidad de gprof en la Identificación de Cuellos de Botella:**  
  `gprof` resulta clave para detectar áreas críticas de optimización. En este caso, los bucles intensivos requieren atención para mejorar el rendimiento global.  

---

## **Resumen**

El análisis de rendimiento realizado mediante `gprof` demuestra que las funciones con bucles intensivos (`func1` y `func2`) consumen la mayor parte del tiempo de ejecución, lo cual es coherente con un equipo basado en un **Intel® Core™ i3 de Ivy Bridge**.  

Comparado con sistemas modernos, el rendimiento es notablemente inferior, pero acorde a las especificaciones de hardware. La identificación de áreas críticas mediante `gprof` permite enfocar esfuerzos de optimización donde más impacto tendrá.



