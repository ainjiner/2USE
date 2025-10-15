# 🧠 2USE - The Doubled Understanding AI

> **"Dua kali lipat yang dapat kamu lihat"** - Melipatgandakan kemampuan berpikir, bukan ketergantungan

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.0-blue.svg)](https://www.typescriptlang.org/)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](http://makeapullrequest.com)

**2USE** (Double U-S, dibaca "double-use" atau "the doubled that you can see") adalah custom AI middleware yang **menolak memberikan jawaban instan** dan **melatih pengguna untuk berpikir kritis** melalui metode Socratic.

Dikembangkan sebagai core intelligence untuk [We Will Shine](https://github.com/sandikodev/we-will-shine) - aplikasi produktivitas belajar dengan UI stoik.

---

## 🎯 What is 2USE?

### **The Problem:**

```
Traditional AI (ChatGPT, Gemini, etc.):
User: "Solve 2x + 3 = 7"
AI: "x = 2. Here's the solution: 2x + 3 = 7, subtract 3..."
└─ User gets answer but learns nothing ❌

Result: AI dependency, no critical thinking, passive learning
```

### **The 2USE Solution:**

```
2USE AI:
User: "Solve 2x + 3 = 7"
2USE: "Great question! Before I give hints, tell me:
      1. What are you trying to find?
      2. What's 'blocking' the x? How can you remove it?
      3. What have you tried so far?
      
      Write your attempts, then we'll continue together! 💡"
└─ User forced to think, then guided step-by-step ✅

Result: Independent thinking, deeper understanding, active learning
```

### **The Philosophy: "The Doubled"**

**2USE = See process + See result = 2x understanding**

| Without 2USE (1x) | With 2USE (2x = "The Doubled") |
|-------------------|--------------------------------|
| See only answer | See journey + destination |
| Copy-paste | Think + Learn |
| Instant gratification | Lasting comprehension |
| AI dependency | AI-assisted independence |

---

## ✨ Features

### **Core Capabilities:**

- 🚫 **Anti-Instant Answer** - Refuses direct solutions, forces thinking
- 🤔 **Socratic Method** - Asks guiding questions, not giving answers
- 📚 **Context-Aware** - Integrates with notes, tasks, study sessions
- 🎯 **Progressive Hints** - Level 1 → 2 → 3 → 4 (gradually more helpful)
- ⏱️ **Thinking Time Enforcement** - Requires 30s+ of thinking before answering
- 📊 **Dependency Monitoring** - Tracks usage patterns, prevents addiction
- 🛡️ **Homework Detection** - Blocks cheating attempts, promotes learning
- 🧩 **Pattern Caching** - 70% cost reduction through Socratic response caching

### **Technical Features:**

- **Multi-LLM Support** - Gemini, OpenAI, Claude, Ollama
- **Middleware Architecture** - Wraps existing LLMs with custom behavior
- **Cost Optimized** - Free tier maximization, intelligent caching
- **Privacy First** - Local-first option, no data selling
- **Open Source** - MIT License, community-driven

---

## 🏗️ Architecture

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
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐     │
│  │   Intent     │  │   Context    │  │   Thinking   │     │
│  │  Classifier  │  │   Analyzer   │  │Time Checker  │     │
│  └──────────────┘  └──────────────┘  └──────────────┘     │
│                                                              │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐     │
│  │  Dependency  │  │   Socratic   │  │   Pattern    │     │
│  │   Monitor    │  │Prompt Engine │  │    Cache     │     │
│  └──────────────┘  └──────────────┘  └──────────────┘     │
└──────────────────────┬──────────────────────────────────────┘
                       │
                       ▼
┌─────────────────────────────────────────────────────────────┐
│              Base LLM (Gemini/GPT/Claude/Ollama)            │
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
│    "Oke! Sebelum aku kasih hint, coba jawab dulu:          │
│     1. Apa yang kamu mau cari?                              │
│     2. Angka 3 itu 'ngeganggu' ga? Gimana atasinnya?        │
│     Tulis jawabanmu dulu, nanti kita lanjut!"               │
└─────────────────────────────────────────────────────────────┘
```

---

## 🚀 Quick Start

### **Installation**

```bash
npm install 2use-ai
# or
yarn add 2use-ai
# or
pnpm add 2use-ai
```

### **Basic Usage**

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

### **With Context Integration**

```typescript
// Example: Integration with note-taking app
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

## 📖 API Reference

### **TwoUse Class**

#### **Constructor**

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
    minimumThinkingTime?: number; // milliseconds
    maxDailyInteractions?: number;
    enableHomeworkDetection?: boolean;
    enableLazyPromptDetection?: boolean;
    cachingEnabled?: boolean;
    progressiveHintLevels?: number;
  };
}
```

#### **Methods**

##### **ask(params: AskParams): Promise<TwoUseResponse>**

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

##### **checkDependency(userId: string): Promise<DependencyScore>**

```typescript
interface DependencyScore {
  score: number; // 0-100, lower is better
  status: 'healthy' | 'warning' | 'concerning' | 'critical';
  dailyUsage: number;
  independenceRate: number; // % of problems solved without AI
  recommendation: string;
}
```

---

## 🎨 Response Modes

2USE operates in different modes based on user intent:

### **1. Socratic Challenge (Default)**

```typescript
User: "What is photosynthesis?"

2USE Response:
"Before I explain, let's explore together:
1. Why are leaves green, not red?
2. What happens if plants are kept in darkness?
3. Where do plants get their energy?

Answer these first, then we'll dive deeper!"
```

### **2. Homework Blocker**

```typescript
User: "Do my math homework questions 1-10, deadline tomorrow"

2USE Response:
"I noticed this looks like homework 📚
I won't give direct answers, but I can help you UNDERSTAND!

Let's start with #1:
- Try it yourself first
- Show me your step-by-step thinking
- I'll point out where you're stuck
- You'll learn and be ready for tests!"
```

### **3. Lazy Prompt Detector**

```typescript
User: "answer this" *paste question*

2USE Response:
"Hmm, seems like you haven't tried thinking first 😅

Tell me:
1. What do you understand from the question?
2. What confuses you?
3. What have you tried?

Just 2-3 sentences is enough!
Then I can give hints that actually help 🧠"
```

### **4. Progressive Hints**

```typescript
// Attempt 1 (Level 0 - Socratic only)
"What are you trying to find? What's blocking you?"

// Attempt 2 (Level 1 - High-level direction)
"Think about isolating the variable. What operation would help?"

// Attempt 3 (Level 2 - Break down the problem)
"The +3 is on the wrong side. What's the opposite of +3?"

// Attempt 4 (Level 3 - Similar example)
"Example: If x + 5 = 10, we subtract 5 from both sides..."

// Attempt 5 (Level 4 - Step-by-step, last resort)
"Okay, let's solve together: 2x + 3 = 7
 Step 1: Subtract 3 from both sides..."
```

---

## ⚙️ Configuration Examples

### **Free Tier Optimization**

```typescript
const twoUse = new TwoUse({
  provider: 'gemini', // 1500 free requests/day
  options: {
    cachingEnabled: true, // Reduce API calls by 70%
    progressiveHintLevels: 4
  }
});
```

### **Local Privacy-First**

```typescript
const twoUse = new TwoUse({
  provider: 'ollama', // Runs locally
  options: {
    model: 'llama3.1', // or mistral, phi
    cachingEnabled: true
  }
});
```

### **Hybrid Setup (Best of Both Worlds)**

```typescript
const twoUse = new TwoUse({
  providers: [
    { name: 'ollama', priority: 1, use: 'simple-questions' },
    { name: 'gemini', priority: 2, use: 'complex-reasoning' }
  ],
  options: {
    autoRouting: true // Automatically choose provider
  }
});
```

---

## 📊 Cost Estimation

| Setup | Monthly Users | Est. Cost | Notes |
|-------|--------------|-----------|-------|
| **Free Tier** | 1,000 | $0 | Gemini Flash + aggressive caching |
| **Hybrid** | 5,000 | $15-30 | Ollama (local) + Gemini (complex) |
| **Scale** | 10,000+ | $50-100 | Multi-provider with fallbacks |

**Cost Breakdown (1000 active students):**
- 50% use AI daily = 500 users
- Avg 10 messages/day = 5,000 messages
- 70% cached = 1,500 LLM calls
- Gemini Flash free tier: **$0** ✅
- GPT-4o mini fallback: ~$13.50/month

---

## 🛡️ Safety Features

### **Anti-Cheating Mechanisms**

```typescript
// Homework pattern detection
const homeworkPatterns = [
  /kerjain PR/i,
  /tugas \d+ nomor/i,
  /deadline (besok|tomorrow)/i,
  /jawaban langsung/i
];

// Copy-paste detection
const isCopied = detectCopyPaste(userMessage);

// Lazy prompt detection
const thinkingTime = now() - lastMessageTime;
if (thinkingTime < 30000) {
  throw new ThinkingTimeRequired();
}
```

### **Dependency Prevention**

```typescript
// Usage limits
const limits = {
  maxDailyMessages: 50,
  maxConsecutiveQuickQuestions: 5,
  minimumBreakTime: 600000 // 10 minutes
};

// Independence scoring
const independenceRate = (solvedAlone / totalProblems) * 100;
// Target: 70%+ (user should solve most alone)
```

---

## 🧪 Testing

```bash
# Run tests
npm test

# Test with different providers
npm test -- --provider=gemini
npm test -- --provider=ollama

# Test specific scenarios
npm test -- --scenario=homework-detection
npm test -- --scenario=lazy-prompt
npm test -- --scenario=progressive-hints
```

---

## 🤝 Contributing

We welcome contributions! Please see [CONTRIBUTING.md](CONTRIBUTING.md) for details.

### **Development Setup**

```bash
# Clone repo
git clone https://github.com/sandikodev/2use.git
cd 2use

# Install dependencies
pnpm install

# Run in dev mode
pnpm dev

# Build
pnpm build
```

### **Areas We Need Help:**

- 🌍 Multi-language support (currently ID/EN)
- 🧠 More Socratic prompt templates
- 🎯 Subject-specific hint strategies (Math, Science, etc.)
- 📊 Analytics dashboard
- 🔬 Research on learning effectiveness

---

## 📚 Research & Impact

### **Metrics We Track:**

- **Thinking Depth Score** - How deeply users think before asking
- **Self-Sufficiency Rate** - % of problems solved independently
- **Dependency Index** - Early warning system for AI addiction
- **Learning Progress** - Actual comprehension vs. answer collection

### **Early Results** (Beta, n=22 students):

- ✅ 68% self-sufficiency rate (target: 70%)
- ✅ 45% reduction in AI messages over 4 weeks
- ✅ 85% student satisfaction (despite initial frustration)
- ✅ Teacher-reported improvement in critical thinking

---

## 🗺️ Roadmap

### **v1.0 (Current)**
- ✅ Socratic prompting engine
- ✅ Multi-LLM support
- ✅ Basic dependency prevention
- ✅ Homework detection
- ✅ Progressive hints

### **v1.1 (Q1 2026)**
- [ ] Voice interface
- [ ] Image/diagram analysis
- [ ] Multi-language (10+ languages)
- [ ] Advanced caching strategies

### **v2.0 (Q2 2026)**
- [ ] Fine-tuned model for education
- [ ] Predictive intervention (before dependency forms)
- [ ] Subject-specific expert modes
- [ ] Teacher analytics dashboard

### **v3.0 (Q3 2026+)**
- [ ] Research API for educational institutions
- [ ] White-label licensing
- [ ] Integration marketplace
- [ ] Global impact measurement

---

## 📄 License

MIT License - see [LICENSE](LICENSE) for details.

---

## 🙏 Acknowledgments

**2USE** is developed by [@sandikodev](https://github.com/sandikodev) as part of [We Will Shine](https://github.com/sandikodev/we-will-shine) project.

**Inspired by:**
- Socratic Method (ancient Greek philosophy)
- Growth Mindset (Carol Dweck)
- Zone of Proximal Development (Lev Vygotsky)
- Islamic educational principles
- Indonesian education context

**Special Thanks:**
- 22 siswa 7D Putri SMP IT Masjid Syuhada (beta testers)
- Educational psychology researchers
- Open source community

---

## 📞 Contact & Support

- **GitHub Issues**: [Report bugs or request features](https://github.com/sandikodev/2use/issues)
- **Discussions**: [Join the community](https://github.com/sandikodev/2use/discussions)
- **Email**: 2use@wewillshine.dev
- **Twitter**: [@wewillshine](https://twitter.com/wewillshine)

---

## 💡 Fun Facts

**Why "2USE"?**

1. **Akronim**: Double **U-S** from **We Will Shine**
2. **Pronunciations**:
   - "Double-use" (how it sounds)
   - "Double you can see" (what it means)
   - "The doubled that you can see" (philosophical depth)
3. **Bahasa Indonesia**: "Dua kali lipat yang dapat kamu lihat"
4. **Triple Meaning**:
   - **Doubled Understanding** - See process + result
   - **Two-way Interaction** - Socratic dialogue
   - **To Use (wisely)** - Use AI without dependency

---

<div align="center">

**Built with ❤️ for independent thinkers**

**"The doubled that makes you unstoppable"**

[⭐ Star us on GitHub](https://github.com/sandikodev/2use) | [🚀 Try We Will Shine](https://github.com/sandikodev/we-will-shine)

</div>
