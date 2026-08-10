# Releasing

1. Update the version and changelog together.
2. Run `npm ci`, `npm run check` and `npm run pack:dry-run`.
3. Confirm the package contains no credentials, local configuration or fixtures.
4. Open and merge a reviewed release pull request.
5. Create a GitHub release whose tag matches `v<package version>`.
6. The protected npm environment publishes through trusted provenance.

The release owner verifies the package from a clean consumer project before it
is announced.
