# mediawiki-ifmobile-extention
Allows to define different output for mobile devices in HTML structure.

This is different approach as in [https://www.mediawiki.org/wiki/Extension:MobileDetect MobileDetect] which generates output and show parts for mobile, parts for desktop and others to both devices.

IfMobile allows to set different styles, different output directly in templates. Main advantage is, when need to provide different output which is not possible (or very complicated) to manage different output in templates. It is not need to made two outputs one for mobile, one for desktop and show proper output on visitors device. IfMobile check visitor device and shows ouput with for example mobile specific html styles, table colspan/rowspan, etc.

## Examples ##
`<div style="background-color:{{#ifmobile:color for mobile devices|color for desktop devices}}">Content</div>`

`<div>{{#ifmobile:Content only for mobiles|Content only for desktop}}</div>`

## Differences between MobileDetect and IfMobile ##
### Previous solution with mobileDetect was this way.
`<span class="mobileonly">{{Feature|name=City|variant=image|size=x20px|text=In city with blahblahblah}}</span>`

`<span class="nomobile">{{Feature|name=City|variant=image|size=x15px|text=In city with blahblahblah}}</span>`

### New solution with IfMobile:
`{{Feature|name=City|variant=image|size={{#ifmobile:x20px|x15px}}|text=In city with blahblahblah}}`

The main advantage is for translators. They no longer have to translate the same texts several times.

Also, the file sent to the visitor is smaller because the content for desktop does not contain content for mobile device and vice versa.


## License ##
BSD
