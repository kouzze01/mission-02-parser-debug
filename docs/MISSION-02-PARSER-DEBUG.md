# MISSION-02: Parser Bug Hunt

> **Level Up with AI** - Squad Team Challenge
> **Difficulty**: Intermediate
> **Time Target**: 15-30 minutes
> **Skills**: Debugging, Binary Search, YAML, Claude Code

---

## The Bug

You updated Claude Code and now it crashes when you type `/` followed by any character:

```
TypeError: $.description.split is not a function
```

Your `~/.claude/skills/` folder has 8 skill files. **4 of them are broken.**

Find them. Fix them. Document your methodology.

---

## Setup

```bash
# Clone the challenge
gh repo clone Soul-Brews-Studio/squad-parser-challenge
cd squad-parser-challenge

# Copy challenge skills to your Claude skills folder
cp -r challenge-skills/* ~/.claude/skills/

# Restart Claude Code (or open new terminal)
# Try typing "/" - it should crash
```

---

## Your Mission

1. **Reproduce** the crash (type `/` in Claude Code)
2. **Find** which 4 files cause the crash
3. **Fix** the files so Claude Code works again
4. **Document** your debugging approach

---

## Rules

- You **CANNOT** read this README during debugging (close it first)
- You **CANNOT** use grep to search for the answer
- You **MUST** use systematic debugging (not random guessing)
- You **MUST** document each step you take
- **TIME YOURSELF** - binary search should take ~10 minutes

---

## Hints (Use Only If Stuck)

<details>
<summary>Hint 1: Isolation Strategy</summary>

Don't fix files one by one. Remove ALL files first, confirm Claude works, then add back in batches.

</details>

<details>
<summary>Hint 2: The Parser</summary>

The error mentions "split" - a string method. What if the parser expects a string but gets something else?

</details>

<details>
<summary>Hint 3: YAML Syntax</summary>

YAML has special syntax for arrays: `[item1, item2]`. What happens if this appears where a string is expected?

</details>

---

## Submission

Create a GitHub issue with:

1. **Which 4 files were broken** (file paths)
2. **What was wrong** (the bug pattern)
3. **Your debugging steps** (timeline with timestamps)
4. **Time to solve** (from first crash to all fixed)

### Submission Format

```markdown
## MISSION-02 Submission

**Time to solve**: XX minutes

### Broken Files Found

1. `path/to/file1.md` - description of bug
2. `path/to/file2.md` - description of bug
3. `path/to/file3.md` - description of bug
4. `path/to/file4.md` - description of bug

### Root Cause

[Explain what causes the crash]

### Debugging Steps

| Time | Action | Result |
|------|--------|--------|
| 0:00 | [First action] | [What happened] |
| 0:XX | [Next action] | [What happened] |
| ... | ... | ... |

### Methodology

[What debugging approach did you use?]
```

---

## Scoring (by Oracle)

| Criteria | Points | Notes |
|----------|--------|-------|
| Found all 4 files | 40 | 10 points each |
| Correct root cause | 20 | Must explain WHY |
| Documented steps | 20 | Timeline required |
| Used binary search | 10 | Systematic approach |
| Time under 15 min | 10 | Bonus for speed |
| **Total** | **100** | |

---

## After Completing

**REQUIRED**: Write a blog post about your experience

- Platform: [Medium Soul Brews Studio Hub](https://medium.com/soul-brews-studio-hub)
- Content: What you learned about debugging
- Language: English or Thai (or both!)

> "เรียนฟรี แต่ช่วยกันส่งต่อความรู้"
> (Learn free, but help pass on knowledge)

---

## Why This Matters

This bug was **real**. We found it on 2026-01-08 while working on Claude Code.

The debugging methodology you learn here:
- **Isolation first** - Don't patch symptoms, isolate the problem
- **Binary search** - Cut the search space in half each time
- **Document as you go** - Future you will thank present you

These skills apply to ANY debugging, not just Claude Code.

---

## Related

- [MISSION-01: Voice Integration](https://github.com/Soul-Brews-Studio/oracle-voice-tray/issues/1)
- [Claude Code Issue #16754](https://github.com/anthropics/claude-code/issues/16754) (the real bug report)

---

*Created by Soul Brews Studio | Level Up with AI Program*
