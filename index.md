# Skillwright

Skillwright is a library of production-grade Agent Skills for Claude Code, Codex, Cursor and other AI coding agents. Each skill turns your agent into a specialist for one shipping task: SEO and AI-search audits, launch copy, landing pages, payments and pre-launch security reviews.

## Skills

- [SEO + AEO + GEO Audit](https://dydipanshu.github.io/skills/seo-geo-audit.md) (free): The SEO + AEO + GEO Audit skill makes your AI coding agent audit a website for Google rankings, answer-engine snippets and citations in ChatGPT, Claude, Perplexity and Gemini. It scores the site, lists the top fixes by impact, then implements them in your codebase: meta tags, structured data, sitemap, robots.txt and llms.txt.
- [Launch Kit](https://dydipanshu.github.io/skills/launch-kit.md) (free): The Launch Kit skill writes a full product launch from your codebase: an X thread, subreddit-specific Reddit posts, a Show HN post and maker comment, a Product Hunt listing, a LinkedIn post and a 14-day posting calendar. Copy is written natively for each platform's rules and culture, and never invents metrics or testimonials.
- [Landing Page](https://dydipanshu.github.io/skills/landing-page.md) (premium): The Landing Page skill makes your AI agent position your product, write conversion copy section by section, and build a fast, accessible, SEO-ready landing page with pricing, FAQ and structured data. It works in your existing stack or produces dependency-free HTML and CSS, and finishes with a conversion review.
- [Payments Setup](https://dydipanshu.github.io/skills/payments-setup.md) (premium): The Payments Setup skill adds checkout, subscriptions and webhooks to your app with Stripe, Lemon Squeezy, Dodo Payments, Paddle or Polar. It verifies webhook signatures, makes event handling idempotent, grants access only after confirmed payment, and tests every billing event, including failed payments, cancellations and refunds.
- [Ship Check](https://dydipanshu.github.io/skills/ship-check.md) (premium): The Ship Check skill runs a pre-launch production readiness review of your web app: leaked secrets, authorization holes, database security, error handling, monitoring, backups, performance and legal pages. It ranks findings as blockers, high or nice-to-have, fixes the blockers, and gives a clear ship or don't-ship verdict.

## Pricing

- Free: $0. Open-source skills, free forever.
- Pro: $9/month. Every premium skill plus new skills every week.
- Founding Lifetime: $149. Pay once, get every skill we ever ship.

## FAQ

### What are Claude Code skills?

Claude Code skills are folders containing a SKILL.md file with instructions that teach Claude Code how to do a specific task. Claude loads a skill automatically when your request matches its description, so you get expert-level results without writing long prompts each time.

### Do Skillwright skills work with Codex, Cursor and other agents?

Yes. Skillwright skills use the open Agent Skills format (a folder with a SKILL.md file), which Claude Code supports natively and other agents such as Codex and Cursor can load. The instructions are plain Markdown, so any capable coding agent can follow them.

### How do I install a skill?

Copy the skill folder into ~/.claude/skills/ to use it in every project, or into .claude/skills/ inside a repository to share it with your team. Free skills can be installed with one git clone command; premium skills are a download after purchase.

### How much does Skillwright cost?

The seo-geo-audit and launch-kit skills are free and open source. Skillwright Pro costs $9 per month or $69 per year and includes every premium skill plus new skills every week. Founding Lifetime access is a one-time $149.

### Can I use the skills in commercial and client projects?

Yes. You can use every Skillwright skill in personal, commercial and client work. You can't resell or redistribute the premium skill files themselves.

### What makes a skill better than a prompt?

A skill is a tested, structured workflow: it tells the agent what to inspect, what checklist to follow, what to output and what never to do. Prompts are written fresh each time and skip steps; skills give the same high-quality process on every run.

### Can I get a refund?

Yes. If a premium skill doesn't work for you, open a support request within 14 days of purchase for a full refund.
