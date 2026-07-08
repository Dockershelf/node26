# node26

Debian packaging for Node.js 26: monolithic `nodejs-26` packages used by the [Dockershelf node-pipeline](../node-pipeline).

## Supported Debian suites

- `trixie`
- `unstable`

Packaging trees live under `debiandirs/<suite>/`. Changelog tracks:

- **mainline** — `changelogs/mainline/<suite>`

## Build (from workspace)

Clone or seed this repo as a sibling of `node-pipeline/`, then from `node-pipeline/`:

```bash
make materialize NODE=26 DIST=trixie
make build NODE=26
```

See the [operations manual](https://github.com/Dockershelf/node-pipeline/blob/main/docs/operations.md) for new majors, version bumps, and new suites.

## Layout

| Path | Purpose |
|------|---------|
| `node/` | Upstream Node.js git submodule (`v26.x` branch) |
| `patches/` | Quilt series (usually empty for monolithic builds) |
| `debiandirs/` | Per-suite Debian packaging (`trixie`, `unstable`) |
| `changelogs/` | `mainline` dch history per suite |
