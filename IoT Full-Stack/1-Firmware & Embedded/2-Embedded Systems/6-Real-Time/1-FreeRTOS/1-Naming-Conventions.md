# Data types
- TickType_t: to count the system ticks
	- The size depends on the configuration and settings **uint16_t** or **uint32_t**
- BaseType_t: for variables where the size depends on the architecture of the system
	- uint16_t or uint32_t
used to ensure portability across different architectures

## Variables Types
- Variables are **prefixed** with their types
	- c: char
	- s: short/uint16_t
	- l: long/int32t
	- u: unsigned
	- p: pointer
	- x: BaseType_t or any other nonstandard types

## Function Names
- Functions are **prefixed** with
	- return type and the name of the file
		- v: for void

``` C
vTaskPrioritySet()

// return void
// defined in task.c
```
- `xTaskCreate(task_function, "Task_Name", Stack_Size, TaskPrameter, Priority, TaskHandle)`
- `vTaskStartScheduler()`

## Macro Names
- Macro in uppercase
- Prefix in lowercase (indicates macro definition file)
``` C
portMAX_DEALY

// located in portable.h
// MAX_DELAY is the macro name
```
- `taskENTER_CRITICAL()` : in task.h (when enter a critical code which disable interrupt to protect shared resources)
- `pdTRUE` : in projdefs.h (For successful operations)
- `configUSE_PREEMPTION` : in freeRTOSConfig.h (enable/disable preemption scheduling in RTOS)