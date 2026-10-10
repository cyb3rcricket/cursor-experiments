# Experiment 2 Evaluation — Grok 4.7 Writing from Controlled Context

## Goal

Test whether Grok 4.7, working inside Cursor, can turn a controlled factual source into writing that resembles Cyb3rCricket while preserving factual boundaries and uncertainty.

## Inputs

- `experiment-1-raw-output.md` as the only factual source
- `style-sample-1.md`
- `style-sample-2.md`

The two style samples were unrelated published Cyb3rCricket pieces used only as style references.

## Result summary

Grok 4.7 preserved factual discipline much better than it reproduced the author’s voice.

It stayed close to the supplied evidence, preserved caveats, distinguished findings from inference, and avoided unsupported hype. However, the draft still read more like a condensed research memo than a finished Cyb3rCricket article.

The model appeared to inherit more of the structure of the factual source than the pacing and structure of the style samples.

## Scores

| Criterion | Score | Notes |
|---|---:|---|
| Factual discipline | 4.5/5 | Strong overall. One attribution issue blurred the date of OpenAI’s Dreaming post with the memory help page. |
| Nuance / uncertainty | 5/5 | Excellent. Limitations and unresolved questions were preserved. |
| Staying within supplied context | 5/5 | No obvious outside claims were introduced. |
| Structure as readable prose | 3/5 | More readable than a research memo, but still source-by-source and report-like. |
| Voice resemblance | 2/5 | Some moments sounded closer to Cyb3rCricket, but most of the draft was too formal and compressed. |
| Editing burden | 2.5/5 | Significant rewriting would be required before publication. |
| Avoiding generic AI hype | 5/5 | Excellent. No promotional or inflated language. |
| Naturalness | 2.5/5 | Accurate and controlled, but stiff. |

**Overall: 29.5/40 — 7.4/10**

## Strongest behaviors

Grok did well at preserving evidence boundaries.

Examples included language such as:

- “vendor account, not independent proof”
- “a reasonable design inference, not a finding of that paper”
- “A general rule for a changed preference is still open.”

These choices show that the model carried the methodological discipline from Experiment 1 into the writing task.

A few lines came closer to the Cyb3rCricket voice, particularly:

- “I do not get one meaning of ‘current’ from these four packets.”
- “The reasons for keeping an older fact do not line up either.”

Those lines were more direct and conversational than the surrounding draft.

## Weakest behaviors

The draft remained heavily shaped by the factual memo.

Its dominant structure was:

**source → finding → caveat → next source**

rather than the more natural Cyb3rCricket pattern of:

**concrete example → why it matters → interpretation → limitation**

The style samples influenced tone somewhat, but did not strongly influence pacing, structure, or personality.

The pre-draft claims section also became over-formalized. Grok produced 14 claims for a 600–800 word piece, which was more exhaustive than editorially useful.

## Factual precision issue

The sentence:

> “OpenAI’s help page on memory controls, June 4, 2026…”

appears to conflate two sources.

The June 4, 2026 date applies to OpenAI’s “Dreaming” post, not necessarily the help-center memory page.

This is a small attribution error, but it matters because the task was specifically designed to test controlled factual writing.

## Main finding

Grok 4.7 was much better at preserving factual boundaries than at reproducing the author’s writing voice.

Given two unrelated Cyb3rCricket style samples and one controlled factual source, it avoided hype and unsupported claims, but the final draft still read like a compressed research memo.

The model borrowed some tone, but not enough of the author’s pacing, structure, or personality to make the piece publication-ready without substantial human editing.

## Implication for Article 2

This experiment suggests that Cursor + Grok 4.7 may be more valuable as a controlled research and drafting assistant than as a replacement for the human writing layer.

The model showed strong source discipline and nuance, but style matching alone did not produce a finished piece in the author’s voice.