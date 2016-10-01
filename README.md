# Proto
A simple HTML & SCSS rapid prototyping toolkit for responsive web design by <a href="http://twitter.com/#!/adamwhitcroft">@adamwhitcroft</a>.

Proto helps you knock up quick responsive layout concepts by providing a set of predefined CSS classes. All that's needed to get going is the `proto.scss` file and some basic HTML.

[Share Proto](http://twitter.com/share?url=https://github.com/AdamWhitcroft/Proto&text=Proto:%20RWD%20Rapid%20Prototyping%20by%20@adamwhitcroft:)

--

## Getting Started

Proto uses a combination of HTML and compiled SCSS to create your prototypes. At the top of the proto.scss file, you'll find the Proto variables.

```
//  Proto vars
//  Be sure to inlclude appropriate units i.e. 'px', '%', 'em' etc
//  (These comments will be stripped out during compile)

//  Base
$blockBackground: #eee;
$centerWidth: 70%;

//  Demo
$DemoPass: #dff0d8;
$DemoFail: #f0d8d8;

//  Media Query
$desktopWidth: 1024px;
$tabletWidth: 768px;
$phoneWidth: 480px;
```

Proto comes with these variables predefined, but feel free to change any of the values to match your own requirements.

## Classes

### The `.block` class

The single most important part of Proto is the .block class. It's the structural foundation of the toolkit, so using it correctly is important. Thankfully, this is pretty straightforward:

```
<div class="block">
  foo
</div>
```

Any 'container' element you create - header, section, article, footer, div etc - should have the `.block` class applied it.

### The `.center` class

Apply this class to a block to center it within its parent. The value of the $centerWidth variable is the width applied to the `.center` class (70% by default).

```
<div class="block center">
  introduction
</div>
```

### The `.grid` class

Grids are a cinch. Add the `.grid class` to any element you'd like to act as a grid wrapper.

```
<div class="block grid">

  <div class="block sixty">
    main content
  </div>

  <div class="block forty">
    sidebar
  </div>
  
</div>
```

Grids can be nested as far down as you'd like allowing the creation of intricate layouts. Only the outermost wrapping element need have the `.grid` class applied.

```
<div class="block grid">

  <div class="block sixty">
    main content
  </div>
  
  <div class="block forty">
    <div class="block fifty">
      col 1
    </div>
    
    <div class="block fifty">
      col 2
    </div>
  </div>
  
</div>
```

### The `.hide` and `.show` class

You can opt to either show an element within a given viewport range, or display it within all but a given viewport range.

Element(s) will be shown within their respective viewport range only.

```
.desktop
.tablet
.phone
```

Element(s) will be shown within all BUT their respective viewport range.

```
.not-desktop
.not-tablet
.not-phone
```

Let's say you wanted an element to only show within the 'desktop' viewport range.

```
<div class="block desktop">
  foo
</div>
```

What about displaying an element on all BUT the 'desktop' viewport range.

```
<div class="block not-desktop">
  bar
</div>
```

### The `.demo` class

If you'd like to demonstrate the effect of the classes set out above without actually hiding any elements, append the class name with `-demo`. This changes the visual style of the element, rather than applying `display: none;` to it.

The following will render a light green box if the viewport width is within the 'desktop' range. As soon as the width drops below this range, it will render as a light red box.

```
<div class="block desktop-demo">
  .desktop-demo
</div>
```

The following will render a light green box if the viewport width is within all BUT the 'tablet' range. As soon as the viewport width is outside of (either above or below) this range, it will render as a light red box.

```
<div class="block not-tablet-demo">
  .not-tablet-demo
</div>
```

### The `-to-` class

Imagine you have a 1x4 grid of elements within the desktop viewport range that but you'd like to become a 2x2 grid in the tablet range and a 4x1 in the phone range. Enter the `-to-` class.

The `-to-` class has a simple naming convention:

```
.{viewport}-to-{new width}
```

Using the above as an example, the following will change the width of each 'twentyfive' block to that of a 'fifty' block at the 'tablet' viewport width and to a 'hundred' width at the 'phone' viewport range.

```
<div class="block grid">

  <div class="block twentyfive tablet-to-fifty phone-to-hundred">
    1
  </div>
  
  <div class="block twentyfive tablet-to-fifty phone-to-hundred">
    2
  </div>
  
  <div class="block twentyfive tablet-to-fifty phone-to-hundred">
    3
  </div>
  
  <div class="block twentyfive tablet-to-fifty phone-to-hundred">
    4
  </div>
  
</div>
```

## Class Reference Table:

For complete usage examples, refer to the <a href="http://adamwhitcroft.com/proto/">Proto</a> website.

| Class | Description |
| ----- | ----------- |
| block | Apply to just about everything |
| center | Centers an element within its parent |
| grid | Defines an element that contains children using a grid system |
| hundred | Sets a width of 100% on an element |
| ninety | Sets a width of 90% on an element |
| eighty | Sets a width of 80% on an element |
| seventyfive | Sets a width of 75% on an element |
| seventy | Sets a width of 70% on an element |
| sixtysix | Sets a width of 66.666% on an element |
| sixty | Sets a width of 60% on an element |
| fifty | Sets a width of 50% on an element |
| forty | Sets a width of 40% on an element |
| thirtythree | Sets a width of 33.333% on an element |
| thirty | Sets a width of 30% on an element |
| twentyfive | Sets a width of 25% on an element |
| twenty | Sets a width of 20% on an element |
| ten | Sets a width of 10% on an element |
| desktop | Defines an element that will only be visible on desktops |
| tablet | Defines an element that will only be visible on tablets |
| phone | Defines an element that will only be visible on phones |
| not-desktop | Defines an element that will be visible on everything but desktops |
| not-tablet | Defines an element that will be visible on everything but tablets |
| not-phone | Defines an element that will be visible on everything but phones |
| -demo | Visually demonstrates that an element will be hidden without hiding it |
| -to- | Defines a change in an element's size depending on the viewport |

## Disclaimer

Proto is not a framework, it's a small toolkit built to speed up responsive layout conceptualisation. Using it as a framework - while possible - isn't advisable. Classes and their usage have been kept as simple as possible to give you greater freedom when exploring layout options.
