# geojson

A repository for public GeoJSON files, intended for use with [Lightdash](https://www.lightdash.com/) charts and other mapping tools.

## Available Files

| File | Description |
|------|-------------|
| [`gbr/regions.geojson`](gbr/regions.geojson) | UK regions (9 English regions + Wales, Scotland, Northern Ireland) |
| [`gbr/gbr_electricity_gsp_groups.geojson`](gbr/gbr_electricity_gsp_groups.geojson) | GB electricity GSP Groups / DNO license areas (14 areas, as of 2024-05-03) |
| [`gbr/gbr_electricity_gsp_regions.geojson`](gbr/gbr_electricity_gsp_regions.geojson) | GB electricity Grid Supply Point (GSP) regions (362 features, as of 2026-02-09) |
| [`world/countries.geojson`](world/countries.geojson) | World countries with ISO 3166 codes (simplified boundaries) |

## Using with Lightdash

To reference a GeoJSON file in a Lightdash chart, use the raw GitHub URL:

```
https://raw.githubusercontent.com/brettshirley/geojson/main/<path-to-file>
```

### Examples

**UK Regions:**
```
https://raw.githubusercontent.com/brettshirley/geojson/main/gbr/regions.geojson
```

**GB Electricity GSP Groups (DNO License Areas):**
```
https://raw.githubusercontent.com/brettshirley/geojson/main/gbr/gbr_electricity_gsp_groups.geojson
```

**GB Electricity GSP Regions:**
```
https://raw.githubusercontent.com/brettshirley/geojson/main/gbr/gbr_electricity_gsp_regions.geojson
```

**World Countries:**
```
https://raw.githubusercontent.com/brettshirley/geojson/main/world/countries.geojson
```

## File Structure

```
geojson/
├── gbr/
│   ├── regions.geojson                       # UK regions with ONS codes and names
│   ├── gbr_electricity_gsp_groups.geojson    # GB electricity GSP Groups / DNO license areas
│   └── gbr_electricity_gsp_regions.geojson   # GB electricity Grid Supply Point (GSP) regions
└── world/
    └── countries.geojson              # World countries with ISO 3166 alpha-2 and alpha-3 codes
```

## GeoJSON Properties

### UK Regions (`gbr/regions.geojson`)

Each feature has the following properties:

| Property | Description | Example |
|----------|-------------|---------|
| `name` | Region name | `"London"` |
| `code` | ONS geography code | `"E12000007"` |

### GB Electricity GSP Groups (`gbr/gbr_electricity_gsp_groups.geojson`)

Grid Supply Point (GSP) Group areas for Great Britain (England, Scotland, and Wales). These correspond to the 14 Distribution Network Operator (DNO) license areas. Source data dated 2024-05-03. Contains 14 features covering the 14 DNO regions operated by 6 DNO companies.

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

### GB Electricity GSP Regions (`gbr/gbr_electricity_gsp_regions.geojson`)

Grid Supply Point (GSP) regions for Great Britain — a more granular subdivision of the GSP Groups. Source data dated 2026-02-09. Contains 362 features.

Each feature has the following properties:

| Property | Description | Example |
|----------|-------------|---------|
| `fid` | Feature ID | `1` |
| `GSPs` | GSP identifier | `"LEGA_1"` |
| `GSPGroup` | GSP Group code (matches `Name` in the GSP Groups file) | `"_D"` |
| `SSEP17Zone` | SSEP 2017 zone number (1–17) | `7` |
| `DSCPs` | DSCP identifier(s), if any | `null` |
| `InGroup_` | Whether the region is part of the named group (`Y`/`N`, may be pipe-delimited for multi-group regions) | `"Y"` |
| `CDCA_I030` | CDCA I030 identifier | `"=GSP_LEGA_1"` |

### World Countries (`world/countries.geojson`)

Each feature has the following properties:

| Property | Description | Example |
|----------|-------------|---------|
| `name` | Country name | `"United Kingdom"` |
| `iso_a2` | ISO 3166-1 alpha-2 code | `"GB"` |
| `iso_a3` | ISO 3166-1 alpha-3 code | `"GBR"` |
