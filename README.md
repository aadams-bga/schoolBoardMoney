- [outsideVsCandidates](https://aadams-bga.github.io/schoolBoardMoney/outsideVsCandidates/)
- [headToHead](https://aadams-bga.github.io/schoolBoardMoney/headToHead/)
- [limitsOff](https://aadams-bga.github.io/schoolBoardMoney/limitsOff/)
- [topDonors](https://aadams-bga.github.io/schoolBoardMoney/topDonors/)
- [moneyFlow](https://aadams-bga.github.io/schoolBoardMoney/moneyFlow/)
- [twoPlaybooks](https://aadams-bga.github.io/schoolBoardMoney/twoPlaybooks/)
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
<iframe id="limitsOff"           src="https://aadams-bga.github.io/schoolBoardMoney/limitsOff/"           height="832" loading="lazy" scrolling="no" frameborder="0" style="display:block;width:100%;border:0;overflow:hidden"></iframe>
<iframe id="topDonors"           src="https://aadams-bga.github.io/schoolBoardMoney/topDonors/"           height="562" loading="lazy" scrolling="no" frameborder="0" style="display:block;width:100%;border:0;overflow:hidden"></iframe>
<iframe id="moneyFlow"           src="https://aadams-bga.github.io/schoolBoardMoney/moneyFlow/"           height="862" loading="lazy" scrolling="no" frameborder="0" style="display:block;width:100%;border:0;overflow:hidden"></iframe>
<iframe id="twoPlaybooks"        src="https://aadams-bga.github.io/schoolBoardMoney/twoPlaybooks/"        height="430" loading="lazy" scrolling="no" frameborder="0" style="display:block;width:100%;border:0;overflow:hidden"></iframe>
<iframe id="attackShare"         src="https://aadams-bga.github.io/schoolBoardMoney/attackShare/"         height="439" loading="lazy" scrolling="no" frameborder="0" style="display:block;width:100%;border:0;overflow:hidden"></iframe>
<iframe id="spendingOverTime"    src="https://aadams-bga.github.io/schoolBoardMoney/spendingOverTime/"    height="650" loading="lazy" scrolling="no" frameborder="0" style="display:block;width:100%;border:0;overflow:hidden"></iframe>
<iframe id="subdistrictMap"      src="https://aadams-bga.github.io/schoolBoardMoney/subdistrictMap/"      height="760" loading="lazy" scrolling="no" frameborder="0" style="display:block;width:100%;border:0;overflow:hidden"></iframe>
<iframe id="totalRaised"         src="https://aadams-bga.github.io/schoolBoardMoney/totalRaised/"         height="1230" loading="lazy" scrolling="no" frameborder="0" style="display:block;width:100%;border:0;overflow:hidden"></iframe>
```

**Where the data lives**

Each graphic folder holds the CSV that graphic reads at runtime, named after the folder. The footer's "Download the data" link points at that file, so a reader downloads exactly what they are looking at.

`dataDownload/` is separate. It holds combined datasets for readers who want the whole thing rather than one chart's slice, and no graphic reads from it.

```
outsideVsCandidates/
  index.html                  <- fetches outsideVsCandidates.csv at runtime
  outsideVsCandidates.csv     <- spender, Through Sept. 30, Oct. 1-15

headToHead/                   <- the 12 CTU-backed vs. reform-backed subdistrict races
limitsOff/                    <- every itemized gift to Biggs and Dominguez
topDonors/                    <- waffle: who funded the school-board-focused groups
moneyFlow/                    <- Sankey links: source, target, amount (also loads d3-sankey)
twoPlaybooks/                 <- independent spending vs. gifts to campaigns, by camp
attackShare/                  <- supporting vs. opposing independent expenditures, by group
spendingOverTime/             <- daily spending by spender; the page sums it into running totals
subdistrictMap/               <- each group's money by subdistrict, candidate and kind; also loads subdistricts.geojson (boundaries + ballot)
totalRaised/                  <- subdistrict candidates: total raised, split into CTU, SEIU, Common Ground, INCS, Urban Center, loans, other donors

dataDownload/
  candidates.csv              <- one row per candidate on the ballot: raised, spent, cash, outside money for/against
  independentExpenditures.csv <- every school board independent expenditure line
```

**Where the numbers come from**

Illinois State Board of Elections filings, Jan. 1, 2025 through reports available Oct. 19, 2026: D-2 quarterly reports (official totals and itemized lines), B-1 independent expenditure reports and A-1 large-contribution reports. Four paper reports ISBE had not yet keyed in (Henderson's, Morales's and Neal's July-Sept. D-2s, and Morales's Oct. 9 A-1) were entered by hand from ISBE's scans; see `manual_entries.xlsx` in the parent project. The CSVs are written by `graphics/export_graphics_csvs.py` in the parent `campaignFinance` project (after `scrape_isbe_web.py`, `race_by_race.py` and `graphics/build_graphics_data.py`); the pages are generated by `graphics/make_d3_pages.py`. Headlines, subtitles and notes are lorem ipsum placeholders.
