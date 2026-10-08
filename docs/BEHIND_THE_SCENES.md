# Behind the scenes

[Extra credit](../README.md) holds optional lessons that build on the three
core walkthroughs. The current topic is a visual explanation of llm-d. This
repository does not launch a server or deploy a cluster.

## What is in this repository?

- [`README.md`](../README.md) is the topic menu.
- [`llm-d/README.md`](../llm-d/README.md) is the llm-d walkthrough.
- [`llm-d/assets/`](../llm-d/assets) holds its diagrams as SVG files.
- [`docs/`](.) holds this guide.

Each topic keeps its walkthrough and illustrations together. You can read
everything directly on GitHub; there is no documentation build to install.

## Following the llm-d diagrams

The walkthrough follows a request from the client toward model servers, then
looks inside the work needed to produce a response. The diagrams cover:

| Diagram | What to look for |
| --- | --- |
| [Inference pool](../llm-d/assets/inference-pool.svg) | The proxy forwards a request after the endpoint picker chooses a server. |
| [Prefill and decode](../llm-d/assets/prefill-decode.svg) | Prompt processing creates the KV cache; generation uses and extends it. |
| [Prefix-aware routing](../llm-d/assets/prefix-aware-routing.svg) | Reusing a cached prompt prefix can reduce repeated work. |
| [Disaggregated request](../llm-d/assets/disaggregated-request.svg) | Separate workers handle prefill and decode, with a cache transfer between them. |
| [Scaling patterns](../llm-d/assets/scaling-patterns.svg) | Additional replicas, separate phases, and a model spread over accelerators solve different problems. |
| [Expert parallelism](../llm-d/assets/expert-parallelism.svg) | Token activations move between a model's experts; this happens inside model execution. |

The diagrams simplify the system so you can follow these ideas. Their worker
counts, layouts, and arrows are conceptual, not a deployment configuration or
performance measurement. HTTP request routing, KV-cache transfer, and expert
dispatch are distinct operations.

## From an explanation to a deployment

There are no Kubernetes manifests or deployment scripts in this repository.
The walkthrough links to the upstream architecture, quickstart, and
well-lit-path guides when you are ready to connect the concepts to a running
system. Hardware and networking requirements depend on the path you choose.

The [extra-credit RFC](https://github.com/red-hat-ai-dev/vllm-zero-to-hero-extra-credit/issues/1)
tracks diagram, terminology, accessibility, and link review. Reviewing these
files does not count as testing an llm-d deployment.

[Back to extra credit](../README.md) · [Read the llm-d walkthrough](../llm-d/README.md)
