# BuildInPublic Claude Plugins

Official Claude Code plugins from [BuildInPublic](https://buildinpublic.so) — Build In Public tools for developers.

## Installation

### Step 1: Add the BuildInPublic marketplace (one-time)

```bash
/plugin marketplace add buildinpublic/bip-claude-plugins
```

### Step 2: Install plugins

```bash
/plugin install bip-commit-generator@bip-claude-plugins
```

That's it! The skill is now available in any of your projects.

---

## Available Plugins

### 🚀 BIP Commit Generator

**Generates Build In Public optimized commit messages, creates 3 ready-to-post tweets, then commits and pushes — all in one command.**

Turn your commits into content gold. No friction. No excuses.

**What it does:**
1. Analyzes your changes automatically
2. Generates a commit message optimized for BuildInPublic's scoring system (60+ for auto-analysis)
3. Creates 3 different tweets from your commit (The Win, The Story, The Lesson)
4. Commits and pushes automatically
5. Gives you tweets ready to copy-paste

**How to use:**

Just say:
- `"commit"` or `"bip commit"`
- `"write a commit message"`
- `"help me commit this"`

Claude will analyze your changes, generate everything, commit, push, and give you tweets to post.

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

---

## 🐦 Ready-to-Post Tweets

**Tweet 1 — The Win**
Just shipped real-time analytics for BuildInPublic 📊

Now you can see your commit patterns, quality scores, and when you're actually productive (spoiler: it's not Mondays).

What metrics would you want to track?

**Tweet 2 — The Story**
Users kept asking: "When am I most productive?"

So I built a dashboard to answer it.

Turns out we all have a mid-week dip. At least now we can see it coming.

**Tweet 3 — The Lesson**
Hot take: If you're building a dev tool without analytics, you're flying blind.

Added Recharts + TanStack Query today. Took 2 hours. Now I know exactly how my users build.

Your users are telling you things through their behavior. Are you listening?

---

## ✅ Shipped!

Commit: a1b2c3d
Branch: main
Remote: origin

Your tweets are ready to copy-paste. Go build in public! 🚀
```

---

## Why BIP Commits Matter

Your commits are your content engine. BuildInPublic's AI analyzes them to:

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

- [BuildInPublic](https://buildinpublic.so) — The visibility OS for software builders

---

Made with love by eddspire x.com/@eddspire
