# geojson

A repository for public GeoJSON files, intended for use with [Lightdash](https://www.lightdash.com/) charts and other mapping tools.

## Available Files

| File | Description |
|------|-------------|
| [`uk/regions.geojson`](uk/regions.geojson) | UK regions (9 English regions + Wales, Scotland, Northern Ireland) |
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

**World Countries:**
```
https://raw.githubusercontent.com/brettshirley/geojson/main/world/countries.geojson
```

## File Structure

```
geojson/
├── uk/
│   └── regions.geojson       # UK regions with ONS codes and names
└── world/
    └── countries.geojson     # World countries with ISO 3166 alpha-2 and alpha-3 codes
```

## GeoJSON Properties

### UK Regions (`uk/regions.geojson`)

Each feature has the following properties:

| Property | Description | Example |
|----------|-------------|---------|
| `name` | Region name | `"London"` |
| `code` | ONS geography code | `"E12000007"` |

### World Countries (`world/countries.geojson`)

Each feature has the following properties:

| Property | Description | Example |
|----------|-------------|---------|
| `name` | Country name | `"United Kingdom"` |
| `iso_a2` | ISO 3166-1 alpha-2 code | `"GB"` |
| `iso_a3` | ISO 3166-1 alpha-3 code | `"GBR"` |
