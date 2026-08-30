# 安家藏玉 — anjiajade.com

## What to upload
Upload the **contents of this folder** to the repository root (or the folder your host serves).

    index.html                 landing page
    privacy/index.html         隱私權政策
    thankyoupage/index.html    表單送出後的感謝頁
    assets/web/                photography
    _ds/                       design system stylesheet + bundle
    support.js, image-slot.js  runtime
    .nojekyll                  required on GitHub Pages so _ds/ is served

## Google Tag Manager
Container **GTM-MRB8SXZG** is installed on all three pages (loaded from inside
each page, with a guard so it can only fire once). After deploying, check it in
GTM → Preview; `dataLayer` and `gtm.js` are confirmed loading locally.

## Notes
- The privacy policy modal no longer flashes on load.
- The 地圖導航 buttons open https://maps.app.goo.gl/hcXDf6vnao6gTHsn6
- The booking form posts to its configured endpoint and redirects to /thankyoupage/.
