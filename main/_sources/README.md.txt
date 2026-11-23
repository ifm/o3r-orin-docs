# README

This project contains documentation for the O3R platform. It is used along with other projects to build to ifm3d.com site.
> Note: it does not cover any of the supported software stacks (ifm3d, ROS, etc).

The documentation is intended to be viewed on [ifm3d.com](https://ifm3d.com/).

## Publication scope

PDS is not supported in the initial OVP93x firmware releases.
Keep [the PDS sources](PDS/) and the generated `generated_docs/pds*.md` files in Git, but do not publish them or link to them from customer pages.

The developer-portal Sphinx configuration excludes these paths beneath `ovp9xx_documentation/`, together with the unused PDS landing icon and contributor material.
Removing a toctree entry alone is not sufficient.
For another assembled source layout, apply the same exclusions relative to that source root.
Do not copy the excluded paths into static assets, source archives, or downloads separately from the Sphinx output.

Build into an empty output directory and replace the deployed OVP93x output so previously generated PDS pages, source copies, search entries, and images do not remain accessible.
The source and navigation can be restored after PDS support and its documentation have been confirmed.
Shared PLC protocol fields remain documented to preserve the wire layout; their presence does not establish PDS support.

## Generate reference tables

The [reference-table generator](.scripts/README.md) creates the Markdown tables used by the documentation from release-specific parameter schemas and diagnostic definitions.
Its contributor guide covers dependencies, input paths, diagnostics-only generation, preview output, and validation.
The [GitLab CI workflow](.scripts/README.md#gitlab-ci) tests the generator and creates downloadable diagnostic tables for a selected OVP93x `FIRMWARE_VERSION`, or for an explicitly selected `DIAGNOSTIC_VERSION`.
