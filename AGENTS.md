# Custom Agent Guidance (AGENTS.md)
1. **Persistent History Maintenance:** Keep the dynamic `/history.md` updated at every milestone (version) or when a new feature is requested and successfully implemented. Ensure no history of prior user features (e.g., effects, controls/hotkeys/keyboard shortcuts, SVG buttons, etc.) is ever discarded.
  * **Never Discard History:** The AI agent must always read `/history.md` at the beginning of, and after each checkpoint during, the session to align with the complete project history.
  * **New/changed content:** When adding a new, or changing/removing an existing feature: effect, feature, user interface (UI) element "control" (button, checkbox, input number/range, textarea, etc.), parameter mapping, audio utility, etc.:
    * **TEST TEST TEST!:** Thoroughly test each new/changed/removed feature with existing features to ensure compatibility and functionality works as intended. Test every constant, variable, function, parameter, control, and element relating to the added/changed/removed feature. Were all axes (rotation and/or translation) directions, speeds, times, etc. included? Does one effect affect another effect in certain specific instances (i.e. line thickness messing up 3D color gradient single-axis rotation at certain angles)?
    * **Synchronous Updates:** Append changes to `history.md`.[Chronological Feature Version History](#) section.
  * **Save and Build Verify:** Complete validation with `compile_applet` before closing a turn.
  * **App version incrementing:** When updating the app version, use semantic versioning: Major.Normal/Minor.Patch/Bug-fix (without adding `.0` to any part) as defined by certain changes:
    * Major: many (5+) new features, can include bug-fixes; user prompt will let AI agent know; increment app version by 1 (non-negative integers).
    * Normal/Minor: some (`<`5) new features (mostly UI-related), can include bug-fixes; increment app version by 0.1 (tenths) or 0.01 (hundredths), depending on current version number (i.e. `1.0` to `1.1`, not `1.10`; but `1.10` to `1.11` is correct).
      * After many patch/bug fixes, depending on their severity and resolution, it is acceptable to increase the normal/minor number so as to not get "bogged down" in deep version numbers (i.e. `x.xx.53`) and give some feeling of app development progress.
    * Patch/Bug fix: bug-fixes *only*; increment version by 0.0.1 (1 thousandths separated by a decimal)
    * The AI agent will ask the user prompter if AI agent is unsure what constitutes "major", "normal", "minor", and/or "patch"/"bug-fix" changes. *DO NOT ASSUME/OVERRIDE EXPLICIT VERSION NUMBERS*: i.e. if told to update app version to `x.x7.9` do *not* change the number to `x.x8.0`. Similarly, if told to update to version `x.xx` do *not* append a `.0`.
  * **Update on manual edit:** whenever a "manual edit" ("I made some changes." prompt) is done (except for edits to `history.md`), append a summary of the manual edit to the last (most recent) app version in `history.md`, unless otherwise instructed.

2. When a hotkey/keyboard/touch control is added, changed/updated, and/or deleted/removed, ensure `index.html`'s `#cie-help-overlay` 'Controls' section, and `.cie-tab-panel` 'Options' > 'Controls' section are updated.

3. **Framework Choice Preservation:** This application is configured as a fast, low-latency, React-free standard HTML5 Canvas/JS app. Always adhere strictly to this native JavaScript architecture; do not introduce complex client-side frameworks unless explicitly requested.

4. **Double-Buffered Performance:** When optimizing drawings or resolving canvas window resize issues, preserve off-screen image caching and double-buffered drawing buffers to avoid screen flashing or blanking.