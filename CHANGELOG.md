# Changes

## 0.7.0

- Rename the extension to **MatchBatch: Search File Actions** and set its publisher to `mzebrahmi`, giving it the extension ID `mzebrahmi.matchbatch`.
- Lower the minimum VS Code version from 1.146.0 to 1.106.0 while retaining support for the built-in Search-results command and Rename toolbar icon.
- Refresh the demos with relative paths and Explorer views before and after file actions, including Delete. Only folder-picker address fields are anonymized.
- Show workspace-relative paths by default in extension previews and messages, with workspace folder names distinguishing multi-root sources.
- Label destinations outside the workspace as Destination and show their file paths relative to the selected destination folder.
- Add **Use Relative Paths** to MatchBatch's VS Code Settings. Turn it off to display full paths. This affects display only; actual file operations and VS Code's native folder-picker UI are unchanged.
- Add separate Copy, Move, and Rename conflict settings: Stop (default), Skip, or Replace existing regular files. Mark replacements in previews; continue rejecting directories, symbolic links, and duplicate planned destinations.
- Add Preserve (default) and Flat folder layouts for Copy and Move.
- Add separate final-confirmation settings for Copy, Move, Delete, and Rename, enabled by default. Keep file previews and native VS Code prompts; retain VS Code's Trash behavior.
- Add a setting for success notifications, enabled by default, without hiding progress or errors.
- Add rename mode and numbering defaults: Add Text, starting number 1, and minimum 3 digits. Keep the chooser and prompts editable for each action.

## 0.6.0

- Show file-action progress in VS Code's Search view and status bar after confirmation, including the selection checks.
- Update Copy and Move counts after each successful file operation, retaining the completed count if the batch stops on an error.
- Keep Rename and Delete as single native VS Code batches, showing activity during submission and confirming the total only after success.
- Let VS Code update Search results through its normal file handling; copied originals remain in the results. Keep completion notifications from holding the action busy flag.
- Live progress UI, WSL, and SSH validation remain pending.

## 0.5.0

- Add the approved magnifying-glass logo as the extension icon.

- Add New Name with optional numbering, and Number Files to add a sequence before or after original stems. Preserve each file's last extension and current folder.
- Let users choose a starting number and minimum digit count, with an underscore separator. Number the whole batch in full-path order; keep the previewed numbers when files are deselected.
- Add Name only (the default), Extension only, and Full filename scopes to literal Find and Replace. Allow changing or removing the last extension, with a confirmation notice that extension changes do not convert file contents.
- Retain before/after previews, final confirmation, native VS Code rename handling, refusal of conflicts and overwrites, and the notification busy-flag fix. Live Rename UI, WSL, and SSH validation remain pending.

## 0.4.0

- Add Rename with VS Code's native rename icon after Move in the Search toolbar, plus Command Palette and filename/path actions.
- Offer Add Text for a prefix and suffix, and Find and Replace for all literal, case-sensitive occurrences in filename stems. Preserve each file's last extension and current folder; skip unchanged names.
- Show old and new paths with folder context, allow deselection, and require final modal confirmation.
- Check source safety and target collisions before submitting a single native `WorkspaceEdit` rename batch. Refuse overwrites and report possible partial application after failure without retrying.
- Retain the 0.3.1 fix that releases the busy flag without waiting for notification dismissal. Live WSL/SSH and Rename UI validation remain pending.

## 0.3.1

- Release the busy flag when an action finishes, without waiting for completion, error, or no-results notifications to be dismissed.
- Add regression tests that keep notifications open while starting another copy after Copy, Move, Delete, no results, and an error.

## 0.3.0

- Add Copy to the Search toolbar, Command Palette, and filename/path action picker.
- Preview and confirm copies through VS Code's filesystem API, keeping source files and refusing existing targets.
- Preserve relative directories and workspace prefixes when copying, using the same destination picker and host checks as Move.
- Use an eye for Show Searchable Files, copy for Copy, trash for Delete, and an open folder for Move; all four precede native expand/collapse.
- Extend mocked Windows, Linux, WSL, and SSH coverage for copying, including cancellation, conflicts, and partial failure. Live remote testing remains pending.

## 0.2.0

- Place the extension's Search icons before VS Code's native expand/collapse icon.
- Run on the workspace extension host, including Linux workspaces connected through WSL and Remote SSH.
- Start VS Code's destination picker at the workspace and preserve remote URI scheme and authority.
- Delete the reviewed selection through VS Code's WorkspaceEdit API. VS Code chooses Trash according to filesystem capability and files.enableTrash; permanent deletion is possible.
- Retain a preview and explicit confirmation because the Explorer Delete command cannot accept an exact file list.
- Require explicit selection when importing Unix Search labels, and support home-directory abbreviations.
- Add mocked Linux, WSL, and SSH coverage. Live remote testing remains pending.

## 0.1.0

- Add Trash and Move icons to the built-in Search view toolbar.
- Add a Files icon that sets a native Search preset with one match per searchable, nonempty text file.
- Review and select unique matching files before either action.
- Find files by name or path glob from the Command Palette, using the same preview and actions.
- Preserve relative directories when moving files, with separate prefixes for multiple workspace roots.
- Refuse unsupported Search output, files outside local workspace roots, unsaved edits, changed files, and move conflicts.
- Use Recycle Bin/Trash without a permanent-delete fallback.
