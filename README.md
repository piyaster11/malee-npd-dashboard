# Unofficial NPD market dashboard (public sources)

Single-file static dashboard (`index.html`, EN/ไทย toggle, no external scripts). Unofficial, independent analysis built from public sources. **Not a Malee publication**; not reviewed or confirmed by Malee Group.

## What is real and what is sample
- **Market insights** tab: public data, each item labelled real / estimate / not found, with its source and date. Google Trends percentages are shown only when they can be recomputed from the saved weekly file under the rules below.
- **All other tabs**: SAMPLE data to show how the tools work. Not real company numbers.

## Source freshness (page updated 8 Nov 2026, Bangkok time)
| Data | Date | What this update did |
|---|---|---|
| Google Trends, original 12 Thai category words (Thailand, 5 years, weekly) | pulled 8 Nov 2026, 09:59 Bangkok | Kept the saved weekly points. Not re-downloaded. |
| 12 added category words | not fetched, 8 Nov 2026 | First request to Google Trends returned HTTP 429. No further requests. No charts and no percentages. |
| Launch-tracker Trend column | file dated 8 Nov 2026 | Percentages removed. Weekly points were not in the file. |
| Retailer website prices (Lotus's, Big C, Tops, Makro public pages) | checked 25 Sep 2026 | Not re-checked. |
| Desk research, company filings, market figures | as of 4 Oct 2026 | Not re-checked. |

## Google Trends method
- Geography is Thailand (`geo=TH`) for every category link and every launch link that has a saved term. The one launch with no saved term (UFC, Vietnam only) has no link and no percentage.
- Category window in the file and in each source link: `today 5-y` (last 5 years), weekly.
- Launch source links use `today 3-m` (last 3 months), which is the Explore window for the old 28-day comparison. The page does not show a launch percentage.
- The week of 8 Nov 2026 is dropped from every category chart and every category percentage. The file was pulled at 09:59 Bangkok that morning, so that week was incomplete. Charts then run from 7 Nov 2021 through 1 Nov 2026.
- “Vs year before” = average of the latest 52 complete weeks (9 Nov 2025–1 Nov 2026) divided by the average of the 52 weeks before that (10 Nov 2024–2 Nov 2025), minus 1.
- “Vs earliest year in this file” = the same latest 52 weeks against the first 52 weeks (7 Nov 2021–30 Oct 2022). This is not a forecast.
- A percentage is shown only when the earlier 52-week average is at least 15 on that word’s own 0–100 scale, and the latest 52-week average is at least 1. A drop that would read as about −90% or worse from a low latest year is not shown. The page rounds the shown percentage to the nearest whole number.
- Search interest is not sales. Google scales each word to its own peak, so two charts cannot be compared by height.
- Each word is a link, “Open in Google Trends ↗”, encoding the query, `geo=TH`, the window (`today 5-y` or `today 3-m`), and `hl` for the page language. The same pattern as the public Thai Credit Radar page. Empty cards stay hatched and still have the link.
- Saved points are also in `trends-weekly.json`. A live Google re-check can differ by a few points because Trends samples searches.
- Click a saved chart, or a word on the 5-year pulse, to expand it. The expanded chart uses the same saved weeks, with the incomplete week of 8 Nov 2026 left off. Related-search scores stay hidden.
- The pulse colours each saved word on its own monthly peak. A darker row is not more searches than a paler row. Words that were not fetched have no coloured cells.
- Compare draws up to four saved lines, each on its own 0–100 peak. That picture is shape only, not a search-volume ranking. No joint Google series was downloaded (HTTP 429, not retried). The button opens those exact words together on Google Trends.
- Related-search words saved on 8 Nov 2026 are listed without their scores. Those scores are not recomputed from the weekly points.
- There is no `mockTrend` series and no synthetic points in the market Trends section.

## Original 12 queries (saved weekly series)
Each card links to Google Trends Explore for that exact query, `geo=TH`, `date=today 5-y`.

| Query | Year-before result | Earliest-year result |
|---|---|---|
| `น้ำมะพร้าว` | +32.3% before rounding (ok) | +73.8% before rounding (ok) |
| `น้ำผลไม้` | +8.2% before rounding (ok) | -3.6% before rounding (ok) |
| `นมโปรตีน` | +96.4% before rounding (ok) | not shown (low_base) |
| `นมโอ๊ต` | +34.8% before rounding (ok) | not shown (low_base) |
| `มัทฉะ` | not shown (low_base) | not shown (low_base) |
| `น้ำส้มคั้น` | +8.8% before rounding (ok) | -29.1% before rounding (ok) |
| `ชาผลไม้` | -10.9% before rounding (ok) | +48.9% before rounding (ok) |
| `คอลลาเจน` | -14.0% before rounding (ok) | -66.2% before rounding (ok) |
| `น้ำผักผลไม้` | +15.5% before rounding (ok) | -9.0% before rounding (ok) |
| `ไม่มีน้ำตาล` | +53.9% before rounding (ok) | +59.1% before rounding (ok) |
| `คอมบูชา` | -43.7% before rounding (ok) | -69.3% before rounding (ok) |
| `โพรไบโอติก` | -16.1% before rounding (ok) | +60.8% before rounding (ok) |

### Arithmetic example (coconut water, `น้ำมะพร้าว`)
- Latest 52 complete weeks, 2025-11-09 to 2026-11-01: average **69.06**.
- The 52 weeks before that, 2024-11-10 to 2025-11-02: average **52.21**.
- Change: (69.06 ÷ 52.21 − 1) = **+32.27%**, shown rounded on the page.
- Earliest 52 weeks, 2021-11-07 to 2022-10-30: average **39.73**, change **+73.81%** before rounding.
- The incomplete point 8 Nov 2026 (value 54) is not in these averages.

Percentages not shown, because the earlier average is under 15:
- `นมโปรตีน`: earliest-year base 10.38. The weekly line is still the saved points. Hiding the % is not a claim that searches stopped.
- `นมโอ๊ต`: earliest-year base 10.17. The weekly line is still the saved points. Hiding the % is not a claim that searches stopped.
- `มัทฉะ`: year-before base 13.90; earliest-year base 1.92. The weekly line is still the saved points. Hiding the % is not a claim that searches stopped.

## Added queries (no figures)
Not duplicates of the original 12. Status for every one: **not fetched**. Source link only.

- `น้ำผลไม้น้ำตาลน้อย` — low-sugar juice
- `เครื่องดื่มเกลือแร่` — electrolyte drink
- `กะทิ` — coconut milk
- `นมปราศจากแลคโตส` — lactose-free milk
- `นมถั่วเหลือง` — soy milk
- `พรีไบโอติก` — prebiotics
- `โพสต์ไบโอติก` — postbiotics
- `ผลไม้กระป๋อง` — canned fruit
- `สับปะรดกระป๋อง` — canned pineapple
- `สมูทตี้` — fruit smoothie
- `เครื่องดื่มวิตามิน` — vitamin drink
- `รับจ้างผลิตเครื่องดื่ม` — contract-made drinks (OEM)

`รับจ้างผลิตเครื่องดื่ม` is a contract-manufacturing phrase, not a shopper product. `กะทิ` is coconut milk, not coconut water (`น้ำมะพร้าว`), which is already in the original 12. `พรีไบโอติก` and `โพสต์ไบโอติก` are not the same word as `โพรไบโอติก`.

## Launch tracker
The table has 15 rows. The saved trend file has 16 keys. `2026-10-01|Tipco` (`Tipco coconut`, too few searches, broad brand-plus-category term) has no row in the table, so it is not shown and has no percentage.

Of the 15 shown rows: 11 were saved as too few searches (still no percentage; each has a source link), 3 had a summary percentage which is removed, and 1 (UFC, outside Thailand) has no saved search term, so it has no link and no percentage.

- `ดอยคำ มะเขือเทศ`: stored -1.0% from recent 3.5 and prior 3.6. Recomputed from those two averages only: -2.7778%. Weekly points were not saved. Not shown.
- `ทิปโก้`: stored -15.0% from recent 3.0 and prior 3.6. Recomputed from those two averages only: -16.6667%. Weekly points were not saved. Not shown.
- `Magic X`: stored 1.0% from recent 3.6 and prior 3.6. Recomputed from those two averages only: 0.0%. Weekly points were not saved. Not shown.

Broad terms, a brand or a brand plus a category, not one product: `Tipco น้ำส้ม`, `ทิปโก้`, `NOBO`, `Oatside` are labelled on the row. `Tipco coconut` is the same kind of broad term but is only in the trend file, not on a row.

## Counts from this audit
- Original category series with saved weekly points: **12**. Points each: **262** (261 used after dropping the partial week).
- Category year-before percentages still shown: **11**. Earliest-year percentages still shown: **9**.
- Category rows with at least one percentage hidden for a low base: **3**.
- Added topics measured: **0**. Added topics not fetched: **12**.
- Launch percentages shown: **0**. Launch percentages removed: **3**. Shown rows still “too few searches”: **11**. Shown rows with no term: **1**. One extra too-few key (`Tipco coconut`) is not on the table.
- Google requests in this update: **1** (HTTP 429). No retry and no other endpoint.

## Other method notes
- No private, internal or personal data is included. Thai text is machine-written.
- Planning tabs (Summary, Score the ideas, and the checklists) remain SAMPLE.

