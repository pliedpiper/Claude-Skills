---
name: handoff
description: Summarize all work done in the current session and write it to handoff.md. Use when context is getting full, ending a session, or passing work to another Claude instance. Triggers on "handoff", "summarize session", "document progress".
---

# Handoff

Create a comprehensive summary of all work completed in the current session and save it to `handoff.md`. This enables continuity when context gets full or when passing the project to a new Claude instance.

## Trigger

- User says "handoff", "/handoff", "create handoff", or "summarize session"
- User indicates context is getting full
- User wants to document what was done before ending a session
- User wants to pass the project to another Claude instance

## Workflow

### Step 1: Gather Session Context

Review the entire conversation to identify:

1. **Tasks Completed**
   - What was the user's original request?
   - What sub-tasks were identified and completed?
   - What files were created, modified, or deleted?

2. **Key Decisions Made**
   - Architecture or design choices
   - Technology/library selections
   - Trade-offs that were discussed and resolved
   - User preferences that were established

3. **Current State**
   - What is working now?
   - What was left incomplete or in progress?
   - Any known issues or bugs discovered?

4. **Files Changed**
   - List all files that were created or modified
   - Note significant changes in each file

5. **Context for Continuation**
   - What would the next Claude instance need to know?
   - Any gotchas or non-obvious details?
   - Relevant file paths and project structure insights

### Step 2: Check for Existing handoff.md

Look for an existing `handoff.md` in the project root:
- If it exists, read it to understand previous sessions
- New session entries will be prepended (newest first)

### Step 3: Write the Handoff Document

Create or update `handoff.md` in the project root directory.

**File Location:** Always save to the project root as `handoff.md`

**Template:**

```markdown
# Project Handoff

This document tracks work sessions to maintain continuity across Claude instances.

---

## Session: {{DATE}} {{TIME}}

### Summary
{{1-3 sentence overview of what was accomplished this session}}

### Tasks Completed
{{Bulleted list of completed tasks}}

### Files Changed
| File | Change Type | Description |
|------|-------------|-------------|
| {{path/to/file}} | {{created/modified/deleted}} | {{brief description}} |

### Key Decisions
{{Bulleted list of important decisions made and why}}

### Current State
{{Description of where the project stands now}}

### In Progress / Next Steps
{{What was left incomplete or what should be done next}}

### Notes for Next Session
{{Any context, gotchas, or details the next Claude instance should know}}

---

[Previous sessions below if they exist]
```

### Step 4: Format Guidelines

- **Date format:** YYYY-MM-DD
- **Time format:** HH:MM (24-hour, local time if available)
- **Be concise but complete** - another Claude instance should be able to pick up exactly where you left off
- **Include file paths** - use relative paths from project root
- **Preserve previous sessions** - don't overwrite, prepend new session above old ones
- **Focus on actionable context** - skip trivial details, emphasize what matters for continuation

### Step 5: Confirm with User

After writing the handoff document:
1. Confirm the file was saved successfully
2. Provide a brief summary of what was documented
3. Mention any in-progress items the user should be aware of

## Example Output

```markdown
# Project Handoff

This document tracks work sessions to maintain continuity across Claude instances.

---

## Session: 2025-12-31 14:30

### Summary
Implemented user authentication system with JWT tokens and added login/logout endpoints to the API.

### Tasks Completed
- Created User model with password hashing
- Implemented JWT token generation and validation
- Added `/auth/login` and `/auth/logout` endpoints
- Created auth middleware for protected routes
- Added unit tests for auth functions

### Files Changed
| File | Change Type | Description |
|------|-------------|-------------|
| src/models/user.ts | created | User model with bcrypt password hashing |
| src/middleware/auth.ts | created | JWT validation middleware |
| src/routes/auth.ts | created | Login/logout route handlers |
| src/utils/jwt.ts | created | Token generation utilities |
| tests/auth.test.ts | created | Auth unit tests (12 tests, all passing) |
| src/app.ts | modified | Added auth routes to Express app |

### Key Decisions
- Chose JWT over sessions for stateless authentication
- Set token expiry to 24 hours based on user preference
- Stored refresh tokens in httpOnly cookies for security

### Current State
Authentication is fully functional. All tests passing. Ready for integration with frontend.

### In Progress / Next Steps
- Frontend login form needs to be connected to these endpoints
- Consider adding password reset functionality
- Rate limiting on auth endpoints not yet implemented

### Notes for Next Session
- The JWT_SECRET is in .env (not committed) - user has it locally
- User prefers using zod for validation (not yet added to auth routes)
- Project uses pnpm, not npm

---
```

## Notes

- Always check if handoff.md exists before writing to avoid losing previous session history
- Keep entries focused on what's needed for continuity, not a play-by-play
- If the session was simple (e.g., answered a question, fixed a typo), the handoff can be brief
- Include error messages or stack traces if they're relevant to ongoing debugging
