# The Twelve-Factor App

## Codebase

> One codebase tracked in revision control, many deploys

* Always use a VCS
* `x` codebases = `x` apps
* "Multiple apps sharing the same code is a violation of twelve-factor." Create modules and use those instead.
* A deploy is a running instance of the app.
* "There is only one codebase per app, but there will be many deploys of the app."

## Dependencies

> Explicitly declare and isolate dependencies

* Never rely on implicit existence of system-wide packages or system tools. If necessary, vendor the tool in question into the app.
* Explicitly declare dependencies via a dependency declaration manifest.
* Use a dependency isolation tool.

## Config

> Store config in the environment
>
> An app’s config is everything that is likely to vary between deploys \(staging, production, developer environments, etc\).

* Twelve-factor requires strict separation of config from code.
* The twelve-factor app stores config in environment variables.
* Grouping config into named groups is not recommended since it does not scale well.

> In a twelve-factor app, env vars are granular controls, each fully orthogonal to other env vars. They are never grouped together as “environments”, but instead are independently managed for each deploy. This is a model that scales up smoothly \[…\].

## Backing services

> Treat backing services as attached resources
>
> A backing service is any service the app consumes over the network as part of its normal operation.

Examples:

* Databases
* SMTP services
* Logging services
* Caching systems
* API-accessible consumer services

Keep in mind that:

* The code for a twelve-factor app makes no distinction between local and third party services.
* Each backing services is a resource. These attached services are loosely coupled with the deploy they are associated with.
* It should be possible to attach and detach resources from deploys at will.

## Build, release, run

> Strictly separate build and run stages

## Processes

> Execute the app as one or more stateless processes

## Port binding

> Export services via port binding

## Concurrency

> Scale out via the process model

## Disposability

> Maximize robustness with fast startup and graceful shutdown

## Dev/prod parity

> Keep development, staging, and production as similar as possible

## Logs

> Treat logs as event streams

## Admin processes

> Run admin/management tasks as one-off processes

