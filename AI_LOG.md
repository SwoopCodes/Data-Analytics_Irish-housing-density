# AI Collaboration Log

This log records significant AI interactions for the AIAS Level 3 requirement. It feeds the 300–500 word AI Collaboration Statement at the end of the notebook.

**Tool:** Claude (Anthropic), model Claude Opus 5.5, used through claude.ai (text and voice).

| Date | Task | Representative prompt | What the AI produced | What I checked, changed or decided |
|---|---|---|---|---|
| 03-Nov-2026 | Understanding the brief; first topic | "I have no idea what I am doing and need the best guidance" | Plain-English summary of the brief; a first draft based on HEA student retention | **Dropped that topic** and decided to brainstorm my own ideas outside education |
| 03-Nov-2026 | Reviewing my 3 topic ideas | "Review them and tell me which of these could be viable" | Feasibility review of housing density, public transport and foreign vs native employment, with data sources | **Chose housing density** myself |
| 03-Nov-2026 | Checking the downloaded data | "Can you confirm the column names are a bit strange?" | Explained the CSO column code pattern; found the national total row and merged small area codes | Downloaded the CSO glossary so the code meanings could be checked against the official source |
| 03-Nov-2026 | Joining the land-area file | "Is this the file you were searching for?" | Confirmed a 100% join on GUID; checked that `Shape__Area` sums to the area of the State | Found and downloaded the boundary file myself |
| 03-Nov-2026 | Choosing features | "Could we argue we would be removing % car commuting because it has no relevance to housing?" | Pushed back: commuting *is* related to density. Suggested dropping it because of its −0.65 correlation with public transport instead | **Decided to drop % car (Option A)**; my original reason was corrected |
| 03-Nov-2026 | End goal and approval email | "What is the actual solution we are trying to solve?" | Linked the project to the National Planning Framework compact growth targets; drafted the email and README | Asked for the email to be shorter and plainer; **found a dead source link** in the AI's reference list |
| 03-Nov-2026 | Repo setup + Phase 1 draft | "Create the project directory with all the necessary files for a first commit" | Folder structure, data notes, data dictionary, Phase 1 draft text, first commit | [Fill in after review: what you rewrote in Phase 1 and why] |
