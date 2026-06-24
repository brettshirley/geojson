# geojson

A repository for public GeoJSON files, intended for use with [Lightdash](https://www.lightdash.com/) charts and other mapping tools.

## Available Files

| File | Description |
|------|-------------|
| [`uk/regions.geojson`](uk/regions.geojson) | UK regions (9 English regions + Wales, Scotland, Northern Ireland) |
| [`uk/gbr_electricity_dno.geojson`](uk/gbr_electricity_dno.geojson) | GB electricity Distribution Network Operator (DNO) license areas (14 areas, as of 2024-05-03) |
| [`world/countries.geojson`](world/countries.geojson) | World countries with ISO 3166 codes (simplified boundaries) |

## Using with Lightdash

To reference a GeoJSON file in a Lightdash chart, use the raw GitHub URL:

```
https://raw.githubusercontent.com/brettshirley/geojson/main/<path-to-file>
```

### Examples

**UK Regions:**
```
https://raw.githubusercontent.com/brettshirley/geojson/main/uk/regions.geojson
```

**GB Electricity DNO License Areas:**
```
https://raw.githubusercontent.com/brettshirley/geojson/main/uk/gbr_electricity_dno.geojson
```

**World Countries:**
```
https://raw.githubusercontent.com/brettshirley/geojson/main/world/countries.geojson
```

## File Structure

```
geojson/
├── uk/
│   ├── regions.geojson                # UK regions with ONS codes and names
│   └── gbr_electricity_dno.geojson    # GB electricity DNO license areas
└── world/
    └── countries.geojson              # World countries with ISO 3166 alpha-2 and alpha-3 codes
```

## GeoJSON Properties

### UK Regions (`uk/regions.geojson`)

Each feature has the following properties:

| Property | Description | Example |
|----------|-------------|---------|
| `name` | Region name | `"London"` |
| `code` | ONS geography code | `"E12000007"` |

### GB Electricity DNO License Areas (`uk/gbr_electricity_dno.geojson`)

Distribution Network Operator (DNO) license areas for Great Britain (England, Scotland, and Wales). Source data dated 2024-05-03. Contains 14 features covering the 14 DNO regions operated by 6 DNO companies.

Each feature has the following properties:

| Property | Description | Example |
|----------|-------------|---------|
| `ID` | Numeric area identifier | `10` |
| `Name` | Internal area name code | `"_A"` |
| `DNO` | DNO short code | `"UKPN"` |
| `Area` | DNO license area name | `"East England"` |
| `DNO_Full` | Full DNO company name | `"UK Power Networks"` |

DNO codes:

| Code | Company | Areas |
|------|---------|-------|
| `ENWL` | Electricity North West | North West England |
| `NGED` | National Grid Electricity Distribution | East Midlands, West Midlands, South Wales, South West England |
| `NPG` | Northern Powergrid | North East England, Yorkshire |
| `SPEN` | SP Energy Networks | North Wales, Merseyside and Cheshire; South and Central Scotland |
| `SSEN` | Scottish and Southern Electricity Networks | North Scotland, Southern England |
| `UKPN` | UK Power Networks | East England, London, South East England |

### World Countries (`world/countries.geojson`)

Each feature has the following properties:

| Property | Description | Example |
|----------|-------------|---------|
| `name` | Country name | `"United Kingdom"` |
| `iso_a2` | ISO 3166-1 alpha-2 code | `"GB"` |
| `iso_a3` | ISO 3166-1 alpha-3 code | `"GBR"` |
