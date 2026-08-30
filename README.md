# 安家藏玉 — anjiajade.com

## Upload
Upload the CONTENTS of this folder to the repository root.

    index.html                 landing page
    privacy/index.html         隱私權政策
    thankyoupage/index.html    感謝頁
    ds/modernist/              stylesheet + component bundle  <-- must be uploaded
    assets/web/                photography
    support.js, image-slot.js  runtime

No folder starts with an underscore any more, so GitHub Pages/Jekyll cannot
skip it. If the pages ever render unstyled, ds/modernist/styles.css is missing.

## Google Tag Manager
GTM-MRB8SXZG is in the <head> of all three pages, with the <noscript> iframe
at the top of <body>. Verify with view-source (search GTM-MRB8SXZG, expect 2
hits per page) or in the console:
Object.keys(google_tag_manager).filter(k=>k.startsWith('GTM'))

## Notes
- Privacy policy: 隱私權政策及個人資料蒐集告知事項, 全悅廣告股份有限公司.
- 地圖導航 buttons open https://maps.app.goo.gl/hcXDf6vnao6gTHsn6
- The form redirects to /thankyoupage/ on success.
