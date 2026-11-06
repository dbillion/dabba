# 🍱 Dabba — Cloud Kitchen Delivery City

**World 05** from the World Prompt Pack — a single-file interactive 3D food delivery operations dashboard built with Three.js.

🔗 **Live Demo**: [https://dbillion.github.io/dabba/](https://dbillion.github.io/dabba/)

![Dabba](https://img.shields.io/badge/World_05-Dabba-E8452C?style=for-the-badge)

## What is this?

A **city-builder-style** 3D Chennai neighbourhood with live food delivery simulation, rider tracking, and a glassmorphic dashboard — all in a single `index.html` file. Features a **bright warm theme** with off-white backgrounds and tomato red accents.

## Procedural 3D Technique

Every 3D object is generated **procedurally at runtime** — zero external models:

| Element | Geometry Technique |
|---------|-------------------|
| **Street grid** | `BoxGeometry` roads on X/Z axes with dashed centre lines |
| **Zebra crossings** | Repeated thin `BoxGeometry` stripes at intersections |
| **Cloud kitchens** | `BoxGeometry` base + red roof + `CylinderGeometry` exhaust fans (rotating) |
| **Apartments** | `BoxGeometry` with varying heights, `BoxGeometry` windows, `CylinderGeometry` water tanks |
| **Tech park** | `BoxGeometry` with glass facade (transparent material) |
| **Shops** | `BoxGeometry` with coloured awnings |
| **Temple tower** | Stacked decreasing `BoxGeometry` (gopuram) + `SphereGeometry` gold finial |
| **Park** | `PlaneGeometry` grass + `CylinderGeometry` trunks + `ConeGeometry` crowns + fountain |
| **Metro station** | `BoxGeometry` platform + pillars (`CylinderGeometry`) + train carriages |
| **Riders** | `Group` of `BoxGeometry` scooter + `BoxGeometry` body + `SphereGeometry` helmet + delivery box |
| **Vehicles** | Cars (`BoxGeometry` + glass cabin) and auto-rickshaws with `CylinderGeometry` wheels |
| **Traffic lights** | `CylinderGeometry` pole + `SphereGeometry` red/green lamps with emissive cycling |

## Delivery Simulation

The autonomous simulation runs continuously:
1. **Order placed** → pin drops on destination building
2. **Kitchen assigned** → order enters cooking queue
3. **Rider dispatched** → idle rider navigates to kitchen via street grid
4. **Pickup** → rider status changes, heads to destination
5. **Delivered** → green burst effect, rider returns to idle
6. Multiple riders and orders run simultaneously

## Weather & Seasons

| Season | Visual Effect |
|--------|--------------|
| **Summer** | Bright warm sunlight, clear sky |
| **Monsoon** | Blue-tinted badge (riders in raincoats planned) |
| **Festival** | Red accent badge (string lights planned) |
| **Night** | Street lights activate, ambient drops, dark sky |

## Dashboard Features

- **KPI Row**: Orders this hour, Avg delivery time, Riders online
- **Order Tracker**: Placed → Accepted → Cooking → Picked Up → On the Way → Delivered
- **Tables**: Orders (ID, dish, ₹ total, status), Riders (name, count, distance, status), Kitchens (name, queue, prep time)
- **Selection**: Click any rider/kitchen/building for detail panel with live stats
- **Camera**: Follows selected rider in real-time

## Fully Responsive

- **Desktop**: Top bar with search + zone switcher, KPI cards, right panel with tables, bottom-left tracker
- **Mobile**: Search bar + area pills, bottom sheet with 5 tabs (Track/Orders/Riders/Kitchens/Info), 5-button bottom nav

## Tech Stack

- **Three.js r128** — 3D rendering (local `js/` with CDN fallback)
- **Vanilla CSS** — glassmorphic panels, no frameworks
- **Single file** — everything in `index.html`

## Run Locally

```bash
npx serve .
# or
python3 -m http.server 8085
```

## World Prompt Pack

| # | World | Theme | Status |
|---|-------|-------|--------|
| 01 | [Gateflow](https://dbillion.github.io/gateflow/) | Airport | ✅ Live |
| 02 | [Orbitline](https://dbillion.github.io/orbitline/) | Spaceport | ✅ Live |
| 03 | [Berthwise](https://dbillion.github.io/berthwise/) | Container Port | ✅ Live |
| 04 | [Boundary](https://dbillion.github.io/boundary/) | Cricket Stadium | ✅ Live |
| **05** | **[Dabba](https://dbillion.github.io/dabba/)** | **Cloud Kitchen** | **✅ Live** |
| 06 | Railgrid | Metro Rail | 🔜 |

## License

MIT
