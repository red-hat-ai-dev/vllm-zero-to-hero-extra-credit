# Explainer validation

Reviewed 2026-10-07 against llm-d v0.10 documentation:

- [Architecture](https://llm-d.ai/docs/architecture): proxy/EPP responsibilities,
  model servers, and InferencePool grouping.
- [Optimized baseline](https://llm-d.ai/docs/well-lit-paths/foundations/optimized-baseline):
  load and prefix awareness.
- [Prefill/decode disaggregation](https://llm-d.ai/docs/well-lit-paths/foundations/pd-disaggregation):
  separate workers, routing sidecar, and KV transfer.

These are moving upstream links. Recheck their semantics when llm-d changes,
especially sidecar/request flow, KV transfer, and accelerator/network requirements.

The lesson is a conceptual visual explainer. There are no deployable manifests,
benchmark measurements, or tested Kubernetes/GPU combinations in this repository.
Single-machine Apple Silicon and RTX 3090 tests of the earlier lessons do not
validate a distributed llm-d deployment. Follow the linked upstream deployment
guide and its version-specific hardware prerequisites for an actual installation.

Run `python3 -m unittest discover -s tests -v` to check repository-local Markdown
and HTML asset references and parse all six SVG files. Pull-request CI runs these
offline checks. Passing XML validation does not establish visual readability or
architectural correctness; those require review of the rendered diagrams and
upstream documentation. Check external URLs when updating the reviewed baseline.

Course repositories are intentionally private during development. The checks do
not interpret an anonymous GitHub 404 as a course-navigation defect.
