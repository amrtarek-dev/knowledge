# Electronics V-A
To understand power in electronics terms we need to cover some basics first

## Current
Current is amount of charge that flow in a single point in second (i = d1/dt), that probably doesn't mean much without some point of reference ot metric to scale it by.

So for example 1 C (coulomb) of charge per second or **1 C/s** is equivalent to **1 ampere**

Devices and their Rough Current Needs:

| Devive / System | Average Current Drain |
|:---------------:|:---------------------:|
| Single Gate in a uProcessor |     10 nA |
| Light Emitting Diode (LED)  |     20 mA |
| Digital TTL chip            |     30 mA |
| Single Gate in TTL Chip     |     5  mA |
| LCD Calculator              |     50 mA |
| 27" Television              |     2  A  |
| Personal Computer           |     5  A  |
| Hairdryer                   |     10 A  |

## Voltage
As we mentioned the Current is a flow of charges in a condauctor, so to make this flow which is electrons move we need force.
So we can merge Voltage by saying that it is represinting the energy needed to move charge in conductor.

1 Volt = 1 J (energy)  / 1 C (charge in coulombs).

So How we can generate Voltage?
There are a number of ways to generate voltages, but most are based on three general principles:
- Chemicals
- Magnetic fields
- Photo-electric effect.

### Chemical Batteries:
Batteries are devices that usae chemcicals (dry or wet) to create an accumulation of charge and hence a voltage.
- Primary cells (not chargeable)
- Chargeable batteries

```md
   -     |  +
_______| |______
       | |

Cathode   Anode

```

> The voltage on the battery is the unloaded voltage, and once you add a load to it this volt will drop a bit brcaues of the internal resistance of the battery

## Series and Parallel
To increase the **voltage** you can use the **series** power cells connection and to increase the **current** you can use the **parallel** cells connection.

### Series
The series connection for the power cells increase the Voltage

```md
  -+   -+   -+   -+
__||___||___||___||___
   |    |    |    |
  1.5v 1.5  1.5  1.5

<-------- 6 V --------->
```

## Paralled
The paralled connection for the power cells increase the Current
```md
 _________
 |       |
 | +     | +
____    ____
 __      __
 | -     | -
 _________

1.5v     1.5v
I1       I2

<---- 1.5V ---->
<--I = I1+I2--->

```

## AC and DC
Alternating and Direct Current

## Ohm's Law

For direct Current

V = I x R

I = V / R

R = V / I

For alternating Current

RMS: Root Maean Square
PP: Peak to Peak

Vrms = Vpp X 1/ 2√2