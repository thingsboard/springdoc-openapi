# springdoc-openapi

[springdoc-openapi](https://springdoc.org/) automates the generation of API
documentation for Spring Boot projects: it examines the application at runtime
to infer the API semantics from the Spring configuration, class structure and
annotations, and produces an OpenAPI 3 description served alongside a Swagger
UI front end.

This repository is the ThingsBoard-maintained fork of
[springdoc/springdoc-openapi](https://github.com/springdoc/springdoc-openapi),
published as `org.thingsboard` artifacts at `TB`-suffixed versions and consumed
by the ThingsBoard platform to serve its interactive API documentation. The
fork differs from the upstream 2.8.8 release as follows:

+ A new ThingsBoard-authored `springdoc-swagger-ui` module packages the
  [ThingsBoard fork of Swagger UI](https://github.com/thingsboard/swagger-ui)
  as a webjar: it downloads the GitHub archive of the `TB`-suffixed Swagger UI
  tag and places its `dist` assets under
  `META-INF/resources/webjars/swagger-ui/`, preserving the Swagger UI
  attribution notice in the jar.
+ `springdoc-openapi-starter-webmvc-ui` depends on that webjar instead of
  `org.webjars:swagger-ui`, and its automatic module name is changed to
  `org.thingsboard.openapi.ui`.
+ `PropertyResolverUtils` logs failures to resolve embedded values in
  documentation properties at trace instead of warn level. The modified file
  carries its own modification notice.
+ The artifacts are published under the `org.thingsboard` group id at the
  fork's `TB`-suffixed version, with the pom metadata updated accordingly,
  Spring Boot pinned to 3.4.8, and the licence text shipped in the main,
  sources and javadoc jars.

The list above serves as the modification notice required by section 4(b) of
the Apache License 2.0 for the changed files that cannot reasonably carry an
in-file notice, such as the poms and test fixtures whose only change is the
version string.

## License

springdoc-openapi is licensed under the Apache License, Version 2.0. See
[LICENSE](LICENSE) for the full license text.
