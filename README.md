# GrowtherLab — legal

Public legal pages for GrowtherLab apps. Served by GitHub Pages at:

**https://growtherlab.github.io/legal/**

This repo is public because GitHub Pages on free accounts only publishes from
public repositories. It contains no source code — only the pages that App Review
and users need to be able to open.

## Layout

```
index.html              directory of apps and their policies
assets/style.css        shared styling for every page
TEMPLATE-privacy.html   starting point for a new app's policy
iman-pro/privacy.html   https://growtherlab.github.io/legal/iman-pro/privacy.html
nerida/privacy.html     https://growtherlab.github.io/legal/nerida/privacy.html
nerida/support.html     https://growtherlab.github.io/legal/nerida/support.html
.nojekyll               serve files as-is, no Jekyll processing
```

## Adding a new app

1. Create a folder named after the app slug, e.g. `qibla-finder/`.
2. Copy `TEMPLATE-privacy.html` into it as `privacy.html`.
3. Replace every `{{PLACEHOLDER}}`.
4. **Verify the data table against the actual code** — every row must describe a
   real network call or a real local store. Do not copy another app's table.
   This table has to agree with the App Privacy form in App Store Connect.
5. If the app needs a Support URL, add `support.html` alongside it. App Review
   requires a reachable support page; `nerida/support.html` is a worked example.
   Answer the questions the app actually raises, not generic filler.
6. Add the app to `index.html`.
7. Commit. Pages redeploys in about a minute.

## Terms of Use

Apps that only sell an auto-renewing subscription can use Apple's standard EULA
rather than hosting their own terms:

```
https://www.apple.com/legal/internet-services/itunes/dev/stdeula/
```

This is the default License Agreement in App Store Connect and is accepted as the
"Terms of Use (EULA)" link on a paywall. Host your own terms here only if the app
does something the standard EULA does not cover.

## Custom domain

If a domain is bought later, point it at this repo in Settings → Pages → Custom
domain. The paths stay the same, so only the host part of each URL changes:

```
https://growtherlab.github.io/legal/iman-pro/privacy.html
                    ↓
https://<domain>/legal/iman-pro/privacy.html
```

Update the URL in each app's source (for Iman Pro: `components/onboarding.tsx`)
and in App Store Connect's Privacy Policy URL field.

## Note

These pages follow a common template and are not legal advice. They satisfy the
App Review requirement for a reachable page that accurately describes what the app
does. Update them whenever the third-party service list or data flow changes.
