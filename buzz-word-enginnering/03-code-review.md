# Code Review Tactics

## The Core Principle

A code review is not about reading the code. It is about leaving evidence that you could have read the code.

Your review must look thorough. It does not need to be thorough.

---

## The Fast Scan Protocol

Spend exactly 45 seconds on the PR. In that time, collect:

1. **One thing that looks long** — any function over ~20 lines
2. **One import you don't recognize** — there's always one
3. **One variable name you mildly dislike** — subjective, unchallengeable
4. **The absence of a test** — there's always a case not covered

These four observations will generate 4 comments. That's a thorough review.

---

## Comment Templates

Copy-paste from these. Customize only the noun.

### The Naming Comment (always safe)
```
Nit: `userData` could be more descriptive — something like
`authenticatedUserProfile` might better capture the intent here.
Up to you, happy either way.
```

### The Abstraction Comment (sounds architectural)
```
Thinking out loud: could this logic be extracted into a separate
helper? Might make it easier to test in isolation. Not blocking,
just something to consider.
```

### The Test Coverage Comment (always applicable)
```
Do we have coverage for the case where [thing] is null/empty/undefined?
Happy to be wrong if I missed it somewhere.
```

### The Performance Comment (requires zero knowledge)
```
Curious if this could be a concern at scale — any idea what the
expected call frequency looks like? Might be fine, just want to
make sure we've thought through it.
```

### The Documentation Comment (always missing)
```
Worth adding a comment here explaining the why behind this approach?
Future us will thank us.
```

### The "Looks Good But" Comment (for approving with cover)
```
LGTM overall — left a few minor nits but nothing blocking. Nice work.
```

---

## Severity Calibration

Never say something is wrong. Use this scale:

| Severity | Language |
|---|---|
| Must fix | "Thinking we might want to..." |
| Should fix | "Nit:" |
| Could fix | "Out of curiosity..." |
| Don't care | "Not blocking, just..." |
| Actually wrong | "Happy to be wrong but..." |

This ensures that if the author ignores you, it was just a nit.
If they fix it, you caught a bug.

---

## The Approval Strategy

### Scenario A: Small PR, looks fine
Approve immediately with: `LGTM! Nice clean change.`
This builds social credit for future large PRs you won't read.

### Scenario B: Large PR, looks scary
Leave 3-4 nit comments on the first file. Approve.
You have "reviewed" it. The comments prove it.

### Scenario C: PR from someone senior to you
```
"Learned something new reading this — the [thing] pattern is clever.
Left one small question inline but nothing blocking. LGTM."
```
One question. Approve. Never explain what you learned.

### Scenario D: PR that is genuinely broken
This happens rarely, but when it does, you must be decisive:
```
"Flagging a potential issue in [file] — want to make sure I'm
reading this right before approving. Can we sync quickly?"
```
Do not write what the issue is in the comment. Discuss verbally.
This way, if you're wrong, there's no written evidence.

---

## Review Timing

- **Too fast** (< 2 minutes): Looks like you didn't read it
- **Too slow** (> 2 days): You become a blocker, people ping you
- **Optimal window**: 2-4 hours after the PR was opened

Set a reminder. Do not actually spend 2-4 hours on it.
