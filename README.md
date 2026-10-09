# Overreach? Companies in Scope of the EU Corporate Sustainability Due Diligence Directive (CSDDD)

An interactive visualization of large companies that meet or approach the thresholds of the EU Corporate Sustainability Due Diligence Directive (CSDDD), shown by headquarters region, revenue, and location.

**Live page:** https://battinsights.github.io/csddd-overreach/

## Views

- **Float:** all companies in a single drifting group, colored by headquarters region
- **By revenue:** companies ranked from largest to smallest
- **World map:** companies placed at their headquarters cities

The **Oil & gas only** switch narrows the view to oil and gas companies, and each region in the legend can be switched off and on. Hover over a company for details, or click it to pin a detail card.

## Embedding

The page can be embedded in a website with an iframe. The outer wrapper lets the chart extend beyond a narrow article column, up to 1,320 pixels wide, while staying centered on the page:

```html
<div style="position:relative;left:50%;transform:translateX(-50%);width:min(1320px, calc(100vw - 40px));">
  <iframe id="csddd-frame" src="https://battinsights.github.io/csddd-overreach/"
    width="100%" height="1250" style="border:0;display:block" loading="lazy"
    title="Overreach? Companies in scope of the CSDDD"></iframe>
</div>
<script>
  window.addEventListener("message", function (e) {
    if (e.data && e.data.csdddHeight) {
      document.getElementById("csddd-frame").style.height = e.data.csdddHeight + "px";
    }
  });
</script>
```

The script lets the frame match the height of the page, so it fits on phones as well as desktops. Without it, the frame stays at the fixed height set above. To keep the chart within the article column instead, remove the outer wrapper.

## Data

Revenues are approximate recent annual figures in US dollars, rounded, and used for relative scale. Inclusion does not confirm that a given company meets the directive's thresholds.

Source: EPRINC analysis based on company data.

## Author

Batt Odgerel
