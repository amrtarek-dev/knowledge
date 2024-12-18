The Puya `PY32F0xx` series HAL provides comprehensive support for managing low-power modes, including seven distinct modes. 

Here’s how to use sleep mode and wake it up, with a focus on providing an example to enter and exit sleep mode:

### **Overview of Low-Power Modes**
1. **Low-Power Run Mode**
    - Reduces frequency and switches the regulator to a low-power state.
2. **Sleep Mode**
    - The Cortex-M0+ core halts, peripherals remain active, and the regulator operates in normal mode.
3. **Low-Power Sleep Mode**
    - Similar to sleep mode but switches the regulator to low power.
4. **Stop 0 Mode**
    - Clocks stop except for LSI/LSE; the main regulator remains on.
5. **Stop 1 Mode**
    - Clocks stop except for LSI/LSE; the low-power regulator is active.


### **Example: Sleep Mode with Wake-Up Using GPIO**

#### **Configuration Steps**
1. **Initialise GPIO for Wake-Up**
    - Configure a GPIO pin as an interrupt source.
2. **Configure NVIC**
    - Enable the NVIC for the corresponding GPIO interrupt.
3. **Enter Sleep Mode**
    - Use `HAL_PWR_EnterSLEEPMode()` to enter sleep mode.
	    - The call to `HAL_PWR_EnterSTOPMode(PWR_MAINREGULATOR_ON, PWR_SLEEPENTRY_WFI)` places the microcontroller in sleep mode. In this state, the core halts while peripherals remain active.
    - Use `HAL_PWR_EnterSTOPMode()` to enter stop mode.
1. **Wake-Up**
    - When the interrupt occurs, the microcontroller exits sleep mode and executes the interrupt handler.

## Example: Code for sleep example

``` cpp
#include "py32f0xx_hal.h"

// GPIO Pin for Wake-Up
#define WAKEUP_GPIO_PIN GPIO_PIN_0
#define WAKEUP_GPIO_PORT GPIOA

// GPIO Interrupt Priority
#define WAKEUP_IRQ_PRIORITY 2

// Function prototypes
void SystemClock_Config(void);
void GPIO_Init_WakeUp(void);
void HAL_GPIO_EXTI_Callback(uint16_t GPIO_Pin);

int main(void)
{
    // HAL Initialization
    HAL_Init();
    SystemClock_Config();
    GPIO_Init_WakeUp();

    // Indicate entering sleep mode (optional, e.g., toggle LED)
    HAL_GPIO_WritePin(GPIOC, GPIO_PIN_13, GPIO_PIN_RESET); 

    // Enter Sleep Mode
    HAL_PWR_EnterSTOPMode(PWR_MAINREGULATOR_ON, PWR_SLEEPENTRY_WFI);

    // Execution resumes here after wake-up
    while (1)
    {
        // Application code
        HAL_GPIO_TogglePin(GPIOC, GPIO_PIN_13);
        HAL_Delay(1000); // Simulated main loop
    }
}

// GPIO Initialization for Wake-Up
void GPIO_Init_WakeUp(void)
{
    __HAL_RCC_GPIOA_CLK_ENABLE();

    GPIO_InitTypeDef GPIO_InitStruct = {0};
    GPIO_InitStruct.Pin = WAKEUP_GPIO_PIN;
    GPIO_InitStruct.Mode = GPIO_MODE_IT_RISING; // Interrupt on rising edge
    GPIO_InitStruct.Pull = GPIO_NOPULL;
    HAL_GPIO_Init(WAKEUP_GPIO_PORT, &GPIO_InitStruct);

    // Enable and set EXTI line Interrupt to the priority
    HAL_NVIC_SetPriority(EXTI0_1_IRQn, WAKEUP_IRQ_PRIORITY, 0);
    HAL_NVIC_EnableIRQ(EXTI0_1_IRQn);
}

// GPIO EXTI Callback
void HAL_GPIO_EXTI_Callback(uint16_t GPIO_Pin)
{
    if (GPIO_Pin == WAKEUP_GPIO_PIN)
    {
        // Wake-Up logic (if needed)
    }
}

// EXTI IRQ Handler
void EXTI0_1_IRQHandler(void)
{
    HAL_GPIO_EXTI_IRQHandler(WAKEUP_GPIO_PIN);
}

// Configure the system clock
void SystemClock_Config(void)
{
    // Add clock configuration code here (not detailed for brevity)
}
```
