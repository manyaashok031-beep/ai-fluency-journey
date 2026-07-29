# AI Self-Learning Journey — Day 2

**Topic Focus:** How LLMs Actually Work
**Status:** ✅ Completed
**Prepared by:** M A Manya

> All core concepts covered in depth, with the apply task completed alongside.

---

## 1. What is an LLM?

LLM stands for Large Language Model. At its core, it is a prediction engine that learned the patterns of human language from hundreds of billions of examples, and it generates responses one word at a time — each new word chosen based on everything that came before it.

> **Analogy**
> Think of the autocomplete feature on a phone keyboard — except trained on the entire internet, at a scale far beyond anything a human could process.

---

## 2. How LLMs Are Trained

Training happens in three distinct phases. In **Pre-Training**, the model is exposed to hundreds of billions of words and plays a fill-in-the-blank game billions of times, picking up language, facts, reasoning patterns, and even coding syntax purely through pattern recognition. In **Fine-Tuning**, it's trained on thousands of examples of ideal conversations, learning to behave like a helpful assistant rather than just predicting the next chunk of text. Finally, in **RLHF (Reinforcement Learning from Human Feedback)**, humans rank multiple candidate responses, and the model learns to produce the kind of answer people consistently prefer.

It's worth understanding that the base model is essentially fixed once this training is complete — it doesn't relearn every day. Day-to-day facts and current events instead reach the model through two separate mechanisms: real-time web search tools, and RAG (Retrieval Augmented Generation), where external databases are connected at the moment a question is asked. New model versions are released every few months carrying updated training data, but between releases the core model itself stays constant.

---

## 3. What Are Tokens?

Tokens are the actual chunks an LLM processes — roughly 4 characters, or about three-quarters of a word, each. Importantly, AI does not see individual letters and it does not see full words either; it sees tokens.

This has two very practical implications. First, pricing is based on tokens, and total cost is input tokens plus output tokens combined — which is why a short, vague prompt can actually end up costing more than a well-written one: the vague prompt tends to trigger a long, generic, meandering response, while a carefully written prompt produces a short, focused one, and output tokens typically weigh more heavily on the total cost. Second, AI genuinely struggles with character-level tasks — like counting how many times a letter appears in a word, or reversing a word letter by letter — because it never actually "sees" individual letters. It's a little like reading an entire book in four-letter chunks and then being asked to count one specific letter throughout.

---

## 4. What is Temperature?

Temperature controls how predictable or creative an AI's output is, on a scale from 0 to 1. At low temperature (close to 0), the model always picks the most statistically likely next word, producing consistent, safe, somewhat repetitive output. At high temperature (closer to 1), it explores less likely words, producing output that's more varied and creative — though occasionally stranger too.

> **Analogy**
> A low-temperature person always answers "rice and dal" when asked what's for dinner. A high-temperature person surprises you every single time — sometimes brilliantly, sometimes bizarrely.

Regular users don't get a literal temperature slider — the platform sets a balanced default, while developers can control it precisely through the API. But the effect can still be simulated through prompt language: asking for "one correct answer" pushes the response toward low-temperature behaviour, while asking for "five wildly different creative ideas" pushes it toward high-temperature behaviour. Regenerating a response is also a simple way to explore a different temperature path for the same prompt.

---

## 5. What is a Context Window?

The context window is everything AI can "see" in the current conversation at any given time, measured in tokens. Once it fills up, the oldest content quietly drops off, and the model literally can no longer see it. Claude's context window currently holds up to 200,000 tokens — roughly 150,000 words, or about the length of a full novel.

Working within this limit across a long project comes down to a few practical strategies: keeping a structured handoff report that summarises everything so far and pasting it at the start of a new session; deliberately starting fresh sessions for natural breakpoints, like treating one day of learning as one conversation; carrying a short personal identity block — ten to fifteen lines summarising who you are — into every new chat; asking AI to checkpoint with a periodic summary during especially long conversations; and, at a more technical level, external memory systems such as vector databases that developers use to extend memory beyond any single context window.

---

## 6. Why Do LLMs Hallucinate?

Hallucination is when AI generates false information with complete confidence. It happens because LLMs are optimised to produce fluent, plausible-sounding text — not text that is guaranteed to be true.

> **Analogy**
> Like a student who read thousands of exam papers but never actually studied the material deeply — writing confident-sounding wrong answers by copying the pattern of what correct answers usually look like.

Hallucinations show up most often around obscure topics, specific facts, dates or citations, recent events past the training cutoff, and prompts built on a false premise that the model simply agrees with and elaborates on. A few practical habits reduce the risk: asking AI to cite its sources, asking it to state a confidence level, breaking a complex question into smaller pieces, providing a source document directly (the essence of RAG), and always verifying anything high-stakes independently. At the company level, techniques like Constitutional AI, RLHF, and dedicated fact-verification layers are used to reduce this further.

This isn't unique to language models either — every category of AI has its own version of the same failure. Computer vision misclassifies (a chihuahua mistaken for a muffin), recommendation systems build false preference models, robotics can mis-model its environment, and game AI can be confidently wrong about strategy. The root cause is always the same: pattern matching standing in for genuine understanding.

---

## 7. LLMs vs AI — What Actually Counts as Intelligence?

It's worth pausing on why this is called Artificial Intelligence at all, given that LLMs arguably don't possess intelligence in the way we normally mean it — and whether LLMs and AI are even the same thing.

They aren't. LLMs are one category within AI, not the whole of it — AI also spans computer vision, robotics, recommendation systems, game AI, and self-driving systems. The word "intelligence" itself is a historical label coined back in 1956, long before modern LLMs existed, and it simply stuck as the technology evolved far beyond its original meaning.

There are two philosophical camps on this, and neither has won. One says intelligence requires genuine understanding, and by that standard LLMs are not intelligent — this is the essence of the Chinese Room argument. The other says that if an output is indistinguishable from human intelligence, it counts as intelligence for all practical purposes — the Turing Test view. The honest, practical answer sits in between: LLMs have no consciousness, no self-awareness, and no genuine understanding, but they produce outputs that sometimes look remarkably like human intelligence, purely through very sophisticated pattern matching.

---

## 8. Embeddings — How AI Actually "Reads" Words

AI cannot read words directly — it only processes numbers. Embeddings are the system that converts words and text into vectors, or lists of numbers, in a way that preserves meaning and the relationships between concepts.

> **Analogy**
> Picture a massive library organised not alphabetically, but by meaning — books on similar topics sit physically close to one another. Embeddings build exactly this kind of arrangement for words, in mathematical space.

| Property | What It Captures |
|---|---|
| Semantic Similarity | Words with similar meanings get similar vectors, sitting close together in mathematical space |
| Relationships | Captures analogical reasoning as an actual mathematical structure |
| Context Sensitivity | The same word gets a different vector depending on the words surrounding it |

| Application | How Embeddings Are Used |
|---|---|
| Semantic Search | Finding documents by meaning, not just by matching keywords |
| RAG Systems | Retrieving the most relevant information from a database to feed into a response |
| Code Similarity Detection | Finding duplicate or similar code across a codebase |
| Recommendation Systems | Finding similar items to recommend, based on meaning rather than tags |

> **4D Framework Connection**
> Embeddings are the invisible infrastructure that makes Description possible at all — a prompt is converted into embeddings before AI processes a single word of it.

---

## 9. The Attention Mechanism

When AI processes a prompt, it doesn't treat every word equally. For each word it generates, it looks back across the entire input and assigns attention scores — deciding which parts are most relevant right at that moment.

> **Analogy**
> Similar to reading a dense legal document — your brain naturally pays closer attention to the critical terms and cross-references them as you go. The Attention Mechanism is how AI does exactly this, mathematically.

| Capability | What It Enables |
|---|---|
| Long-Range Dependencies | Connects words or concepts that are far apart in a document |
| Multi-Head Attention | Multiple attention processes run in parallel, each catching something different |
| Self-Attention | The model also attends to the response it is currently generating |

| Observation | Explanation via Attention |
|---|---|
| Beginning and end of prompts are handled better | Attention is naturally stronger at the boundaries of the input |
| Critical instructions work better placed at both the start and end | Both positions receive strong attention scores |
| Very long prompts cause things to get missed in the middle | Attention gets diluted once spread across too many tokens |
| Specific, concrete words draw more attention than vague ones | High-signal words attract higher attention scores |

> **4D Framework Connection**
> The Attention Mechanism is exactly what makes Discernment necessary — AI selectively attends to parts of a prompt, so it's on me to evaluate whether it attended to the right parts.

---

## 10. RLHF — A Deeper Look

RLHF bridges the gap between a model that can merely predict text and one that is genuinely helpful, harmless, and honest. It's the process that shapes an AI's values and behaviour, not just its language ability.

> **Analogy**
> Like training a chef where food critics taste every dish produced, rank them, and the chef studies those rankings to calibrate precisely to what the critics value. Over thousands of meals, the chef becomes finely tuned to human preference.

| Phase | What Happens |
|---|---|
| Phase 1 — Collecting Human Preference Data | Human raters are shown the same prompt with 2–5 different AI responses and rank them from best to worst |
| Phase 2 — Training a Reward Model | A separate AI is trained on this preference data to predict what human raters would prefer for any given response |
| Phase 3 — Reinforcement Learning | The language model generates responses, the Reward Model scores them, and the language model learns to score higher over time |

| Behaviour AI Learned | How RLHF Produced It |
|---|---|
| AI declines harmful requests | Human raters consistently downranked harmful responses |
| AI admits uncertainty | Raters preferred honest uncertainty over confident wrongness |
| AI gives structured responses | Raters preferred organised answers over walls of text |
| AI hedges on political topics | Raters were inconsistent, so the model learned to hedge |

> **Note**
> RLHF makes models match human preference — but human preference isn't always correct. If raters tended to prefer confident-sounding answers, the model learns to sound confident even when it shouldn't, which is part of what feeds hallucination. Anthropic layers Constitutional AI on top of RLHF specifically to address this.

> **4D Framework Connection**
> RLHF is how the Diligence principle gets baked into AI at a structural level — human raters took the job of evaluating outputs seriously, so the model carries that same standard forward.

---

## ✅ End of Day 2 Report

**How LLMs Actually Work** — completed and logged.
