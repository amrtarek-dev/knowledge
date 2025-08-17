Classes in Kotlin is the only way to make a custom variables by defining:
- Properties
- Primary Constructor
- Functions
- Initialization Blocks
- Secondary Constructors


## Properties
``` kotlin
class Person {
	val name: String = "Jim"
	var weightLbs: Double = 0.0
	var weighKilos: Double
		get() =  weightsLbs / 2.2
		set(value) {
			weightLbs = value * 2.2
		}
}



val p = Person()
val name = p.name

p.weightLbs = 220.0
// Runs weightKilos getter, retruns 100.0
val kilos = p.weightKilos

// Runs weighKilos setter
p.weighKilos = 50.0
// Returns 110.0
val lbs = p.weightLbs
```

## Primary Constructor
You can create constructor in the class by adding a `constructor` keyword (Optional)

``` kotlin
// class Person (name: String, weightLbs: Double)
class Person constructor(name: String, weightLbs: Double) {
	// val name = name
	val name: String = name
	var weightLbs: Double = weightLbs
	var weighKilos: Double
		get() =  weightsLbs / 2.2
		set(value) {
			weightLbs = value * 2.2
		}
}

val p = Person("Bob", 176.0)

val name = p.name
val lbs = p.weightLbs
val kilos = p.weightkilos
```

A cleaner version of the above code:
``` kotlin
class Person(val name: String, var weightLbs: Double) {
	var weighKilos: Double
		get() =  weightsLbs / 2.2
		set(value) {
			weightLbs = value * 2.2
		}
}
```