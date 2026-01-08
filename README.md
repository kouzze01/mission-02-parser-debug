---
name: squad-challenge
description: Squad team debugging challenge - find the parser bug
---

# MISSION-02: Parser Bug Hunt

> **Level Up with AI** - Squad Team Challenge
> **Difficulty**: Intermediate | **Time Target**: 15-30 min

See [docs/MISSION-02-PARSER-DEBUG.md](docs/MISSION-02-PARSER-DEBUG.md) for full instructions.

## The Bug

Claude Code crashes with this error when typing `/` + characters:

```
TypeError: $.description.split is not a function
```

## Your Mission

1. **Reproduce** the bug in a test environment
2. **Find** the culprit file(s)
3. **Fix** the issue
4. **Document** your debugging methodology

## Setup

```bash
# Copy challenge files to ~/.claude/skills/
cp -r challenge-skills/* ~/.claude/skills/

# Restart Claude Code
# Type /he and watch it crash
```

## Challenge Structure

```
challenge-skills/
├── skill-alpha/
│   ├── SKILL.md
│   └── references/
│       └── api.md
├── skill-beta/
│   ├── SKILL.md
│   └── operations/
│       ├── workflow.md
│       └── helpers.md
├── skill-gamma/
│   └── SKILL.md
└── skill-delta/
    ├── SKILL.md
    └── examples/
        └── usage.md
```

**8 files total. 4 are broken. Find them.**

## Rules

1. You may NOT read this README after starting
2. Use systematic debugging (not random guessing)
3. Document each step you take
4. Time yourself

## Success Criteria

- [ ] Error no longer occurs
- [ ] All files properly fixed
- [ ] Documented debugging methodology
- [ ] Explained ROOT CAUSE (not just "fixed it")

## Hints (open only if stuck > 15 min)

<details>
<summary>Hint 1: Isolation</summary>
Try removing ALL files first, then add back in batches.
</details>

<details>
<summary>Hint 2: YAML</summary>
The bug is related to YAML parsing, not missing files.
</details>

<details>
<summary>Hint 3: Data Type</summary>
What happens when YAML sees `[something]`?
</details>

## After Completion

1. Write a retrospective
2. Share your debugging methodology
3. Compare time: Our team found it in ~10 minutes using binary search

---

## Submission

Create a GitHub issue in this repo with:
1. Which 4 files were broken
2. What was wrong (root cause)
3. Your debugging steps (with timestamps)
4. Time to solve

**Scoring**: Oracle will grade your submission (100 points max)

**Blog Requirement**: After completing, write about your experience on [Medium Soul Brews Studio Hub](https://medium.com/soul-brews-studio-hub)

> "เรียนฟรี แต่ช่วยกันส่งต่อความรู้"
> (Learn free, but help pass on knowledge)

---

**Created by**: Soul Brews Studio | Level Up with AI Program
**Bug source**: Real production bug from 2026-01-08
**Issue**: https://github.com/anthropics/claude-code/issues/16754
**Related**: [MISSION-01: Voice Integration](https://github.com/Soul-Brews-Studio/oracle-voice-tray/issues/1)
