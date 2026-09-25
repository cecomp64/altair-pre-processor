> [!IMPORTANT]
> **This repository has moved.** The processing core (Altair) now lives in
> [`altair-observatory-system/processing`](https://github.com/cecomp64/altair-observatory-system/tree/main/processing),
> merged with its full history. This repository is archived and read-only; open issues and
> pull requests there.

# altair-pre-processor

Fully automated, event-triggered astrophotography pre-processing: raw frames from a night's
imaging session are calibrated and integrated headlessly with PixInsight WBPP into one master
per (telescope, camera, filter, target) per night, plus optional weighted multi-night masters
that reuse registration. Targets Windows + NINA: a processing PC collects frames from each
rig PC's NINA folder (configured per rig) onto a required NAS, which is the canonical raw
store that processing reads in place, and backs raw lights and outputs up to Amazon S3 as
the first pipeline step. Older raw lights and calibrated subs move to S3-only, with safe
cleanup and automatic re-fetch.

See [docs/SPEC.md](docs/SPEC.md) for the implementation specification.
