# AI Drone Map

**Every machine, one command.**

Open source drone mapping built for the way data is processed now: one job spread across every CPU and GPU you can reach, paid only while it runs, and simple enough to deploy in minutes.

> **AIDM 0.1.0 is out.** Based on the ODX 3.8.4 engine, with Linux images for x86-64 and arm64. Every image processes a real survey before it is published, and the GPU image is tested on a real NVIDIA GPU and also runs without one. Processing is unchanged; the performance and distributed work starts from here. See the [roadmap](#roadmap).

## Try it

Process a folder of drone images (put them in `/path/to/datasets/project/images`):

```
docker run -ti --rm -v /path/to/datasets:/datasets ghcr.io/aidronemap/aidm:0.1.0 --project-path /datasets project
```

Or run the task API and open http://localhost:3000 in a browser:

```
docker run -p 3000:3000 ghcr.io/aidronemap/aidm-api:2.5.0
```

The API is compatible with NodeODX, so WebODM and other existing clients can use it as a processing node.

## Why AIDroneMap

Drones capture more images, at higher resolution, than ever before. Turning them into orthophotos, elevation models, point clouds and 3D models takes serious computing power, and that power costs money. Today the usual choice is a machine big enough for your largest job that sits idle most of the time, or a long wait.

AIDroneMap starts from a different idea: compute you rent by the second, or already own, joined into one pool for as long as a job needs it and released when the job ends.

## Repositories

| Repository | What it is | Status |
| --- | --- | --- |
| [aidm](https://github.com/AIDroneMap/aidm) | The photogrammetry engine, forked from [ODX](https://github.com/WebODM/ODX) | 0.1.0 released |
| [aidm-api](https://github.com/AIDroneMap/aidm-api) | The task API, forked from [NodeODX](https://github.com/WebODM/NodeODX) and compatible with it | 2.5.0 released |
| [aidm-ui](https://github.com/AIDroneMap/aidm-ui) | An open web interface for a single operator, written from scratch | Planning |
| Cloud layer | A scheduler with connectors that run jobs on Modal, other GPU clouds billed by the second, your own machines or a cluster | Coming next |

Each piece works on its own and speaks one open, NodeODX-compatible task API.

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
| Foundation | Oct to Nov 2026 | Engine fork, Linux images for x86-64 and arm64, smoke tests (done); weekly sync with ODX |
| Measure and compute | Dec 2026 to Jan 2027 | Per-stage profiling, baseline numbers against ODX, first cloud connector |
| Speed and pipelines | Feb to Mar 2027 | First speedups, pipeline files, CLI and MCP server, a mixed CPU and GPU pool |
| AI stages and 1.0 | Apr to Jun 2027 | Dataset pre-flight check, AI masking, documentation, public 1.0, open UI preview |

## Get involved

- Questions and ideas: the Discussions tab of each repository.
- Bugs: open an issue in the repository concerned.
- Code: read the [contributing guide](https://github.com/AIDroneMap/.github/blob/main/CONTRIBUTING.md). Every commit needs a DCO sign-off.
- Security problems: use **Report a vulnerability** in the repository's Security tab, not a public issue.

## Credits

AIDM builds on [ODX](https://github.com/WebODM/ODX) and the [WebODM](https://github.com/WebODM) project, on [OpenDroneMap](https://github.com/OpenDroneMap) where it all began, and on OpenSfM, OpenMVS, PDAL, GDAL and Entwine. Thank you to everyone who built them.

AIDroneMap is an independent project. It is not affiliated with or endorsed by WebODM or OpenDroneMap.

## Links

- Website: [aidronemap.org](https://aidronemap.org) (coming soon)
- Developer documentation: [aidronemap.dev](https://aidronemap.dev) (coming soon)

## Maintainer and sponsor

AIDroneMap is maintained by [Dimitri Albino](https://github.com/DimitriAlbino) and sponsored by [ITALDRONI](https://italdroni.it). Sponsorship never buys features: everything in the engine stays open.
