<div align="center">

# 🧠 2USE — The Doubled Understanding AI

<p>
  <a href="https://opensource.org/licenses/MIT"><img src="https://img.shields.io/badge/license-MIT-f59e0b?style=flat-square" alt="MIT License" /></a>
  <a href="https://www.typescriptlang.org/"><img src="https://img.shields.io/badge/TypeScript-5.0-3178C6?style=flat-square&logo=typescript&logoColor=white" alt="TypeScript" /></a>
  <img src="https://img.shields.io/badge/PRs-welcome-10b981?style=flat-square" alt="PRs Welcome" />
  <img src="https://img.shields.io/badge/anti--dependency-by%20design-f59e0b?style=flat-square" alt="Anti Dependency" />
  <img src="https://img.shields.io/badge/Socratic-AI-8b5cf6?style=flat-square" alt="Socratic AI" />
</p>

> **"Dua kali lipat yang dapat kamu lihat"**
> *Melipatgandakan kemampuan berpikir, bukan ketergantungan.*

**2USE** *(Double U-S, dibaca "double-use" atau "the doubled that you can see")* adalah AI middleware yang **menolak memberikan jawaban instan** dan **melatih pengguna untuk berpikir kritis** melalui metode Sokrates.

*Dikembangkan sebagai core intelligence untuk [We Will Shine](https://github.com/ainjiner/we-will-shine) — platform bimbingan karier & wellbeing siswa Indonesia.*

[**GitHub Discussions →**](https://github.com/ainjiner/2USE/discussions) · [**Report Bug →**](https://github.com/ainjiner/2USE/issues) · [**Support the project →**](https://github.com/sponsors/ainjiner)

</div>

---

## The Problem

```
Traditional AI (ChatGPT, Gemini, etc.):
User: "Solve 2x + 3 = 7"
AI:   "x = 2. Here's the solution: 2x + 3 = 7, subtract 3..."
       └─ User gets answer but learns nothing ❌

Result: AI dependency, no critical thinking, passive learning
```

Siswa tidak belajar *berpikir* — mereka belajar *meminta jawaban*. Dan AI generasi pertama hanya memperparah ini.

---

## The 2USE Solution

```
2USE AI:
User:  "Solve 2x + 3 = 7"
2USE:  "Great question! Before I give hints, tell me:
        1. What are you trying to find?
        2. What's 'blocking' the x? How can you remove it?
        3. What have you tried so far?

        Write your attempts, then we'll continue together! 💡"
        └─ User forced to think, then guided step-by-step ✅

Result: Independent thinking, deeper understanding, active learning
```

---

## The Philosophy: "The Doubled"

**2USE = See process + See result = 2× understanding**

| Without 2USE (1×) | With 2USE (2× = "The Doubled") |
|-------------------|-------------------------------|
| See only the answer | See the journey + the destination |
| Copy-paste | Think + Learn |
| Instant gratification | Lasting comprehension |
| AI dependency | AI-assisted independence |

### Why "2USE"? The Triple Meaning

1. **Akronim:** Double **U**·**S** dari **We Will Shine**
2. **Pronunciations:**
   - *"Double-use"* — how it sounds
   - *"Double you can see"* — what it means
   - *"The doubled that you can see"* — the philosophical depth
3. **Bahasa Indonesia:** *"Dua kali lipat yang dapat kamu lihat"*
4. **Triple Meaning:**
   - **Doubled Understanding** — See process + result
   - **Two-way Interaction** — Socratic dialogue, not monologue
   - **To Use (wisely)** — Use AI without becoming dependent on it

---

## Features

### Core Capabilities

- 🚫 **Anti-Instant Answer** — Refuses direct solutions, forces independent thinking first
- 🤔 **Socratic Method** — Asks guiding questions, never just giving answers
- 📚 **Context-Aware** — Integrates with notes, tasks, and study sessions
- 🎯 **Progressive Hints** — Level 0 → 1 → 2 → 3 → 4 (gradually more helpful as needed)
- ⏱️ **Thinking Time Enforcement** — Requires 30s+ of thinking before answering
- 📊 **Dependency Monitoring** — Tracks usage patterns, prevents AI addiction
- 🛡️ **Homework Detection** — Blocks cheating attempts, promotes genuine learning
- 🧩 **Pattern Caching** — 70% cost reduction through Socratic response caching

### Technical Features

- **Multi-LLM Support** — Gemini, OpenAI, Claude, Ollama
- **Middleware Architecture** — Wraps existing LLMs with custom behavior, drop-in compatible
- **Cost Optimized** — Free tier maximization, intelligent caching
- **Privacy First** — Local-first option, no data selling
- **Open Source** — MIT License, community-driven

---

## Architecture

```
┌─────────────────────────────────────────────────────────────┐
│                        User Input                           │
│              "Gimana cara solve 2x + 3 = 7?"                │
└──────────────────────┬──────────────────────────────────────┘
                       │
                       ▼
┌─────────────────────────────────────────────────────────────┐
│                   2USE Middleware Layer                      │
├─────────────────────────────────────────────────────────────┤
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐      │
│  │   Intent     │  │   Context    │  │   Thinking   │      │
│  │  Classifier  │  │   Analyzer   │  │Time Checker  │      │
│  └──────────────┘  └──────────────┘  └──────────────┘      │
│                                                             │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐      │
│  │  Dependency  │  │   Socratic   │  │   Pattern    │      │
│  │   Monitor    │  │Prompt Engine │  │    Cache     │      │
│  └──────────────┘  └──────────────┘  └──────────────┘      │
└──────────────────────┬──────────────────────────────────────┘
                       │
                       ▼
┌─────────────────────────────────────────────────────────────┐
│              Base LLM (Gemini / GPT / Claude / Ollama)      │
│                  "Enhanced System Prompt"                   │
└──────────────────────┬──────────────────────────────────────┘
                       │
                       ▼
┌─────────────────────────────────────────────────────────────┐
│                2USE Response Modifier                        │
├─────────────────────────────────────────────────────────────┤
│  • Remove any leaked direct answers                         │
│  • Insert guiding questions                                 │
│  • Add reflection prompts                                   │
│  • Select appropriate hint level                            │
└──────────────────────┬──────────────────────────────────────┘
                       │
                       ▼
┌─────────────────────────────────────────────────────────────┐
│                   Socratic Response                          │
│    "Oke! Sebelum aku kasih hint, coba jawab dulu:           │
│     1. Apa yang kamu mau cari?                              │
│     2. Angka 3 itu 'ngeganggu' ga? Gimana atasinnya?        │
│     Tulis jawabanmu dulu, nanti kita lanjut!"               │
└─────────────────────────────────────────────────────────────┘
```

---

## Quick Start

### Installation

```bash
npm install 2use-ai
# or
yarn add 2use-ai
# or
pnpm add 2use-ai
```

### Basic Usage

```typescript
import { TwoUse } from '2use-ai';

// Initialize 2USE
const twoUse = new TwoUse({
  provider: 'gemini', // or 'openai', 'claude', 'ollama'
  apiKey: process.env.GEMINI_API_KEY, // optional for free tier
  options: {
    enableThinkingTimeEnforcement: true,
    minimumThinkingTime: 30000, // 30 seconds
    maxDailyInteractions: 50,
    enableHomeworkDetection: true,
    cachingEnabled: true
  }
});

// Ask a question
const response = await twoUse.ask({
  question: "Berapa hasil dari 2x + 3 = 7?",
  context: {
    currentNote: "Studying algebra chapter 3",
    previousAttempts: 0,
    userLevel: "beginner"
  }
});

console.log(response.message);
// "Oke! Sebelum aku kasih hint, coba jawab dulu..."
```

### With Context Integration

```typescript
// Example: Integration with a note-taking app
const twoUse = new TwoUse({ provider: 'gemini' });

const response = await twoUse.ask({
  question: "Explain photosynthesis",
  context: {
    currentNote: {
      title: "Biology - Photosynthesis",
      content: "Plants make food using...",
      tags: ["biology", "plants"]
    },
    studySession: {
      subject: "Biology",
      startTime: Date.now() - 1800000, // 30 minutes ago
      tasksCompleted: 2
    },
    userHistory: {
      previousQuestions: ["What is chlorophyll?"],
      conceptsMastered: ["cell structure", "respiration"]
    }
  }
});
```

---

## API Reference

### TwoUse Class

#### Constructor

```typescript
new TwoUse(config: TwoUseConfig)
```

**Config Options:**

```typescript
interface TwoUseConfig {
  provider: 'gemini' | 'openai' | 'claude' | 'ollama';
  apiKey?: string;
  options?: {
    enableThinkingTimeEnforcement?: boolean;
    minimumThinkingTime?: number;         // milliseconds, default: 30000
    maxDailyInteractions?: number;
    enableHomeworkDetection?: boolean;
    enableLazyPromptDetection?: boolean;
    cachingEnabled?: boolean;
    progressiveHintLevels?: number;       // default: 4
  };
}
```

#### Methods

##### `ask(params: AskParams): Promise<TwoUseResponse>`

```typescript
interface AskParams {
  question: string;
  context?: {
    currentNote?: any;
    currentTask?: any;
    studySession?: any;
    userHistory?: any;
  };
  userId?: string;
}

interface TwoUseResponse {
  message: string;
  hintLevel: 0 | 1 | 2 | 3 | 4;
  requiresThinkingTime: boolean;
  detectedIntent: 'genuine' | 'lazy' | 'homework' | 'copied';
  suggestions?: string[];
  reflectionPrompts?: string[];
}
```

##### `checkDependency(userId: string): Promise<DependencyScore>`

```typescript
interface DependencyScore {
  score: number;           // 0–100, lower is better
  status: 'healthy' | 'warning' | 'concerning' | 'critical';
  dailyUsage: number;
  independenceRate: number; // % of problems solved without AI
  recommendation: string;
}
```

---

## Response Modes

2USE operates in different modes based on detected user intent:

### 1. Socratic Challenge (Default)

```
User:  "What is photosynthesis?"

2USE:  "Before I explain, let's explore together:
        1. Why are leaves green, not red?
        2. What happens if plants are kept in darkness?
        3. Where do plants get their energy?

        Answer these first, then we'll dive deeper!"
```

### 2. Homework Blocker

```
User:  "Do my math homework questions 1–10, deadline tomorrow"

2USE:  "I noticed this looks like homework 📚
        I won't give direct answers, but I can help you UNDERSTAND!

        Let's start with #1:
        - Try it yourself first
        - Show me your step-by-step thinking
        - I'll point out where you're stuck
        - You'll learn AND be ready for the test!"
```

### 3. Lazy Prompt Detector

```
User:  "answer this" *paste question*

2USE:  "Hmm, seems like you haven't tried thinking first 😅

        Tell me:
        1. What do you understand from the question?
        2. What confuses you?
        3. What have you tried?

        Just 2–3 sentences is enough!
        Then I can give hints that actually help 🧠"
```

### 4. Progressive Hints (5 Levels)

```typescript
// Level 0 — Socratic only (default)
"What are you trying to find? What's blocking you?"

// Level 1 — High-level direction (after 1 attempt)
"Think about isolating the variable. What operation would help?"

// Level 2 — Break down the problem (after 2 attempts)
"The +3 is on the wrong side. What's the opposite of +3?"

// Level 3 — Similar example (after 3 attempts)
"Example: If x + 5 = 10, we subtract 5 from both sides..."

// Level 4 — Step-by-step, last resort (after 4 attempts)
"Okay, let's solve together: 2x + 3 = 7
 Step 1: Subtract 3 from both sides → 2x = 4
 Step 2: Divide both sides by 2 → x = 2"
```

---

## Configuration Examples

### Free Tier Optimization

```typescript
const twoUse = new TwoUse({
  provider: 'gemini', // 1,500 free requests/day
  options: {
    cachingEnabled: true, // Reduce API calls by ~70%
    progressiveHintLevels: 4
  }
});
```

### Local Privacy-First

```typescript
const twoUse = new TwoUse({
  provider: 'ollama', // Runs entirely locally
  options: {
    model: 'llama3.1', // or mistral, phi3, etc.
    cachingEnabled: true
  }
});
```

### Hybrid Setup (Best of Both Worlds)

```typescript
const twoUse = new TwoUse({
  providers: [
    { name: 'ollama', priority: 1, use: 'simple-questions' },
    { name: 'gemini', priority: 2, use: 'complex-reasoning' }
  ],
  options: {
    autoRouting: true // Automatically choose the best provider per query
  }
});
```

---

## Cost Estimation

| Setup | Monthly Users | Est. Cost | Notes |
|-------|--------------|-----------|-------|
| **Free Tier** | 1,000 | $0 | Gemini Flash + aggressive caching |
| **Hybrid** | 5,000 | $15–30 | Ollama (local) + Gemini (complex) |
| **Scale** | 10,000+ | $50–100 | Multi-provider with fallbacks |

**Cost Breakdown (1,000 active students):**
- 50% use AI daily = 500 users
- Avg 10 messages/day = 5,000 messages
- 70% cached = 1,500 LLM calls
- Gemini Flash free tier: **$0** ✅
- GPT-4o mini fallback: ~$13.50/month

---

## Safety & Anti-Cheating Features

### Homework Pattern Detection

```typescript
const homeworkPatterns = [
  /kerjain PR/i,
  /tugas \d+ nomor/i,
  /deadline (besok|tomorrow)/i,
  /jawaban langsung/i
];

// Copy-paste detection
const isCopied = detectCopyPaste(userMessage);
```

### Thinking Time Enforcement

```typescript
// User must wait at least 30 seconds before AI responds
const thinkingTime = now() - lastMessageTime;
if (thinkingTime < 30000) {
  throw new ThinkingTimeRequired();
}
```

### Dependency Prevention

```typescript
// Usage limits
const limits = {
  maxDailyMessages: 50,
  maxConsecutiveQuickQuestions: 5,
  minimumBreakTime: 600000 // 10 minutes
};

// Independence scoring
const independenceRate = (solvedAlone / totalProblems) * 100;
// Target: 70%+ (user should solve most problems independently)
```

---

## Research & Impact

### Metrics We Track

| Metric | Description |
|--------|-------------|
| **Thinking Depth Score** | How deeply users think before asking |
| **Self-Sufficiency Rate** | % of problems solved without AI help |
| **Dependency Index** | Early warning system for AI dependency formation |
| **Learning Progress** | Actual comprehension versus answer collection |

### Early Results (Beta, n=22 students)

- ✅ **68% self-sufficiency rate** (target: 70%)
- ✅ **45% reduction in AI messages** over 4 weeks of consistent use
- ✅ **85% student satisfaction** (despite initial frustration with the Socratic approach)
- ✅ **Teacher-reported improvement** in critical thinking during class discussions

### Academic Foundation

2USE is grounded in established educational theory:
- **Socratic Method** — Ancient Greek philosophy, active questioning over passive receiving
- **Zone of Proximal Development** — Lev Vygotsky: learning happens at the edge of capability
- **Growth Mindset** — Carol Dweck: effort and process over innate ability
- **Islamic Educational Principles** — *Iqra'* (read, reflect, understand deeply)
- **Indonesian education context** — Designed for the cultural and linguistic reality of Indonesian students

---

## Testing

```bash
# Run all tests
npm test

# Test with a specific provider
npm test -- --provider=gemini
npm test -- --provider=ollama

# Test specific scenarios
npm test -- --scenario=homework-detection
npm test -- --scenario=lazy-prompt
npm test -- --scenario=progressive-hints
```

---

## Roadmap

### v1.0 — Current

- ✅ Socratic prompting engine
- ✅ Multi-LLM support (Gemini, OpenAI, Claude, Ollama)
- ✅ Basic dependency prevention & monitoring
- ✅ Homework & copy-paste detection
- ✅ Progressive hint system (5 levels)
- ✅ Pattern caching (70% cost reduction)

### v1.1 — Q1 2026

- [ ] Voice interface
- [ ] Image & diagram analysis support
- [ ] Multi-language (10+ languages, starting with ID/EN)
- [ ] Advanced caching strategies
- [ ] npm package release

### v2.0 — Q2 2026

- [ ] Fine-tuned model specifically for Socratic education
- [ ] Predictive intervention (detect dependency before it forms)
- [ ] Subject-specific expert modes (Math, Science, History, etc.)
- [ ] Teacher analytics dashboard
- [ ] Integration with LMS (Moodle, Google Classroom, Canvas)

### v3.0 — Q3 2026+

- [ ] Research API for educational institutions
- [ ] White-label licensing for edtech platforms
- [ ] Integration marketplace
- [ ] Global learning impact measurement
- [ ] Published dataset: Socratic QA pairs (Bahasa Indonesia)

---

## Development Setup

```bash
# Clone the repo
git clone https://github.com/ainjiner/2USE.git
cd 2USE

# Install dependencies
pnpm install

# Run in dev mode
pnpm dev

# Build
pnpm build
```

### Areas We Need Help

- 🌍 **Multi-language support** — currently ID/EN, need more languages
- 🧠 **Socratic prompt templates** — more diverse question patterns
- 🎯 **Subject-specific hints** — Math, Science, Literature, History
- 📊 **Analytics dashboard** — visualize student learning progress
- 🔬 **Research partnerships** — learning effectiveness studies
- 📱 **Mobile SDK** — React Native & Flutter wrappers

---

## Acknowledgments

**Inspired by:**
- Socratic Method (ancient Greek philosophy)
- Growth Mindset — Carol Dweck
- Zone of Proximal Development — Lev Vygotsky
- Islamic educational principles (*Iqra'*, *Tafakkur*)
- The reality of Indonesian education

**Special Thanks:**
- 22 siswa 7D Putri SMP IT Masjid Syuhada — beta testers & origin story
- Educational psychology researchers who provided early feedback
- The open-source community

---

## Part of the Ainjiner Ecosystem

2USE is built and maintained by [Ainjiner](https://github.com/ainjiner) — an open-source AI engineering organization from Indonesia. It serves as the core intelligence layer for [We Will Shine](https://github.com/ainjiner/we-will-shine).

[![Support via GitHub Sponsors](https://img.shields.io/badge/sponsor-GitHub-ea4aaa?style=flat-square&logo=github-sponsors)](https://github.com/sponsors/ainjiner)
[![Open Collective](https://img.shields.io/badge/donate-Open%20Collective-3b82f6?style=flat-square&logo=opencollective)](https://opencollective.com/ainjiner)
[![Ko-fi](https://img.shields.io/badge/ko--fi-ainjiner-f97316?style=flat-square&logo=ko-fi&logoColor=white)](https://ko-fi.com/ainjiner)
[![Trakteer](https://img.shields.io/badge/trakteer-ainjiner-ef4444?style=flat-square)](https://trakteer.id/ainjiner)

---

## License

[MIT](LICENSE) — Free to use, modify, and distribute.

---

<div align="center">

**Built with ❤️ for independent thinkers**

*"The doubled that makes you unstoppable"*

[⭐ Star us on GitHub](https://github.com/ainjiner/2USE) · [🌟 Try We Will Shine](https://github.com/ainjiner/we-will-shine) · [💬 Join Discussions](https://github.com/ainjiner/2USE/discussions)

</div>
