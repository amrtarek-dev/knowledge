## FreeRTOS Native API 
(used with PlatformIO / raw GCC / Arduino)

| Concept   | API                                                                |
| --------- | ------------------------------------------------------------------ |
| Task      | `xTaskCreate()`                                                    |
| Delay     | `vTaskDelay()`                                                     |
| Queue     | `xQueueCreate()`, `xQueueSend()`, `xQueueReceive()`                |
| Semaphore | `xSemaphoreCreateBinary()`, `xSemaphoreTake()`, `xSemaphoreGive()` |
| Scheduler | `vTaskStartScheduler()`                                            |
- Task Creation: `xTaskCreate()`
``` C
BaseType_t xTaskCreate(
	TaskFunction_t pvTaskCode,
	const char * const pcName,
	configSTACK_DEPTH_TYPE usStackDepth,
	void * pvParamenters,
	UBaseType_t uxPriority,
	TaskHandle_t * pxCreatedTask
)

```
### Blink LED
``` C
#include "FreeRTOS.h"
#include "task.h"

void blinkTask(void *pvParameters)
{
    while (1)
    {
        HAL_GPIO_TogglePin(GPIOC, GPIO_PIN_13);
        vTaskDelay(pdMS_TO_TICKS(1000));
    }
}

int main(void)
{
    HAL_Init();
    SystemClock_Config();

    xTaskCreate(blinkTask, "Blink", 128, NULL, 1, NULL);
    vTaskStartScheduler();

    while (1) {}
}

```

### Create a Queue
``` C
QueueHandle_t queue;

void producer(void *pvParameters)
{
    int value = 42;
    while (1)
    {
        xQueueSend(queue, &value, portMAX_DELAY);
        vTaskDelay(pdMS_TO_TICKS(500));
    }
}

void consumer(void *pvParameters)
{
    int value;
    while (1)
    {
        xQueueReceive(queue, &value, portMAX_DELAY);
        // Do something with value
    }
}

int main(void)
{
    HAL_Init();
    SystemClock_Config();

    queue = xQueueCreate(5, sizeof(int));

    xTaskCreate(producer, "Producer", 128, NULL, 1, NULL);
    xTaskCreate(consumer, "Consumer", 128, NULL, 1, NULL);
    vTaskStartScheduler();
}

```

## CMSIS-RTOS v2 
(used with STM32CubeMX projects)

|Concept|CMSIS-RTOS API|
|---|---|
|Init|`osKernelInitialize()`|
|Start|`osKernelStart()`|
|Task|`osThreadNew()`|
|Delay|`osDelay()`|
|Queue|`osMessageQueueNew()`, `osMessageQueuePut/Get()`|
|Semaphore|`osSemaphoreNew()`, `osSemaphoreAcquire/Release()`|

### Blink LED
``` C
#include "cmsis_os.h"

void blinkTask(void *argument)
{
    for (;;)
    {
        HAL_GPIO_TogglePin(GPIOC, GPIO_PIN_13);
        osDelay(1000);
    }
}

int main(void)
{
    HAL_Init();
    SystemClock_Config();

    osKernelInitialize();
    osThreadNew(blinkTask, NULL, NULL);
    osKernelStart();

    while (1) {}
}
```

### Create a Queue
``` C
osMessageQueueId_t myQueue;

void producer(void *argument)
{
    int value = 123;
    for (;;)
    {
        osMessageQueuePut(myQueue, &value, 0, 0);
        osDelay(500);
    }
}

void consumer(void *argument)
{
    int value;
    for (;;)
    {
        osMessageQueueGet(myQueue, &value, NULL, osWaitForever);
        // Process value
    }
}

int main(void)
{
    HAL_Init();
    SystemClock_Config();

    osKernelInitialize();

    myQueue = osMessageQueueNew(5, sizeof(int), NULL);

    osThreadNew(producer, NULL, NULL);
    osThreadNew(consumer, NULL, NULL);

    osKernelStart();

    while (1) {}
}
```

