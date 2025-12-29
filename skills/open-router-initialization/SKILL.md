# OpenRouter Setup Skill

Set up OpenRouter in this project using the OpenAI SDK integration.

## Workflow

### Step 1: Detect Project Runtime

Check the project to determine the runtime:

- **Node.js/TypeScript**: Look for `package.json`
- **Python**: Look for `pyproject.toml`, `requirements.txt`, or `.py` files

If both exist or neither exist, ask the user which runtime they want to configure.

---

### Step 2: Install Dependencies

**Node.js/TypeScript:**
```bash
npm install openai
# or
yarn add openai
# or
pnpm add openai
```

**Python:**
```bash
pip install openai
# or
uv add openai
# or
poetry add openai
```

---

### Step 3: Environment Setup

1. **Check `.gitignore`** — Ensure `.env` is listed. If not, add it:
   ```
   .env
   .env.local
   .env*.local
   ```

2. **Create `.env`** — Copy from `.envexample` in this skill folder, or create with:
   ```env
   # OpenRouter API Configuration
   # Get your key at: https://openrouter.ai/settings/keys
   OPENROUTER_API_KEY=sk-or-v1-your-key-here

   # Optional: For OpenRouter leaderboard attribution
   YOUR_SITE_URL=http://localhost:3000
   YOUR_SITE_NAME=My App
   ```

3. **Remind the user** to replace the placeholder with their real API key from https://openrouter.ai/settings/keys

---

### Step 4: Initialize the Client

Create an OpenRouter client file with the appropriate code:

**Node.js/TypeScript (`lib/openrouter.ts` or `src/openrouter.ts`):**
```typescript
import OpenAI from 'openai';

export const openrouter = new OpenAI({
  baseURL: 'https://openrouter.ai/api/v1',
  apiKey: process.env.OPENROUTER_API_KEY,
  defaultHeaders: {
    'HTTP-Referer': process.env.YOUR_SITE_URL || '',
    'X-Title': process.env.YOUR_SITE_NAME || '',
  },
});

// Smoke test function
export async function testOpenRouter() {
  const completion = await openrouter.chat.completions.create({
    model: 'google/gemini-2.5-flash',
    messages: [{ role: 'user', content: 'Say "OpenRouter is working!" and nothing else.' }],
  });
  return completion.choices[0].message.content;
}
```

**Python (`openrouter_client.py` or `lib/openrouter.py`):**
```python
import os
from openai import OpenAI

openrouter = OpenAI(
    base_url="https://openrouter.ai/api/v1",
    api_key=os.getenv("OPENROUTER_API_KEY"),
)

def test_openrouter():
    """Smoke test to verify OpenRouter is configured correctly."""
    completion = openrouter.chat.completions.create(
        model="google/gemini-2.5-flash",
        messages=[{"role": "user", "content": 'Say "OpenRouter is working!" and nothing else.'}],
        extra_headers={
            "HTTP-Referer": os.getenv("YOUR_SITE_URL", ""),
            "X-Title": os.getenv("YOUR_SITE_NAME", ""),
        },
    )
    return completion.choices[0].message.content

if __name__ == "__main__":
    print(test_openrouter())
```

---

### Step 5: Run Smoke Test

Execute the smoke test to verify everything works:

**Node.js/TypeScript:**
```bash
npx tsx lib/openrouter.ts
# or add a test script and run: npm run test:openrouter
```

**Python:**
```bash
python openrouter_client.py
```

Expected output: `OpenRouter is working!`

---

## OpenRouter Headers

These optional headers help with attribution on OpenRouter leaderboards:

| Header | Description | Example |
|--------|-------------|---------|
| `HTTP-Referer` | Your site URL | `https://myapp.com` |
| `X-Title` | Your app name | `My AI App` |

---

## Model Naming Convention

OpenRouter uses the format: `provider/model-name`

### Step 6: Provide Model List

Read `models.json` from this skill folder. It contains a structured list of top models organized by provider, with metadata including:
- `id`: The model ID to use in API calls (format: `provider/model-name`)
- `name`: Human-readable name
- `tier`: Category (flagship, balanced, fast, reasoning, code, search)
- `note`: Optional additional info

Copy `models.json` to the project if the user needs programmatic access to the model list.

**Top models (December 2025):**
| Model ID | Tier | Description |
|----------|------|-------------|
| `google/gemini-2.5-flash` | fast | Most popular - fast & cheap |
| `google/gemini-2.5-pro-preview` | flagship | Most capable Gemini |
| `anthropic/claude-opus-4.5` | flagship | Most capable Claude |
| `anthropic/claude-sonnet-4.5` | balanced | Balanced Claude |
| `openai/gpt-5` | flagship | Latest GPT |
| `openai/o3` | reasoning | Reasoning model |
| `deepseek/deepseek-r1` | reasoning | Strong reasoning model |
| `meta-llama/llama-4-maverick` | flagship | Open-source |

See `models.json` in this skill folder for the complete structured list.

Browse all models at: https://openrouter.ai/models
Rankings: https://openrouter.ai/rankings

---

## Troubleshooting

| Error | Cause | Solution |
|-------|-------|----------|
| `401 Unauthorized` | Invalid API key | Check `OPENROUTER_API_KEY` is set correctly |
| `402 Payment Required` | Insufficient credits | Add credits at https://openrouter.ai/credits |
| `429 Too Many Requests` | Rate limited | Wait and retry, or upgrade plan |
| `Model not found` | Invalid model ID | Check model format: `provider/model-name` |
| `Connection refused` | Network issue | Check internet connection and firewall |

---

## Quick Reference

**Base URL:** `https://openrouter.ai/api/v1`

**Environment Variables:**
- `OPENROUTER_API_KEY` — Required
- `YOUR_SITE_URL` — Optional (for attribution)
- `YOUR_SITE_NAME` — Optional (for attribution)

**Get API Key:** https://openrouter.ai/settings/keys

**Documentation:** https://openrouter.ai/docs
