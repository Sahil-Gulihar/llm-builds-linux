# benchflow

Hard tasks for coding agents. Current focus: Can agents build Linux distros?

## Inspirations

- Deepmind L9 scientist (responsible for RL training for Gemini CLI) told me they were looking for tasks that take at least 100 steps for agents to solve and low pass rate.
- Many AI hardware founders told me that claude code currently fails very hard at building linux distros for them, despite doing everything else pretty decently. They need to do it on a daily basis because it's an important part of their product. (tasks are hard)
- LLM Speedrunner is a very interesting benchmark that lets ai build an entire models https://github.com/facebookresearch/llm-speedrunner
- Also general vibe from talks with frontier lab employees + startup founders + vcs + researchers give me hints that these things are not done (at least properly yet):
  - Coding agent on complex repos
  - Coding agents on repos that need onboarding (k8s e.g.)
  - What areas are coding agents good at (python, fullstack, design?)
  - E2e tasks
  - Long horizon tasks

## Ideas

- 100 tasks that take agents 100 steps to solve (coding mostly)
- Can agents build linux distro (or how many)
- Can agents build chrome (and can they do follow up tasks)
- Can agents build their own bun / rust cargo / openshift / kubernetes etc etc.
- Given any repo / open-source repo and relevant keys / env vars. How far can agents go
- Can agents build their own mobile os etc.
- Inspection on which mode is good at what. E.g. openai models are good at python and claude better at design (similar to design arena)
- Can we harvest talents worldwide (China, India) to create these kinds of environments

## People to outreach to

- People recently worked at eval startup or on linkedin still working on eval / ai infra / data companies. Use ratebench to approach.
- People at cursor, anthropic, cognition, codegen.com, codeos etc. use ratebench to interview
- Researchers at openai, researchers of evals. Use ratebench to interview.
- People Ashwarya knew
- All people from dc agents, terminal bench, harbor (discord, google docs)
- Swebench slack channel, github
- Dolby labs people (enterprise ai use case, how they use claude code, their prs etc.)
- Chrome people (used to add dolby vision support)
- Red hat people (obviously). How many flavors of linux image can claude code build
- Cloud native, kubernetes, docker people

Target: 50 ppl and 10 replies

## Plan

**Phase 1: make hard tasks (e.g. agent builds linux distros)**

Success criteria:
- Have at least a dozen envs / tasks
- Have tested how far can different models go

**Phase 2:** TBD

---

## Some initial thoughts

### Why Linux distro building is a good benchmark

- Long-horizon multi-step tasks (100+ steps easily)
- System-level understanding (kernel, bootloaders, package managers)
- Config file generation and management
- Very long feedback loops (builds take minutes to hours)
- Errors are often cryptic (kernel panics, boot failures)
- Many interdependent config files

### Potential task variants

1. Minimal distro - Build a bootable Linux from scratch (LFS-style)
2. Custom Ubuntu/Fedora spin - Use existing tools (live-build, lorax)
3. Embedded Linux - Yocto/Buildroot for specific hardware
4. Container-optimized - Minimal distro for containers (like Alpine)

### Tools agents would need to use

- debootstrap, live-build (Debian/Ubuntu)
- lorax, kickstart (Fedora/RHEL)
- Yocto Project, Buildroot (embedded)
- Docker/QEMU for testing
