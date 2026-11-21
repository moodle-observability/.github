# Welcome to **Moodle Observability**!

This organization brings together open-source **Moodle** plugins and tools for **observability**: error tracking, performance monitoring, logs, metrics and tracing, so that Moodle administrators and developers can see what is happening in their platform and fix problems faster.

All plugins target **Moodle 5.3 and later** and are released under the **GPL-3.0** license.

## Plugins

| Plugin | Description | Status |
| :--- | :--- | :--- |
| [moodle-tool_sentry](https://github.com/moodle-observability/moodle-tool_sentry) | Sends Moodle errors and performance data to [Sentry](https://sentry.io) (self-hosted or cloud). Available in the [Moodle Plugins directory](https://moodle.org/plugins/tool_sentry). | ✅ Stable |
| [moodle-tool_prometheus](https://github.com/moodle-observability/moodle-tool_prometheus) | Exposes platform metrics (active users, task queues, quiz attempts, cache, disk) in OpenMetrics format for [Prometheus](https://prometheus.io). | 🛠️ Planned (MVP) |
| [moodle-tool_taskmonitor](https://github.com/moodle-observability/moodle-tool_taskmonitor) | Monitors cron and scheduled/adhoc tasks, records durations and failures, and alerts administrators. | 🛠️ Planned (MVP) |
| [moodle-tool_healthcheck](https://github.com/moodle-observability/moodle-tool_healthcheck) | Liveness and readiness endpoints for Kubernetes probes and load balancers. | 🛠️ Planned (MVP) |
| [moodle-tool_otel](https://github.com/moodle-observability/moodle-tool_otel) | Distributed tracing with [OpenTelemetry](https://opentelemetry.io), exported via OTLP. | 🔬 Research (backlog) |

## Roadmap

1. **v0.1.0 – MVP** for `tool_prometheus`, `tool_taskmonitor` and `tool_healthcheck`: plugin scaffold, CI with `moodle-plugin-ci`, core features, PHPUnit tests and documentation.
2. **Alignment of `tool_sentry`** with the organization CI standard.
3. **`tool_otel` spike**: evaluate the OpenTelemetry PHP SDK with the Moodle bootstrap before committing to an MVP.
4. **Publication** of each plugin in the [Moodle Plugins directory](https://moodle.org/plugins) once stable.

Track progress in each repository's issues and in the `v0.1.0 – MVP` milestone.

## Contributing

Contributions are welcome! Read the [contributing guide](https://github.com/moodle-observability/.github/blob/main/CONTRIBUTING.md) before opening a pull request. Issues labeled [`good first issue`](https://github.com/search?q=org%3Amoodle-observability+label%3A%22good+first+issue%22+state%3Aopen&type=issues) are a good starting point.

Check out the organization's portal website:

> 🌐 [Organization Website](https://moodle-observability.github.io/)
