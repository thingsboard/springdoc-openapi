# springdoc-openapi

springdoc-openapi generates OpenAPI 3 documentation for Spring Boot applications at runtime and serves it together with Swagger UI. This repository is a fork of [springdoc/springdoc-openapi](https://github.com/springdoc/springdoc-openapi) used by the ThingsBoard platform to serve its interactive API documentation.

Published as `org.thingsboard` artifacts at `TB`-suffixed versions.

## Differences from upstream

The fork differs from the upstream 3.1.1 release as follows:

- A new ThingsBoard-authored `springdoc-swagger-ui` module packages the [ThingsBoard fork of Swagger UI](https://github.com/thingsboard/swagger-ui) as a webjar. It downloads the GitHub archive of a `TB`-suffixed Swagger UI tag, places its `dist` assets under `META-INF/resources/webjars/swagger-ui/`, and copies the Swagger UI `NOTICE` into the jar.
- `springdoc-openapi-starter-webmvc-ui` and `springdoc-openapi-starter-webflux-ui` depend on that webjar instead of `org.webjars:swagger-ui`. Their test fixtures expect the `HttpLoginAuth` plugin and the ThingsBoard license header in the Swagger UI initializer.
- `PropertyResolverUtils` logs failures to resolve embedded values in documentation properties at trace instead of warn level.
- The artifacts are published under the `org.thingsboard` group id at the fork's `TB`-suffixed version to the ThingsBoard repository instead of Maven Central, with `org.thingsboard.openapi` automatic module names and pom metadata that names ThingsBoard and this repository.
- The sources and javadoc jars carry the license texts, as the main jars already did.

## Licensing

springdoc-openapi is licensed under the Apache License, Version 2.0. See [LICENSE](LICENSE) for the full license text.
