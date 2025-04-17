Functions in Kotlin can be declared by `fun` keyword and it accept parameters and all functions returns a value, if no useful value returned it returns `Unit`

``` kotlin
class Person(val name: String, var weightLbs: Double) {
	var weighKilos: Double
		get() =  weightsLbs / 2.2
		set(value) {
			weightLbs = value * 2.2

	// Unit here is optional
	fun eatDessert(addedIceCream: Boolean = true): Unit {
		weightLbs += if (addedIceCream) 4.0 else 2.0
	}
	// with default value
	fun calcGoalWeightLbs(lbsToLose: Double = 10.0): Double {
		return weightLbs - lbsToLose
	}
}


val p = person("Bob", 176.0)

p.eatDessert(false)
// Returns 178.0
val lbs = p.weightLbs

p.eatDessert()
// Returns 182.0
lbs = p.weightLbs
// lbsToLose is the default (10), so it Returns 172
val gw = p.calcGoalWeighlbs()
```

Passing the parameters can be:
1. Positionally (using the position of parameter)
2. Namely (using the name of the parameter)

``` kotlin
val p1 = Person("Jim", 185.0)
val p2 = Person(weightLbs = 185.0, name = "Jim")
```