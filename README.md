- [outsideVsCandidates](https://aadams-bga.github.io/schoolBoardMoney/outsideVsCandidates/)
- [headToHead](https://aadams-bga.github.io/schoolBoardMoney/headToHead/)
- [attackShare](https://aadams-bga.github.io/schoolBoardMoney/attackShare/)
- [spendingOverTime](https://aadams-bga.github.io/schoolBoardMoney/spendingOverTime/)
- [subdistrictMap](https://aadams-bga.github.io/schoolBoardMoney/subdistrictMap/) (add `#7A` or any subdistrict to the link to open with it selected)
- [totalRaised](https://aadams-bga.github.io/schoolBoardMoney/totalRaised/)

**Use this as the embed code**
Change id and the slug portion of the src url

```html
<iframe
  id="outsideVsCandidates"
  src="https://aadams-bga.github.io/schoolBoardMoney/outsideVsCandidates/"
  height="457"
  loading="lazy"
  scrolling="no"
  frameborder="0"
  style="display:block;width:100%;border:0;overflow:hidden"
></iframe>
```

**Put this somewhere on the page**

```html
<script>
(function () {
  function ask() {
    var frames = document.getElementsByTagName("iframe");
    for (var i = 0; i < frames.length; i++) {
      try { frames[i].contentWindow.postMessage({ type: "iap-graphic-request" }, "*"); } catch (e) {}
    }
  }
  window.addEventListener("message", function (e) {
    if (!e.data || e.data.type !== "iap-graphic-height") return;
    var frame = document.getElementById(e.data.id);
    if (frame) frame.style.height = e.data.height + "px";
  });
  ask();
  window.addEventListener("load", ask);
  setTimeout(ask, 500);
  setTimeout(ask, 2000);
})();
</script>
```

**All iframes for reference**

Heights are the rendered height at 640px wide; the script above resizes each one to fit.

```html
<iframe id="outsideVsCandidates" src="https://aadams-bga.github.io/schoolBoardMoney/outsideVsCandidates/" height="457" loading="lazy" scrolling="no" frameborder="0" style="display:block;width:100%;border:0;overflow:hidden"></iframe>
<iframe id="headToHead"          src="https://aadams-bga.github.io/schoolBoardMoney/headToHead/"          height="870" loading="lazy" scrolling="no" frameborder="0" style="display:block;width:100%;border:0;overflow:hidden"></iframe>
<iframe id="attackShare"         src="https://aadams-bga.github.io/schoolBoardMoney/attackShare/"         height="439" loading="lazy" scrolling="no" frameborder="0" style="display:block;width:100%;border:0;overflow:hidden"></iframe>
<iframe id="spendingOverTime"    src="https://aadams-bga.github.io/schoolBoardMoney/spendingOverTime/"    height="650" loading="lazy" scrolling="no" frameborder="0" style="display:block;width:100%;border:0;overflow:hidden"></iframe>
<iframe id="subdistrictMap"      src="https://aadams-bga.github.io/schoolBoardMoney/subdistrictMap/"      height="760" loading="lazy" scrolling="no" frameborder="0" style="display:block;width:100%;border:0;overflow:hidden"></iframe>
<iframe id="totalRaised"         src="https://aadams-bga.github.io/schoolBoardMoney/totalRaised/"         height="1230" loading="lazy" scrolling="no" frameborder="0" style="display:block;width:100%;border:0;overflow:hidden"></iframe>
```
