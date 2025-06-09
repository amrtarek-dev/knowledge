
``` C
#include <stdio.h>

int main(void) {
    // Let's assume we use an unsigned integer to hold bit flags.
    unsigned int flags = 0;  // Initially, all bits are 0.
    
    // Define the bit position you want to manipulate.
    // For example, we'll work with bit position 3 (counting from 0).
    unsigned int bit_position = 3;
    
    // Create a bit mask using a left shift.
    // This mask will have only the bit at 'bit_position' set to 1.
    unsigned int mask = 1 << bit_position; // For bit 3, mask is 0b00001000.
    
    // ----------------------------------------------------------------
    // SETTING A BIT:
    // To set a bit (force it to 1) without changing other bits, use bitwise OR.
    flags |= mask;
    // Now, bit 3 in 'flags' is set.
    
    // Checking if the bit is set:
    if (flags & mask) {
        printf("After setting: Bit %u is set.\n", bit_position);
    } else {
        printf("After setting: Bit %u is not set.\n", bit_position);
    }
    
    // ----------------------------------------------------------------
    // CLEARING A BIT:
    // To clear a bit (force it to 0) without changing other bits, use bitwise AND with the complement of the mask.
    flags &= ~mask;
    // Now, bit 3 in 'flags' is cleared.
    
    // Checking if the bit is clear:
    if (!(flags & mask)) {
        printf("After clearing: Bit %u is clear.\n", bit_position);
    } else {
        printf("After clearing: Bit %u is not clear.\n", bit_position);
    }
    
    // ----------------------------------------------------------------
    // TOGGLING A BIT (Bonus):
    // Toggling flips the bit: if it's 1 it becomes 0, and if it's 0 it becomes 1.
    flags ^= mask;  // Toggle bit 3.
    printf("After toggling: Bit %u state: %s\n", bit_position,
           (flags & mask) ? "set" : "clear");
    
    // Toggling again will revert the bit to its original state.
    flags ^= mask;
    printf("After toggling again: Bit %u state: %s\n", bit_position,
           (flags & mask) ? "set" : "clear");
    
    return 0;
}
```
