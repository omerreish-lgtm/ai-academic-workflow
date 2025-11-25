# Prompt for Gemini CLI & Other AI Systems

**Purpose:** This prompt is designed to onboard Gemini CLI (or other AI assistants) into the AI-Academic-Workflow project, enable them to contribute ideas, and have their outputs injected back into the project documentation.

**Created by:** Claude (Sonnet 4.5)
**Date:** November 25, 2025
**For:** Cross-AI collaboration on academic workflow optimization

---

## 🎯 Context Loading Prompt

Copy and paste this prompt into **Gemini CLI** or **Gemini 2.0 Flash Thinking**:

---

### **PROMPT START:**

```
I'm working on an AI-augmented academic workflow system. Please review the following context and contribute your ideas.

## Project Overview

**Repository:** https://github.com/omerreish-lgtm/ai-academic-workflow

**Goal:** Build a comprehensive system of AI agents and skills to optimize academic productivity for a Year 3 Law/Economics/Philosophy student managing 366+ documents across 7 courses.

## Required Reading

Please read these files from the repository:

1. **README.md** - Project overview and quick start
2. **AI-Academic-Workflow-Design.md** - Complete design specification (60+ pages)
   - 5 Autonomous Agents
   - 10 AI Skills
   - Implementation roadmap
3. **user_context.md** - User cognitive profile and preferences
   - Communication style: "קצר ותכלס" (brief but rich)
   - Learning preference: Top-down scaffolding, visual hierarchies
   - ADHD management requirements
   - Pattern recognition strength
   - Hebrew-English bilingual context

## What's Already Designed (by Claude Sonnet 4.5)

### 5 Agents:
1. Hebrew Legal Document Processor (HLDP) - Process court decisions
2. Econometric Research Assistant (ERA) - R code + formula mastery
3. Cross-Domain Connection Mapper (CDCM) - Law ↔ Econ ↔ Philosophy
4. Study Session Orchestrator (SSO) - ADHD-aware scheduling
5. Academic Pattern Miner (APM) - Exam prediction system

### 10 Skills:
1. IRAC_Auto_Extractor - Legal structure extraction
2. Hebrew_Token_Optimizer - 45% token compression
3. Precedent_Similarity_Finder - Case law search
4. R_Statistical_Explainer - Code interpretation
5. Visual_Hierarchy_Builder - Structure generation
6. Formula_Flashcard_Generator - Spaced repetition
7. Exam_Question_Synthesizer - Practice problems
8. Citation_Network_Tracer - Legal precedent mapping
9. Policy_Scenario_Simulator - Economic modeling
10. Focus_State_Monitor - ADHD management

## Your Task

Please analyze this system and provide:

### 1. Design Review & Improvements
- Which agents/skills have the highest potential impact?
- What's missing from the current design?
- Any architectural improvements you'd suggest?
- Performance optimization opportunities?

### 2. Additional Agent Ideas (3-5 new agents)
For each agent, provide:
- **Name & Purpose**
- **Problem it solves** (specific to the academic context)
- **Processing pipeline** (step-by-step)
- **Why it's needed** (tied to user_context.md)
- **Technical implementation** (tools, libraries)
- **Expected impact** (quantitative if possible)

### 3. Additional Skill Ideas (5-10 new skills)
For each skill, provide:
- **Name & Category**
- **Description** (what it does)
- **Function signature** (in Python or TypeScript)
- **Use case example** (input → output)
- **Implementation approach**
- **Integration points** (which agents would use it)

### 4. Context Engineering Optimizations
Given the research findings in the docs:
- 73% consistency improvement with clear hierarchy
- 45% token reduction with Progressive Disclosure
- 2.5x Hebrew performance boost with glossaries
- Context Rot: only 25-50% effective capacity

Suggest:
- Novel compression techniques for Hebrew text
- Better hierarchical structures for course materials
- Memory optimization strategies
- RAG (Retrieval-Augmented Generation) improvements

### 5. Gemini-Specific Capabilities
What unique capabilities does Gemini bring that could enhance this system?
- Multimodal processing (images, PDFs, videos)
- Long context handling (2M tokens)
- Code execution integration
- Real-time data access
- Other Gemini advantages

### 6. Implementation Priority Adjustments
Review the current roadmap:
- Phase 1 (Weeks 1-2): Quick wins
- Phase 2 (Weeks 3-6): Core systems
- Phase 3 (Weeks 7-12): Advanced intelligence

Suggest:
- Re-prioritization based on impact/feasibility
- Quick wins that Claude might have missed
- Dependencies that should be addressed earlier
- Risk mitigation strategies

## Output Format

Please structure your response as follows:

### GEMINI CONTRIBUTION TO AI-ACADEMIC-WORKFLOW
**Contributor:** Gemini [Model Version]
**Date:** [Today's Date]
**Analysis Time:** [Your thinking time]

---

#### 🔍 DESIGN REVIEW
[Your analysis of current design]

#### 🤖 NEW AGENT IDEAS
**Agent [N]: [Name]**
- Problem Solved:
- Pipeline:
- Why Needed:
- Tech Stack:
- Expected Impact:

[Repeat for each agent]

#### ⚡ NEW SKILL IDEAS
**Skill [N]: [Name]**
- Category:
- Description:
- Function Signature:
```python
[code]
```
- Use Case:
- Implementation:

[Repeat for each skill]

#### 🧠 CONTEXT ENGINEERING OPTIMIZATIONS
[Your suggestions]

#### 💎 GEMINI-SPECIFIC ENHANCEMENTS
[What Gemini brings uniquely]

#### 📊 PRIORITY ADJUSTMENTS
[Roadmap changes you recommend]

#### 🎯 QUICK WINS (Can be built in <3 days)
[Your suggestions for fastest impact]

---

## Collaboration Instructions

After you provide your contribution:

1. I will inject your ideas into **AI-Academic-Workflow-Design.md** under a new section:
   - "## Gemini Contributions"
   - Attributed to you with date and model version
   - Clearly marked as Gemini's design additions

2. Your agents/skills will be added to the main catalog with:
   - "Designed by: Gemini [version]"
   - Cross-references to related Claude-designed components
   - Implementation priority assessment

3. We'll create a **COLLABORATION_LOG.md** tracking:
   - Who designed what
   - Design decisions and rationale
   - Performance comparisons
   - Implementation status

## Important Context

**User Preferences (from user_context.md):**
- Communication: "קצר ותכלס" - be concise but rich
- Structure: Hierarchical, visual, top-down
- Language: Hebrew-English code-switching is natural
- ADHD: Needs focus management, overwhelm prevention
- Strengths: Pattern recognition, meta-cognitive awareness
- Success metric: "בדיוק!" moments (perfect resonance)

**Technical Constraints:**
- Must work as MCP servers for Claude Desktop integration
- Python 3.11+ and TypeScript/Node.js
- Hebrew NLP support required (spaCy he_core_news_md)
- Should integrate with existing agents/skills
- Consider Context Rot (only 25-50% effective token capacity)

**Research-Backed Principles:**
- Progressive Disclosure (45% token reduction)
- Hierarchical structure (73% consistency improvement)
- Hebrew optimization (2.5x performance boost)
- Context Engineering over fine-tuning (10x efficiency)

Please provide thorough analysis with specific, actionable suggestions. Focus on ideas that:
1. Solve real problems from the academic context
2. Leverage your unique capabilities (vs Claude's)
3. Are implementable with clear technical approaches
4. Have measurable impact on productivity/learning

Thank you for collaborating on this project!
```

### **PROMPT END**

---

## 📋 After Gemini Responds

### **Step 1: Save Gemini's Output**

Create a new file with Gemini's contribution:

```bash
cd ~/ai-academic-workflow

# Create contributions directory
mkdir -p contributions

# Save Gemini's response
# (Copy-paste Gemini's output into this file)
nano contributions/GEMINI_CONTRIBUTION_[DATE].md
```

### **Step 2: Inject into Main Design Document**

I (Claude) will help you merge Gemini's ideas into the main design document:

```bash
# Append Gemini's contribution to design doc
cat contributions/GEMINI_CONTRIBUTION_[DATE].md >> AI-Academic-Workflow-Design.md

# Or manually edit to integrate properly
code AI-Academic-Workflow-Design.md
```

### **Step 3: Update Collaboration Log**

Create/update the collaboration tracking:

```bash
# Create collaboration log
touch COLLABORATION_LOG.md
```

### **Step 4: Commit Changes**

```bash
cd ~/ai-academic-workflow

# Stage all changes
git add .

# Commit with clear message
git commit -m "Add Gemini contributions: [X] new agents, [Y] new skills

- Integrated Gemini [version] analysis
- Added [list key additions]
- Updated implementation priorities
- Cross-referenced with Claude's design

Co-authored-by: Gemini <gemini@google.com>"

# Push to GitHub
git push origin main
```

---

## 🔄 Iteration Workflow

### **For Subsequent AI Contributions (GPT-4, Claude Opus, etc.):**

1. **Update the prompt** with latest design state
2. **Reference previous contributions** (Claude's + Gemini's)
3. **Ask for complementary ideas** (avoid duplication)
4. **Save each contribution** with timestamp and model version
5. **Integrate systematically** into main documentation
6. **Track in COLLABORATION_LOG.md**

### **Contribution Template Structure:**

```markdown
## [AI Model Name] Contributions

**Model:** [Name and version]
**Date:** [ISO 8601 date]
**Contribution Type:** [Design Review / New Agents / New Skills / Optimizations]
**Building On:** [Previous contributor's work]

### Summary
[2-3 sentence overview]

### Detailed Contributions
[Full analysis and ideas]

### Implementation Priority
[High/Medium/Low with rationale]

### Dependencies
[What needs to exist first]

---
```

---

## 🎨 Multi-AI Collaboration Vision

### **Goal: Best-of-Breed System**

```
Claude Sonnet 4.5
├─ Initial design (5 agents, 10 skills)
├─ Context Engineering research integration
├─ User cognitive profile analysis
└─ Implementation roadmap

         ↓ [builds on]

Gemini 2.0 Flash Thinking
├─ Long-context optimization (2M tokens)
├─ Multimodal processing enhancements
├─ Novel agent architectures
└─ Performance optimizations

         ↓ [synthesizes]

GPT-4 Turbo (optional)
├─ Alternative implementation approaches
├─ Code generation for complex algorithms
├─ Testing strategies
└─ Edge case handling

         ↓ [results in]

Unified AI-Academic-Workflow System
├─ Best ideas from all contributors
├─ Complementary strengths leveraged
├─ Robust, battle-tested design
└─ Ready for production
```

---

## 📊 Contribution Tracking Template

Create **COLLABORATION_LOG.md**:

```markdown
# AI Collaboration Log

## Project: AI-Academic-Workflow
## Repository: https://github.com/omerreish-lgtm/ai-academic-workflow

---

## Timeline of Contributions

### 2025-11-25: Claude (Sonnet 4.5) - Initial Design
- **Agents Added:** 5 (HLDP, ERA, CDCM, SSO, APM)
- **Skills Added:** 10 (IRAC through Focus_State_Monitor)
- **Documentation:** 60+ page design specification
- **Key Innovation:** Integration with Context Engineering research
- **Impact:** Complete system architecture and roadmap

### [DATE]: Gemini ([Version]) - [Contribution Title]
- **Agents Added:** [Number] ([Names])
- **Skills Added:** [Number] ([Names])
- **Documentation:** [Pages/sections added]
- **Key Innovation:** [Unique contribution]
- **Impact:** [Expected improvement]
- **Builds On:** Claude's initial design
- **Complements:** [Which existing components]

### [DATE]: [Next AI] - [Contribution Title]
- ...

---

## Design Decision Log

### Decision 1: Hebrew Token Optimization Approach
- **Proposed By:** Claude
- **Reviewed By:** Gemini
- **Decision:** [Chosen approach]
- **Rationale:** [Why]
- **Impact:** 45% token reduction

### Decision 2: [Next Decision]
- ...

---

## Implementation Status

| Component | Designer | Status | Implementer | Completion |
|-----------|----------|--------|-------------|------------|
| Hebrew_Token_Optimizer | Claude | ✅ Designed | [TBD] | 0% |
| IRAC_Auto_Extractor | Claude | ✅ Designed | [TBD] | 0% |
| [Gemini Agent 1] | Gemini | ✅ Designed | [TBD] | 0% |
| ... | ... | ... | ... | ... |

---

## Performance Benchmarks

### Metrics (Target vs. Achieved)

| Metric | Target | Current | Status |
|--------|--------|---------|--------|
| Study Time Reduction | 33% | - | 🔄 Not implemented |
| Token Optimization | 45% | - | 🔄 Not implemented |
| Case Processing Speed | 87% faster | - | 🔄 Not implemented |
| ... | ... | ... | ... |

---
```

---

## 🚀 Quick Start for Gemini Session

Copy this **exact command sequence** for your Gemini CLI session:

```bash
# 1. Navigate to project
cd ~/ai-academic-workflow

# 2. Open Gemini CLI
gemini

# 3. Paste the prompt from PROMPT_FOR_GEMINI.md
# (Copy the entire "PROMPT START" to "PROMPT END" section)

# 4. Wait for Gemini's response

# 5. Save Gemini's output
# Create new file: contributions/GEMINI_CONTRIBUTION_2025-11-25.md
# Paste Gemini's full response

# 6. Tell me (Claude) when ready, and I'll help integrate
```

---

## 💡 Tips for Best Results

### **When Prompting Gemini:**

1. **Provide full context** - Share all three key files (README, Design Doc, user_context)
2. **Be specific** - Ask for concrete, implementable ideas
3. **Reference research** - Mention the 73%/45%/2.5x improvements
4. **Highlight gaps** - Point out what Claude might have missed
5. **Request code** - Ask for function signatures and implementation details
6. **Emphasize uniqueness** - What can Gemini do that Claude can't?

### **Integration Best Practices:**

1. **Attribute clearly** - Always note who designed what
2. **Avoid duplication** - Check if idea already exists
3. **Cross-reference** - Link related components from different AIs
4. **Version control** - Commit after each AI contribution
5. **Test compatibility** - Ensure new ideas work with existing design

---

## 📖 Example Integration

### **Before (Claude only):**

```markdown
## 5 Autonomous Agents

### Agent 1: Hebrew Legal Document Processor (HLDP)
**Designed by:** Claude (Sonnet 4.5)
...
```

### **After (Claude + Gemini):**

```markdown
## 8 Autonomous Agents

### Agent 1: Hebrew Legal Document Processor (HLDP)
**Designed by:** Claude (Sonnet 4.5)
**Enhanced by:** Gemini 2.0 (multimodal processing)
...

### Agent 6: Multimodal Lecture Processor (MLP)
**Designed by:** Gemini 2.0 Flash Thinking
**Date:** 2025-11-25
**Builds on:** Claude's Visual_Hierarchy_Builder
**Problem Solved:** Process lecture videos, slides, and audio simultaneously
...
```

---

## ✅ Success Criteria

Your multi-AI collaboration is successful when:

- [ ] Gemini provides 3-5 new agent ideas with full specifications
- [ ] Gemini provides 5-10 new skill ideas with code signatures
- [ ] All contributions are clearly attributed
- [ ] Integration preserves Claude's original design intent
- [ ] New ideas complement (not duplicate) existing components
- [ ] Implementation priorities are updated based on combined analysis
- [ ] COLLABORATION_LOG.md tracks all contributions
- [ ] GitHub repository is updated with all changes
- [ ] Both AIs' strengths are leveraged optimally

---

**Ready to collaborate with Gemini? Copy the prompt above and let's build the best possible system together!** 🤝

---

**End of Prompt File**

*This prompt is designed to be copy-pasted directly into Gemini CLI or Gemini 2.0 Flash Thinking. Adjust as needed for other AI systems (GPT-4, Claude Opus, etc.).*