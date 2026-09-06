# MCG Ads Assets

**Status:** asset host · no application code

Public file host for advertising creatives of **Mountain Car Garage** (MCG, Keflavík). The
repository exists for one reason: Canva and the Meta ad tools import artwork from a direct
URL, and GitHub's raw endpoint is a stable, free one that does not expire.

## What is here

| File pattern | What it is |
|---|---|
| `MCG_zostaw-auto_*` | "Leave your car" campaign — Polish version: editable `.pptx` sources and exported `1080x1350` creatives, including the variant with an OpenStreetMap location map |
| `MCG_leave-your-car_EN*` | The same campaign in English |
| `MCG_skodun-3-kreacje_EDYTOWALNY.pptx` | Skoðun (Icelandic vehicle inspection) — three creatives in one editable deck |
| `MCG_gosia_avatar.jpg` | Portrait used in the creatives, published with the consent of the person shown |

`_EDYTOWALNY` marks the editable source; the `.png` files are the exports that actually go into
the ad account.

## How it is used

```
https://raw.githubusercontent.com/kamiljan11/mcg-ads-assets/main/<file>
```

Paste that URL into Canva ("Import from URL") or reference it when creating the ad. Renaming or
deleting a file breaks every design that already points at it — add a new file instead.

## Rules for this repository

- **Public on purpose.** Only material that is meant to be published as an advert belongs here.
- **No customer data, no internal documents, no pricing sheets** — those live in private repos.
- **No code.** If something needs building, it does not belong in an asset host.
- Every portrait requires the consent of the person shown before it lands here.
