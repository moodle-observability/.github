# Welcome to **Moodle Observability**!

This organization brings together open-source **Moodle** plugins and tools for **observability**: error tracking, performance monitoring, logs, metrics and tracing, so that Moodle administrators and developers can see what is happening in their platform and fix problems faster.

All plugins target **Moodle 5.3 and later** and are released under the **GPL-3.0** license.

## Plugins

| Plugin | Description | Status |
| :--- | :--- | :--- |
| [moodle-tool_sentry](https://github.com/moodle-observability/moodle-tool_sentry) | Sends Moodle errors and performance data to [Sentry](https://sentry.io) (self-hosted or cloud). Available in the [Moodle Plugins directory](https://moodle.org/plugins/tool_sentry). | ✅ Stable |
| [moodle-tool_prometheus](https://github.com/moodle-observability/moodle-tool_prometheus) | Exposes platform metrics (active users, sessions, task queues, quiz attempts, cache stores, disk) for [Prometheus](https://prometheus.io), with an extension point for other plugins. | 🛠️ 0.1.0 (alpha) |
| [moodle-tool_taskmonitor](https://github.com/moodle-observability/moodle-tool_taskmonitor) | Alerts when cron stops or tasks keep failing, with a task health report and an extension point for other alert channels. | 🛠️ 0.1.0 (alpha) |
| [moodle-tool_healthcheck](https://github.com/moodle-observability/moodle-tool_healthcheck) | Liveness and readiness endpoints for Kubernetes probes and load balancers, with checks contributed by other plugins. | 🛠️ 0.1.0 (alpha) |
| [moodle-tool_otel](https://github.com/moodle-observability/moodle-tool_otel) | Distributed tracing with [OpenTelemetry](https://opentelemetry.io): request, web service and task spans exported via OTLP. | 🛠️ 0.1.0 (alpha) |
| [moodle-tool_opensearch](https://github.com/moodle-observability/moodle-tool_opensearch) | [OpenSearch](https://opensearch.org) base for Moodle plugins: connection, queue, bulk shipping, data streams with retention and metrics. | 🛠️ 0.1.0 (alpha) |
| [moodle-logstore_opensearch](https://github.com/moodle-observability/moodle-logstore_opensearch) | Log store that writes Moodle events to OpenSearch: the same fields as the standard log, or xAPI statements, each in its own data stream. | 📐 Planning |

## Roadmap

1. **Done:** 0.1.0 (alpha) of `tool_prometheus`, `tool_taskmonitor`, `tool_healthcheck`, `tool_otel` and `tool_opensearch`, and alignment of `tool_sentry` with the organization CI standard.
2. **`logstore_opensearch`:** the log store in `standard` mode (same fields as Moodle) on top of `tool_opensearch` 0.1.0, and later in `xapi` mode.
3. **Core proposals** to unblock database query and outgoing HTTP spans in `tool_otel`.
4. **Publication** of each plugin in the [Moodle Plugins directory](https://moodle.org/plugins) once stable.

Track progress in the issues of each repository.

## Contributing

Contributions are welcome! Read the [contributing guide](https://github.com/moodle-observability/.github/blob/main/CONTRIBUTING.md) before opening a pull request. Issues labeled [`good first issue`](https://github.com/search?q=org%3Amoodle-observability+label%3A%22good+first+issue%22+state%3Aopen&type=issues) are a good starting point.

Check out the organization's portal website:

> 🌐 [Organization Website](https://moodle-observability.github.io/)
