It is used to extend the capabilities of the FIBARO system using Lua object-oriented.

https://manuals.fibaro.com/home-center-3-quick-apps/

Quick App Class
``` lua
function QuickApp:myMethod()
	self:debug("Hello from my method")
end
```

the QuickApp class is used to represent the created device, it has built in methods.
`self` is an object that can be used inside the Quick App class.