# Central Bank of Uruguay Exchange Rates API — bcu-exchange-rate

[![npm version](https://img.shields.io/npm/v/bcu-exchange-rate.svg)](https://www.npmjs.com/package/bcu-exchange-rate)
[![license](https://img.shields.io/npm/l/bcu-exchange-rate.svg)](https://github.com/AllRates-Today/bcu-exchange-rate/blob/main/LICENSE)
[![zero dependencies](https://img.shields.io/badge/dependencies-0-brightgreen.svg)](https://www.npmjs.com/package/bcu-exchange-rate)
[![TypeScript](https://img.shields.io/badge/TypeScript-types%20included-3178C6.svg)](https://www.typescriptlang.org/)
[![USD/UYU today](https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fallratestoday.com%2Fapi%2Fopen%2Fcentral-bank%2Fbcu%3Fsource%3DUSD%26target%3DUYU&query=%24.rate&label=USD%2FUYU%20published%20by%20Central%20Bank%20of%20Uruguay&color=0A7E8C&cacheSeconds=3600)](https://allratestoday.com/central-bank-rates-api/bcu/)
[![rate date](https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fallratestoday.com%2Fapi%2Fopen%2Fcentral-bank%2Fbcu%3Fsource%3DUSD%26target%3DUYU&query=%24.rate_date&label=rate%20date&color=555&cacheSeconds=3600)](https://allratestoday.com/central-bank-rates-api/bcu/)

**Official Central Bank of Uruguay (Uruguay) daily exchange rates for Node.js and TypeScript. The published central bank rates behind tax filings, customs valuations, audits, and compliant invoicing — not market estimates, but the numbers Central Bank of Uruguay itself prints, every business day.**

## 🚀 Why this client?

- 🏛️ **Official published rates** — Central Bank of Uruguay's own table, with the publisher's own `rate_date` on every response
- 📅 **History back to 2000** — point-in-time tables and daily series for any past date
- 🔀 **Published vs derived, always flagged** — computed inverse/cross pairs carry `derived: true`, never mixed with official prints
- ⚡ **Zero dependencies** — pure ESM + CJS over global `fetch`; Node 18+, Bun, Deno, and edge runtimes
- 🔷 **Type-safe** — full TypeScript definitions shipped with the package
- 🧾 **Compliance-grade metadata** — `rate_type`, publication date, and source disclaimer on every response

> **Official rate, not mid-market:** every value here is a number Central Bank of Uruguay itself published, fixed once printed and carrying the central bank's own `rate_date` — what filings and audits require. Need the live mid-market rate for pricing or display instead? Use the [mid-market API](https://allratestoday.com/docs/) or [`@allratestoday/sdk`](https://www.npmjs.com/package/@allratestoday/sdk). The two can diverge by several percent.

## ⚡ Try it without a key

The latest Central Bank of Uruguay table is also served keyless, CORS-open and edge-cached, for evaluation, embeds and AI agents:

```bash
curl "https://allratestoday.com/api/open/central-bank/bcu?source=USD&target=UYU"
```

```js
const r = await fetch('https://allratestoday.com/api/open/central-bank/bcu').then((x) => x.json());
console.log(r.rate_date, r.rates.length); // the central bank's latest published table, no key
```

The open endpoint serves the *latest* table only and asks for a visible attribution link. The client below uses the keyed API, which adds point-in-time tables, history, and CSV/XML/Excel output.

## 📈 Latest published table

Today's full Central Bank of Uruguay table, straight from the central bank's latest publication. On GitHub it is refreshed by [a daily Action](.github/workflows/daily-table.yml) that reads the keyless endpoint above and commits only when the central bank publishes a new table; the copy on npm is as of the package's publish date.

<!-- daily-table:start -->
Published **2026-10-08** by Central Bank of Uruguay — 60 rates. Updated 2026-10-08.

| Base | Quote | Type | Rate |
| --- | --- | --- | ---: |
| ARS | UYU | buy | 0.026517 |
| ARS | UYU | sell | 0.026517 |
| AUD | UYU | buy | 27.970076 |
| AUD | UYU | sell | 27.970076 |
| BRL | UYU | buy | 8.010439 |
| BRL | UYU | sell | 8.010439 |
| CAD | UYU | buy | 28.269123 |
| CAD | UYU | sell | 28.269123 |
| CHF | UYU | buy | 48.364205 |
| CHF | UYU | sell | 48.364205 |
| CLP | UYU | buy | 0.041089 |
| CLP | UYU | sell | 0.041089 |
| CNY | UYU | buy | 5.998717 |
| CNY | UYU | sell | 5.998717 |
| COP | UYU | buy | 0.012495 |
| COP | UYU | sell | 0.012495 |
| DKK | UYU | buy | 6.030204 |
| DKK | UYU | sell | 6.030204 |
| EUR | UYU | buy | 45.071389 |
| EUR | UYU | sell | 45.071389 |
| GBP | UYU | buy | 53.177725 |
| GBP | UYU | sell | 53.177725 |
| HKD | UYU | buy | 5.123664 |
| HKD | UYU | sell | 5.123664 |
| HUF | UYU | buy | 0.123374 |
| HUF | UYU | sell | 0.123374 |
| INR | UYU | buy | 0.415468 |
| INR | UYU | sell | 0.415468 |
| ISK | UYU | buy | 0.329185 |
| ISK | UYU | sell | 0.329185 |
| JPY | UYU | buy | 0.254752 |
| JPY | UYU | sell | 0.254752 |
| KRW | UYU | buy | 0.029965 |
| KRW | UYU | sell | 0.029965 |
| MXN | UYU | buy | 2.207897 |
| MXN | UYU | sell | 2.207897 |
| MYR | UYU | buy | 9.8337 |
| MYR | UYU | sell | 9.8337 |
| NOK | UYU | buy | 4.204044 |
| NOK | UYU | sell | 4.204044 |
| NZD | UYU | buy | 22.529663 |
| NZD | UYU | sell | 22.529663 |
| PEN | UYU | buy | 11.67165 |
| PEN | UYU | sell | 11.67165 |
| PYG | UYU | buy | 0.007063 |
| PYG | UYU | sell | 0.007063 |
| RUB | UYU | buy | 0.470859 |
| RUB | UYU | sell | 0.470859 |
| SEK | UYU | buy | 4.031603 |
| SEK | UYU | sell | 4.031603 |
| TRY | UYU | buy | 0.81712 |
| TRY | UYU | sell | 0.81712 |
| USD | UYU | buy | 40.21 |
| USD | UYU | sell | 40.21 |
| VES | UYU | buy | 0.046101 |
| VES | UYU | sell | 0.046101 |
| XDR | UYU | buy | 54.357486 |
| XDR | UYU | sell | 54.357486 |
| ZAR | UYU | buy | 2.421166 |
| ZAR | UYU | sell | 2.421166 |

Source: [Official rates published by BCU, served by AllRatesToday](https://allratestoday.com/central-bank-rates-api/bcu/). Rates are as printed by the central bank; AllRatesToday is not affiliated with it.
<!-- daily-table:end -->

## 🔑 Get your API key

Get a free API key at [allratestoday.com/register](https://allratestoday.com/register) — no credit card required. Latest rates are on every plan, including free.

## 📦 Installation

```bash
npm install bcu-exchange-rate
```

```bash
yarn add bcu-exchange-rate
```

```bash
pnpm add bcu-exchange-rate
```

Requires Node 18+ (global `fetch`); also runs on Bun, Deno and edge runtimes. Also published under the org scope as [`@allratestoday/bcu-exchange-rate`](https://www.npmjs.com/package/@allratestoday/bcu-exchange-rate) — same code, same versions.

## 🏁 Quick start

```js
import { getRate } from 'bcu-exchange-rate';

const pair = await getRate('USD', 'UYU', { apiKey: 'art_live_...' });
console.log(pair.rate, pair.rate_date); // the official Central Bank of Uruguay rate, on the central bank's own date
```

## 📚 API reference

- [Latest pair rate](#latest-pair-rate) — one pair from the latest published table
- [Full published table](#full-published-table) — everything the central bank printed, in one call
- [Table for a date](#table-for-a-date) — the official table for an invoice or filing date
- [Daily time series](#daily-time-series) — one pair across a date range

---

### Latest pair rate

Free plan and up. Pairs the central bank does not print directly are resolved from its table and flagged (see *Published vs derived rates* below).

```js
const pair = await getRate('USD', 'UYU', { apiKey: 'art_live_...' });
```

**Response:**

```javascript
{
  bank: 'bcu',
  name: 'Central Bank of Uruguay',
  rate_date: '2026-10-08',   // Central Bank of Uruguay's own publication date
  source: 'USD',
  target: 'UYU',
  rate: 40.21,
  rate_type: 'sell',
  derived: false,
  method: 'published',
  disclaimer: 'Official rates as published by the named central bank. On weekends/holidays the most recent published rate_date is returned.'
}
```

### Full published table

Free plan and up. The complete table for the latest publication date.

```js
import { getLatestRates } from 'bcu-exchange-rate';

const table = await getLatestRates({ apiKey: 'art_live_...' });
console.log(table.rate_date, table.rates.length);
```

**Response:**

```javascript
{
  bank: 'bcu',
  name: 'Central Bank of Uruguay',
  rate_date: '2026-10-08',
  rates: [
    { "base": "USD", "quote": "UYU", "type": "sell", "value": 40.21 },
    { "base": "USD", "quote": "UYU", "type": "buy", "value": 40.21 },
    // … the rest of the published table (30 currencies vs UYU)
  ],
  disclaimer: '…'
}
```

### Table for a date

Paid plans. The official table for any date since 2000 — weekends and holidays return the most recent published date, flagged via `published_on_requested_date`, which is exactly the in-force rate a filing needs.

```js
import { getRatesForDate } from 'bcu-exchange-rate';

const day = await getRatesForDate('2026-06-30', { apiKey: 'art_live_...' });
// Optionally narrow to one pair:
const one = await getRatesForDate('2026-06-30', { apiKey: 'art_live_...', source: 'USD', target: 'UYU' });
```

**Response:**

```javascript
{
  bank: 'bcu',
  requested_date: '2026-06-30',
  rate_date: '2026-06-30',                // the date actually published
  published_on_requested_date: true,      // false when a weekend/holiday fell back
  rates: [ /* the full table for that date */ ],
  disclaimer: '…'
}
```

### Daily time series

Paid plans. One resolved rate per publication date — ready for charting, revaluation runs, or audit workpapers.

```js
import { getHistory } from 'bcu-exchange-rate';

const series = await getHistory(
  { source: 'USD', target: 'UYU', from: '2026-01-01', to: '2026-10-08' },
  { apiKey: 'art_live_...' }
);
```

**Response:**

```javascript
{
  bank: 'bcu',
  source: 'USD',
  target: 'UYU',
  from: '2026-01-01',
  to: '2026-10-08',
  count: 152,
  rates: [
    // one entry per publication date
    { date: '2026-10-08', rate: 40.21, rate_type: 'sell', derived: false, method: 'published' },
    // …
  ],
  disclaimer: '…'
}
```

Pass `{ symbol: 'USD' }` instead of `source`/`target` to get the raw published rows for one currency (all rate types, no pair resolution).

---

## 🗺️ Currencies covered

Central Bank of Uruguay currently publishes rates covering **30 currencies** against the UYU (as of the latest table):

🇦🇷 `ARS` · 🇦🇺 `AUD` · 🇧🇷 `BRL` · 🇨🇦 `CAD` · 🇨🇭 `CHF` · 🇨🇱 `CLP` · 🇨🇳 `CNY` · 🇨🇴 `COP` · 🇩🇰 `DKK` · 🇪🇺 `EUR` · 🇬🇧 `GBP` · 🇭🇰 `HKD` · 🇭🇺 `HUF` · 🇮🇳 `INR` · 🇮🇸 `ISK` · 🇯🇵 `JPY` · 🇰🇷 `KRW` · 🇲🇽 `MXN` · 🇲🇾 `MYR` · 🇳🇴 `NOK` · 🇳🇿 `NZD` · 🇵🇪 `PEN` · 🇵🇾 `PYG` · 🇷🇺 `RUB` · 🇸🇪 `SEK` · 🇹🇷 `TRY` · 🇺🇸 `USD` · 🇻🇪 `VES` · `XDR` · 🇿🇦 `ZAR`

## 🏛️ Source

The Central Bank of Uruguay publishes daily official quotations — buying and selling rates for about 30 currencies against the peso, with each day's table set at the previous evening's close. It is the reference Uruguayan accounting, customs and courts cite, and the published history reaches back to 2000.

- Publisher's own page: [Cotizaciones](https://www.bcu.gub.uy/Estadisticas-e-Indicadores/Paginas/Cotizaciones.aspx) · [www.bcu.gub.uy](https://www.bcu.gub.uy)
- Publication: every business day; the exact schedule, freshness status and any current delay are on the [Central Bank of Uruguay rates page](https://allratestoday.com/central-bank-rates-api/bcu/)
- Values are stored unmodified, with the publisher's own `rate_date` on every row — see the [methodology](https://allratestoday.com/official-rates-methodology/)

## 🧭 Reading the numbers

- `value` is always **quote currency per 1 unit of base currency** (`base: "EUR", quote: "USD", value: 1.15` means 1 EUR = 1.15 USD).
- Central Bank of Uruguay quotes **UYU per 1 unit of foreign currency** (e.g. `base: "USD", quote: "UYU"` means UYU per one US dollar).
- Need the other way round? Ask `getRate(target, source)` and the API inverts or crosses for you, flagged `derived: true` — never divide a published rate yourself in a compliance workflow.
- `rate_type` tells you which of the central bank's series a row belongs to (`sell` here); some publishers print buy/sell or several fixings for the same pair.

## 🧩 ERP & accounting systems

Loading the official Central Bank of Uruguay rate into an accounting system is a supported workflow, not a hack. Step-by-step guides with the direction each system expects:

- [Dynamics 365 Business Central](https://allratestoday.com/docs/integrations/business-central/) — built-in Currency Exchange Rate Service, no code
- [Xero](https://allratestoday.com/docs/integrations/xero/) · [QuickBooks Online](https://allratestoday.com/docs/integrations/quickbooks/) · [SAP S/4HANA and ECC](https://allratestoday.com/docs/integrations/sap/) · [Odoo](https://allratestoday.com/docs/integrations/odoo/)

The same keyed endpoints return `?format=csv`, `?format=xml` and `?format=xlsx`, and accept the key as `?api_key=` on the URL for importers that cannot send headers:

```bash
curl "https://allratestoday.com/api/v1/central-bank/bcu/latest?format=xml&api_key=art_live_..."
```

## 🤖 AI agents

- MCP server: `npx -y @allratestoday/central-bank-mcp` (stdio) or the hosted endpoint `https://allratestoday.com/api/mcp` — tools for official rates, history, cross-bank comparison and publication calendars
- Already using the general SDK or MCP server? Since 2026-10-01 [`@allratestoday/sdk`](https://www.npmjs.com/package/@allratestoday/sdk) 1.4+ has `officialRates('bcu')` and [`@allratestoday/mcp-server`](https://www.npmjs.com/package/@allratestoday/mcp-server) 0.6+ has a `get_official_rates` tool — both return this source's latest table with no key, so you can add it without a second dependency
- Claude Code plugin (no key): `/plugin marketplace add AllRates-Today/claude-code-plugin` then `/plugin install allratestoday@allratestoday` — bundles both MCP servers plus an `/official-rate bcu ...` command
- Machine-readable site guide: [llms.txt](https://allratestoday.com/llms.txt) · [for-ai-agents](https://allratestoday.com/for-ai-agents/)

## ⚖️ Published vs derived rates

If Central Bank of Uruguay does not print a pair directly, the API resolves it from the central bank's own table and says so — official and computed values are never confused:

| `method` | `derived` | Meaning |
| --- | --- | --- |
| `published` | `false` | The central bank printed this pair directly |
| `inverse` | `true` | Computed as 1 ÷ the published opposite direction |
| `cross` | `true` | Computed via UYU from two published rates |

## 🛡️ Error handling

Errors are thrown as `Error` with `status` (HTTP code) and `body` (the API's JSON error) attached:

```js
try {
  const pair = await getRate('USD', 'XXX', { apiKey: 'art_live_...' });
} catch (err) {
  console.log(err.message); // human-readable reason
  console.log(err.status);  // e.g. 404
}
```

| Status | Meaning |
| ------ | ------- |
| — | Missing `apiKey` (thrown before any request) |
| `400` | Malformed date or parameters |
| `401` | Invalid API key |
| `403` | Endpoint needs a [paid plan](https://allratestoday.com/pricing/) (historical dates & series) |
| `404` | Pair or date range not covered by Central Bank of Uruguay |
| `429` | Monthly quota exceeded |

## 🔷 TypeScript

Full definitions ship with the package — no `@types` install:

```ts
import type { LatestRates, PairRate, DatedRates, RateEntry, HistoryQuery, RequestOptions } from 'bcu-exchange-rate';
```

## 📦 CommonJS

```javascript
const { getRate } = require('bcu-exchange-rate');

getRate('USD', 'UYU', { apiKey: 'art_live_...' }).then((pair) => console.log(pair.rate));
```

## 💡 Quota tips

- Rates change once per business day — cache the published table locally and a small monthly quota goes a long way.
- Every request counts toward your AllRatesToday quota, shared across all AllRatesToday endpoints on your key.

## 📖 Methods reference

| Method | Plan | Description |
| ------ | ---- | ----------- |
| `getRate(source, target, { apiKey })` | Free | Latest rate for one pair, resolved from the published table |
| `getLatestRates({ apiKey })` | Free | The central bank's full latest published table |
| `getRatesForDate(date, { apiKey, source?, target? })` | Paid | The official table (or one pair) for a YYYY-MM-DD date |
| `getHistory({ symbol \| source+target, from?, to? }, { apiKey })` | Paid | Daily series since 2000 |

## 📥 Bulk data (no key)

Need the whole archive rather than an API call? The same published tables are mirrored daily as open data:

- Hugging Face: [AllRates/central-bank-exchange-rates](https://huggingface.co/datasets/AllRates/central-bank-exchange-rates) — one CSV per institution (`rates/bcu.csv`)
- Kaggle: [allratestoday/central-bank-exchange-rates](https://www.kaggle.com/datasets/allratestoday/central-bank-exchange-rates)
- CDN JSON: `https://cdn.jsdelivr.net/gh/AllRates-Today/central-bank-exchange-rates@main/data/bcu/latest.json`

## 🔗 Links

- [Central Bank of Uruguay rates page](https://allratestoday.com/central-bank-rates-api/bcu/) — live table, publication cadence, FAQ
- [All central bank sources](https://allratestoday.com/central-bank-rates-api/)
- [Package docs on the site](https://allratestoday.com/docs/sdk/bcu-exchange-rate/) · [ERP integration guides](https://allratestoday.com/docs/integrations/)
- [API documentation](https://allratestoday.com/docs/#central-bank) · [Interactive reference](https://allratestoday.com/api-reference/) · [Methodology](https://allratestoday.com/official-rates-methodology/)
- [Register (free)](https://allratestoday.com/register) · [Pricing](https://allratestoday.com/pricing/)
- [GitHub](https://github.com/AllRates-Today/bcu-exchange-rate)

## 📜 License

MIT
