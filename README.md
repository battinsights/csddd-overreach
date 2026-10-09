# Overreach? Companies in Scope of the EU Corporate Sustainability Due Diligence Directive (CSDDD)

An interactive visualization of large companies that meet or approach the thresholds of the EU Corporate Sustainability Due Diligence Directive (CSDDD), shown by headquarters region, revenue, and location.

**Live page:** https://battinsights.github.io/csddd-overreach/

## Views

- **Float:** all companies in a single drifting group, colored by headquarters region
- **By revenue:** companies ranked from largest to smallest
- **World map:** companies placed at their headquarters cities

The **Oil & gas only** switch narrows the view to oil and gas companies, and each region in the legend can be switched off and on. Hover over a company for details, or click it to pin a detail card.

## Embedding

The page can be embedded in a website with an iframe. The script widens the chart beyond a narrow article column so that its left edge lines up with the article text and its right edge lines up with the right edge of the site's layout. It also lets the frame match the height of the page, so it fits on phones as well as desktops.

```html
<div id="csddd-wrap" style="max-width:none !important">
  <iframe id="csddd-frame" src="https://battinsights.github.io/csddd-overreach/"
    width="100%" height="1300" style="border:0;display:block" loading="lazy"
    title="Overreach? Companies in scope of the CSDDD"></iframe>
</div>
<script>
  (function () {
    var wrap = document.getElementById("csddd-wrap");
    var frame = document.getElementById("csddd-frame");
    function widen() {
      wrap.style.width = "";
      var column = wrap.offsetWidth;
      var left = wrap.getBoundingClientRect().left;
      var right = document.documentElement.clientWidth - 24;
      for (var el = wrap.parentElement; el && el !== document.body; el = el.parentElement) {
        var box = el.getBoundingClientRect();
        if (box.width > column + 100) {
          right = Math.min(right, box.right - (parseFloat(getComputedStyle(el).paddingRight) || 0));
          break;
        }
      }
      wrap.style.width = Math.max(column, right - left) + "px";
    }
    widen();
    window.addEventListener("load", widen);
    window.addEventListener("resize", widen);
    window.addEventListener("message", function (e) {
      if (e.data && e.data.csdddHeight) frame.style.height = e.data.csdddHeight + "px";
    });
  })();
</script>
```

Without the script, the frame stays at the fixed height above and the width of the article column.

## Data

Revenues are approximate recent annual figures in US dollars, rounded, and used for relative scale. Inclusion does not confirm that a given company meets the directive's thresholds.

Source: EPRINC analysis based on company data.

## Author

Batt Odgerel
