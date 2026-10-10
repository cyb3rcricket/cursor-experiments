# Artifact provenance and public-safety review

## Recovery notes

- Experiment 1’s prompt, four source packets, raw output, and evaluation were copied from the saved Cursor workspace.
- Experiment 2’s prompt, three inputs, raw output, and evaluation were copied from the saved Cursor workspace.
- Experiment 3’s prompt, five fictional project inputs, and evaluation were copied from the saved Cursor workspace.
- Experiment 3 did not have a separate saved raw-output file. Its `raw-output.md` was recovered from the complete final assistant text in the original Cursor agent transcript and preserved verbatim.

The raw outputs have not been corrected, shortened, reformatted, or rewritten after delivery. That includes Experiment 2’s source-attribution error. All three saved prompts and answers were compared with the recovered transcripts and match after normalizing line endings and ignoring a trailing file newline.

The transcripts show one user prompt per experiment. Experiment 1 includes the agent's own draft editing before its final answer. Experiment 3 includes the Firebase challenge in its initial prompt.

## What is intentionally excluded

The public packet does not include Cursor agent transcripts, editor history, screenshots, or machine metadata. The recovered transcripts contain absolute local paths, workspace identifiers, and tool-call details. They were used privately to check the submitted prompts, delivered answers, and run sequence; those checks are summarized in [REVIEW_NOTES.md](REVIEW_NOTES.md).

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

The folder and file names were normalized for public readability. File contents copied from the experiment workspaces were not edited. Experiment 2's factual input was originally saved as `experiment-1-raw-output.md.txt`; it is packaged as `inputs/experiment-1-raw-output.md`, the name requested in the prompt. Its bytes match Experiment 1's raw output.

`ARTIFACTS.sha256` covers the 21 preserved prompts, inputs, outputs, and evaluations. It intentionally excludes the README files, this provenance note, the review notes, and `.gitattributes`, which can be maintained without changing the historical evidence.

From the repository root, verify the preserved artifacts with `sha256sum -c ARTIFACTS.sha256` on systems that provide that command. On Windows PowerShell:

```powershell
Get-Content -LiteralPath 'ARTIFACTS.sha256' | ForEach-Object {
    $expected, $path = $_ -split '  ', 2
    $actual = (Get-FileHash -LiteralPath $path -Algorithm SHA256).Hash
    if ($actual -ine $expected) { throw "Hash mismatch: $path" }
}
```

`.gitattributes` disables automatic line-ending conversion for `experiments/` so a Git checkout retains those original bytes. Experiment 3's answer was extracted as UTF-8 Markdown; its text matches the recorded response, with a final file newline added.
