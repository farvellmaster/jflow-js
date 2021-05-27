# JFlow-Core Documentation
### A NPM package that exports jflow-js classes to your project.

# Where to start:

```bash
npm install jflow-core
```
# Custom Build Examples

### To create a custom handle event:

```javascript

    // Object constructor waits for 
    // element id and css className
    const htmlElement = new Handler({
        element: "idString",
        css: [ "className1", "className2" ]
    });

```

### The constructed Handler object returns a list of methods for trigger events that returns a Promise not resolved:

* Trigger events must be returned in a execution context.

```javascript

    // Click event
    return htmlElement.onClick( "trigger-className" );

    // Timeout event
    const time = 1200;
    return htmlElement.onTimeout( time );

    // Scroll event
    const direction = 1, offset = 100;
    // direction moves target on Y exe;
    return htmlElement.onScroll( "targetId", -direction, offset  )

```

### Create a custom Parallax object

```javascript

    // direction can be negative
    // offset specifies minOffset to trigger
    const htmlElement = new Parallax({
        target: "targetId",
        direction: -1.2,
        offset: 100
    });

    // starts event listener
    hmtlElement.listen();

```

### Create a custom Lightbox object

* All id's and classNames are required! You can copy and paste.

```html

    <section id="lightbox">
        <span class="lightbox-close lightbox-control">x</span>
            
        <figure>
            <span class="previous-button lightbox-control"><</span>
            <img id="lightbox-photo" src="#" alt="lightbox-main-photo">
            <span class="next-button lightbox-control"><</span>
        </figure>

        <p id="lightbox-caption" class="caption"></p>
        <nav id="lightbox-roullette" class="roullette"></nav>
    </section>

```

* You must put lightbox-control class to trigger lightbox.

```html

    <figure class="grid-container lightbox-control">
        <img class="grid-image" src="images/port_01.jpg" alt="port_01">
        <figcaption class="grid-caption">Lorem ipsum dolor sit amet.</figcaption>
    </figure>

```

```javascript

    // Only pass your html references
    // and css class animations
    const lightbox = new Lightbox({
        images: ".grid-image",
        texts: ".grid-caption",
        css: [ "disappear", "appear" ]
    });

```

#

Questions?
----------

If you have any questions, please feel free to send me an email;

