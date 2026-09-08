# Awesome Laravel Observability [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> A curated list of tools for finding out what a Laravel application is actually doing in production — errors, logs, metrics, traces, queues, and the dashboards that tie them together.

Laravel ships with good first-party tooling, and the community fills the gaps around it. Everything here is either open source or has a usable free tier; commercial services are marked and kept in their own section.

For Horizon-specific packages, see the sibling list [awesome-horizon](https://github.com/boring-o11y/awesome-horizon).

## Contents

- [First-party tools](#first-party-tools)
- [Application monitoring](#application-monitoring)
- [Errors and exceptions](#errors-and-exceptions)
- [Logging](#logging)
- [Log viewers](#log-viewers)
- [Metrics](#metrics)
- [Tracing](#tracing)
- [Profiling](#profiling)
- [Local debugging](#local-debugging)
- [Queues and background jobs](#queues-and-background-jobs)
- [Scheduled tasks](#scheduled-tasks)
- [Health checks](#health-checks)
- [Uptime monitoring](#uptime-monitoring)
- [Database and queries](#database-and-queries)
- [Audit and activity logs](#audit-and-activity-logs)
- [Pulse cards and Telescope watchers](#pulse-cards-and-telescope-watchers)
- [Self-hosted backends](#self-hosted-backends)
- [Hosted services](#hosted-services)
- [Reading](#reading)

## First-party tools

- [Telescope](https://github.com/laravel/telescope) - Request, query, job, and exception inspector. Built for local and staging; needs pruning and gating before it goes near production.
- [Pulse](https://github.com/laravel/pulse) - Real-time dashboard for slow queries, slow jobs, slow requests, usage, and exceptions, sampled and aggregated so it can run in production.
- [Horizon](https://github.com/laravel/horizon) - Dashboard and code-driven supervisor configuration for Redis queues.
- [Pail](https://github.com/laravel/pail) - Tail application logs from the console, with filtering by level, user, and message.
- [Nightwatch](https://github.com/laravel/nightwatch) - Agent package for Laravel's own hosted monitoring service.

## Application monitoring

- [laravel-top](https://github.com/leventcz/laravel-top) - `top`-style real-time view of requests per second, memory, and slowest routes, straight from the terminal.
- [Vigilance](https://github.com/anousss007/laravel-vigilance) - Driver-agnostic control center for queues, jobs, commands, and scheduler, with app-wide APM, tracing, and metrics.
- [Nightowl](https://github.com/lemed99/nightowl-agent) - Self-hosted monitoring agent positioned as a drop-in Nightwatch alternative.
- [Inspector](https://github.com/inspector-apm/inspector-laravel) - Code execution monitoring package for the Inspector service, open source agent with a free tier.
- [Live Profiler](https://github.com/badoo/liveprof) - Continuous profiling for live sites, aggregating samples over time, with a separate [web UI](https://github.com/badoo/liveprof-ui).
- [Vigilant](https://github.com/govigilant/vigilant) - Self-hosted all-in-one web monitoring: uptime, SSL, DNS, Lighthouse, and broken links.

## Errors and exceptions

- [sentry-laravel](https://github.com/getsentry/sentry-laravel) - Official Sentry SDK, with performance tracing, breadcrumbs, and queue job context. Works against self-hosted Sentry too.
- [Ignition](https://github.com/spatie/laravel-ignition) - The error page shipped with Laravel, with runnable solutions for common mistakes.
- [laravel-error-solutions](https://github.com/spatie/laravel-error-solutions) - Adds AI-generated and package-provided solutions to the error page.
- [laravel-flare](https://github.com/spatie/laravel-flare) - Reports errors to Flare, Spatie's hosted error tracker.
- [bugsnag-laravel](https://github.com/bugsnag/bugsnag-laravel) - Official Bugsnag notifier for Laravel and Lumen.
- [rollbar-php](https://github.com/rollbar/rollbar-php) - Rollbar client for PHP, with a Laravel service provider included.
- [honeybadger-laravel](https://github.com/honeybadger-io/honeybadger-laravel) - Official Honeybadger reporter.
- [laravel-exception-notify](https://github.com/guanguans/laravel-exception-notify) - Pushes exceptions to Slack, Discord, Telegram, DingTalk, Bark, mail, and a dozen other channels.
- [laravel-github-monolog](https://github.com/Naoray/laravel-github-monolog) - Log channel that opens (and deduplicates) GitHub issues for errors.

## Logging

- [laravel-http-logger](https://github.com/spatie/laravel-http-logger) - Middleware that logs incoming requests, with control over which fields are redacted.
- [laravel-request-logger](https://github.com/bilfeldt/laravel-request-logger) - Logs request and response pairs under a shared correlation ID.
- [laravel-log-to-db](https://github.com/danielme85/laravel-log-to-db) - Monolog channel that writes log events to SQL or MongoDB instead of files.
- [laravel-tail](https://github.com/spatie/laravel-tail) - Artisan command to tail application logs, including over SSH.
- [laravel-log-enhancer](https://github.com/freshbitsweb/laravel-log-enhancer) - Attaches request, user, and environment context to every log line.
- [laravel-log-alarm](https://github.com/saasscaleup/laravel-log-alarm) - Watches log output and alerts on error patterns and thresholds.

## Log viewers

- [log-viewer](https://github.com/opcodesio/log-viewer) - The most complete of the bunch: fast, searchable, handles large and rotated files, supports Horizon and daily channels.
- [laravel-log-viewer](https://github.com/rap2hpoutre/laravel-log-viewer) - Single-route, zero-config viewer. Small and dependable.
- [LogViewer](https://github.com/ARCANEDEV/LogViewer) - Long-standing viewer with per-level stats and its own dashboard.
- [Laravel-Log-Reader](https://github.com/JackieDo/Laravel-Log-Reader) - Reader and management tool with filtering and deletion.

## Metrics

- [laravel-prometheus](https://github.com/spatie/laravel-prometheus) - Exports application metrics to Prometheus with a fluent registration API.
- [prometheus_client_php](https://github.com/PromPHP/prometheus_client_php) - The underlying instrumentation library, with Redis, APCu, and in-memory storage adapters.
- [laravel-horizon-prometheus-exporter](https://github.com/LKaemmerling/laravel-horizon-prometheus-exporter) - Exposes Horizon workload, wait times, and process counts as Prometheus metrics.
- [httptheus](https://github.com/boring-o11y/httptheus) - Prometheus exporter for outgoing Guzzle and Laravel HTTP client calls.
- [Grafana dashboard for Horizon](https://grafana.com/grafana/dashboards/11034-laravel-horizon/) - Ready-made Grafana dashboard for the exporter above.

## Tracing

- [opentelemetry-php](https://github.com/open-telemetry/opentelemetry-php) - The official OpenTelemetry SDK for PHP.
- [opentelemetry-php-instrumentation](https://github.com/open-telemetry/opentelemetry-php-instrumentation) - Extension enabling automatic instrumentation without touching application code.
- [opentelemetry-php-contrib](https://github.com/open-telemetry/opentelemetry-php-contrib) - Auto-instrumentation for Laravel, Guzzle, PDO, Redis, and more.
- [laravel-opentelemetry](https://github.com/keepsuit/laravel-opentelemetry) - Opinionated Laravel integration: traces requests, queries, queue jobs, HTTP client calls, and console commands out of the box.
- [horizon-telemetry](https://github.com/worksome/horizon-telemetry) - OpenTelemetry instrumentation for Horizon and queue workers.
- [laraotel](https://github.com/Mahmoud-Italy/laraotel-opentelemetry-laravel) - Lightweight OpenTelemetry wiring for Laravel apps.
- [xray-laravel](https://github.com/Napp/xray-laravel) - AWS X-Ray tracing, useful on Vapor and other AWS deployments.
- [zipkin-php](https://github.com/openzipkin/zipkin-php) - Zipkin instrumentation library for PHP.

## Profiling

- [php-spx](https://github.com/NoiseByNorthwest/php-spx) - Sampling and tracing profiler with a built-in web UI. The easiest serious profiler to set up.
- [XHGui](https://github.com/perftools/xhgui) - Web interface that stores and compares XHProf profiles over time.
- [laravel-xhprof](https://github.com/laracraft-tech/laravel-xhprof) - Drop-in XHProf setup for Laravel requests and commands.
- [xhprof-buggregator-laravel](https://github.com/maantje/xhprof-buggregator-laravel) - Sends XHProf profiles from Laravel to Buggregator.

## Local debugging

- [Laravel Debugbar](https://github.com/fruitcake/laravel-debugbar) - The default answer for local request, query, and timeline inspection.
- [Clockwork](https://github.com/itsgoingd/clockwork) - Browser extension and web UI showing requests, queries, jobs, commands, and tests. Strong CLI and API coverage.
- [Buggregator](https://github.com/buggregator/server) - Single-binary debug server that catches var-dumps, Sentry-format exceptions, SMTP mail, and XHProf profiles.
- [LaraDumps](https://github.com/laradumps/laradumps) - Desktop app for dumps, queries, and job payloads, with per-screen organisation.
- [Ray](https://github.com/spatie/ray) - Commercial desktop debug app with a [Laravel package](https://github.com/spatie/laravel-ray) for queries, jobs, events, and mail.
- [New Debug Bar](https://github.com/newdebugbar/newdebugbar) - Recent rewrite of the debug bar idea, built to be readable by both humans and AI agents.
- [laravel-telescope-toolbar](https://github.com/fruitcake/laravel-telescope-toolbar) - Symfony-style toolbar rendered on top of Telescope data.
- [filament-debugger](https://github.com/stephenjude/filament-debugger) - Mounts Telescope, Horizon, and Pulse inside a Filament panel with policy-based access.
- [trace-replay](https://github.com/iazaran/trace-replay) - Records process traces and replays them deterministically for debugging.

## Queues and background jobs

Horizon-specific packages live in [awesome-horizon](https://github.com/boring-o11y/awesome-horizon). The entries here work with any queue driver.

- [Laravel Queue Monitor](https://github.com/romanzipp/Laravel-Queue-Monitor) - Database-backed job monitoring with progress, timing, and failure history.
- [laravel-queue-insights](https://github.com/SanderMuller/laravel-queue-insights) - Self-hosted, driver-agnostic per-class throughput, duration, and failure metrics.
- [Vantage](https://github.com/storviaio/vantage) - Queue dashboard covering database, Redis, SQS, and Beanstalkd, with a failed-job view and retries.
- [laravel-failed-job-monitor](https://github.com/spatie/laravel-failed-job-monitor) - Sends a notification whenever a queued job fails.
- [filament-jobs-monitor](https://github.com/ultraviolettes/filament-jobs-monitor) - Queue monitoring as a Filament resource.
- [Moox Jobs](https://github.com/mooxphp/jobs) - Filament plugin for queues, failed jobs, and batches.
- [Deck](https://github.com/getdeckapp/deck) - Job-class observability and safe cancellation for running jobs.
- [Skyline](https://boring-observability.dev/skyline) - Commercial Horizon drop-in with per-job history, arguments, and operational controls.

## Scheduled tasks

- [laravel-schedule-monitor](https://github.com/spatie/laravel-schedule-monitor) - Records every scheduled task start, finish, failure, and skip, and pings Oh Dear when configured.
- [Watchtower](https://github.com/Devifyo/watchtower) - Production-safe dashboard for crons, queues, and errors that also lets you act on them.
- [laravel-heartbeat](https://github.com/eXolnet/laravel-heartbeat) - Scheduled job that pings an external dead-man's-switch service.
- [healthchecks.io](https://healthchecks.io) - Cron and heartbeat monitoring with a generous free tier and a self-hosted option.

## Health checks

- [laravel-health](https://github.com/spatie/laravel-health) - The standard health-check package: database, cache, queue, disk, scheduler, and Horizon checks with JSON and HTML endpoints.
- [cpu-load-health-check](https://github.com/spatie/cpu-load-health-check) - Adds a CPU load check to the above.
- [filament-spatie-laravel-health](https://github.com/shuvroroy/filament-spatie-laravel-health) - Renders those health checks inside Filament.
- [laravel-health-check](https://github.com/ans-group/laravel-health-check) - Independent health-check package for Laravel and Lumen.
- [servermonitor](https://github.com/sarfraznawaz2005/servermonitor) - Periodic checks of server and application prerequisites.

## Uptime monitoring

- [Uptime Kuma](https://github.com/louislam/uptime-kuma) - The default self-hosted uptime monitor: HTTP, TCP, DNS, push, and status pages.
- [laravel-uptime-monitor](https://github.com/spatie/laravel-uptime-monitor) - Uptime and SSL certificate monitoring inside your own Laravel app.
- [server-monitor-app](https://github.com/spatie/server-monitor-app) - Standalone PHP app that runs health checks against your servers over SSH.
- [Uptime Kita](https://github.com/syofyanzuhad/uptime-kita) - Self-hosted uptime monitoring built with Laravel.
- [uptime-monitor](https://github.com/nafiesl/uptime-monitor) - Small self-hosted web monitoring tool built on Laravel.

## Database and queries

- [laravel-query-detector](https://github.com/beyondcode/laravel-query-detector) - Catches N+1 queries during development and reports them in the browser or logs.
- [laravel-slower](https://github.com/halilcosdu/laravel-slower) - Records slow queries and suggests indexes, with a built-in dashboard.
- [laravel-soar](https://github.com/guanguans/laravel-soar) - Runs SOAR against your queries for optimisation and rewrite suggestions.
- [laravel-db-profiler](https://github.com/dmitry-ivanov/laravel-db-profiler) - Query profiler for both web and console runs.
- [laravel-showsql](https://github.com/dietercoopman/laravel-showsql) - Sends the SQL for a specific block of code to Telescope, Ray, or the log.
- [phpunit-query-count-assertions](https://github.com/mattiasgeniar/phpunit-query-count-assertions) - Asserts query counts in PHPUnit and Pest, so N+1 regressions fail the build.
- [slow-query-notifier](https://github.com/thomasjohnkane/slow-query-notifier) - Notifies you when a query crosses a duration threshold.

## Audit and activity logs

- [laravel-activitylog](https://github.com/spatie/laravel-activitylog) - Logs model changes and custom activity with causer and subject attribution.
- [laravel-auditing](https://github.com/owen-it/laravel-auditing) - Per-model change history with configurable drivers and resolvers.
- [Chronicle](https://github.com/laravel-chronicle/core) - Append-only, verifiable audit trails for compliance use cases.
- [laravel-audit-log](https://github.com/iamfarhad/laravel-audit-log) - Entity-level auditing with a separate table per model.
- [yammi-audit-log](https://github.com/RomaLytar/yammi-audit-log) - Change history that attributes actions to users, jobs, commands, or the scheduler.
- [laravel-logger](https://github.com/jeremykenedy/laravel-logger) - Out-of-the-box user activity logging with a bundled UI.
- [laravel-user-monitoring](https://github.com/binafy/laravel-user-monitoring) - Tracks logins, page visits, and model interactions with a dashboard.
- [activitylog for Filament](https://github.com/rmsramos/activitylog) - Spatie activity logs as a Filament resource.
- [filament-activity-log](https://github.com/pxlrbt/filament-activity-log) - Alternative Filament integration for activity logs.
- [laravel-activitylog-ui](https://github.com/MuhammadSadeeq/laravel-activitylog-ui) - Standalone UI for Spatie activity logs with filtering and analytics.

## Pulse cards and Telescope watchers

- [pulse-validation-errors](https://github.com/timacdonald/pulse-validation-errors) - Surfaces the validation errors your users hit most.
- [pulse-outdated](https://github.com/aarondfrancis/pulse-outdated) - Shows outdated Composer dependencies on the Pulse dashboard.
- [laravel-pulse-schedule](https://github.com/hosmelq/laravel-pulse-schedule) - Lists scheduled tasks and their next run times.
- [pulse-users](https://github.com/abbasudo/pulse-users) - Usage distribution card.
- [telescope-guzzle-watcher](https://github.com/huzaifaarain/telescope-guzzle-watcher) - Captures outgoing Guzzle requests in Telescope.

## Self-hosted backends

- [SigNoz](https://github.com/SigNoz/signoz) - OpenTelemetry-native platform for traces, metrics, and logs in one place.
- [OpenObserve](https://github.com/openobserve/openobserve) - Logs, metrics, traces, RUM, and session replay with low storage overhead.
- [Grafana Loki](https://github.com/grafana/loki) - Log aggregation designed to pair with Prometheus and Grafana.
- [Vector](https://github.com/vectordotdev/vector) - High-performance pipeline for collecting, transforming, and routing observability data.
- [GlitchTip](https://glitchtip.com) - Open source error tracking that speaks the Sentry protocol, so any Sentry SDK works against it.

## Hosted services

- [Nightwatch](https://nightwatch.laravel.com) - Laravel's own monitoring product: requests, queries, jobs, exceptions, and scheduled tasks.
- [Sentry](https://sentry.io/for/laravel/) - Errors plus performance tracing; the most common choice in Laravel apps.
- [Flare](https://flareapp.io) - Error tracking from the Spatie team, tightly integrated with Ignition.
- [Bugsnag](https://www.bugsnag.com) - Error monitoring with release-health tracking.
- [Honeybadger](https://www.honeybadger.io/for/laravel/) - Errors, uptime, and cron monitoring in one subscription.
- [Rollbar](https://rollbar.com) - Error tracking with grouping and deploy tracking.
- [Inspector](https://inspector.dev) - Execution monitoring aimed specifically at Laravel and Symfony.
- [Blackfire](https://blackfire.io) - Profiler with performance assertions you can run in CI.
- [Tideways](https://tideways.com) - PHP-focused APM combining monitoring with a callgraph profiler.
- [Scout APM](https://scoutapm.com) - APM that ties slow transactions back to the responsible line of code.
- [New Relic](https://newrelic.com) - Full-stack APM with a mature PHP agent.
- [Datadog](https://www.datadoghq.com) - Metrics, logs, and traces, with the [dd-trace-php](https://github.com/DataDog/dd-trace-php) agent.
- [Elastic Observability](https://www.elastic.co/observability) - The Elastic stack, with an [official PHP APM agent](https://github.com/elastic/apm-agent-php).
- [Oh Dear](https://ohdear.app) - Uptime, broken links, certificates, and scheduled-task monitoring, with first-class Laravel packages.
- [Better Stack](https://betterstack.com) - Uptime monitoring, incident management, and log management.

## Reading

- [Laravel logging documentation](https://laravel.com/docs/12.x/logging) - Channels, stacks, and context. Start here before adding anything else.
- [Laravel Telescope documentation](https://laravel.com/docs/12.x/telescope) - Including the production gating and pruning notes people skip.
- [Laravel Pulse documentation](https://laravel.com/docs/12.x/pulse) - Sampling, custom cards, and recorders.
- [OpenTelemetry PHP documentation](https://opentelemetry.io/docs/languages/php/) - Getting the SDK and auto-instrumentation extension working.
- [awesome-horizon](https://github.com/boring-o11y/awesome-horizon) - Sibling list covering Horizon dashboards, alternatives, and queue drivers.

## Contributing

Pull requests are welcome. One entry per line, alphabetised within its section where possible, with a short description of what the tool actually does. Projects should be maintained and usable; commercial products belong in [Hosted services](#hosted-services) and are marked as such.
