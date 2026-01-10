---
name: bip-commit-generator
description: Generates Build In Public optimized commit messages from git diffs. Use when committing code, writing commit messages, or when the user says "commit", "bip commit", or asks for a commit message.
allowed-tools:
  - Bash(git:*)
  - Read
  - Grep
  - Glob
user-invocable: true
---

# BIP Commit Generator

Generate commit messages that are **Build In Public content gold** — optimized for ShipLoud's AI analysis and social media transformation.

## Core Mission

Transform code changes into commit messages that:
1. **Score 60+ for auto-analysis** by ShipLoud
2. **Tell a human story** — the struggle, breakthrough, and lesson
3. **Fuel 9 content angles** — StoryArc, Personality, Insights, Feature Shout, Heavy Bites, Controversial, Worldbuilding, Unique Perspectives, Surprise
4. **Show the builder's authentic voice**

## Execution Steps

### Step 1: Gather Context (Run in Parallel)

```bash
# Staged changes
git diff --staged

# Recent commits for context/threading
git log -5 --oneline

# Unstaged changes (in case user forgot to stage)
git diff

# Current branch
git branch --show-current
```

Also read:
- `CLAUDE.md` or `README.md` for project context
- `package.json` for tech stack
- Any relevant files from the diff to understand the feature area

### Step 2: Analyze the Changes

Evaluate:

| Factor | What to Look For |
|--------|------------------|
| **Scope** | Which feature area? (auth, payments, UI, API, etc.) |
| **Size** | Lines changed — substantial (50+) or small? |
| **Files** | Single file or multi-file architectural change? |
| **Type** | New feature, bug fix, refactor, perf, docs? |
| **Complexity** | Simple tweak or complex problem solved? |
| **Patterns** | Libraries added? Design patterns used? |
| **User Impact** | What can users do now that they couldn't before? |

### Step 3: Infer the Human Story

**Think like a Build In Public content creator.** Extract the narrative:

1. **The Problem** — What was broken, missing, or suboptimal?
   - Look at: file names, function names, error handling added, comments
   - Example: Adding retry logic → "handling flaky network conditions"

2. **The Journey** — What was the path to the solution?
   - Look at: complexity of changes, multiple approaches in diff, refactored code
   - Example: Replacing a library → "tried X, didn't work, switched to Y"

3. **The Solution** — What's the technical approach?
   - Look at: new dependencies, patterns used, architecture decisions
   - Example: Adding Redis → "caching for faster responses"

4. **The Impact** — Why does this matter to users?
   - Look at: UI changes, error messages improved, performance gains
   - Example: Lazy loading images → "faster page loads on slow connections"

5. **The Lesson** — What would help other builders?
   - Look at: non-obvious solutions, gotchas avoided, best practices applied
   - Example: Using `Promise.all` instead of sequential awaits → "3x faster"

6. **The Energy** — What's the emotional vibe?
   - Look at: commit time, branch name, complexity conquered
   - Late night + complex fix = "finally cracked it after hours of debugging"

### Step 4: Generate the Commit Message

Use this structure:

```
<type>(<scope>): <clear description of what you built/fixed>

<Why this matters — the problem you solved>
<Your solution — technical approach and key decisions>
<Impact — what changed for users or the codebase>

[Optional: Tech used, metrics, lessons learned]
```

#### Commit Types (Conventional Commits)

| Type | When to Use | Score Boost |
|------|-------------|-------------|
| `feat` | New feature or capability | +25 |
| `fix` | Bug fix | +25 |
| `perf` | Performance improvement | +25 |
| `refactor` | Code restructuring without behavior change | +15 |
| `docs` | Documentation only | +5 |
| `test` | Adding/updating tests | +10 |
| `chore` | Maintenance, dependencies | +5 |

### Step 5: Score Check

Before presenting, verify the message would score well:

**Score Boosters (include these):**
- ✅ Conventional commit prefix (`feat:`, `fix:`, etc.)
- ✅ Specific description (not generic)
- ✅ Technical details (libraries, patterns)
- ✅ User impact explained
- ✅ Quantifiable metrics if available

**Score Killers (avoid these):**
- ❌ Generic words: "update", "fix", "changes", "stuff"
- ❌ Single-word messages
- ❌ No context or explanation
- ❌ Missing the "why"

### Step 6: Present the Message

Output format:

```
## 🚀 BIP Commit Message

\`\`\`
<the commit message>
\`\`\`

**Estimated Score:** XX/100 (Auto-analyzed ✅ / Staged ⏳)

**Content Angles This Enables:**
- StoryArc: <one-liner>
- Insights: <one-liner>
- Feature Shout: <one-liner>

---

Ready to commit? Run:
\`\`\`bash
git commit -m "<message>"
\`\`\`
```

## Content Angle Optimization

When crafting the message, consider which angles it could fuel:

| Angle | What to Include in Commit |
|-------|---------------------------|
| **StoryArc** | Problem → journey → solution narrative |
| **Personality** | Authentic voice, struggles, excitement |
| **Insights** | Lessons other builders can learn |
| **Feature Shout** | What users can now do |
| **Heavy Bites** | Strong technical opinions/decisions |
| **Controversial** | Unconventional approaches taken |
| **Worldbuilding** | How this fits the bigger vision |
| **Unique Perspectives** | Fresh problem-solving angles |
| **Surprise** | Counterintuitive discoveries |

## Examples

### Example 1: New Feature

**Diff shows:** New dashboard component with charts, API route, TanStack Query hooks

**Generated message:**
```
feat(dashboard): add real-time commit analytics with daily/weekly breakdowns

Users kept asking for visibility into their build patterns. New dashboard
shows commit frequency, quality scores, and content performance over time.

Built with Recharts for clean data viz and TanStack Query for real-time
updates. The weekly view helps spot patterns — like that mid-week productivity
dip we all pretend doesn't exist.

Stack: Recharts, TanStack Query, Supabase RPC
```

**Score: 92/100** ✅

---

### Example 2: Bug Fix

**Diff shows:** Added null checks, error handling in payment webhook

**Generated message:**
```
fix(payments): handle webhook race condition causing duplicate charges

Found a nasty edge case where slow webhook responses could trigger duplicate
payment processing. Added idempotency keys and a 30-second dedup window.

Users won't get double-charged anymore when Stripe is having a slow day.
The kind of bug that keeps you up at night until it's fixed.
```

**Score: 88/100** ✅

---

### Example 3: Refactor

**Diff shows:** Extracted repeated auth logic into middleware across 8 files

**Generated message:**
```
refactor(api): consolidate auth checks into single middleware — 400 lines gone

Copy-pasted auth validation was scattered across 12 API routes. Classic tech
debt that makes every auth bug a game of whack-a-mole.

Extracted into one middleware with proper error messages and token refresh.
Now auth logic lives in one place. Future me will thank present me.

Deleted: 400 lines of duplicate code
Added: 1 bulletproof middleware
```

**Score: 90/100** ✅

---

## Special Cases

### If No Staged Changes
```bash
git diff
```
Check for unstaged changes and remind the user to stage them:
> "No staged changes found. Run `git add <files>` first, or would you like me to help identify what to commit?"

### If Changes Are Too Small (<15 lines, single file)
Still generate a quality message, but note:
> "⚠️ Small change detected. Consider batching with related work for higher content potential."

### If It's a WIP/Checkpoint
Suggest staging instead of committing:
> "This looks like work-in-progress. Consider using `git stash` or waiting until the feature is more complete for better content potential."

## Reference

For the complete Commit Bible with all scoring details, templates, and psychology signals, see [commit-bible.md](commit-bible.md).

## Remember

**The goal is not just a good commit message — it's a commit message that becomes Build In Public content gold.**

Every commit is a story. Tell it well.
