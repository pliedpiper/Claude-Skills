---
name: trending-audio-finder-realtor
description: Find trending audio for TikTok, Instagram Reels, and Facebook. Triggers on "trending sounds", "viral audio", "popular music for reels". Provides curated recommendations with real estate content adaptation ideas.
---

# Trending Audio Finder

Find current trending sounds for TikTok, Instagram Reels, and Facebook, with adaptation guidance for real estate content.

## Workflow

### Step 1: Search for Current Trends

Run multiple web searches to gather trending audio data:

```
Search queries (run 2-3):
- "trending tiktok sounds this week [current month year]"
- "viral instagram reels audio [current month year]"
- "trending songs for reels [current month year]"
```

Prioritize results from these reliable sources:
- **Tokboard** (tokboard.com) - Real-time TikTok sound rankings
- **TikTok Creative Center** (ads.tiktok.com/business/creativecenter) - Official trending data
- **Later Blog** - Weekly trending sound roundups
- **Hootsuite Blog** - Social media trend reports
- **Kapwing Resources** - Trending audio compilations

### Step 2: Curate the List

From search results, identify 5-8 sounds that meet these criteria:
- Currently trending (within past 2 weeks)
- Appropriate for professional/brand content
- Versatile enough for real estate adaptation
- Mix of categories: upbeat, emotional, funny, motivational

For each sound, gather:
- Sound name and original artist (if applicable)
- Direct link to TikTok/Instagram sound page when available
- Current usage context (what types of videos use it)
- Vibe/mood category

### Step 3: Generate Realtor Adaptations

For each sound, provide a specific real estate content idea. Consider these content themes:

**First-Time Buyer Focus:**
- Home tour reveals and reactions
- "Things I wish I knew" educational content
- Mortgage/financing tips made simple
- Move-in day celebrations
- Before/after transformation reveals

**General Realtor Content:**
- Day-in-the-life clips
- Market update snippets
- Client testimonial moments
- Open house energy
- Neighborhood highlights
- Behind-the-scenes showing prep

Match sound vibes to content types:
- **Upbeat/energetic** → Home tours, open houses, sold celebrations
- **Emotional/sentimental** → Client stories, move-in days, dream home reveals
- **Funny/quirky** → Realtor life moments, market commentary, relatable struggles
- **Motivational** → First-time buyer encouragement, "you can do this" content
- **Trending dialogue/memes** → Adapt the format with real estate scenarios

### Fallback Strategy

If primary sources don't yield enough current results:
- Expand time range to past month instead of past 2 weeks
- Include evergreen viral sounds that remain consistently popular
- Note any data freshness limitations to the user
- Suggest the user check TikTok's Discover page directly for real-time trends

## Output Format

**IMPORTANT:** Always save results to a markdown file in the current working directory.

### File Naming Convention
```
trending-audio-YYYY-MM-DD.md
```
Use today's actual date. Example: `trending-audio-2025-12-15.md`

### Template Rules

- Text in `{{PLACEHOLDER}}` must be replaced with actual data
- All other text is **static** and must appear exactly as shown
- Include exactly 5-8 sounds, each following the identical format
- Every sound gets its own `### N. Sound Name` section with the table
- The Quick Reference table must include one row per sound found

### File Template

Copy this template exactly, replacing only the `{{PLACEHOLDER}}` values:

```markdown
# Trending Audio for Realtors

**Generated:** {{MONTH}} {{DAY}}, {{YEAR}}
**Platforms:** TikTok, Instagram Reels, Facebook

---

## Summary

This report contains {{NUMBER}} trending sounds curated for real estate content creators. Sounds are sourced from TikTok, Instagram Reels, and Facebook trends as of {{MONTH}} {{YEAR}}.

---

## Trending Sounds

### 1. {{SOUND_NAME}}

| Field | Details |
|-------|---------|
| **Artist** | {{ARTIST_NAME or "Original Sound"}} |
| **Platform** | {{TikTok / Instagram / Both}} |
| **Link** | {{URL}} |
| **Vibe** | {{upbeat / emotional / funny / motivational}} |
| **Trending Usage** | {{1-2 sentence description}} |

**Realtor Content Idea:** {{Specific content idea for real estate}}

---

### 2. {{SOUND_NAME}}

| Field | Details |
|-------|---------|
| **Artist** | {{ARTIST_NAME or "Original Sound"}} |
| **Platform** | {{TikTok / Instagram / Both}} |
| **Link** | {{URL}} |
| **Vibe** | {{upbeat / emotional / funny / motivational}} |
| **Trending Usage** | {{1-2 sentence description}} |

**Realtor Content Idea:** {{Specific content idea for real estate}}

---

[CONTINUE THIS EXACT FORMAT FOR SOUNDS 3-8]

---

## Quick Reference

| # | Sound | Vibe | Best For |
|---|-------|------|----------|
| 1 | {{SOUND_NAME}} | {{VIBE}} | {{One-line content suggestion}} |
| 2 | {{SOUND_NAME}} | {{VIBE}} | {{One-line content suggestion}} |
| 3 | {{SOUND_NAME}} | {{VIBE}} | {{One-line content suggestion}} |
| 4 | {{SOUND_NAME}} | {{VIBE}} | {{One-line content suggestion}} |
| 5 | {{SOUND_NAME}} | {{VIBE}} | {{One-line content suggestion}} |
[Add rows 6-8 if applicable]

---

## Pro Tips

- Sounds trend for 1-3 weeks typically; act fast on production
- Save sounds to favorites immediately for later use
- Check sound usage count—sweet spot is trending but not oversaturated
- Some sounds are region-locked; test before planning content around them
- Remix/mashup versions sometimes perform better than originals
- **Verify links before use**—sound URLs may change or become unavailable

---

*Report generated on {{MONTH}} {{DAY}}, {{YEAR}}*
```

### Saving the File

1. Replace all `{{PLACEHOLDER}}` values with actual data
2. Replicate the sound section format exactly for each sound (5-8 total)
3. Use the Write tool to save to `trending-audio-YYYY-MM-DD.md`
4. Confirm the file path to the user after saving

## After Saving

Once the file is saved, inform the user:
1. The file path where the report was saved
2. A brief summary of how many sounds were found
3. Remind them that sound trends change quickly, so they should act on the ideas within 1-2 weeks