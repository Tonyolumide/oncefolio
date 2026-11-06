# Oncefolio

Recoverable agent purchases for a structured-data validation report on NEAR: pay, lose the response, restart, and recover the same purchase and result.

## Reviewed source release

The complete reviewed MIT source snapshot is available as [oncefolio-source.tar.gz](oncefolio-source.tar.gz). It contains 73 source and documentation files.

- SHA-256: `7917b19a4ea81ab10e6ff672163b6a958634b9b449da08ab56ad42651ca95a0e`
- License: [MIT](LICENSE)
- Extract with: `tar -xzf oncefolio-source.tar.gz`

This is the exact source archive reviewed for publication. It excludes runtime keys, databases, generated build outputs, and testnet validation data.

## Product scope

Oncefolio is an API/CLI MVP. It stores raw requests and reports offchain, accepts native NEAR payments on the provider account, and lets the buyer recover a purchase after a lost response. It has no production web UI and does not promise automatic refunds when report delivery fails.

## Testnet run

The reviewed contract is deployed to `oncefolio-provider-993067a8.testnet`. On 2026-11-06, the purchase/recovery flow was validated with `oncefolio-buyer-993067a8.testnet`: one 0.1 NEAR testnet payment succeeded, then duplicate and conflicting deposits were rejected and refunded. Total attached deposits were capped at 0.3 test NEAR. Mainnet was not used.

The testnet validation evidence is local to the build workspace and is not included in the source archive.

## Local demo

After extracting the archive, run `./oncefolio setup` on macOS ARM64 with Node 24 and pnpm 11.25.0, then:

```sh
./oncefolio demo
./oncefolio test
```

The archive includes the full README, architecture notes, tests, and TESTNET_RUNBOOK.md.
