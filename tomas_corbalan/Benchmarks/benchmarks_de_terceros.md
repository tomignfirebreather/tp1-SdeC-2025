# Selección de Benchmarks para Evaluar Rendimiento

La siguiente tabla muestra una selección de los benchmarks que considero que son los más adecuados considerando las tareas más comunes que realizo a diario.

| **Tarea**                                                | **Benchmark Recomendado**                                                   | **Motivo**                                                                                   |
|----------------------------------------------------------|----------------------------------------------------------------------------|---------------------------------------------------------------------------------------------|
| Desarrollo de software en VS Code para desarrollo web    | Phoronix Test Suite (compilación), JetStream 2 (rendimiento JavaScript)     | Evalúa el rendimiento en compilación y ejecución de código web y scripts.                  |
| Desarrollo de firmware en IDEs (MCUXpresso, MPLAB, Arduino) | Phoronix Test Suite (compilación), CoreMark, SPEC CPU                      | Mide el rendimiento en entornos de desarrollo embebido y compilación cruzada.              |
| Navegación web, YouTube                                  | JetStream 2, MotionMark, WebXPRT                                             | Evalúan el rendimiento de navegación, animaciones y aplicaciones web interactivas.        |
| Trabajo con planillas de cálculo y documentos de texto   | PCMark 10, Geekbench (Single-Core), LibreOffice Benchmarks                  | Evalúan la capacidad de procesamiento en tareas ofimáticas comunes.                       |
| Juegos                                                   | 3DMark, Unigine Superposition, Cinebench R23 (Single & Multi-Core)          | Mide el rendimiento gráfico y de CPU en juegos y entornos 3D exigentes.                   |
| Reproductores de audio (Tidal, Spotify)                  | PCMark 10 (Media Playback), AIDA64 (Multimedia)                             | Evalúa la reproducción multimedia y la capacidad multitarea.                             |

## Clasificación de Benchmarks

Los benchmarks seleccionados se pueden clasificar según el tipo de pruebas que realizan, proporcionando una visión más clara de sus objetivos y usos específicos:

- **Benchmarks Sintéticos (CPU, GPU, RAM, Almacenamiento)**: Realizan pruebas diseñadas específicamente para medir el rendimiento de componentes individuales o subsistemas bajo condiciones controladas.  
  Ejemplos: Cinebench R23, 3DMark, AIDA64, CrystalDiskMark, PassMark Memory Test.  

- **Benchmarks del Mundo Real**: Simulan escenarios de uso cotidiano para evaluar el rendimiento en condiciones más realistas y relevantes.  
  Ejemplos: PCMark 10, WebXPRT, Unigine Superposition.  

- **Benchmarks de Aplicaciones**: Ejecutan software real o aplicaciones típicas para medir el rendimiento en tareas comunes.  
  Ejemplos: Phoronix Test Suite, LibreOffice Benchmarks.  

- **Benchmarks de Carga Intensiva**: Evalúan el rendimiento bajo condiciones extremas o máximas de carga para medir la estabilidad y eficiencia del hardware.  
  Ejemplos: SPEC CPU, FurMark, MemTest86.  

## Clasificación por Componente Evaluado

Otra forma de clasificar los benchmarks es según el componente específico que analizan:

- **CPU (Procesador)**: Miden el rendimiento del procesador en tareas computacionales.  
  Ejemplos: Cinebench R23, SPEC CPU, Geekbench.  

- **GPU (Tarjeta Gráfica)**: Evalúan el rendimiento gráfico y capacidades de procesamiento paralelo.  
  Ejemplos: 3DMark, Unigine Superposition, FurMark.  

- **RAM (Memoria Principal)**: Analizan el rendimiento de la memoria y la latencia.  
  Ejemplos: PassMark Memory Test, AIDA64, MemTest86.  

- **Almacenamiento (Discos Duros y SSDs)**: Evalúan el rendimiento en lectura/escritura y latencia.  
  Ejemplos: CrystalDiskMark, ATTO Disk Benchmark.  

Estas clasificaciones permiten una visión integral del rendimiento de un sistema, abordando tanto el rendimiento general como el específico de cada componente.
