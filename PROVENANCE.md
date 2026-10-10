# Artifact provenance and public-safety review

## Recovery notes

- Experiment 1’s prompt, four source packets, raw output, and evaluation were copied from the saved Cursor workspace.
- Experiment 2’s prompt, three inputs, raw output, and evaluation were copied from the saved Cursor workspace.
- Experiment 3’s prompt, five fictional project inputs, and evaluation were copied from the saved Cursor workspace.
- Experiment 3 did not have a separate saved raw-output file. Its `raw-output.md` was recovered from the complete final assistant text in the original Cursor agent transcript and preserved verbatim.

The raw outputs have not been corrected, shortened, reformatted, or rewritten. That includes Experiment 2’s source-attribution error.

## What is intentionally excluded

The public packet does not include Cursor agent transcripts, editor history, screenshots, or machine metadata. Those records contain absolute local paths, workspace identifiers, and tool-call details. They do not add useful evidence beyond the saved prompts, inputs, and first-run answers.

## Privacy review

The publication set was checked for:

- email addresses, phone numbers, street addresses, and credentials;
- local Windows and OneDrive paths;
- API keys, tokens, passwords, and other secrets;
- the account holder’s legal name; and
- references to private or real internal projects presented as experimental facts.

No credentials or private contact details were found in the publication set. The retained names, handles, and links are public citations already present in the source packets or published style samples.

`Lantern` is a fictional project created for Experiment 3. `TinyTalk` appears only in negative prompt constraints; the experiments do not expose TinyTalk implementation details.

## Integrity note

The folder and file names were normalized for public readability. File contents copied from the experiment workspaces were not edited. `ARTIFACTS.sha256` records the experiment artifacts so the publication set can be checked for later changes.

`.gitattributes` disables automatic line-ending conversion for `experiments/` so a Git checkout retains those original bytes. Experiment 3's answer was extracted as UTF-8 Markdown; its text matches the recorded response, with a final file newline added.
