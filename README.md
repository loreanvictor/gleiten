# gleiten

super easy interactive html animations, based on vertical scroll, mouse position, etc.

**NOTE**: if you just want some animation on elements when they are "scrolled into view", there are better libraries to achieve that such as [AoS](https://michalsnik.github.io/aos/). this library helps you design interactive animations based on parameters such as body scroll position, mouse position, etc.

## how to install

_coming soon_

## how to use

### basic usage

```html
<p data-gleiten='{"0vh": {"rotate":"0deg"}, "50vh": {"rotate": "90deg"}}'>hellow</p>

<script>
window.addEventListener('load', function() {
  
  gleiten.animate().on(gleiten.verticalScroll());
  
});
</script>
```

the `<p>` element will rotate 90 degrees as the page scrolls from `0vh` to `50vh`.

---

```html
<p data-gleiten='{"0vh": {"scale": 1}, "50vh": {"scale": 2}}'>hellow</p>
<p>world!</p>

<script>
  window.addEventListener('load', function() {
  
    gleiten.animate().on(gleiten.verticalScroll());
  
    gleiten.animate(document.getElementsByTagName('p'), {
      '0vh': {rotate: '0deg'},
      '50vh': {rotate: '90deg'}
    }).on(gleiten.verticalScroll());
  
  });
</script>
```

the first `<p>`(_hellow_) scales up and rotates, and the second `<p>`(_world!_) only rotates, as the page scrolls from `0vh` to `50vh`.

---

```html
<div id="holder" style="height:50vh; overflow: auto">
  <div style="height: 100vh">
    <p data-gleiten='{"0vh": {"scale": 1}, "50vh": {"scale": 2}}'>hellow</p>
  </div>
</div>

<script>
  window.addEventListener('load', function() {
  
    gleiten.animate().on(gleiten.verticalScroll(document.getElementById('holder')));
  
  });
</script>
```

will scale the `<p>` element up, but the animation is bound to scrolling of `#holder` element instead of body (body doesn't scroll).
