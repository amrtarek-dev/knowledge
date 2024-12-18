To make an automatic code execution for class there are 2 ways to do so:
- Initializer Blocks
- Secondary Constructor

## Initializer Blocks
it is :
- Always runs during constructor
- You can have multiple initlializer blocks if desired
- All of them will run every time

``` kotlin
init {
 // the code needs to be initilized
}
```
## Secondary Constructor
it is:
- Runs only when used
- can have multiple if desired
- Runs when used to construct instance
- Code runs after all initializer blocks
- Must delegate to primary constructor if type includes one.