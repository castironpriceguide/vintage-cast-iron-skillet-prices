# Vintage cast iron skillet prices: Griswold and Wagner

What Griswold and Wagner cast iron skillets actually sell for: the median price paid in completed eBay sales, per skillet,
and a monthly price index. Published by [Cast Iron Price Guide](https://castironpriceguide.com/), which shows the same figures page by page and
updates them every day. This repository is refreshed once a month.

Data date: 2026-10-10. 66 skillets with a current value; 2 months of the price index (62 skillet rows).

## Files

### `data/values.csv`

One row per skillet with a value from the last 90 days (a median of at least 5 sales).

| Column | Meaning |
|---|---|
| `id` | the skillet's id on the site |
| `maker` | `griswold` or `wagner` |
| `size` | the size number cast on the skillet |
| `logo` | `slant`, `large_block`, `small_block`, `sidney_o`, or `other` when the listings did not state it |
| `bottom` | `heat_ring`, `smooth`, or `unknown` when the listings did not state it |
| `name` | the skillet's name on the site |
| `url` | its page, with every sale behind the value |
| `median_usd` | the median price paid, US dollars, item price without shipping |
| `sales_90d` | the number of sales the median is taken from |
| `value_date` | the date of the value |

### `data/price-index.csv`

One row per month and maker. A skillet is compared when it sold at least 5 times in both the month and the month before; its
change is the change in its median sale price. The maker's `change` is the median of those changes, left empty when fewer than
5 skillets could be compared. Columns: `month`, `maker`, `change` (a fraction: `0.0040` is +0.40%), `compared`, `rose`,
`fell`, `unchanged`, `sales` (the maker's sales that month), `published_date`, `url` (the month's page).

### `data/price-index-skillets.csv`

The skillets behind each figure: `month`, `maker`, `id`, `name`, `prev_sales`, `prev_median_usd`, `sales`, `median_usd`,
`change`.

## How the prices are collected

Public eBay listings of Griswold and Wagner skillets are read as they appear and checked after they end; only completed sales
count, at the item price paid. Damaged pieces, reproductions, enamelled or plated pieces, lids, sets and other items are left
out. Details: [how the values are computed](https://castironpriceguide.com/methodology/) and [the price index](https://castironpriceguide.com/price-index/).

## Licence and citation

[CC BY 4.0](LICENSE): free to share and adapt, also commercially, with attribution and a link to https://castironpriceguide.com/.

Cite as: Cast Iron Price Guide, castironpriceguide.com, October 2026.
