---
title: Oryx service layer
description: Oryx service layer abstracts system functionality using DI
template: concept-topic-template
last_updated: Apr 13, 2023
---

{% info_block warningBox %}

Oryx is currently running under an *Early Access Release*. Early Access Releases are subject to specific legal terms, they are unsupported and do not provide production-ready SLAs. They can also be deprecated without a General Availability Release. Nevertheless, we welcome feedback from early adopters on these cutting-edge, exploratory features.

{% endinfo_block %}

The service layer in Oryx serves as the foundation for the business logic. The main objective of the service layer is to abstract all the system functionality, including querying backend services, data caching and reloading, state management, and reactivity. Dependency injection (DI) plays a crucial role in achieving this objective.

Furthermore, DI is utilized by many higher-level elements and concepts in Oryx, ranging from adapters and normalizers to HTTP interceptors, authentication, product loading, cart management, and the checkout process.

## Dependency injection npm package

The `@spryker-oryx/di` package provides DI to Oryx applications and other packages. It can even be used outside the Oryx framework. It includes a variety of useful utilities to streamline working with DI, such as the following:

- TypeScript model definitions. For example, Providers.
- `Injector`: the implementation of a DI container in TypeScript.
- Functions used to set up and manage injectors. For example, `createInjector()` or `getInjector()`.
- Utilities that can be used to resolve dependencies: `inject` and `resolve`.

In a typical Oryx application, the application orchestrator automatically handles much of the work related to setting up the DI container. Nevertheless, the `@spryker-oryx/di` library provides a set of tools that can be used to further customize and fine-tune DI.

## Next steps

[Using services](/docs/scos/dev/front-end-development/{{page.version}}/oryx/dependency-injection/dependency-injection-using-services.html)