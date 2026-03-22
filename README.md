# MEXC Exchange - Live Trading Statistics WordPress Plugin (Overview)

Public overview repository for the private WordPress plugin implementation.

> This repository documents capabilities and integration architecture only. Private implementation code is intentionally not published.

## Live status

- Product mode: live WordPress frontend plugin connected to private FastAPI backend
- Live URL: `https://logicencoder.com/mexc-app/`

## Problem solved

Provide an operator-friendly, web-delivered dashboard in WordPress while keeping backend processing isolated. The plugin renders realtime metrics, exposes snapshot ingestion endpoints, and handles SEO/sitemap tasks for generated pages.

## Tech stack

- PHP (WordPress plugin)
- WordPress Shortcodes, AJAX, REST API routes
- JavaScript dashboard runtime in plugin-rendered markup
- Backend integration through HTTP/WS endpoints

## Core plugin responsibilities

- Frontend rendering via shortcode: `[mexc_dashboard]`
- AJAX fetch of backend stats and monitoring
- REST endpoint for snapshot ingest:
  - `POST /wp-json/mexc/v1/snapshot`
- Snapshot settings/status and sitemap controls in admin
- SEO meta/canonical handling for snapshot pages

## Integration flow

1. User opens plugin-driven dashboard page
2. Plugin JS requests backend API data
3. Backend streams/fetches fresh trading metrics
4. Backend periodically posts snapshots to plugin REST endpoint
5. Plugin stores snapshot pages and updates sitemap/search engine ping workflow

## Security boundary

- Private repository keeps implementation details private
- Public overview excludes:
  - endpoint secrets
  - sensitive server wiring
  - private admin internals

## UI updates in current iteration

- Removed related coins widget from live dashboard layout
- Kept coin display mode controls (`Ticker`, `Name`, `Both`)
- Adjusted mobile layout so display mode controls sit under search input to prevent overlap

## Screenshots

![MEXC Live Trading Statistics Dashboard](./screenshot.png)

## Author note

The plugin is built with a practical, self-taught delivery style: solve the immediate operator UX need, optimize for constrained environments, and keep architecture maintainable across backend/frontend boundaries.
