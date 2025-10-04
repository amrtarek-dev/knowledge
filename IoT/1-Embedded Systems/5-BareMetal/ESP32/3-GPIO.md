Managing GPIO pins involves configuring the pin mode (input/output), reading its state, or setting it to a specific state.

## Using **Arduino Framework**
1. **Setup GPIO**
2. Set GPIO Output
3. Read GPIO Input

Use `pinMode()` to configure the pin as input or output.
``` cpp
#define GPIO_OUTPUT_PIN  2   // GPIO2 for output
#define GPIO_INPUT_PIN   4   // GPIO4 for input

void setup() {
    pinMode(GPIO_OUTPUT_PIN, OUTPUT);  // Configure GPIO2 as output
    pinMode(GPIO_INPUT_PIN, INPUT);   // Configure GPIO4 as input
}
```
Use `digitalWrite()` to set the pin state.
``` cpp
digitalWrite(GPIO_OUTPUT_PIN, HIGH);  // Set GPIO high
digitalWrite(GPIO_OUTPUT_PIN, LOW);   // Set GPIO low
```
Use `digitalRead()` to get the pin state.
``` cpp
int level = digitalRead(GPIO_INPUT_PIN);  // Read GPIO state
```