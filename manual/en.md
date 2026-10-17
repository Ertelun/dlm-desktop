# DLM Desktop 1.3.8 (r219) user manual

[Manual home](../MANUAL.md) · [日本語](ja.md) · [README](../README.md)

This manual covers Windows x64 version 1.3.8 (r219). Checked on October 16, 2026 (JST). Screen labels come from the XAML, presentation properties and localization functions in the latest source matching the distribution record: `c17445c3b63f9bbbab2ab8843c8c0462eef35024`. Code-formatted labels match the English interface. For sign-in, purchases and download initiation on provider websites, follow the provider's own interface.

<a id="contents"></a>
## Contents: choose your task

| Your task | Where to go |
|---|---|
| Start using DLM, download a work and open it | [Basic workflow](#basic): [Launch](#start) → [Choose a library](#library) → [Download](#download) → [View](#view) |
| Learn how to save from a particular service | [Providers](#providers): [Ordinary downloads](#ordinary) · [DLsite multipart](#multipart) · [GOG](#gog) · [Membership posts](#membership) |
| Use the browser, check progress or download again | [Browser controls](#browser) · [Progress and cancellation](#progress) · [Updates and redownloads](#redownload) |
| Add, change or relocate storage | [Library folders](#roots) · [Watch Folder](#watch) |
| Find works more easily | [Search and filters](#search) · [Layout and sorting](#display) · [Saved views](#saved-views) |
| Organize favorites and collections | [Favorites and collections](#collections) · [Bulk actions, hiding and deletion](#bulk) |
| Correct metadata, creator names or work relationships | [Metadata](#metadata) · [Creator names](#creators) · [Same Work Stack](#stacks) · [Append/DLC](#relations) |
| Resume reading or a game | [Continue](#continue) |
| Learn detailed viewer controls | [Images/PDF](#reader) · [Video/audio](#media) · [3D](#model3d) · [Creative assets](#assets) |
| Launch or install a game | [Game actions](#games) |
| Protect settings and manage storage | [Backup and restore](#backup) · [Caches](#maintenance) · [Diagnostics and review](#health) |
| Change language or solve a problem | [Appearance and language](#language) · [Troubleshooting](#troubleshooting) · [Keyboard shortcuts](#shortcuts) |

<a id="basic"></a>
## Basic workflow: the essentials

These four steps take you from choosing a storage folder to downloading a supported work and opening it from the library. An image or PDF work using a supported [ordinary download](#ordinary) is a useful first example.

<a id="start"></a>
### 1. Launch the application

1. Get the Windows x64 ZIP from the [current release page](https://github.com/Ertelun/dlm-desktop/releases/tag/v1.3.8).
2. Close any previously running DLM Desktop and extract the entire ZIP into a new, empty folder.
3. Run `DoujinLibraryManagerDesktop.exe`. The adjacent `app` folder is also required.

.NET is bundled. The embedded browser requires Microsoft Edge WebView2 Runtime. If the application starts in Japanese, change it under [Appearance and language](#language).

The sidebar has four destinations. A leading ○ means the destination is inactive; ● marks the current screen.

| Example label | Purpose |
|---|---|
| `○ Library` | Find and open saved works |
| `○ Continue` | Resume from reading, launch and newly registered candidates |
| `○ Download` | Start downloads on official provider pages |
| `○ Settings` | Manage storage, language and backups |

<a id="library"></a>
### 2. Choose your library

1. In the first-run prompt, click `Choose Library and set up`.
2. Select the folder where you want to save and manage works. Choose a new storage location or an existing DLM library.
3. Wait for loading to finish. The first folder also becomes the download destination.

If you selected `Later`, use `Choose library` at the top of the Library screen. Once a library exists, this button adds another folder.

With multiple folders registered, the one marked ★ is the destination for new downloads. See [Adding folders and changing the destination](#roots). Choosing an arbitrary folder containing ordinary files does not automatically register all of them as new works.

<a id="download"></a>
### 3. Download a work

1. Open `○ Download` in the sidebar.
2. Select the service at the top, such as `DLsite`, `DMM / FANZA`, `itch.io` or `BOOTH`.
3. Sign in on the displayed official website and open the purchased work or other content page.
4. **Start the download using the provider website's own controls.** The wording differs by provider and work.
5. Open `DL Center` on the right to check downloading, validation, extraction and registration. If the right tools are collapsed, the `↓` icon opens the same screen.
6. After saving and registration finish, return to Library and confirm the work appears. Click `Reload` if needed.

A transfer can reach 100% while validation, extraction or registration continues. **Confirm that the work appears in Library and can be opened.** GOG requires [explicit finalization](#gog). For membership services, follow the [post-specific steps](#membership); for split DLsite downloads, follow the [multipart steps](#multipart).

<a id="view"></a>
### 4. Open the downloaded work

1. Return to Library in the sidebar.
2. Search for the title or locate its card.
3. For supported images, PDFs, video and audio, click `Read`. Works with reading history show `Resume`.
4. Choose an item through `Table of contents`, or move with `← Previous` / `Next →`.
5. Click `Close` to return to Library. Saved reading positions are used when resuming later.

Available actions depend on the work. Games use [launch/install actions](#games), and creative assets use [asset inspection](#assets). Open `Details` on a card for more information.

[Back to contents](#contents)

<a id="features"></a>
## Detailed feature instructions

<a id="providers"></a>
### Download according to the provider

<a id="ordinary"></a>
#### Ordinary downloads from DLsite, DMM/FANZA, itch.io, BOOTH and Gumroad

Select the service on the Download screen, sign in on its official page and start saving. For Gumroad, choose `Gumroad` and save the supported file from the official library or content screen. Supported archives and direct files are registered after validation.

| Provider | Saving route in this version |
|---|---|
| DLsite | Supported ordinary archives; split delivery has [separate steps](#multipart) |
| DMM/FANZA | Supported ordinary downloads; official-player-only delivery uses the provider's official route |
| itch.io / BOOTH | Supported archives and direct-file formats |
| Gumroad | Supported files explicitly downloaded from official library/content pages |

See [Provider Capabilities](../PROVIDER_CAPABILITIES.md) for scope. Recognizing a file format does not mean every delivery mode or work can be processed.

<a id="multipart"></a>
#### Save DLsite multipart files

1. Select `DLsite` and open the work's official download page.
2. Download `part1.exe` and every required subsequent part from the same work's delivery set.
3. If `part1.exe` needs browser confirmation, open `Browser save confirmation` and check its browser-side status.
4. Check that saving and registration finish for each file in `DL Center`.
5. Open `Physical folder` from the library work to inspect the complete set.

The original filenames are preserved and the files are grouped under one work. DLM does not merge multipart files or automatically run an installer. Follow the work's official instructions for extraction or installation.

<a id="gog"></a>
#### Register a complete GOG installer set as one work

1. Select `GOG` and sign in on the official account/library page.
2. Save every required Offline Backup Game Installer file for the game, including the `.exe` and any required `.bin` files.
3. Wait for all downloads and file checks to finish.
4. When `Finalize GOG intake and register` becomes available, click it. The finalization banner above the browser is also available when the right tools are collapsed.
5. Confirm the registered work in Library.

**Saving the files alone does not finish registration. Complete the finalization step.** DLM does not automatically run or extract the installer. The later [game action](#games) is a separate operation.

<a id="membership"></a>
#### Save posts from Fantia, pixivFANBOX, Patreon and Ci-en

1. Select the service button and sign in on its official website.
2. Open the **individual post page** you want to save.
3. Save supported images and attachments through that post's official download controls.
4. Save additional files from the same post. Files associated with that post are grouped under the same work.
5. Check saving and registration in `DL Center` and Library.

This version does not require manual post-title entry or DLM-side start/finish actions. It does not automatically traverse a post list to download everything. Supported DLsite work/announcement links in Ci-en are handed to the DLsite screen.

[Back to contents](#contents)

<a id="browser"></a>
### Navigate the browser or open an external browser

| Right-side control | Purpose |
|---|---|
| `Back` / `Forward` | Navigate page history |
| `Reload` | Reload the current page |
| `External browser` | Open the current allowed target in the Windows default browser |
| `Browser save confirmation` | Open the browser's standard download confirmation UI |
| `DL Center` | Open saving/processing history and progress |
| `Change destination` | Open instructions for changing the ★ destination in Settings |

Use `›` on the right to collapse the tools and `‹` in the collapsed state to expand them. Hover over the icons to check their tooltips. Hovering over a service button exposes a menu for returning to its home, library or other provider-specific start page.

To change a service's starting page, edit its URL under `Default browser pages` in Settings and click `Save` on that row. `Reset to default` restores the default. Use each row's `Hide` to hide a service from Download; the button changes to `View` to bring it back. Only HTTPS URLs in the matching provider family can be saved. Hiding a provider does not delete saved works.

If embedded sign-in fails, use another official sign-in method or `External browser`. External browser sign-in state is not copied into DLM. **This version has no standalone action that registers any arbitrary externally downloaded folder as a new work.** `Choose downloaded folder` in an existing work's details is a validation helper, [not new-work registration](#troubleshooting).

<a id="progress"></a>
### Check progress or cancel an operation

`DL Center` shows downloading, extraction and registration progress. If a row offers an enabled `Cancel`, you can cancel that operation. The available cancellation stages depend on the operation.

When the total size is unknown, progress shows received bytes, such as `Downloading (123.4 MiB received)`. Concurrent transfer displays update about every 150 ms. Provider preparation and post-transfer validation/extraction can take time; check both received bytes and the current processing stage.

`Clear history` clears history when available. It does not delete work files. Validation and extraction can take time after transfer, so check registration separately from the transfer percentage.

When Activity Center is open, `Refresh status` refreshes the current status and actions such as `Work details` open the related work. DLM's progress does not establish the transfer progress or completion of an external official browser or distribution application.

<a id="redownload"></a>
### Check updates or download an existing work again

1. Open `Details` for the work.
2. Use `Check for updates` to check the official product page's update date against the saved download date. The available information may be insufficient to determine an update.
3. To download again, click `Redownload` and read the confirmation.
4. Start the download yourself on the official product page that opens.
5. Check the validation and registration result.

Redownloads recheck the original work location before replacement. They do not move that work into the ★ destination for new works. Automatic replacement stops if a duplicate, move, disconnected location or similar conflict is detected.

[Back to contents](#contents)

<a id="roots"></a>
### Add library folders, change the destination or relocate storage

Use `Library folders` in Settings.

| Your task | Steps |
|---|---|
| Browse multiple libraries together | Register a folder using `Add Library folder` |
| Change the destination for new downloads | Click `★ Set as download destination` on the desired row |
| Remove a registration | Click `Remove from list` on the row; work files remain |
| Move a folder to a new location | Use `Relocate…` on an available row, choose an empty destination, and follow the copy, verification and switch confirmations |
| Locate a disconnected folder again | Use `Reconnect…` on its row, select a candidate and review the work-identity comparison |
| Continue an interrupted move | Use `Resume / finalize relocation…` |
| Clear an incomplete relocation record | Use `Abandon incomplete relocation record…`; clearing the record does not delete the original or copied data |

Up to 32 library folders can be registered. Only one is the destination for new works. A disconnected ★ folder does not cause an automatic switch to another folder. Relocation assistance copies and verifies files, creates a Safe Snapshot and switches the registered location. It does not automatically delete the original folder.

<a id="watch"></a>
### Intake new supported files from a chosen folder

1. Under `Watch Folder` in Settings, click `Add Watch Folder`.
2. Select the local folder to watch.
3. Enable `Enable automatic intake`.
4. Use `Check now` to check immediately.
5. To stop watching a folder, click `Remove` on its row.

Up to four folders can be watched. Their direct children are checked every five seconds. Supported archives, PDFs, images, video, audio and 3D models enter the intake route. Subfolders are not watched recursively. Files being copied are held until their size and modification time stabilize. Repeated registration of the same content is suppressed, and source files are not automatically deleted.

<a id="search"></a>
### Search for works and combine filters

1. Type into the search box in Library. `Ctrl+F` moves focus to it.
2. Open the creator, category or site filter and select one or more entries.
3. Add favorites, collection, history or relationship conditions as needed.
4. Click an active-condition chip to remove it, or use `Clear all`.

Search uses saved display/original/alternate titles, creator names, product IDs, providers, categories, formats and collections. Multiple entries inside one filter are combined with OR; different filter types are combined with AND. For example, “creator A or B” can be combined with “CG or manga.”

`Clear all creators`, `Clear all categories` and `Clear all sites` clear only that filter type. `Clear all` clears search/filter conditions while preserving sorting.

<a id="display"></a>
### Change sorting, card density and grouping

Library sorting offers `Title ↑`, `Creator ↑`, `Category ↑`, `Site` and `Recently opened`. Choose `Standard grid`, `Compact grid` or `Compact list` for layout. `Ctrl+Shift+D` also cycles the density.

For grouping, open `Manage` and choose `By creator`, `No grouping`, `By category`, `By site` or `By status`.

<a id="saved-views"></a>
### Save and reuse a frequent search

1. Set the search, filters and sorting in Library.
2. Open `Manage` → `Save / reuse view conditions…`, or press `Ctrl+Shift+V`.
3. Enter a view-condition name and click `Save current conditions`.
4. Later, select it in the list and click `Apply selected conditions`.
5. Use `Rename` / `Delete` to manage saved conditions.

Deletion here removes the saved conditions. Work files are unaffected.

[Back to contents](#contents)

<a id="collections"></a>
### Organize works with favorites and collections

The star on a card toggles its favorite state. Use the collection icon on the card, or `Details` → `Edit collections`, to open the editor. Change `Favorite` or collection membership and click `Save`.

Create, rename and delete collections through `Manage` → `Manage collections`. Enter a name and click `Add`, or select a collection and use `Rename` / `Delete`. Collections organize works within DLM; these actions do not relocate physical folders.

<a id="bulk"></a>
### Apply bulk actions, hide works or delete them

1. Use the selection checkboxes on work cards/rows to select the targets.
2. Open the selection menu with `▶`.
3. Adjust the targets with `Select all visible` / `Clear selection`.
4. Choose actions such as `★ Add to favorites`, `☆ Remove from favorites`, `Add to collection` or `Remove from collection`. Select the target collection for collection actions.

`Hide works` removes works from normal library presentation. Find them through `Manage` → `Hidden works` and restore them with `Show works again`. Hiding does not delete work files.

**`Delete works` permanently deletes files in the work folder. It does not move them to the Recycle Bin.** Review the targets in the confirmation. [User-state backups](#backup) exclude work files, so keep a separate copy if you need the original content.

<a id="metadata"></a>
### Correct display titles, creators, categories or thumbnails

1. Open `Manage` → `Metadata maintenance`.
2. Select the works.
3. Enable the fields you want to edit: `Change display title`, `Change creator / circle display` or `Change display category`, and enter the values.
4. With exactly one work selected, use `Change representative image` → `Choose image from work` to select an image within that work.
5. Click `Preview and apply changes`, review the targets and changes, and apply them.

Applying an enabled field with an empty value clears that field's user override. Use `Restore inherited value` for the thumbnail or `Reset all overrides for selected works` for all overrides. These changes affect display metadata; they do not rename folders or change work files or original provider metadata. Changing the display category does not change the source category used for viewer/game classification.

<a id="creators"></a>
### Merge creator-name variants or correct one work

1. Select the reference work in Library, then open `Manage` → `Merge / correct creator names`.
2. Choose an existing creator name or enter the name to display.
3. Select the scope for works sharing the original creator name, or choose `Change the creator name for this work only`.
4. Review the resulting display and scope, then click `Apply these changes`.
5. To undo the setting, use `Remove the creator-name merge setting` / `Remove the setting for this work only`.

The changes affect creator display, search, filters and grouping. They do not edit work files or provider records.

<a id="stacks"></a>
### Group multiple entries for the same work in the interface

1. Select the works for a bulk action and click `Create Same Work Stack from selection`.
2. Review the entries in the confirmation and save. You can also use `Add to Same Work Stack` on an Action Center candidate.
3. Expand the group in Library to see its entries and choose the one to open.
4. Manage it from work details with `Set as representative`, `Remove from stack` or `Dissolve stack`.

A Same Work Stack groups presentation. Each entry keeps its own provider, product ID, files and storage location. It is not a substitute for Append/DLC relationships.

<a id="relations"></a>
### Connect a game Append/DLC to its parent work

1. Open the game's `Details` → `Manual Append/DLC setting`.
2. Choose `Link to a parent work as an append` or `Link to a parent work as DLC` and select the parent.
3. Click `Save`.
4. If automatic inference is unsuitable, use `Keep as an independent work (suppress automatic detection)`. To remove the manual setting, use `Remove manual setting and restore automatic detection`.

This screen does not overwrite explicit relationships in original metadata. Settings are stored in DLM's local state. Expand the parent card or use related works in its details to navigate to child works.

[Back to contents](#contents)

<a id="continue"></a>
### Resume reading or a game

The sidebar's Continue screen shows Continue Hub 2.0. It builds candidates from reading positions, successful game launches and library registration times, showing up to 24 in newest-first order. Use a candidate's action button to open that work. It targets the entry actually used, rather than replacing it with a group's representative.

`Hide` hides that candidate at that point in time; `Clear visible candidates` hides the currently visible set. Use `Restore hidden` to restore them. Works, reading positions and game files are not deleted. New reading or launch activity can make candidates appear again.

<a id="reader"></a>
### Read images/PDFs and use contents or bookmarks

| Control | How to use it |
|---|---|
| `Table of contents` | Select a page/media entry and click `Go to selected item`. You can also double-click a list entry |
| `From beginning` | Return to the beginning without deleting history or bookmarks |
| `← Previous` / `Next →` | Move to the previous/next page or media |
| `Single page` / `Spread` | Change image layout |
| `Right→Left (RTL)` / `Left→Right (LTR)` | Change image reading direction, including arrow-key navigation |
| `☆ Bookmark` | Toggle the bookmark on the current image page |
| `Prev ★` / `Next ★` | Move between bookmarks |
| `Fit to screen` / `1:1 view` | Change the display size |
| `Full screen` | Toggle full screen |

For internal PDF pages, `← Previous PDF page` / `Next PDF page →` are also available. Image layouts and bookmarks apply only to the media types that support them.

Use `Continuous viewing` and `Previous work` / `Next work` for navigation between works when a target is available. To advance images automatically, select a slideshow interval and click `Start slideshow`.

Toggle `Shuffle OFF` to make next-work navigation choose a random viewable work, excluding the current work, from the current filtered library results. Previous-work navigation remains in the normal order.

### Delete the current work and continue in fullscreen (1.3.8+)

Press `Shift+Delete` while viewing in fullscreen to confirm permanent deletion of the folder of the work currently being viewed. Cancel is selected by default. **Work files are permanently deleted without using the Recycle Bin.** Check the target before confirming.

After success, viewing continues in the same fullscreen window using the current filter and ordered/random mode. Ordered viewing returns to the library at the end; no remaining candidates also returns to the library. Cancellation or failure restores the current work.

During deletion, the current phase, deleted file count and elapsed time are shown. Press `Esc` or select `Return to Library` to leave viewing. A confirmed deletion continues after returning, so this does not cancel deletion. Physical deletion can still take time depending on file count and storage.

<a id="media"></a>
### Play video or audio

Opening supported media attempts automatic playback. Use `▶ Play / Resume`, `⏸ Pause`, `■ Stop`, the seek bar and volume control. Playback continues to the next item at the end of a track/video.

| Key | Video/audio action |
|---|---|
| `Space` / `K` | Play/pause |
| `←` / `→`, `J` / `L`, `Ctrl+←` / `Ctrl+→` | Seek backward/forward by 5, 10 or 30 seconds respectively |
| `↑` / `↓`, `M` | Adjust volume by 5% / toggle mute |
| `[` / `]`, `R` | Change speed in 0.25x increments (0.50–2.00x) / reset to 1.00x |
| `A`, `B`, `X` | Set repeat start / end / clear AB repeat |
| `N` / `P` | Next/previous video or audio track |

A recognized extension may still fail because of the file's codec or content. Use `Open with default app` to hand it to a suitable external application. `Help` shows controls for the current media type.

<a id="model3d"></a>
### Inspect 3D views, parts and textures

1. Open a supported 3D model in the viewer. Left-drag rotates, right-drag moves, and the wheel/middle-drag zooms.
2. Use `Reset view` or the front/back and other view buttons to return to a useful view.
3. Open `Parts / Texture` and select a part on the model or in the list.
4. Inspect it with `Zoom here`, `Only this part`, `Show all parts` and related controls.
5. Use `Choose texture →`, select an in-work candidate and click `Apply to this part` to apply it to the preview. `Choose another image` / `Restore original` are also available.
6. Manage presentation state with `↶ Undo` / `↷ Redo`, `Save current state` and `Reapply selected history`.

History retains up to 30 presentation states and in-work texture assignments. Making a new change after going back in history discards later redo history. Purchased model and image originals are not modified. Use `Open in specialist app` for specialist editing or `Work folder` to inspect originals.

<a id="assets"></a>
### Inspect creative assets and hand them to a specialist application

Creative-asset cards show `Inspect asset`. `Inspect in DLM` in work details also opens the lightweight inspector. Check the format and basic information, then use `Open in specialist app` for editing or `Open actual folder` to locate originals.

Inspection within DLM and editing in a specialist application are separate operations. DLM does not edit every creative-asset format internally.

<a id="games"></a>
### Launch/install games or choose a different executable

Depending on the game's state, actions include `Launch`, `Select launch file` and `Install`. Click the available action and complete any executable selection/confirmation. If running an installer, follow the installer's subsequent instructions.

If automatic classification is unsuitable, use these actions in work details:

| Detail action | Purpose |
|---|---|
| `Manually mark as launchable / choose EXE` | Choose an EXE inside the work folder and treat the work as launchable |
| `Manually mark as installable / choose EXE/MSI` | Choose an EXE/MSI and treat the work as installable |
| `Launch with another EXE` | Choose another EXE; a successfully started selection is saved for the work |
| `Return to automatic detection` | Clear manual classification and the saved launch target |

Only supported files within the work folder can be selected. Completing a download does not install or launch the game. Official-player-only works use their official route.

[Back to contents](#contents)

<a id="backup"></a>
### Back up or restore user state

1. In the backup/restore area of Settings, click `Back up now…`.
2. Choose where to save the `.dlmbackup` file, review the included information and confirm saving.
3. To restore, use `Restore from backup…`, choose the file and follow the confirmations.
4. Use `Create Safe Snapshot` for a manual recovery point, or `Review incomplete operation…` to review incomplete operations.

Included state covers favorites, collections, saved conditions, creator corrections, manual relationships, Same Work Stacks, metadata overrides and reading state. **Work files, sign-in credentials and execution settings are excluded.** The backup itself is not encrypted.

Significant local-state changes create automatic Safe Snapshots. Retention targets up to five generations and a combined 512 MiB while keeping the latest valid recovery point. Keep a separate file backup to protect the actual works.

<a id="maintenance"></a>
### Delete caches or saved thumbnails

Choose the target under storage maintenance in Settings and follow its confirmation.

| Control | Target |
|---|---|
| `Delete browser cache` | Browser cache; cookies, sign-in state, LocalStorage and IndexedDB remain |
| `Delete download cache` | App-managed download cache |
| `Delete saved thumbnails` | Saved thumbnails; regenerate/reacquire them when needed |

To fill missing official images, use `Manage` → `Check/fill official thumbnails`. It checks what can be acquired for works without a saved official thumbnail, rather than reacquiring those already saved.

<a id="health"></a>
### Diagnose library issues and review candidates

Open `Manage` → `Library Health` to diagnose reachability, display metadata, relationships and free space. `Recheck` refreshes the diagnosis; state/category conditions filter the results. Diagnosis alone does not move/delete works or automatically change their metadata.

`Manage` → `Action Center` shows Same Work candidates and metadata review items. Use `View in Library` to inspect a work, then `Add to Same Work Stack` / `Edit metadata` to act on it. Enable `Show ignored items` to review previously ignored items. A candidate appearing does not merge or delete files.

<a id="language"></a>
### Change the interface language or theme

Use Settings → `Appearance and accessibility`.

- `Language`: choose `Use system language`, `Japanese` or `English`. The change also applies to open application screens.
- `Theme`: choose `Use system setting`, `Light` or `Dark`. Windows High Contrast takes priority.

Changing the interface language does not machine-translate work titles or creator names. Official websites and standard Windows folder dialogs follow their own language settings.

<a id="troubleshooting"></a>
### Troubleshoot by symptom

| Symptom | What to check |
|---|---|
| DLM asks for a destination | [Choose a library](#library), then check that the ★ folder is connected in [Settings](#roots) |
| The embedded browser does not appear | Check WebView2 Runtime and confirm the full ZIP was extracted with `app` beside the EXE |
| Sign-in is rejected | Use another official method or the [external browser](#browser). External sign-in need not apply inside DLM |
| Transfer is at 100%, but no work appears | Check validation/extraction/registration in [DL Center](#progress). GOG needs [finalization](#gog) |
| Japanese names extracted from a ZIP are garbled | Extract again from the original ZIP using 1.3.5 or later. If it is unavailable, use [Redownload](#redownload) from work details and the official provider. Starting the application alone does not repair existing names |
| DLsite part1.exe remains waiting | Check [browser save confirmation](#multipart) and acquire every required later part |
| A work is missing | Clear search/filters, check [hidden works](#bulk) and [connected storage](#roots), then reload |
| You want to register an externally downloaded folder | No standalone arbitrary-folder registration is shipped. Folder selection in existing work details is a validation helper. [Watch Folder](#watch) intake of supported files is a separate feature |
| Video, audio or a model will not open | Content/codecs can fail despite a recognized extension. Use the [default/specialist application](#media) or inspect the physical folder |
| A game launches the wrong file | [Choose a different EXE from details](#games) |
| The ★ destination is disconnected | [Reconnect it](#roots) or explicitly mark another registered folder as ★ |
| Restoring a backup does not restore the works | User-state backups exclude work content. Check the [separate file backup](#backup) |

See [Known Limitations](../KNOWN_LIMITATIONS.md) for scope and [Feedback](../FEEDBACK.md) for reporting problems.

<a id="shortcuts"></a>
### Check keyboard shortcuts

| Application action | Key |
|---|---|
| Library / Continue / Download / Settings | `Alt+1` / `Alt+2` / `Alt+3` / `Alt+4` |
| Focus search | `Ctrl+F` |
| Open saved conditions | `Ctrl+Shift+V` |
| Cycle Library density | `Ctrl+Shift+D` |
| Reload Library | `F5` when rescanning is available |

| Image/PDF viewer action | Key |
|---|---|
| Next / previous | `PageDown` or `Space` / `PageUp`; arrows follow reading direction |
| Beginning / contents | `Home` / `T` |
| Single/spread layout / reading direction | `S` / `R` for images |
| Bookmark | `B` for images |
| Fit to screen / 1:1 | `F` / `O` |
| Full screen | `F11` |
| Permanently delete the current work in fullscreen (with confirmation) | `Shift+Delete` |
| Return to the library during deletion (confirmed deletion continues) | `Esc` |
| Next / previous work | `Shift+PageDown` or `Shift+Space` / `Shift+PageUp`, when a target is available |
| Close help, contents and full screen in that order; close the viewer when none is open | `Esc` |

Some of these keys control playback for video/audio. See the [video/audio table](#media) and `Help`, which changes to match the current media.

[Back to contents](#contents) · [Manual home](../MANUAL.md) · [日本語](ja.md)
