- [headToHead](https://aadams-bga.github.io/schoolBoardMoney/headToHead/)
- [attackShare](https://aadams-bga.github.io/schoolBoardMoney/attackShare/)
- [spendingOverTime](https://aadams-bga.github.io/schoolBoardMoney/spendingOverTime/)
- [districtMap](https://aadams-bga.github.io/schoolBoardMoney/districtMap/) (add `#7A` or any subdistrict to the link to open with it selected)

**Use this as the embed code**
Change the slug portion of the src url

```html
<iframe
  src="https://aadams-bga.github.io/schoolBoardMoney/headToHead/"
  height="970"
  loading="lazy"
  scrolling="no"
  frameborder="0"
  style="display:block;width:100%;border:0;overflow:hidden"
></iframe>
```

**Put this somewhere on the page** (once, however many graphics the page has)

```html
<script>
window.addEventListener("message", function (e) {
  if (!e.data || e.data.type !== "embed-size") return;
  var frames = document.getElementsByTagName("iframe");
  for (var i = 0; i < frames.length; i++) {
    if (frames[i].contentWindow === e.source) frames[i].style.height = e.data.height + "px";
  }
});
</script>
```

**Sites that use Sidechain (Chalkbeat)** don't need the script or the iframe. Embed with their own tag:

```html
<side-chain src="https://aadams-bga.github.io/schoolBoardMoney/headToHead/"></side-chain>
```

Each graphic sends its height as `{ sentinel: "amp", type: "embed-size", height }`, the message Sidechain and AMP iframes listen for.

**All iframes for reference**

Heights are the rendered height at 640px wide; the script above resizes each one to fit.

```html
<iframe src="https://aadams-bga.github.io/schoolBoardMoney/headToHead/"        height="970" loading="lazy" scrolling="no" frameborder="0" style="display:block;width:100%;border:0;overflow:hidden"></iframe>
<iframe src="https://aadams-bga.github.io/schoolBoardMoney/attackShare/"       height="487" loading="lazy" scrolling="no" frameborder="0" style="display:block;width:100%;border:0;overflow:hidden"></iframe>
<iframe src="https://aadams-bga.github.io/schoolBoardMoney/spendingOverTime/"  height="741" loading="lazy" scrolling="no" frameborder="0" style="display:block;width:100%;border:0;overflow:hidden"></iframe>
<iframe src="https://aadams-bga.github.io/schoolBoardMoney/districtMap/"       height="1006" loading="lazy" scrolling="no" frameborder="0" style="display:block;width:100%;border:0;overflow:hidden"></iframe>
```
