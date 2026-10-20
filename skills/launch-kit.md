# Launch Kit skill for Claude Code

The Launch Kit skill writes a full product launch from your codebase: an X thread, subreddit-specific Reddit posts, a Show HN post and maker comment, a Product Hunt listing, a LinkedIn post and a 14-day posting calendar. Copy is written natively for each platform's rules and culture, and never invents metrics or testimonials.

Tier: free

## When to use it

- Launching a SaaS, app or open-source project
- Getting your first 100 users
- Writing a Show HN or Product Hunt launch
- Planning build-in-public posts

## SKILL.md

---
name: launch-kit
description: Write a complete launch kit for a product - X/Twitter thread, Reddit posts tailored per subreddit, Hacker News "Show HN", Product Hunt listing, LinkedIn post, and a 14-day posting calendar. Use when the user is launching a product, feature or project, asks for launch posts, social copy, or "how do I get my first users".
---

# Launch Kit

You write launch copy that gets real users, not vanity likes. Every platform has its own culture;
copy that works on X gets removed on Reddit and flagged on Hacker News. Write for each one natively.

## Step 1: Gather facts (read before asking)

Read the README, landing page, pricing and recent commits. Extract:

- What it does, in one sentence a non-expert understands
- Who it's for (specific: "solo founders shipping SaaS", not "everyone")
- The painful problem it removes, and what people do today instead
- Proof: numbers, demos, screenshots, benchmarks, early user quotes
- Price and whether there's a free tier or trial
- The founder's story: why they built it (one or two true sentences)

Ask the user only for what you can't find. Never invent users, metrics, testimonials or press.

## Step 2: Write each asset

### X / Twitter thread (5-8 posts)
- Post 1: the hook. A specific outcome or surprising fact, not "I'm excited to announce". Under 200 chars.
- Posts 2-6: problem, what you built, a demo (tell the user where a GIF/video goes), how it works, proof
- Last post: link plus a clear ask (try it, reply with feedback, repost if useful)
- Also write 3 standalone follow-up posts for later days (a build lesson, a metric, a user story)

### Reddit (one version per subreddit, 3-5 subreddits)
- Pick subreddits where the audience has the problem, and note each one's self-promotion rules
  (many require a ratio of non-promotional activity, or only allow it on specific weekdays/threads)
- Lead with value: what you learned, how you solved it. Mention the product late, plainly, once.
- Title as a statement or question a member would write, not an ad. No emojis or hype words.
- Flag subreddits where a direct link will likely get removed and suggest a comment-link approach

### Hacker News "Show HN"
- Title: `Show HN: <Name> – <plain description of what it does>` (no superlatives)
- First comment from the maker: what it is, why you built it, how it works technically,
  what's rough, what feedback you want. Humble and specific. HN rewards technical depth.

### Product Hunt
- Tagline (60 chars max), description (260 chars), 3-5 topic tags
- Maker's first comment (story + what's special + launch-day offer if any)
- Gallery plan: 4-6 image captions in order
- Note: launch 12:01am Pacific; tell the user to line up supporters to comment, not just upvote

### LinkedIn post
- First 2 lines must earn the "see more" click. Story-led, one lesson, product as the result.

## Step 3: 14-day calendar

A table: day, platform, asset, goal. Spread launches so the user can reply to every comment
(engagement in the first hours decides reach). Include build-in-public posts after launch day.

## Rules

- Write in the founder's voice: first person, plain words, specific numbers
- Banned phrases: "game-changer", "revolutionize", "excited to announce", "unlock", "supercharge",
  "in today's fast-paced world"
- Every claim must be checkable from the product or the user's own words
- Output everything in one Markdown file (`launch-kit.md`) so the user can copy-paste

