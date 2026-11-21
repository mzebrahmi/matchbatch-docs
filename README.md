# MatchBatch: Search File Actions

Copy, move, delete, or rename whole files from VS Code's built-in Search view. Search for content, review the matching files, and confirm your changes from the Search toolbar.

Requires VS Code **1.106.0 or newer** with an open, trusted folder. This minimum includes the built-in Search-results command and Rename toolbar icon.

## See it in action

The demos use relative paths. Folder-picker address fields are anonymized.

### Show Searchable Files

Use the eye icon to list searchable, nonempty text files with one result per file. Your Search filters and exclusions remain in effect.

![Show Searchable Files in VS Code's Search view](https://mzebrahmi.github.io/matchbatch-docs/media/demos/show-searchable-files.gif)

### Copy files

Copy selected files to another folder, preserving their folder structure and keeping the originals.

![Reviewing and copying matching files in VS Code](https://mzebrahmi.github.io/matchbatch-docs/media/demos/copy-files.gif)

### Delete files

Review the selected files and confirm deletion through VS Code. Trash behavior follows VS Code's settings and the filesystem.

![Reviewing and deleting matching files in VS Code](https://mzebrahmi.github.io/matchbatch-docs/media/demos/delete-files.gif)

### Move files

Move selected files to another folder while preserving their folder structure.

![Reviewing and moving matching files in VS Code](https://mzebrahmi.github.io/matchbatch-docs/media/demos/move-files.gif)

### Rename files

Add text, find and replace, assign a new name, or number files. Preview the new names before confirming. Find and Replace can also change extensions.

![Previewing and applying a batch rename in VS Code](https://mzebrahmi.github.io/matchbatch-docs/media/demos/rename-files.gif)

## Settings

Open VS Code's **Settings** and search for **MatchBatch**.

All setting IDs below start with `searchFileActions.`.

| Setting | Default | What it changes |
| --- | --- | --- |
| `useRelativePaths` | `true` | Show workspace-relative paths in previews and messages; disable for full paths. |
| `copy.conflictBehavior` | `stop` | Existing Copy targets: `stop`, `skip`, or `replace`. |
| `move.conflictBehavior` | `stop` | Existing Move targets: `stop`, `skip`, or `replace`. |
| `rename.conflictBehavior` | `stop` | Existing Rename targets: `stop`, `skip`, or `replace`. |
| `copy.folderLayout` | `preserve` | Keep relative folders (`preserve`) or copy files directly into the destination (`flat`). |
| `move.folderLayout` | `preserve` | Keep relative folders (`preserve`) or move files directly into the destination (`flat`). |
| `copy.confirm` | `true` | Show the final Copy confirmation dialog. |
| `move.confirm` | `true` | Show the final Move confirmation dialog. |
| `delete.confirm` | `true` | Show the final Delete confirmation dialog. |
| `rename.confirm` | `true` | Show the final Rename confirmation dialog. |
| `showCompletionNotifications` | `true` | Show success notifications; progress and errors remain visible when disabled. |
| `rename.defaultMode` | `add` | Initially select Add Text (`add`), Find and Replace (`replace`), New Name (`name`), or Number Files (`number`). |
| `rename.numberStart` | `1` | Prefill the starting number, zero or greater. |
| `rename.numberDigits` | `3` | Prefill the minimum number of digits, from 1 to 12. |

**Conflicts:** `stop` stops the operation when a destination file exists; `skip` leaves those files out; `replace` overwrites existing regular files and marks them in the preview. Directories, symbolic links, and two planned files with the same destination are always rejected, including in flat layout.

File previews are always shown. Confirmation settings control only the extension's final dialog; native VS Code prompts can still appear. Trash behavior follows VS Code's settings and the filesystem. Rename defaults remain editable in the mode chooser and numbering prompts.

Relative paths include workspace folder names in multi-root workspaces. Destinations outside the workspace use a **Destination** label and destination-relative paths. This changes displayed paths only; VS Code controls the folder-picker UI, which can still show full paths.

## Privacy

MatchBatch has no telemetry or analytics and does not collect or aggregate usage statistics. It does not send your file contents, search queries or results, filenames, or paths to its developer, analytics services, or a separate hosted file-processing service.

File actions run in your selected local, WSL, remote, or network storage environment. VS Code, storage providers, cloud-sync software, and documentation hosts have their own data practices. Viewing the hosted demo images or opening documentation links may make network requests to GitHub.

## License

MatchBatch is proprietary software, free to use for personal, educational, and commercial work. Redistribution or resale requires the copyright owner's written permission. See [LICENSE.txt](LICENSE.txt) for the full terms.

## Support

Report bugs and request features in [GitHub Issues](https://github.com/mzebrahmi/matchbatch-docs/issues).

This repository contains documentation and demo assets for MatchBatch. The extension implementation is maintained separately.
