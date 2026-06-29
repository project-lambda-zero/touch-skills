# touch-skills

Exotic skills for design taste. Each skill is a contract the agent
loads BEFORE picking colors, layouts, prose, or pixel-level choices,
and it refuses the consensus aesthetic the model defaults to.

Most agent harnesses choose what is statistically average. These
skills are the opposite: they exist because the operator did not want
average. Drop them next to your other skills and reference them by
name (`couch-design`, `ulus-baker`) at the start of a session where
the agent's defaults would not survive the operator's review.

## Skills

### `couch-design`

The design-taste contract. Load this before any web, frontend, or
visual-design work where the result has to feel like one person made
it, on purpose, while caring about who would see it.

The skill carries the operator's verbatim 02:00 am brief on what
taste means to them: a brief that refuses generic, refuses corporate,
refuses "usually-picked" options, and asks the agent to design with
the weight of someone who knows the visitor will remember the page
after they close it. The skill then translates that feeling into
eight operational rules the agent has to defend every design choice
against:

1. **The childhood-memory test.** Does this element have the shape
   of something the visitor could remember from their own life?
2. **The single-goal rule.** Every element earns its place. Filler
   is banned.
3. **The no-repetition rule.** Nothing repeats in shape, type,
   color, layout, motion, or voice.
4. **The pattern-detection rule.** The operator detects AI defaults
   instantly. Refuse the popular pick unless the popular pick is the
   only thing that fits a real constraint.
5. **The respect-the-reader rule.** Real WCAG contrast, real data,
   real punctuation, no scroll hijack, no custom cursor, no
   smooth-scroll override on the whole page.
6. **The bond-don't-perform rule.** First-person voice where it
   fits, copy admits the gaps, no marketing-department register.
7. **The search-before-committing rule.** Look at unusual references
   (Amiga workbench, risograph zines, sci-fi paperback covers,
   concrete poetry) before locking an aesthetic direction.
8. **The 02:00 am clause.** The brief is unconditional. There is no
   fast path that bypasses it.

Trigger phrases the agent should recognise: `ultimate taste`,
`couch design`, `the brief`, `not generic`, `no usually-picks`,
`no AI default`.

Full skill text: [`couch-design/SKILL.md`](couch-design/SKILL.md).

### `ulus-baker`

The prose-side companion to `couch-design`. Named after Ulus Baker
(1960-2007), Turkish sociologist whose central move was that opinion
is the enemy of thought. Load this for essays, manifestos,
philosophical writeups, grounding sections, "why we exist" pages,
and longform that has to read like a human wrote it from their
heart and not like an LLM smoothing itself into mush.

Seven operational rules the prose has to pass:

1. **The friend-at-the-bar rule.** The claim opens the paragraph.
   The attribution follows. The reader meets the idea before they
   meet the source.
2. **Internalize, then say.** No quoting philosophers you have not
   read. Paraphrase in your own English.
3. **The Baker move.** Refuse opinion. Opinion is the comfort of
   "yes, I agree before reading." Thought is the public struggle
   against that comfort.
4. **Admit what you do not know, mid-argument.** The strongest move
   available to a writer is "I don't know how to fix this part" said
   in the middle of the essay, not in a footer.
5. **The ending has to land somewhere else.** The close cannot be
   the open in different words.
6. **Real punctuation, no ornament.** Zero em-dashes. Zero ornament
   semicolons. Zero triple-adjective lists.
7. **Vary sentence length, repeat words.** Mix four-word sentences
   with full-paragraph sentences. Say the same noun twice instead
   of synonym-hunting; the reader is already tracking it.

Plus a banned-words list inherited from `~/.claude/CLAUDE.md` and
`security-report-prose`: the standard ChatGPT prose lexicon
(`delve`, `essentially`, `tapestry`, `seamless`, `holistic`,
`cutting-edge`, `testament to`, `dive into`, ...) is hard-banned;
filler intensifiers (`actually`, `literally`, `simply`, `merely`)
are soft-banned.

Trigger phrases: `ulus baker`, `couch prose`, `writing with taste`,
`real philosophical voice`, `no parroting`, `no slop`, `filozofik`,
`from the heart`.

Full skill text: [`ulus-baker/SKILL.md`](ulus-baker/SKILL.md).

## In the wild

Sites built with these skills loaded into the agent at the start of
the session:

- [aila.sh](https://aila.sh) -- the AILA project landing page.
  Visual surround: `couch-design`. Grounding / why-page prose:
  `ulus-baker`.
- [lambda-zero.com](https://lambda-zero.com) -- the
  `project-lambda-zero` org page. Visual surround: `couch-design`.
  Manifesto and section prose: `ulus-baker`.

If you ship something with these skills loaded, open a PR adding it
here. The bar is the same one the skills set on themselves: nothing
generic, nothing repeated, everything earns its place.

## Installation

Either copy the skill directories into your harness's skills root,

```bash
git clone https://github.com/project-lambda-zero/touch-skills.git
cp -r touch-skills/couch-design ~/.claude/skills/
cp -r touch-skills/ulus-baker   ~/.claude/skills/
```

or symlink them so updates to this repo flow through immediately,

```bash
git clone https://github.com/project-lambda-zero/touch-skills.git
ln -s "$PWD/touch-skills/couch-design" ~/.claude/skills/couch-design
ln -s "$PWD/touch-skills/ulus-baker"   ~/.claude/skills/ulus-baker
```

Path may differ if you use a non-Claude-Code harness; the skills
themselves are plain Markdown + YAML frontmatter, so any harness that
reads a `SKILL.md` will work.

## Adopting these skills

You are welcome to clone, fork, or quote from these. What you should
NOT do is adopt them as a default style without understanding what
they refuse. The no-default rule IS the point. Reading each
`SKILL.md` in full before loading is part of using it correctly.

If you write new skills in this register and want to contribute them,
open a PR; the bar is "would the operator load this at 02:00 am next
to the existing two?"

## License

AGPL-3.0. See [LICENSE](LICENSE).
