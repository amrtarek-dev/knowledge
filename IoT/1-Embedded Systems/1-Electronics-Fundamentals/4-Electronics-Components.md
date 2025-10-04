# Electronics Components

## Resistor
A resistor is a passive component that implements electrical resistance as a circuit element by resist of the current flow.
it has 2 types:
- precision resistor
- Non precision resistor (configurable)

### Color Code
The resistors have a color code that says how much resistance it could generate.

```md
    /\    /\
___/  \  /  \___
       \/
```

The equation to calculate the resistance from the color code is:

R = (10 * b1 + b2)* 10^b3  +/- b4 


| Band    | b1  | b2  | b3  | b4  |
|:-------:|:---:|:---:|:---:|:---:|
| Silver  |     |     | -1  | +/-10% |
| Gold    |     |     |  -2 | +/-5% |
| Black   | 0   | 0   | 0   |      |
| Brown   | 1   | 1   | 1   |      |
| Red     | 2   | 2   | 2   |      |
| Orange  | 3   | 3   | 3   |      |
| Yellow  | 4   | 4   | 4   |      |
| Green   | 5   | 5   | 5   |      |
| Blue    | 6   | 6   | 6   |      |
| Violet  | 7   | 7   | 7   |      |
| Grey    | 8   | 8   | 8   |      |
| white   | 9   | 9   | 9   |      |

## Capacitor
Capacitors are energy storage devices that are typically used in analog circuits to store energy and filter signals.
- Nonpolarized (Mono)
- Polarized

```md
---||---
```
It consist usually of two parallel plates (Metal) of equal length separated by some distance of Dielectric which determine the capacitance of the capacitor. (**C**) which is measured in farads (F)

> Capacitors have **Voltage rating** which is the maximum voltage that can be applied to a capacitor before it breaks down.

Capacitors types:
- **Electrolytic/Polarized** : they are aluminum canister electrolytic capacitor with capacity from 0.001 microF to 1 F ( High voltage, relatively high frequency stability and tolerance)
- **Ceramic** : from 1 picoF to 1 microF (medium voltage, fairly stable, and medium good frequency, good for bypass circuits)
- **Mica** : from 1 picoF to 20,000 pF (Very high performance of high frequency applications, high voltage, high stability)
- **Tantalum** : From 0.1 microF to 1000 mircroF, very low leakage, low inductance, best for power supply filters and bypass capacitors for chips.


## Inductors
Simply it is a coils of wire, and it is generating a Magnetic Flux when current flow in it.
and when the source of power stops the magnetic flux start to fade gradually (Changing magnetic field produce a current) and this will generate a reverse current (opposite the old source direction) for a while. (What the capacitor does normally).
and it is measured by Henrys H.
> In many cases you can use Capacitors in place of Inductors and vise versa.

symbol:
a normal coil or a coil with 2 lines under it (it has a solid core).

Normally they are used in filters and Power supply circuits

> Ideal Capacitors and Inductors are reactive and do not dissipate power.

> The main difference between Capacitors and Indicators is the frequency pass and block,
> so Capacitors are passing the high frequency, but the inductors blocks the high frequencies.

To read an Inductor if it has 3 digits it will represent micro henry ('value'value'* 10 'value')
ex:
100 = 10 micro henry
221 = 22 * 10^1 = 220

> Axial inductors is looks like the normal resistors, even with colors on it but it is not follow the resistor colors code.

### Transformer
it is an implementation of inductors, which has 2 inductors (Primary, and secondary) with solid core, once the current run in the primary a magnetic flux will be created and the second coil will have this flux and generate a current depend on the coil turn numbers.
Only AC volt.
number turns of inductor 1 over 2 = volt 1 over vol2 2
N1 / N2 = V1 / V2
it used to step up and step down the voltages.

### Diode
Diode is an example of Semiconductor devices which use the P-N junction, 
Positive and Negative junction has a depletion region that has a saturated P and N charge and once you add an external volt on there are 2 situations:
- positive to positive (Anode) and negative to negative(Cathode), which will make the depletion region (The Gate) smaller and that will allow the current to flow. (forward biases)
- Positive to negative, which will increase the depletion region, close the gate (high resistance) (reverse biases).

Types:
- normal diode (for single direction current)
- Zener Diode (break down diode)(stable the voltage (reference) on the reverse connection)
- Schottky diode (low forward voltage drop, fast switching (RF applications))
- Light Emitting Diode
- Photo diodes (generate current when exposed to light)

### Transistor
