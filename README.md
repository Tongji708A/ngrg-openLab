# OpenLab @ nGRG

**An open, neutral, reproducible research testbed for AI-RAN — under O-RAN Alliance · nGRG governance.**

> Enable world-wide AI-RAN technology research and development by providing a neutral, open, and reproducible research testbed under O-RAN nGRG governance.

The lab exists to give global AI-RAN researchers a common, credible, reproducible experimental platform — a stable open base for exploring new directions. It is **not** a ranking of vendors; it is a neutral stage on which open stacks and vendor tooling are exercised in the open.

---

## Concept

| Principle | What it means |
|---|---|
| **Open baseline** | [OpenAirInterface (OAI)](https://openairinterface.org/) is the primary research stack — fully open (LGPL/CeCILL), academically reproducible, vendor-neutral by design. |
| **Dual-vendor compute** | NVIDIA GPU acceleration alongside Intel and AMD x86 — a neutral plane where each vendor's AI-RAN enablement is exercised on equal footing. |
| **Reproducible by default** | Every stack is source-built and scripted, from protocol code to channel model — results others can re-run, not just read. |

Benchmarking is used as a *method* (a validation baseline for proofs-of-concept), **not** as the lab's outward theme — the research value lies in exploring new directions on a stable open base, not in judging whose numbers are better.

---

## Research Directions

### AI-on-Open-RAN — flagship direction

A broad theme, not a single project: use the open, disaggregated, GPU-accelerated Open RAN platform as both a **substrate for AI** and a **target for AI** — letting AI and RAN empower each other on one shared, reproducible base.

| Thread | Meaning | Handle in the lab |
|---|---|---|
| **AI enhancing RAN** | ML reshaping RAN functions themselves | Neural receivers, learned scheduling, beam-management xApps (Sionna + PyTorch + FlexRIC) |
| **AI hosted on RAN** | AI services/workloads co-located on RAN compute | Edge-AI inference sharing the GPU/CPU fabric with vRAN — isolation, scheduling, interference |
| **AI + RAN shared platform** | Resource orchestration and contention between AI and RAN on one fabric | Dynamic orchestration, reproducible energy/throughput trade-off benchmarks |

Built directly on the lab's existing open baseline (OAI), AI/channel plane (Sionna · PyTorch), and near-RT RIC (FlexRIC) — no new substrate required.

---

## Research Stack

A full O-RAN stack, open top to bottom — all software, all source-built, running end-to-end without special hardware.

| Layer | Components |
|---|---|
| **Control · O-RAN / RIC** | FlexRIC (near-RT RIC) · xApps (KPM · RC · MAC · TC) · E2 SM (KPM v3 · RC · E2AP v3) |
| **RAN L1–L3 · gNB & UE** | **OpenAirInterface** (gNB + nrUE · RFsim) *[baseline]* · srsRAN Project (gNB · ZMQ) · srsRAN 4G · UERANSIM |
| **Core · 5G Core & EPC** | Open5GS (5G SA + EPC · 20 NFs) · MongoDB subscriber DB |
| **AI & Channel plane** | Sionna (link-level PHY + ray-tracing) · PyTorch (CUDA/GPU) · 5G-LENA (ns-3 NR system-level) · MATLAB 5G (link-level cross-check) |
| **Fabric · Compute** | NVIDIA CUDA (GPU acceleration) · Intel Xeon 6 · AMD Threadripper |

### Compute fabric

| Node | CPU | GPU | Notes |
|---|---|---|---|
| **Node A** · local | AMD Threadripper 7960X (24C / 48T) | NVIDIA RTX 5090 · 32 GB | 384 GB RAM · Ubuntu 22.04 LTS |
| **Node B** · remote | Intel Xeon 6 | NVIDIA RTX 5090 | Intel x86 AI-RAN node · shared access |

The fabric already spans **both x86 vendors — Intel Xeon 6 and AMD Threadripper — each paired with an NVIDIA RTX 5090**, realizing the "x86 + NVIDIA GPU" compute tier with genuine dual-vendor coverage.

---

## Current Progress

**Status (2026 Q3):** Phase 0 infrastructure complete; Phase 1 in progress.

### ✅ Live today — simulation & experimentation

- Two-node dual-vendor compute fabric online (AMD + Intel, NVIDIA GPU on each)
- Multi-stack RAN on CPU + GPU: full software **L1–L3 emulation** with virtual RF (RFsim / ZMQ)
- **End-to-end 5G SA** — OAI gNB + nrUE against Open5GS core
- **O-RAN E2/RIC closed loop** — FlexRIC + xApps (KPM / RC)
- Link-level PHY (Sionna) and system-level (5G-LENA) benchmarks

### 🔜 Next

- **Over-the-air via O-RU** — introduce radio units for real-signal, full end-to-end RAN validation on the same open stacks
- First AI-on-Open-RAN proofs-of-concept (dataset + model + code)
- Multi-node reproducible benchmarks across the shared fabric

### Roadmap

| Phase | Window | Milestone |
|---|---|---|
| Phase 0 | 2026 Q2 | Infrastructure — servers, OAI deployment, CI pipeline ✅ |
| Phase 1 | 2026 Q3 | OAI + NVIDIA GPU + Intel CPU integrated; first AI-RAN PoC 🔧 |
| Phase 2 | 2026 Q4 | Live RF via O-RU; reproducible benchmarks (as method, not theme) |
| Phase 3 | 2027 H1 | ARM, RISC-V, accelerator cards; first major nGRG research output |

---

## Outputs

1. **Research outputs** — nGRG Research Reports and top-tier conference papers
2. **Reference designs** — reproducible AI-RAN prototypes released as dataset + model + code
3. **Open-source contributions** — improvements fed back upstream to OAI and the O-RAN ecosystem
4. **Standards-relevant findings** — evidence that feeds into O-RAN Alliance specification work

---

## Governance

Hosted under **O-RAN Alliance · nGRG** governance. Open application, member-priority; outputs contributed back to the open community.

- Hao Xu — Tongji University · nGRG RS-02 Co-leader
- Tommaso Melodia — Northeastern University · nGRG Co-Chair
- Tao Chen — VTT · nGRG Chair

---

*Licensed under the terms in [LICENSE](LICENSE).*
