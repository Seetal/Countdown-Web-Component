# Countdown Web Component

A simple web component that counts down a specified number of seconds.

## Usage

Link to the countdown-timer.js file.

Add the following html:

```html
<countdown-timer
  class="timer"
  id="timer-3"
  time="20"
  auto-start="true">
    <p class="time-remaining" data-timer role="timer"></p>
    // Optional control button below, leave out if not needed.
    <button class="button" data-start-btn>Start</button>
</countdown-timer>
```

If using the ring, add the following template to your page:

```html
  <template data-countdown-ring>
    <svg>
      <circle class="circle" cx="50%" cy="50%"/>
    </svg>
  </template>
```

## Custom complete event

When a timer finishes, a custom event is dispatched which contains the id of the timer.
You can listen for this event with:

```html
document.addEventListener('timer-complete', (event) => {
  console.log(`Timer ${event.detail} finished`);
})
```

## Attributes

### auto-start
Timer will start automatically on connectedCallback.

### show-ring
A ring will show around the timer giving a visual representation of time passed and remaining.

### ring-width
Width of the ring, this is a number, the unit will depend on the 'fluid-ring' attribute.

### fluid-ring
If true the ring width will be percent based. If false it will be pixel based, this means if the countdown component is in a fluid container which could be different sizes based on viewport, the proportion of the ring width to the component could change. Setting 'true' for fluid-width will always keep the proportion of the ring width the same no matter the size of the components container.


## CSS

There is some basic css which should be simple to adapt. The important part is the .circle class which is used to animate the circle svg.
