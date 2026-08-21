# Market-Signal-Agent

A pipeline of prompt-driven agents for a faceless YouTube affiliate/digital
product business — from finding trending topics to shipping ready-to-review
scripts and post designs across every platform.

1. [`market-signal-agent-prompt.md`](./market-signal-agent-prompt.md) —
   finds trending topics/products, screens them for a monetization angle
   (affiliate, free giveaway, paid product) plus audience-fit, brand
   safety, duplicate, and legal/claims risk, then scores and ranks a
   batch of candidates.
2. [`content-demographic-strategy-agent-prompt.md`](./content-demographic-strategy-agent-prompt.md) —
   takes that validated batch and produces a data-backed content
   strategy for each item: value objective per asset, buyer persona,
   objection handling, competitor analysis, format/visual
   recommendations, compliance language, and feedback-loop tracking.
3. [`multi-platform-content-design-agent-prompt.md`](./multi-platform-content-design-agent-prompt.md) —
   takes each strategy profile and produces the actual scripts, shot
   lists, and still-post designs for YouTube (long-form + Shorts),
   TikTok, Instagram, and Facebook, ready for a pre-production review
   before handoff to the video editor/graphic designer.

## Setup

Prompts 1 and 2 call for real YouTube trend/competitor data (trending
topics, search volume signals, competitor video view/like/comment
counts) via the YouTube Data API v3. To supply it:

1. Copy `.env.example` to `.env`.
2. Set `YOUTUBE_API_KEY` in `.env` to your own YouTube Data API v3 key
   (Google Cloud Console → APIs & Services → Credentials).
3. Export it into your shell/agent environment before running a prompt,
   e.g. `export $(cat .env | xargs)` (or your tool's equivalent).

`.env` is git-ignored — never commit a real key. If a key is ever
pasted into a chat, ticket, or log, treat it as compromised and
regenerate it in Google Cloud Console regardless of whether it reached
this repo.
