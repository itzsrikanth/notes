# Anthropic — AI Inferencing & Research Career Path

> *Last updated: March 6, 2026*
> *Source: [anthropic.com/careers/jobs](https://www.anthropic.com/careers/jobs)*

## My Profile

- Full-stack engineer (transitioned from front-end)
- Learning LLM inferencing; contributing to SGLang
- Goal: move into **AI inferencing / research engineering** at the cutting edge
- Anthropic India expansion — want to be first in line when roles open

---

## The Anthropic Inference Org — How It's Structured

Anthropic's inference-related work spans three major teams:

```
┌─────────────────────────────────────────────────────┐
│                 INFERENCE ORG                        │
│                                                      │
│  ┌──────────────┐ ┌───────────────┐ ┌─────────────┐ │
│  │  Inference    │ │ Cloud         │ │ Inference   │ │
│  │  (Core)       │ │ Inference     │ │ Deployment  │ │
│  │              │ │ (CSP-facing)  │ │ (Launch)    │ │
│  └──────────────┘ └───────────────┘ └─────────────┘ │
└─────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────┐
│           AI RESEARCH & ENGINEERING                  │
│                                                      │
│  ┌──────────────┐ ┌───────────────┐ ┌─────────────┐ │
│  │ Performance  │ │  ML Systems   │ │ Research    │ │
│  │ Engineering  │ │  Engineer     │ │ Engineer    │ │
│  │ (GPU/Perf)   │ │ (RL/Tools)    │ │ (Various)  │ │
│  └──────────────┘ └───────────────┘ └─────────────┘ │
└─────────────────────────────────────────────────────┘
```

---

## Target Roles — Tiered by Reachability

### 🟢 Tier 1 — Reachable Now (12-18 month prep)

#### ML Systems Engineer, RL Engineering
- **Apply**: https://job-boards.greenhouse.io/anthropic/jobs/4952051008
- **Location**: SF | NYC | Seattle
- **Salary**: $500K–$850K
- **Why target this**:
  - Builds the RLHF training pipeline — the algorithms that train Claude
  - Only requires **4+ years SWE experience** — lowest bar of all inference roles
  - Explicitly says *"want to learn more about ML research"* — they expect people to grow in
  - Representative work: profiling RL pipelines, implementing new training algorithms, debugging training slowdowns
- **Gap analysis**:
  - ❌ Large-scale distributed systems experience
  - ❌ LLM training at scale (but SGLang work helps)
  - ⚠️ Python proficiency (needs to be your primary language)
- **Prep required**:
  - Deep Python fluency (asyncio, profiling, GIL internals)
  - Understand RLHF end-to-end (PPO, DPO, reward modeling)
  - Contribute to SGLang's training/fine-tuning pathways

---

#### Software Engineer, Inference Deployment
- **Apply**: https://job-boards.greenhouse.io/anthropic/jobs/5111745008
- **Location**: SF | NYC | Seattle
- **Salary**: $320K–$485K
- **Why target this**:
  - Deploys models across GPU, TPU, Trainium fleets
  - More SWE-flavored than pure ML — deployment pipelines, orchestration, rollout strategies
  - Directly touches inference serving — bridges your software eng skills to ML inference
- **Gap analysis**:
  - ❌ 5+ years deployment/release infrastructure experience
  - ❌ Kubernetes-based deployments
  - ⚠️ Resource-constrained scheduling / capacity planning
- **Prep required**:
  - Kubernetes deep dive (not just basics — rolling updates, custom controllers)
  - CI/CD for ML model deployment
  - Understand inference lifecycle: model loading → batching → serving → monitoring

---

#### ML Systems Engineer, Research Tools (Tokenization)
- **Apply**: https://job-boards.greenhouse.io/anthropic/jobs/4952079008
- **Location**: SF | NYC | Seattle
- **Salary**: $320K–$405K
- **Why target this**:
  - Builds tokenization & encoding systems for pretraining and finetuning
  - Bridge between SWE and ML research — *"engineering that directly enables scientific progress"*
  - BPE tokenization, data pipelines — foundational ML infra
- **Gap analysis**:
  - ⚠️ ML pipeline experience
  - ⚠️ Tokenization algorithms (BPE, WordPiece, SentencePiece)
  - Need strong Python + data processing skills
- **Prep required**:
  - Study tokenizer implementations (HuggingFace tokenizers library)
  - Understand transformer data pipeline: raw text → tokens → embeddings
  - Build/optimize a tokenizer as a learning project

---

### 🟡 Tier 2 — Stretch Target (18-24 month prep)

#### Staff / Senior SWE, Inference (Core)
- **Apply**: https://job-boards.greenhouse.io/anthropic/jobs/4951696008
- **Location**: SF | NYC | Seattle
- **Salary**: $300K–$485K
- **Why it's the dream role**:
  - THE core inference team — serves Claude to millions worldwide
  - Compute-agnostic inference across GPUs, TPUs, Trainium
  - Work: routing algorithms, autoscaling, prompt caching, structured sampling
  - Representative projects are exactly what SGLang works on
- **Gap analysis**:
  - ❌ Significant distributed systems experience
  - ❌ LLM inference optimization (batching, caching, KV-cache management)
  - ❌ Load balancing / request routing at scale
  - ⚠️ Python or Rust proficiency
- **Prep required**:
  - SGLang contributions are GOLD here — focus on the scheduler, RadixAttention, batch manager
  - Study: PagedAttention (vLLM), continuous batching, speculative decoding
  - Learn fundamentals of KV-cache management, prefix caching
  - System design for high-throughput serving systems

---

#### Staff / Senior SWE, Cloud Inference
- **Apply**: https://job-boards.greenhouse.io/anthropic/jobs/5107466008
- **Location**: SF | Seattle
- **Salary**: $300K–$485K
- **Why it's interesting**:
  - Multi-cloud inference (AWS, GCP, Azure) — deploys Claude everywhere
  - Capacity management, cost optimization, autoscaling across providers
  - Less ML-heavy, more infra engineering with inference context
- **Gap analysis**:
  - ❌ Large-scale distributed systems
  - ❌ Cloud platform operations (K8s, IaC)
  - ❌ Multi-region deployments
- **Prep**: Kubernetes + cloud infra deep expertise needed

---

### 🔴 Tier 3 — Long-term Aspiration (2-3 year path)

#### Performance Engineer
- **Apply**: https://job-boards.greenhouse.io/anthropic/jobs/4020350008
- **Location**: SF | NYC | Seattle
- **Salary**: $280K–$850K
- **Why it's the cutting edge**:
  - Low-latency, high-throughput LLM sampling
  - GPU kernel development, quantization
  - Load balancing, fault-tolerant distributed systems
- **Gap**: Needs supercomputing-scale experience, GPU/accelerator programming, OS internals

#### Performance Engineer, GPU
- **Apply**: https://job-boards.greenhouse.io/anthropic/jobs/4926227008
- **Location**: SF | NYC | Seattle
- **Salary**: $280K–$850K
- **Why it's ultimate cutting edge**:
  - CUDA, Triton, CUTLASS, Flash Attention, tensor core optimization
  - Co-design attention mechanisms for next-gen hardware
  - INT8/FP8 quantization, kernel fusion, NCCL
- **Gap**: Needs deep GPU programming background — this is a hardware-software boundary role

---

## India Expansion Reality

| Fact | Detail |
|------|--------|
| **India roles today** | **ZERO** — no India-based listings as of March 2026 |
| **Current locations** | SF, NYC, Seattle, London, Dublin, Zürich |
| **Visa sponsorship** | Yes — they sponsor visas and retain immigration lawyers |
| **Remote-friendly roles** | Some roles marked "Remote-Friendly (Travel-Required)" |
| **When India opens** | Likely Engineering/Infra first, then Research |

**Strategy**: Build skills now so you're an obvious hire when India roles open. The inference + SGLang combination is rare and valuable.

---

## Skill Gap → Preparation Matrix

### Must-Have Skills (Common Across All Target Roles)

| Skill | Current | Target | How to Build |
|-------|---------|--------|-------------|
| **Python (systems-level)** | Web/scripting | Profiling, asyncio, GIL, Cython | SGLang codebase, CPython internals |
| **Distributed systems** | Basic | Large-scale serving | Design distributed KV-store, study Raft/Paxos |
| **LLM inference fundamentals** | Learning | Working knowledge | SGLang, vLLM codebases |
| **Kubernetes** | Unknown | Operational | K8s the hard way, deploy model serving |
| **Cloud infra (GCP/AWS)** | Unknown | Working | Set up inference serving on GCP/AWS |

### Differentiating Skills (Separate You From Other Candidates)

| Skill | Role It Unlocks | How to Build |
|-------|----------------|-------------|
| **RLHF/DPO implementation** | ML Systems Eng, RL | Implement from scratch, study TRL library |
| **KV-cache management** | Core Inference | SGLang's RadixAttention, PagedAttention |
| **Continuous batching** | Core Inference | SGLang scheduler, Orca paper |
| **GPU profiling** | Performance Engineer | Nsight, PyTorch profiler on SGLang |
| **Tokenization internals** | ML Systems Eng, Tools | HuggingFace tokenizers, write a BPE impl |
| **Rust** | Inference (strong candidate) | Rewrite a component of SGLang in Rust |

---

## SGLang → Anthropic Bridge

Your SGLang contributions are your **#1 competitive advantage**. Here's how to maximize it:

### High-Impact SGLang Contributions That Map to Anthropic Roles

| SGLang Area | Anthropic Role Connection |
|-------------|--------------------------|
| **Scheduler / Batch Manager** | Core Inference SWE — request routing, batching |
| **RadixAttention / KV-cache** | Core Inference — prompt caching, structured sampling |
| **Model loading / Tensor parallelism** | Inference Deployment — multi-accelerator serving |
| **RLHF / reward model serving** | ML Systems Eng, RL — training pipeline |
| **Triton kernels** | Performance Engineer — GPU optimization |
| **Benchmark suite** | All roles — performance analysis mindset |
| **CPU backend** | Shows hardware-agnostic thinking (multi-accelerator at Anthropic) |

### Priority contributions to make:
1. **Scheduler optimization** — directly maps to Anthropic's inference routing
2. **Multi-backend support** — Anthropic runs on GPU, TPU, Trainium
3. **Profiling infrastructure** — Performance engineering mindset
4. **Fine-tuning / RLHF pipeline** — unlocks RL Engineering role

---

## Preparation Timeline

### Phase 1: Foundation (Now → Month 3)
- [ ] Make Python your primary language (not just scripting)
- [ ] Complete 3+ meaningful SGLang PRs (scheduler/batching area)
- [ ] Read: "Efficient Memory Management for LLM Serving with PagedAttention" (vLLM paper)
- [ ] Read: "Efficiently Scaling Transformer Inference" (Pope et al.)
- [ ] Read: Anthropic's research papers — Constitutional AI, RLHF from Human Feedback
- [ ] Implement a basic transformer inference engine from scratch

### Phase 2: Depth (Month 3 → Month 9)
- [ ] Deep-dive into SGLang's RadixAttention and prefix caching
- [ ] Learn Kubernetes — deploy a model serving system on K8s
- [ ] Study RLHF: implement PPO/DPO training loop
- [ ] Understand tokenization: implement BPE from scratch
- [ ] Build: end-to-end inference serving system (model loading → batching → serving → monitoring)
- [ ] Contribute to SGLang's multi-backend (TPU/Trainium) support

### Phase 3: Ready to Apply (Month 9 → Month 12-18)
- [ ] Have 10+ SGLang contributions showing depth in inference systems
- [ ] System design practice: design an LLM serving system at scale
- [ ] Study distributed systems: consensus, fault tolerance, load balancing
- [ ] Write a blog post showcasing inference optimization work
- [ ] Prepare narrative: front-end → full-stack → ML inference systems engineer
- [ ] Apply to Tier 1 roles; Express Interest in Tier 2 roles

---

## Key Research Papers to Read

1. **PagedAttention** — Kwon et al. (vLLM) — KV-cache management
2. **Orca** — Yu et al. — Continuous batching for LLM serving  
3. **Flash Attention** — Dao et al. — Memory-efficient attention
4. **FlexGen** — Sheng et al. — High-throughput LLM serving on a single GPU
5. **SGLang: Efficient Execution of Structured LLM Programs** — Zheng et al.
6. **Scaling Laws for Neural LMs** — Kaplan et al. (Anthropic founders)
7. **Constitutional AI** — Bai et al. (Anthropic)
8. **Training Language Models to Follow Instructions with Human Feedback** — Ouyang et al. (RLHF)
9. **Speculative Decoding** — Leviathan et al. — Parallel token generation
10. **Medusa** — Cai et al. — Multi-head decoding for faster inference

---

## Summary: Where I Stand

```
Current Position                    Target Position
─────────────                       ───────────────
Full-Stack Engineer      ──────►    ML Systems / Inference Engineer
│                                   │
├─ React/TS/Node         ──────►    ├─ Python (systems-level)
├─ Web APIs              ──────►    ├─ Distributed inference systems
├─ UI/UX                 ──────►    ├─ Inference observability
├─ Basic Python           ────►     ├─ RLHF/training pipelines
└─ SGLang (learning)      ────►     └─ KV-cache, batching, scheduling
```

**The bridge**: SGLang contributions + deep inference knowledge + software engineering maturity.

**Bottom line**: The **ML Systems Engineer, RL Engineering** role is the most reachable entry point into Anthropic's inference world, with only 4+ years SWE required and explicit openness to candidates who *"want to learn ML research."* From there, lateral moves into Core Inference or Performance Engineering become natural.
