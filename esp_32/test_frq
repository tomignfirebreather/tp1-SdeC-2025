#include <stdio.h>
#include "driver/gpio.h"
#include "esp_log.h"
#include "soc/rtc.h"
#include "esp_pm.h"

// Definir los pines de los LEDs
#define LED1_PIN GPIO_NUM_1  
#define LED2_PIN GPIO_NUM_22  
#define LED3_PIN GPIO_NUM_23 
#define FREQ_CPU 160  // Frecuencia de la CPU {80 - 160 - 240} Mhz

// Etiqueta para logs
static const char *TAG = "LED_CONTROL";

// Variables para el estado de los LEDs
static bool led2_state = false;
static bool led3_state = true;

// Función para ejecutar un bucle intensivo con sumas de enteros
void integer_sum_loop(uint32_t iterations) {
    uint32_t sum = 0;
    for (uint32_t i = 0; i < iterations; i++) {
        sum += i;
    }
    ESP_LOGV(TAG, "Suma de enteros: %lu", sum);
}

// Función para ejecutar un bucle intensivo con sumas de floats
void float_sum_loop(uint32_t iterations) {
    float sum = 0.0;
    for (uint32_t i = 0; i < iterations; i++) {
        sum += (float)i;
    }
    ESP_LOGV(TAG, "Suma de floats: %.2f", sum);
}

void config_sys(void){

    // Configurar la frecuencia de la CPU
    esp_pm_config_t pm_config = {
        .max_freq_mhz = FREQ_CPU,  // Frecuencia máxima 
        .min_freq_mhz = FREQ_CPU,   // Frecuencia mínima 
        .light_sleep_enable = false // No entrar en light sleep
    };
    ESP_ERROR_CHECK( esp_pm_configure(&pm_config) );

    // Configurar los pines GPIO para los LEDs
    gpio_config_t io_conf = {
        .pin_bit_mask = (1ULL << LED1_PIN) | (1ULL << LED2_PIN) | (1ULL << LED3_PIN),
        .mode = GPIO_MODE_OUTPUT,
        .pull_up_en = GPIO_PULLUP_DISABLE,
        .pull_down_en = GPIO_PULLDOWN_DISABLE,
        .intr_type = GPIO_INTR_DISABLE,
    };
    gpio_config(&io_conf);

    ESP_LOGI(TAG, "Configuración de GPIO completada. Iniciando bucle principal...");

}
void app_main(void) {
    config_sys();
    // Contador para el LED3
    uint32_t counter = 0;

    while (1) {
        if (counter % 1000000 == 0) {  // 
            led2_state = !led2_state;  // Hacer toggle del estado del LED2
            gpio_set_level(LED2_PIN, led2_state);
            ESP_LOGI(TAG, "LED2 toggled: %s", led2_state ? "ON" : "OFF");
        }

        // Cambiar el estado del LED3 cada 5000 ms (5 segundos)
        if (counter % (5000000*7 ) == 0) {  // 
            led3_state = !led3_state;  // Hacer toggle del estado del LED3
            gpio_set_level(LED3_PIN, led3_state);
            ESP_LOGI(TAG, "LED3 toggled: %s", led3_state ? "ON" : "OFF");
        }

        // Incrementar el contador
        counter++;
        // Retardo ajustado según la frecuencia del CPU
        integer_sum_loop(50000000);
        float_sum_loop(50000000);

    }
}
