.. _config_http_conn_man_header_sanitizing:

HTTP header sanitizing
======================

For security reasons, Envoy will "sanitize" various incoming HTTP headers depending on whether the
request is an internal or external request. The sanitizing action depends on the header and may
result in addition, removal, or modification. Ultimately, whether the request is considered internal
or external is governed by the :ref:`x-forwaded-for <config_http_conn_man_headers_x-forwarded-for>`
header (please read the linked section carefully as how Envoy populates the header is complex and
depends on the :ref:`use_remote_address <config_http_conn_man_use_remote_address>` setting).

Envoy will potentially sanitize the following headers:

* x-forwarded-client-cert
* x-forwarded-for
* x-forwarded-proto
* x-request-id
* x-envoy-internal
* x-envoy-force-trace
* x-envoy-external-address
* x-envoy-downstream-service-node
* x-envoy-downstream-service-cluster
* x-envoy-retry-on
* x-envoy-grpc-retry-on FIXFIX code
* x-envoy-upstream-alt-stat-name
* x-envoy-upstream-rq-timeout-ms
* x-envoy-upstream-rq-per-try-timeout-ms
* x-envoy-upstream-rq-timeout-alt-response
* x-envoy-expected-rq-timeout-ms
