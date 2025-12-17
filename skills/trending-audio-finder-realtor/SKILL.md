---
name: trending-audio-finder-realtor
description: Find trending audio for TikTok, Instagram Reels, and Facebook. Triggers on "trending sounds", "viral audio", "popular music for reels". Provides complete video briefs with scripts, shot timing, and on-screen text for real estate content.
---

# Trending Audio Finder

Find current trending sounds for TikTok, Instagram Reels, and Facebook. Generates complete video briefs with scripts, shot-by-shot timing, and on-screen text suggestions tailored for real estate content creators.

## Workflow

### Step 1: Search for Current Trends

Run multiple web searches to gather trending audio data:

```
Search queries (run 2-3):
- "trending tiktok sounds this week [current month year]"
- "viral instagram reels audio [current month year]"
- "trending songs for reels [current month year]"
```

When you find trending sounds, also search for example videos:
```
- "[sound name] tiktok trend"
- "[sound name] viral video example"
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
- Example video link showing the trend in action (prioritize popular/well-executed examples)
- Current usage context (what types of videos use it)
- Vibe/mood category

### Step 3: Create Full Video Briefs

For each sound, create a complete video brief that the realtor can immediately use to film. Each brief should include a script, shot timing, and on-screen text.

**Content Theme Guidelines:**

*First-Time Buyer Focus:*
- Home tour reveals and reactions
- "Things I wish I knew" educational content
- Mortgage/financing tips made simple
- Move-in day celebrations
- Before/after transformation reveals

*General Realtor Content:*
- Day-in-the-life clips
- Market update snippets
- Client testimonial moments
- Open house energy
- Neighborhood highlights
- Behind-the-scenes showing prep

**Match sound vibes to content types:**
- **Upbeat/energetic** → Home tours, open houses, sold celebrations
- **Emotional/sentimental** → Client stories, move-in days, dream home reveals
- **Funny/quirky** → Realtor life moments, market commentary, relatable struggles
- **Motivational** → First-time buyer encouragement, "you can do this" content
- **Trending dialogue/memes** → Adapt the format with real estate scenarios

**Script Structure (for each sound):**

1. **Hook (0-3 sec):** Attention-grabbing opener—question, bold statement, or visual surprise
2. **Main Content (3-12 sec):** The core value, story beat, or payoff
3. **CTA (final 2-3 sec):** What you want viewers to do next (follow, comment, save, DM)

**Shot Timing Guidelines:**
- Watch the example video to identify beat drops, transitions, or lyric moments
- Plan shot changes to align with audio beats
- Note any text reveal timing from popular versions

**On-Screen Text Rules:**
- Keep text to 3-7 words per screen
- Use text to reinforce the hook or add context the audio doesn't provide
- Place text where it won't cover the realtor's face

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

This report contains {{NUMBER}} trending sounds with complete video briefs for real estate content. Each sound includes a script, shot-by-shot timing, and on-screen text suggestions ready for filming. Sounds are sourced from TikTok, Instagram Reels, and Facebook trends as of {{MONTH}} {{YEAR}}.

---

## Trending Sounds

### 1. {{SOUND_NAME}}

| Field | Details |
|-------|---------|
| **Artist** | {{ARTIST_NAME or "Original Sound"}} |
| **Platform** | {{TikTok / Instagram / Both}} |
| **Link** | {{URL}} |
| **Example Video** | [Watch the trend]({{EXAMPLE_VIDEO_URL}}) |
| **Vibe** | {{upbeat / emotional / funny / motivational}} |
| **Trending Usage** | {{1-2 sentence description}} |

#### Video Concept
{{1-2 sentence description of the video idea and realtor angle}}

#### Script

| Timing | What to Say/Do | On-Screen Text |
|--------|----------------|----------------|
| 0:00-0:03 | **HOOK:** {{Opening action or line}} | {{Text overlay for hook}} |
| 0:03-0:08 | {{Main content beat 1}} | {{Text overlay}} |
| 0:08-0:12 | {{Main content beat 2}} | {{Text overlay}} |
| 0:12-0:15 | **CTA:** {{Closing action or line}} | {{Text overlay for CTA}} |

#### Filming Notes
{{Any specific tips: location suggestions, props needed, or how to nail the timing}}

---

### 2. {{SOUND_NAME}}

| Field | Details |
|-------|---------|
| **Artist** | {{ARTIST_NAME or "Original Sound"}} |
| **Platform** | {{TikTok / Instagram / Both}} |
| **Link** | {{URL}} |
| **Example Video** | [Watch the trend]({{EXAMPLE_VIDEO_URL}}) |
| **Vibe** | {{upbeat / emotional / funny / motivational}} |
| **Trending Usage** | {{1-2 sentence description}} |

#### Video Concept
{{1-2 sentence description of the video idea and realtor angle}}

#### Script

| Timing | What to Say/Do | On-Screen Text |
|--------|----------------|----------------|
| 0:00-0:03 | **HOOK:** {{Opening action or line}} | {{Text overlay for hook}} |
| 0:03-0:08 | {{Main content beat 1}} | {{Text overlay}} |
| 0:08-0:12 | {{Main content beat 2}} | {{Text overlay}} |
| 0:12-0:15 | **CTA:** {{Closing action or line}} | {{Text overlay for CTA}} |

#### Filming Notes
{{Any specific tips: location suggestions, props needed, or how to nail the timing}}

---

[CONTINUE THIS EXACT FORMAT FOR SOUNDS 3-8]

---

## Quick Reference

| # | Sound | Vibe | Video Concept | Difficulty |
|---|-------|------|---------------|------------|
| 1 | {{SOUND_NAME}} | {{VIBE}} | {{One-line concept}} | {{Easy/Medium/Hard}} |
| 2 | {{SOUND_NAME}} | {{VIBE}} | {{One-line concept}} | {{Easy/Medium/Hard}} |
| 3 | {{SOUND_NAME}} | {{VIBE}} | {{One-line concept}} | {{Easy/Medium/Hard}} |
| 4 | {{SOUND_NAME}} | {{VIBE}} | {{One-line concept}} | {{Easy/Medium/Hard}} |
| 5 | {{SOUND_NAME}} | {{VIBE}} | {{One-line concept}} | {{Easy/Medium/Hard}} |
[Add rows 6-8 if applicable]

**Difficulty Key:** Easy = talking head or simple shots | Medium = multiple locations or transitions | Hard = precise timing or props required

---

## Pro Tips

**Timing & Trends:**
- Sounds trend for 1-3 weeks typically; act fast on production
- Save sounds to favorites immediately for later use
- Check sound usage count—sweet spot is trending but not oversaturated
- Some sounds are region-locked; test before planning content around them
- Remix/mashup versions sometimes perform better than originals

**Scripting & Filming:**
- **Watch the example videos** to understand timing, transitions, and format before filming
- Hook is everything—if the first 2 seconds don't grab attention, viewers scroll
- Speak faster than feels natural; short-form video rewards quick pacing
- Film multiple takes and pick the one with the best energy
- Record in good lighting (natural light near a window works great)

**On-Screen Text:**
- Add text even if you're talking—many viewers watch on mute
- Use contrasting colors so text is readable
- Reveal text in sync with audio beats for professional feel

**Links & Resources:**
- **Verify links before use**—sound and video URLs may change or become unavailable

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