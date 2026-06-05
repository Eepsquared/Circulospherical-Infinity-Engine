# ♾️ Circular Infinity Engine - Development Archive & Chat History

This document serves as the persistent, durable **in-workspace archive** of the full design history, requested features, user decisions, and development checkpoints for the **Circular Infinity Engine**. 

Because chat platform windows may refresh or clear across sessions, this file is **actively updated by the assistant at every checkpoint/version** to preserve 100% of your progress, documentation, and customization instructions.

---

## 📅 Project Metadata
* **App Name:** Circulospherical Infinity Engine
* **Current Version:** v1.16 (Stable)
* **Status:** Build succeeds perfectly (`npm run build` is 100% green).
* **Environment:** React-free high-performance pure HTML5 / JS Canvas hybrid structure for sub-millisecond drawing loops.

---

## 🚀 Chronological Chat History & Feature Versions

### 📍 Version 1.01: Core Engine Initialization & Infinite Math
* **User Intent:** Create a mathematically sound, mesmerizing interactive art piece of nested orbits, spirals, or geometric curves.
* **Implementation:** 
  * Designed an ultra-high performance canvas scheduler rendering hundreds of nested circular structures with dynamic coordinates.
  * Added floating control panel supporting live updates to orbital counts, frequencies, decay parameters, and colors.
  * Implemented local-storage-based preset persistence.

### 📍 Version 1.02: UI Expansion & Layout System (Float vs. Dock)
* **User Intent:** Allow user to either have controls floating over the art or rigidly docked on the side like a sidebar.
* **Implementation:**
  * Created the `Dock to right` toggler (`#cie-dockBtn`).
  * Built double resize handle systems:
    * **Docked Mode:** Side resize handle (`#cie-resize-handle`) allowing smooth width setting.
    * **Floating Mode:** Corner/edge resize boundary handles (`.cie-resize-edge`) enabling custom bento sizing over the canvas.

### 📍 Version 1.03: Ping-Pong Animations & Wobble Parameters
* **User Intent:** Introduce automated, sweeping movement for parameters with custom bounds to create dynamic organic breathing motion.
* **Implementation:**
  * Integrated the "Ping-Pong" ↔ toggler buttons for advanced parameters (e.g., `wobbleAmp`, `wobbleFreq`, `distortAmp`, `distortFreq`, `chromaAmt`, `scanlinesOp`, `scanlinesSp`).
  * Added dynamic **Ping-Pong Boundary Popovers ⊞** where user can input individual Min/Max bounds for any animating parameter.
  * Rendered custom overlay indicators directly inside/around range sliders to visually highlight active sweep ranges.

### 📍 Version 1.04: Keyboard Pan, Scroll, and Recenter controls
* **User Intent:** Introduce standard controls to navigate the infinite canvas smoothly.
* **Implementation:**
  * Added mouse-drag pan, shift-drag rotate, and scroll/pinch zoom.
  * Configured reliable native keyboard listeners:
    * `W` `A` `S` `D` to pan the canvas Up, Left, Down, and Right.
    * `Q` / `E` to rotate left and right.
    * `ArrowUp` / `ArrowDown` to zoom.
    * `Space` to Pause/Resume, `R` for design randomization, `F` for Fullscreen, `H` to hide the panel, and `M` to minimize it.

### 📍 Version 1.05: SVG Preservation, Mini Visualizer, and CSS Clean-ups
* **User Intent:** Polish look and feel, fix rendering blanking artifacts on resize, and make sharing visual.
* **Implementation:**
  * Resolved canvas "blanking" during resize observers by caching double-buffered canvas pixel data to offscreen buffers and restoring them immediately after resize.
  * Integrated a highly performant **Mini Audio/Value Visualizer** inside the options tab.
  * Updated the "Copy Share Code" action to use a modern, minimalist nested sharing SVG button:
    ```svg
    <svg viewBox="0 0 24 24" width="11" height="11">...</svg>
    ```

### 📍 Version 1.06: Temporal Motion Blur, Global Timeline Scrubbing, and Control Polish
* **User Intent:**
  * Rename "Global Speed" to "Global speed", removing custom bolding/color styles.
  * Introduce a high-fidelity motion blur effect by using a temporal blending technique where the current frame is lightly mixed with a stored history of previous frame transforms.
  * Add a global 'Timeline' slider that lets the user manually scrub through the animation phase to inspect specific geometric moments.
* **Implementation:**
  * **Global speed Control Polish**: Lowercase-renamed the label and validated its CSS properties so that it inherits standard `.cie-label` properties without extra bolding or color overrides.
  * **Global Timeline Slider**: Placed a master Timeline slider right below Global speed in the Anim tab. Built custom bindings that dynamically animate the slider in loop-step with `pTime` during play, but instantly override `pTime` and proportional `rTime` if the user scrubs it manually (via mouse dragging or manual number field changes), updating the canvas immediately when paused.
  * **Temporal Motion Blur**: Configured a state history buffer (`transformHistory`) to cache previous transforms, zoom factors, and color theme phases on active frames. Created a localized state drawer `drawSingleState` to redraw previous snapshots with smooth exponential-decay opacities underneath the current frame. Natively incorporated "Enable", "Steps", and "Intensity" configs as third-wave parameters with reset/limit/ping-pong integrations inside the FX panel.

---

### 📍 Version 1.07: Audio Reactivity, Undo/Redo Shortcuts, Infinite Zoom, and Control Restructuring
* **User Intent:**
  * Implement an audio input analyzer mapping ambient sound to visual parameters.
  * Implement a lightweight state-history undo/redo buffer supporting `Ctrl+Z` / `Ctrl+Y`.
  * Add an Infinite Zoom option with automatic depth clamping.
  * Restructure controls to dock the action bar at the footer in a single scrollable pane.
  * Remove slow overlapping "Mirror" and redundant modes "2-Way H Inverted" and "2-Way V Inverted".
* **Implementation:**
  * **Audio Input Analyzer**: Created Web Audio API analyzer mapping real-time frequency data dynamically to 'Pulse' and 'Wobble' parameters automatically when Enable Mic is checked. Added Sensitivity and Smoothing controls to options.
  * **Undo/Redo State History**: Built a slider parameter history queue. Hooked 'change' event listeners into all parameters and custom global keystrokes `Ctrl+Z` / `Ctrl+Y` to let user backtrack visual setups instantly.
  * **Infinite Zoom Option**: Added an "Infinite" checkbox next to Viewport "Zoom". Calculated dynamic visual shift patterns and levels (`levelShift`) to continuously render default base depths (6 for 3d4plus/4-way cross, 8 for others) on mathematical sub-levels while scaling, avoiding pixelation or blank screens.
  * **Action Bar Unification**: Unified `#cie-action-bar` as an integrated footer component inside `#cie-controls` window, preserving proper vertical scrolling of standard menus, and widened docked mode default setting to `256px` to keep headers on a single line.
  * **Refined Modes & Features**: Removed laggy nested `Mirror (H+V)` renders, and cleaned up redundant inverted modes (`2hi` / `2vi` replaced with standard geometric dual renders).

---

### 📍 Version 1.08: Visual Polish, Action-Bar Nesting, and Filter Fixes
* **User Intent:**
  * Fix the CSS canvas invert filter behavior.
  * Correct vertical flow nesting for `#cie-action-bar` to restore container-height scrolling correctness.
  * Refine sharing and action bar icon assets (SVG width/height and high-fidelity emojis).
* **Implementation:**
  * **Invert Action Correction**: Fixed the active Canvas invert state filter check so that default color-inverting behaves precisely under native filters without visual flickering.
  * **Action Bar DOM Nesting Refinement**: Moved `#cie-action-bar` inside the `.cie-content` DOM hierarchy, ensuring that all action items flow cohesively alongside options parameters and maintain strict scroll boundary limits inside the docked sidebar.
  * **High-Definition Sharing & Export Assets**: Upgraded the action button configurations, perfecting SVG viewBox styling dimensions to `12px` and updating the export button to use high-contrast multi-colored `🖼️` representations.

---

### 📍 Version 1.09: Infinite Zoom Performance Optimizations, Smooth Multi-Strobe Fading, 3D Pitch Control, and Visual Polish
* **User Intent:**
  * Fix background resetting flashing on bg fade.
  * Implement smooth color-cycling transitions in multi-strobe.
  * Solve infinite zoom framerate drop / premature culling.
  * Allow 3D pitch/vertical model rotation using Shift + Mouse-drag.
  * Clean up and rename options and controls labels (remove "Enable" prefixes, apply proper title tooltips, rename sliders per specs, and add iconic emojis).
  * Auto-hide child dynamic speed and multi-strobe controls if dynamic parent selections are static/inactive.
* **Implementation:**
  * **Background Smooth Sweeping**: Avoided clearing and solid-filling the canvas during `bgFade` transitions by cache-shielding background frames inside `lastBGKey` on the main drawing thread, while clearing it selectively only on state loads.
  * **Continuous Theme Interpolation**: Implemented a super-smooth continuous theme-shifting formula in `getColor` using dual-index blending with floating-point multipliers, turning choppy multi-strobe steps into an elegant fluid rainbow flow.
  * **Infinite Zoom Screen Culling & Depth Preservation**: Solved zoom framerate drop by adding a screen-space bounding check in all recursive drawing levels (`drawRec`, `drawOneWayNested`, `drawNode3D`); if huge parent circles expand completely outside screen dimensions, their canvas render commands are culled, boosting framerate from 11 fps back to 60 fps. Preserved continuous depth loops by rendering outer levels down to offset level `levelShift - 2` with automatic sub-level color pinning.
  * **Interactive 3D Vertical Rotation (Pitch)**: Implemented shift-drag vertical mouse movement mapping to a newly introduced global `manualRotY` pitch parameter. Integrated pitch into node coordinate mappings of "3D 4-Way+" recursive projection steps to rotate the 3D model on its Y/Z axis.
  * **Control Renaming & Iconic Emojis**: Cleaned up the controls panel to use human, modern UI casing rules, renamed sliders (`Zoom scale width`, `Depth orbit`, etc.), removed raw "Enable" prefixes in checkboxes, added high-fidelity cursor status tooltips ("On/Off"), and integrated helpful iconic representation emojis (🌐, ⏱️, 📏, 🔍) across labels.
  * **Dynamic UI Auto-Hiding**: Programmed the sidebar to fully auto-collapse child inputs (`cie-cycleSpeedRow`, `cie-multiStrobeSection`, `cie-modeSpeedRow`) when dynamic parent settings are configured as static color or static mode, decluttering the options pane.

---

### 📍 Version 1.10: State-Preserved Floating Panel Transitions
* **User Intent:**
  * Resolve a layout bug wherein the controls panel shrunk permanently to a narrow, squished 210px width upon being undocked (floated) from the right side of the workspace, which distorted control elements and gave the impression that an older, degraded version of the app interface was loaded.
* **Implementation:**
  * **Interactive Floating State Capture**: Created memory-allocated storage indicators (`floatTop`, `floatLeft`, `floatRight`, `floatWidth`, `floatHeight`) that capture the exact bounding properties and positioning styles of the floating GUI panel immediately before docker integration transforms.
  * **Fidelity Transition Restoration**: Modified the `.cie-dockBtn` listener to swap the saved spatial coordinates and resized width dimensions seamlessly back onto the panel during float-conversion cycles. Replaced the static, disruptive `210px` reset with a smooth class fallback that preserves the signature 260px wide layouts or the user's custom-resized workspace configurations.

---

### 📍 Version 1.11: High-Precision Slider Limits, Drag-and-Drop Limit Overlays, Vertical Scroll Fixes, and Aesthetics
* **User Intent:**
  * Enable live dragging of slider limit markers and ranges.
  * Prevent limit marker text wrap and add a quick limits range reset button.
  * Fix index rounding freeze issues where standard sliders get stuck at 0.075 when limit is 0.
  * Correct docked sidebar height scrolling by fixing premature HTML tag closures.
  * Implement dark-themed custom scrollbars (matching Google AI Studio).
  * Enable the canvas "Invert colors" checkbox and wire options menu Help listener.
  * Optimize high-frequency FPS calculations to skip update calculations when hidden.
* **Implementation:**
  * **Interactive Limit Dragging**: Engineered custom drag-and-drop event handlers supporting touch/mouse listeners to update custom ping-pong boundaries dynamically on hover-drag. Configured `width: max-content` layout settings to prevent marker labels from folding.
  * **Interactive Range Resets**: Programmed popover automatic asset injection, dynamically placing range-reset buttons `↺` next to popover close handlers to restore default limits with a single click.
  * **Sub-Step Precision Animation (`ppValues`)**: Solved the `0.075` step-rounding freeze by storing animating values in a sub-step high-precision cache `ppValues`, avoiding browser range-input precision constraints.
  * **HTML Tag Restructure & Unified Scrolling**: Identified and eliminated a premature duplicate closing `div` within the FX tab, preserving `#cie-content`'s coverage of 'designs' and 'options' panes. Formatted all panel scrollbar aesthetics with deep charcoal scrollbars mirroring Google AI Studio.
  * **Interactive Polish**: Mapped click listeners to both help buttons, configured a high-performance CSS filter toggler on the main canvas element to invert all canvas colors instantly on checkbox toggle, and skipped FPS calculations entirely by default.

---

### 📍 Version 1.12: Unified Docked Scrollbar Layouts, Dynamic Canvas Color Inversion, and Persistent Section Signposts
* **User Intent:**
  * When the control panel is docked, keep the 'action bar' always visible at the bottom while the rest of the control panel vertically scrolls.
  * Add and show clear, readable section signpost names at the top of each tab panel section when docked.
  * Move the simple inline 'invert canvas' checkbox out of the Background Color section and restructure it as a fully configured 'Invert color' control group with modern interactive controls (reset, numeric inputs, range limits, and high-frequency dynamic ping-pong animations).
* **Implementation:**
  * **Docked Footer Unification**: Repositioned the unified `#cie-action-bar` directly beneath the scrollable `#cie-content` DOM container within the parent `#cie-controls` div. Adjusted display structures to render `#cie-content` with full flexible vertical scrolling while keeping the action bar pinned statically to the bottom in docked view states.
  * **Persistent Section Headers**: Engineered custom CSS rules and added declarative `.cie-docked-section-header` signposts (Main, Anim, FX, Designs, Options) indicating section locations, contextually activated exclusively during docked Sidebar state layouts.
  * **Interactive Color Inversion Slider**: Restructured the hidden `#cie-invert` checkbox into an interactive range slider element inside its own dedicated 'Invert color' group, complete with reset listeners, manual precision numerical inputs, limit popovers, and automated logarithmic speed checkboxes/randomizations. Coerced legacy checkbox configurations to continuous floating-point numeric states dynamically inside the setting loader to ensure full backward compatibility.

---

### 📍 Version 1.13: 3D Spherical Infinity Engine Pattern Expansion, Default Control docking, and custom CSS Number inputs
* **User Intent:**
  * Implement 3D render patterns: rename "Mode" to "Pattern" to distinguish 2D and 3D.
  * Create a new "3D 2-Way Horizontal" rendering pattern with true 3D spatial geometry branching.
  * Adapt title bar of the application: dynamically rename title to "Spherical Infinity Engine v5.1" in 3D patterns, and keep "Circular Infinity Engine v5.1" in 2D patterns.
  * Default control panel container to the docked state layout.
  * Customize built-in up/down spinner arrows of number inputs to be narrower and colored `#838383`.
* **Implementation:**
  * **3D 2-Way Horizontal Pattern**: Added a high-fidelity 3D spatial branching model `draw3D2H` that recursively positions and projects circles along the X-Z projection coordinates. Handled safe recursion boundaries up to depth level 9. Expanded randomized preset lists, mouse drag rotations, and safety limits.
  * **Dynamic Title Bar Styling**: Subscribed the header banner and browser document title to the Active Pattern state. Whenever a 3D pattern (names starting with `3d`) is active, updates text to `Spherical Infinity Engine v5.1` dynamically; reverting automatically to `Circular Infinity Engine` in 2D.
  * **Default Docking Layout**: Transferred `#cie-controls` container to initial docked classing inside CSS and HTML, initialized startup coordinate states to `isDocked = true`, and configured the initial icon action mapping for the sidebar-dock toggle to Float Panel state.
  * **Built-in input Number Spinner Customization**: Styled the browser's built-in step buttons (`::-webkit-inner-spin-button`) with high-priority widths of `8px`, utilizing high-performance CSS filters (brightness/contrast combination) to shade them to a matching `#838383` visual tone without breaking native click functionality.

---

### 📍 Version 1.14: Multi-Scale Speed Dropdowns, Global speed Ping-pong Loop Fix, and Help Tooltips
* **User Intent:**
  * Fix 'Global speed' ping-pong animation freeze/lock when values sweep below 0.05.
  * Add a 'Sync breath' detail description row within the help modal animation submenu.
  * Replace '.cie-speed-chk' custom speed checkboxes and logs text with a `╭╯` dropdown overlay select containing Linear, Exponential, Factorial, Gompertz growth, Hyperbolic, Logarithmic, Logistic s-curve, Polynomial (cubic), Polynomial (quadratic) mathematics.
* **Implementation:**
  * **Global speed Ping-pong Lock Correction**: Updated the step modifier math in `runPP` to clamp the active speed factor at minimum threshold limit `0.05` ONLY for the `globalSpeed` parameter, allowing smooth continuous directional reversals without crossing below 0 or getting locked.
  * **Sync breath Help Documentation**: Injected a help card row outlining that 'Sync breath' maps breath oscillations directly to rotation/pTime phase steps instead of the dynamic timeline.
  * **High-Contrast Multi-Scale Speed Selectors**: Replaced speed checkboxes with a streamlined `╭╯` select container overlay. Features highlight indicators (color swaps from high-contrast yellow if active, to standard slate grey if linear) and standard tooltip mappings.
  * **Advanced Math Scale Evaluator**: Implemented mathematical equations for each selector setting inside `runPP()`, executing true factorial approximation, Gompertz growth curves, logistic S-curves, cubic/quadratic polynomials, log/exp curves, and hyperbolas inside the render-loop update thread.

---

### 📍 Version 1.15: Static Unified Title Sync & Interactive Sticky Section Headers
* **User Intent:**
  * Adopt a single global naming strategy starting with "Circulospherical Infinity Engine" without changing the header text or browser document title dynamically when swapping between 2D and 3D patterns.
  * Facilitate effortless version editing in the future by automatically matching header references to the main HTML document title.
  * Enhance docked sidebar navigation by making the segment signposts sticky; keeping the active section's header visible at the top of the pane during scroll ranges, until the subsequent section pushes it up.
* **Implementation:**
  * **Static Unified Title Synchronization**: Eliminated dynamic title text manipulation logic in the main loop. Programmed a lightweight startup script reading `document.title` and binding it instantly to both the header `.hdr-text` and help menu title header `#cie-help-title`, protecting static, seamless future version bumps.
  * **Interactive Sticky CSS Headers**: Modified `.cie-docked-section-header` styles in CSS, applying `position: sticky; top: 0; z-index: 10;`. Anchored by the scrolling `.cie-content` body, headers now intelligently hover and stack sequentially on scroll, improving control visibility.

---

### 📍 Version 1.155: Interactive Hover & Tap Label Micro-Animations
* **User Intent:**
  * Add a gorgeous chromatic aberration style to the "Chroma split" label that splits red and cyan colors on hover or tap.
  * Implement professional micro-effects for "Motion blur" (horizontal motion trailing blurs), "Vignette" (radial-like linear fade on start & end boundaries), "Steps" (stagger-animates letters vertically to form steps), and "Feedback echo" (layered echoing text-shadows).
  * Increment the version number specifically by a minor bump of 0.5 to 1.155 to signify localized layout and styling modifications.
* **Implementation:**
  * **Chroma split Aberration**: Engineered keyframe animation `cie-chroma-anim` producing rapid, vibrant red and cyan shifting text-shadows to recreate realistic digital chromatic aberration on hover and tap configurations.
  * **Velocity Motion Blur**: Built speed-tracking shadow tails translating elements horizontally with slight horizontal blurs (`filter: blur(0.6px)`) simulating motion traces.
  * **Vignette Edge Fading**: Integrated elegant linear gradient text backgrounds with `background-clip: text;` masking edge limits selectively.
  * **Pulsed Echo Shadows**: Programmed oscillating text-shadow replicas moving and fading out outwards horizontally to emulate sonic or acoustic echo trails.
  * **Staircase Step Animation**: Restructured the "Steps" label to enclose each character individually. Configured stagger timing delays and vertical transformations so characters ascend sequentially to form a stair step.

---

### 📍 Version 1.16: Infinite Zoom Performance Optimizations, Color Refactoring, and FX Associations
* **User Intent:**
  * Fix the extreme zoom performance lag by resolving state culling limits.
  * Assure all FX interactive checkbox label controls toggling functions dynamically sync with checking actions.
  * Restructure visual inverting layouts, limit Background invert to background layer, and implement a dedicated independent Line color invert option.
  * Apply aesthetic hover animations to Distance, Spacing, and Scanlines labels.
  * Bump engine version to 1.16.
* **Implementation:**
  * **Infinite Zoom Spatial Culling Fix**: Identified that the global variable `currZFact` was never assigned the actual rendering scale, rendering screen bounding culls inactive at high zooms and causing drop to 11 FPS. Hooked progressive value assignments `currZFact = zFact` inside the core render frame loop, boosting rendering framerate to a smooth 60 FPS constraint.
  * **Interactive Label Clicking Sync**: Associated all checkbox inputs directly with their accompanying visual label elements using custom inline `for` attributes, allowing users to toggle checkboxes cleanly by tapping anywhere on the text.
  * **Line & Background Invert Separation**: Added a separate mathematical line-color invert slider `cie-lineInvert` right under Line Color section. Extracted background elements (background pickers, fading ranges, and background color invert toggles) into a beautifully self-contained `Background` option box, mathematically inverting and rendering colors independently without bulky global canvas filters.
  * **Subtle Hover Animations**: Connected a `'s p a c e d  o u t'` spacing zoom transition to 'Spacing' and 'Distance' labels. Hooked a dynamic scanning animation to the 'Scanlines' parent label for instant interactive visual feedback.

---

## 🛠️ Complete Feature Index & Shortcuts

| Hotkey / Control | Action | Details |
| :--- | :--- | :--- |
| **`Space`** | Pause / Resume | Freezes the animation math immediately |
| **`R`** | Randomize Design | Swaps all parameters to a beautifully computed procedural art matrix |
| **`F`** | Toggle Fullscreen | Expands the canvas experience to the full display size |
| **`H`** | Hide UI | Toggles visibility of the entire controls panel |
| **`M`** | Minimize Menu | Collapses controls to a tiny top bar |
| **`W` / `A` / `S` / `D`** | Pan Canvas | Iteratively shifts current `panX` and `panY` coordinates |
| **`Q` / `E`** | Rotate View | Iteratively rotates the viewport transform matrix |
| **`↑` / `↓` (Arrow Keys)** | Zoom | Scales canvas graphics smoothly around center coordinate |
| **Mouse Drag** | Free Pan | Left click & drag over the empty background space to pan |
| **Shift + Drag** | Rotate | Rotates around the canvas center point |
| **Scroll / Pinch** | Scale | Zoom in and out seamlessly |
| **`Timeline` Slider** | Manual Scrubbing | Drag to manually drive and inspect specific geometric moments in real time |
| **`Motion Blur` Setup** | Temporal Trail FX | Blends past frame transforms procedurally beneath the current scene |

---

## ⚙️ Build and Development Configuration
Your environment is configured with **Vite** serving index.html instantly on Port 3000. Under the hood, the project is configured with zero external heavy frameworks to safeguard peak performance and render loop latency:

* **Entry point:** `/index.html` (embedded styles, control panel HTML, Canvas, WebGL/2D mathematical shading context, and event listeners).
* **Styles:** Clean dark-mode layout with customizable borders, custom sliders, responsive popover positioning, and dynamic range overlays.
* **Packaging:** `/package.json` with scripts:
  * `npm run dev` — local development server on port 3000 list.
  * `npm run build` — static compilation to `/dist` to guarantee fast delivery via Cloud Run.

---

## 📝 Guidelines for Next Sessions
1. **Never Discard History:** The AI agent must always read `/CHAT_HISTORY.md` at the beginning of the journey to align with the complete state of the art.
2. **Synchronous Updates:** When adding a new feature, slider, parameter mapping, or audio utility, append it to the [Chronological Chat History](#) sections above.
3. **Save and Build Verify:** Complete validation with `compile_applet` before closing a turn.
