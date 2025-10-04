
The full screen option in the e-learning module sometimes makes troubles, so we will disable it by making 2 steps:
- remove the fullscreen = 1 from the url
- remove the fullscreen icon at top right

## From URL
To remove the fullscreen = 1 from the url you have to edit a js file in website_slides addons.

`odoo/addons/website_slides/static/src/js/slides_course_slides_list.js`

``` python
_updateHref: function () {     this.$(".o_wslides_js_slides_list_slide_link").each(function (){
    var href = $(this).attr('href');
    var operator = href.indexOf('?') !== -1 ? '&' : '?';
    $(this).attr('href', href + operator + "fullscreen=1");
};
```
You need to change the fullscreen=1 to =0

To do so you need to:
1. define a module to add your js assets located in `static/src/js` and name it for example `slides_course_slides_list_custom.js`:

```js
odoo.define('e_learning.slides_course_slides_list_custom', function (require) {
	"use strict";
	var SlidesCourseSlidesList = require('website_slides.SlidesCourseSlidesList');
	
	SlidesCourseSlidesList.include({
		_updateHref: function () {
		this.$(".o_wslides_js_slides_list_slide_link").each(function (){
			var href = $(this).attr('href');
			var operator = href.indexOf('?') !== -1 ? '&' : '?';
			$(this).attr('href', href + operator + "fullscreen=0");
			});
		},
	});
});
```

2. There is a fullscreen button you need to disable it, it is in `website_slides/views/websites_slides_templates_lesson.xml`
you need to remove this code from the file:
```xml
<a class="btn btn-light border ms-2 my-1" role="button" t-att-href="'/slides/slide/%s?fullscreen=1' % (slug(slide))">
	<i class="fa fa-desktop me-xl-2 my-1"/>
	<span class="d-none d-xl-inline-block">Fullscreen</span>
</a>
```

To do so you have to make a xml file in your module in `/views/` let's call it `website_slides_templates_lesson.xml`

And add this code in it:
```xml
<?xml version="1.0" encoding="UTF-8"?>
<odoo>
	<template id="slide_content_detailed_inherit" inherit_id="website_slides.slide_content_detailed">
		<!-- Remove the fullscreen button -->
		<xpath expr="//a[contains(@class, 'btn btn-light border ms-2 my-1') and contains(@t-att-href, 'fullscreen=1')]" position="replace"/>
	</template>
</odoo>
```

This will replace the selected xpath with nothing, which will delete the code.