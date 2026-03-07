# Action Plan — 2-Year Career Roadmap

*Start date: March 2026 · Target: Escape toxic role → AI inference role at a dream company*
*Track progress by checking boxes: `[ ]` → `[/]` (in progress) → `[x]` (done)*

---

## Dream Companies & Why

| Company | Why I Want It | Role Type | Priority |
|---|---|---|---|
| **NVIDIA** | Stock upside + GPU/inference is their DNA | AI Inference / Developer Tools | ⭐⭐⭐⭐⭐ |
| **Google** | Stock upside + DeepMind/TPU/on-device AI | AI/ML Platform Engineer | ⭐⭐⭐⭐⭐ |
| **Anthropic** | Pure innovation, inference org, cutting edge | ML Systems / Inference Deployment | ⭐⭐⭐⭐⭐ |
| **Adobe** | Work-life balance + AI features in creative tools | AI/ML Engineer | ⭐⭐⭐⭐ |
| **Meta** | ExecuTorch, PyTorch, on-device AI | AI Infra / Edge ML | ⭐⭐⭐ |
| **Apple** | MLX, CoreML, on-device privacy | ML Platform Engineer | ⭐⭐⭐ |

### Avoid
- ❌ **Amazon** — toxic PIP culture, same problem I'm escaping
- ❌ **Service-based companies** (TCS, Infosys, Wipro, Accenture) — freelancing for enterprise, no innovation

---

## Phase 1: Foundation & Escape (Months 1–6)

*Priority: Leetcode + System Design + Behavioral + Ship OSS project → Start interview pipeline*

### Time Split (12 hrs/week total)

```
┌──────────────────────────────────────────────┐
│  Leetcode:          5 hrs/week  (42%)        │
│  System Design:     2 hrs/week  (17%)        │
│  Behavioral Prep:   1 hr/week   (8%)         │
│  OSS Project:       4 hrs/week  (33%)        │
└──────────────────────────────────────────────┘
```

### Leetcode (5 hrs/week)

> **Already done**: ~30-40 problems in DP, Graph, Binary Search ✅

- [x] DP fundamentals (30-40 problems done)
- [x] Graph traversal — BFS/DFS (done)
- [x] Binary Search patterns (done)
- [ ] **Month 1–2**: Fill gaps — Arrays, Strings, Two Pointers, Sliding Window, Stack/Queue
- [ ] **Month 2–3**: Trees (BST, traversals, LCA), Heap/Priority Queue, Trie
- [ ] **Month 3–4**: Revisit weak DP patterns (interval DP, bitmask DP, knapsack variants)
- [ ] **Month 4–6**: Company-tagged problems (NVIDIA, Google, Anthropic on Leetcode)
- [ ] **Ongoing**: 1 medium/day on weekdays, 1 hard on weekends

### System Design (2 hrs/week)

- [ ] **Month 1**: Fundamentals — load balancing, caching, DB sharding, CAP theorem
  - Resource: *Grokking System Design* or *System Design Interview (Alex Xu Vol 1)*
- [ ] **Month 2**: Standard problems — URL shortener, rate limiter, notification system
- [ ] **Month 3**: ML-specific system design — design an LLM serving system, model training pipeline
  - This is critical for NVIDIA/Google/Anthropic AI roles
- [ ] **Month 4–5**: Practice mock interviews (Pramp, interviewing.io, or with a friend)
- [ ] **Month 5–6**: Company-specific patterns:
  - **Google**: Design YouTube recommendations, Google Drive sync, distributed cache
  - **NVIDIA**: Design an inference serving platform, TensorRT pipeline, GPU scheduler
  - **Anthropic**: Design Claude's inference routing, multi-accelerator serving, prompt caching
  - **Adobe**: Design real-time image processing pipeline, collaborative editing

### Behavioral Prep (1 hr/week)

- [ ] **Month 1–2**: Write 8-10 STAR stories covering:
  - [ ] Led a technical decision under ambiguity
  - [ ] Handled conflict or toxic team dynamics (you have real experience here)
  - [ ] Shipped something with tight deadlines
  - [ ] Failed and recovered / learned from failure
  - [ ] Mentored or helped a teammate grow
  - [ ] Dealt with disagreement on technical approach
  - [ ] Took initiative beyond job scope (your self-learning story)
  - [ ] Adapted to a major change (frontend → fullstack pivot)
- [ ] **Month 3–4**: Practice delivery — record yourself, refine for 2-min responses
- [ ] **Month 4–6**: Company-specific values prep:
  - **Google**: Googliness — collaboration, humility, user-focus
  - **NVIDIA**: Innovation, speed, technical depth
  - **Anthropic**: Safety-consciousness, mission alignment, intellectual honesty
  - **Adobe**: Creativity, work-life balance, collaboration

### OSS Project: `local-bench` (4 hrs/week)

> An edge LLM benchmarking CLI — "Geekbench for LLMs"

- [ ] **Week 1–3**: Repo setup, CLI skeleton, first benchmark (tokens/sec + memory)
- [ ] **Week 4–7**: Multi-quantization (Q2→Q8), quality scoring, device profiling
- [ ] **Week 7–10**: Web dashboard/leaderboard (GitHub Pages), add 5 popular models
- [ ] **Week 10–12**: Blog post, post to r/LocalLLaMA + HN, community submissions
- [ ] **Target**: 100+ GitHub stars by month 3

### Career Skills (Weave into daily work + weekends)

- [x] Make **Python your primary language** — stop defaulting to JS/TS
- [ ] Learn **Docker deeply** (not just `docker run` — Dockerfiles, multi-stage, compose)
- [ ] Understand **GGUF format**, quantization levels, and quality trade-offs (through local-bench)
- [ ] Read: PagedAttention paper (vLLM), SGLang paper, Flash Attention paper

### Interview Pipeline (Start month 4)

- [ ] Update resume: emphasize full-stack + AI + local-bench project
- [ ] Apply to **Adobe** first (work-life balance, lower bar, good practice)
- [ ] Apply to **Google L4/L5** (AI/ML Platform or Edge AI teams)
- [ ] Apply to **NVIDIA** (Developer Tools, Inference SDK, TensorRT teams)
- [ ] Begin Anthropic application prep (portfolio + narrative)

---

## Phase 2: Level Up & Land (Months 7–12)

*Priority: Interview → Accept offer → Begin deep AI learning*

### Interviews & Applications

- [ ] **Anthropic**: Apply to ML Systems Engineer (RL) or Inference Deployment
  - Prep narrative: L2 Support → Frontend → Full-stack → AI implementer → inference engineer
  - Highlight: local-bench shows inference knowledge, OSS shows initiative
- [ ] **Google**: Target "AI/ML Software Engineer" or "On-Device ML" roles
  - L4 if <5 YoE, L5 if 5+
  - System design: design an LLM serving system at scale
- [ ] **NVIDIA**: Target "Deep Learning Inference Engineer" or "TensorRT" roles
  - Highlight: quantization knowledge from local-bench
- [ ] **Adobe**: Apply to Firefly AI team or Sensei AI platform
  - Lower stress interview, good fallback with great WLB

### OSS Project Growth

- [ ] Add CI/CD — auto-benchmark on new model releases
- [ ] Add community-submitted device results
- [ ] Hit 500+ GitHub stars
- [ ] Evaluate: convert to a product? (benchmarking-as-a-service for AI teams)

### Deep Learning (Post-Escape)

- [ ] **SGLang first contributions** — scheduler, batch manager area
- [ ] Study RLHF: PPO, DPO, reward modeling (for Anthropic prep)
- [ ] Kubernetes deep dive (deploy model serving on K8s)
- [ ] Implement a basic transformer inference engine from scratch
- [ ] Read Anthropic papers: Constitutional AI, RLHF from Human Feedback

---

## Phase 3: Establish & Differentiate (Months 13–18)

*Priority: Excel in new role + Build reputation in edge AI*

### At New Company

- [ ] Deliver strong first 6 months — earn trust, learn the inference stack
- [ ] Identify opportunities to bring edge AI / optimization expertise
- [ ] Build internal relationships with ML/inference teams

### Open Source & Community

- [ ] 10+ meaningful SGLang contributions (scheduler, multi-backend, profiling)
- [ ] Grow local-bench to 1K+ stars or pivot to next project
- [ ] Write 3+ technical blog posts (inference optimization, quantization findings)
- [ ] Speak at 1 meetup or conference (online counts)

### Skills Deepening

- [ ] KV-cache management, prefix caching, speculative decoding
- [ ] GPU profiling (Nsight, PyTorch profiler) — even if not writing CUDA
- [ ] System design for high-throughput serving systems
- [ ] Study tokenization internals (BPE, WordPiece) for breadth

---

## Phase 4: Compound & Choose Direction (Months 19–24)

*Priority: Decide path — stay at company / move up / start something*

### Career Decision Point

- [ ] **Evaluate**: Am I at the right company? Right team? Learning enough?
- [ ] **If yes**: Push for promotion / more impactful projects
- [ ] **If no**: Apply to stretch roles (Anthropic Core Inference, NVIDIA GPU Inference, Google TPU team)
- [ ] **If entrepreneurial itch**: Evaluate converting local-bench or new project into a business

### Stretch Goals

- [ ] Apply to **Anthropic Tier 2 roles** (Core Inference, $300K–$485K)
  - By now: SGLang contributions + local-bench + 1yr inference role = strong candidate
- [ ] Evaluate Anthropic India expansion (if roles have opened)
- [ ] If local-bench has traction: explore "Geekbench for LLMs" as a funded startup idea
- [ ] Consider: open-source AI wearable software platform (long-term vision)

### Knowledge Goals

- [ ] Can explain inference lifecycle end-to-end (model loading → batching → serving → monitoring)
- [ ] Can design a distributed LLM serving system on whiteboard
- [ ] Familiar with GPU/TPU/Trainium differences at a software level
- [ ] Published 5+ technical posts with community following

---

## Company Prep Cheat Sheet

### NVIDIA Interview Focus
| Area | What They Ask |
|---|---|
| Coding | Medium-hard leetcode, heavy on arrays/graphs/DP |
| System Design | GPU-aware inference systems, TensorRT pipeline |
| Domain | CUDA basics, quantization, model optimization |
| Culture Fit | Innovation-driven, fast-paced |

### Google Interview Focus
| Area | What They Ask |
|---|---|
| Coding | Hard leetcode (2-3 rounds), graph/tree heavy |
| System Design | Distributed systems, MapReduce, serving at scale |
| Googliness | Collaboration, ambiguity tolerance |
| ML | ML System Design if applying to AI roles |

### Anthropic Interview Focus
| Area | What They Ask |
|---|---|
| Coding | Python-heavy, systems problems |
| System Design | LLM serving, inference optimization |
| Research awareness | Know their papers (Constitutional AI, RLHF) |
| Culture Fit | Safety-conscious, mission-aligned |

### Adobe Interview Focus
| Area | What They Ask |
|---|---|
| Coding | Medium leetcode (2 rounds) |
| System Design | Standard distributed systems |
| Domain | ML integration in creative tools |
| Culture Fit | Collaborative, balanced |

---

## Monthly Check-In Template

```markdown
## Month [X] Check-In — [Date]

### Leetcode
- Problems solved this month: ___
- Total solved: ___
- Weak areas: ___

### OSS Project
- Commits this month: ___
- GitHub stars: ___
- Community engagement: ___

### Applications & Interviews
- Companies applied: ___
- Interviews scheduled: ___
- Results: ___

### Learning
- Papers read: ___
- New skills: ___
- Blog posts written: ___

### Mood & Energy
- Toxic job coping: 1-5 (1=awful, 5=manageable)
- Motivation level: 1-5
- Adjustments needed: ___
```

---

## The North Star

```
March 2026                          March 2028
───────────                         ───────────
Stuck. Toxic culture.               At NVIDIA/Google/Anthropic/Adobe
No inference experience.   ──────►  Working on AI inference
Grinding leetcode alone.            Recognized OSS contributor
Scattered energy.                   Focused. Growing. Shipping.
```

> **Rule**: Every week, at least 1 leetcode problem and 1 commit to local-bench. No zero weeks. Consistency > intensity.
