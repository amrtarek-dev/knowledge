It is a single focused thing that the user can do, so it:
- Serve as a place to present UI
- It has a lifecycle which are a series of methods.

## Activity UI (XML)
it consists of:
- View class 
	- which is the basic UI building block, drawing & event handling + many specialized classes.
		- View classes for Buttons, images, etc...
	- ViewGroup:
		- It holds other views, also know a container class.
		- Layout: They are special invisible ViewGroup which handle the view positioning.

### Layout Classes
Layout classes are an important part of activity UI development because activity UIs need to be responsive, and this is because Android supports a very rich set of different devices. 
And a specific display characteristic of those devices can vary a great deal, so our UIs must adapt to these differing display characteristics.

Do not use absolute positioning, because it would be limiting, instead use an adaptive layout.
- FrameLayout: it has only one direct child, which provides a blocked-out area.
- LinearLayout: it puts the things inline (vertically or Horizontally), and support weighted distribution.
- RelativeLayout: it puts the things in relative positioning to parent or each other

Working with those layout classes can sometimes become challenging because oftentimes we'd have to use a complex grouping of nested layout classes to achieve a desired appearance. 
These complex nestings made the UIs hard to design and oftentimes resulted in a UI that was slow to render.

So to address these challenges, we now have the ConstraintLayout class.

#### ConstraintLayout Class
ConstraintLayout combines many of the capabilities of other layout classes and, as a result, is often the only layout class needed, and it is deeply supported by the Android Studio.

it support:
- Relative size/position
- Ratio-based size/position
- weighted relationships
- Guideline-based size/position
- Group size/position distribution (chains)

>Should set horizontal & vertical constraints, first element will be positioned at 0,0 without constraints.
>Setting constraints with the designer (drag circle at mid-line to relationship)
>Setting fixed size with the designer (drag corner squares)
>It works in dp (device independant pixel)

## Activity Code (Java/Kotlin)
In the Kotlin source code where we provide the activity's functionality, and that functionality is a key part of our overall user experience.

There is no implicit relationship between layout and the code, the code must load layout by using `setContentView` method which is a part of the generated class `R`, which allows us to access app resources.

So to access the layout you have to use `R.layout.the_layout_name`, and then you can interact with views in the layout by the view ID.

``` kotlin
setContentView(R.layout.activity_main)
```

## Activity Interaction
Because Activities are distinct from one another, activity can not create another activity, but we relay on `intents` to interact.

So when activity want to start another activity:
- Create an instant of intent class
- Start activity by calling `startActivity` method and pass the created intent to method.
- The system will get this activity and run it.