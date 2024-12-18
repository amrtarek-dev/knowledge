ADC is acronym for Analog to Digital Converter, which is used to convert analog signals into digital signals, allowing analog data (like voltage) to be processed in digital systems. ADCs are widely used in electronics, especially in microcontrollers and digital signal processing systems, to interpret real-world analog signals, such as temperature, sound, and light, into a format that digital systems can handle.

To convert Analog signal to Digital signals you have to make 3 steps:
- Sample and Hold
- Quantization
- Encoding

## Sample and Hold
it is making a sample every a specific time (Sampling rate: number of samples / second), and hold and read this signal (volt) with minimum frequency (Nyquist Criteria =>  Fs >= 2Fm)

## Quantization
Each sampled value is rounded to the nearest digital level, which are a number of levels depend on the percision that we assign the sampled value to the nearest one, to prepare it to the next step which is the Encoding.

> There is a tolerance produced due to assign the desecrate signal to nearest quatization level which can be increased by reducing the precision, or decreased by increasing the precision.

The quality of an ADC is determined by its **resolution** (number of bits), **sampling rate**, and **accuracy**.
## Encoding
The quantized value is converted into a binary code (a series of digital bits) depend on the nearest quantization level.

## Types of ADC
1. **Flash ADC (Parallel ADC)**:
    - **Operation**: Uses a bank of comparators, each with a different reference voltage, to simultaneously compare the input voltage to the references.
    - **Pros**: Very fast, ideal for high-speed applications.
    - **Cons**: High power consumption, complex circuitry, and expensive, especially for high resolutions.
    - **Use cases**: Video processing, radar systems.
The flash ADC uses a bank of comparators to simultaneously compare the input voltage to multiple reference levels
``` md
       Analog Input
             |
             v
       +-------------+
       | Comparators |
       +-------------+
        |  |  |  |  |
        |  |  |  |  |
       Ref Ref Ref Ref
       Voltages |
               v
        +-------------+
        | Priority    |
        | Encoder     |
        +-------------+
             |
             v
       Digital Output

```
1. **Successive Approximation Register (SAR) ADC**:
    - **Operation**: Uses a binary search algorithm to approximate the input signal step-by-step, finding the digital equivalent one bit at a time.
    - **Pros**: Good balance of speed, resolution, and power efficiency.
    - **Cons**: Moderate speed compared to flash ADC.
    - **Use cases**: General-purpose data acquisition, audio applications.
The SAR ADC uses a binary search algorithm to converge to the correct digital output one bit at a time.
``` md
       Analog Input
             |
             v
       +-------------+
       | Sample &    |
       | Hold Circuit|
       +-------------+
             |
             v
       +-------------+
       | Comparator  |
       +-------------+
             |
             v
       +-------------+
       | SAR Logic   |
       | (Binary     |
       | Search)     |
       +-------------+
             |
             v
       Digital Output

```
1. **Sigma-Delta (ΔΣ) ADC**:
    - **Operation**: Oversamples the input signal with a high-frequency clock, then uses digital filtering and decimation to convert it to a lower sampling rate.
    - **Pros**: High resolution and excellent noise performance, suitable for low-frequency signals.
    - **Cons**: Slow compared to SAR and flash ADCs.
    - **Use cases**: High-precision applications, like audio and instrumentation.
The sigma-delta ADC oversamples the input signal and uses digital filtering for high resolution.
``` md
       Analog Input
             |
             v
       +-------------+
       | Integrator  |
       +-------------+
             |
             v
       +-------------+
       | Comparator  |
       +-------------+
             |
             v
       +-------------+
       | Digital     |
       | Filter      |
       +-------------+
             |
             v
       +-------------+
       | Decimator   |
       +-------------+
             |
             v
       Digital Output
```
1. **Dual Slope (Integrating) ADC**:
    - **Operation**: Measures the time it takes for an integrator’s output to reach a reference level, providing a digital value proportional to the input.
    - **Pros**: High noise immunity and accuracy.
    - **Cons**: Very slow, making it unsuitable for high-speed applications.
    - **Use cases**: Digital voltmeters, industrial control.
The dual-slope ADC charges a capacitor and then discharges it, measuring the time to get a digital value.
``` md
       Analog Input
             |
             v
       +-------------+
       | Integrator  |
       +-------------+
             |
             v
       +-------------+
       | Comparator  |
       +-------------+
             |
             v
       +-------------+
       | Timer /     |
       | Counter     |
       +-------------+
             |
             v
       Digital Output

```
1. **Pipeline ADC**:
    - **Operation**: Combines the principles of flash and SAR ADCs, dividing the conversion process into multiple stages. Each stage converts part of the signal before passing it to the next.
    - **Pros**: Good speed-to-power ratio, moderate resolution.
    - **Cons**: Complexity in design.
    - **Use cases**: Intermediate-speed applications like digital video and communication systems.
The pipeline ADC has multiple stages, each converting part of the input signal, similar to a pipeline.
``` md
       Analog Input
             |
             v
       +-------------+
       | Stage 1     |
       | (Partial    |
       | Conversion) |
       +-------------+
             |
             v
       +-------------+
       | Stage 2     |
       | (Partial    |
       | Conversion) |
       +-------------+
             |
             v
       +-------------+
       | Stage N     |
       | (Final      |
       | Conversion) |
       +-------------+
             |
             v
       Digital Output
```