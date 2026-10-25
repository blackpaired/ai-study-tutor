# Example session

A shortened example of a tutoring session with `/study-tutor`. The material is a set of lecture notes on the nerves of the upper limb. *User* is the student, *AI* is the agent running the skill.

---

**User:** `/study-tutor ~/Documents/Anatomy/Upper-limb/`

**AI:** I've read *Upper limb – muscles and nerves*. Here's how I'd split it:
0. Core rules · 1. Shoulder girdle nerves · 2. Axillary nerve · 3. Musculocutaneous nerve · 4. Radial nerve · 5. Median nerve · 6. Ulnar nerve · 7. Hand muscles (about 8 units).
Say *slower*, *faster*, *example*, *explain differently*, *sketch*, *summarise* or *stop* at any time.

Before we start: **What do you already know about how muscles get their nerves? "Nothing" is a fine answer.**

---

**User:** not much, I just learn the tables by heart

**AI:** Perfect starting point – today you'll see that most of the table can be *derived* instead of memorised.

**Unit 0 – Core rules. Chunk 1: compartments.**

The limbs are divided by sheets of connective tissue (**fascia**) into **compartments** – think of rooms in a flat. Muscles in the same room usually do the same job, and they are supplied by the **same nerve**.

```
 Arm, cross-section
 ┌──────────── anterior compartment ────────────┐  flexors   → musculocutaneous n.
 │      biceps   brachialis   coracobrachialis   │
 ├──────────────────── humerus ─────────────────┤
 │                  triceps                     │  extensors → radial n.
 └──────────── posterior compartment ───────────┘
```

**Rule 1: one compartment = one nerve.**

**What do you think – which nerve supplies the brachialis, and why can you answer that without having learned it?**

---

**User:** musculocutaneous because it's in the front room?

**AI:** **Correct** – and the reason you gave ("it's in the front room") is exactly the point. You derived it instead of remembering it.

**Chunk 2: exceptions.** Rules have exceptions, and exams love them. A muscle that lies at the **border between two compartments** can be supplied by **both** nerves.

**What would you predict for the lateral part of the brachialis, which borders the posterior compartment?**

---

**User:** maybe both nerves?

**AI:** **Exactly.** Your notes say: lateral part of the brachialis, *inconstantly* also the **radial nerve** (p. 6).

**Now in your own words:** why can the brachialis get two nerves, while the biceps only gets one?

---

**User:** because biceps is in the middle of the front room and brachialis touches the back room

**AI:** **Correct**, and nicely put. In the exam say it with the terms: "The biceps lies entirely in the anterior (flexor) compartment; the lateral part of the brachialis borders the posterior (extensor) compartment, so it can also be supplied by the radial nerve."

**Unit 0 wrap-up.** Explain rule 1 and its exception in 2–3 sentences, as if you were explaining it to a fellow student.

---

*… after the summary: a correct mnemonic, the key points in bullets, a mini review of earlier units, then unit 1 …*

---

**User:** stop

**AI:** Today: units 0–2 (core rules, shoulder girdle nerves, axillary nerve).
- **Sits well:** compartment rule, deriving nerves from position.
- **Still shaky:** the difference between "medial/lateral pectoral nerve" (named after the cords, not their position).
- **Next time:** a short review, then unit 3 (musculocutaneous nerve).

I've saved your progress in `Upper-limb_Progress.md`.

---

## The progress file it writes

```markdown
# Progress: Upper limb – muscles and nerves

Language: English

## Learning plan
- [x] 0. Core rules (2026-10-25)
- [x] 1. Shoulder girdle nerves (2026-10-25)
- [x] 2. Axillary nerve (2026-10-25)
- [ ] 3. Musculocutaneous nerve  ← continue here
- [ ] 4. Radial nerve
- …

## Still shaky
- Medial/lateral pectoral nerve – named after the cords, not the position (notes p. 4)

## Core rules (short version)
1. One compartment = one nerve.
2. Dorsal layer (extensors) and ventral layer (flexors) get different nerves.
3. Innervation shows a muscle's origin, not its function.

## Sessions
### 2026-10-25 – units 0–2
- Derived most assignments from rule 1; exception principle understood.
```
