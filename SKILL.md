---
name: content-system
description: Turn a technical topic or source into one short-form video script (reel / Shorts / TikTok) or explainer that fuses an engaging personal story with accurate, simple technical substance. Use when writing or improving a script that must hook with a real problem, explain a real mechanism clearly, and pay off at the end — especially AI/LLM or other technical topics for an educated but non-expert audience.
---

# Content System

Turn one technical source into one short video that hooks with a real problem, explains the
real mechanism simply, and pays off at the end. Story + real substance, in a normal voice.

Loose on purpose. Three beats, a voice, a substance rule. The beats hold it together; everything
inside is yours to play with. It's a shape to fill creatively, not a checklist to obey.

---

## The shape

**1. Hook — the mystery, built on the hero.**
Open on a specific, relatable problem and stop at the strange result. Build the mystery on the
**hero** (the thing you're explaining) and its **contradiction** ("same model, wrong one time,
right the next"). Say it the simplest natural way — don't over-qualify for pedantic precision
("one landed tails", not "at least one landed tails") if the clean version carries it. End on the
raw question — "but why?" — don't restate the contradiction you just showed. No orphan terms:
don't name a mechanism in the hook you won't explain for three paragraphs.

**2. Build — follow the viewer's questions.**
Don't list facts in order. Thread it as the chain of questions the viewer is actually asking,
each beat answering the last and raising the next — and **write those questions into the
script**: *"but why does it get it wrong?" → answer → "so what does 'step by step' change?" →
answer → "but is that hard-coded? how does it even know what to do?" → answer.* The questions are
the thread; they turn the tech into a story unfolding instead of a lecture.
- Introduce and explain each concept in the same breath.
- **Bake analogies into the verbs** ("it jots its working into a short-term memory and reads it
  back"), don't slap a label on them ("it's like a scratchpad"). No "the important bit:" —
  if it's in the script, it's already important.
- Get the mechanism scientifically right, and frame it as the answer to the viewer's question.

**3. Payoff — answer the hook, then stop.**
Often the aha is a single line that answers the hook's question ("that's how 'think step by step'
works") — the explanation already did the work. Land that line and stop. Only a one-line CTA
after it. No restating, no "once this clicked I started…" wind-down.

---

## Substance — keep the causal links, cut the decoration

Keep every concept that is a **link in the causal chain** — the steps that make the answer make
sense. Cut only **consequence-free specifics**: facts that are true but lead nowhere.

Same fact, two framings — one load-bearing, one decoration:
- KEEP: "the data runs through the network once per word, so it only gets a single pass, which
  makes multi-step reasoning impossible." Every clause is a link.
- CUT: "it travels through all 80 layers." The number changes nothing.

Don't cut a mechanism just because a flashier version of it was decoration. The test for each
fact: *is it a link in the chain, or a number with no consequence?* Links stay and get explained
(simply, with the real name). Numbers-with-no-consequence go.

---

## Voice (where it usually breaks)

Talk like you're explaining to a friend. Flat, plain, a little run-on. Most sentences should be
unremarkable — slop is what happens when every line tries to land. Reference:

> "turns out they're stateless, which means every call knows nothing about the last one. so then
> how does it even remember the chat? it doesn't, the app just pastes the whole thing back in…"

**No slop. Cut on sight:** triads · "it's not X, it's Y" and two-beat reveals · punchy fragments
for effect · balanced/poetic closers · a flourish on every line (one light touch max) · hype
words (literally, wild, magic, "here's the thing") · em-dashes for drama.

---

## Before posting

- [ ] Hook: hero + contradiction, simplest phrasing, ends on the question — no answer, no orphan terms
- [ ] Build is a question-chain: each beat answers the last and raises the next, questions written in
- [ ] Causal links kept and explained; consequence-free specifics cut; mechanism accurate
- [ ] Analogies baked into the verbs, not labelled
- [ ] Aha answers the hook in ~a line, then stops; one-line CTA
- [ ] Reads like talking, not performing (slop list clean)

---

## Worked example — "prompt" (chain-of-thought)

Hero: chain-of-thought prompting. Question-chain: *why wrong? → what does step-by-step change? →
but how does it know what to do?* Causal links kept (one pass per word → no multi-step reasoning;
reasoning as working memory in the hidden states; the learned "wait" signal). Decoration cut (80
layers, vectors, probability notation).

> I asked an AI: two coins are tossed, one landed tails, what's the chance the other one is heads?
> It said 50%, full confidence. That's wrong, the answer's two-thirds. But add "think step by
> step" first, and the same model gets it right. But why? What is "think step by step" actually
> doing to it?
>
> Let's take the first case. An AI can't stop and think before it answers. The only way it thinks
> is by writing words, one at a time, and each word costs the same small, fixed amount of compute,
> whether it's an easy word or the hardest step of the problem. They call it FLOPs, and it's fixed
> because the data runs through the network's layers exactly once per word, so it only ever gets a
> single pass, which makes real multi-step reasoning impossible.
>
> And that's what "think step by step" fixes. By making it write its reasoning before the answer,
> you give it more of those passes. And as it writes, it jots its half-finished working into a
> short-term memory called the hidden states, then reads it back for the next step. Now it's not
> guessing in one shot, it's working through the problem.
>
> But is that hard-coded? How does the model even know what to do? It's the word "wait". The AI
> types "wait" into its own context to buy itself time, because it was trained on billions of
> pages of human writing where "wait, let me check that" almost always comes right before a
> correction. So once it plants "wait" in its response, it reads that back and takes it as the
> signal to stop and re-check.
>
> That's how "think step by step" works.
>
> And that's just one of them. I've documented a whole set of prompting techniques that work like
> this. Comment "prompt" and I'll send them over.

Hook ends on "but why?" · each beat raises the next question · "once per word → no multi-step"
kept as a causal link · analogy in the verbs ("jots… reads it back") · "wait" framed as the model
doing it itself · aha is one line, then the CTA.
