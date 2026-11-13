# Venntier runtime third-party sources

## Why this repository exists

Venntier distributes application container images containing open-source runtime components. Recipients need usable access to the covered third-party source, licenses, and applicable build modifications corresponding to those components. This repository provides versioned source-release assets and provenance while we work toward authoritative supplier-hosted source access.

This repository contains **third-party sources only**. It does not publish Venntier proprietary application source and does not grant a license to the application. Each upstream component retains its own license; there is no blanket license overriding those terms. Authentic notices are retained in upstream archives and the materials directory. Venntier-authored explanatory text and manifests are provided under CC0-1.0: https://creativecommons.org/publicdomain/zero/1.0/ .

## Current release and its limits

Release `vt-analytics-runtime-20261113-820a45f7dd1a` is a **source-evidence prerelease**, covering the 20 pending packages in the assessed runtime image:

- Image config digest: `sha256:820a45f7dd1a96ad96a29f47602d83fc1ffad3107c50ca62f6f965d518fb37ee`
- Application build commit: `404d7b0ce3a491216f151431996bde1a9015eb25`
- Build/assessment: https://github.com/venntier/vt_analytics/actions/runs/43279258014 (may require repository access)

The config digest is the scanned local image identity, **not a registry manifest digest**. This release describes that built candidate, not a later branch tip or an asserted production release.

The upstream archives are pinned to the source revisions recorded in the supplier package SBOMs. GCC and glibc each serve multiple installed subpackages. `manifest.json` maps every package version/PURL to its source group and archive hash. `materials/` contains supplier package SPDX documents, authentic notices, available public recipes/patches, and retrieval evidence.

**These assets are not yet a declaration of complete corresponding-source compliance.** Original supplier recipes are inaccessible; available public recipes are corroboration, not proof of equivalence. Some configuration, patches or build inputs may still be missing. Publishing this prerelease does not turn the runtime license gate green. It also does not establish relinking/replacement conditions or recipient contract terms.

## Download and verify

1. Open the matching versioned GitHub release.
2. Download `manifest.json`, `SHA256SUMS`, `runtime-source-materials.tar.gz`, and the source-group archives for your packages.
3. Run `sha256sum --check SHA256SUMS` with all listed assets present.
4. Consult the package mapping, retained notices, and remaining-work fields before treating the materials as complete.

Archives are retained byte-for-byte as retrieved. Different mirrors can package the same revision differently; the manifest records the actual downloaded archive hashes. Source availability does not imply a byte-reproducible binary build.

## Closing gaps and moving to supplier hosting

We will seek complete public supplier references, original patches/configuration and build inputs. When coverage is verified, publish a new versioned release identifying the resolved gaps. Prefer Chainguard-hosted complete sources when available, but retain older releases for recipients of images that reference them. Do not silently replace existing release assets or redirect old versions to unrelated newer source.

For a missing source or access problem, open an issue here with the release tag, package version and image identity. Do not include credentials or proprietary application code.
