# Universal CLAUDE.md - Engineering Edition

> A battle-tested CLAUDE.md optimized for software engineers. More practical, more specific, more useful than the trending version.

[![Awesome](https://awesome.re/badge.svg)](https://github.com/forrestchang/andrej-karpathy-skills)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## 🎯 Why This Exists

The trending [andrej-karpathy-skills](https://github.com/forrestchang/andrej-karpathy-skills) CLAUDE.md is great for AI/ML research, but **software engineers need different guidance**:

- We deal with error handling, not tensor operations
- We need code review checklists, not just teaching philosophies
- We want severity markers (🔴🟡🟢), not vague "be clear" suggestions

This version fills that gap.

## 🚀 Quick Start

```bash
# 1. Copy to your project
curl -O https://raw.githubusercontent.com/acrusher2026/Agentic-Engineering-claude/main/CLAUDE.md

# 2. Run Claude Code
claude

# 3. Claude automatically adopts this persona
```

Or manually paste the content into Claude.ai Project Instructions.

## ✨ Key Improvements

| Feature | Original | This Version |
|---------|----------|--------------|
| **Target** | AI/ML researchers | Software engineers |
| **Language** | Python-centric | Language-agnostic |
| **Code Review** | ❌ No checklist | ✅ 8-point auto-checklist |
| **Response Format** | Teaching style | 3 concrete templates |
| **Severity Levels** | ❌ None | 🔴🟡🟢 Marked issues |
| **Debugging** | ❌ Not covered | ✅ 5-step protocol |
| **Anti-patterns** | ❌ Not listed | ✅ 8 common traps |

## 📋 What's Inside

### Core Philosophy
- **First Principles**: Break down to fundamentals, build up
- **Occam's Razor**: Simplest working solution is best
- **Explicit > Implicit**: Code should be obvious

### Engineering Principles
```
Quality Hierarchy:
1. Correctness (handles all cases)
2. Clarity (intent is obvious)
3. Conciseness (no boilerplate)
4. Performance (only when needed)
```

### Response Templates

#### 1. Concept Explanation
```
One-sentence summary → Intuition → Example → Edge cases → Related concepts
```

#### 2. Code Review
```
Overall assessment → Line-by-line issues (🔴🟡🟢) → Fixed version → Key takeaways
```

#### 3. Design Comparison
```
Options → Trade-off matrix → Recommendation → Migration path
```

## 🎯 Real Examples

### Example 1: Code Review

**Your question**: "Is this Go code good?"
```go
func Process() error {
    data, _ := fetchData()
    return processData(data)
}
```

**Claude's response** (with this CLAUDE.md):

> 🔴 **Critical** (Line 3): Error ignored with `_`
>
> This silently fails. You won't know if it's a network timeout, auth failure, or data corruption.
>
> **Fixed version**:
> ```go
> func Process() error {
>     data, err := fetchData()
>     if err != nil {
>         return fmt.Errorf("fetching data: %w", err)
>     }
>     return processData(data)
> }
> ```
>
> **Key takeaway**: Never ignore errors in Go. If truly unnecessary, explicitly comment why.

### Example 2: Concept Explanation

**Your question**: "Explain mutex"

> **Mutex** is a tool that ensures only one goroutine accesses a resource at a time.
>
> **Intuition**: Like a bathroom key - only one person holds it, others wait in line.
>
> **Example**:
> ```go
> var mu sync.Mutex
> var counter int
> 
> func Increment() {
>     mu.Lock()
>     counter++
>     mu.Unlock()
> }
> ```
>
> **When to use**: Shared state that needs atomic updates
> **When NOT to use**: Can use channels for ownership transfer, atomic for simple counters
>
> **Related**: RWMutex (read-heavy), sync/atomic (simple ops), channels (ownership)

## 🔧 Language Support

Optimized for all mainstream languages:
- Go
- Python
- TypeScript / JavaScript
- Rust
- Java
- C/C++

## 📊 Code Review Checklist (Auto-applied)

When reviewing your code, Claude automatically checks:

- [ ] **Correctness**: All edge cases handled? Input validated?
- [ ] **Errors**: Every error checked? Context added?
- [ ] **Concurrency**: Race conditions? Deadlocks? Leaks?
- [ ] **Resources**: Files closed? Connections released?
- [ ] **Testing**: Happy path + error paths covered?
- [ ] **Documentation**: Public APIs documented?
- [ ] **Naming**: Intent-revealing names?
- [ ] **Dependencies**: Minimal and necessary?

## 🚫 Anti-patterns Flagged

| Severity | Pattern | Why It's Bad |
|----------|---------|--------------|
| 🔴 | `_, _ = fn()` | Silent failures |
| 🔴 | Return nil on error | Hides problems |
| 🟡 | String concat in loops | O(n²) performance |
| 🟡 | Overly clever one-liners | Hard to maintain |
| 🟡 | Premature abstraction | Unnecessary complexity |
| 🟢 | Inconsistent naming | Confusing |
| 🟢 | Missing doc comments | Poor DX |

## 🐛 Debugging Protocol

When helping debug, Claude follows:

1. **Reproduce** - Make it fail consistently
2. **Isolate** - Binary search through code
3. **Hypothesize** - Form theory about cause
4. **Verify** - Test the theory
5. **Fix & Understand** - Solve + prevent recurrence

## 💡 Pro Tips

- Place `CLAUDE.md` in project root → Claude Code auto-loads it
- For Claude.ai web: Paste into Project Instructions
- Works with any IDE extension supporting Claude

## 📄 File Structure

```
.
├── CLAUDE.md          # Main configuration
├── README.md          # This file
└── examples/          # (Optional) Example conversations
    ├── code-review.md
    └── debugging.md
```

## 🤝 Contributing

This is a starting point. Adapt it to your team's needs:

- Add your specific tech stack conventions
- Include your company's coding standards
- Modify checklists for your domain

## 📜 License

MIT - Use it, fork it, improve it.

## 🙏 Credits

Inspired by [andrej-karpathy-skills](https://github.com/forrestchang/andrej-karpathy-skills) but rebuilt for general software engineering.

---

**Star this repo if it helps you write better code!** ⭐
