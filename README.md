# Kazakhstan Administrative Divisions / Қазақстан



## Overview

| Item | Details |
|------|---------|
| Region | 16 |
| District | 168 |
| Coordinates | ✅ Included (all levels) |
| Formats | JSON, NDJSON, CSV |
| License | CC-BY-4.0 |
| Last Updated | 2026-08-20 |
| Website | [openadmindata.org/kz](https://openadmindata.org/kz/) |
| API | [openadmindata.org/api/kz](https://openadmindata.org/api/kz/) |
| Flag | [PNG](https://onlygames.me/flags-png/kz/) · [SVG](https://onlygames.me/flags-svg/kz/) · [PDF](https://onlygames.me/flags-pdf/kz/) |
| National Anthem | [🎵 Listen & Download Kazakhstan National Anthem MP3](https://onlygames.me/national-anthems/kz/) |

## Browse by Region

| # | Region | Districts | Link |
|---|----|----|------|
| 1 | Ақтөбе (Aqtöbe) | 13 | [Browse](divisions/aqtobe-kz01/) |
| 2 | Қостанай (Qostanay) | 17 | [Browse](divisions/qostanay-kz02/) |
| 3 | Қызылорда (Qyzylorda) | 8 | [Browse](divisions/qyzylorda-kz03/) |
| 4 | Атырау (Atyrau) | 8 | [Browse](divisions/atyrau-kz04/) |
| 5 | Батыс Қазақстан (West Kazakhstan) | 12 | [Browse](divisions/west-kazakhstan-kz05/) |
| 6 | Ақмола (Aqmola) | 15 | [Browse](divisions/aqmola-kz06/) |
| 7 | Қарағанды (Qaraghandy) | 9 | [Browse](divisions/qaraghandy-kz07/) |
| 8 | Солтүстік Қазақстан (North Kazakhstan) | 12 | [Browse](divisions/north-kazakhstan-kz08/) |
| 9 | Павлодар (Pavlodar) | 10 | [Browse](divisions/pavlodar-kz09/) |
| 10 | Шығыс Қазақстан (East Kazakhstan) | 16 | [Browse](divisions/east-kazakhstan-kz10/) |
| 11 | Алматы облысы (Almaty) | 16 | [Browse](divisions/almaty-kz11/) |
| 12 | Маңғыстау (Mangghystau) | 5 | [Browse](divisions/mangghystau-kz12/) |
| 13 | Оңтүстік Қазақстан (South Kazakhstan) | 14 | [Browse](divisions/south-kazakhstan-kz13/) |
| 14 | Жамбыл (Zhambyl) | 11 | [Browse](divisions/zhambyl-kz14/) |
| 15 | Алматы (Almaty City) | 1 | [Browse](divisions/almaty-city-kz15/) |
| 16 | Астана (Astana) | 1 | [Browse](divisions/astana-kz16/) |

## Data Files

| File | Format | Description |
|------|--------|-------------|
| [all-region.json](data/all-region.json) | JSON | All 16 region records |
| [all-district.json](data/all-district.json) | JSON | All 168 district records |
| [all-flat.json](data/all-flat.json) | JSON | Levels 1-1 flat array |
| [all-flat.ndjson](data/all-flat.ndjson) | NDJSON | Streaming format |
| [all-flat.csv](data/all-flat.csv) | CSV | Spreadsheet format |
| [hierarchy.json](data/hierarchy.json) | JSON | Nested tree |
| [schema.json](data/schema.json) | JSON Schema | Data schema |

## Quick Start

### Python

```python
import json

with open("data/all-region.json", "r", encoding="utf-8") as f:
    data = json.load(f)

for r in data:
    print(f"{r['name']['local']} ({r['name']['en']}) — {r['children_count']['district']} districts")
```

### JavaScript

```javascript
import { readFileSync } from "fs";

const data = JSON.parse(readFileSync("data/all-region.json", "utf-8"));
console.log(`Total: ${data.length} regions`);
```

## Schema

| Field | Type | Description |
|-------|------|-------------|
| `id` | string | Unique identifier |
| `level` | integer | 1=region, 2=district |
| `level_name` | object | Level label (local + English) |
| `name.local` | string | Name in local script |
| `name.en` | string | English name |
| `name.slug` | string | URL-safe slug |
| `parent` | object/null | Parent division reference |
| `ancestors` | array | Full ancestor chain |
| `children_count` | object | Count of children per level |
| `zip_codes` | array | Postal codes (where available) |
| `geo.lat` | string | Latitude (WGS84) |
| `geo.lon` | string | Longitude (WGS84) |

Full schema: [data/schema.json](data/schema.json)

## Hierarchy Browse

```
divisions/{region-slug}/
```

Districts are listed inline in each region's README.

## AI Integration

- [llms.txt](docs/llms.txt) — Quick reference for AI agents
- [llms-full.txt](docs/llms-full.txt) — Summary with per-region links
- [Per-region data](docs/llms-full/) — Full data by region

## Citation

```
Kazakhstan Administrative Divisions Dataset (CC-BY-4.0)
URL: https://github.com/open-admin-data/kazakhstan-administrative-divisions
```

See [CITATION.cff](CITATION.cff) for machine-readable citation.

## License

- **Data**: [CC-BY-4.0](LICENSE)

## Related

- [Open Admin Data](https://openadmindata.org) — Browse, search and explore administrative divisions for every country
- [open-admin-data](https://github.com/open-admin-data) — GitHub organization with all country repos
- [ListBase](https://www.listbase.org) — Structured reference data for every country
