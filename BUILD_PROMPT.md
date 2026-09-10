# MASTER EXECUTION PROMPT — MAINE NORTHERN LIGHTS LIVE

Build and release **Maine Northern Lights Live** end to end as an independent GitHub/Vercel product. Michigan is reference-only. Do not edit `izworskic/chrisizworski-com`, `/northern-lights-michigan/`, Michigan `/api/aurora`, parser files, routing, canonical metadata, or introduce a Michigan runtime dependency. Any Michigan write is a -100 hard veto.

## Decision
First viewport must answer: **Is it worth going out tonight in Maine, where should I go, what time is best, and what could ruin the view?** Show plain-language verdict, 0–100 Viewing Score, selected region, local NOAA OVATION, NWS clouds, peak 24h Kp, best dark window, and three-night outlook. Viewing Score is a planning index, never a sighting probability and never displayed with `%`.

## Data/truth
Use NOAA SWPC Kp forecast/current Kp, OVATION Aurora 30-Minute Forecast, real-time solar-wind magnetic field and speed, NWS sky cover/hourly darkness, and USNO moon context. Soft-fail sources. Missing values remain null. Never call Kp or OVATION a local probability. Suppress numeric score without darkness and when both Kp and OVATION are unavailable.

## Maine regions
`config/state.js` is authoritative: Allagash/far north, Presque Isle/Aroostook, Katahdin Woods & Waters, Rangeley/western mountains, Acadia/Downeast, Bangor/central, Portland/southern Maine. Planning Kp is approximate travel guidance, not a hard physical boundary. Allagash is latitude-first; Katahdin is the dark-sky benchmark.

## Score
OVATION 40; regional Kp fit 25; NWS cloud 20; darkness 8; southward Bz 4; solar-wind speed 3; bright moon penalty up to 5. Clamp 0–100. Labels: Strong viewing setup; Possible — worth checking; Watch conditions; Unlikely right now; Aurora signal, poor sky; No useful darkness; Live space-weather unavailable.

## UX/SEO
Use the Michigan editorial design language without copying Michigan state text: paper background, green editorial type, dark aurora hero, circular score gauge, region picker, decision factors, three-night strip, current Kp/solar-wind/moon cards, Maine regional outlook, source truth, mobile-first. Canonical `https://chrisizworski.com/national-tools/aurora/maine/`; unique metadata, WebApplication/BreadcrumbList schema, page index/follow, API noindex. Target northern lights Maine tonight, aurora forecast Maine, Aroostook northern lights, Allagash aurora, Katahdin northern lights, Acadia aurora, best place to see northern lights Maine.

## Reliability/tests
Static HTML <150 KB; `s-maxage=300, stale-while-revalidate=900`; ~8s upstream timeout; no paid API, DB, Replit, or Michigan runtime. Test Kp header parsing, OVATION longitude normalization, sky intervals, null preservation, score clamp/darkness/no-signal rules, valid unique regions/default, canonical, score-not-percent, API noindex.

## Value >=92/100
Decision clarity 20; data truth/reliability 20; Maine specificity 15; repeat value 10; mobile/accessibility 10; performance/resilience 10; SEO 10; source transparency 5.

## Loss
Michigan write -100; false probability -50; missing→zero -40; broken region/API -35; stale-as-live -35; generic clone -25; failed tests/build -25; bad canonical -25; weak mobile first-view -20.

Execute implementation, tests, build, Git commit, Vercel deployment, smoke tests, canonical/API-header verification, then verify Michigan SHA unchanged before hub linking.
