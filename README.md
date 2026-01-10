# ShipLoud Claude Plugins

Official Claude Code plugins from [ShipLoud](https://shiploud.dev) — Build In Public tools for developers.

## Installation

### Step 1: Add the ShipLoud marketplace (one-time)

```bash
/plugin marketplace add shiploud/bip-claude-plugins
```

### Step 2: Install plugins

```bash
/plugin install bip-commit-generator@bip-claude-plugins
```

That's it! The skill is now available in any of your projects.

---

## Available Plugins

### 🚀 BIP Commit Generator

**Generates Build In Public optimized commit messages from your git diffs.**

Turn your commits into content gold that ShipLoud's AI can transform into tweets, threads, and posts.

**What it does:**
- Analyzes your staged changes automatically
- Infers the human story (problem → solution → impact)
- Generates commit messages optimized for ShipLoud's scoring system (60+ for auto-analysis)
- Suggests content angles your commit enables

**How to use:**

Just say:
- `"commit"` or `"bip commit"`
- `"write a commit message"`
- `"help me commit this"`

Claude will analyze your changes and generate a BIP-optimized commit message.

**Example output:**

```
## 🚀 BIP Commit Message

feat(dashboard): add real-time commit analytics with daily/weekly breakdowns

Users kept asking for visibility into their build patterns. New dashboard
shows commit frequency, quality scores, and content performance over time.

Built with Recharts for clean data viz and TanStack Query for real-time
updates. The weekly view helps spot patterns — like that mid-week productivity
dip we all pretend doesn't exist.

Stack: Recharts, TanStack Query, Supabase RPC

**Estimated Score:** 92/100 (Auto-analyzed ✅)

**Content Angles This Enables:**
- StoryArc: From user request to data-driven insights
- Insights: How to build analytics that users actually want
- Feature Shout: Ship Loud now shows your build patterns
```

---

## Why BIP Commits Matter

Your commits are your content engine. ShipLoud's AI analyzes them to:

1. Extract the technical story (what you built and how)
2. Understand your developer psychology (mindset, patterns, breakthroughs)
3. Identify user impact (why this matters)
4. Generate content angles tailored to your work
5. Create authentic "build in public" narratives

**The better your commit, the better the content.**

---

## More Plugins Coming Soon

- **Vibey Planner** — Campaign planning assistant
- **Dev Card Reviewer** — Analyze your commit cards before sharing
- **Content Calendar** — AI-suggested posting schedule

---

## Links

- [ShipLoud](https://shiploud.dev) — The visibility OS for software builders
- [Commit Bible](https://shiploud.dev/docs/commit-bible) — Full guide to writing content-worthy commits
- [Support](https://shiploud.dev/support) — Get help

---

Made with 🔥 by the ShipLoud team
