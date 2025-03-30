### Resultados Esperados

| Frecuencia | Tiempo(s) |     
| ---------- | ------ | 
| 80 MHz     | 16.51     |     
| 160 MHz    | 8.8  |     
| 240 MHz    | 5.5    |     

    Nota: Los flotantes son ~10-100x más lentos que los enteros en ESP32

Conexiones Hardware

    LED1 → GPIO 22

    LED2 → GPIO 123

    Resistores: 220Ω en serie

Cómo Usar

    Ajustar FREQ_CPU en el código

    Cargar programa al ESP32

    Observar frecuencia de parpadeo de los LEDs
