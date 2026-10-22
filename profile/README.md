# AIDroneMap

**Every machine, one command.**

Open source drone mapping built for the way data is processed now: one job spread across every CPU and GPU you can reach, paid only while it runs, and simple enough to deploy in minutes.

> AIDroneMap is just getting started and nothing is released yet. This page describes what we are building. The roadmap below shows where we are.

## Why AIDroneMap

Drones capture more images, at higher resolution, than ever before. Turning them into orthophotos, elevation models, point clouds and 3D models takes serious computing power, and that power costs money. Today the usual choice is a machine big enough for your largest job that sits idle most of the time, or a long wait.

AIDroneMap starts from a different idea: compute you rent by the second, or already own, joined into one pool for as long as a job needs it and released when the job ends.

## What we are building

| Project | What it is |
| --- | --- |
| **AIDM** | The photogrammetry engine, forked from [ODX](https://github.com/WebODM/ODX). Distributed, GPU-aware, and released every week. |
| **Cloud layer** | A scheduler with connectors that run AIDM on Modal, other GPU clouds billed by the second, your own machines or a cluster. Nothing runs between jobs. |
| **Open UI** | A web interface for a single operator, with a desktop app for Windows, macOS and Linux. |
| **Tools** | A command-line tool, an SDK and an MCP server, so scripts and AI agents can run and check jobs. |

Each piece works on its own and speaks one open, NodeODX-compatible task API. Existing clients such as WebODM can switch to AIDM by changing one URL, and the output files stay the same.

## Principles

- **Simple to deploy, simple to use.** One engine image, one command to run it, one URL to point a client at.
- **Keep your tools.** A compatible API and familiar outputs, so nothing you use today has to change.
- **Pay only while it runs.** No machine left idle, and no single cloud provider required.
- **Measured in public.** Every speed or accuracy claim comes with a benchmark against ODX, with method and datasets published.
- **Open and independent.** The engine is licensed AGPL-3.0, and there are no paid features in it.

## Roadmap

Target dates, subject to change as the work progresses.

| Phase | Target | Focus |
| --- | --- | --- |
| Foundation | Nov 2026 | Engine fork, Linux images, test datasets, weekly sync with ODX |
| Measure and compute | Dec 2026 to Jan 2027 | Per-stage profiling, baseline numbers against ODX, first cloud connector |
| Speed and pipelines | Feb to Mar 2027 | First speedups, pipeline files, CLI and MCP server, a mixed CPU and GPU pool |
| AI stages and 1.0 | Apr to Jun 2027 | Dataset pre-flight check, AI masking, documentation, public 1.0, open UI preview |

## Credits

AIDM builds on [ODX](https://github.com/WebODM/ODX) and the [WebODM](https://github.com/WebODM) project, on [OpenDroneMap](https://github.com/OpenDroneMap) where it all began, and on OpenSfM, OpenMVS, PDAL, GDAL and Entwine. Thank you to everyone who built them.

AIDroneMap is an independent project. It is not affiliated with or endorsed by WebODM or OpenDroneMap.

## Links

- Website: [aidronemap.org](https://aidronemap.org) (coming soon)
- Developer documentation: [aidronemap.dev](https://aidronemap.dev) (coming soon)

## Maintainer and sponsor

AIDroneMap is maintained by [Dimitri Albino](https://github.com/DimitriAlbino) and sponsored by [ITALDRONI](https://italdroni.it). Sponsorship never buys features: everything in the engine stays open.
