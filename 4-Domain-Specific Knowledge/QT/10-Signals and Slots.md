Signals and Slots is the fundamental inner object communication pattern provided by Q, it is a form of the observer pattern.

Normally you can use the designer to generate the signal and slot `connect`, or use the `connect` method in the cpp code.
``` cpp
connect("Sender", "Signal", "Receiver", "Slot")
```

Signal and Slots are many to many relationship, so single signal can have many slots, and single slot can have many signals