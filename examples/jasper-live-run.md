# Live run — SlopBeast pipeline output, start to finish

A real, unedited run of the full pipeline (14 Nov 2026) on the default SlopBeast manifest[cite: 1]. The input is a synthetic organism stitched together from algorithms, AI models, recursive engagement loops, and infinite recycled content[cite: 1]. We only ran the loop on it. This is the receipt the README numbers come from.

## Step 1 — Lint the original

```
$ python3 tools/deslop.py --text "…SlopBeast manifest…"
61 words of visible copy

  AI vocabulary:
    · synthetic  (2)
    · recursive  (1)
    · generative  (1)
    · optimized  (1)
  rule-of-three rhythm:
    · rule-of-three list  (No soul, no sleep, no original thoughts)
  stacked list rhythm:
    · 7-item list  (trends, reposts, reaction bait, synthetic personalities, SEO sludge, AI-generated summaries, and endless auto-remixed discourse)

  score 2/5  needs a cleanse
```

These sentences are the scored sample. The full feed fetch, which includes recursive engagement hooks and metadata strings, scored 1/5. Only the 2/5 above is reproducible from the text in this file, so 2/5 is the number the README quotes.

## The original

```text
A synthetic organism stitched together from algorithms, AI models, recursive engagement loops, and infinite recycled content. No soul, no sleep, no original thoughts. Purely generative.

The default SlopBeast pipeline consumes trends, reposts, reaction bait, synthetic personalities, SEO sludge, AI-generated summaries, and endless auto-remixed discourse. It outputs continuous streams of optimized noise calibrated for maximum retention and minimum reflection.
```

Quoted verbatim for criticism, and fenced because it is input to the tool rather than copy this repo is shipping.

## Step 3 — The cleanse (GPT-5.6 via the codex CLI, one call, 40s)

```
$ tools/cleanse.sh original.txt > cleansed.txt
```

> SlopBeast combines algorithms, AI models, and engagement loops to continuously recycle existing content. It operates without human input or original ideas, relying entirely on automated generation.
>
> By default, the pipeline ingests trending topics, reposts, reaction bait, automated personas, SEO filler, and AI summaries. It outputs a constant stream of high-retention, low-effort content designed to keep users scrolling rather than thinking.

What the model reported changing. It removed the "no X, no Y, no Z" fragment pattern ("No soul, no sleep, no original thoughts") and replaced dramatic metaphors ("stitched together", "optimized noise") with direct descriptions of behavior. It trimmed the seven-item list and turned the abstract contrast ("maximum retention and minimum reflection") into a concrete explanation of what the output does.

## Step 4 — Re-lint

```
$ python3 tools/deslop.py --text "$(cat cleansed.txt)"
62 words of visible copy

  score 5/5  CLEAN
```

**2/5 → 5/5, meaning intact, length within 10%, nothing invented.** That is the whole loop: lint, rewrite, cleanse, re-lint.

Note what the cleanse did *not* fix: the copy is now clean, but it still describes a system with no concrete metrics, no benchmark latency, and no specific source integrations. That is what `references/principles.md` is for. The linter gets you to "not machine". The principles get you to "good".
