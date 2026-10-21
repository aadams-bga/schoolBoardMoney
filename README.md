**Illinois Answers iframes**

```html
<iframe src="https://aadams-bga.github.io/schoolBoardMoney/headToHead/"        height="970" loading="lazy" scrolling="no" frameborder="0" style="display:block;width:100%;border:0;overflow:hidden"></iframe>
<iframe src="https://aadams-bga.github.io/schoolBoardMoney/attackShare/"       height="487" loading="lazy" scrolling="no" frameborder="0" style="display:block;width:100%;border:0;overflow:hidden"></iframe>
<iframe src="https://aadams-bga.github.io/schoolBoardMoney/spendingOverTime/"  height="741" loading="lazy" scrolling="no" frameborder="0" style="display:block;width:100%;border:0;overflow:hidden"></iframe>
<iframe src="https://aadams-bga.github.io/schoolBoardMoney/districtMap/"       height="1006" loading="lazy" scrolling="no" frameborder="0" style="display:block;width:100%;border:0;overflow:hidden"></iframe>
```

**Illinois Answers script**

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

**Chalkbeat (Sidechain)**

```html
<side-chain src="https://aadams-bga.github.io/schoolBoardMoney/headToHead/"></side-chain>
<side-chain src="https://aadams-bga.github.io/schoolBoardMoney/attackShare/"></side-chain>
<side-chain src="https://aadams-bga.github.io/schoolBoardMoney/spendingOverTime/"></side-chain>
<side-chain src="https://aadams-bga.github.io/schoolBoardMoney/districtMap/"></side-chain>
```
