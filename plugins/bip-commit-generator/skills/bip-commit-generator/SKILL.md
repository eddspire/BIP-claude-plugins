---
name: bip-commit-generator
description: Generates Build In Public optimized commit messages, creates 3 ready-to-post tweets, then commits and pushes. Use when committing code, writing commit messages, or when the user says "commit", "bip commit", or asks for a commit message.
allowed-tools:
  - Bash(git:*)
  - Read
  - Grep
  - Glob
user-invocable: true
---

# BIP Commit Generator

Generate commit messages that are **Build In Public content gold** — optimized for BuildInPublic's AI analysis and social media transformation. Then auto-generate tweets and ship it.

## Core Mission

Transform code changes into:
1. **Commit messages that score 60+** for auto-analysis by BuildInPublic
2. **3 ready-to-post tweets** — different angles for your audience
3. **Auto-commit and push** — ship it immediately

The commit message tells a human story — the struggle, breakthrough, and lesson. The tweets amplify it.

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

### Step 6: Generate 3 Tweets

Create 3 different tweets from the commit, each with a different angle:

**Tweet 1 — The Win (Feature Shout)**
- Lead with what you shipped
- Keep it punchy and celebratory
- Include a hook that makes people curious
- End with engagement driver (question or CTA)

**Tweet 2 — The Story (StoryArc/Personality)**
- Share the journey or struggle
- Be vulnerable about challenges faced
- Show the human side of building
- Relatable developer moments

**Tweet 3 — The Lesson (Insights/Heavy Bites)**
- Extract a teachable moment
- Share a hot take or opinion
- Give actionable advice
- Something other builders can learn from

**Tweet Guidelines:**
- Max 280 characters each
- Use line breaks for readability
- No hashtags (they look desperate)
- Be authentic, not corporate
- Include 1-2 relevant emojis max (optional)

### Step 7: Present Everything

Output format:

```
## 🚀 BIP Commit Message

\`\`\`
<the commit message>
\`\`\`

**Estimated Score:** XX/100 (Auto-analyzed ✅)

---

## 🐦 Ready-to-Post Tweets

**Tweet 1 — The Win**
<tweet text>

**Tweet 2 — The Story**
<tweet text>

**Tweet 3 — The Lesson**
<tweet text>

---
```

### Step 8: Commit and Push

After presenting the commit message and tweets, immediately execute:

```bash
# Stage all changes if not already staged
git add -A

# Commit with the generated message
git commit -m "<the commit message>"

# Push to remote
git push
```

**Important:**
- Use `git push -u origin <branch>` if the branch has no upstream
- If push fails due to no upstream, set it and retry
- Report success or failure to the user

Final output after pushing:

```
## ✅ Shipped!

Commit: <short hash>
Branch: <branch name>
Remote: <remote url or name>

Your tweets are ready to copy-paste. Go build in public! 🚀
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

**Generated output:**

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
```

---

### Example 2: Bug Fix

**Diff shows:** Added null checks, error handling in payment webhook

**Generated output:**

```
## 🚀 BIP Commit Message

fix(payments): handle webhook race condition causing duplicate charges

Found a nasty edge case where slow webhook responses could trigger duplicate
payment processing. Added idempotency keys and a 30-second dedup window.

Users won't get double-charged anymore when Stripe is having a slow day.
The kind of bug that keeps you up at night until it's fixed.

**Estimated Score:** 88/100 (Auto-analyzed ✅)

---

## 🐦 Ready-to-Post Tweets

**Tweet 1 — The Win**
Fixed a payment bug that was double-charging users 💸

Idempotency keys + dedup window = no more angry refund emails.

Sleep quality: restored.

**Tweet 2 — The Story**
Got a support ticket at 11pm: "Why was I charged twice?"

Spent 3 hours in webhook logs. Found a race condition that only happens when Stripe is slow.

The scariest bugs are the ones that work 99% of the time.

**Tweet 3 — The Lesson**
PSA for anyone handling payment webhooks:

Always use idempotency keys. Always.

Stripe can retry. Networks can lag. Your code needs to handle "this already happened."

Learned this the hard way so you don't have to.

---

## ✅ Shipped!

Commit: d4e5f6g
Branch: main
Remote: origin
```

---

### Example 3: Refactor

**Diff shows:** Extracted repeated auth logic into middleware across 8 files

**Generated output:**

```
## 🚀 BIP Commit Message

refactor(api): consolidate auth checks into single middleware — 400 lines gone

Copy-pasted auth validation was scattered across 12 API routes. Classic tech
debt that makes every auth bug a game of whack-a-mole.

Extracted into one middleware with proper error messages and token refresh.
Now auth logic lives in one place. Future me will thank present me.

Deleted: 400 lines of duplicate code
Added: 1 bulletproof middleware

**Estimated Score:** 90/100 (Auto-analyzed ✅)

---

## 🐦 Ready-to-Post Tweets

**Tweet 1 — The Win**
Deleted 400 lines of code today and the app got better.

Consolidated 12 copy-pasted auth checks into 1 middleware.

Sometimes the best code is the code you remove.

**Tweet 2 — The Story**
Found the same auth check copy-pasted in 12 different files.

Every time we fixed an auth bug, we had to fix it 12 times.

Today I mass-deleted everything and wrote it once. Took 2 hours. Should've done it months ago.

**Tweet 3 — The Lesson**
The rule I follow now:

If you copy-paste code more than twice, you're creating a bug farm.

Every duplicate is a place where future-you will forget to update something.

Abstractions aren't always premature. Sometimes they're overdue.

---

## ✅ Shipped!

Commit: h7i8j9k
Branch: main
Remote: origin
```

---

## Special Cases

### If No Staged Changes
```bash
git diff
```
Check for unstaged changes. If there are unstaged changes, stage them automatically with `git add -A` and proceed. If there are truly no changes:
> "No changes detected. Make some changes first, then run /commit again."

### If Changes Are Too Small (<15 lines, single file)
Still generate everything (commit message, tweets, commit, push), but note:
> "⚠️ Small change — tweets might feel thin. Consider batching related work next time for more content potential."

### If It's a WIP/Checkpoint
Proceed anyway but adjust the messaging:
> "This looks like work-in-progress. Committing anyway — you can always squash later. Tweets focused on the journey rather than a finished feature."

### If Push Fails
Handle common failures:
- **No upstream branch:** Run `git push -u origin <branch>` to set upstream
- **Behind remote:** Run `git pull --rebase` then retry push
- **Permission denied:** Inform user to check their git credentials

Report the issue and retry once. If it still fails, show the commit was successful but push needs manual intervention.

## Reference

For the complete Commit Bible with all scoring details, templates, and psychology signals, see [commit-bible.md](commit-bible.md).

## Remember

**The goal is not just a good commit message — it's a commit message AND tweets that become Build In Public content gold.**

Every commit is a story. Tell it well. Then ship it immediately.

**The workflow is:**
1. Analyze changes
2. Generate commit message
3. Generate 3 tweets
4. Commit and push
5. User copies tweets and posts

No friction. No excuses. Ship it.
