<p align="center">
  <a href="https://yatmo.com"><img src="https://raw.githubusercontent.com/Yatmo/.github/main/profile/img/logo.png" width="96" alt="Yatmo"></a>
</p>

<h1 align="center">Neighbourhood intelligence for real estate</h1>

<p align="center">
  Maps, points of interest, travel times and written neighbourhood descriptions for property pages,
  in 25 countries. Plugins for the web, WordPress, Odoo and mobile apps, a REST API and an MCP server for AI assistants.
</p>

<p align="center">
  <a href="https://yatmo.com">Website</a> ·
  <a href="https://documentation.yatmo.com">Documentation</a> ·
  <a href="https://documentation.yatmo.com/getting-started">Quick start</a> ·
  <a href="https://yatmo.com/#map-playground">Live playground</a> ·
  <a href="https://documentation.yatmo.com/countries">Countries</a>
</p>

<p align="center">
  <img src="https://raw.githubusercontent.com/Yatmo/.github/main/profile/img/map-and-summary.png" width="800" alt="Yatmo map with points of interest, travel times and the neighbourhood summary on a property page">
</p>

## What a property page gets

- **Map with the places that matter**: schools, nurseries, shops, public transport, stations, motorways, healthcare, leisure, with real travel times on foot, by bike, by car and by public transport.
- **Neighbourhood text**: a written description of the area (education, shopping, public transport, roads, leisure, nearby cities), generated per location, in the languages of the country, and indexable by search engines and AI assistants.
- **Scores, isochrones and routes**: areas reachable in 5, 10 and 20 minutes, route from the property to any place the visitor clicks, favourite addresses with the visitor's own commute.
- **Search by travel time, by drawn zone or by lifestyle** for listing search pages, and clustered listings on the map.
- **Cookieless and self-contained**: no Google Maps key, no tracking, one iframe or one script tag.

Countries: Albania, Australia, Austria, Belgium, Bosnia and Herzegovina, Bulgaria, Canada, Croatia, Cyprus, France, Germany, Greece, Ireland, Italy, Luxembourg, Malta, Montenegro, Morocco, the Netherlands, Portugal, Serbia, Slovenia, Spain, Switzerland and the United Kingdom. 23 languages.

## Pick your integration

| Stack | What you get | Where |
|---|---|---|
| **Any website** | One iframe: map, summary, scores, isochrones, routes, configured by URL parameters | [Iframe plugin](https://documentation.yatmo.com/plugins/iframe) |
| **JavaScript** | Map, summary table and summary text as script tags with one config object; listing search on the map | [JavaScript plugins](https://documentation.yatmo.com/plugins/js-map) |
| **npm (Node, TypeScript)** | `@yatmo/sdk`: typed API client for servers and edge (text as HTML, summaries, POIs, isochrones, routes, geocoding); `@yatmo/maps`: the browser plugins from npm | [Yatmo/yatmo-sdk-js](https://github.com/Yatmo/yatmo-sdk-js) · [@yatmo/sdk](https://www.npmjs.com/package/@yatmo/sdk) · [@yatmo/maps](https://www.npmjs.com/package/@yatmo/maps) |
| **WordPress** | Blocks and shortcodes for the map and the indexable neighbourhood text | [wordpress.org/plugins/yatmo-map](https://wordpress.org/plugins/yatmo-map/) · [Yatmo/yatmo-plugin-wordpress](https://github.com/Yatmo/yatmo-plugin-wordpress) |
| **Odoo 17 to 20** | Website building blocks and QWeb templates for the map and the indexable text | [apps.odoo.com](https://apps.odoo.com/apps/modules/20.0/yatmo_map) · [Yatmo/yatmo-plugin-odoo](https://github.com/Yatmo/yatmo-plugin-odoo) |
| **iOS** | Swift package, MapLibre Native | [Yatmo/yatmo-sdk-ios](https://github.com/Yatmo/yatmo-sdk-ios) |
| **Android** | Kotlin, XML views and Jetpack Compose, MapLibre | [Yatmo/yatmo-sdk-android](https://github.com/Yatmo/yatmo-sdk-android) |
| **React Native** | `@yatmo/react-native`, TypeScript | [Yatmo/yatmo-sdk-react-native](https://github.com/Yatmo/yatmo-sdk-react-native) |
| **Flutter** | `yatmo_sdk` on pub.dev | [Yatmo/yatmo-sdk-flutter](https://github.com/Yatmo/yatmo-sdk-flutter) |
| **AI assistants and agents** | MCP server: location summary, nearby POIs, nearest by category, accessibility profile | [Yatmo/yatmo-mcp](https://github.com/Yatmo/yatmo-mcp) · [docs](https://documentation.yatmo.com/mcp) |
| **Your own backend** | REST API: summary, listing enrichment, points, isochrones, geocoding, routes, static map images | [API documentation](https://documentation.yatmo.com/api) |

## Quick start

A Yatmo licence key is required: [get one](https://yatmo.com). The documentation pages embed live examples, and [Yatmo/yatmo-examples](https://github.com/Yatmo/yatmo-examples) holds ready-to-run pages: iframe, JavaScript map, neighbourhood text, a complete property page, search by travel time, REST API.

**Iframe**, the smallest integration:

```html
<iframe
    width="100%" height="560"
    src="https://map.yatmo.com/plugin.html?licenseKey=YOUR_KEY&country=BE&language=EN&latitude=50.8520525&longitude=4.3442926&mode=overlay&zoom=15"
    frameborder="0" allowfullscreen loading="lazy"></iframe>
```

**JavaScript**, when the map must blend into your page:

```html
<div id="map" style="width: 100%; height: 500px;"></div>
<script>
    yatmoConfig = {
        licenseKey: 'YOUR_FRONTEND_KEY',
        language: 'EN',
        country: 'BE',
        container: 'map',
        center: [4.352514, 50.846714],   // [longitude, latitude]
        zoom: 16
    };
</script>
<script src="https://map.yatmo.com/map_v3.js"></script>
```

**REST API**, from your server (backend key):

```bash
curl -H 'LicenseKey: YOUR_KEY' \
  'https://be.yatmo.com/summary?latitude=50.8520525&longitude=4.3442926&language=EN'
```

**MCP server**, for Claude, ChatGPT, Cursor or your own agent:

```json
{
  "mcpServers": {
    "yatmo": {
      "url": "https://mcp.yatmo.com/mcp/v1",
      "headers": { "LicenceKey": "YOUR_KEY" }
    }
  }
}
```

## In the editor and on the phone

<p align="center">
  <img src="https://raw.githubusercontent.com/Yatmo/.github/main/profile/img/neighbourhood-text.png" width="800" alt="The neighbourhood text, indexable by search engines, on a property page">
</p>
<p align="center">
  <img src="https://raw.githubusercontent.com/Yatmo/.github/main/profile/img/odoo-builder.png" width="800" alt="The Yatmo Map block and its options in the Odoo website builder">
</p>
<p align="center">
  <img src="https://raw.githubusercontent.com/Yatmo/.github/main/profile/img/mobile-ios.png" width="240" alt="Yatmo map in a demo iOS app">
  <img src="https://raw.githubusercontent.com/Yatmo/.github/main/profile/img/mobile-android.png" width="240" alt="Yatmo map in a demo Android app">
</p>

## About

Yatmo SRL, Belgium. The plugins and SDKs in this organisation are open source (MIT or LGPL); the data and the API are a paid service for real estate portals, agency networks and developers. [Terms](https://yatmo.com/terms) · [Privacy](https://yatmo.com/privacy) · support@yatmo.com
