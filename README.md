# 安家藏玉 — anjiajade.com

## Upload
Upload the CONTENTS of this folder to the repository root.

    index.html                 landing page
    privacy/index.html         隱私權政策
    thankyoupage/index.html    感謝頁
    ds/modernist/              stylesheet + component bundle  <-- must be uploaded
    assets/web/                photography
    support.js                 runtime

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

## Hero video
The hero holds for 1s with scrolling locked, then slides up to reveal a
self-hosted mp4 that autoplays (unmuted where the browser allows it, muted
otherwise). Scrolling during the hold reveals it early and counts as the user
gesture that permits sound. Two files, one per breakpoint:

    assets/web/hero-reel-desktop.mp4   > 700px
    assets/web/hero-reel-mobile.mp4    <= 700px

Only the matching breakpoint's file is fetched (preload="none" + data-src).
Both are large (~60MB) — they are under GitHub's 100MB per-file limit but
above the 50MB warning threshold, and Git LFS is NOT used. Re-encoding them
smaller is the single biggest win available on this page.

Sound toggle bottom-left, tap the video to pause, blurred overlay with a play
button on pause or end.

## Deploy build notes
The 30 photographs are plain <img> tags in this build (they are editable
image-slot placeholders in the authoring file). That removes image-slot.js and
its /.image-slots.state.json request. The two hero images load eagerly; the rest
are lazy. The favicon data URI is percent-encoded — raw spaces made it invalid.
