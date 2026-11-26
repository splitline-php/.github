<p align="center">
  <img src="../assets/splitline-social-preview.png" alt="Splitline — Open-source PHP endurance telemetry & self-hosted analytics" width="100%" />
</p>

## Repositories

### [Splitline App (`splitline-php/splitline`)](https://github.com/splitline-php/splitline)
Local-first, self-hosted personal endurance and health telemetry platform built with Laravel, Inertia, Vue, and SQLite. Packaged as a multi-arch Docker image (`ghcr.io/splitline-php/splitline`) with zero external database or cache services.

### [Splitline Ingest Monorepo (`splitline-php/ingest`)](https://github.com/splitline-php/ingest)
MIT-licensed PHP 8.5 package monorepo powering Splitline's FIT parsing, weather & wind-vector enrichment, Best Efforts analytics, and wearable ingestion. All packages are stateless, require zero `ext-intl` or `ext-bcmath`, pass PHPStan Level 8 with no baseline, and publish via automated subtree splits to Packagist:

| Package | Packagist | Purpose |
| :--- | :--- | :--- |
| [`splitline/core`](https://github.com/splitline-php/core) | [![Packagist Version](https://img.shields.io/packagist/v/splitline/core)](https://packagist.org/packages/splitline/core) | Contracts, immutable SI DTOs, sliding-window rate limiter, `ActivityClassifier`, `BestEffortCalculator` |
| [`splitline/parsers`](https://github.com/splitline-php/parsers) | [![Packagist Version](https://img.shields.io/packagist/v/splitline/parsers)](https://packagist.org/packages/splitline/parsers) | Pure PHP binary `.fit` and `.zip` parser (`FitParser`) |
| [`splitline/weather`](https://github.com/splitline-php/weather) | [![Packagist Version](https://img.shields.io/packagist/v/splitline/weather)](https://packagist.org/packages/splitline/weather) | Adaptive route waypoint sampling, wind-vector math, Open-Meteo client & enricher |
| [`splitline/laravel`](https://github.com/splitline-php/laravel) | [![Packagist Version](https://img.shields.io/packagist/v/splitline/laravel)](https://packagist.org/packages/splitline/laravel) | Laravel HTTP, Cache, Sleep, and ServiceProvider bridge |
| [`splitline/provider-garmin-personal`](https://github.com/splitline-php/provider-garmin-personal) | [![Packagist Version](https://img.shields.io/packagist/v/splitline/provider-garmin-personal)](https://packagist.org/packages/splitline/provider-garmin-personal) | Garmin Connect Personal API provider (personal self-hosted use) |
| [`splitline/provider-file-import`](https://github.com/splitline-php/provider-file-import) | [![Packagist Version](https://img.shields.io/packagist/v/splitline/provider-file-import)](https://packagist.org/packages/splitline/provider-file-import) | Standalone `.fit` / `.zip` import provider with SHA-256 deduplication |

> **Want to add a new wearable provider (Oura, Polar, Suunto, Wahoo, Coros, Whoop)?** Read [`ADDING_A_PROVIDER.md`](https://github.com/splitline-php/ingest/blob/main/ADDING_A_PROVIDER.md) and open a pull request against [`splitline-php/ingest`](https://github.com/splitline-php/ingest).
