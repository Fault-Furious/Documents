# Telemetry for loading Main Page:

## Traces:
Traces: "What happened during this specific request?" (individual request lifecycle)
In context of telemetry, refers to a specific request, query or function 

Check this link for how OpenTelemetry traces look like
https://www.dash0.com/knowledge/opentelemetry-tracing

- Send HTTP get request to https://www.nordic_online_discussion_platform.com/
- response status
## Metrics:
Metrics: "What is happening across all requests?" (aggregated statistics)
Check this for metrics:
https://www.dash0.com/knowledge/opentelemetry-metrics


- update page views for main page (https://www.nordic_online_discussion_platform.com/)
- device type metrics
- May not be relevant yet, we might want to consider this later

## Logs:
Logs: "Why did this specific thing happen?" (detailed context and events)

In context of telemetry, the whole context of a specific event, in this case load main page. Often includes traces as context. (For example log in event could include both HTTP request and database query as context)

Check this for how OpenTelemetry logs look like:
https://www.dash0.com/knowledge/opentelemetry-logging-explained

Custom event for main page load (come up a name for the event), 
should include trace_id that links to the related HTTP request trace, user Agent, client IP, server IP and level/severity, URL
