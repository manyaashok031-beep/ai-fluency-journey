# Prompt Engineering Cheatsheet

## What This Is
A personal reference guide covering the core concepts of Prompt Engineering — written in my own words as part of my 8-Day AI Fluency Self-Learning Course. This cheatsheet covers what prompt engineering is, how AI reads prompts, the 6 core techniques, and the 8 most common mistakes — all connected to the 4D Framework of AI.

## What I Learned
- Prompt Engineering is not just about asking questions — it is the skill of designing, structuring, and refining instructions to get reliable and accurate outputs from AI consistently
- AI reads your entire prompt as one block of content and fills every missing gap with its own assumptions — clarity in your prompt is everything
- The 6 core techniques (Role, Context, Task, Format, Constraint, Example) work best when combined together in a single prompt
- The first AI response is always a starting point, never a final product — iteration is where the real value comes from
- Every mistake in prompt engineering comes down to one root cause — leaving too many gaps for AI to assume incorrectly

## How to Use This
Read section by section as a reference while writing prompts. Each technique and mistake includes a real example you can learn from directly.

## Tools Used
- Markdown
- Claude AI (learning partner and tutor)

## About
**Manya** | 8-Day AI Fluency Self-Learning Course | Goal: Internship  by Year 3

---

## 1. What is Prompt Engineering?

Prompt Engineering is the skill of giving clear, structured, and well-defined instructions to an AI to get the work done in exactly the way you want — consistently, not just once by luck.

Think of AI as a new intern at a company who does not know anything — what work to do, where to go, whom to approach, or what tools to use. A senior engineer guides that intern by telling them exactly what to do, how to do it, in what format, what the limits are, and whom to refer to. Prompt Engineering is exactly that senior engineer — the one who tells AI what to do, how to do it, and in what structure.

In simple words: **Prompt Engineering is the skill of designing, structuring, and refining instructions to an AI system to get reliable, accurate, and useful outputs — consistently.**

---

## 2. How AI Actually Reads Your Prompt

AI does not read your prompt word by word the way you read a sentence. It reads your entire prompt as **one block of content** and fills in any missing information using its own assumptions — based on the billions of examples it was trained on.

When you write something unclear or incomplete, AI does not stop and ask *"Why didn't you tell me this?"* — it assumes and gives the most average, generic answer suitable for anyone, not for you specifically.

**The golden rule:** Every gap you leave in your prompt, AI fills with an assumption. Your job is to leave as few gaps as possible.

---

## 3. Connection to the 4D Framework

The 4D Framework — Delegation, Description, Discernment, and Diligence — connects directly to Prompt Engineering at every level:

- **Delegation** — Deciding what role AI plays and what role you play. This is directly related to the Role technique in prompt engineering — assigning AI a specific identity before giving any instruction.
- **Description** — This IS prompt engineering. Telling AI what to do, how to do it, in what format, and within what limits. Prompt Engineering is Description taken to a professional level.
- **Discernment** — Evaluating and analysing the output given by AI. This connects to the iteration process — checking whether the response is correct, well-structured, and actually what you needed.
- **Diligence** — Taking responsibility for the output AI produces. Since you instructed AI, the output is your responsibility. This means not giving up after the first attempt and refining the prompt until you get the result you actually need.

---

## 4. The 6 Core Prompting Techniques

### Technique 1 — Role
Tell AI exactly who or what it should be before giving any instruction. When you assign a role, AI immediately adjusts its behaviour, tone, and perspective to match that role — just like an actor who stays in character throughout a performance.

Without a role, AI gives a generic response written for nobody in particular. With a role, it responds from the specific perspective and expertise level you assigned.

**Example:**
> *"You are a professional drawing teacher with 5 years of experience teaching beginners. Suggest creative drawing ideas for a complete beginner who struggles with finding inspiration."*

---

### Technique 2 — Context
Give AI your background story before your actual question. The more context you give, the more personalised and accurate the response will be. Without context, AI assumes everything and gives a generic answer suited for the average person — not for you.

Think of it like visiting a doctor. A patient who says *"I feel unwell"* gets generic advice. A patient who says *"I am 19 years old, no prior health issues, sharp pain in my lower back since yesterday that gets worse when I sit"* gets specific, accurate help.

**Example:**
> *"I am a first year student in a Bachelor of Arts college. I have to write an essay on the topic 'The Dream' but I am not getting creative ideas. Help me suggest some interesting approaches to make my essay stand out."*

---

### Technique 3 — Task
Tell AI exactly what you want it to do — clearly and specifically. Do not leave the actual action vague. A prompt with role and context but no clear task is like briefing an employee on who they are and where they work but never telling them what their job is.

Be specific: do you want a summary, an explanation, a list, a comparison, a code review, a draft? Name it precisely.

**Example:**
> *"You are a senior Java developer. I am a first year student learning Java basics. Explain the difference between an Array and an ArrayList — give me a simple definition of each, a real-life analogy for each, and one code example showing when to use each one."*

---

### Technique 4 — Format
Tell AI exactly how to structure its response. Without a format instruction, AI picks whatever structure feels most average or generic. With a format instruction, you get exactly the structure you need.

Common format instructions: step by step, bullet points, comparison table, simple explanation, code with explanation, short paragraph, numbered list.

**Example:**
> *"Give me a simple recipe to cook a rice bath in a step-by-step format, explaining each step in simple words so that a complete beginner can follow and make it easily."*

---

### Technique 5 — Constraint
Tell AI what it should NOT do as clearly as you tell it what to do. Without constraints, AI over-explains, adds unnecessary information, or goes off topic trying to be as thorough as possible. Constraints keep AI focused and within the boundaries you actually need.

Common constraints: word limit, complexity level, topics to avoid, language style, scope limitations.

**Example:**
> *"Explain how AI works at a basic level for a complete beginner. Keep the response under 200 words. Use one real-life analogy and relate every point to it. Do not mention any high-level technical concepts or jargon that a beginner would not understand."*

---

### Technique 6 — Example
Show AI an example of what a good output looks like before asking for your actual output. When you show AI the format, style, or structure you expect, it analyses the pattern and replicates it. This is one of the most powerful techniques — examples teach faster and more precisely than instructions alone.

**Example:**
> *"I want to create a LinkedIn post announcing that I completed an AI Fluency certification. Here is an example of a post I liked from someone else: [paste example]. Help me write my own post in a similar style — professional, concise, and highlighting what I learned. Here is my information: [your details]."*

---

### Combining All 6 Techniques

Using all 6 techniques together in one prompt gives dramatically better results than any vague question ever could. Here is what a fully combined prompt looks like:

> *"You are a senior Java backend developer with experience hiring interns at product companies in Germany. [Role] I am a first year ISE student in Bengaluru with basic Java OOP knowledge — classes, objects, and loops — from a Biology background with no prior coding experience. [Context] Review this Java code I wrote for managing an ArrayList of student names and give me feedback on: correctness, clean code practices, and any improvements. [Task] Structure your feedback as: what is correct, what needs improvement, and one specific thing I should learn next. [Format] Keep the response under 300 words and do not use advanced Java concepts beyond what a first year student would know. [Constraint] Here is an example of the feedback style I find most helpful: [paste example]. [Example]"*

---

## 5. The 8 Common Mistakes in Prompt Engineering

### Mistake 1 — Vague Request
A vague prompt leaves too many gaps for AI to assume. The result is a generic answer suited for anyone — not for what you actually needed. The fix is to answer these questions inside your prompt: Who am I? What exactly do I need? Why do I need it? How should it be structured? What should it avoid?

---

### Mistake 2 — Asking Multiple Unrelated Things at Once
For example: *"Explain cybersecurity, how it works, top hiring companies, and the future of the field."* When AI tries to answer everything, it gives shallow answers on all topics. Attention and quality are divided. The fix is to ask each question separately, in order, with proper technique applied to each.

---

### Mistake 3 — Not Telling AI Who You Are
Without context about yourself, AI gives a generic answer for the average person. Always mention your background, level, and goal — the information that is relevant to your specific request. Just like no one can help you solve a problem they do not fully understand, AI cannot personalise a response without knowing who you are.

---

### Mistake 4 — Accepting the First Response Without Iteration
The first response is a starting point, not a final product. Judging AI purely on its first attempt is like judging a dish a beginner cook makes for the very first time — the first attempt may need more salt, less spice, a different technique. The fix is to analyse the output, identify what is wrong or missing, and refine it iteration by iteration until you get exactly what you need. Great AI outputs, like great sculptures, are never made in one attempt.

---

### Mistake 5 — Trusting AI Blindly Without Discernment
Copying AI output directly and submitting or publishing it without checking is a serious mistake. AI can be wrong, outdated, or confidently incorrect. Always analyse the output — is it accurate? Is it current? Is this actually how it should be? Just like you would not follow wrong directions on a map without verifying, you should not use AI output without applying your own judgement first.

---

### Mistake 6 — Using AI as a Search Engine
AI has a knowledge cutoff — it does not have access to real-time information. Using it for current news, live prices, or recent events may give outdated or incorrect answers. AI is best used for explaining concepts, generating content, reasoning through problems, and brainstorming ideas. For current facts and real-time data — use a search engine.

---

### Mistake 7 — Writing Prompts Like Search Queries
Keywords work well in search engines but not in AI. A keyword-style prompt like *"Java ArrayList tutorial"* gives a generic, list-like output. A full-sentence prompt with context, role, and constraints gives a rich, personalised, and useful response. Always write prompts as full sentences with proper technique.

---

### Mistake 8 — Prompt Abandonment — Giving Up Too Early
Prompt Engineering is a skill, not a shortcut. Just like you cannot write perfect code on the very first try, you cannot always get a perfect AI response on the first attempt. The fix is to keep refining — add more context, tighten constraints, provide an example, or try a completely different approach. What matters is not perfection on the first try — it is the persistence to keep improving until you get there.

---

## 6. Quick Reference — All 6 Techniques at a Glance

| Technique | What It Does | One-Line Reminder |
|---|---|---|
| Role | Assigns AI an identity | Tell AI who to be before anything else |
| Context | Gives AI your background | More context = more personalised response |
| Task | Tells AI exactly what to do | Name the specific action clearly |
| Format | Structures the response | Tell AI how to present the answer |
| Constraint | Sets limits and boundaries | Tell AI what NOT to do as clearly as what to do |
| Example | Shows AI what good output looks like | Show don't just tell |

---

## 7. Quick Reference — All 8 Mistakes at a Glance

| # | Mistake | One-Line Fix |
|---|---|---|
| 1 | Vague Request | Answer who, what, why, how inside your prompt |
| 2 | Multiple Unrelated Tasks | One prompt, one focused task |
| 3 | No Context | Always introduce yourself before the task |
| 4 | Accepting First Response | Iterate until it is exactly right, not just close |
| 5 | Blind Trust | Question, analyse, then use the output |
| 6 | Using AI as Search Engine | Search engines for facts, AI for thinking |
| 7 | Keyword Prompts | Write full sentences with context and intent |
| 8 | Giving Up Too Early | Diagnose why it failed, refine, and try again |

---

*Written by Manya | Part of the 8-Day AI Fluency Self-Learning Course | April 2026 
