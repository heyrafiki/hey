# hey

The command line for the Heyrafiki API.

## What this tool is for

Use `hey` to test a Sandbox integration from the command line. It checks local
configuration and makes authenticated read requests, so integration teams can
verify their setup before they build it into an application.

`hey` gives integration teams a fast, scriptable path into the same REST API
used by the Platform and SDKs. It checks local configuration and runs
authenticated read requests against Sandbox projects.

## Build and run

Requires Node.js 22 or newer.

```bash
git clone https://github.com/heyrafiki/hey.git
cd hey
npm ci
npm run check
node dist/index.js doctor
```

Set `HEYRAFIKI_API_KEY`, then inspect a resource:

```bash
node dist/index.js get /practitioners?limit=5
```

The command prints the API request identifier and structured errors, giving CI
and operational tools the information needed to troubleshoot a request. Write
operations remain in the REST API and SDKs, where applications provide the
required intent and idempotency key.

## Package contents

```bash
npm run pack:dry-run
```

The package contains the compiled command, README, license and package
metadata. Keys and local configuration are never included.

## Security

Keep API keys in an environment secret store and use a Sandbox project for
integration tests. Report vulnerabilities through the
[Heyrafiki security policy](https://github.com/heyrafiki/.github/blob/main/SECURITY.md).

## License

Licensed under the [Apache License 2.0](./LICENSE).
