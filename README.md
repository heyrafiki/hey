# hey

The command line for the Heyrafiki API.

## Where this fits

The CLI is a diagnostic and Sandbox-read surface for Heyrafiki's versioned
REST contract. It gives integration teams a scriptable way to verify local
configuration and governed reads without moving authorization or domain
decisions into the command line.

`hey` gives integration teams a fast, scriptable path into the same governed
REST contract used by the Platform and SDKs. It checks local configuration and
runs authenticated read requests against Sandbox projects.

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

The command preserves the API request identifier and typed error envelope so
CI and operator workflows can retain the same evidence as direct REST clients.
Write operations remain caller-controlled through the REST API and typed SDKs.

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
