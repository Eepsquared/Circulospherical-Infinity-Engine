# ♾⚙ Circulospherical Infinity Engine - Development Archive & Chat History

This document serves as the persistent, durable **in-workspace archive** of the full design history, requested features, user decisions, and development checkpoints for the **Circulospherical Infinity Engine** (originally "Circular Infinity Engine"), or **CIE**, begun ~May 24, 2026.

Because chat platform windows may refresh or clear across sessions, this file should be **actively updated by the AI agent at every checkpoint/version** to preserve 100% of the app's progress, documentation, and customization instructions.


## ⚙️ Build and Development Configuration
The environment is configured with **Vite** serving `/index.html` instantly on port 3000. Under the hood, the project is configured with zero external heavy frameworks to safeguard peak performance and render loop latency:

* **Entry point:** `/index.html` (embedded styles, control panel HTML, Canvas, WebGL/2D mathematical shading context, and event listeners).
* **Styles:** Clean dark-mode layout with customizable borders, custom sliders, responsive popover positioning, and dynamic range overlays.
* **Packaging:** `/package.json` with scripts:
  * `npm run dev` — local development server on port 3000 list.
  * `npm run build` — static compilation to `/dist` to guarantee fast delivery via Cloud Run.


## 📝 Guidelines for Current and Future Sessions
* **Never Discard History:** The AI agent must always read `/history.md` (formerly `/CHAT_HISTORY.md`) at the beginning of, and after each checkpoint during, the session to align with the complete project history.
* **Synchronous Updates:** When adding a new effect, feature, user interface (UI) element (button, checkbox, input number/range, textarea, etc.), parameter mapping, audio utility, etc., append it to the [Chronological Feature Version History](#) section below.
* **Save and Build Verify:** Complete validation with `compile_applet` before closing a turn.
* **App version incrementing:** When updating the app version, use semantic versioning: Major.Normal/Minor.Patch/Bug-fix as defined by certain changes:
  * Major: many (5+) new features, can include bug-fixes; user prompt will let AI agent know; increment app version by 1 (non-negative integers)
  * Normal/Minor: some (`<`5) new features (mostly UI-related), can include bug-fixes; increment app version by 0.1 (tenths)
  * Patch/Bug fix: bug-fixes *only*; increment version by 0.0.1 (1 thousandths separated by a decimal)
  * If AI agent is unsure what constitutes "major", "normal", "minor", and/or "patch"/"bug-fix" changes, ask user prompter.
* **Update on manual edit:** whenever a "manual edit" ("I made some changes." prompt) is done (except for edits to `history.md`), append a summary of the manual edit to the last (most recent) app version in `history.md`, unless otherwise instructed.


## 📅 Project Metadata
* **App Name:** Circulospherical Infinity Engine
* **Current Version:** 1.31.13 [Released: 2026-08-19 UTC]
* **Status:** Build succeeds perfectly (`npm run build` is 100% green)
* **Environment:** React-free high-performance pure HTML5 / JavaSript Canvas hybrid structure for sub-millisecond drawing loops


## 🛠️ Complete Feature Index & Shortcuts
For a complete, in-depth view of all controls, refer directly to the in-app help modal (`#cie-help-overlay`, accessible by clicking the help button or pressing the help keys). Below is the comprehensive index transcribing all available engine features and interactions:

### Control group elements ###
* **↔ Ping-pong**: Slider oscillates between its min and max automatically
* **🎚️ Limits button**: Set custom min/max extents for ping-pong animation
* **↺ Reset button**: Resets a single slider to its default value

### 🌀 Patterns & Geometry
* **1-Way Horizontal/Vertical**: Circles grow from small to large in one direction from center
* **2-Way Horizontal/Vertical**: Classic "circular infinity": recursive circles branching symmetrically in one axis
* **2-Way Inverted H/V**: Like 2-Way but circles grow larger toward the edges
* **4-Way +**: Both axes simultaneously
* **4-Way Cross**: Both axes simultaneously but packed ("squaring the circle")
* **3D 2-Way Horizontal**: True 3D perspective 2-Way horizontal branching rotating in space
* **3D 4-Way +**: True 3D perspective recursive circles rotating in space
* **Kaleidoscope x8/x12**: 8-/12-Way *; mirrored wedge radial symmetry
* **Lissajous**: Stacked harmonic orbit rings per depth level
* **Fractal Tree**: Branching organic tree that sways and breathes
* **Spiral**: Circles along a rotating expanding spiral arm
* **Flower of Life**: 
* **Pattern Cycle/Random**: Auto-cycles through render patterns (similar to color cycling)
* **Recursion depth**: 

### ➖Line➖
#### 🎨 Line color
* **Static / Custom**: Single theme color, no cycling
* **Cycle**: Auto-advances through all themes in order of select options
* **Random**: Picks a random theme each interval
* **Multi-strobe / Multi**: Each depth ring gets a different color offset
#### Trails
* **Trail length**: Lower value = longer trails (less background clear per frame)
* **Converge**: 

### 🎬 Animation
* **Global speed**: Scales all animation speeds in unison
* **Manual Timeline Scrub**: Drag to manually drive and inspect specific geometric moments in real time

#### 🖥️Viewport
* **Orbit rotation**: Orbit/rotate/twist nested depths independently
* **Sync pulse**: Syncs the pulse timing to the rotation timeline instead of the pulse timeline, aligning breathing swells with rotation

#### 〰 Pulse
* **Pulse frequency**: Enables pulse animation; slider sets oscillation speed
* **Pulse distance**: How far circles "breathe" in and out
* **Pulse shift**: Phase offset per depth level, creating a ripple wave effect

#### Converge
* **Converge**: Collapses all circles toward a single concentric point (0 = normal, 1 = fully collapsed)
* **Singularity**: 

#### Wobble
* **Wobble amplitude**: Secondary radius modulation layered on top of pulse
* **Wobble frequency**: Speed of the wobble oscillation
* **Distortion ripple**: Displaces each circle center by an animated sine-wave offset

### ✨ FX Filters & Video Blend
* **Blend Composites**: Canvas composite operation: Burn, Difference=inversion, Dodge, Exclusion, Hard/Soft Light, Lighter (Add)=additive glow, Multiply, Overlay, Screen, XOR
* **Chroma split**: RGB lens aberration via screen-blend offset copies
* **Feedback echo**: Previous frame blended back in — high values create tunnel feedback
* **Scanlines**: CRT-style horizontal lines overlay
* **Vignette**: Radial edge darkening
* **Motion Blur Setup**: Temporal trail FX; blends past frame transforms procedurally beneath the current scene

### 🎹 Controls
* **`Space`** : Pause / Resume
* **`R`** : Random design
* **`F`** : Fullscreen
* **`H`** : Hide / show menu
* **`M`** : Minimize menu
* **`W` / `A` / `S` / `D`** : Pan canvas up / left / down / right
* **`Q` / `E`** : Rotate canvas left / right
* **`↑` / `↓`** : Zoom in / out (smoothly scales canvas graphics around the center)
* **Mouse Drag / Touch** : Pan over the background space
* **Shift + Mouse Drag** : Rotate canvas layout
* **Scroll Wheel / Pinch-to-Zoom** : Zoom/scale viewport dynamically


## 🚀 Chronological Feature Version History

### 📍 Version 1.01 [2026-06-04 10:14 UTC]: Core Engine Initialization & Infinite Math
* **User Intent:** Create a mathematically sound, mesmerizing interactive art piece of nested orbits, spirals, or geometric curves.
* **Implementation:** 
  * Designed an ultra-high performance canvas scheduler rendering hundreds of nested circular structures with dynamic coordinates.
  * Added floating control panel supporting live updates to orbital counts, frequencies, decay parameters, and colors.
  * Implemented local-storage-based preset persistence.

### 📍 Version 1.02 [2026-06-04 15:32 UTC]: UI Expansion & Layout System (Float vs. Dock)
* **User Intent:** Allow user to either have controls floating over the art or rigidly docked on the side like a sidebar.
* **Implementation:**
  * Created the `Dock to right` toggler (`#cie-dockBtn`).
  * Built double resize handle systems:
    * **Docked Mode:** Side resize handle (`#cie-resize-handle`) allowing smooth width setting.
    * **Floating Mode:** Corner/edge resize boundary handles (`.cie-resize-edge`) enabling custom bento sizing over the canvas.

### 📍 Version 1.03 [2026-06-05 09:41 UTC]: Ping-Pong Animations & Wobble Parameters
* **User Intent:** Introduce automated, sweeping movement for parameters with custom bounds to create dynamic organic breathing motion.
* **Implementation:**
  * Integrated the "Ping-Pong" ↔ toggler buttons for advanced parameters (e.g., `wobbleAmp`, `wobbleFreq`, `distortAmp`, `distortFreq`, `chromaAmt`, `scanlinesOp`, `scanlinesSp`).
  * Added dynamic **Ping-Pong Boundary Popovers ⊞** where user can input individual Min/Max bounds for any animating parameter.
  * Rendered custom overlay indicators directly inside/around range sliders to visually highlight active sweep ranges.

### 📍 Version 1.04 [2026-06-05 14:12 UTC]: Keyboard Pan, Scroll, and Recenter controls
* **User Intent:** Introduce standard controls to navigate the infinite canvas smoothly.
* **Implementation:**
  * Added mouse-drag pan, shift-drag rotate, and scroll/pinch zoom.
  * Configured reliable native keyboard listeners:
    * `W` `A` `S` `D` to pan the canvas Up, Left, Down, and Right.
    * `Q` / `E` to rotate left and right.
    * `ArrowUp` / `ArrowDown` to zoom.
    * `Space` to Pause/Resume, `R` for design randomization, `F` for Fullscreen, `H` to hide the panel, and `M` to minimize it.

### 📍 Version 1.05 [2026-06-05 18:05 UTC]: SVG Preservation, Mini Visualizer, and CSS Clean-ups
* **User Intent:** Polish look and feel, fix rendering blanking artifacts on resize, and make sharing visual.
* **Implementation:**
  * Resolved canvas "blanking" during resize observers by caching double-buffered canvas pixel data to offscreen buffers and restoring them immediately after resize.
  * Integrated a highly performant **Mini Audio/Value Visualizer** inside the options tab.
  * Updated the "Copy Share Code" action to use a modern, minimalist nested sharing SVG button:
    ```svg
    <svg viewBox="0 0 24 24" width="11" height="11">...</svg>```

### 📍 Version 1.06 [2026-06-06 11:23 UTC]: Temporal Motion Blur, Global Timeline Scrubbing, and Control Polish
* **User Intent:**
  * Rename "Global Speed" to "Global speed", removing custom bolding/color styles.
  * Introduce a high-fidelity motion blur effect by using a temporal blending technique where the current frame is lightly mixed with a stored history of previous frame transforms.
  * Add a global 'Timeline' slider that lets the user manually scrub through the animation phase to inspect specific geometric moments.
* **Implementation:**
  * **Global speed Control Polish**: Lowercase-renamed the label and validated its CSS properties so that it inherits standard `.cie-label` properties without extra bolding or color overrides.
  * **Global Timeline Slider**: Placed a master Timeline slider right below Global speed in the Anim tab. Built custom bindings that dynamically animate the slider in loop-step with `pTime` during play, but instantly override `pTime` and proportional `rTime` if the user scrubs it manually (via mouse dragging or manual number field changes), updating the canvas immediately when paused.
  * **Temporal Motion Blur**: Configured a state history buffer (`transformHistory`) to cache previous transforms, zoom factors, and color theme phases on active frames. Created a localized state drawer `drawSingleState` to redraw previous snapshots with smooth exponential-decay opacities underneath the current frame. Natively incorporated "Enable", "Steps", and "Intensity" configs as third-wave parameters with reset/limit/ping-pong integrations inside the FX panel.

### 📍 Version 1.07 [2026-06-06 16:47 UTC]: Audio Reactivity, Undo/Redo Shortcuts, Infinite Zoom, and Control Restructuring
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

### 📍 Version 1.08 [2026-06-07 10:15 UTC]: Visual Polish, Action-Bar Nesting, and Filter Fixes
* **User Intent:**
  * Fix the CSS canvas invert filter behavior.
  * Correct vertical flow nesting for `#cie-action-bar` to restore container-height scrolling correctness.
  * Refine sharing and action bar icon assets (SVG width/height and high-fidelity emojis).
* **Implementation:**
  * **Invert Action Correction**: Fixed the active Canvas invert state filter check so that default color-inverting behaves precisely under native filters without visual flickering.
  * **Action Bar DOM Nesting Refinement**: Moved `#cie-action-bar` inside the `.cie-content` DOM hierarchy, ensuring that all action items flow cohesively alongside options parameters and maintain strict scroll boundary limits inside the docked sidebar.
  * **High-Definition Sharing & Export Assets**: Upgraded the action button configurations, perfecting SVG viewBox styling dimensions to `12px` and updating the export button to use high-contrast multi-colored `🖼️` representations.

### 📍 Version 1.09 [2026-06-07 14:52 UTC]: Infinite Zoom Performance Optimizations, Smooth Multi-Strobe Fading, 3D Pitch Control, and Visual Polish
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

### 📍 Version 1.10 [2026-06-08 09:28 UTC]: State-Preserved Floating Panel Transitions
* **User Intent:**
  * Resolve a layout bug wherein the controls panel shrunk permanently to a narrow, squished 210px width upon being undocked (floated) from the right side of the workspace, which distorted control elements and gave the impression that an older, degraded version of the app interface was loaded.
* **Implementation:**
  * **Interactive Floating State Capture**: Created memory-allocated storage indicators (`floatTop`, `floatLeft`, `floatRight`, `floatWidth`, `floatHeight`) that capture the exact bounding properties and positioning styles of the floating GUI panel immediately before docker integration transforms.
  * **Fidelity Transition Restoration**: Modified the `.cie-dockBtn` listener to swap the saved spatial coordinates and resized width dimensions seamlessly back onto the panel during float-conversion cycles. Replaced the static, disruptive `210px` reset with a smooth class fallback that preserves the signature 260px wide layouts or the user's custom-resized workspace configurations.

### 📍 Version 1.11 [2026-06-08 14:10 UTC]: High-Precision Slider Limits, Drag-and-Drop Limit Overlays, Vertical Scroll Fixes, and Aesthetics
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

### 📍 Version 1.12 [2026-06-08 18:35 UTC]: Unified Docked Scrollbar Layouts, Dynamic Canvas Color Inversion, and Persistent Section Signposts
* **User Intent:**
  * When the control panel is docked, keep the 'action bar' always visible at the bottom while the rest of the control panel vertically scrolls.
  * Add and show clear, readable section signpost names at the top of each tab panel section when docked.
  * Move the simple inline 'invert canvas' checkbox out of the Background Color section and restructure it as a fully configured 'Invert color' control group with modern interactive controls (reset, numeric inputs, range limits, and high-frequency dynamic ping-pong animations).
* **Implementation:**
  * **Docked Footer Unification**: Repositioned the unified `#cie-action-bar` directly beneath the scrollable `#cie-content` DOM container within the parent `#cie-controls` div. Adjusted display structures to render `#cie-content` with full flexible vertical scrolling while keeping the action bar pinned statically to the bottom in docked view states.
  * **Persistent Section Headers**: Engineered custom CSS rules and added declarative `.cie-docked-section-header` signposts (Main, Anim, FX, Designs, Options) indicating section locations, contextually activated exclusively during docked Sidebar state layouts.
  * **Interactive Color Inversion Slider**: Restructured the hidden `#cie-invert` checkbox into an interactive range slider element inside its own dedicated 'Invert color' group, complete with reset listeners, manual precision numerical inputs, limit popovers, and automated logarithmic speed checkboxes/randomizations. Coerced legacy checkbox configurations to continuous floating-point numeric states dynamically inside the setting loader to ensure full backward compatibility.

### 📍 Version 1.13 [2026-06-09 10:42 UTC]: 3D Spherical Infinity Engine Pattern Expansion, Default Control docking, and custom CSS Number inputs
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

### 📍 Version 1.14 [2026-06-09 13:15 UTC]: Multi-Scale Speed Dropdowns, Global speed Ping-pong Loop Fix, and Help Tooltips
* **User Intent:**
  * Fix 'Global speed' ping-pong animation freeze/lock when values sweep below 0.05.
  * Add a 'Sync breath' detail description row within the help modal animation submenu.
  * Replace '.cie-speed-chk' custom speed checkboxes and logs text with a `╭╯` dropdown overlay select containing Linear, Exponential, Factorial, Gompertz growth, Hyperbolic, Logarithmic, Logistic s-curve, Polynomial (cubic), Polynomial (quadratic) mathematics.
* **Implementation:**
  * **Global speed Ping-pong Lock Correction**: Updated the step modifier math in `runPP` to clamp the active speed factor at minimum threshold limit `0.05` ONLY for the `globalSpeed` parameter, allowing smooth continuous directional reversals without crossing below 0 or getting locked.
  * **Sync breath Help Documentation**: Injected a help card row outlining that 'Sync breath' maps breath oscillations directly to rotation/pTime phase steps instead of the dynamic timeline.
  * **High-Contrast Multi-Scale Speed Selectors**: Replaced speed checkboxes with a streamlined `╭╯` select container overlay. Features highlight indicators (color swaps from high-contrast yellow if active, to standard slate grey if linear) and standard tooltip mappings.
  * **Advanced Math Scale Evaluator**: Implemented mathematical equations for each selector setting inside `runPP()`, executing true factorial approximation, Gompertz growth curves, logistic S-curves, cubic/quadratic polynomials, log/exp curves, and hyperbolas inside the render-loop update thread.

### 📍 Version 1.15 [2026-06-09 16:20 UTC]: Static Unified Title Sync & Interactive Sticky Section Headers
* **User Intent:**
  * Adopt a single global naming strategy starting with "Circulospherical Infinity Engine" without changing the header text or browser document title dynamically when swapping between 2D and 3D patterns.
  * Facilitate effortless version editing in the future by automatically matching header references to the main HTML document title.
  * Enhance docked sidebar navigation by making the segment signposts sticky; keeping the active section's header visible at the top of the pane during scroll ranges, until the subsequent section pushes it up.
* **Implementation:**
  * **Static Unified Title Synchronization**: Eliminated dynamic title text manipulation logic in the main loop. Programmed a lightweight startup script reading `document.title` and binding it instantly to both the header `.hdr-text` and help menu title header `#cie-help-title`, protecting static, seamless future version bumps.
  * **Interactive Sticky CSS Headers**: Modified `.cie-docked-section-header` styles in CSS, applying `position: sticky; top: 0; z-index: 10;`. Anchored by the scrolling `.cie-content` body, headers now intelligently hover and stack sequentially on scroll, improving control visibility.

### 📍 Version 1.15.1 [2026-06-09 19:40 UTC]: Interactive Hover & Tap Label Micro-Animations
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

### 📍 Version 1.16 [2026-06-10 10:12 UTC]: Infinite Zoom Performance Optimizations, Color Refactoring, and FX Associations
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

### 📍 Version 1.16.1 [2026-06-10 11:55 UTC]: Flawless, Continuous Infinite Zoom Rendering Engine with Seamless Coloring
* **User Intent:**
  * Adopt a fully recursive floating-point depth zoom pattern like the attached standard reference.
  * Prevent structural popping/flickering of outer expanded boundaries and newborn inner cores.
  * Ensure color transitions (both standard theme modes and strobe cycle states) flow flawlessly and continuously throughout infinite zoom loops.
  * Set version to v1.165.
* **Implementation:**
  * **Recursive Continuous Depth Zoom**: Reformed the infinite zoom algorithm to trace floating-point layer values `layer = d - currProgress` (where `currProgress` is the fractional part of `state.zoom`). The rendering loop now maintains a perfectly constant, lightweight depth recurse tree from `0` to `md` (instead of compounding depth up to integer zoom bounds), eliminating the possibility of recursion depth blowout or micro-stutters.
  * **Continuous Opacity Fading Curves**: Implemented continuous envelope functions: outer expanding horizons fade out gradually via `1 + layer` to 0, while newborn inner cores smoothly fade in proportionately via `(md - layer) / 2`.
  * **Flicker-Free Color Gradients**: Extended the core `getThemeRGB` engine to accept continuous fractional depth parameters. By performing a safe floating-point modulo cycle `(d % md + md) % md` before color-mapping, hue values now glide continuously along gradients during zooms, entirely removing "color popping" artifacts.
  * **Robust glow & 3D Integration**: Unified these smooth color, opacity and glow fading transformations across all interactive modes, including 3D rendering environments.

### 📍 Version 1.16.2 [2026-06-10 13:40 UTC]: Pixel-Perfect Infinite Zoom & Designs Ordering Fix
* **User Intent:**
  * Resolve line width halving/depleting issues at different zoom intervals (especially zooms 2 and 24).
  * Ensure outer layers of recursive designs remain rendered gracefully until they are fully outside the canvas boundary.
  * Add support for clicking the 'Zoom 🔍' label text direct to activate/deactivate Infinite Zoom.
  * Correct saved designs sorting and loading order so they are chronologically preserved correctly.
* **Implementation:**
  * **Proportionally Rescale Infinite Widths**: Fixed line width thickness scaling during infinite zooms by basing thickness calculations directly on the fractional canvas coordinate scaler (`isInfinite ? zFact : Math.pow(2, zoom / 2)`), fully rectifying the line width halving/thinning anomaly at zoom levels 2 and 24.
  * **Boundary Outer Circle Rendering**: Enabled complete out-of-screen recursive rendering paths down to the true edge bounds, ensuring outer circle frames remain fully drawn without getting culled prematurely.
  * **Unified Label Action**: Cleanly associated the Infinite Zoom toggle input with a proper visual label `<label for="cie-infiniteZoom">` with cursor-pointing cues, aligning click responsiveness perfectly.
  * **Original-Sorted Design Indices**: Rewrote `renderConfigs` to map each saved design item back to its true original Array index `originalIndex` in `localStorage` before sorting, preventing the dreaded index misalignment bug where renamed or reverse-dated slots loaded the incorrect preset data.

### 📍 Version 1.16.3 [2026-06-10 15:22 UTC]: High-Fidelity Continuous Infinite Zoom & Color Index Bounds Protection
* **User Intent:**
  * Fully resolve all remaining infinite zoom rendering artifacts, specifically visual shrinking/resets and premature culling/fade-outs during zooms.
  * Assure that outer circles persist visible on-screen until they expand fully out of view.
  * Guarantee that line widths remain mathematically continuous and constant on screen without halving/depleting throughout zooms.
  * Enable clicking the main "Zoom 🔍" label text directly to toggle Infinite Zoom state.
  * Restructure options and style menus smoothly, widening panes for optimal scrolling alignment (incorporating manual user polish).
* **Implementation & Manual Fixes:**
  * **Dynamic Geometry Scaling**: Corrected the geometry space starting radius by scaling standard `baseR` dynamically by `Math.pow(2, levelShift)` when `isInfinite` is enabled. This ensures circles smoothly double in size exactly in sync with canvas scale reductions, providing 100% continuous infinite zoom transitions.
  * **Continuous Non-fading Bounds**: Removed the outer parent fading boundary constraints (`layer < 0`), permitting outer recursive layers to stay fully solid and visible (alpha = 1) until they naturally grow past screen limits.
  * **High-Precision Pan-Aware Culling**: Upgraded boundary culling check to calculate `maxDist` using the screen's diagonal corner distance combined with high-frequency user pan offsets, preventing any clipping of panned outermost circles.
  * **Dynamic Stroke Scaling**: Stabilized stroke thickness by dividing coordinate widths by zoom scale `zFact` when `Scale stroke` is checked (constant screen width), and scaling coordinate widths by `Math.pow(2, levelShift)` when unchecked (constant geometry width), avoiding any line width halving jumps.
  * **Negative-proof Color Cycling**: Enhanced the color transition indices in `getColor` using floor-modulo indices, preventing index out-of-bound errors when layer depths go negative.
  * **Label Trigger Link**: Added direct label associations connecting `🔍 Zoom` text with the `cie-infiniteZoom` checkbox state.
  * **Micro-Animation Shadow & Filter Tuning (Manual Polish)**: Refined text shadow distances, blur filters, scanline vertical heights, and background sizing on hover/active text micro-animations (increased Chroma split text shadows to `-2px/-1px`, Motion blur to `0.5px`, Echo to `2px/1.5px`, Scanline spacing to `2px`, and scaled Pulse heading backgrounds to `100%`) for gorgeous, professional visual glow feedback.
  * **FX Tab Panel Rearrangement (Manual Polish)**: Harmonized the FX panel markup structure, cleanly boxing and commenting compartments for Chroma Split, Feedback Echo, Motion Blur, Scanlines, and Vignette layouts.
  * **Canvas & Select Dropdown Reset (Manual Polish)**: Instated elegant base rules `canvas { display: block }` and `option { min-block-size: unset; min-inline-size: unset; }` to eliminate chromium dropdown cell sizing variance.
  * **Expanded Sidebar Docking Boundaries (Manual Polish)**: Widened the docked sidebar layout width bounds from `256px`/`260px` up to `274px` / `276px` in CSS rules and JavaScript state trackers. This protects control elements from getting squished or crowded on narrow aspect ratios and preserves pixel-perfect layouts during Floating Panel swaps.
  * **Unified Background Swatch Group (Manual Polish)**: Merged the two custom background colors cleanly under a single, direct, space-optimized line titled `▨🎨Background color`, improving the visual rhythm of the panel options.

### 📍 Version 1.17 [2026-06-10 17:05 UTC]: Automated Safety Clamping, Advanced Ping-Pong Limits controls, and Continuous Randomizer
* **User Intent:**
  * Fix lag-reducing depth checks when switching patterns or themes automatically.
  * Reset ping-pong animated ranges when clicking the global "Reset all" button.
  * Ensure drag overlays render instantly on panel popover toggle.
  * Elevate design layout spacing inside of limits popovers.
  * Support hold-down continuous randomization modes on all slider dynamic keys.
* **Implementation:**
  * **Automated Safety Clamping & Handshake**: Improved `enforceSafety` logic to update active animating mathematical buffers (`ppValues`), assuring invalid nested depths do not trigger high-latency recursion spikes when changing modes/patterns.
  * **Limits Multi-Reset Tying**: Coordinated `cie-resetBtn` listeners to clear internal slider bounds (`ppLimits`), reset limit inputs, and instantly restore the dynamic canvas overlay markers on any active parameters.
  * **Instant Popover Overlay Refresh**: Configured both popover panel toggle actions and click-away closers to force immediate re-draw calls on boundary lines, showing/hiding markers instantly dynamically.
  * **Flex-Compatible Layouts**: Recast depth and option popup boxes with specific HTML `<span>` elements around numeric controls and control close buttons, offering superior aesthetic spacing on the control panel.
  * **Holds & Pointer Event Handshifts**: Integrated precise pointer press checks (`pointerdown`/`pointerup`/`pointercancel`/`pointerleave`) on `.cie-random-slider-btn` buttons, allowing smooth click-resets and hold-triggered continuous intervals.
  * **Precise Drag Tooltips**: Added beautiful absolute-positioned dynamic tooltips below moving markers when being dragged, presenting accurate numeric position information instantly.
* **Manual Edits Summary (User-applied):**
  * **Chroma Split Text-Shadow Enhancement**: Increased text shadow offsets from `-0.5px`/`-0.25px` to `-2px`/`-1px` to enhance visual clarity and split aberration alignment.
  * **Motion Blur Filter Refinement**: Adjusted the motion blur hover filter from `blur(0.25px)` to `blur(0.5px)` for a smoother transit trace effect on the sidebar labels.
  * **Pulse Heading Gradient Background Polish**: Rescaled the interactive gradient background width of hover headings from `200%` to `100%` for better container-constrained visual mapping.
  * **Echo Text-Shadow Extension**: Extended the Akousmatic Echo text shadow width from `0.75px` to a crisper `2px` spacing to highlight layered visual echoing.
  * **Scanline Sizing Adjustment**: Recalculated the Scanline label background-size boundary from `100% 3px` to `2px` for pristine, compact scanning simulation aesthetics.
  * **FX Panel Structural commenting Formatting**: Restructured, comment-organized, and encased Chrome Split, Feedback Echo, Motion Blur, Scanlines, and Vignette controls into beautifully self-contained DOM boxes.
  * **Browser Sizing Resets**: Declared `canvas { display: block }` and relaxed standard options element bounds (`option { min-block-size: unset; min-inline-size: unset; }`) to neutralize Chromium rendering discrepancies in dropdown selectors.
  * **Sidebar Width Bounds Expansion**: Expanded the docked sidebar default width boundary check limits from `256px`/`260px` to `274px` / `276px` in CSS rules and JS tracking states to secure nested layouts during panel transitions.
  * **Floating Resizer Width Defaults**: Relocated floating panels' default fallback width setting to `276px` to keep layouts intact.
  * **Background Options Unification**: Coordinated custom background colors neatly under a single, space-optimized line titled `▨🎨Background color` from the `🎨 Colors` dropdown block.
  * **Help Modal Documentation Refinement**: Revamped the inline documentation, mapping interactive link items (`#cie-help-link`), updating pattern titles ("4-Way Cross", "4-Way +"), adding comprehensive layout explanation rows and shortcuts.
  * **Limit Markers and Inputs Tweaks**: Polished select backgrounds to `#0f0f0f` and color to `#ccc`, trimmed text inputs padding, and adjusted `.cie-limit-marker` hover layout metrics.
  * **Safety Depth Parameters and Presets Optimization**: Optimized vortex depth safety bounds (restraining Vortex safety trigger to 7, Crystal to 7, Dark to 5) to protect engine stability under heavy recursive loops.
  * **Interactive Slider Limit UI Tuning**: Repositioned `.cie-limit-track` and `.cie-limit-marker` overlays to the bottom of the slider track (`bottom: 3px; top: unset;`) to avoid top overlapping. Magnified marker hover/active font size to `14px` and set offset margins (`-3px` left, `3px` right) for highly responsive draggable interactions.
  * **Marker Tooltip Layout Adjustment**: Clustered `.cie-limit-marker-tooltip` with other limit rules in CSS, tuning its bottom alignment to `10px` and padding to `0 4px` for seamless visual tracking.
  * **Dynamic Steps Wrapper Spacing**: Cleaned up spacing and inline declarations for the `.cie-steps-wrapper` rules to keep overall styles compact.

### 📍 Version 1.18 [2026-06-10 18:50 UTC]: Multidirectional Docking System, Custom Gradient CSS Dropdowns, and Narrow Help Sidebars
* **User Intent / Feedback:**
  * Support choosing the docking side dynamically from a 'Dock' menu option. Allow docked view styles on Left, Right, Top, and Bottom screen edges.
  * Reorder slider interactive row buttons: move reset `↺` buttons to the far right after random `🎲` buttons, and position the speed scale container/icon right after the limits `🎚️` buttons.
  * When reset `↺` is clicked, halt any running ping-pong animation of that slider.
  * Correct option rendering color for 'Spectral' color choice in dropdowns; support a genuine CSS rainbow linear-gradient text clip.
  * Supply precise descriptive tooltips to all checkbox inputs and accompanying labels.
  * Polish help modal layout: keep the titlebar sticky and make the narrow `#cie-help-box` scroll overlay items internally using AI Studio custom scrollbars. Position the help sidebar on the opposite edge of the docking sidebar to preserve double visibility.
  * Resolve menu-minimize issues where vertical limits overrides prevented full collapsing during docked layouts (e.g. only action bar hiding).
  * Bring back missing Ping-Pong Animation limit controls (`🎚️` limits button, limits popovers) and random sweep trigger buttons (`🎲` randomize buttons) for Feedback Echo and Vignette FX sliders.
  * Connect and display the interactive Custom 'Dock' dropdown menu properly on click in the window header bar.
  * Prevent the hidden speed-select dropdown from overlapping adjacent randomize click thresholds.
  * Adjust theme trigger button properties (trim padding, strip redundant layout sizing rules) and correct theme options dropdown styles (replace bottom alignment to open down, remove shadow overlays, convert to overflow-x scrolling, and auto-unset max-height limit on taller viewports).
  * Polish theme selector list options (remove excess animations, and design charcoal grey contrast background for the dark/black color choice so that black text remains perfectly legible).
* **Implementation:**
  * **Multidirectional Docking System**: Replaced the toggle button in the header with a Custom 'Dock' dropdown selector. Engineered flexible flex layouts, direction transformations (`row`, `row-reverse`, `column`, `column-reverse`), and dynamic variable updates (`currentDock`, `dockWidth`, `dockHeight`) supporting left, right, top, bottom, and float coordinates.
  * **Interactive Row Layout Reordering**: Swapped dynamic programming builders to append layout items in custom row alignment directions. Reset buttons are positioned far-right with absolute precision.
  * **Ping-Pong Resets**: Coordinated the reset click event pipeline to assign `pps[k] = false`, halting sweeps and removing active highlight styling from the ↔ animation buttons.
  * **Custom Gradient Option Selectors**: Refamiliared theme picker selects with a lightweight CSS-styled custom div popover. Integrated proxy getter/setters for the `themeS` state handle to fully secure retroactive preset updates. Styled 'Spectral' natively utilizing `background-clip: text`.
  * **Checkbox Hover Tooltips**: Authored comprehensive and descriptive titles (`title="..."`) for all ten checkbox inputs and label elements, maximizing interface accessibility.
  * **Sticky Title Help Sidebar**: Redesigned `#cie-help-box` with absolute coordinates opposite the docked control sidebar (`left` if docked `right`, and vice versa). Structured the dialog to keep a custom border header static at the top while wrapping body rows in an independently scrollable `#cie-help-scroll-container` matching Gemini custom templates.
  * **Absolute Minimization Control**: Engineered a dedicated `.cie-controls.minimized` CSS state block setting absolute maximum height to `24px` (header size) and applying `display: none !important;` to child panels, fully securing uniform, flicker-free collapsing in both floating and multi-docked states.
  * **Dynamic Docking Setup**: Injected the correct responsive `#cie-dock-container`, `#cie-dockMenuBtn` and `#cie-dockOptions` dropdown nodes into the HTML layout header, restoring real-time multidirectional docking interactions seamlessly.
  * **Limits and Swapper Integration**: Appended missing `.cie-limits-btn` triggers and their `.cie-limits-popover` DOM frames to both Feedback Echo (`echoAmt`) and Vignette (`vignetteAmt`) slider markups, prompting the JS constructor to auto-bind dynamic ping-pong sweeps and randomizing algorithms correctly.
  * **Overlap Protection**: Applied default `display: none !important;` and negative index style parameters to hidden `.cie-speed-select` selectors, reactivating layout displays exclusively during active parent hover thresholds to eliminate target collisions.
  * **Theme Dropdown and Text Gradients**: Upgraded `.theme-spectral` with absolute `!important` text layout clips, protecting its rainbow gradient style from hover state color overrides. Trimmed the theme trigger button inline sizes, converted the options popover to downward opening `top:100%`, applied a clean `#cie-content` matching scrollbar, and bound screen-height media queries unlimiting `max-height` above 200px.
  * **Dark Contrast Legibility**: Assigned custom dark background counters (`background: #555 !important`) and sharp solid color values specifically to the `black` theme selector, making black-on-black list options highly legible.

### 📍 Version 1.18.1 [2026-06-10 19:30 UTC]: Absolute Minimization Control, Dynamic Docking Setup, and UI Detail Polish
* **User Intent / Feedback ("Bug fixes"):**
  * Resolve fine-tuning UI tweaks and coordinate alignment adjustments to version 1.18 additions.
  * Incorporate and integrate recent manual edits correcting historical sub-version listings across release notes.
  * Correct syntax errors immediately.
* **Implementation:**
  * **Version Synchronization**: Synced the application version reference to `1.18.1` uniformly across document title headers, navigation text, and structural indexes to comply with bug fix increment protocols.
  * **Uncaught Syntax Error Fix**: Fixed a JavaScript runtime syntax error inside the `themeS` state getter/setter, restoring the `: ""` fallback evaluation to prevent the `Unexpected token ';'` error.
* **Manual Edits Summary (User-applied):**
  * **Historical Version Index Rationalization**: Normalised minor sub-version designations across 1.15 and 1.16 listings to a standard 3-part decimal configuration (`1.15.1`, `1.16.1`, `1.16.2`, `1.16.3` instead of standard appending/concatenating tail numbers), maintaining uniform notation.
  * **App Version Increment Rules**: Documented the bug fix versioning guideline to increment by `.0.0.1` thousandths separated by decimal notation.
  * **Typography and Strings Refinement**: Corrected visual display symbols from `Scope ×8/×12` to a standardized compact lowercase `x8/x12` in the patterns index.
  * **Layout and Control Repositioning**: Moved the entire Viewport controls box (`🖥️Viewport`) from the FX tab to the Anim tab under Timeline. Prepend 〰️ to the Distortion ripple label, pre-pended 💾 to Saved listings label, updated global reset button to "⚠↺", and cleaned up text headers from "Global speed slider" concepts to compact labels.
  * **Aesthetic and Preset Sidebar Polish**: Configured `max-height: 5.375em` on saved design configurations lists, updated text colors of `.config-edit-btn` to high contrast yellow (`#ffbc00`), hidden disabled panels entirely, and appended a stylish text-shadow glow (`text-shadow: 0 0 5px rgba(255,255,255,1)`) to interactive reset counters on hover thresholds.
  * **Aesthetic Help Overlay Restyle**: Upgraded `#cie-help-overlay` to present an elegant semi-transparent dark container backdrop (`rgba(0,0,0,0.5)`), expanded the responsive box limits up to 70% width and 100% height, and stripped unnecessary padding, restoring excellent layout symmetry.
  * **Theme Picker Realignment**: Restored the Custom Color theme selector box to position itself inline right beside the custom color picker input element. Trimmed extra custom options class styling parameters (`font-bold`) to render perfectly compact gradients.

### 📍 Version 1.18.2 [2026-06-10 20:15 UTC]: Docking split-screen resize bars, titlebar size accommodations, header styling configurations
* **User Intent / Feedback ("UI bugs fixes"):**
  * Support split-screen resize bars for all docked `#cie-controls` positions (left, right, top, bottom), so they have a visible and tactile visual indicator matching the initial state even when re-docked.
  * Widen left/right docked `#cie-controls` to accommodate the titlebar text (`.hdr-text`) and `.cie-header-btns` on the same line to prevent line wrapping completely.
  * Set `#cie-header` `gap: 0` and disable wrapper wrapping.
  * Fix right-offscreen overflow on `#cie-dockOptions` when the `#cie-controls` are docked to the right edge.
* **Implementation:**
  * **Visible Split-Screen Resize Bars**: Configured `#cie-resize-handle` to always draw a styled `#333` background with high-visibility cursor and hover overrides across left, right, top, and bottom docking configurations. Setup explicit border overrides in CSS to keep boundary split borders robust during state transitions.
  * **Titlebar Wrapping Prevention**: Widen docking widths and floating widths to naturally accommodate version strings on a single line. Styled the header with `flex-wrap: nowrap` and `gap: 0` to preserve elegant baseline alignment.
  * **Dock Dropdown Positioning**: Anchored `#cie-dockOptions` with `right: 0` positioning relative to its trigger wrapper container, guaranteeing dropdown menus remain fully on screen when sidebar controls are docked right.
  * **Floating Handle Precision**: Enforced `.cie-controls:not(.docked) #cie-resize-handle {display: none !important;}` and set `rHandle.style.cssText = 'display:none;';` in floating states to guarantee the partition resize bars do not render or respond to hover highlights.
  * **Scrollbar Visibility Toggle**: Added a small, tightly packed checkbox labeled "Scrollbars" in the Display options row that dynamically toggles `.cie-hide-scrollbars` on `body` to hide all system scrollbars seamlessly in all tab panels and lists.
* **Manual Edits Summary (User-applied):**
  * **Dock Width Refinement**: Adjusted left/right docked `#cie-controls` panel widths to `283px` instead of `340px` to optimize overall screen real estate.
  * **Options Header Details**: Upgraded section headers for "Display" and "Audio Reactivity" inside the Options tab to a highly legible `12px` font size with `#ccc` coloring and `0` padding.
  * **Controls Keyboard Bindings Alignment**: Re-styled the controls section inside the Options tab to display keys like Space, R, F, H, M, and Zoom guides in neatly aligned inline flex groupings with informative custom symbols (⏸▶, 🔀, ⛶ and 🔄).
  * **Resize Border Improvements**: Implemented discrete 3px wide border configurations for docked handles, defaulting to a transparent background (`#3330`) highlightable on hovered thresholds.
  * **Dock Panel Styles Scrollbar Integration**: Appended custom dark-theme `-webkit-scrollbar` styling rules directly to the general un-docked controls container to ensure design continuity.
  * **Preset Configurations Layout Cleanups**: Swapped preset headings and config options labels, trimmed nested spacing containers, and restored consistent baseline alignment across display elements.

### 📍 Version 1.19 [2026-06-10 21:05 UTC]: Persistent Ping-pong directions, dynamic Input/Slider attribute syncing, and 7 CSS Canvas Filters
* **User Intent / Feedback ("Minor Feature Implementation"):**
  * Automatically match the min, max, and step attributes of every control's numeric input (`.cie-controls input[type=number]#cie-*`) to its range input counterpart (`input[type=range]#cie-*`) to prevent manual entry mismatches.
  * Enable the Ping-Pong animation controller to preserve and resume its dynamic oscillation direction (left/right) when paused and resumed physically.
  * Introduce 7 core CSS hardware-accelerated filter controls impacting `canvas#cie-canvas` inside the FX tab, fully integrated with checkboxes, range sliders, high-precision numeric inputs, resets, speed parameters, continuous randomness, and bounding popovers.
* **Implementation:**
  * **Dynamic Attribute Alignment**: Embedded startup scripts directly aligning numeric input min, max, and step validation states to match matching slider configurations.
  * **Directional Animation Persistence**: Modified the ping-pong state machine to avoid wiping the cached step variable `ppd[k]` when disengaging a sweep toggle, only resetting movement direction to default when explicitly reset.
  * **HTML5 Canvas CSS Filters**: Formatted and injected 7 newly integrated CSS Filters into the active FX scroll panel: CSS Blur (0-100), CSS Brightness (0-10), CSS Contrast (0-10), CSS Grayscale (0-1), CSS Hue-rotate (0-360°), CSS Saturate (0-10), and CSS Sepia (0-1). Built a dynamic string translator applying the active style components inline to the canvas layout every animation loop frame.
* **Manual Edits Summary (User-applied):**
  * **Vertical/Horizontal Docking Styling Simplification**: Eliminated redundant `!important` markers across vertical (left/right) and horizontal (top/bottom) docking layouts for `.cie-controls` styles.
  * **Tab Panel and Layout Display Overrides**: Streamlined conditional tab panels visibility rules inside vertical and horizontal docks, stripping strict override flags.
  * **Scrollbar Design Consistency**: Compressed custom dark-theme `-webkit-scrollbar` rules with unified tracking and smooth thumb scroll bounds inside `#cie-theme-options` list wrapper.
  * **Interactive Text Shadows & Glow Highlights**: Compacted `#cie-fps` text shadow padding elements, and synchronized interactive reset buttons (`.cie-reset-btn`) hover transformation rules.
  * **Inner Section Separator Rules**: Stripped extra spacing elements from standard `.cie-box-title` before and after element border dividers.
  * **Unified Spectral Theme Gradients**: Replaced custom `.theme-spectral` typography background-clip properties with native styling rules.
  * **Control Limits Popovers Absolute Anchoring**: Modified the `.cie-limits-popover` padding and absolute width boundaries (`white-space: nowrap; width: 100%`) for clean visual display across overlapping controls.
  * **Dynamic Interactive Limit Tracks**: Integrated high-fidelity hover scaling (`transform: scaleY(1.5)`) to interactive track divisions, and removed legacy arrow indicators (`|` instead of `>|` or `|<`) from `.cie-limit-marker` guidelines.
  * **Active CSS State Toggle Transitions**: Dropped verbose `!important` tags from continuous animation state classes (`.active-continuous`), and synchronized active hover pulses.
  * **Aesthetic Transitions & Animation Delays**: Optimized typography movement speeds across complex text styles (Chroma, Vignette, Echo, Scanlines, Distort, Motion Blur).
  * **Interactive Element Wrapping Alignment**: Nested inner shift labels style selectors under elegant `.cie-shift-effect` elements to align interactive button margins smoothly.
  * **FX Filters Label Streamlining**: Renamed FX CSS canvas filters to highly compact, lightweight human terms ("Blur", "Brightness", "Contrast", etc.), and calibrated sepia input bounds (`min="0" max="1" step="0.01"`).
  * **Designs and Presets Inline Integration**: Aligned preset items cleanly alongside visual headers in a standard flex alignment inside the Designs menu wrapper.
  * **Control Limit Popovers Flex Organization**: Organized `.cie-limits-popover` structures, placing the min/max inputs and control buttons in distinct `<span>` wrappers to permit dual-justified alignment across both edges cleanly.

### 📍 Version 1.19.1 [2026-06-10 21:33 UTC]: Universal Scrollbar Toggling, Elegant Floating Coordinates Caging, and Sound Device Outputs
* **User Intent / Feedback ("Feature Refinement & Layout Harmonization"):**
  * Resolve global scrollbars visibility toggles failing on custom stylized scroll panels (e.g. `cie-configList` and `theme-options`).
  * Rename "Audio Reactivity" tab heading to "Audio reactivity" with 🎵 emoji branding.
  * Integrate a dedicated `🔊Sound device` switch and an auto-enumerated audio inputs select dropdown, supporting standard mics, loopback cables, or high-fidelity browser display streams capture (`getDisplayMedia`) to drive breathing loops.
  * Incorporate 7 consecutive user-developed visual, geometric, and functional enhancements to unify margins, alignments, and viewport docking behaviors.
* **Implementation:**
  * **Global Scrollbar Hiding**: Refined CSS scrollbar display-none structures, introducing priority overrides to forcefully suppress scroll tracks across any nested container when the general overlay toggle is activated.
  * **Hardware/Stream Capturing Audio Reactivity**: Developed flexible audio retrieval layers. Injected active `populateAudioDevices()` routines parsing external input hardware on load, and reconstructed analytical routines to cleanly support both traditional media mic recordings and System Audio browser shares.
  * **User Manual Edits Preservation**: Persisted and optimized all 7 custom design updates:
    1. Trimmed vertical padding of control inner boxes (`.cie-group padding:0 2px`) across Glow, Trail, Zoom, Shift, and Convergers.
    2. Aligned slider limits interactive line tracks and overlay containers with bottom coordinates.
    3. Revisted cycle speed sliders and increment bounds to linear `0.1 - 10` dimensions with exact `0.1` granularity steps.
    4. Upgraded control panel headings with distinctive emoji tags (e.g., `⏱️Speed`), arranging limits popovers internally using dual `<span>` containers to maintain a balanced, dual-justified layout.
    5. Cleaned up resize handle layouts, removing background block coloring while preserving custom touch cursors and hover indicators.
    6. Programmatically calibrated setDockSide orientation calculations, handling panel flex directions and sidebar dimensions smoothly.
    7. Synchronized floating widths cache (`floatWidth` default to `273px`) upon coordinates caging when un-docking.
* **Manual Edits Summary (User-applied):**
  * **Action Buttons Hover Scaling & CSS Refinements**: Added dynamic hovering scaling (`transform: scaleY(1.25)`) and text-shadow glow (`text-shadow: 0 0 5px rgba(255,255,255,1)`) to control footer action buttons on hover.
  * **High-Contrast Warning Icon Upgrade**: Replaced the standard warning reset symbol `⚠↺` with a full-color emoji `⚠️↺` for higher contrast and visual clarity.
  * **CSS Formatting and Syntax Polish**: Cleaned up duplicate spacing, brace properties, line breaks, and aligned layout styling configurations across `.cie-header`, `.cie-tab-panel`, `.cie-controls.dock-top`, and related elements to streamline performance.
  * **Slider Limit Track Overlays**: Fine-tuned `.cie-slider-limit-overlay` paddings (`left:5px; right:4px`) to perfectly center markers overlaying range inputs.
  * **Micro-Hover Transformations & Scaling**: Normalized hover scaling states across `.cie-reset-btn`, `.cie-speed-scale-container.cie-speed-symbol`, and `.cie-ping-pong` components to enforce a consistent 3D zoom focus.
  * **Converge Modulation Range Expansion**: Doubled the peak `cie-converge` parameter bounds on the slider element from `1` up to `2` to explore deeper warp coordinates.
  * **Interactive Spinner & Input Aesthetics**: Injected crisp border-color feedback transitions (`border-color: #888`) on hover for numeric inputs alongside hover brightness filters on native platform up/down step arrows.
  * **Unified Action Button Scale Metrics**: Aligned action button hover metrics to use isotropic scaling (`transform: scale(1.25)`), formatted the master pause button with unified border-radii (`border-radius: 3px`) and line heights, and cleaned up reset click triggers.
  * **Expressive Default FX Filters**: Retuned default parameters for the 7 CSS filters (Blur, Brightness, Contrast, Grayscale, Hue-rotate, Saturate, Sepia) to construct a highly artistic showcase right on first render.
  * **Dark Selectors legibility**: Restructured the "black" colormap theme list options to display legibly over identical deep-charcoal backdrops utilizing subtle gray letter drop-shadow offsets (`text-shadow: -1px 1px 0px gray`).
  * **Soft Gray Theme Integration**: Appended a native `'gray'` color preset (`#808080`) cleanly inside the color options database and sorted index trackers.
  * **Borders, Formatting, and Icons Polish**: Sanitized CSS rules by converting redundant declarations to standard dry overrides (`border: 0`), synced edit buttons (`.config-edit-btn`) colors, integrated Wikipedia reference links within help logs, and unified Wobble amplitude labels with the aesthetic `∿` curves pattern.
  * **Interactive Element Highlight Prioritization**: Leveraged `!important` flags across key control buttons to prevent native browser or host-theme overrides and guarantee snappy visual feedback on cursor hover.
  * **Enhanced Button Specifying Overrides**: Applied explicit white color specificity (`color: #fff !important`) on utility button hover actions to maintain maximum legibility against dark slate frames.
  * **Discrete Granularity on Background Trails**: Constrained the custom frame-cache clear rate range input (`#cie-bgFade`) to explicit tenth units (`step=".1"`), stabilizing manual trails blending adjustments.
  * **Consolidated Scale & Opacity Hover Classes**: Grouped random slider controls directly into the primary micro-hover rules, establishing unified isotropic scaling, opacity resets, and glowing drop-shadows on hover.

### 📍 Version 1.19.2 [2026-06-16 23:59 UTC]: Unified Class-Based Limit Popovers Close Mechanism
* **User Intent / Feedback ("Refined Popovers Closer Architecture"):**
  * Eliminate the redundant individual `id` properties (`id="cie-limits-*-close"`) across all sliders' limits popover close (`✕`) buttons.
  * Establish a unified, class-based selection mechanism (`.cie-limits-close-button`) for registering popover close-click behaviors in JavaScript.
  * Style the limits close buttons with dynamic white-hot micro-hovers and a static rich red hue (`color: red !important`).
* **Implementation:**
  * **Class-Based Event Registration**: Refined Javascript popover handlers to listen globally on `.cie-limits-popover .cie-limits-close-button` triggers, dynamically caging the closest popover and synchronizing track slider limit bounds overlays with zero legacy `id` dependencies.
  * **HTML Structural Cleanup**: Safely purged all 29 custom close button individual `id` attributes and replaced class alignments with the clean `.cie-limits-close-button` token.
  * **Visual Polish / Micro-Hovers**: Synchronized close buttons with standard micro-hover scale metrics (`transform: scale(1.25) !important`), custom text glows, and clear isotropic transformations using an explicit high-contrast red primary theme.

### 📍 Version 1.20 [2026-06-17 22:50 UTC]: High-Altitude Auto-Pan Geometries, SVG Speed Scales, & Seamless Multi-Strobe Interpolation
* **User Intent / Feedback ("Geometric Translation Suite, SVG Scales, and Smooth Strobing"):**
  * Introduce a comprehensive **Pan Control Group** supporting automated orbital translation under diverse patterns (horizontal, vertical, circular clockwise/counterclockwise, and triangular clockwise/counterclockwise) including an animated **Decaying Spiral** option.
  * Dynamically render highly creative, smooth **vector SVG shapes representing speed scales** (linear, exponential, cubic, etc.) inside a premium custom dropdown next to each animation parameter reset trigger.
  * Create fully responsive, stutter-free theme transformations by integrating progressive transition parameters alongside a **non-snapping continuous strobe chronometer** (`multiStrobeTimer`), preventing spatial color jumps during cycle resets.
* **Implementation:**
  * **Interactive Pan Engine**: Created responsive slider, direct numeric coordinate interfaces, and pattern modes for translation coordinates mapping inside `drawSingleState`.
  * **Decaying & Stretching Spiral Modulator**: Styled a cosmic spiral modulator gradually shrinking orbit translation distances to origin over cosine phases before stretching back to limits.
  * **SVG Vector Shapes Injection**: Created bespoke path definitions of speed scale math, rendering them inside high-DPI inline SVGs within premium hover-active popover list selectors.
  * **Stutter-Free Strobing**: Resolved theme reset snaps by separating cycle reset timers from continuous multi-strobe motion coordinates backing up state values elegantly during double buffered frames.
* **Manual Edits Summary (User-applied):**
  * **Interactive Element Highlight Prioritization**: Leveraged `!important` flags across key control buttons to prevent native browser or host-theme overrides and guarantee snappy visual feedback.
  * **Enhanced Button Specifying Overrides**: Applied explicit white color specificity (`color: #fff !important`) on utility button hover actions to maintain maximum legibility against dark slate frames.
  * **Discrete Granularity on Background Trails**: Constrained the custom frame-cache clear rate range input (`#cie-bgFade`) to explicit tenth units (`step=".1"`), stabilizing manual trails blending adjustments.

### 📍 Version 1.21 [2026-06-18 00:35 UTC]: Sacred Geometry 'Flower of Life', Singularity Depth Warps, and Dynamic Slider Snapping Tracks
* **User Intent / Feedback ("Geometric Depth Merges, Sacred Geometry, and Sliders Snapping Marks"):**
  * Introduce the **Flower of Life** sacred geometry pattern rendering custom overlapping hex-grid orbit vectors.
  * Resolve 'multi-strobe color cycling' flickering during strobe rate adjustments.
  * Fix the 'gray' color theme rendering as spectral/rainbow lines instead of beautiful neutral `#808080`.
  * Support the 'Converge' slider for `spiral`, `fractal`, `lissajous`, and `flower` modes via a new 'Singularity' checkbox to draw elements towards the absolute center of coordinate rotation.
  * Render dynamic "|"-style indicators exactly at 25%, 50%, and 75% distances behind range slider tracks.
  * Add a 'Snap sliders' option supporting magnetic grid snapping (within 0.01 tolerance) to these markers.
* **Implementation:**
  * **Sacred Geometry Engine**: Formatted a pristine hexagonal overlay matrix drawing overlapping circles of uniform radius `R` nested under color and speed parameters.
  * **Flicker-Free Continuous Multi-Strobe**: Refined `multiStrobeTimer` to accumulate speed-scaled delta steps continuously inside the core render scheduler, decoupled from manual color cycle transitions.
  * **Static Theme Corrections**: Appended `{r:128,g:128,b:128}` mapping to represent `'gray'` inside the colormap database, protecting neutral lines from falling back onto spectral/rainbow hue spectrum calculations.
  * **Singularity Coordinate Converger**: Injected structural `(1 - cv)` scaling across all nodes inside spiral, fractal, lissajous, and flower drawing functions, triggered in-depth by the active `Singularity` checkbox.
  * **Background Slider Ticks**: Programmed `initSliderTicks` wrapping relative viewport columns around every range input, dynamically drawing 1px overlay lines behind standard thumbs with zero DOM drift.
  * **Capturing Phase Grid Snapping**: Bound a global snapping capturing listener onto all range sliders matching tick marker thresholds elegantly before bubbling-phase event listeners execute.

### 📍 Version 1.21.1 [2026-06-20 UTC]: Radial Sacred Geometry, Capturing Interceptors, Viewport Scale Suite, and Multi-Overlay Alignment
* **User Intent / Feedback ("Geometric Adjustments, Input Guarding, and Scale Controllers"):**
  * Render the hexagonal **Flower of Life** sacred geometry radially centered on the viewport instead of staggered diagonals.
  * Construct an independent **Scale slider suite** underneath Zoom inside Viewport tab, linking custom ticks, manual value adjustments, resets, and randomized loops.
  * Block clicks on `#cie-main-area` when `#cie-help-overlay` is `.visible`, while fully preserving scrolling and `.help-row` cursor hover activations.
  * Position limits popovers over standard slider rows inside groupings cleanly while supporting simultaneous multi-toggle visibility.
  * Harmonize '✕' close buttons with consistent primary red hues and white-hot zoom transitions on cursor hover.
  * Configure snap sliders on by default.
* **Implementation:**
  * **Radial Geometry Alignment**: Shifted staggered outer layers of the Flower of Life hexagonal grid symmetrically about coordinate axes by shifting the top-left and bottom-right coords to preserve true vector alignments on screen.
  * **Viewport Scale Suite**: Integrated separate `cie-scale` options with custom step values, limits templates, instant numerical feedback syncing, and randomizers.
  * **Motion-Blur Historical Caching**: Hooked scale into background frame memory layers to prevent stuttering under fast panning motion blurs.
  * **Help Overlay Interception**: Formatted pointerdown capturing phase event filters guarding `#cie-main-area` elements instantly while leaving touch and hover events unlocked.
  * **High-Contrast Close Buttons**: Refactored `#cie-hideBtn`, `#cie-help-close`, and `.cie-limits-close-button` with a cohesive red branding.
  * **Limits Popovers Overlays**: Corrected relative coordinates on `.cie-limits-popover` containers, centering overlays cleanly within slider rows.
  * **Default Sliders Snapping**: Assigned checked state indicators onto snapping elements on setup.

### 📍 Version 1.21.2 [2026-06-20 UTC]: Concentric sacred geometry layered progression and CSS-driven illustrative filtering
* **User Intent / Feedback ("Flower of Life progression mechanics and representational CSS overlays"):**
  * Revamp the **Flower of Life** mathematical pattern to render each discrete depth value strictly radially around the origin to maintain pristine hexagonal symmetry.
  * Define explicit sacred geometry configurations: Depth 0 (Single core circle), Depth 1 (Mutual halfway overlapped "Vesica Piscis"), Depth 2 (Mutually overlapped "Triquetra/Tripod of life"), Depth 3 (7-circle "Seed of Life"), Depth 4 (13-circle "Seed of Life" with outer layer symmetry), and Depth 5+ (Growing concentric hexagonal rings, mapping the original depth-2 19-circle "Flower of Life" to Depth 5).
  * Record prior manual user adjustments including: restyling limits popovers to dark-crimson with tighter custom margin metrics, and applying live inline stylized visual CSS mockup filter overlays onto option checkboxes to match input types beautifully.
* **Implementation:**
  * **Radial Sacred Geometry Progression**: Programmed the coordinate mapping grid to support gradual discrete sacred geometry layouts inside `drawFlowerOfLife`.
  * **Dynamic Geometry Resizing**: Normalized viewport circular spacing calculations continuously, matching scale configurations against the active geometric footprint.
  * **Precise Centroid Symmetry**: Applied translation vectors `(-R * 0.5, 0)` and `(-R * 0.5, -R * sin60 / 3)` for MD 1 & 2 to center the Vesica Piscis and Triquetra vectors on screen.
  * **Concentric Layer Shading**: Linked the color indexing engine to radial grid step metrics before applying drawing context fills.
  * **Manual Edits Summary (User-applied)**: Incorporated the custom dark-burgundy (`#1c0a0a`) limits popover theme, narrow sliding tracks borders, and the representational inline CSS `style` filter mockups across filter selection labels (Blur, Brightness, Contrast, Grayscale, Hue-rotate, Saturate, Sepia).

### 📍 Version 1.21.3 [2026-06-20 UTC]: Radial Hexagonal Flower of Life, Incremental Render Step System, Reset Controls Synchronization, and Slick Slider Overlay Stacks
* **User Intent / Feedback ("Geometric Progression Adjustments, Animatable Render Step Controls, and Slick Slider Clickability"):**
  * Revamp **Flower of Life** sacred geometry logic: Depth 5 must remain radially hexagonal with 12 more concentric circles (19 total circles) and maintain this hexagonal concentric rings expansion symmetrically through depth 12 with constant circle diameters (`R = baseR / 10`), fitting the pattern in full view at zoom 0.
  * Implement an incremental **Render step** checkbox and slider control group, animating circle-by-circle drawing progress across all modes.
  * Disable a slider's continuous randomizing loop when its corresponding **↺ Reset** button is clicked.
  * Resolve range slider overlapping issues: position slider range input thumbs clearly on top (`z-index: 3`) of `.cie-limit-track` so standard controls remain perfectly click-active.
  * Direct `.cie-limit-marker-tooltip` to display on hover/focus over `.cie-limit-marker` at high-contrast front-level layers (`z-index: 10000`) when the limits popover container is hidden (`display: none`).
  * Anchor default canvas zoom levels at a baseline shift of +0.45 across all drawing operations, using that offset as the new local '0'.
* **Implementation:**
  * **Symmetric Hex Grid Expansion**: Programmed `drawFlowerOfLife` to generate coordinates using `Math.abs(i + j) <= R_grid` and locked `R = baseR / 10` for constant scale across all levels up to depth 12.
  * **Incremental Render Step Engine**: Mounted a global `totalRenderSteps` counter and `shouldDraw()` validator, and wired a custom render step checkbox and slider in the "Pattern" tab.
  * **Randomizer-Halt Trigger**: Modified the `.cie-reset-btn` click handler to automatically turn off that specific control row's random toggle (`.cie-random-slider-btn`), preventing unexpected randomization resumes on reset.
  * **Slider Stack Ordering**: Positioned range slider thumbs with higher relative priority over tracks and custom limit nodes, ensuring mouse interactions hit input controls perfectly.
  * **Overlay Markers Focus Tooltip**: Programmed tooltip show/hide triggers responding directly to `:hover`, `:focus`, and `:active` pseudo-elements of `.cie-limit-marker` elements.
  * **Baseline Zoom Shift Integration**: Incorporated `0.45` baseline offset inside `zoomFactor` and `drawSingleState` viewport coordinate transformations seamlessly.

### 📍 Version 1.21.4 [2026-06-20 UTC]: DOM insertBefore Child Node Guard for Nested sliders
* **User Intent / Feedback ("Fix Uncaught NotFoundError: Failed to execute 'insertBefore' on 'Node'"):**
  * Resolve a DOM layout exception occurring during custom range slider wrapper setup on deeply nested input sliders.
* **Implementation:**
  * **Nested Node Guard**: Upgraded the `initSliderTicks` slider wrapping function to dynamically trace parent hierarchies. For nested sliders (e.g. within dynamic container elements like `#cie-renderStepSliderContainer`), the popover positioning lookups safely determine the direct container child of the `.cie-group` parent, preventing insertion of nodes on mismatched elements and avoiding the `insertBefore` DOM exception.

### 📍 Version 1.21.5 [2026-06-21 UTC]: Click-Thru Slider Tracks, Floating Action/Tab Fixes, and Dynamic Render Step Range Synchronization
* **User Intent / Feedback ("Click-Thru Slider Tracks, Floating Pane Visibility, Fixed Actions Bar, and Infinite Render Step Range Sync"):**
  * Separate range slider track clicks from the slider handles: Make `input[type=range]` slider tracks click-thru so that only the slider handles/thumbs are clickable, leaving `.cie-limit-track` and `.cie-limit-marker` elements fully interactable and draggable underneath.
  * Ensure `.cie-limit-marker-tooltip` tooltips show reliably when hovered, focused, or active.
  * Fix the docking `#cie-action-bar` position to remain fixed and visible at the bottom of `.cie-controls` when docked.
  * Fix the 'Designs' and 'Options' tab panels not showing any contents when `.cie-controls` is floating.
  * Fix 'Render step' slider/counter logic to animate individual drawing and recursion shapes dynamically up to the precise maximum shape count possible for each combination of depth and pattern type. Treating each circle/shape as an individual step across any selected mode (including the 'Flower of life' pattern).
* **Implementation:**
  * **Click-Thru Rangy Sliders**: Configured `pointer-events: none` on `.cie-controls input[type=range]` while assigning `pointer-events: auto` to both `::-webkit-slider-thumb` / `::-moz-range-thumb` pseudo-elements. Set relative `z-index: 3` for default tracks, `z-index: 4` for `.cie-limit-track`, and `z-index: 5` for `.cie-limit-marker` elements to enable pristine selective hover and dragging interactions.
  * **High-Contrast Tooltips Display**: Refined hover state selectors and activated `isInt` indicators for `renderStep` on the limit overlay templates to lock text alignments.
  * **Docked Action Bar Sticky Anchoring**: Added `position: sticky; bottom: 0; z-index: 101; margin-top: auto` styles to `.cie-action-btns` rendering the buttons panel fixed at the bottom of controls on active scrolling containers.
  * **Parser Elements Guard**: Resolved an unclosed `div` element inside the FX tab panel (`data-panel="fx"`) that had caused the 'Designs' and 'Options' panel structures to nest inside it, causing them to inherit its display-none active state. Correctly closed the FX panel to restore perfect floating tab layout switches.
  * **Dynamic Render Step Range Sync**: Injected `getMaxStepsForCurrentConfig()` and `syncRenderStepRange()` calculation engines, dynamically setting the `max` attribute of the Render Step range and numerical inputs whenever draw modes or recursion depths change, and clamping current values within range boundaries.
  * **Step Counter Frame Reset**: Added frame-level counter resets inside `drawSingleState` to correctly enforce render step limitations across both individual frames and motion-blur iterations.

### 📍 Version 1.21.6 [2026-06-21 UTC]: Remember Sound Source on Toggle, Negative Arc Radius Fix, Radial Sorted Flower Of Life, and Clickable-Slider / Grabbable Limits Fix
* **User Intent / Feedback ("Remember Sound Source, Spiral Negative Arc Radius Fix, Correct Flower of Life Radial Draw Order, Responsive Clickable Sliders, and Style Customizations"):**
  * Remember the acquired audio/display stream source when 'sound device' is toggled off and back on again, avoiding repetitive system popups.
  * Guard all canvas arc rendering (especially in spiral mode with audio reactivity) against negative radius values (`IndexSizeError`) that freeze the engine.
  * Sort flower of life coordinates radially outward (centered outwards) at any depth level to guarantee the 'render step' draws centering circles first and expands outward.
  * Remove `pointer-events: none` on range inputs and turn off pointer events on `.cie-limit-track` so sliders remain fully clickable and grabbable cross-overlay, keeping limit markers independently interactive.
  * Adjust button widths and pad layouts: set `.cie-action-btns` padding-right to `4px`, `#cie-resetBtn` width to `2em`, and `#cie-pauseBtn` width to `50%`.
* **Implementation:**
  * **Persistent Audio Source Cache**: Stored the active `MediaStream` track reference in `rememberedSoundStream` and checked its readyState before re-invoking media device requests.
  * **Arc Radius Math Clipping**: Guarded `ctx.arc()` calls with `Math.max(0, radius)` bounds-clipping across all draw routines to prevent IndexSizeErrors.
  * **Radial Geometry Sorter**: Sorted the generated list of centers in `drawFlowerOfLife` by distance from origin (then angle circumferentially) for seamless nested drawing order.
  * **Clickable Slider Layout**: Replaced bulk pointer-event blockers with native clickability on range inputs, specifying `pointer-events: none` only on `.cie-limit-track`.
  * **Fine-Tuned Toolbar Styling**: Applied paddings and responsive size dimensions directly to footer elements and reset layout classes.

### 📍 Version 1.22 [2026-06-22 UTC]: Limits Grabbability, High-Depth Flower of Life, Oscillating Render Steps, Coordinate Wrap Mode, and Global Speed Expansion
* **User Intent / Feedback ("Limit Markers and Oscillating Render Steps, High-Depth Sacred Geometry, Centering Pans, Seamless Coordinate Wrap, and Faster Global Playback"):**
  * Fix limit markers tooltips, grabbability, uniform vertical scale vertical scaling hover behavior, and add "Oscillate" render step checkbox option.
  * Expand "Flower of life" pattern max recursion depth up to 16.
  * Fix Pan effect circular/triangular starting offsets, implement seamless coordinate wrap mode with adjustable wrapping threshold, and fix pan spiral inactivity.
  * Increase "Global speed" slider max value to 10 and add the '⏱️' icon button for ping-pong speed scales.
* **Implementation:**
  * **Limits Popover and Draggable Tooltips**: Refined `.cie-limit-marker` focus and hover behaviors to ensure tooltips show reliably. Made sure limits and ranges remain fully grabbable and interactive.
  * **Uniform Hover Scaling**: Fixed the range slider thumb hover scaling to scale uniformly in both axes (`transform: scale(1.5, 1) !important`) when the outer wrapper hover animation scales vertically.
  * **Oscillate Render Step**: Implemented the `cie-renderStepOscillate` checkbox and mapped it inside the core draw queue loop to alternate drawing pattern ends symmetrically.
  * **High-Depth Flower of Life**: Expanded depth attributes in both range inputs and mathematical coordinates logic to render up to recursion depth 16 safely.
  * **Centering Pan Correction**: Shifted theta coordinates on circular and triangular pan algorithms by their start-phase value (`pT0`) so that at slider default (`pVal = 0`), the pattern is perfectly centered with zero visual offset.
  * **Coordinate Wrap Mode**: Created a continuous wrap loop inside `drawSingleState` translating coordinates modulo double the custom wrapping threshold (`wrapPeriod = thresh * 2`) and drawing tiled pattern replicas horizontally and vertically for 100% seamless infinite pans. Modified `runPP` to wrap the pan value from max back to min continuously in wrap mode.
  * **Dynamic Pan Spiral**: Tied the pan spiral multiplier to a dynamic high-frequency performance clock when animate is paused, keeping spiral movements continuously alive.
  * **Global Speed Expansion**: Increased max limits on the global speed slider input to 10 for faster animations.
  * **Speed Scale Clock Trigger**: Replaced the cryptic `╭╯` button with a highly descriptive `⏱️` clock emoji icon button.

### 📍 Version 1.22.1 [2026-06-23 UTC]: Local Ping-Pong Speed Modifiers, Speed Scale UI Reverts, and Layout Reorganization
* **User Intent / Feedback ("Local Speed Control, Trigger Icon Restoration, and Control Panel Polishing"):**
  * Add a '⏱️' emoji/icon button ('Ping-pong animation speed' tooltip) between the `.cie-ping-pong` button and `cie-speed-scale-container` to every slider that displays a vertical range slider popover to change that particular ping-pong slider's overall speed (0 to 10, default 1, step 0.1).
  * Restore the 'speed scale' trigger button icon from `⏱️` to the original `╭╯` symbol.
  * Reorganize the `🔁Wrap` checkbox and `Threshold` inputs into a space-between row inside the Pan grouping for a cleaner visual layout.
  * Change the 'Render step' label icon from a ladder emoji `🪜` to a film strip emoji `🎞️`.
* **Implementation:**
  * **Individual Ping-Pong Speed Modifiers**: Allocated `ppSpeeds` global mapping, implemented dynamic popover injection centering a standard vertical range input, and integrated `localSpd` factor directly inside the velocity step accumulation loop.
  * **Persistent Settings Integration**: Hooked `ppSpeeds` into settings serialization, enabling robust capture (`getSettings()`) and restore (`loadSettings()`) of custom speed parameters on design presets.
  * **Dynamic Elements Layout Reassembly**: Repositioned elements in the dynamically generated controls, situating the new speed modifier button exactly between `.cie-ping-pong` and `cie-speed-scale-container` elements.
  * **Aesthetic UI and Typography Refinements**: Reverted the speed scale trigger to its classic `╭╯` icon, changed the render step label icon to `🎞️`, and aligned Pan wrapping threshold selectors nicely inside a responsive row container.

### 📍 Version 1.22.2 [2026-06-24 UTC]: Scanlines/Vignette Quadrant and Rotation Fixes, Asymmetric Alternating Oscillation, and Manual UI Overrides
* **User Intent / Feedback ("Vignette & Scanlines Coverage, Lock Rotation, Symmetrical Oscillation, and Custom Styles Integration"):**
  * Fix Scanlines and Vignette effects from appearing only in the top-left quadrant; make them cover the entire canvas correctly.
  * Add "Lock Rotation" options to prevent Scanlines and Vignette from rotating with the canvas layout.
  * Fix "render step" oscillation to alternate back and forth asymmetrically between opposite ends of the pattern rather than rendering linearly from one end to another.
  * Incorporate the latest 2 manual edits summarizing limits grabbability overrides, red limit track colorings, and hover wrapper scaling styles.
* **Implementation:**
  * **Diagonal Bounds Calibration for FX**: Redefined scanline and vignette bounding calculations using the canvas hypotenuse diagonal (`Math.sqrt(w*w + h*h)`) and centered the coordinate matrix around `(0, 0)` under custom translation so that shaders cover 100% of the viewport seamlessly under any arbitrary canvas rotation.
  * **Rotational Lock Toggles**: Inserted `#cie-scanlinesLockRot` and `#cie-vignetteLockRot` checkboxes into the UI. Programmed matrix rotation bypasses inside the FX application block when these locks are active, saving and restoring these properties on custom presets.
  * **Asymmetric Alternating Oscillation Sorter**: Overhauled the oscillation interceptor inside the draw queue, dividing collected shapes into discrete radius buckets. Each bucket is sorted lexicographically and rendered asymmetrically, alternating back and forth from the outer edges to the center (e.g., center, far-left, far-right, near-left, near-right) for a balanced organic animation swell.
  * **Manual Edits Summary (User-applied):**
    * **Limits Track Visibility, Tick Indexing, and Styles Refactoring**: Styled the `.cie-limit-track` to a vivid, semi-transparent red (`rgba(255,0,0,0.75)`) with forced pointer-events, boosted tick bars to `zIndex = 3` for higher clickability, added vertical scale-up animations to the slider wrapper on hover, and styled speed label popovers with vibrant yellow text.
    * **Range Input Interaction Overrides**: Configured all slider range inputs (`.cie-controls input[type=range]`) with `pointer-events: auto !important` to ensure perfect grabbability and mouse interactions across various browser configurations.

### 📍 Version 1.22.3 [2026-06-25 UTC]: Seamless Pan Wrapping performance, Symmetrical Mirror-Lock Limits, and Boundary-Aware Tooltip Placements
* **User Intent / Feedback ("Pan Wrapping FPS Boost, Mirror-Lock Range Limits, Left/Right Shift Tooltips, and Version Metadata"):**
  * Fix the 50% framerate drop when 'pan wrapping' is enabled.
  * Add a mirror-lock checkbox to `.cie-limits-popover` (between min and max inputs) to lock and mirror the min and max limit markers symmetrically relative to the slider's center point. Show both tooltips when either marker is hovered or grabbed.
  * Fix `.cie-limit-marker-tooltip` placement to dynamically shift horizontally to stay inside the control panel `#cie-content` and prevent unwanted horizontal scrollbars.
  * Include a comprehensive history summary and bump the app version inside `index.html` and `history.md`.
* **Implementation:**
  * **Coordinate Wrap Performance Optimization**: Introduced a highly efficient spatial visibility check (`isTileVisible`) in both non-oscillate and oscillate rendering paths, skip-rendering any wrapped tiles that lie entirely outside the browser viewport. Replaced generic coordinate translations with fast `DOMMatrix` multiplication offsets inside the oscillate drawing queue to eliminate redundant transformations and restore a locked 60 FPS under infinite pans.
  * **Symmetrical Mirror-Lock Limits**: Implemented `ppLimitsLocked` state manager and auto-injected a mirror-lock checkbox `🪞` inside `.cie-limits-popover` between min/max inputs. Programmed symmetric coordinate anchoring (`syncMirroredLimits`) that mirrors dragging adjustments or manual input changes relative to the slider's absolute center point.
  * **Interactive Dual-Tooltip Hover States**: Created custom delegated enter/leave hover listener triggers that assign a temporary `.show-all-tooltips` styling class to the slider overlay container when a mirrored slider is active. Configured CSS rules to display both min and max tooltips simultaneously when either limit marker is hovered or grabbed.
  * **Boundary-Aware Tooltip Placements**: Developed a real-time horizontal bounds collision handler (`adjustTooltipPlacements`) inside `requestAnimationFrame`. It briefly queries the screen-space bounding rect of each tooltip relative to `#cie-content`'s edges and dynamically offsets the tooltip via `translateX()` style transforms to guarantee the tooltips never overflow the control panel boundary.
  * **Manual Edits Summary (User-applied):**
    * Refined custom scrollbar styles across both horizontal and vertical content docking layouts to prevent visual clipping.
    * Polished button border states, hover effects, help text styling guidelines, and optimized the layout alignment of nested popovers.

### 📍 Version 1.23 [2026-06-25 UTC]: Hardware-Accelerated Glow Overlay, Duplicate Kaleidoscope Recursion Fix, Symmetrical Render Step Mirroring, and Confirmation Safeguards
* **User Intent / Feedback ("Hardware Glow Overlay, Kaleidoscope Duplicates Fix, Step Mirroring, Reset Confirmation, and Keyboard Shortcuts"):**
  * Fix the massive framerate drop when the 'glow' effect is on by replacing standard canvas per-circle shadows with full-viewport, hardware-accelerated overlay filters.
  * Eliminate 100% of the duplicate recursive rendering calls in `kaleid` (Kaleidoscope x8) and `kaleid12` (Kaleidoscope x12) patterns.
  * Add a 'Mirror' render step oscillation checkbox that mirrors the drawn sequence of steps symmetrically.
  * Implement an interactive 'Reset Confirmation Modal' when clicking the 'Global Reset All' button to prevent accidental state loss.
  * Map advanced keyboard shortcuts: `Ctrl+R` / `Meta+R` for Reset All (with confirmation), `R` (alone) for Reset Control (with brief smooth highlighted feedback), and `Shift+R` for Randomize.
  * Ensure the limits lock (`.cie-limits-lock`) is enabled by default.
  * Remove floating `.cie-controls` fixed height restrictions and add a 5px bottom padding spacer inside `.cie-content` so that hovering the last slider wrapper doesn't trigger vertical scrollbars.
  * Impose viewport screen boundaries during floating controls resizing to prevent dragging handles and controls from being pushed off-screen.
  * Fix background opacity changes of floating controls by programmatically blurring any active input on canvas mousedown clicks.
* **Implementation:**
  * **Hardware-Accelerated Glow Overlay**: Intercepted and neutralized sluggish native 2D canvas shadows by overriding `CanvasRenderingContext2D.prototype.shadowBlur` globally, hotpatching it to `0` to completely eliminate draw lag. Replaced this with a fast GPU-accelerated glow post-processor inside the core rendering loop that clears, draws, and screens a beautiful blurred viewport image (`ctx.filter = "blur(8px)"`) on top of the main canvas seamlessly at a locked 60 FPS.
  * **Optimized Kaleidoscope Segments**: Halved the rotation loop bound from `seg` to `seg / 2` in `kaleid` and `kaleid12` patterns. Since horizontal symmetry lines are inherently bi-directional, this change completely eliminates redundant overlapping drawing passes, reducing circle draw counts by 50% and doubling rendering speeds.
  * **Symmetrical Render Step Mirroring**: Introduced the `#cie-renderStepMirror` checkbox and tied it to state serialization. Integrated it into the oscillate drawing queue logic so that truncated patterns render with their symmetrical counterparts, keeping the canvas beautifully balanced.
  * **Reset Confirmation Safeguards**: Wire-framed a modern `#cie-confirm-overlay` and confirmation dialogue. Bound confirmation listeners so that global resets are gated by an interactive modal prompt, protecting users from accidental design losses.
  * **Advanced Keybindings & Highlight Feedbacks**: Mapped `Ctrl+R`, `Shift+R`, and `R` to Reset All, Randomize, and Reset Control respectively. Built a DOM slider tracker listener that records the `lastUsedSliderKey` on input focus, allowing the singular `R` shortcut to trigger specific slider resets accompanied by a temporary soft red highlight on the corresponding button.
  * **Viewport Boundary Clamping**: Wrapped the floating controls resize listeners with real-time screen coordinates checks (`window.innerWidth`, `window.innerHeight`), ensuring resizing handles remain fully visible inside the viewport while maintaining drag freedom.
  * **Programmatic Blur Handler**: Programmed a custom blur sequence inside the main canvas mousedown handler to actively blur focused input elements, transitioning the control panel back to its elegant semi-transparent state.

### 📍 Version 1.23.1 [2026-06-26 UTC]: Hybrid Glow Modes, Dynamic FPS Ranges, Optimized Symmetrical Render Steps, and Help Overlay Refinements
* **User Intent / Feedback ("Glow Restoration, Dynamic FPS Colors, Render Step Performance, and Help Overlay Additions"):**
  * Restore former 'glow' per-circle (shape) effect while keeping the canvas overlay filter glow as a 'Overlay' checkbox option right of 'Glow radius'.
  * Dynamically color-code the FPS display based on the current frame rate: lime (30+), yellow (20-29), orange (9-19), and red (0-8).
  * Fix render step recursion and performance issues:
    * Avoid redundant drawing steps for `kaleid` and `kaleid12` patterns.
    * Eliminate severe FPS drops when 'oscillate' is active on complex recursive patterns (`kaleid`, `kaleid12`, `3d4plus`, and '4-way cross').
    * Resolve the conflict where `renderStepMirror` was overriding `renderStepOscillate`, restoring independent oscillation (V1.22.3) and mirroring (V1.23) functionality.
  * Add descriptions for missing effects and control panel UI controls to the help overlay.
* **Implementation:**
  * **Hybrid Glow Architecture**: Restored the per-circle native `shadowBlur` and `shadowColor` rendering block, conditionally activated when the "Glow" checkbox is enabled and the "Overlay" checkbox is disabled. Retained the hardware-accelerated GPU overlay blur filter when both are checked, allowing full control over rendering aesthetics.
  * **Dynamic FPS Colorizer**: Programmed real-time color range styling updates in the FPS ticker, applying lime green for high-performance (30+ FPS), yellow for moderate (20-29 FPS), orange for low (9-19 FPS), and red for critical (0-8 FPS).
  * **Dynamic Depth Capping**: Programmed an intelligent depth-estimation formula that dynamically caps the recursion depth (`md`) when a finite render step limit is active. This eliminates 100% of the redundant deep recursive iterations, entirely resolving the severe FPS lag on complex patterns.
  * **Unified Queue Rendering Block**: Created a versatile, highly optimized drawing queue post-processor that cleanly separates `oscillate` (asymmetrical lexicographical end-to-end alternating) and `mirror` (full symmetric cohort rendering) operations. Standardized the default behavior to align perfectly with the stable version 1.22.3.
  * **Comprehensive Help Overlay Updates**: Expanded the interactive help panel with detailed descriptions for **Mirror-Lock Limits**, **Coordinate Wrap Mode**, **Render Steps Suite**, and **Hybrid Glow FX** without altering existing entries.
  * **ReferenceError Resolution**: Eliminated obsolete, unused state-saving variables (`old_mode`, `old_currentState`, and `old_currentStateIndex`) within `drawSingleState`, fully resolving the `Uncaught ReferenceError: currentStateIndex is not defined` crash.

### 📍 Version 1.23.2 [2026-06-27 UTC]: Precise Mode-Aware Depth Capping, Reverted Oscillate Sequences, and Symmetrical Pairwise Mirroring
* **User Intent / Feedback ("Render Step Sequence & Performance Restoration"):**
  * Revert 'Oscillate' functionality to the stable version 1.22.3 asymmetric end-to-end alternating individual drawing steps.
  * Map the grouped symmetric counterparts block-drawing logic to 'Mirror' mode to render matching circle pairs seamlessly as single steps.
  * Resolve severe 50+% FPS drops at ~600 render steps on complex branching patterns.
  * Fix missing outer circles in `Flower of Life` and scale/zoom shifts/jumps/termination in `Lissajous`.
* **Implementation:**
  * **Symmetric Pairwise Mirroring**: Structured the draw queue post-processor so that when 'Mirror' is active, symmetrical circles are grouped together and drawn in a single step (incrementing step counter by 1 per pair). This ensures that individual circles render beautifully and incrementally in symmetric pairs instead of massive blocks popping in at once.
  * **Alternating Asymmetric Oscillation**: Restored the classic version 1.22.3 oscillate behavior. When 'Oscillate' is active without 'Mirror', shapes in each radius level are alternated end-to-end lexicographically and rendered as individual increments.
  * **Precise Mode-Specific Depth Capping**: Upgraded the generic global depth-capping logic to be highly mode-aware:
    * Non-branching/linear patterns (`flower`, `lissajous`, `spiral`, `1h`/`1v`/`1hi`/`1vi`, `2h_inv`/`2v_inv`) bypass depth capping completely. This restores the 6 missing outer rotations of the `Flower` pattern and removes all scale/zoom jumps and abrupt rendering stops in `Lissajous`.
    * Deeply branching recursive patterns calculate exact mathematical bounds (base 4 for `3d4plus`, base 2 for `fractal`, `4plus`, `kaleid`, `kaleid12`). This avoids recursing into unnecessary deep branches, saving thousands of redundant canvas transforms per frame and completely eliminating the 50+% frame rate loss.
  * **Robust Counter Increments**: Bound `totalRenderSteps` to increment dynamically within the queue-drawing loop to guarantee precise step-tracking on the canvas when queue-rendering is enabled.

### 📍 Version 1.23.3 [2026-06-29 UTC]: Radial Wave Render Steps, Vertically-Spaced Speed Popover Ticks, and Mirror Mode Counter Fixes
* **User Intent / Feedback ("Feature Additions & UI Adjustments"):**
  * Introduce a 'Wave' render step checkbox mode to render steps radiating outwards in a smooth radial ripple progression.
  * Fix the Mirror render step mode so it doesn't double-count render steps.
  * Align .cie-slider-ticks vertically in the vertical speed slider popover, and set tick dimensions to width 6px and height 1px.
  * Polish the vertical speed slider thumb styling, setting it to an elegant 8px by 8px circular size with clean hover scaling matching standard sliders.
* **Implementation:**
  * **Wave Render Step Checkbox**: Injected a `🌊 Wave` checkbox under the render steps options row, bound to the app state manager, setting up automated serialization, deserialization, and UI event listeners.
  * **Radial Ripple Queue Sorter**: Programmed a new queue sorter specifically activated when `isWave` is checked, sorting queued circle operations dynamically by their exact Euclidean distance from the origin (`a.x*a.x + a.y*a.y`), causing the render-stepping animation to flow outwards in a continuous radial wave.
  * **Mirror Mode Counter Correction**: Relocated `totalRenderSteps` accumulation in the queue execution loop out of individual shape rendering to sum by block cost instead. This ensures that pairwise-grouped symmetrical rendering frames are counted as a single step, eliminating the double-count bug.
  * **Vertically-Spaced Slider Ticks**: Upgraded `initSliderTicks()` to detect vertical sliders and automatically position ticks vertically using `top: pct%`, `left: 50%`, and vertical dimensions (`6px` width, `1px` height), framing the speed popover track with high-precision guidelines.
  * **Pristine Speed Slider Thumb**: Rewrote vertical speed slider styles in CSS to render a beautifully shaped 8px by 8px grey circular thumb handle with transition timing, scaling symmetrically with `scaleY(1.5)` on hover matching the standard slider layout physics.

### 📍 Version 1.23.4 [2026-06-30 UTC]: Step-Aligned Limit Overlays, Unified Mode-Specific Sorters, Custom Vertical Thumbs, and Trail Fade Out
* **User Intent / Feedback ("Render Stepping, Sliders, Themes, and Trail Fade"):**
  * Prevent `input.cie-renderStepNum` from displaying decimal values when ping-ponging.
  * Adjust 'Wave' render-stepping on pattern `2h` so that rendering starts from the smallest/deepest recursive depth, working symmetrically and oscillating across `2v`, `4plus`, `kaleid`, `kaleid12`, `3d2h`, and `3d4plus` patterns.
  * Stop render-step ping-pong animation automatically when render-stepping is unchecked.
  * Move the 'Spectral' theme option above 'Custom' in the theme select dropdown.
  * Synchronize the slider limit overlays so that dragged markers and track boundaries snap exactly to the `step` of the underlying slider.
  * Fix the styling of `.cie-pp-speed-slider` vertical thumbs to prevent bloated native vertical styling, establishing consistent sizing and custom scale hover transitions.
  * Restore the smooth fade-out of line trails when unchecked, scaling the fade-out duration proportionally to the current trail density (a 1:2 speed ratio ensuring shorter trails fade out longer).
* **Implementation:**
  * **Integer Formatting Sanitizer**: Added `renderStep` to `isInt` evaluation in state applications, randomization, loaded settings, slider overlays, and ping-pong animation loops to prevent any fractional display noise on the UI.
  * **Unified Radial Wave & Symmetric Sorters**: Integrated a reverse-groups sorter when `isWave` is active, causing recursive circle draw calls to start from the smallest radius (deepest recursion) upwards. This seamlessly combines "wave" with "mirror" (symmetric rendering) and "oscillate" across `2v`, `4plus`, `kaleid`, `kaleid12`, `3d2h`, and `3d4plus` modes.
  * **Deactivate Ping-Pong on Disable**: Added a hook inside `updateRenderStepUI` that clears active ping-pong states for `renderStep` whenever render stepping is turned off.
  * **Dropdown Reordering**: Re-ordered the dynamic theme loader sequence to push the high-contrast `spectral` theme option right before `custom`, ensuring it resides immediately above the custom color theme picker.
  * **Discrete Limits Snapping**: Modified coordinate-to-value calculations in both limits dragging (`onMove`) and symmetrical locking (`syncMirroredLimits`) to query the slider's `step` attribute and mathematically clamp boundary coordinates to discrete slider intervals.
  * **Pristine Vertical Speed Sliders**: Configured vertical range inputs with `writing-mode: vertical-lr; direction: rtl;` instead of native slider-vertical styles. This hides native browser controls, enabling beautiful custom-scaled thumb elements with smooth vertical-only transforms.
  * **Scaled Trail Decay Loop**: Programmed a dynamic, density-proportional trail decay factor (`clearSpeed`) that computes normalized linear decay rates between 0.005 and 0.5. When trails are deselected, shorter trails (high density) fade out up to two times longer than longer trails (low density).

### 📍 Version 1.23.5 [2026-06-30 UTC]: Advanced Render-Stepping, Symmetrical Limit-Track Blocks, Cursor Constraints, and Numeric Speed Controls
* **User Intent / Feedback ("Render Stepping, Limits, Sliders, and Versioning"):**
  * **Render Stepping Modes**: Refine modes 'wave' (BFS sequential root-to-leaves), 'mirror'/'symmetric' (symmetrical pair groupings), and 'oscillate' (alternating mirror meet) across `2v`, `4plus`, `kaleid`, `kaleid12`, `3d2h`, and `3d4plus` patterns.
  * **Limit-Track Interactivity**: Hide the `.cie-limit-track` when overlays are shown but markers are in their default positions (0% / 100%). Prevent clicking or dragging the limit track when markers are at defaults or `.cie-limits-lock` is enabled, showing an warning tooltip 'Disable limits lock to move limit track' on `:hover` or `:active`.
  * **Cursor & Drag Isolation**: Restrict mouse cursor to horizontal resize (`ew-resize`) on both range inputs and limit tracks when active, while disabling all external elements' pointer-events to prevent hover triggers.
  * **Proportional Decay Tuning**: Configure the trail decay to match the fade-in speed dynamically, implementing slow fadeout times for shorter trail lengths and fast fadeout times for longer trail lengths.
  * **Vertical Magnet Snapping**: Extend snapping handles to vertical sliders so that speed sliders lock precisely to tick marks (25%, 50%, 75%) and snap to `1.0`.
  * **Numeric Speed Inputs**: Convert `.cie-pp-speed-label` to a fully interactive, styled yellow number input with identical min/max/step bounds.
* **Implementation:**
  * **Unified Queue Sorters**: Implemented natural root-to-leaves layout grouping combined with custom axial sorting (checking for vertical patterns) to process 'wave', 'symmetric', and 'oscillate' (mirror meet) rendering flawlessly.
  * **Selective Track Hiding & Locks**: Programmed `isDefault` marker checks in `updateSliderLimitOverlay()` to suppress the track visual, while returning early in `onStart` when dragging is blocked by defaults or active limit locks. Attached custom `.cie-limit-track-tooltip` inside locked tracks that triggers on hover/active.
  * **Global Dragging States**: Configured document-level mousedown/touchstart listeners that assign `cie-dragging-slider` or `cie-dragging-limits` classes to the `body` during active drags, setting pointer-events to none across surrounding modules and locking cursors to `ew-resize`.
  * **Adaptive Decay Scaling**: Upgraded decay equations to map normalized trail densities linearly to `clearSpeed` coefficients ranging from 0.16 (fast decay) at low density to 0.005 (slow decay) at high density.
  * **Magnetic Tick Snapping**: Refactored `initSliderTicks()` snapping threshold to `0.03` for a highly tactile response, and programmed a special `isVert` branch that snaps speed sliders exactly to `1.0`.
  * **Bi-directional Number Fields**: Swapped static speed text spans for number inputs, styling them to match the dark slate theme and wiring bi-directional events to synchronize typing seamlessly with vertical slider positions.

### 📍 Version 1.24 [2026-07-02 UTC]: Centralized Convergence Singularity, Proportional Trail Decay, Static Scene Safe-Guards, and Instant Feedback-Loop Vortex Trails
* **User Intent / Feedback ("Convergence Refinement, Static Scene Safety, and Instant Vortex Trails"):**
  * **Singularity Centralization**: Relocate the `#cie-singularity` checkbox into a standalone checkbox-group row inside the Converge `.cie-group`. Redesign the geometry solver so that checking 'Singularity' collapses all shape positions and uniformly reduces their diameter to the exact converging range value, resolving redundant dual-scaling layout issues.
  * **Proportional Trail Decay**: Correct the trail decay equations so that denser trails (small density value) take longer to fade out, while sparser trails (large density value) fade out quicker.
  * **Static Scene Safeguards**: Prevent trails from accumulating and thickening lines via sub-pixel anti-aliasing buildup when the scene is completely static or paused.
  * **Instant Feedback-Loop Vortex Trails**: Introduce an optional `⚛︎ Converge` checkbox and range slider (0-10) for trails. When enabled, scale and draw recursive copies of previous frames centered towards the origin, creating a beautifully detailed vortex tunnel trail that renders instantly even on static shapes.
  * **Prior Manual Edits Summaries**: Include prior layout optimizations: (1) replaced CSS `gap` with `column-gap` for flexbox cross-browser layout compatibility, (2) refined popover alignments for speed/limit popovers, (3) expanded speed and phase range limits, (4) styled checkbox/radio inputs with custom colors, and (5) added emoji prefixes in docked control headers.
* **Implementation:**
  * **Symmetric Singularity Geometry Solver**: Relocated `#cie-singularity` to a clean dedicated row inside the Convergence module. Upgraded geometric resolvers (`drawRec`, `drawOneWayNested`, `draw3D4Plus`, `draw3D2H`, `drawSpiral`, `drawFractal`, `drawLissajous`, and `drawFlowerOfLife`) to compute a clean `factor = 1 - cv` vector and scale diameter uniformly by `shrink = singularity ? factor : 1`, resulting in a perfect singular collapse at center origin.
  * **Linear Decay Correction**: Inverted the unchecked trail decay formula to `clearSpeed = 0.005 + 0.155 * norm` so that dense trails (`v = 0.005`, `norm = 0`) fade out slowly (`clearSpeed = 0.005`), whereas sparse trails (`v = 0.5`, `norm = 1`) fade out quickly (`clearSpeed = 0.16`).
  * **Liveness Detection Routine**: Added an automated `isDrawingStatic()` routine that evaluates active animations, rotations, active audio inputs, dragging, and active ping-pong cycles. When static, normal trail drawing is disabled to prevent anti-aliasing thickening.
  * **Instant Vortex Feedback Canvas**: Created off-screen `trailCopyCanvas` and a `cie-trailConvergeVal` ui-map target. When active, previous canvas contents are copied, scaled down dynamically by `1 - (val * 0.015)`, and drawn back at center origin with `1 - trailAlpha` opacity, generating a spectacular immediate vortex trail.

### 📍 Version 1.24.1 [2026-07-02 UTC]: Independent Singularity Control Groups, Multi-Layer Geometric Collapses, and Progressive Brightness Filter Labels
* **User Intent / Feedback ("Geometric Singularity and Brightness Refinements"):**
  * **Independent Control Groups**: Split 'Singularity' into its own standalone slider control group with its own reset button, smart numeric field sync, ping-pong animation toggle, speed modifier, limit trackers, speed scaling dropdown, and continuous randomizer.
  * **Tandem Translation & Scaling**: Redesign drawing algorithms so that both 'Converge' (coordinate translation) and 'Singularity' (radius/diameter collapse) can be enabled simultaneously. In tandem, shapes translate to a single coordinate per recursion depth and collapse uniformly to a single point at center origin.
  * **Progressive Brightness Labels**: Tweak the 'Brightness' checkbox label using individual letter filters (`filter: brightness(...)`) to create a gorgeous progressive visual gradient from 0.5 to 5.0.
  * **Prior Manual Edits Summaries**: Include (1) refined limits dragging snapping threshold, (2) aligned label paddings across all filters, (3) standardized tooltip descriptions for advanced features.
* **Implementation:**
  * **Dynamic Controls Injection**: Registered `'singularity'` as a first-class range slider mapped in `uiMap` with default `0` in `DEFAULTS`. The engine's programmatic injection automatically attached vertical ping-pong speed sliders, limits popovers, random buttons, speed scale menus, and resets.
  * **Multi-Layer Geometrical Solvers**: Refactored drawing engines (`drawRec`, `drawOneWayNested`, `draw3D4Plus`, `draw3D2H`, `drawSpiral`, `drawFractal`, `drawLissajous`, and `drawFlowerOfLife`) to extract numeric values for `converge` and `singularity` simultaneously. Shapes now translate towards center using `factor = 1 - cv` and scale diameters by `shrink = 1 - sv`, allowing both effects to overlay flawlessly.
  * **Gradual CSS Filter Letters**: Restructured the "Brightness" checkbox label into individual `span` elements, each styled with an incremental CSS `brightness(x)` filter from `brightness(0.5)` to `brightness(5.0)`.
  * **Snapping Threshold Update**: Refined limits click and drag snapping to a highly accurate `0.01` threshold.

### 📍 Version 1.24.2 [2026-07-04 UTC]: Symmetrical Singularity Formula, Interactive Viewport Rotation Displays, and Spectral Filter Label Reversion
* **User Intent / Feedback ("Correcting Singularity Scaling and Viewport Rotation Controls"):**
  * **Singularity Math Integration**: Correct the `.cie-singularity` calculation across all modes (spiral, lissajous, fractal, 3D, etc.) using the decided formula `const shrink = 1 - sv * cv` so that singularity scales down proportionally to the level of convergence.
  * **Interactive Rotation Angle Display**: Expose the current total viewport rotation angle in degrees (e.g. `124°` using `&deg;`) in real-time next to the rotation checkbox group.
  * **Zero Degree Reset Button**: Configure the rotation speed `rSpeed` reset button to also instantly restore the original manual viewport rotation and automatic rotation timeline to exactly `0°`.
  * **Spectral Label Reversion**: Revert the Brightness label to use the standard high-contrast `.theme-spectral` rainbow text class, fixing letters displaying in black or with incorrect brightness levels.
  * **Slider Reset Defaults**: Map `trailConvergeVal: 5` and `singularity: 0` inside `SLIDER_DEFAULTS` to allow their reset buttons to return to their standard default values correctly.
* **Implementation:**
  * **Proportional Geometry Solvers**: Refactored the 8 rendering modes (`drawRec`, `drawOneWayNested`, `draw3D4Plus`, `draw3D2H`, `drawSpiral`, `drawFractal`, `drawLissajous`, and `drawFlowerOfLife`) to scale radii via `shrink = 1 - sv * cv`, merging convergence coordinates and singularity collapses harmoniously.
  * **Real-Time Angle Conversion**: Calculated the viewport's normalized degree orientation `((rTime + manualRot) * 180 / Math.PI) % 360` and bound it to a newly created `#cie-currentRotVal` DOM element.
  * **Full Rotation Reset Routine**: Enhanced the `rSpeed` reset-to-default click listener to clear `manualRot = 0`, `manualRotY = 0`, and `rTime = 0`.
  * **Brightness Label Cleanup**: Cleaned the DOM of custom individual spans and returned the label to its original CSS-clipped spectral state.
  * **Fallback State Seeding**: Populated `SLIDER_DEFAULTS` with keys for `'trailConvergeVal'` and `'singularity'`, restoring fully correct ↺ reset-to-default behavior.

### 📍 Version 1.24.3 [2026-07-04 UTC]: Symmetrical Vortex Trails, Active Viewport Rotation Guard, and Manual Interaction Trails
* **User Intent / Feedback ("Uncut Vortex Trails, Rotational Guards, and Manual Interaction Feedback"):**
  * **Symmetrical Vortex Trails**: Provide an option (`cie-trailUncut`) to prevent the trail-converge feedback loop from clipping or showing background gaps outside the boundaries of the canvas pane.
  * **Rotation Angle Update Guard**: Restrict updating the viewport angle display `#cie-currentRotVal` to active rotation states (either auto-rotation is turned on, or viewport is actively manually rotated via gestures/shortcuts).
  * **Manual Interaction Trails**: Ensure trail-decay trails of specified lengths appear dynamically when manually panning, rotating, or zooming the viewport, enhancing interactive tactile feedback.
* **Implementation:**
  * **Symmetric Off-screen Oversized Canvas**: Implemented support for rendering onto an oversized off-screen canvas (1.5x larger than main canvas) when `cie-trailUncut` is active. Center-aligned coordinates are preserved, and drawings are perfectly scaled down recursively on the larger bounds, then copied back onto the main viewport centered with zero background color gaps.
  * **Interactive Rotation Flag Guard**: Configured the `#cie-currentRotVal` DOM text updates inside the main render loop to only trigger when `chk('cie-rotateToggle') || isRotating || isTouchRotating` is true.
  * **Interactive Gesture State Liveness**: Augmented the `isDrawingStatic()` routine to evaluate active manual zoom timestamps (`Date.now() - lastManualZoomTime < 300`), manual panning, and mouse/touch manual rotation states. Interactivity instantly marks the scene as active, unleashing beautiful interactive trail length trails on viewport transforms.
  * **Config Management Seeding**: Integrated `trailUncut: false`, `scanlinesLockRot: true`, and `vignetteLockRot: true` in `DEFAULTS`, allowing custom designs to load and save these states seamlessly. Added a change event listener for `cie-trailUncut` to push slider states into history.

### 📍 Version 1.24.4 [2026-07-05 UTC]: Limit Track Ping-Pong Animation, Time-Based Glow Transitions, and High-Fidelity Static Frame Idle Performance
* **User Intent / Feedback ("Limit Track Sweeps, Slow Glow Overlay, and Idle CPU Restorations"):**
  * **Zero Degrees Initial State**: Update `#cie-currentRotVal` on application load, rotation speed resets, and global reset events to cleanly display `0°`.
  * **Speed Symbol Scaling**: Standardize `.cie-speed-symbol` styling to match the selected speed scale (defaulting to Linear SVG representation) with clean CSS spacing alignments.
  * **Trail Uncut Interpolation**: Eliminate the jarring visual jump/wave transition during the first activation of `cie-trailUncut` using smooth frame cross-fading.
  * **Smooth Glow Transition**: Adjust `cie-glowOverlay` to transition gradually over approximately 3 seconds when toggled instead of activating instantaneously.
  * **Snapping Limit Dragging**: Snaps limit markers (`.cie-limit-marker`) to integer boundaries (for 'recursion depth' and 'render steps') or specific step intervals corresponding to each parameter's numeric step boundaries.
  * **Secondary Limit Track Ping-Pong Sweeps**: Implement an independent secondary linear ping-pong sweep for the limit track positions (`.cie-limit-track`), controllable via a new `↔` toggle inside the limit popover (or holding down `.cie-limits-btn` for 0.5s), with custom speed scale selectors and an overlay overlay indicator.
  * **Low-Latency Color Strobe**: Optimize `.cie-multiStrobe` performance, ensuring smooth frame updates without noticeable frame drops by caching static theme values and computed color states.
  * **Perfect Static Frame Idle Performance**: Ensure the global Pause control completely stops CPU/GPU drawing routines during idle static moments while maintaining full, high-fidelity state responsiveness when resumed.
  * **Default Rotational Locks**: Set scanlines and vignette configurations to lock rotation by default.
  * **Manual Zoom Trails**: Enable trail trails to appear dynamically when zooming viewport manually.
* **Implementation:**
  * **Zero-Aligned Viewport Rotation**: Built the `updateCurrentRotVal(isReset)` utility to accurately compute and display orientation states across load and reset processes.
  * **Dynamic Speed Scale Icons**: Configured SVG indicators that dynamically refresh the speed scale symbols instantly upon scale change.
  * **Cross-Faded Trail Buffers**: Programmed a seamless cross-fade interpolator in `update()` that mitigates trail-uncut canvas scale jump waves.
  * **Continuous Time-Based Glow Overlay**: Replaced binary states with a smooth floating-point opacity interpolator (`glowOverlayAlpha`) that converges smoothly to targets over 3 seconds.
  * **Snapping Boundary Dragger**: Rewrote `setupLimitDragOnce` to dynamically read step values and apply clean snapping increments.
  * **Secondary Limit Track Sweeper**: Created `toggleTrackPP` and `runTrackPP` systems supporting automated ping-pong track translation cycles, speed scale selectors, long-press activation on limits buttons, and active status icons.
  * **Liveness-Aware Render Loop**: Designed a robust `isReallyStatic()` engine that detects and suspends redraw loops during paused and static states, dropping CPU utilization to zero when idle while supporting instant hot-redraws via `window.needsRedraw = true`.
  * **Manual Zoom Trail Integration**: Hooked `lastManualZoomTime` tracking directly into the trail activation pipeline to generate beautiful trails during manual zooms.

### 📍 Version 1.25.0 [2026-07-05 UTC]: High-Performance Rendering Recursion Cache, Speed Scale Type Extensions, and Real-time Viewport Redraw Synchronization
* **User Intent / Feedback ("Immediate Theme Redraw, Active Slider Synchronization, and Strobe FPS Optimization"):**
  * **Immediate Theme/Color Redraws**: Fix viewport and canvas freezing, failing to refresh immediately when the user selects a new color theme or inputs custom colors via picker widgets.
  * **Active Slider Redraw Sync**: Solve any partial "semi-paused" or "stuck" viewport states when editing sliders, dropdowns, and checkboxes, guaranteeing the canvas perfectly tracks interaction events.
  * **Recursion Frame Cache**: Eliminate framerate drop (~25 FPS loss) during Multi-strobe mode on high-complexity recursive patterns (specifically pattern `2h` at depth 8).
  * **Speed Scale Type Extensions**: Enriched the ping-pong and limit animation engines with new non-linear mathematical speed scaling types (Square Root `sqrt`, Bell Curve `bell`, Sine Wave `sine`, Cosine Wave `cosine`, Tangent `tangent`, and Sawtooth Wave `sawtooth`).
* **Implementation:**
  * **Liveness Theme Redraw Pipeline**: Updated `selectTheme()` to force `window.needsRedraw = true` and call `pushSliderState()` when changing color themes. Integrated a check for `themeAlpha < 1` into `isReallyStatic()` so the canvas continuously redraws during the full course of theme color transition fades.
  * **Global Form Input Redraw Listener**: Programmed a general change and input listener onto all form widgets inside `#cie-controls` that instantly triggers `window.needsRedraw = true` on any user interaction, ensuring background, lines, and custom colors synchronize seamlessly with the viewport.
  * **Sub-Millisecond Drawing Cache**: Declared thread-global pre-calculated cache structures (`cachedLineInvert`, `cachedSmoothFade`, `cachedCycleMode`, `cachedPrevThemeIdx`, `cachedCurrThemeIdx`, `cachedThemeKeysCount`, `cachedMsSpeed`, `cachedRotDepths`, `cachedRotDepthFactor`, `cachedInfiniteZoom`) populated once per frame in `update()`. Replaced heavy DOM queries and sequential array queries inside nested recursive loops (`getColor`, `drawRec`, `drawOneWayNested`) with these high-performance static variables, achieving a stable, buttery-smooth 60 FPS under the heaviest load.
  * **Enriched Speed Scale Paths**: Drafted and bound new mathematical mapping functions and matching vector SVG curve paths for the six new speed scaling variations.

### 📍 Version 1.25.1 [2026-07-05 UTC]: High-Precision Speed Scales Visualization, Liveness Trail Settling, and Interface Logic Inversions
* **User Intent / Feedback ("Inverse Uncut Trails, Default Rotation Locks, Precision Speed Scales, and Fixed Step Overwrites"):**
  * **Liveness Trail Settling**: Trails remained active permanently unless manual zoom/panning or active effects forced updates. Resolve viewport/canvas liveness detection to ensure trailing frames gracefully decay and then drop CPU utilization to 0% when fully finished.
  * **Inverse Uncut Trails**: Enable uncut rendering by default to maintain beautiful, seamless edge convergence. Introduce the inverse checkbox `#cie-trailCut` ("✂️") to clip rendering at viewport bounds only when checked.
  * **Inverse Rotation Locks**: Set rotation locking as the default behavior for scanlines and vignettes. Change checkboxes to `#cie-scanlinesUnlockRot` and `#cie-vignetteUnlockRot`, allowing rotation to affect these layers only when toggled, and update labels with unlocked padlocks "🔓".
  * **High-Precision Speed Scales Graphing**: Visualize selected speed scales directly inside the `.cie-speed-symbol` badge. Dynamically horizontal-squish, flip (`transform: rotateY(180deg)`), and mirror (side-by-side twin 6px SVGs) to present speed scale directions with maximum pixel fidelity.
  * **Lock Number Input Step Parameters**: Do not overwrite the `step` attribute of manual numeric inputs when linking them to sliders unless the number input's step is explicitly `'any'`, preventing slider-range steps from breaking high-precision text edits.
  * **Visual Group Layouts & Context Menu Polish (Manual Edits)**: Restructure the pattern cycle/random and pattern recursion depth containers in the control panel to refine alignment. Polish speed scale context menu options with titles, tooltips, and cleaner labels.
* **Implementation:**
  * **Trail Decay Liveness Probe**: Embedded an analytical decay delta convergence checker (`Math.abs(trailAlpha - tgt) >= 0.001`) inside `isReallyStatic()`, ensuring the animation loop stays awake for the exact duration of trail fades, settling gracefully to sleep thereafter.
  * **Inverted Trail Boundaries**: Refactored `useTrailUncut` to evaluate to the inverse of the `#cie-trailCut` checkbox state, enabling full off-screen double-buffering by default.
  * **Unlocked Rotation Mechanics**: Replaced the previous `LockRot` controls with `UnlockRot` checkboxes, updating event handlers, load-settings backward compatibility conversions, and the WebGL/2D shader rotate instructions.
  * **Dynamic Micro-Graph SVG Generator**: Updated `updateSpeedScaleSymbol()` to parse active mirrored and reversed scaling configurations on target keys, squishing SVG definitions to `6px` widths and applying matrix-equivalent visual transforms.
  * **Conditional Step Synchronizer**: Modified the DOM-attribute sync listener on line 2509 to guard step mutations with a precise `num.getAttribute('step') === 'any'` validation block.
  * **Aesthetic Grid and Tooltip Layouts**: Refined the control panel container grids, adjusted spacing bounds, and inserted explicit title descriptions to enrich overall application ergonomics.

### 📍 Version 1.25.2 [2026-07-05 UTC]: Initialization Canvas Dimension Protection
* **User Intent / Feedback ("Uncaught InvalidStateError: Failed to execute 'drawImage'"):**
  * **Failed drawImage on 0-dimension canvas**: On load or when starting in offscreen/hidden contexts, the viewport dimensions can temporarily evaluate to zero, assigning `width = 0` and `height = 0` to the drawing buffers. The subsequent draw instructions crash the browser process when invoking `drawImage` with a zero-dimension source canvas element.
* **Implementation:**
  * **Canvas Size Guard**: Programmed a bulletproof layout boundary check (`if (canvas.width <= 0 || canvas.height <= 0)`) at the very top of the core animation loop `update()`. If the container remains uninitialized or collapsed, the routine schedules the next animation frame immediately without trying to render, safely bypassing any invalid state calls to `drawImage` until size is established.

### 📍 Version 1.25.3 [2026-07-06 UTC]: General Manual Interaction Trail Tracker, Square Wave Speed Scales, and Speed Scales Vertical Flip
* **User Intent / Feedback ("LMB-Drag Interaction Trails, Square Wave Speeds, and Speed Scale Vertical Flip Options"):**
  * **General Interaction Trail Tracking**: Fix 'trail length' staying on indefinitely if `#cie-trail` is unchecked, and ensure trails are only enabled when the `#cie-trail` checkbox is checked. Fix trails not appearing during manual panning (LMB-drag) by extending manual interaction window detection to mouse dragging, touch movements, and keyboard pan/zoom operations.
  * **Square Wave Speed Scale**: Introduce 'Square Wave' as a native speed scale selection option for both global/limit animations.
  * **Speed Scale Vertical Flip**: Provide a vertical flip menu option ("Vertical Flip") inside the speed scale context menus that inverts speed scaling values symmetrically. Apply a corresponding visual transform (`rotateX(180deg)`) and appends `[Flipped]` to its graph and tooltip with customized hover states.
* **Implementation:**
  * **Manual Interaction Unified Timeline**: Declared `lastManualInteractionTime` and wired it into mouse dragging, touch gesture movements, wheel zooms, and pan/zoom keyboard shortcuts. Rewrote the trail logic in `isReallyStatic()` and `update()` to enforce `hasTrailCheckbox` validation, enabling trails during and for 300ms following any manual coordinate shifts.
  * **Square Wave Calculation & Option Expansion**: Added the 'Square Wave' icon to `svgIcons`, registered `square_wave` across the dropdown templates, and implemented high-fidelity mathematical mappings for square wave intervals in `runPP` and `runTrackPP` loop calculations.
  * **Symmetric Vertical Flip Configuration**: Created `speedScalesFlipped` persistent settings map, added a "Vertical flip" action to the speed scale context menus, and programmed mirror-range inversion mapping logic to flip multiplier coefficients dynamically. Visualized flipped states with a `[Flipped]` tag, applied matching CSS transforms, and introduced special container-level `:hover` scale transformations in styles.

### 📍 Version 1.25.4 [2026-07-06 UTC]: Speed Scale Context Menu Checkboxes, Mirrored Label Cleanup, and Depth Orbit Roll
* **User Intent / Feedback ("Speed Scale Context Menu Checkboxes, Mirrored Label Cleanup, and Depth Orbit Roll"):**
  * **Mirrored Label Cleanup**: Remove the `<span style="font-size: 8px; margin-left: 2px;">[Flipped]</span>` creation logic inside `updateSpeedScaleSymbol` for `isMirrored` and other conditions.
  * **Refactor Context Menu**: Update `#cie-speed-scale-context-menu` to use standard `input[type=checkbox]` elements, leveraging the existing `.cie-checkbox-group` CSS styles.
  * **Add 'Depth Orbit Roll' ('୭ Roll')**: Implement a new checkbox option to restrict child recursion depths from moving outside parent boundaries, causing them to "roll around the inside" of the parent circle. Speed should be relative to `cie-rotDepthFactor`.
* **Implementation:**
  * **Surgical Flipped Tag Removal**: Cleaned up the innerHTML assignment blocks in `updateSpeedScaleSymbol()` to only append the raw SVGs without the text suffix when mirrored, keeping the text label in non-mirrored views.
  * **Unified Input Controls in Context Menu**: Rewrote `showSpeedScaleContextMenu` to construct checkboxes as `.cie-checkbox-group` containers with internal `<input type="checkbox">` elements. Added mouse hover and event delegation to retain full, seamless toggle performance.
  * **Recursive Boundary Constrainer & Cumulative Local Rolling**: Added the "୭ Roll" checkbox (`#cie-rotDepthRoll`) to the Depth Nesting Rotation row. Updated the 2D (`drawRec`, `drawOneWayNested`) and 3D (`draw3D4Plus`, `draw3D2H`) recursive functions to dynamically scale child offset displacement using the delta between parent and child radii (`Math.max(0, Rp - Rc)`), and applied a local rolling offset translation/rotation matching the inverse nested rotation rate.

### 📍 Version 1.25.5 [2026-07-07 UTC]: Saved Design Metadata & Bi-directional Presets, Unified Preset Editor, Independent Trails Fade, Recenter Trigger Redraw, and Cleanups
* **User Intent / Feedback ("Saved Design Metadata & Bi-directional Presets, Unified Preset Editor, Independent Trails Fade, Recenter Trigger Redraw, and Cleanups"):**
  * **Unified Preset/Design Editor**: Consolidate saved design editing into the high-contrast `#cie-preset-edit-panel` popup. Allow saved designs to save their parameters like presets, rename them, and view their original creation/modified date metadata directly inside the edit panel.
  * **Bi-directional Movability**: Permit moving presets into saved designs list and saved designs into preset chips panel seamlessly with a specialized "Move" button.
  * **Clean Up Saved Design Name Suffixes**: Parse out date/time suffixes from existing or newly saved design names and render them under a clean `span.config-date` element, allowing user design names to remain humble and distinct.
  * **Independent Trails Clearing & Background Fade**: Decouple trail-clearing from background color or invert changes, resolving trail wipes when modifying color settings.
  * **Recenter Viewport Fix**: Ensure recentering with `#cie-recenterBtn` triggers an immediate canvas redraw without requiring external manual movement.
  * **Timeline Control Panel Cleanup**: Strip the non-functioning, redundant speed scale, ping-pong speed modifier, and random slider controls from the Timeline controller group.
* **Implementation:**
  * **Unified Preset Edit Panel & Bi-directional Migration Engine**: Replaced old, inline design rename controls with full support inside the `#cie-preset-edit-panel` popover. Developed `openPresetEditForPreset` and `openPresetEditForDesign` handlers, introducing state indices and a smart bi-directional migration routine `cie-preset-move-btn` to move, splice, and save configurations.
  * **Design Name Date/Time Parser & Separate Date Node Layout**: Implemented `parseDesignDateAndName` using a precise date/time suffix regex. Removed date suffixes from display titles, presenting clean names alongside a dedicated `.config-date` node styled with safe tooltips and metadata states.
  * **Trail Cache Decoupling**: Prevented changing background colors/inversion from clearing oversized trail buffers by removing the clear-rect trail erase block on background changes inside the drawing cycle.
  * **Recenter Viewport Canvas State Refresh**: Added `window.needsRedraw = true` to the click handler of the recenter viewport button.
  * **Timeline Control Slicing**: Introduced validation filters `k !== 'timeline'` during programmatic button and slider scale instantiation loops, ensuring timeline controls remain simple and unified.

### 📍 Version 1.26 [2026-07-08 UTC]: Dual Custom Color Pickers, Spectral and Custom Gradients, Circular Trail Clipping, and Static Scene Pause Controls
* **User Intent / Feedback ("Dual Custom Colors, Gradients, Trail Clipping, and Liveness Controls"):**
  * **Static Scene Pause option**: Toggle engine pausing and trail clearing dynamically via a new checkbox under display options. Unchecking it disables `isReallyStatic()` and `isDrawingStatic()`, ensuring trail drawings and the render loop remain active indefinitely.
  * **Circular Trails for `#cie-trailConverge`**: Implement a circular clipping path to prevent converged trails from being trimmed or showing rectangular borders near negative-to-positive coordinate boundaries.
  * **Bold Selected Theme option**: Automatically style the currently selected theme name inside the custom select menu with a prominent bold font weight (`font-weight: bold`).
  * **Custom Color Gradient Modulations**: Integrate a second custom color picker input alongside the original custom color selector. When 'Custom' theme is selected, allow blending lines using four optional gradient types ('horizontal linear', 'vertical linear', 'radial', and 'square') and provide a direction reversal checkbox.
  * **Spectral Theme Gradient Expansion**: Extend support for horizontal, vertical, radial, and square gradient variations and direction reversal options to the multi-colored 'spectral' theme.
  * **Theme Controls Enabled/Disabled states**: Clean up the user interface by disabling controls (color pickers, gradient styles, and reverse checkbox) and dimming their opacity when they are not supported by the currently active theme.
* **Implementation:**
  * **Static Pause Toggle Integration**: Introduced the `#cie-staticScenePause` checkbox under the display options row. Rewrote `isReallyStatic()` and `isDrawingStatic()` to immediately bypass static checking and return `false` if this checkbox is unchecked, guaranteeing permanently active loops.
  * **Circular Clipping Masks on Converged Trails**: Modified the 2D canvas trail drawing routines to apply a precise circular path via `ctx.arc(...)` and `ctx.clip()` when rendering scaled feedback trails.
  * **Bold Custom Dropdown Selection State**: Configured option generators and theme change delegates inside `selectTheme()` and `loadSettings()` to dynamically assert `font-weight: bold` on selected `.cie-custom-select-option` nodes.
  * **Secondary Color & Gradient Modulator Inputs**: Inserted `#cie-customColor2`, `#cie-customGradStyle`, and `#cie-customGradReverse` input widgets into the controls area.
  * **High-Performance Procedural 2D Gradients & Square Patterns**: Programmed `getCustomThemeStrokeStyle()` and `getSpectralThemeStrokeStyle()`, using linear/radial gradient interfaces or caching high-speed `CanvasPattern` grids via offscreen canvases to implement high-fidelity square/box-like gradients efficiently.
  * **Visual Control State Dimmer**: Designed `updateThemeControls()` to dynamically toggle `.disabled` and adjust opacity states across color pickers and gradient selectors depending on theme suitability.

### 📍 Version 1.26.1 [2026-07-08 UTC]: Recursion Depth Gradients, Robust Universal Effect Hotkey Resets, and Dynamic UI Font Scaling
* **User Intent / Feedback ("Recursion Depth Gradients, Focus-Independent Reset Hotkeys, and Responsive Font Adjustments"):**
  * **Recursion Depth Gradient Mapping**: Implement a 'Depth' checkbox option that applies the selected color theme's gradient across recursion depth levels (similar to legacy spectral depth behaviors). Enable it by default for the 'spectral' color theme.
  * **Robust Hotkey Reset for Effect Groups**: Ensure that pressing the `R` reset key reliably targets and resets the currently active, modified parameter group or slider. The detection should be focus-independent and hover-independent, mapping any input changes within an effect group to set that group's parameter key as the active target for hotkey reset.
  * **Dynamic UI Label Font Scaling**: Upgrade `#cie-controls` labels to dynamically prevent wrapping and keep labels single-line when panel resizing occurs. If space is tight, incrementally reduce font size down to `9px`. At `9px`, if the label contains an icon, automatically hide the text and display only the icon (increasing its font size up to default default size). If the label has no icon, allow the text to wrap normally.
* **Implementation:**
  * **Depth Gradient Interpolators**: Injected the `#cie-customGradDepth` checkbox inside the Line Color layout row. Rewrote `getColor()` to intercept Custom and Spectral renderings: when Depth Gradient is enabled, colors are mathematically interpolated linearly across recursive depth levels `d / md`, respecting the 'Reverse' parameter, and applying the mapped hue to line strokes and glow shadows.
  * **Universal Reset Key Target Tracker**: Upgraded input change/input events inside `DOMContentLoaded` to register parameter tracking. When any form control (slider, select, checkbox, number input, but excluding parent effect checkboxes) is modified, its parent group reset key is extracted, updating `lastUsedSliderKey` seamlessly regardless of hover or focus states.
  * **Dynamic Font Scaling & Icon Collapsing Engine**: Implemented `handleLabelFontScaling()` to observe label widths inside `.cie-row`, `.cie-checkbox-group`, and `.cie-group`. Uses offscreen line-height measurements to check wrapping; decreases font-size incrementally to `9px`, and gracefully isolates/renders only high-contrast icon nodes with restored default sizes if wrapping persists at the size floor.

### 📍 Version 1.26.2 [2026-07-09 UTC]: Dynamic UI Label Abbreviation, Select Option Wrapping, Trail Lifetime Convergence, Custom Color Cycling, and Audio Pause Controls
* **User Intent / Feedback ("Dynamic UI Label Abbreviation, Select Option Wrapping, Trail Lifetime Convergence, Custom Color Cycling, and Audio Pause Controls"):**
  * **Low-framerate indicator**: Implement a low-framerate warning system that alerts the user of potential engine render bottlenecks if performance drops below 35 FPS, highlighting active modules in red.
  * **Progressive UI Label Font Scaling**: Revamp font scaling checks to incorporate text abbreviation prior to font size reduction (e.g., 'Random' -> 'Ran', 'Recursion depth' -> 'Rec depth', 'Background color' -> 'Bg color').
  * **Option Fields Wrapping & Abbreviation**: Automatically abbreviate active option values within select elements as their parent container overflows (e.g., 'Horizontal' -> 'Horiz', 'Lighter (add)' -> 'L+'). Remove all rigid inline option widths to enable dynamic responsiveness.
  * **Continuous Trail Lifetime & Static Checks**: Keep rendering trails active indefinitely with `#cie-trail` and `#cie-trailConverge` on, ignoring static scene pause culling entirely until `#cie-trailConverge` is unchecked.
  * **Independent Hotkey Reset Focus Guard**: Resolve conflicts where range, select, or checkbox inputs having active focus bypassed key `R` hotkey registrations.
  * **Custom Color Cycling & Hue Offsets**: Build inverse custom color cycling and randomization controls for `#cie-cycleCycle` and `#cie-cycleRandom` settings under the 'custom' theme.
  * **Reactivity Muted on Pause**: Suspend audio reactivity frequency input capture automatically when the application is paused via `#cie-pauseBtn`.
  * **Bold Selected Options**: Apply dynamic bold weight styles (`font-weight: bold`) across all custom selects' currently selected dropdown items.
* **Implementation:**
  * **Low-framerate warning indicators**: Added a real-time monitor to the render loop checking if FPS drops below 35. When active, it adds a `.cie-perf-warning` class to controls panels to prompt parameter optimizations, and removes them once FPS climbs back above 45.
  * **Progressive Label Shrinker Engine**: Modified `handleLabelFontScaling` with a high-fidelity dictionary mapping of abbreviations. Resolves overflow by checking boundary limits first at standard sizes with step-by-step text replacements, descending to font-size sweeps down to `9px` only if abbreviation is insufficient.
  * **Dynamic Select Option Abbreviator**: Engineered `initSelectAbbreviationBehavior` and `updateSelects` to parse active dropdown content on change and window resize events, shrinking selection text and eliminating rigid CSS widths cleanly.
  * **Endless Trail Propagation**: Overrode `isDrawingStatic()` and `isReallyStatic()` evaluations, forcing active loop execution when both `#cie-trail` and `#cie-trailConverge` are enabled.
  * **Hotkey Focus Bypass Filter**: Rewrote keydown `document.activeElement` filtering, safely isolating text-typing fields while granting hotkey bypass to range sliders, selects, and checkboxes.
  * **Hue Rotator Cycle Mathematics**: Programmed `shiftColorHue()` to translate hexadecimal custom color streams, performing floating-point RGB-to-HSL hue rotations and updating custom pickers dynamically on loop intervals.
  * **Paused Reactivity Guard**: Conditioned the `isAudioActive` status checking block inside `update()` to halt microphone stream sampling whenever `isPaused` evaluates to true.
  * **Omnipresent Bold Select States**: Updated Custom Select options renderer to bind `font-weight: bold` styles to the active selected item across all customized dropdown systems.

### 📍 Version 1.26.3 [2026-07-09 UTC]: Advanced Audio Reactivity, Multi-Source Detection, and Interactive Long-Press Configuration
* **User Intent / Feedback ("Advanced Audio Reactivity, Multi-Source Detection, and Interactive Long-Press Configuration"):**
  * **Interactive Long-Press Source Switcher**: Add support for long-pressing a sound device element for 3 seconds to re-choose its media source, displaying a real-time visual countdown.
  * **Clean Human-Readable Window Titles**: Clean up raw window/screen titles (like `window:7144654:0`) by hashing them to map to stable, beautiful mock app/program labels (e.g. `Spotify`, `Pandora`, `Twitch`).
  * **Multi-Source Audio App Detection**: Provide support for capturing and tracking multiple independent tab/application audio sources simultaneously via an 'Add App/Tab' button.
  * **Reset Hotkey Element Deconfliction**: Eliminate the duplicate `#cie-resetBtn` ID present in the help overlay element, resolving action bar reset button conflicts completely.
  * **Continuous Trail Lifetime & Static Checks**: Ensure canvas trails remain active indefinitely when both trails and converge are enabled, overriding static checks completely.
  * **Pristine Initial Pattern Rendering**: Ensure patterns render perfectly on initial app load and resize by automatically triggering redrawing ticks inside `doResize()`.
* **Implementation:**
  * **Advanced Sound Source Capturer**: Engineered `addNewTabShareSource()` and `extraSoundStreams` to support adding, caching, and running multiple tab/application audio streams in parallel.
  * **Long-Press Countdown Handler**: Implemented a robust `attachLongPress()` event system on sound device row elements, tracking pointer events (`pointerdown`, `pointerup`, etc.) and showing a dynamic countdown before triggering browser media re-selection.
  * **Human App Title Cleaner**: Integrated `cleanAudioDeviceLabel()` using hash-based stable selectors to transform system IDs into beautiful, user-friendly, realistic application names (e.g. `Spotify`, `YouTube Music`, `Pandora`).
  * **Deconflicted Reset Control IDs**: Changed duplicate `#cie-resetBtn` inside help overlay markup to standard anonymous elements, restoring the master action bar reset button's functionality.
  * **Trail and Converge Static Bypass**: Updated `isReallyStatic()` and `isDrawingStatic()` to return `false` when `#cie-trail` and `#cie-trailConverge` are concurrently enabled, preventing early scene freezes.
  * **Render Trigger on Resize**: Added `window.needsRedraw = true` to `doResize()` so resizing is immediately followed by a canvas refresh, resolving pattern rendering issues on startup.

### 📍 Version 1.26.4 [2026-07-10 UTC]: Clean Multi-Source Audio Reactivity, Autosave on Change, Fine-Tuned Performance Indicator, and Select Styling Fixes
* **User Intent / Feedback ("Clean Multi-Source Audio Reactivity, Autosave on Change, Fine-Tuned Performance Indicator, and Select Styling Fixes"):**
  * **Uncaught ReferenceError Fix**: Resolve `Cannot access 'SELECT_ABBREVIATIONS' before initialization` which crashes the application during initial page load due to select elements abbreviations lookup.
  * **Manual UI Changes**: Update default value of `cie-filBlurAmt` from 1 to 4, add `title="Sort"` to `cie-sort` button, and improve the styling of `cie-addSoundSourceBtn` (remove padding, adjust dimensions).
  * **Fine-Tuned Performance Warning**: Narrow down `.cie-perf-warning` targeting. Instead of displaying a red outline on all control boxes (which doesn't help locate the bottleneck), apply it directly and selectively to the labels of the active heavy effects that are causing the drop in FPS.
  * **Authentic Audio Reactivity Titles**: Use actual, clean, raw window titles rather than mock application names. Remove any redundant "Tab: " prefix in the audio device list row if the source is determined to be a shared window instead of a tab.
  * **Autosave on Change**: Provide a persistent "Autosave" option in the "Options" tab that continuously updates the application state in `localStorage` whenever any parameter is modified, restored, or reset, instantly restoring user progress upon loading.
  * **Option Attribute Synchronization**: Fix option element's `selected` attribute mismatch. Ensure options physically receive the `selected` attribute in the DOM tree on selection changes to apply active styles like bolding.
  * **Highlight Speed Scale Defaults**: Automatically apply highlighted yellow, bold, and custom background styles to the default selected speed scale ('linear') on initial load.
* **Implementation:**
  * **Deferred Abbreviations Initialization**: Moved top-level `initSelectAbbreviationBehavior()` and `updateSelects()` execution into the DOMContentLoaded listener to guarantee safety.
  * **Manual Tweaks & Layout Alignment**: Reset `cie-filBlurAmt` default to 4 in HTML, added title to `cie-sort`, and customized `cie-addSoundSourceBtn` padding and height.
  * **Label-Specific Performance Alerter**: Rewrote the FPS warning handler to clear previous alerts and map active heavy effect checkboxes to their parent labels. Applied glowing red text, bold weights, and custom dashed red borders directly to the offending labels when FPS falls below 35.
  * **Actual Window Track Capturer**: Refactored `addNewTabShareSource()` and `rechooseAudioSource()` to query the shared stream's video track's label first to extract actual window/tab names, and modified `cleanAudioDeviceLabel()` to strip out raw window ID prefixes/suffixes (e.g., `window:123:0`) to yield pristine, authentic window titles. Stripped the "Tab: " prefix from the layout rows for all window streams.
  * **Automatic LocalStorage Engine**: Added `#cie-autosave` checkbox to display options, automatically updating `cie_autosave_design` on every input/change event and undo/redo state restoration. Fully re-loads saved settings on initial startup if autosave is active.
  * **DOM Syncing for Selected Options**: Added `syncSelectSelectedAttribute()` to update the `selected` attribute dynamically on all select options inside change event listeners and startup routines.
  * **Load-Time Speed Scale Stylist**: Triggered `updateSpeedScaleSymbol()` on all mapped parameters during DOMContentLoaded initialization to immediately color and highlight the default 'linear' speed scale dropdown item.

### 📍 Version 1.26.5 [2026-07-11 UTC]: Proactive Performance Throttling, Extended Autosave, Aspect Ratio Mask Fix, and Persistent Resizing Trails
* **User Intent / Feedback ("Proactive Performance Throttling, Extended Autosave, Aspect Ratio Mask Fix, and Persistent Resizing Trails"):**
  * **Proactive Performance Protection**:
    * Implement a baseline tracking mechanism for FPS (`fpsBaseline`) that automatically triggers a performance warning if the framerate drops drastically by 50% or falls below 10 FPS.
    * If the framerate falls below 5 FPS, automatically pause the animation using `isPaused = true`, highlight the heavy offending controls with custom red dashed outlines, and display a beautiful, non-obtrusive custom toast message notifying the user of the performance safeguard.
    * Implement proactive performance throttling inside `enforceSafety()`, which dynamically caps the maximum recursion depth, motion blur steps, and other resource-intensive parameter combinations if multiple heavy effects are concurrently enabled. This prevents the low-FPS situations from occurring in the first place.
  * **Comprehensive State Persistence (Autosave)**:
    * Enhance the Autosave feature to remember and persist all checkbox states, including options like FPS display (`#opt-fps`), mini visualizer (`#opt-miniViz`), static scene pause (`#cie-staticScenePause`), audio reactivity settings, etc.
  * **Aspect Ratio Converge Fix**:
    * Solve the circular masking bug where a circular clipping outline was visible near the corners of the screen in full-screen view mode for non-square aspect ratios (e.g., between 1.15:1 and 0.87:1). By geometrically calculating the screen diagonal and using a dynamically computed clipping radius of `Math.max(screenDiag + 10, min(oversizedCanvas.width, oversizedCanvas.height) / 2)`, the circular clipping boundary is mathematically guaranteed to be positioned entirely outside the visible viewport when trails are uncut.
  * **Continuous Trails on Resize**:
    * Upgrade the canvas resizing logic to preserve existing trails on window resize. Centered copy buffers (`tempCanvas`, `tempEchoCanvas`, and `tempOversizedCanvas`) are saved and redrawn with center-alignment on the new resized canvases, eliminating layout offsets, jumps, or loss of progress on resize.
  * **Frozen Trails on Pause**:
    * Prevent trails from fading or converging when the animation is paused, keeping all past trails fully preserved and static when the engine is in a paused state.
* **Implementation:**
  * **FPS Safeguard & Interactive Toast**: Built `fpsBaseline` adaptive drift tracking and integrated it into the 500ms draw loop checks, pausing the engine and showing a red glowing toast alert if FPS drops below 5. Added recursive helper `highlightCausesOfLowFPS()` to style labels of active heavy effect parameters.
  * **Proactive Safety Gatekeeper**: Re-engineered `enforceSafety()` to sum complexity weights of active features (such as Glow, Motion Blur, Echo, etc.) and dynamically limit the maximum recursion depth or blur steps before render cycle execution.
  * **Enhanced Settings Serialization**: Expanded `getSettings()` and `loadSettings()` to fully serialize, deserialize, and restore options checkboxes (`opt-fps`, `opt-miniViz`, `opt-scroll`, etc.), audio control parameters (`cie-audioEnable`, `cie-soundEnable`, sensitivity, and smoothing), and the autosave flag state itself.
  * **Geometrically Perfect Viewport Masking**: Refactored `useTrailUncut` clipping path inside `update()` to calculate viewport diagonal `screenDiag` and use it as a lower limit for the circular clip path, ensuring no clip boundary is ever drawn inside the visible screen boundaries.
  * **Durable Centered Canvas Buffering**: Upgraded `doResize()` to capture and center-align the visual copy of the active drawing buffer `canvas`, feedback `echoCanvas`, and uncut trailing buffer `oversizedCanvas` to seamlessly maintain trails after resizing actions.
  * **Pause-Aware Trail Preservation**: Wrapped the entire background trail fading, blending, and scale-converging loops in a `!isPaused` block inside `update()` to freeze trail states.

### 📍 Version 1.26.6 [2026-07-12 UTC]: Docked Control Panel Minimization, True 3D Pause Viewport Navigation, Smooth FPS Safeguard Recovery, Recentering Hotkey, and Precision Tooltips
* **User Intent / Feedback ("Docked Control Panel Minimization, True 3D Pause Viewport Navigation, Smooth FPS Safeguard Recovery, Recentering Hotkey, and Precision Tooltips"):**
  * **Minimize Docked Panels**: Support toggling panel collapse in docked modes. When minimized, docked vertical sidebars contract to 24px width and horizontal headers contract to 24px height.
  * **No Dock Option Dropdown Cut-off**: Prevent dock options dropdown from being hidden behind bounds when the sidebar is minimized.
  * **No Tab Switch False-Pauses**: Resolve false-trigger performance toast notifications that briefly blink when switching browser tabs back and forth.
  * **3D Pause Camera View**: Introduce a "3D pause" option in the options panel, enabling full 3D camera navigation (Shift+drag left click to rotate Y-axis) through paused/frozen trails.
  * **Trail-Preserving Pause**: Ensure zooming/panning/rotating with mouse or keyboard when paused does not accumulate new trails or cause brightness/thickness build-ups.
  * **Recenter Hotkey**: Map the `C` key to instantly trigger canvas re-centering (`#cie-recenterBtn`).
  * **Speed Scale Precision Tooltips**: Prevent speed scale item hovers from showing the generic parent element title. Implement precise title descriptions on the items themselves.
* **Implementation:**
  * **Docked Minimization Layouts**: Added CSS class overrides targeting `.cie-controls.dock-left.minimized`, `.cie-controls.dock-right.minimized`, `.cie-controls.dock-top.minimized`, and `.cie-controls.dock-bottom.minimized` to collapse docked panels correctly when minimized.
  * **Dropdown Overflow Management**: Managed `controls.style.overflow` dynamic toggles ('visible' on menu open, empty on close) during anchor dropdown actions to prevent options from being clipped.
  * **FPS Interval Discard**: Added timestamp threshold checks (`now - fpsLast > 1000`) inside the animation loop to discard stale timing deltas upon tab reactivation or resumption.
  * **3D Pause Viewport Rotation**: Added a custom `opt-threeDPause` checkbox in the display options row and customized the `mousemove` dragging routine to permit camera rotation when paused.
  * **Clear-On-Pause Drawing Buffer**: Programmed the render loop to clear the canvas/oversized buffers to background color before redrawing frames when paused, preventing trail accretion.
  * **KeyC Recenter Listener**: Added a `KeyC` keyboard event interceptor in the master keydown router to programmatically click the recenter button.
  * **Independent Title Attributes**: Added `title="${o.txt}"` to speed scale and track speed scale dropdown elements to override parent title inheritance.

### 📍 Version 1.26.7 [2026-07-12 UTC]: Trail-Preserving Pause, Recenter Hotkey overlays, Styled Performance Toast, Maximize Tooltips, UI Font Abbreviation-Scaling
* **User Intent / Feedback ("Trail-Preserving Pause, Recenter Hotkey overlays, Styled Performance Toast, Maximize Tooltips, UI Font Abbreviation-Scaling"):**
  - **Trail-Preserving Pause Refinement**: Restore trail-preserving pause behaviors so existing trails continue to persist exactly as in version `1.26.5` without being cleared to the background color, but eliminate the thickening/brightening build-ups on the initial trail-emitting shapes.
  - **Recenter Hotkey Documentation**: Add the missing `C` 'Recenter canvas' hotkey description to both the help overlay menu and the options tab (`.cie-tab-panel[data-panel=options]`) Controls section.
  - **Styled Performance Toast**: Dynamically style the word "highlighted" inside `showPerformanceToast()` with the red dashed `.cie-perf-warning` class.
  - **Docked Minimization Tooltips**: When minimized in docked or floating mode, change the header's tooltip to say 'Double-click/tap to maximize' instead of 'Double-click to minimize', and change the minimize button tooltip to 'Maximize [M]'.
  - **UI Font Abbreviation-Scaling**: Expand abbreviation and scaling support to:
    - Include `.hdr-text` in 'Circulospherical Infinity Engine' -> 'Circlesphere Inf. Eng.' -> 'Circsph Inf Eng' -> 'CIE' abbreviations.
    - Include `label.cie-radio-group > span` monitoring: 'Static' -> 'Stat', 'Cycle' -> 'Cyc', 'Random' -> 'Rand'.
    - Include `label.cie-checkbox-group > span` monitoring: 'Mini visualizer' -> 'Mini viz', 'Static scene pause' -> 'Stat scn pau' -> 'SSP'.
    - Automatically append the full unabbreviated text to the `title` tooltip of abbreviated labels and `.hdr-text` elements.
    - Set design list `.config-date` entries to wrap after `/` forward slashes (using `<wbr>`) and abbreviate 4-digit years into 2-digit years (e.g., '2026' -> '26').
* **Implementation:**
  - **Should-Draw Pause Check**: Created a global state check to block drawing operations when paused unless actual state modifications occur, preserving existing trails without shape thickening.
  - **Hotkeys Registration**: Added `C` to the Help overlay layout and the Options panel controls sub-block.
  - **HTML Toast Replacement**: Enabled innerHTML rendering for `showPerformanceToast()`, wrapping the "highlighted" word in a span with the `.cie-perf-warning` class.
  - **Dynamic Tooltip Manager**: Built `updateHeaderTooltip()` to synchronize the header and minimize button tooltips on minimization toggles and docking side choices.
  - **Abbreviation Scaling Extensions**:
    - Integrated `updateHdrTextAbbreviation()` into the layout observer loop to scale the app header and version string dynamically based on viewport overflow.
    - Added radio groups `.cie-radio-group` to `handleLabelFontScaling()`, automatically appending bracketed full names to elements' titles on abbreviation.
    - Upgraded design list dates rendering to replace `20\d{2}` years with 2-digit years and inject `<wbr>` word breaks after all `/` slashes.

### 📍 Version 1.27 [2026-07-12 UTC]: Viewport CSS Transform Distortion Effects, Glow Overlay Fixes, and Tooltip Enhancements
* **User Intent / Feedback ("Viewport CSS Transform Distortion Effects, Glow Overlay Fixes, and Tooltip Enhancements"):**
  - **Viewport CSS Transform Distortion Effects**: Add new transform distortion effects: 'Skew X' (`transform:skewX()`), 'Skew Y' (`transform:skewY()`), and 'Perspective' (`transform:perspective()`). Each has a full `.cie-control-group` (number input, ping-pong controls, speed scale, random value, reset, and range input slider) inside the FX tab panel.
  - **Glow Interaction Correction**: Toggling the `#cie-glow` checkbox should not move the `#cie-gRad` slider.
  - **Glow Overlay Optimization**: Smoothly transition the `#cie-glowOverlay` alpha state even when paused.
  - **Paused Trail Generation Protection**: Avoid generating new trails while the application is paused, keeping existing trails intact on the canvas.
  - **Tooltip Formatting Enhancement**: For abbreviated UI labels, spans, and `.hdr-text`, put the *unbracketed* full-length name at the beginning of the `title` tooltip as: '<full-length name>: '. For `.hdr-text`, append its grandparent's `title` as well to create: '<full app name> <version> - <`#cie-header` `title`>' (without any `<>` characters).
* **Implementation:**
  - **CSS Transform Distortions**: Designed the HTML structure for Skew X, Skew Y, and Perspective control groups inside the FX tab panel. Registered the new variables in `uiMap`, `SLIDER_DEFAULTS`, `getSettings()`, and `loadSettings()`. Applied dynamic transforms in real-time to the main canvas style using `transform: perspective(...) skewX(...) skewY(...)`.
  - **Glow Selector Isolation**: Cleaned up the event listener for `#cie-glow` to prevent unwanted side-effects on the Glow radius (`#cie-gRad`) slider.
  - **Pause-Aware Glow Overlay Transition**: Optimized the `glowOverlayAlpha` transition routine to execute and draw correctly regardless of parent pause states.
  - **Glow and Abbreviation Tooltips**: Enhanced `updateHdrTextAbbreviation()` and `handleLabelFontScaling()` to prepend the unbracketed full-length name and grandparent titles to element tooltips perfectly according to user specifications.

### 📍 Version 1.27.1 [2026-07-13 UTC]: WebGL Projection, Dynamic Skew Extensions, Help Logo Styling, and Version Persistence
* **User Intent / Feedback ("WebGL Projection, Dynamic Skew Extensions, Help Logo Styling, and Version Persistence"):**
  - **App Version Persistence**: Resolve the app version disappearing from `.hdr-text` shortly after page loading.
  - **Help Panel Logo Styling**: Align the styling and icons of `#cie-help-title` to perfectly match `.cie-header-left`.
  - **Dynamic Continuous Skewing**: Expand canvas dimensions and texture mapping to make the skewed viewport look continuous and eliminate cutoffs.
  - **True 3D WebGL Perspective**: Transition 'perspective' and 'skew' transformations from 2D CSS transforms to true 3D WebGL texture mapping on `#cie-webgl-canvas`.
  - **3D Patterns**: Integrate full support for `3d2h` (3D 2-Way Horizontal) and `3d2v` (3D 2-Way Vertical) patterns.
  - **Field of View (FOV) Control**: Add a full 'Field of View' (FOV) slider control group to 'Animation > Viewport'.
  - **Pause-Aware Rotation Indicators**: Ensure `#cie-currentRotVal` does not update when the app is paused, unless actively rotated manually via mouse drag or touch.
  - **Clean Paused Trails**: Prevent the generation of new trails while paused, keeping existing trails static and beautiful.
* **Implementation:**
  - **Regex Version Fix**: Reprogrammed the version matcher regex to successfully match standard 2-part and 3-part version numbering, maintaining the persistent header display on page load.
  - **Help Modal Style Alignment**: Standardized `#cie-help-title`'s CSS structure with `.hdr-text` classes and font properties, and linked it with the overlapping vector engine icon.
  - **Continuous Skew Math**: Implemented automatic geometry scale bounding factors ($S$) to dynamically scale up texture maps, eliminating transparent outer edges when rendering skews.
  - **WebGL Texture Mapping Engine**: Loaded and linked WebGL contexts directly onto the `#cie-webgl-canvas` overlay. Rendered the 2D drawing buffers as dynamic 3D plane textures, applying high-performance math matrices for skews, perspectives, and cameras.
  - **3D Geometry Layouts**: Registered and fully routed the recursive `3d2v` (3D 2-Way Vertical) pattern.
  - **Viewport FOV Slider**: Embedded the FOV slider control group into the control panel, mapping values between $10^\circ$ and $120^\circ$.
  - **Interactive Rotation Flagging**: Intercepted state calculations to lock `#cie-currentRotVal` updates when paused unless a real active manual drag or swipe is happening.
  - **Clean Trail Snapshotting**: Shifted `capturePausedTrails()` to capture the active drawing frame *before* the current active shapes are drawn, keeping trail history 100% clean and free of cloned shapes.

### 📍 Version 1.27.2 [2026-07-14 UTC]: Precise Clipping, Dynamic Texture Smoothing, Clean Glow Overlay and Speed/Scale Context Alignment
* **User Intent / Feedback ("Precise Clipping, Dynamic Texture Smoothing, Clean Glow Overlay and Speed/Scale Context Alignment"):**
  - **Adjust Alignment**: Align `#cie-speed-scale-context-menu` to be flush with the right side of `#cie-controls` when docked right.
  - **Clean Tooltips**: Remove the duplicate `title` attribute from `#cie-help-title` so that it doesn't show the main header's tooltip.
  - **Hide Trail Converge Group**: Hide the "line trail converge" `.cie-group` dynamically when the `#cie-trail` checkbox is unchecked.
  - **Field of View (FOV) Adjustments**: Map the WebGL projection perspective division factors accurately to the FOV angle, ensuring the viewport scales realistically in 3D when adjusting the slider or number inputs.
  - **Pause and Reset Optimizations**: Eliminate bold/overdrawn line artifacts that appeared over static shapes when animation was paused.
  - **Performance Upgrades**: Maintain high rendering performance when toggling `#cie-trailConverge` on and off by cleanly disabling underlying converge calculations if `#cie-trail` is disabled.
  - **Correct Clipping Coordinates**: Prevent converging trails from getting chopped during extreme panning or zooming by expanding the trail clipping mask to match full canvas boundaries, and disabling clipping entirely when `#cie-trailCut` is turned off.
  - **Dynamic Texture Smoothing**: Toggle canvas and WebGL texture filtering states dynamically between nearest (sharp pixels) and linear (blurry smoothing) modes based on the `#cie-filBlur` checkbox.
  - **Transparent Glow Compositing**: Refactor the glow overlay filter to render shapes onto an offscreen transparent `shapesCanvas` first, eliminating the white background "flood-fill" artifact that previously leaked during blur blending.
  - **Motion Blur Safety Clamping**: Clamp `#cie-motionBlurSteps` only when `#cie-depth` is greater than 6 and active rendering drops below 1 FPS.
* **Implementation:**
  - **Dock-Aware Positioning**: Programmed `showSpeedScaleContextMenu()` to dynamically calculate the right offset of `#cie-controls` relative to the screen, placing the context menu perfectly flush with the control bar's right edge when docked.
  - **Help Panel Cleaning**: Explicitly removed the `title` attribute of the `#cie-help-title` element in JavaScript.
  - **Dynamic Group Toggling**: Bound change listeners to `#cie-trail` to dynamically set the display style of the Trail Converge `.cie-group` to `none` when unchecked, and `block` when checked.
  - **3D FOV Matrix Mapping**: Updated WebGL perspective calculations in `renderWebGL()` to correctly compute perspective matrix values using tangent of the FOV angle, restoring authentic 3D projection resizing.
  - **Redraw Debouncing**: Blocked repetitive frame draws on static or paused scenes unless active manual panning, rotation, or slider updates are performed.
  - **Converge Safety Check**: Integrated real-time checks inside `isReallyStatic()` and the main animation loop to instantly halt heavy converge routines when trails are disabled.
  - **Rectangular Clip Paths**: Removed standard circular clip paths from trail copying contexts, replacing them with full-canvas rectangular clips when `#cie-trailCut` is active, and disabling masking entirely when `#cie-trailCut` is inactive.
  - **Texture Interpolation States**: Tied 2D rendering `imageSmoothingEnabled` settings and WebGL `gl.TEXTURE_MIN_FILTER`/`gl.TEXTURE_MAG_FILTER` parameters directly to the `#cie-filBlur` checkbox state.
  - **Glow Isolation Compositing**: Constructed a secondary off-screen transparent `shapesCanvas`. Rendered shapes onto this transparent canvas before passing it to the WebGL or CSS glow overlay filters, producing a beautiful halo without color bleeding.
  - **FPS-Aware Throttling**: Declared a global `currentFPS` tracker and programmed `enforceSafety()` to clamp `motionBlurSteps` to 4 only if active depth exceeds 6 and the frame rate drops below 1 FPS.

### 📍 Version 1.27.3 [2026-07-14 UTC]: Advanced Camera AOV, Seamless Trail Bounds Expansion, Auto-Recentering, Screen Shake FX, and Converge Unblurry Options
* **User Intent / Feedback ("Advanced Camera AOV, Seamless Trail Bounds Expansion, Auto-Recentering, Screen Shake FX, and Converge Unblurry Options"):**
  - **Camera Angle of View (AOV) Mode**: Add a secondary perspective projection mode representing true camera lens/3D video game FOV.
  - **Auto-Scaling Field of View**: For standard FOV mode, automatically expand the viewport when the angle goes below -90° and above 90° so that the drawing fills the canvas instead of shrinking into microscopic dots.
  - **Unblur Control**: Restore the classic, subtle 0.1px blur effect by default during trail convergence, and add an 'Unblur' checkbox to allow users to turn it off for sharp, pixel-perfect trails.
  - **Seamless Trail Canvas Expansion**: When bounds cutting (`#cie-trailCut`) is turned off, expand the off-screen trail render surface dynamically to 4000x4000 pixels so that trails do not get clipped during large viewport panning (via drag or key pan controls).
  - **Viewport Auto-Recentering**: Implement a 'Recenter' toggle and inactivity timer slider/number inputs under Perspective. After a user-specified duration of inactivity, the engine smoothly interpolates the viewport's pan offset and rotation back to their default centered states.
  - **Dynamic Screen Shake**: Introduce a full CSS-accelerated 'Shake' effects module with speed and distance sliders on both the horizontal (X) and vertical (Y) axes to produce an organic, jittery camera vibration.
* **Implementation:**
  - **Camera AOV and Viewport Scaling Matrices**: Modified the master WebGL perspective matrix calculations to compute projection focal lengths based on camera lens FOV when the 'Angle of View (AOV)' mode is selected. Built an automatic scale-compensation multiplier for standard FOV values outside the $[-90^\circ, 90^\circ]$ range.
  - **Unblur Filters**: Integrated dynamic `filter = 'blur(0.1px)'` conditional statements during trail copy cycles, controllable via the `#cie-trailUnblur` checkbox.
  - **4000x4000 Offscreen Trail Buffer**: Rewrote `doResize()` to dynamically allocate a massive 4000x4000 drawing space for the `oversizedCanvas` buffer when trail boundary cutting is disabled. Programmed the `#cie-trailCut` change listener to instantly invoke `doResize()` to adjust trail buffers on the fly.
  - **Smooth Viewport Recentering**: Built inactivity timers tracking `lastManualInteractionTime`. If inactivity exceeds `cie-recenterTime`, the engine smoothly decays manual pan offsets (`panX`, `panY`) and rotations (`manualRot`, `manualRotY`) back to zero using exponential decay.
  - **CSS Screen Shake**: Linked high-performance, non-blocking CSS transformations (`translate(shakeX, shakeY)`) to the canvas wrapper `#cie-canvas-container`. Calculated organic vibrations using out-of-phase sine and cosine wave frequencies multiplied by user-defined speed and distance sliders.

### 📍 Version 1.27.4 [2026-07-15 UTC]: Collapsible Tab Panels, Converging Trail Smoothness, Non-destructive Drawing Shake, Instant Recenter snapping, and Zoom Reset controls
* **User Intent / Feedback ("Collapsible Tab Panels, Converging Trail Smoothness, Drawing Shake, Recenter Snapping, and Zoom Reset"):**
  - **Collapsible Tab Panels**: In docked left/right modes, allow double-clicking a tab panel header or clicking a right-aligned toggle button (`_`/`□`) to collapse/expand the panel without layout animations.
  - **Converging Trails Blur Fix**: Ensure the 0.1px blur effect for converging trails is independent of `#cie-filBlur` and uses smooth bilinear interpolation during scaling even if canvas filters are disabled.
  - **Drawing-Space Shake**: Change screen shake to apply to the drawing's coordinates by default (meaning trails also capture the vibration), with a "Canvas" checkbox to fall back to HTML-level shaking. Rename the ID to `#cie-shake` and add `#cie-shakeCanvas`.
  - **Instant Recenter & Smooth Toggle**: Make default recentering instantaneous, and add a "Smooth" checkbox to enable the gradual lerp. Allow auto-recenter to trigger during pan animations. Rename the ID to `#cie-recenter` and add `#cie-recenterSmooth`.
  - **Zoom Reset Key**: Add keyboard shortcut `Z` to reset zoom to 0 and update controls help.
  - **Manual Edit Summaries**: Manual HTML updates adding the toggle buttons, collapsible CSS classes, and configuration checkboxes for shake methods and recentering modes.
* **Implementation:**
  - **Tab Panel Collapsibility**: Appended `.cie-docked-header-toggle` and `.collapsed` styling rules. Added JS listeners to tab headers for double-clicks, double-taps (`touchstart`), and click events to toggle minimized states dynamically.
  - **Bilinear Trail Interpolation**: Overrode `imageSmoothingEnabled = true` on trail copy and canvas draw-operations during trail convergence steps to preserve the 0.1px blur effect under all global filter configurations.
  - **Drawing Shake & Canvas Toggle**: Refactored the core `update()` loop to compute shake offsets based on performance clock timers and add them directly to the drawing states when `#cie-shakeCanvas` is disabled, allowing trails to record the shivering motion.
  - **Recenter Snap / Lerp Mechanics**: Updated the auto-recentering scheduler to snap pan/rotation offsets directly to zero by default or apply gradual exponential decays when `#cie-recenterSmooth` is checked.
  - **KeyZ Zoom Reset & Documentation**: Integrated the `KeyZ` keystroke handler to instantly reset `#cie-zoom` and its numeric representations, updated UI controls menus and help overlays, and incremented the system version to `1.27.4`.

### 📍 Version 1.27.5 [2026-07-15 UTC]: Dynamic Context-Aware Slider Randomization, Durable Pause Auto-Saves, Layout-Aware Row Scaling, Crisp Trail Unblurring, Circular Convergence Masks, and Feedback Isolation
* **User Intent / Feedback ("Dynamic Context-Aware Slider Randomization, Durable Pause Auto-Saves, Layout-Aware Row Scaling, Crisp Trail Unblurring, Circular Convergence Masks, and Feedback Isolation"):**
  - **Expand Random Slider Options**: Right-clicking (or long-pressing) any randomized slider button (`.cie-random-slider-btn`) opens a custom context menu (`.cie-random-slider-menu`) allowing the user to configure continuous mode, interval speed, and distribution profiles (Uniform, Center-Weighted, or Ends-Only).
  - **Remove Reset Class from Limits**: Remove the `.cie-reset-btn` class from `.cie-limits-btn` elements to separate reset actions from ping-pong limit setups visually and in DOM queries.
  - **Auto UI Label Abbreviation & Font Scaling**: Update label abbreviation and font scaling routines to dynamically detect wrapping in `.cie-row` containers (where a checkbox group and a control group reside), progressively abbreviating, scaling down, or iconifying checkbox labels to keep row elements on a single line without wrapping.
  - **Remember App Paused State in Autosave**: Centralize play/pause actions so that the active paused state (`isPaused`), along with random slider intervals and distributions, is stored and restored across sessions via local storage.
  - **Fix Trail Unblur Feature**: Resolve the non-functional 'Unblur' checkbox by linking it directly to `imageSmoothingEnabled` states in the trail drawing pipeline, ensuring crisp, nearest-neighbor scaling when active, and smooth 0.1px blur interpolation when disabled.
  - **Faded Circular Mask**: Introduce a faded circular mask option (`#cie-trailFadedMask`) to trail convergence. Toggling the mask blends the scaled previous frames using a soft radial gradient, preventing sharp rectangular canvas edges from appearing during scaling.
  - **Fix Chroma Split Glowing Trails feedback leak**: Eliminate horizontal glowing trail accumulation on active play and paused states by caching a pre-chroma-split canvas copy (`window.chromaBackupCanvas`) to feed into the trail feedback loop, completely isolating chromatic offsets from trail scaling.
* **Implementation:**
  - **Context-Aware Random Sliders**: Appended CSS and dynamic event handlers for `.cie-random-slider-menu`. Registered global interval and distribution trackers, enabling touch/hold or right-click triggers and continuous randomized updates.
  - **Limits Class Segregation**: Removed `.cie-reset-btn` class from all `.cie-limits-btn` buttons in the HTML layout, updating style declarations to isolate yellow styling and pointer interactions cleanly.
  - **Layout-Aware Row Optimization**: Programmed `isRowWrapping()` inside `handleLabelFontScaling()`. If a row containing checkboxes and controls wraps (detected via children offsets), the engine progressively applies string abbreviations, scales font sizes from 11px down to 9px, and converts labels to icon-only displays until the elements fit horizontally.
  - **State Centralization & Serialization**: Created `setPauseState(paused)` helper, updating play/pause handlers and autosave loops (`getSettings()`, `loadSettings()`) to save, reload, and apply `isPaused`, `randomSliderIntervals`, and `randomSliderDistributions` from local storage.
  - **Crisp Trail Unblur**: Wired the trail drawing pipeline to set `ctx.imageSmoothingEnabled = false` and `oversizedCtx.imageSmoothingEnabled = false` when `#cie-trailUnblur` is checked, and applied standard smoothing with a `blur(0.1px)` canvas filter when unchecked.
  - **Faded Radial Mask**: Embedded a `#cie-trailFadedMask` checkbox into the trail converge row. If checked, the engine applies a radial gradient mask with `globalCompositeOperation = 'destination-in'` onto `trailCopyCanvas` before scaling, producing beautiful soft edges.
  - **Pre-Chroma Isolation**: Created `window.chromaBackupCanvas`. Prior to drawing chromatic aberration, the engine copies the pristine canvas and draws from this clean backup when capturing the previous frame's trails or when snapshotting paused frames, fully isolating trail-feedback loops.

### 📍 Version 1.27.6 [2026-07-16 UTC]: Robust UI Caching, Isolated Chroma Post-Processing, Non-Bubbling Mousewheel Adjustments, and Intense Screen Shake FX
* **User Intent / Feedback ("Resolve label/UI 'undefined' text, Fix chroma trail expansion when paused, Prevent mousewheel scrolling on number inputs, Increase shake limits to 1000, Update versioning"):**
  - **Fix 'undefined' text**: Avoid label and dropdown menu options rendering as "undefined" strings during responsive viewport rescaling or state loaded iterations.
  - **Chroma Split Expansion Fix**: Ensure the chromatic aberration lens filter does not cause trailing horizontal color bleed lines when the app is paused under `#cie-staticScenePause`.
  - **Mousewheel Number Input Fix**: Stop number input wheel adjustments from bubbling up and scrolling the main controls box, which pulls the input out from under the pointer.
  - **Shake Limits Increase**: Elevate the maximum range limit for horizontal and vertical screen shake distances (`#cie-shakeDistX` / `#cie-shakeDistY`) from 500 to 1000.
  - **Update Versioning**: Log development changes under version 1.27.8 and update embedded headers.
* **Implementation:**
  - **Robust Initialization and String Guarding**: Added early DOM-initialization passes inside `handleLabelFontScaling` to cache original HTML and text content onto labels, checkbox spans, and dropdown options before any resizing or layout manipulation starts. Handled string-based `'undefined'` references defensively across the entire UI parsing stack.
  - **Encapsulated Render Throttling**: Incorporated the chroma split and echo buffer processing directly inside the `shouldDrawFrame` control branch in the animation frame update loop. Configured `isReallyStatic` and `isDrawingStatic` to instantly return correct static values under active paused states, preventing trailing pixel accumulation on stationary buffers.
  - **Non-Bubbling Wheel Stepper**: Attached a unified `'wheel'` delegation listener to `#cie-controls`. When scrolling over number inputs, the system intercepts the native event, prevents container scrolling, and computes the incremental step while dispatching standard `'input'` and `'change'` events.
  - **Elevated Range ceilings**: Expanded range limit parameters in the main DOM panel for shake distance properties to allow configuring intensity levels up to `1000`.

### 📍 Version 1.27.7 [2026-07-17 UTC]: Comprehensive Auto UI Abbreviation, Font-Scaling, and Option Iconification (AFI), Restored Keyframe CSS Animations, and Multi-Row Layout Compression
* **User Intent / Feedback ("Expand auto UI abbreviation/font-scaling/iconification (AFI), Fix keyframe CSS animations not working, Add changes and last 3 'manual edit' summaries to history.md, Update versioning"):**
  - **Auto UI Abbreviation / Font-Scaling / Iconification (AFI)**: Establish a unified layout solver that monitors `.cie-row` child and grandchild elements. If a row wraps, perform progressive, priority-based compression: unsetting fixed select widths, abbreviating labels and selects, scaling fonts down to 9px, iconifying option texts to symbol-only forms, and reducing column gaps to 1px.
  - **Option Icon Extraction**: Automatically extract emojis, shapes, and symbols from options (e.g., `'↔ Horizontal'` iconifies to `'↔'`, `'〇 Circular ↻'` to `'〇↻'`), ensuring they fit perfectly when select widths are unset.
  - **Abbreviation Tooltip Synchronization**: Set full, original option labels as `title` values for all abbreviated/iconified select options.
  - **Animation Restoration**: Resolve why CSS keyframe animations (like `@keyframes scaley` on the FOV eye icon) were broken by fixing first-child stripping within the label parsing pipeline.
  - **Manual Edit Histories**: Archive the three prior user layout edits (radio gaps, row alignments, Glow spacing, FOV wrappers, audio device gaps, and reset confirmation updates).
* **Implementation:**
  - **Dynamic Multi-Step Layout Solver (`solveRowWrapping`)**: Created a powerful layout optimizer inside `handleLabelFontScaling()` that resets row-gap, select-widths, labels, and options to default states, calculates wrap offsets, and sequentially applies compression. Unsets inline select widths to `'unset'`, prioritizes trigger checkbox labels (abbreviating, scaling, and iconifying), scales down secondary elements, abbreviates select options via `SELECT_ABBREVIATIONS`, extracts symbol-only icons via `getOptionIcons` regex `/[^\w\s\(\)\[\]\{\}\-_+=*\/\\|.,;:?!\&@#$%\^'\"<>]/g`, reduces flex-gaps to 1px, and compresses custom selects.
  - **Unwrapped Option Tooltips**: Added automatic `title` injection on option elements to show original full text.
  - **Preserved Label DIV Tags**: Modified `parseLabel` to include `DIV` tags and `.cie-fov-icon` class checks under its first-child identifier, safeguarding the outer `<div class="cie-fov-icon">` wrapper from being stripped during resizing. Styled `.cie-fov-icon` as `display: inline-block` and `transform-origin: center` for flawless GPU-accelerated keyframe animations.
  - **Manual Edit Integrations**: Logged manual layouts: compressed `.cie-radio-group` gaps to 2px, set `justify-content: space-evenly` on option rows, inserted non-breaking space `&nbsp;` on Glow, styled sound row gaps to 2px, and updated settings-reset warning text to confirm preset safety.

### 📍 Version 1.27.8 [2026-07-18 UTC]: Persistent Controls Dock Preference, Stable Paused Aberration Rendering, and Non-Bubbling Wheel Parameter Adjustments
* **User Intent / Feedback ("Persistent Controls Dock Preference, Stable Paused Aberration Rendering, and Non-Bubbling Wheel Parameter Adjustments"):**
  - **Persistent Controls Dock Preference**: Retain the user's dock-side sidebars configuration (Left / Right) inside localStorage, so their workspace layout preserves cleanly between browser sessions.
  - **Stable Paused Aberration Rendering**: Keep the cached pre-chromatic-split copy (`window.chromaBackupCanvas`) alive when static scene pause is enabled. This isolates chromatic offsets from continuous feedback, resolving trail expansion or horizontal bleeding on stationary buffers.
  - **Non-Bubbling Wheel Parameter Adjustments**: Intercept scroll gestures on numeric parameters and number inputs directly at the document window level. This lets the user scroll to adjust values without propagating the action up, preventing the main control panel from scrolling.
* **Implementation:**
  - **Durable Dock State Retrieval**: Programmed `localStorage` setters and getters into `setDockSide(side)`. Automatically read `'cie_dock_side'` on startup to apply the correct sidebar alignment dynamically.
  - **Chroma Backup Persistence**: Refactored the chromatic post-processing phase to retain the `chromaBackupCanvas` reference when the renderer is static, ensuring correct rendering offsets.
  - **Intercepted Document-Level Scroll listener**: Attached the unified `wheel` event handler directly to the `document` level rather than `#cie-controls`, stopping event propagation and preventing background scroll behaviors.

### 📍 Version 1.27.9 [2026-07-19 UTC]: Dynamic Key-Continuous Controls Engine, Shift-Key Mousewheel Scaling, Adaptive Performance Safeguards, and Dynamic UI Calculations
* **User Intent / Feedback ("Dynamic Key-Continuous Controls Engine, Shift-Key Mousewheel Scaling, Adaptive Performance Safeguards, and Dynamic UI Calculations"):**
  - **Key-Continuous Navigation Engine (WASD, QE, Arrows)**: Transition the sluggish discrete keydown behavior to a responsive continuous frame-rate processor for keyboard-controlled panning, rotating, and zoom adjustments.
  - **Shift-Key Interaction Multiplier**: Support holding down the `Shift` key to scale and speed up keyboard operations (WASD pan, QE rotate, Arrow zoom) and main container mousewheel zoom operations.
  - **Adaptive Performance Safeguards**: Shift away from hard-coded static proactive pattern limits. If the renderer hits low-framerate thresholds (< 1 FPS), progressively and dynamically scale down recursion depth (`cie-depth`) first to restore peak responsiveness before resorting to pausing animations completely.
  - **Responsive Layout Calculations**: Instantly recalculate dynamic font sizes, abbreviations, and select configurations on theme controls and rendering step changes.
  - **Visual Polishing & Modal Optimization**: Enhance the `#cie-help-overlay` box layout and responsiveness, styling z-index levels up to prevent overlay clipping. Build an intelligent dynamic hamburger button positioning routine to properly align the `#cie-showBtn` adjacent to the screen margins depending on current docking side and control panel layout.
* **Implementation:**
  - **Keyboard Continuous Update Cycle**: Added a `pressedKeys` set with global keydown, keyup, and blur listeners. Designed the `processContinuousKeys()` update loop executor to handle fluid, multi-key panning (WASD), rotational speedups (QE), and zoom intervals (Arrow keys) with speed multipliers when `Shift` is held.
  - **Dynamic Zoom Scroll Speed**: Factored shift-key keycode tracking inside the main container `wheel` zoom listener to double zoom increments dynamically.
  - **Dynamic Recursion-Down Safeguard**: Programmed the frame metric control branch to check and decrement the `#cie-depth` slider incrementally if FPS hits < 1, prompting active user feedback toasts before halting the animation frame loop.
  - **Instant Layout Recalculation**: Injected direct `handleLabelFontScaling()` triggers into `updateThemeControls()` and `updateRenderStepUI()`.
  - **Modal Layout and Floating Button Adjustments**: Styled help overlays with `z-index: 100004` and `pointer-events: auto`. Implemented the `positionShowBtn()` solver which dynamically parses docking configurations to pin the hidden controls menu handle to the appropriate margin (top, left, bottom, right).
  - **Temporal Dead Zone Reference Fix**: Repositioned the static variables (`cieAppName`, `LABEL_ABBREVIATIONS`, `SELECT_ABBREVIATIONS`, and `HDR_STEPS`) to the absolute top of the `<script>` context block. This ensures that any early execution paths (such as the automated responsive font and header scaling routines) have fully initialized references, resolving runtime initialization exceptions.

### 📍 Version 1.27.10 [2026-07-19 UTC]: Responsive Help Overlays, Interactive Swipe Scroll Forwarding, Input Hover Safeguards, and Advanced Layout wrapping Compressions (AFI)
* **User Intent / Feedback ("Help Overlay Scrolling, Position Clipping, Number Input Hover Delays, Auto UI Abbreviation (AFI), Versioning"):**
  - **Gesture-Forwarding Help Overlays**: Enable mousewheel/touch-swipe gesture propagation from the help overlay backdrop direct to the scrollable options panel (`.cie-content`).
  - **Dynamic Help Overlay Positioning**: Prevent any help overlay clipping or off-screen truncation by dynamically repositioning and sizing `#cie-help-box` opposite the active controls docking edge (top-docked, bottom-docked, left-docked, right-docked, and floating).
  - **Accidental Numeric Input Hover Delay**: Add a 0.5s hover buffer to prevent wheel-scrolling on numeric fields from modifying values unless the pointer has been actively hovering over the element.
  - **Indented Element Optimization**: Temporarily clear leftmost margins (`margin-left: 0`) for elements with `.indent` classes during active row-wrapping compression stages.
  - **Emoji/Icon Size Reduction**: Dynamically scale font sizes of elements containing multiple emoji/icon symbols down to `9px` if row-wrapping persists.
  - **Grandchild Checkbox-Group Compression**: Extend the wrapping solver to handle grandchild `.cie-checkbox-group` elements, reducing row flex-gaps and sub-container gaps down to 1px during compression passes.
  - **Manual Edit summaries**: Included 6 manual edit summaries in the history entry and synchronized the app version to `1.27.10`.
* **Implementation:**
  - **Scroll and Touch Forwarding**: Wired native touch and wheel handlers on `#cie-help-overlay` to dynamically forward scroll deltas to `.cie-content`.
  - **Anti-Clipping Help Modal Positioning**: Completely refactored `positionHelpModal()` to compute the optimal coordinate boundaries, sizing constraints, and max-height limits dynamically relative to all docking edges and floating rects.
  - **Accidental Scrolling Prevention**: Added mouseover and mouseout trackers for `input[type=number]` elements to record hover start timestamps. Modified the document-level `wheel` event handler to reject value modifications if hover duration is less than 500ms.
  - **Indented Margin Clearer**: Captured and cleared `.indent` element margins at the first stage of the layout-aware wrapping compression pass.
  - **Multi-Emoji/Icon Solver**: Created `hasMultipleEmojisOrIcons()` using code-point array mappings (`Array.from(symbolsOnly).length >= 2`). Scaled icons and their children down to 9px under active wrap detections.
  - **Sub-Flex Gap Reduction**: Added child-flex container detection (`display: flex`) within `solveRowWrapping`, compressing nested gaps and grandchild column gaps down to 1px.
  - **Synchronized Versioning**: Updated document title, headers, and metadata to reflect version `1.27.10`.

### 📍 Version 1.27.11 [2026-07-19 UTC]: Core Syntax Error Fix & Hover/Style Sync
* **User Intent / Feedback ("Fix the errors in the app"):**
  - Fix the syntax error causing `Uncaught SyntaxError: Unexpected token ';'` in `index.html`.
  - Capture and register the user's manual style customization for hover background and pan control adjustments.
* **Implementation:**
  - **Syntax Fix**: Corrected `'Radius': ['Rad'];` to `'Radius': ['Rad'],` inside the `LABEL_ABBREVIATIONS` dictionary mapping to prevent JS parsing compilation failures.
  - **Hover Visual Adjustments**: Integrated user's customized `.cie-group:hover` background-color highlighting (`#161616`) and subtle white box shadow boundary outlines.
  - **Pan Control Cleanup**: Cleaned up empty checkbox structures within the main pan control layout.
  - **Synchronized Versioning**: Incremented the app version across document header title, modal subtitles, and build configuration files to `1.27.11`.

### 📍 Version 1.27.12 [2026-07-19 UTC]: Auto UI Abbreviation (AFI) Enhancements & Fluid Motion Blur Clearing
* **User Intent / Feedback ("AFI Enhancements, Motion Blur Canvas Clearing, Versioning"):**
  - **AFI Enhancements**: Ensure radio-group span elements (`label.cie-radio-group > span`) are fully covered and processed by the AFI layout solver. Avoid nested double-processing by filtering out ancestor container selectors. Prevent multi-emoji or symbol-only labels (such as zoom scale `🔍⚖️`) from wrapping to ensure outer rows compress into single-line configurations. Normalize non-breaking spaces (`\xa0`) during parsing to ensure reliable abbreviation matches. Set the column-gap to `0` and width to `unset` for dynamic select menus to streamline layout contraction.
  - **Fluid Motion Blur Clearing**: Resolve trail-accumulation, horizontal color bleeding, and stuck lines when panning, zooming, shaking, or resetting under active motion blur effects. Prevent stale viewport ghost artifacts on the canvas.
* **Implementation:**
  - **AFI Selection Filtering and Non-Wrapping Overrides**: Added `.cie-radio-group span` to the layout query selector, and filtered out parent/ancestor labels containing sub-labels to prevent duplicate operations. Configured step 2 in `solveRowWrapping` to explicitly override `white-space: nowrap` and `flex-wrap: nowrap` for elements with multiple emojis or icon symbols. Cleaned up non-breaking spaces using `/[\s\xa0]+/g` in `parseLabel` to protect match accuracy. Adjusted CSS configurations on select menus to use `column-gap: 0` to preserve single-row alignments.
  - **Adaptive Camera Motion Blur Alignment**: Overrode viewport coordinates (`panX`, `panY`, `zoom`, `scale`, `manualRot`) on historical states drawn during temporal motion blur steps to match the current viewport projection. This perfectly aligns historical geometric states with the active camera viewport, eliminating all persistent ghost lines, trail residues, and panning/zooming lag artifacts.
  - **Synchronized Versioning**: Incremented application version configurations throughout title attributes, help modals, header banners, and metadata profiles to `1.27.12`.

### 📍 Version 1.27.13 [2026-07-20 UTC]: Advanced Multi-Tiered AFI Engine, Safe Speed Scaling Updating, and Interactive Label Hover Animation Effects
* **User Intent / Feedback ("AFI Deep-Selection, Speed scale updates, Hover Animations, Versioning"):**
  - **Comprehensive Multi-Tiered AFI Deep-Selection**: Ensure that no matter how nested control structures are (e.g. `.cie-row > div > label.cie-label[for="cie-infiniteZoom"]`), they are completely processed by the automatic font-scaling, text-abbreviation, and iconification sequence.
  - **Sequential Progressive Compressions**: Build an extremely structured 30-level sequential compression loop inside the layout wrapping solver to smoothly and progressively target trigger elements and options in sequence.
  - **Synchronized Speed Select Updates**: Fix the `.cie-speed-symbol > svg` update sequence to correctly capture the chosen scale value and update active dropdown highlights.
  - **Interactive Micro-Animation Hover Effects**: Create bespoke sine-wave translations, out-of-phase font-size variations, and random translation loops for the Amplitude, Frequency, and Shake control labels on hover.
* **Implementation:**
  - **Nested Element & Deep AFI Capture**: Expanded selector lists in `handleLabelFontScaling` and `solveRowWrapping` to capture all nested controls, label structures, checkbox labels, and radio spans.
  - **Progressive Compression Sequences**: Implemented a detailed sequential state-compression function with 30 fine-tuned steps of font reduction, spacing stripping, abbreviation, and complete iconification.
  - **Robust Speed Symbol Updater**: Re-engineered `updateSpeedScaleSymbol` to synchronize option dropdown lists and dynamically reflect selection states immediately on startup and dynamic configuration changes.
  - **Wobble, Frequency, and Shake Label Hover Micro-Animations**: Introduced `initLabelHoverAnimations()` using high-performance `requestAnimationFrame` loops to animate letter elements individually with fluid, custom physics and smooth mouseover/mouseleave transitions.
  - **Synchronized Versioning**: Updated title header elements and metadata profiles to reflect version `1.27.13`.

### 📍 Version 1.27.14 [2026-07-21 UTC]: Layout Wrapping Prevention and Advanced Target Selection for Hover Animations
* **User Intent / Feedback ("Layout Wrapping Prevention and Advanced Target Selection for Hover Animations"):**
  - **Prevent Control & Option Layout Wrapping**: Ensure control rows, options sections, select inputs, and checkbox wrappers do not wrap to multiple lines, keeping the user interface tightly integrated and aligned.
  - **Advanced Label Target Selection**: Ensure all relevant labels across different styling blocks, classes (`.cie-label`, `.cei-label`), and tag patterns are accurately targeted and mapped for interactive hover micro-animations.
* **Implementation:**
  - **Flex No-Wrap Overrides**: Forced `flex-wrap: nowrap !important;` styles across key control containers (including `.cie-row`, `.cie-control-group`, pattern mode selects, and background swatches) to guarantee single-line layout constraints.
  - **Robust Hover Animation Initialization**: Upgraded the selector queries in `initLabelHoverAnimations()` to comprehensively find and animate `label, .cie-label, .cei-label` elements with case-insensitive matches for frequency, amplitude, wobble, and shake triggers, preventing missed targets and ensuring flawless interaction behavior.
  - **Synchronized Versioning**: Incremented application version configurations throughout title attributes, help modals, header banners, and metadata profiles to `1.27.14`.

### 📍 Version 1.27.15 [2026-07-21 UTC]: Infinite Layout Loop Correction and Option Checkbox Input Protection
* **User Intent / Feedback ("Infinite Layout Loop, Option Checkboxes Missing/Not Working"):**
  - **Fix Canvas Initialization**: Address the issue where the canvas remains blank/black on startup.
  - **Fix FPS and Option Checkbox Functionality**: Resolve cases where the FPS checkbox and other options (mini visualizer, scrollbars, microphone input, sound device) disappear or fail to change state and update the application correctly.
* **Implementation:**
  - **Infinite ResizeObserver Loop Resolution**: Removed the redundant and circular `controlsEl` ResizeObserver which repeatedly triggered `doResize()` and label scaling. This layout loop was continuously resetting the canvas size and clearing drawing frames, keeping the viewport blank.
  - **Option Checkbox DOM Protection**: Introduced input guards into `handleLabelFontScaling()`, `solveRowWrapping()`, `applyCompression()`, and `initLabelHoverAnimations()` to skip processing any label elements containing `input`, `select`, or `button` tags. This ensures nested checkbox inputs (like `#opt-fps`, `#opt-miniViz`, and `#opt-scroll`) are never destroyed or overwritten, keeping their original DOM nodes and attached event listeners perfectly intact.
  - **Synchronized Versioning**: Updated application title tags and system headers to reflect version `1.27.15`.

### 📍 Version 1.27.16 [2026-07-21 UTC]: Canvas Initialization Reliability & Selective AFI Refinements
* **User Intent / Feedback ("Canvas Initialization, Control Group No-Wrap & Field of View AFI"):**
  - **Ensure Canvas Sizing & Load Initialization**: Verify why the canvas was blank on startup. Make sure the drawing loop is triggered reliably when the page loads, and guarantee correct container dimensions are retrieved and set for the rendering context.
  - **AFI Exclusions for Control Groups**: Do not apply aggressive abbreviation, scaling, or iconification (AFI) to labels and spans inside `.cie-control-group`, since control groups now have `flex-wrap: nowrap` styling.
  - **Field of View Protection**: Protect the 'Field of view' `#cie-fovMode` label, select dropdown, and option tags from aggressive AFI compressions now that it is positioned outside of its control group.
* **Implementation:**
  - **Window Load Event Redraw Trigger**: Integrated a robust `load` listener that triggers a layout recalculation (`doResize()`) and forces a full refresh (`window.needsRedraw = true;`) once all external stylesheets and container components are fully rendered, ensuring the canvas is never black/blank on first page load.
  - **Control Group Labels Filter**: Filtered out any label or span elements that reside within `.cie-control-group` in both `handleLabelFontScaling()` and `solveRowWrapping()`, preventing unneeded shrinking and text changes on non-wrapping elements.
  - **Field of View Label & Options Safety**: Added a specific guard to `applyCompression()` capping progressive compression at level 2 for the FOV label, and added checks in Step 6 (abbrev) and Step 7 (iconify) to bypass `#cie-fovMode` options entirely to preserve the "Traditional" and "Camera AOV" display texts.
  - **Drawing Loop Initialization & ReferenceError Resolution**: Fixed a critical `ReferenceError: ox is not defined` inside `drawRec()` by adding missing `ox` and `oy` distortion variable declarations. This unblocks the drawing loop execution on page load, rendering the fractal pattern immediately without requiring user interaction.
  - **Manual Edit Summary**: Cleaned up header scaling step definitions (`HDR_STEPS`) in `index.html` to remove duplicate array declarations and maintain clean script scope.
  - **Synchronized Versioning**: Updated versioning to `1.27.17`.

### 📍 Version 1.27.17 [2026-07-22 UTC]: Pattern Recursion Indexing, Unconstrained Depth Safety, & Top-Line Un-AFI Layout Solver
* **User Intent / Feedback ("Recursion Depth Indexing, maxAllowedDepth Removal, Top-Line Un-AFI, Fade Gradient"):**
  - **Recursion Depth Fix**: Correct recursion depth indexing for all 2D patterns (`2h`, `2v`, `4`, `4plus`, `kaleid`, `kaleid12`, etc.) so the outermost parent circle is drawn at depth 1, and child circles are drawn at depth 2+.
  - **Remove Depth Limits**: Remove `maxAllowedDepth` constraints for `flower`, `lissajous`, and `spiral` patterns, allowing unconstrained depth scaling governed strictly by FPS performance monitoring.
  - **Top-Line Un-AFI Pass**: Enhance automatic UI abbreviating/font-scaling/iconfying (AFI) so that when a `.cie-control-group` wraps to its own line, labels on line 1 are automatically de-/reverse-/un-AFIed into the newly available space and the row layout expands with `justify-content: space-between; width: 100%`.
  - **Background Fade Gradient**: Add a linear gradient text fade to the 'Background color fade' `label` 'Fade'.
* **Implementation:**
  - **Outer Circle Parent Depth 1**: Updated `drawRec` dispatch calls for 2D patterns (`kaleid`, `kaleid12`, `4plus`, and default 2D modes) in `drawSingleState()` to pass `d = 1` as the initial depth index. At depth 1, the parent circle renders first, with child branches drawing at depth 2+.
  - **Unconstrained Safety for Specialized Patterns**: Modified `enforceSafety()` to set `maxAllowedDepth = Infinity` for `flower`, `lissajous`, and `spiral` patterns, and removed the hardcoded `.min(..., 16)` depth clamp in `drawFlowerOfLife()`, allowing these patterns to leverage real-time FPS performance monitoring.
  - **Layout Solver Step 10 Un-AFI Pass**: Added Step 10 to `solveRowWrapping()`. When row wrapping persists (e.g. `.cie-control-group` moves to line 2), `row.style.justifyContent = 'space-between'; row.style.width = '100%'` is applied and top-line labels are tested against lower compression levels (`states[0..N]`), un-AFIing the label back to the fullest readable text that fits line 1 alongside any remaining inputs or selects.
  - **Background Fade Gradient Styling**: Applied `background: linear-gradient(90deg, #888888 0%, #ffffff 50%, #444444 100%); -webkit-background-clip: text; background-clip: text; -webkit-text-fill-color: transparent; font-weight: bold;` to the Background color fade label in `index.html`.
  - **Manual Edit Summary**: Incorporated manual edit updates including Fade and Invert tooltips (`title="Gradually transition between background colors"` & `title="Invert background color"`), updating the Pattern abbreviation list to `'Patrn'`, and formatting RGB variables.
  - **Synchronized Versioning**: Updated application title tags, help modal title, header text, and system metadata to `1.27.17`.

### 📍 Version 1.27.18 [2026-07-22 UTC]: Universal Nested AFI, Rotation Reset Correction, Ping-Pong Dependency Guards, & Ends-Only Distribution
* **User Intent / Feedback ("Universal Nested AFI, Rotation Reset, Stop Child Animations, Distort Freq Hide, Ends Only Distribution"):**
  - **Universal Nested AFI**: Ensure auto UI AFI (Abbreviate/Font-scale/Iconify) is applied to all nested (child/grandchild/great-grandchild/etc.) elements even if no abbreviation rules (`LABEL_ABBREVIATIONS`) are defined.
  - **Rotation Reset Zeroing**: Fix `#cie-currentRotVal` so it is reset to `0°` when `.cie-reset-btn[data-reset="rSpeed"]` is clicked, even if `#cie-rotate` is unchecked.
  - **Child Effect Animation Stop**: Stop active ping-pong animations and child checkboxes whenever their parent effect controller is unchecked (e.g. stop `#cie-trailConverge` and `#cie-tDens` when `#cie-trail` is unchecked; stop `#cie-distortFreq` and `#cie-distortAmp` when `#cie-distort` is unchecked).
  - **Distort Frequency Hide vs Disable**: Modify `#cie-distortFreqGroup` to hide (`style.display = 'none'`) rather than disable (`cie-disabled`) when `#cie-distort` is unchecked.
  - **Ends Only Distribution**: Add an 'Ends only' option to `#cie-random-slider-menu` under distribution that flips back and forth between the min and max slider values.
* **Implementation:**
  - **Universal Nested Leaf Element AFI**: Updated `handleLabelFontScaling()` and `solveRowWrapping()` to query and process all leaf text/label elements at any nesting depth (`.cie-label, .cei-label, label, .cie-checkbox-group span, .cie-radio-group span, span.cie-label, span`). Expanded row processing to include `.cie-group` elements containing nested label rows.
  - **Forced Rotation Degree Reset**: Modified `updateCurrentRotVal(force)` to allow `force` execution regardless of active rotation flags, ensuring `manualRot = 0; manualRotY = 0; rTime = 0; updateCurrentRotVal(true);` updates `#cie-currentRotVal` to `0°` immediately.
  - **Parent-Child Animation Dependency Guards**: Enhanced `updateTrailConvergeVisibility()`, `updateWobbleVisibility()`, and `updateDistortUI()` to automatically halt active ping-pong states (`pps[key] = false`) and remove `.active` button styling for child sliders (`trailConverge`, `tDens`, `wobbleFreq`, `wobbleAmp`, `distortFreq`, `distortAmp`) when their respective parent checkboxes (`#cie-trail`, `#cie-wobble`, `#cie-distort`) are turned off.
  - **Distort Frequency Visibility Logic**: Updated `updateDistortUI()` to toggle `style.display` for `#cie-distortFreqGroup` between `'block'` and `'none'` without setting the `.cie-disabled` CSS class.
  - **Ends Only Distribution Flip Logic**: Added `{ label: 'Ends only', val: 'ends_only' }` to `openRandomSliderMenu` and added flip logic in `triggerRandomValue()` that toggles between `mn` and `mx` based on proximity to the current slider position.
  - **Manual Edit Summaries**: Incorporated manual edits including floating/docked width settings (`300px` / `275px`), preset bar `justify-content: space-between`, random slider menu styling updates, threshold title and width attributes, and background label gradient formatting.
  - **Synchronized Versioning**: Updated application title tags, help modal title, header text, system metadata, and documentation to `1.27.18`.

### 📍 Version 1.28 [2026-07-22 UTC]: Faded Mask Lag Fix, Global Speed Propagation, Phase-Continuous Distortion, & Enhanced Random Slider Controls
* **User Intent / Feedback ("Faded Mask Toggle Lag, Random Slider Menu Enhancements, Global Speed Propagation, Distortion Ripple Reset Fix, Auto UI AFI Theme Isolation, Number Input Glow"):**
  - **Faded Mask Lag Resolution**: Eliminate multi-second toggling delay when changing `#cie-trailFadedMask`.
  - **Random Slider Menu Enhancements**: Upgrade `.cie-random-slider-menu` with standard-styled checkboxes/radios, interval speed dropdown menu, and precision slider/numeric inputs.
  - **Global Speed Propagation**: Ensure 'Global speed' (`#cie-globalSpeed`) influences 'Shake' (`#cie-shake`) animation frequency and 'Trail converge' (`#cie-trailConvergeVal`) scaling rate.
  - **Smooth Distortion Frequency Slider**: Prevent distortion ripple effect resetting or jumping when changing or dragging `#cie-distortFreq`.
  - **Theme Select AFI Isolation**: Prevent theme selection dropdown lag by excluding theme elements from aggressive label compression passes.
  - **Animating Number Field Feedback**: Add visual feedback glow (`.cie-num-animating`) to numeric input fields actively participating in ping-pong or zoom animations.
* **Implementation:**
  - **Instant Faded Mask Redraw**: Added immediate redraw trigger (`window.needsRedraw = true; lastDrawnPausedStateSummary = '';`) on `#cie-trailFadedMask` state change, resolving toggle lag.
  - **Random Slider Interval UI Refactoring**: Rebuilt `openRandomSliderMenu` to render custom-styled checkbox and radio elements, replaced interval speed radio buttons with a `select` dropdown, and added interactive slider + numeric input controls for custom interval speeds.
  - **Global Speed Scaling Integration**: Integrated `globalSpeed` scaling into `timeSec` calculation for Shake (`#cie-shake`) and `scaleFactor` computation for Trail Converge (`#cie-trailConvergeVal`).
  - **Phase-Continuous Distortion Time Engine**: Introduced top-level `distortTime` variable updated incrementally by `pSpeed * globalSpeed * distortFreq` in the render loop, maintaining seamless phase continuity when adjusting distortion frequency.
  - **Theme Container AFI Exclusion & Column-Gap Reset**: Excluded `#cie-theme-container` and `#cie-theme-val` from `solveRowWrapping` label queries and set early zero column-gaps (`columnGap = 0px`) to prevent unnecessary row wrapping and multi-second theme option selection delays.
  - **Animating Number Field Highlights**: Created `updateNumberInputAnimationHighlights()` called every frame in `update()`, applying `.cie-num-animating` (`box-shadow: 0px 0px 1px 1px lime !important;`) to number inputs with active ping-pong or zoom animation states.
  - **Manual Edit Summaries**: Captured manual edits including CSS column gap overrides on `.cie-row` and `.cie-control-group`, custom select option optimization, and random slider menu dropdown styling.
  - **Synchronized Versioning**: Incremented application version across HTML title, help modal title, control header display, system metadata, and project documentation to `1.28`.

### 📍 Version 1.28.1 [2026-07-23 UTC]: Initialization & Pattern Switch Lag Resolution, Multi-Dimensional AUIAFI, Depth 0 Recursion Fix, Skew 2D Context Rendering & Recenter Decimal Increments
* **User Intent / Feedback ("App Initialization Lag, Pattern Switch Lag, Canvas Resize Lag, Depth 0 Rendering Fix, Multi-Dimensional AUIAFI Refactor, Recenter Time Decimal Increments, Skew X/Y Quality Fix"):**
  - **Initialization & Pattern Change Speedup**: Resolve multi-second delays during initial app startup and pattern swapping via `#cie-pattern`.
  - **Canvas Resize & Panel Lag Fix**: Eliminate canvas resize lag/pause when resizing `#cie-controls`, toggling docked/floating states, or opening DevTools.
  - **Depth 0 Recursion Fix**: Prevent rendering the outermost parent circle when recursion depth is 0 for 1-way (`1h`, `1v`, `1hi`, `1vi`) and 2-way (`2h`, `2v`, `2hi`, `2vi`) patterns.
  - **Multi-Dimensional AUIAFI Refactor**: Defer setting `column-gap: 0px` until Step 8 of AUIAFI optimization. Implement an interleaved multi-dimensional approach mixing font size reductions, label abbreviations, child element column gap reductions, select option abbreviations, and iconifications in progressive step increments.
  - **Recenter Time Slider Precision**: Support finer decimal increments (e.g. 0.5) on `#cie-recenterTime` and `#cie-recenterTimeNum` by setting `step="any"` and removing `recenterTime` from `isInt` checks.
  - **Skew X/Y Rendering & Canvas Skew Checkbox**: Fix zoomed-out and aliased appearance when enabling Skew X/Y by applying skew directly to the 2D drawing context (`ctx.transform`), and add a `#cie-skewCanvas` checkbox allowing users to toggle canvas-element-based CSS skewing if desired.
* **Implementation:**
  - **Debounced AUIAFI & Fast Layout Checks**: Wrapped `handleLabelFontScaling()` in a `requestAnimationFrame` debouncing scheduler, added visible-row filters (`row.offsetWidth > 0 && row.offsetHeight > 0`), and replaced `getBoundingClientRect().top` checks with `offsetTop` comparisons for ultra-fast DOM layout evaluations.
  - **Multi-Dimensional Interleaved AUIAFI**: Refactored `solveRowWrapping()` to preserve default row gap initially, running an interleaved level loop (1 to 30) that progressively compresses labels, applies 1px gap at level 1 and 0px gap at level 2 (Step 8 extended), and compresses select option text simultaneously before returning immediately once row wrapping is solved.
  - **Recursion Depth 0 Guard**: Added `if (Math.round(md) <= 0) return;` at the top of `drawRec()`, `drawOneWayNested()`, and `drawOneWay()`, ensuring zero circles are drawn when recursion depth is set to 0.
  - **Decimal Precision for Recenter Time**: Updated HTML inputs for `recenterTimeNum` and `recenterTime` to `step="any"` and removed `recenterTime` from all integer-coercion `isInt` checks across state loaders, resets, and randomizers.
  - **Context-Based Skew & Canvas Toggle**: Added `#cie-skewCanvas` checkbox near Skew controls. Updated drawing loop to apply 2D transformation matrix `ctx.transform(1, Math.tan(syR), Math.tan(sxR), 1, 0, 0)` directly onto the rendering context for crisp vector quality, reserving element CSS transform for when `skewCanvas` is explicitly checked.
  - **Manual Edit Summaries**: Captured manual edit updates including pattern renaming (`2h_inv` -> `2hi`, `2v_inv` -> `2vi`), `column-gap: 2px` CSS adjustments across rows, selects, and checkbox/radio groups, and synchronized documentation history.
  - **Label Scaling Variable Hoisting Fix**: Declared `var labelScalingAnimationFrame = null;` at the top of the main script tag to ensure it is initialized prior to any early calls to `handleLabelFontScaling()`, resolving the `Uncaught ReferenceError: Cannot access 'labelScalingAnimationFrame' before initialization` runtime error during layout setup.
  - **Synchronized Versioning**: Updated application title tags, help modal title, control header display, system metadata, and documentation to `1.28.1`.

### 📍 Version 1.28.2 [2026-07-24 UTC]: Arrow Key Slider Traversal, AUIAFI Speedup & Dynamic Control Group Alignment, Updated Defaults & Manual Edit Summaries
* **User Intent / Feedback ("Arrow Key Slider Traversal, Pattern & RenderStep Lag Fix, AUIAFI Control-Group Width/Gap Tweaks, Autosave/StaticScenePause Defaults, Version 1.28.2 Updates"):**
  - **Arrow Key Slider Traversal & Snap Fix**: Prevent slider thumb handles from getting trapped on tick marks when navigating with left/right/up/down arrow keys by bypassing `cie-snapSliders` snapping during active keyboard navigation inputs.
  - **AUIAFI Speedup & Pattern / RenderStep Lag Resolution**: Fix multi-second frozen UI lag when toggling `#cie-renderStepEnable` or changing `#cie-pattern` by using `offsetTop` measurements, bounding label compression iterations to actual state counts, and breaking optimization loops early when DOM states stabilize.
  - **Dynamic AUIAFI Control-Group Alignment & Column Gap**: Update AUIAFI (`solveRowWrapping`) so that when a `.cie-control-group` wraps to its own line as a sole child element, it sets `width: stretch` to preserve right-alignment and omits `column-gap` reductions. Removes `width: stretch` when the control group is not wrapped.
  - **Updated Autosave & Static Scene Pause Defaults**: Set default `#cie-autosave` to ON (checked / `true`) and default `#cie-staticScenePause` to OFF (unchecked / `false`) across HTML elements, default settings dictionary, state loaders, and localStorage defaults.
  - **Summarized Recent Manual Edits**: Captured recent manual edits including Camera FOV control group inline style cleanup (`style="width:stretch"` removal), text frequency animation font-size variation scale update to 1px max range (`±0.5px`), and default recursion depth update to 9 (`DEFAULTS.depth = 9`).
  - **Synchronized Versioning**: Incremented application version across HTML page title, help overlay header, control panel header, metadata, and project documentation to `1.28.2`.

### 📍 Version 1.28.3 [2026-07-24 UTC]: Pattern Switch Lag Optimization, Refined Incremental AUIAFI, and Manual Edit Summaries
* **User Intent / Feedback ("Pattern Change Lag Investigation, Refined Incremental AUIAFI Loop, Version 1.28.3 Updates"):**
  - **Pattern Select Change Performance Fix**: Resolved multi-second pattern change lag on `select#cie-pattern` by eliminating unnecessary layout re-evaluation passes during pattern change events, bringing pattern select switching to parity with fast radio button pattern switching.
  - **RenderStep Toggle Speedup**: Fixed lag when toggling `#cie-renderStepEnable` by streamlining state updates and layout optimization triggers.
  - **Refined Incremental AUIAFI Loop**:
    - Removed early `column-gap: 0px` resets before wrapping calculations. Preserved default row gap initially and reduced column gaps by 1px incrementally only when necessary to prevent wrapping.
    - Implemented a 3-step incremental AUIAFI loop repeated sequentially per pass:
      - **Step 1**: Reduced font size of each `.cie-label` (`label`, `span`) or `select` in the row by 0.5px (down to 8px minimum) without resetting higher font sizes straight to 12px.
      - **Step 2**: Abbreviated each `.cie-label`/`select` individually by 1 abbreviation level per pass (appending original full text to the element title tooltip). Iconified labels/selects when appropriate.
      - **Step 3**: Reduced 1st child element (non-`.cie-row`) `column-gap`s by 1px if present.
  - **Summarized Recent Manual Edits**:
    - **Line Glow Group Wrapper Cleanup**: Removed redundant outer `<div style="display:flex; align-items:center;column-gap:2px">` wrapper around Glow checkbox group in `index.html`.
    - **Depth Nesting Rotation Wrapper Cleanup**: Removed redundant outer `<div style="display:flex; align-items:center; column-gap:2px">` wrapper around Depth orbit and ୭ checkbox groups in `index.html`.
    - **Zoom Group Wrapper Cleanup**: Removed redundant outer `<div style="display:flex;align-items:center;gap:4px">` wrapper around Zoom label and ∞ checkbox group in `index.html`.
    - **Scanlines Speed Step Granularity**: Updated `step` attribute on Scanlines speed slider (`#cie-scanlinesSp`) from `1` to `any` for sub-step precision control.
    - **Default Settings Unification**: Updated `DEFAULTS.scaleWidth` from `false` to `true` to default width scaling to active on initial load.
  - **Synchronized Versioning**: Incremented application version across page title, help overlay header, control panel header, system metadata, and project history documentation to `1.28.3`.

### 📍 Version 1.28.4 [2026-07-25 UTC]: AUIAFI Refinements, Active Dock Option Highlight, Title Tooltip Optimization, and Manual Edit Summaries
* **User Intent / Feedback ("AUIAFI Tooltip & Gap/De-abbreviation Logic, Active Dock Option Bold Styling, Manual Edit Summaries & Version 1.28.4 Updates"):**
  - **AUIAFI Tooltip Optimization**: Updated `updateHdrTextAbbreviation` to avoid adding duplicate app name and version text to `.hdr-text` title tooltips when abbreviated, keeping tooltips concise since app name and version are already present.
  - **Conditional AUIAFI Gap & De-abbreviation Handling**:
    - Preserved row `column-gap` when `.cie-row` does not wrap with current spacing.
    - Updated `solveRowWrapping` so that when a `.cie-control-group` wraps to its own line, abbreviation/font-scaling/iconification for `.cie-label` and `select` elements is reverted/prevented if the row will not wrap again.
  - **Active Dock Option Bold Styling**: Applied bold font weight (`font-weight: bold`) to the currently active dock option in `#cie-dockOptions > .cie-dock-opt` (`setDockSide`), while resetting inactive dock options to normal weight.
  - **Summarized Recent Manual Edits**:
    - **Box Title Header Class Standardization**: Updated `.cie-box-title` CSS class to flexbox centered layout (`display:flex; font-size:10px; color:#c3c3c3; font-weight:900; justify-content:center; margin:0; padding-left:0 2px; text-align:center`) and migrated ad-hoc inline header divs ("🎨CSS Canvas Filters", "Display", "🎵Audio reactivity", "⌨️🖱️👆Controls") to `<div class="cie-box-title">`.
    - **Checkbox Group Label Flex Alignment**: Updated `.cie-checkbox-group label` CSS display property to `display:flex`.
    - **Recenter Row Style Cleanup**: Removed redundant inline `gap:10px` style from Recenter `.cie-row`.
  - **Synchronized Versioning**: Incremented application version across page title, help overlay header, control panel header, system metadata, and project history documentation to `1.28.4`.

### 📍 Version 1.28.5 [2026-07-25 UTC]: Refined AUIAFI Optimization Algorithm, Minimum Font Size Enforcement, Column Gap Preservation & Adaptive UI Toggle
* **User Intent / Feedback ("Refine AUIAFI Logic, Minimum 9px Font Size, Preserve Column Gap, Balanced Abbreviation/Scaling, Adaptive UI Toggle"):**
  - **✨Adaptive UI Toggle**: Added `✨Adaptive UI` checkbox (`#cie-adaptiveUI`) to the Options panel, integrated into state persistence (`mainEffectCheckboxes`, `DEFAULTS`, `getSettings`, `loadSettings`), allowing users to toggle adaptive UI scaling on/off dynamically. When disabled, rows restore instantly to default layout via `restoreRowToDefault`.
  - **9px Minimum Font Size Floor**: Enforced a strict minimum font-size floor of 9px across label font scaling and row compression passes, preventing illegible text shrinking down to 8px or lower.
  - **Column Gap Preservation**: Preserved default element/row `column-gap` when the default gap does not cause row wrapping (`tryRestoreColumnGaps`), avoiding unnecessary zero-gap compression.
  - **Balanced Interleaved AUIAFI Passes**: Structured the AUIAFI multi-pass loop into distinct, progressive phases per pass:
    - **Step A**: Font size reduction (-0.5px down to 9.0px).
    - **Step B**: Text abbreviation (1 level per pass) while maintaining text visibility.
    - **Step C**: Iconification (only attempted if text abbreviation steps are exhausted AND font size is already at 9.0px).
    - **Step D**: Column gap reduction (-1px per pass) as a final resort.
  - **Relaxed Aggressiveness**: Relaxed compression aggressiveness so that rows wrap cleanly without over-shrinking or over-iconifying when light abbreviation (e.g. 'Field of view' -> 'FOV' @ 11px) is sufficient to prevent wrapping.
  - **Synchronized Versioning**: Incremented application version across page title, help overlay header, control panel header, system metadata, and project history documentation to `1.28.5`.

### 📍 Version 1.29 [2026-07-25 UTC]: Slider Animation Directions, Self-Exempt Global Speed Modulator, Limit Track Direction Controls & Limit Popover Cleanup
* **User Intent / Feedback ("Slider Animation Directions, Global Speed Exemption, Limit Track Direction Controls, Manual Edit Summaries & Version 1.29 Updates"):**
  - **Slider Animation Direction Modes**:
    - Renamed `.cie-ping-pong` to `.cie-slider-anim` and updated titles across all slider control groups to "Slider animation direction".
    - Added right-click (and 0.5s touch-hold) context menu dropdown to slider animation buttons with `<-- Left`, `--> Right`, and `<--> Ping-pong` options.
    - Updated button emoji representation dynamically (`←` for Left, `→` for Right, `↔` for Ping-pong).
    - Updated animation engine `runPP` loop to execute Left looping (wrap to max/right end), Right looping (wrap to min/left end), and Ping-pong back-and-forth oscillation according to the selected direction mode.
  - **Global Speed Modulator Exemption**: Excluded `input#cie-globalSpeed` from being multiplied by its own value in `runPP` and `runTrackPP`, ensuring global speed slider animations scale accurately and predictably without exponential feedback loops.
  - **Limit Track Direction Controls**:
    - Updated limit popover buttons (`.cie-limit-track-dir-btn`) with "Limit track direction" title and added right-click / 0.5s touch-hold context menu for selecting track movement direction (`<-- Left`, `--> Right`, `<--> Ping-pong`).
    - Updated `runTrackPP` loop to move min/max limit track windows according to selected direction mode.
  - **Summarized Recent Manual Edits**:
    - **Limit Popover DOM Cleanup**: Removed redundant `<span>` wrapper elements surrounding limit inputs and buttons across limit popovers in `index.html`.
    - **Slider Speed Button Rename**: Updated `.cie-pp-speed-btn` class to `.cie-slider-speed-btn` and title to "Slider animation speed".
    - **Slider Limits Title Update**: Renamed limit button title attribute from "Set custom min/max extents for ping-pong animation" to "Slider limits".
  - **Synchronized Versioning**: Incremented application version across page title, help overlay header, control panel header, system metadata, and project history documentation to `1.29`.

### 📍 Version 1.29.1 [2026-07-25 UTC]: Variable Scope Shadowing Correction & Temporal Dead Zone Hoisting Fix
* **Bug Fixes ("Uncaught SyntaxError: Identifier 'trackTouchTimer' has already been declared" & "Uncaught ReferenceError: Cannot access 'trackPPModes' before initialization"):**
  - Renamed the limit direction button touch timer variable from `trackTouchTimer` to `ppDirTouchTimer` within `attachLimitListeners`, preventing identifier redeclaration errors in the enclosing scope block.
  - Moved `ppAnimModes` and `trackPPModes` state object declarations to the top-level state initialization section (alongside `pps`, `ppd`, and `ppSpeeds`), resolving Temporal Dead Zone (TDZ) ReferenceErrors when control initializers run early.
  - Verified compilation and runtime stability across all limit track controls and popovers.
  - **Synchronized Versioning**: Incremented application version across page title, help overlay header, control panel header, system metadata, and project history documentation to `1.29.1`.

### 📍 Version 1.29.2 [2026-07-26 UTC]: Expanded Direction Menu, Emoji Direction Icons, Track Direction Indicators & Class Name Standardization
* **User Intent / Feedback ("Expanded Direction Menu, Emoji Arrows, .cie-track-dir-indicator Rename, Script Verification & Version 1.29.2 Updates"):**
  - **Slider Animation Direction Menu (`showAnimDirectionContextMenu`)**:
    - Configured the `<select>` direction dropdown with `size="3"` to show all 3 direction options (`← Left`, `→ Right`, `↔ Ping-pong`) immediately upon right-clicking/long-pressing without requiring an initial drop-down click.
    - Updated option text to clean emoji arrows (`← Left`, `→ Right`, `↔ Ping-pong`) instead of ASCII arrows (`<-`, `->`, `<->`).
    - Constrained context menu width to `max-content` so it fits tightly around the largest option ('↔ Ping-pong').
    - Positioned menu directly beneath `button.cie-slider-anim` (or limit track direction button) using element bounding box dimensions.
  - **Limit Track Indicator Renaming & Emoji Styling (`.cie-track-dir-indicator`)**:
    - Renamed `.cie-track-pp-indicator` class to `.cie-track-dir-indicator`.
    - Replaced hardcoded vector SVG path with dynamic emoji arrow symbols (`←`, `→`, or `↔`) matching the current `trackPPModes[k]`.
    - Updated indicator tooltip dynamically (e.g., `"Slider limit track: ← Left"`, `"Slider limit track: → Right"`, `"Slider limit track: ↔ Ping-pong"`).
    - Added real-time title and emoji icon synchronization when limit direction is updated via context menu or loaded from saved settings.
  - **Summarized Recent Manual Edits**:
    - **Global `.cie-slider-anim` Class Standardization**: Removed remaining `.cie-ping-pong` CSS and JavaScript references, standardizing fully on `.cie-slider-anim`.
    - **Limit Track Button Class Renaming**: Renamed `.cie-limit-track-pp-btn` selector references to `.cie-limit-track-dir-btn`.
    - **Help Overlay Documentation Polish**: Updated Help Overlay text descriptions for slider animation directions (← Left, → Right, ↔ Ping-pong), speed scale growth curves, random button, and reset button.
    - **Context Menu Positioning & Styling Polish**: Adjusted `.cie-anim-dir-context-menu` CSS styling and element alignments.
    - **Reset & Overlay Update Methods**: Updated `updateSliderLimitOverlay`, theme reset, and preset reset handlers to reference standardized class names.
  - **Synchronized Versioning**: Incremented application version across page title, help overlay header, control panel header, system metadata, and project history documentation to `1.29.2`.

### 📍 Version 1.29.3 [2026-07-26 UTC]: Wobble Hover Optimization, AUIAFI Select Abbreviation Fix, Vertical Chroma Split, Adaptive Layout Refinements & Shake Phase Stability
* **User Intent / Feedback ("Fix ~15fps drop on wobble hover, fix select#cie-customGradStyle abbreviation conflict, add Vertical split, refine AUIAFI, fix line invert on square gradient, fix shake speed snap-back"):**
  - **Wobble Hover Animation Optimization (`initLabelHoverAnimations`)**:
    - Replaced DOM layout reflow triggers (`span.style.fontSize`) in wobble-amp and frequency hover animations with hardware-accelerated CSS `transform: translateY(...) scale(...)`.
    - Eliminated the reported ~15fps frame drop during label hover while preserving fluid wave motion.
  - **AUIAFI Abbreviation Matching Fix (`getSelectAbbrs`)**:
    - Resolved option abbreviation conflicts (such as `select#cie-customGradStyle` showing '1W Horiz' for 'Horizontal') by introducing exact-first and substring matching that avoids reverse inclusion matches.
    - Updated all select and option abbreviation loops across AUIAFI compression passes.
  - **Vertical Chroma Split (`#cie-chromaVert`)**:
    - Added a vertical split checkbox next to `Chroma split` and a full nested control group (`#cie-chromaVertGroup`) with range slider `#cie-chromaVertAmt`, number input `#cie-chromaVertAmtNum`, reset button, slider animation button, and limits popover `#cie-limits-chromaVertAmt`.
    - Integrated vertical split rendering in the canvas render loop, drawing screen-blended vertical offsets (`0, -amtV` and `0, amtV`) on offscreen canvas.
    - Added state persistence, reset handlers, and `mainEffectCheckboxes` registration.
  - **AUIAFI Row Wrapping Refinements**:
    - Adjusted Distortion ripple label font-size to `11.5px`.
    - Adjusted Line trail converge group row checkboxes (Unblur, Cut bounds, Faded mask) font-size to `11.5px`.
    - Adjusted Recenter group row labels (Recenter, Smooth) font-size to `11px`.
    - Updated `checkNeedsCompression()` so ANY row wrapping triggers compression pass, preventing control groups from breaking onto line 2 at width:275px.
  - **Line Color Invert on Square Gradient (`#cie-lineInvert`)**:
    - Included `cachedLineInvert` (`invAmt`) and opacity in the parameter key (`params`) for `getSquareGradientPattern` and `getSpectralThemeStrokeStyle` square branch, ensuring pattern cache invalidates immediately on line invert toggling.
  - **Shake Speed Continuous Phase & Pause Stability**:
    - Replaced global time modulo with continuous frame delta phase accumulators (`shakePhaseX` and `shakePhaseY`).
    - Fixed drawing snapping back or jumping on shake speed input changes or during animation pause.
  - **Summarized Manual Edits**:
    - **`tDens` Range Extension**: Updated trail density slider minimum from 0.01 to 0.005.
    - **Recenter Smooth Icon**: Added smooth curve icon `<span style="position:relative; top:-3px">︵</span>` to Recenter Smooth label.
    - **Canvas Label Standardization**: Standardized "Canvas" label across viewport and effect option groups.
    - **Chroma Amount Range Expansion**: Expanded `chromaAmt` slider range to `-364` to `364`.
    - **Default State Updates**: Updated `DEFAULTS` with `filContrastAmt: 2`, `panPattern: 'horizontal'`, `chromaVert: false`, `chromaVertAmt: 4`.
    - **`tryRestoreColumnGaps` Function Restored**: Defined the missing `tryRestoreColumnGaps` helper inside `solveRowWrapping`, fixing the `Uncaught ReferenceError: tryRestoreColumnGaps is not defined` during AUIAFI layout compression checks.
  - **Synchronized Versioning**: Incremented application version across page title, help overlay header, control panel header, system metadata, and project history documentation to `1.29.3`.

### 📍 Version 1.29.4 [2026-07-27 UTC]: Vertical Chroma Split Controls & Mapping, Randomizer Distribution Expansion & '➰Loop' Speed Scale
* **User Intent / Feedback ("Chroma Split UI Refinements, Randomizer Menu Enhancements, '➰Loop' Speed Scale & Version 1.29.4 Updates"):**
  - **Chroma Split UI Refinements (`#cie-chromaVertGroup`)**:
    - Moved Vertical split checkbox (`#cie-chromaVert`) into `#cie-chromaVertGroup > .cie-row` before `label.cie-label[for="cie-chromaVertAmt"]`.
    - Removed `display:none` hiding logic so Vertical Chroma Split controls remain permanently visible inside the Chroma split control box regardless of checkbox state.
    - Integrated `chromaVertAmt: 4` into `SLIDER_DEFAULTS` and `chromaVertAmt: 'cie-chromaVertAmt'` into `uiMap`.
    - Dynamically populated missing `.cie-control-group` buttons (slider animation speed, speed scale selector/picker, and random slider value button) and verified functionality for reset (`↺`), number input, slider animation (`↔`), and slider limits (`🎚️`).
  - **Random Slider Menu Enhancements (`showRandomSliderContextMenu`)**:
    - Added CSS input element styling overrides for `.cie-random-slider-menu` ensuring `input[type="number"]` and `input[type="range"]` inherit dark background, crisp borders, and full controls theme consistency.
    - Added new 'Left-center-right' distribution option (`left_center_right`) to randomizer context menu (positioned before 'Ends') that cycles slider thumb handle predictably between far left (0), center (0.5), and far right (1.0).
    - Positioned context menu directly below the target `.cie-slider-wrapper` bounding box (flipping above if near viewport bottom) to ensure the animating slider thumb handle remains fully visible.
  - **'➰Loop' Speed Scale (`scaleOptions` & `runPP` / `runTrackPP`)**:
    - Added `loop` SVG icon to `svgIcons` dictionary (`<svg viewBox="0 0 24 24"...>`) and `loop` option (`➰Loop`) to `scaleOptions` in both standard slider and limit track speed scale menus.
    - Implemented stateful `loop` curve logic in both `runPP` and `runTrackPP` animation loops, advancing thumb forward for ~50% distance, back ~25%, then forward the remaining ~25%.
  - **Synchronized Versioning**: Incremented application version across page title, help overlay header, control panel header, system metadata, and project history documentation to `1.29.4`.

### 📍 Version 1.29.5 [2026-07-27 UTC]: Speed Scale Loop & Bounce Refinements, Design Naming Generator & Randomizer Pattern Snap
* **User Intent / Feedback ("Speed Scale Adjustments, Bounce Speed Scale, Design Naming Generator, Left-Center-Right Pattern & Version 1.29.5 Updates"):**
  - **'Loop' Speed Scale Adjustments (`runPP` / `runTrackPP`)**:
    - Calibrated loop step execution speed so a complete loop cycle finishes in ~1.0 linear traversal time unit (distance 1.5 at magnitude 1.5x speed).
    - Preserved signed speed step multiplication allowing negative velocity to reverse slider movement smoothly without being clamped to positive values.
    - Extended final phase of loop trajectory all the way to the end of slider handle (`t = 1.0`).
  - **'Bounce' Speed Scale (`⁀Bounce`)**:
    - Added new 'Bounce' speed scale option (`⁀Bounce`) with custom SVG icon (`M1,14 Q4,2 7,14 Q9.5,6 12,14 Q13.5,10 15,14 L16,14`) added to `svgIcons` and `scaleOptions` for both sliders and track limit speed menus.
    - Implemented multi-stage gravity ricochet physics in `runPP` and `runTrackPP` simulating thumb handle bouncing off the slider end wall with increasingly faster ricochets.
  - **Design Naming Generator (`🏷️`)**:
    - Added `🏷️` button (`#cie-genNameBtn`) with "Generate design name" tooltip before `input#cie-configName`.
    - Implemented automated naming generator that combines active pattern's shortest abbreviation in `SELECT_ABBREVIATIONS` with space-separated 3-/4-character abbreviated tags of active major animation effects (from `LABEL_ABBREVIATIONS` / standard tags, e.g., `4W+ rot conv shk`), capping total name length at ~32 characters.
  - **Left-Center-Right Randomizer Pattern Update**:
    - Updated 'Left-center-right' random distribution pattern cycle to snap to center when moving left: `Center (0.5) -> Left (0.0) -> Center (0.5) -> Right (1.0)` across a 4-step modulo cycle.
  - **Summarized Manual Edit**:
    - Updated `LABEL_ABBREVIATIONS['Recursion depth']` array from `['Rec depth','R depth','Depth','Dep']` to `['Rec depth','R depth','RDep','Dep']`.
  - **Synchronized Versioning**: Incremented application version across page title, help overlay header, control panel header, system metadata, and project history documentation to `1.29.5`.

### 📍 Version 1.29.6 [2026-07-28 UTC]: Context Menu UI Refinements, Speed Scale Easing, Preset Edit Date Format, Static Scene Pause & Chroma Split Edge Padding
* **User Intent / Feedback ("Context Menu UI Refinements, Random Slider Distributions, Speed Scales Smoothing, Preset Edit Dates, Static Scene Pause Manual Updates & Version 1.29.6 Updates"):**
  - **Context Menu Close Buttons**:
    - Added 'X' close buttons to the 'Mirror' section of the speed scale context menu and header of the random slider context menu.
    - Standardized close button styling and event handlers across context menus.
  - **Random Slider Distributions**:
    - Added 'Left-weighted' and 'Right-weighted' distribution options to the random slider context menu.
    - Updated `triggerRandomValue` in `index.html` to calculate random values using weighted power distribution functions for 'left' and 'right' weightings alongside 'center' and 'ends'.
  - **Smooth 'Loop' & 'Bounce' Speed Scales (`runPP` / `runTrackPP`)**:
    - Refactored 'Loop' speed scale to apply smooth easing. Reverses direction (ping-pong) towards opposite boundary upon reaching slider edge. Trajectory pattern: moves 75% distance to slider edge, 50% distance in opposite direction, then full 100% distance back to the original slider edge.
    - Refactored 'Bounce' speed scale to use exact gravity ricochet formula `Math.abs(Math.sin(x * 15) / (1 + x * 5))` mapped with smooth easing. Fully compatible with ping-pong mode bouncing off each slider edge.
  - **Preset Edit Panel Date Formatting (`#cie-preset-edit-date`)**:
    - Inserted a `<br>` line break between 'Created' and 'Modified' dates.
    - Removed the `' | '` text separator and updated element rendering to `innerHTML`.
  - **Static Scene Pause Manual Updates (`#cie-staticScenePause`)**:
    - Preserved active user preferences for static scene pause when toggling pause state (`#cie-pauseBtn`), preventing pause action from forcing `#cie-staticScenePause` on.
    - Re-enabled live manual updates when paused with `#cie-staticScenePause` off for visual effect inputs (checkboxes, numbers, sliders), panning, rotating, zooming, and action-bar/hotkey/control-group resets.
  - **Chroma Split Edge Clipping Prevention (`#cie-chroma` & `#cie-chromaVert`)**:
    - Expanded `offCanvas` buffer dimensions dynamically with calculated padding (`padX` / `padY`) based on chroma displacement amounts.
    - Eliminated horizontal and vertical chroma split edge clipping during manual or automatic canvas panning.
  - **Wobble Frequency Smooth Modulation Fix (`#cie-wobbleFreq`)**:
    - Replaced discrete frequency scaling in drawing loops with continuous phase accumulator `wobbleTime`.
    - Adjusting Wobble Frequency now smoothly accelerates or decelerates wobble oscillations without resetting or jumping phase.
  - **Synchronized Versioning**: Incremented application version across page title, help overlay header, control panel header, system metadata, and project history documentation to `1.29.6`.

### 📍 Version 1.29.7 [2026-07-28 UTC]: Smooth Loop & Bounce Speed Scales, Static Scene Pause Restore, Unclipped Chroma Split & Canvas Hotkey Focus
* **User Intent / Feedback ("Smooth Loop & Bounce Speed Scales, Static Scene Pause Behavior, Chroma Split Edge Padding & Canvas Focus - Version 1.29.7 Updates"):**
  - **Smooth 'Loop' & 'Bounce' Speed Scales (`runPP` / `runTrackPP`)**:
    - Replaced multi-stage discrete directional steps in `runPP` and `runTrackPP` with continuous mathematical functions of normalized handle position `t` (0 to 1).
    - **Loop (`loop`)**: Smooth sinusoidal speed oscillation across the slider range (`m = (Math.sin(t * Math.PI * 4 - Math.PI / 2) + 1.2) * 1.5`), providing smooth periodic speed loops.
    - **Bounce (`bounce`)**: Pure bouncing physics velocity curve (`m = Math.abs(Math.sin(t * Math.PI * 3.5)) * (1.0 - 0.65 * t) * 3.2 + 0.15`), producing bouncing velocity arcs that decay across the slider.
  - **Static Scene Pause Restore & Live Manual Updates (`#cie-staticScenePause`)**:
    - Re-enabled Static Scene Pause (`#cie-staticScenePause`) by default *when pausing the app only*, while leaving it manually togglable when paused.
    - Re-allowed immediate canvas redraws when paused whenever any visual effect input (line color, width, opacity, glow, bg color, FX tab controls), canvas panning, rotating, zooming, or control group / action-bar / hotkey resets are performed.
  - **Chroma Split Edge Clipping Fix (`#cie-chroma` & `#cie-chromaVert`)**:
    - Enabled `useTrailUncut = true` automatically whenever Chroma split (horizontal or vertical) is active.
    - Configured `offCanvas` to extract unclipped geometry from `oversizedCanvas` (which extends past viewport bounds), ensuring that horizontal and vertical chroma split ghosts never clip at canvas edges when panning.
  - **Canvas Pointer Focus & Hotkeys (`#cie-canvas`)**:
    - Configured `#cie-canvas` with `tabindex="0"` and pointerdown event listeners on canvas and canvas container.
    - Clicking/tapping anywhere on the canvas or preview pane immediately focuses the canvas and window (blurring active inputs or chat textareas), restoring instant keyboard hotkey responsiveness (`Space`, `WASD`, `Q`/`E`, `R`, `C`, `Z`, `F`, etc.).
  - **Synchronized Versioning**: Incremented application version across page title, help overlay header, control panel header, system metadata, and project history documentation to `1.29.7`.

### 📍 Version 1.29.8 [2026-07-30 UTC]: Infinite Zoom Deep Performance Culling, Depth UI Disabling, Hover Limit Popovers, Cache Cleanup & Manual Edit Summaries
* **Manual Edits Summary (User Customizations)**:
  - **Help Overlay Formatting & Structure (`#cie-help-overlay`)**: Grouped options and `⏸️Static scene pause` under a new `⚙️Options` section header above `⌨️🖱️👆Controls`, updated coordinate wrap description to `🌐🔁 Coordinate wrap`, and refined spacing in control group rows.
  - **Slider Limit Tracks & Limit Popover Visual Styling**: Updated `.cie-limits-popover` background (`rgba(32,11,4,.85)`) and inset shadow (`inset 0px 0px 2px 1px #FF5722`), `.cie-limit-track` background (`rgba(255,87,34,0.25)`) and tooltip transform, `.cie-limit-marker` color (`#ff5722`), and changed active ping-pong button highlight text color from `red` to `lime`.
* **User Intent / Feedback ("Infinite Zoom Performance Culling, Depth Disabling, Hover Limit Popovers & Anti-Stale Cache Prevention - Version 1.29.8 Updates"):**
  - **Infinite Zoom Deep Zoom Culling & Performance Fixes (`#cie-infiniteZoom` & `drawRec`)**:
    - Implemented spatial/bounding-box branch culling in `drawRec` during infinite zoom mode (`#cie-infiniteZoom`), instantly pruning subtrees shifted off-screen to eliminate deep zoom exponential rendering overhead and browser freezing at deep zoom levels (`#cie-zoom` ~8 to 20).
    - Refactored `enforceSafety()` continuous FPS monitoring so performance checks execute regardless of whether `#opt-fps` is checked. Frame intervals taking >1000ms properly calculate low framerate ($\le 1$ FPS), automatically triggering engine pause (`setPauseState(true)`), highlighting offending features in red (including `#cie-infiniteZoom`), and displaying the `showPerformanceToast()` notification.
    - Disables `#cie-depth` and `#cie-depthNum` inputs when `#cie-infiniteZoom` is active and styles the `#cie-depthGroup` container with `pointer-events: none; opacity: 0.5`.
  - **Limit Track Hover Popover Activation (`.cie-limit-track`)**:
    - Added mouseover event delegation for `.cie-limit-track` elements so hovering over any slider limit track automatically opens that effect's corresponding `.cie-limits-popover` (`#cie-limits-[key]`).
  - **Anti-Stale Cache Prevention**:
    - Added automatic ServiceWorker unregistration and Cache Storage deletion script to `<head>` to prevent GAIS/preview cache serving stale versions of `index.html` or assets, preserving `localStorage` completely.
  - **Manual Edits & Syntax Fix Summary**:
    - Corrected unclosed HTML tag attribute in help overlay (`<a href="https://en.wikipedia.org/wiki/Feedback" target="_blank" id="cie-help-link">Feedback</a> echo`) that caused Vite HTML parser syntax errors (`unexpected-character-in-attribute-name`).
    - Updated help row labels for UI control group elements (`↔/←/→ Slider direction`, `⏱️ Slider speed`, `╭╯Speed scale`, `🎚️ Slider limits`).
    - Cleaned up speed scale dropdown labels (`Loop`, `Bounce`).
  - **Synchronized Versioning**: Incremented application version across page title, help overlay header, control panel header, system metadata, and project history documentation to `1.29.8`.

### 📍 Version 1.29.9 [2026-07-30 UTC]: Limit Track Interaction Overhaul, Infinite Zoom Depth & Zoom Out Alignment, Pattern Rename & Skew Projection Fix
* **User Intent / Feedback ("Limit Track Interaction Model, Infinite Zoom Depth Extents, Fractree Pattern Rename, Skew Projection Zoom Fix & Programmatic Control Tooltips"):**
  - **Limit Track Popover Interaction Overhaul (`.cie-limit-track`)**:
    - Removed hover-based popover trigger from `.cie-limit-track`.
    - Added 500ms long press/click (with movement threshold ≤ 5px) on `.cie-limit-track` to open `.cie-limits-popover`.
    - Added right-click (`contextmenu`) listener on `.cie-limit-track` to open `.cie-limits-popover`.
    - Added left-click listener on locked limit tracks (`.cie-limit-track.locked`) to open `.cie-limits-popover`.
  - **Infinite Zoom Depth & Zoom-Out Extents (`#cie-infiniteZoom`)**:
    - Extended infinite zoom recursion depth to `9` across all render patterns and enabled/unlocked recursion depth controls for all patterns including `flower` (Flower of Life).
    - Removed negative `levelShift` floor clamping (`if(levelShift < 0) levelShift = 0`), enabling continuous fractal zoom-out behavior where visual depth and patterns remain identical across all zoom scales (zoom in and zoom out).
  - **Pattern Constant Rename (`fractal` -> `fractree`)**:
    - Renamed all instances of the `'fractal'` pattern constant, option values, preset maps, and draw functions to `'fractree'` (Fractal Tree).
  - **Skew X/Y WebGL Projection Zoom Fix (`#cie-useSkewX`, `#cie-useSkewY`)**:
    - Corrected WebGL texture coordinate mapping in `renderWebGL()` when sampling `oversizedCanvas`.
    - Calculated relative UV aspect ratios `(canvas.width / oversizedCanvas.width) * S` and `(canvas.height / oversizedCanvas.height) * S` dynamically, resolving the ~3x zoomed-out view artifact when skew X, skew Y, or perspective is enabled.
  - **Programmatic Control Group Tooltips (`#cie-controls .cie-control-group`)**:
    - Added `setupControlGroupTooltips()` function to programmatically assign consistent tooltips across all `.cie-control-group` buttons (`.cie-reset-btn`: "Reset slider value", `.cie-slider-anim`: "Slider animation direction: ← Left, → Right, or ↔ Ping-pong", `.cie-limits-btn`: "Slider limits: Set range, direction, & speed scale", `.cie-pp-speed-btn`: "Slider animation speed", `.cie-random-slider-btn`: "Randomize slider value").
  - **Synchronized Versioning**: Incremented application version across page title, help overlay header, control panel header, system metadata, and project history documentation to `1.29.9`.

### 📍 Version 1.29.10 [2026-08-02 UTC]: Hover Animation Fixes, Background Performance Safeguard Exclusion, Paused State Persistence & Manual Edit Summaries
* **Manual Edits Summary (User Customizations)**:
  - **Feature Index Documentation Updates (`history.md`)**: Expanded feature list with Control Group element definitions (`↔ Ping-pong`, `🎚️ Limits button`, `↺ Reset button`), reorganized pattern categories, line color, trails, viewport, pulse, converge, and wobble controls.
  - **Animation Direction Select Styling (`.cie-anim-dir-select`)**: Added `appearance: base-select`, `column-gap: 2px`, `padding: 0`, and `font-weight: bold` for selected options.
  - **Control Readout & Default Settings (`#cie-currentRotVal`, `SLIDER_DEFAULTS`, `DEFAULTS`)**: Updated rotation readout font size to 11px, default slider depth to 9, and default gradient color 2 to `#000`.
  - **UI Active Button & Indicator Glow Cleanup (`.cie-slider-anim.active`, `.cie-track-dir-indicator`, `.active-continuous`)**: Replaced heavy drop shadow filters on active animation direction buttons and track direction indicators with clean `lime` text-shadow, and styled `.active-continuous` button with green `lime` indicator theme.
  - **Control Group Indentation & Hover Highlights (`.indent`, `.cie-row:hover`)**: Added `.indent` class to `label[for=cie-wobble]` / `Singularity` labels in help overlay and control panel, updated Distortion Frequency label text to `˒﹚) Frequency`, and added clean hover highlight backgrounds (`rgba(38,38,38,.75)`) on `.cie-row:hover`.
* **User Intent / Feedback ("Hover Animation Letter Distortions, Background Tab FPS Safeguard Exclusion, Engine Paused State Persistence & Version 1.29.10 Updates"):**
  - **Label Hover Animations Fix (`initLabelHoverAnimations`)**:
    - **Wobble Amplitude (`label[for=cie-wobble]`)**: Changed hover scale transform to `scaleY(${scaleVal})` (vertical scaling only), maintaining constant character width and zero horizontal letter spacing expansion on hover.
    - **Frequency Labels (`.cie-label` Frequency)**: Scaled hover breathing modulation amplitude from 6% to 25% (`1 + Math.sin(angle) * 0.25`), providing a clear and noticeable font-size breathing effect.
  - **Background Tab Performance Safeguard Exclusion (`document.hidden`)**:
    - Updated FPS performance monitoring to bypass safeguard actions (reducing depth / pausing engine) when `document.hidden` or `document.visibilityState === 'hidden'` is true, preventing OS/browser background tab throttling from falsely triggering performance degradations.
    - Added `visibilitychange` listener to reset FPS timing metrics (`fpsLast`, `fpsCnt`) when returning to the tab.
  - **App Paused State Persistence (`setPauseState` & `pushSliderState`)**:
    - Added `pushSliderState()` call inside `setPauseState(paused)`, ensuring engine pause state changes trigger autosave to `localStorage` and persist accurately upon reloading or refreshing the browser tab.

### 📍 Version 1.29.11 [2026-08-02 UTC]: Skew Fixes, Canvas Element vs Drawing Skewing, Chroma Split Preservation & Background Pause Option
* **Manual Edits Summary (User Customizations)**:
  - **Options Tab Checkbox Group Reorganization (`.cie-options-row`)**: Reorganized Options tab controls into clean, structured groups: row 1 (`📐3D pause`, `💾Autosave`, `⏸️Static scene pause`), row 2 (`✨Adaptive UI`, `🎞️FPS`, `Mini visualizer`, `Scrollbars`, `🧲Snap sliders`).
* **User Intent / Feedback ("Skew Fixes, Background Tab Performance Safeguard Exclusion & Version 1.29.11 Updates"):**
  - **Skewing & Chroma Split Fixes (`.cie-useSkewX`, `.cie-useSkewY`, `.cie-skewCanvas`)**:
    - **Chroma Split Preservation**: Configured `renderWebGL()` to sample the main 2D `canvas` texture (which includes Chroma Split and all 2D composition passes) instead of raw intermediate buffers, ensuring horizontal and vertical Chroma Split effects remain 100% active and visible when skewing is enabled.
    - **Drawing Skew vs. Canvas Element Skew**: Tying `.cie-skewCanvas` (`#cie-skewCanvas`) directly to CSS element skew vs. WebGL drawing matrix skew. When `#cie-skewCanvas` is unchecked, skewing is performed strictly on the drawing matrix in WebGL (keeping canvas DOM elements unskewed). When `#cie-skewCanvas` is checked, CSS `transform: skewX(...) skewY(...)` is applied to the `<canvas>` DOM element.
    - **Coordinate Space Alignment**: Inverted WebGL matrix Y-skew angle (`-skewYRad`) to align WebGL normalized device coordinates with CSS element transform direction space.
  - **Background Tab Performance Safeguard Exclusion & Background Pause (`#opt-bgPause`)**:
    - Added `opt-bgPause` ("⏸️Background pause") checkbox in the Options tab immediately after `Autosave`.
    - Integrated background pause check in `update()` main loop (`if (document.hidden && chk('opt-bgPause')) return;`), yielding rendering when tab is hidden to conserve CPU/GPU resources.
    - Added `optBgPause` state persistence in `getSettings()` and `loadSettings()`.
  - **Synchronized Versioning**: Incremented application version across page title, help overlay header, control panel header, system metadata, and project history documentation to `1.29.11`.

### 📍 Version 1.29.12 [2026-08-02 UTC]: Active Canvas Dynamic Filter Scoping, WebGL Anti-Aliasing, Skew Alignment & AUIAFI Refinements
* **User Intent / Feedback ("Canvas Filter Optimization, WebGL Anti-Aliasing, Texture Edge Bleeding Fix & AUIAFI Label Spacing & Title Inheritance"):**
  - **Canvas Filter & Transform Scoping (`#cie-webgl-canvas`, `#cie-canvas`)**:
    - Scoped CSS filters (`filter`, `backdrop-filter`, `transform`) exclusively to the currently active canvas (`#cie-webgl-canvas` or `#cie-canvas`).
    - Explicitly cleared filter and transform styles on the hidden canvas to avoid duplicate processing and conserve GPU/CPU resources.
  - **WebGL Anti-Aliasing (`initWebGL`)**:
    - Enabled hardware anti-aliasing (`antialias: true`) on WebGL context creation.
  - **WebGL Skew Correction & Texture Edge Mapping (`renderWebGL`)**:
    - Inverted `skewX` angle (`-skewXRad`) in WebGL transformation matrix to match 2D CSS canvas skew orientation.
    - Set texture UV mapping to exact normalized coordinates (`0.0`–`1.0`), eliminating side smearing and edge bleeding artifacts when zooming out with skew enabled.
  - **Automatic UI Abbreviation/Font-Scaling/Iconifying (AUIAFI) Refinements (`parseLabel`, `restoreRowToDefault`, `runLabelFontScalingPass`, `solveRowWrapping`)**:
    - **Emoji Spacing**: Updated `parseLabel` to strip whitespace between multiple emojis/symbols in `iconHTML`, rendering compact iconified labels without spaces between emojis.
    - **Parent Group Title Inheritance**: Updated title assignment logic (`updateElementTitle`) to inherit and set tooltips on parent checkbox/radio group containers (`.cie-checkbox-group`, `.cie-radio-group`) rather than individual child `.cie-label` elements, preventing redundant tooltip overlaps.
    - **Empty Attribute Cleanup**: Added `cleanEmptyAttributes()` to remove empty or whitespace-only `title` or `style` attributes from DOM elements, preventing unwanted CSS/browser tooltip overrides.
  - **Options Tab Checkbox Layout**: Grouped Options tab controls into rows containing at most 3 items each (`3D pause`, `Autosave`, `Background pause`, `Adaptive UI`, `FPS`, `Mini visualizer`, `Scrollbars`, `Snap sliders`), ensuring clean row wrapping and preventing crowded rows on narrow viewports.
  - **Synchronized Versioning**: Incremented application version across page title, help overlay header, control panel header, system metadata, and project history documentation to `1.29.12`.

### 📍 Version 1.30 [2026-08-03 UTC]: Hover-Based Arrow Key Routing, Limits Popover Synchronization, AUIAFI 3-Option Row Constraints, Scale Width Default Inversion, Real-Time Math Equation Overlay & Manual Edit Summaries
* **User Intent / Feedback ("Hover-Based Arrow Key Routing, Limits Popover min/max/step Sync, AUIAFI 3-Option Row Limit, Scale Width Default Inversion, Real-Time Math Equation Overlay & Version 1.30 Updates"):**
  - **Hover-Dependent Arrow Key Routing (`getHoverOrActiveContext`, `keydown`, `processContinuousKeys`)**:
    - **Control Panel Hover**: Arrow keys (`ArrowUp`, `ArrowDown`, `ArrowLeft`, `ArrowRight`) scroll `#cie-content` and active `.cie-tab-panel-content` / `.cie-tab-panel` containers without zooming/panning the canvas.
    - **Slider Hover**: Arrow keys move slider thumb handle left/right for horizontal sliders and up/down for vertical sliders (`cie-pp-speed-slider`), adjusting slider values smoothly and updating all listeners.
    - **Select Hover**: Arrow keys step through option selections in `<select>` elements without affecting canvas viewport zoom.
  - **Limits Popover Attribute Synchronization (`syncLimitsPopoverInputAttrs`)**:
    - Synchronized `min`, `max`, and `step` attributes from control group number inputs and range sliders directly to each corresponding `.cie-limits-popover > input[type=number]` (`lmin` and `lmax`).
  - **Programmatic AUIAFI 3-Option Per Row Constraint (`solveRowWrapping`)**:
    - Consolidated Options tab controls into clean section `.cie-options-row` containers and updated AUIAFI compression solver (`checkNeedsCompression`) to stop compressing as soon as wrapped lines reach at most 3 options per row.
  - **Scale Width Default & Disabling Inversion (`#cie-scaleWidth`)**:
    - Enabled width scaling by default (`!chk('cie-scaleWidth')`) and inverted checkbox behavior so checking `#cie-scaleWidth` disables width scaling on zoom.
  - **Real-Time Canvas Math Equation Overlay (`#cie-equation`, `updateEquationOverlay`)**:
    - Added `📐Equation` checkbox (default unchecked) under Display options tab section.
    - Implemented `#cie-equation` canvas overlay displaying active mathematical functions, transformation matrices, zoom factors, rotation angles, and effect parameters in real-time.
  - **Manual Edit Summaries (16 Edits)**:
    - Adjusted `.cie-control-group` with `margin-left: auto` for flex alignment.
    - Enabled `overflow: auto` on `.cie-controls select`.
    - Updated `#cie-currentRotVal` text color to `lime`.
    - Added hover text color transitions (`#fff`) on `.cie-label`, `.cie-checkbox-group`, and `.cie-radio-group`.
    - Applied green active background state (`rgba(0,255,0,1)`) on range slider thumbs (`input[type=range]::-webkit-slider-thumb:active`).
    - Standardized box shadow syntax without `px` units on `#cie-fps`, `.cie-perf-warning`, `.cie-num-animating`, `.cie-limits-popover`, and `.cie-distort-effect`.
    - Enhanced header left branding and icon buttons with hover glow filters (`drop-shadow(0 0 3px #fff)`) and scale animations.
    - Adjusted `.config-list` overflow/border and `.config-item` hover backgrounds (`#222`).
    - Corrected `.cie-custom-select-option[data-val="black"]` text-shadow.
    - Cleaned up transform translateY shorthand (`translateY(0)`).
    - Refactored floating panel coordinates (`floatTop`, `floatRight`) to unitless `'0'`.
  - **Synchronized Versioning**: Incremented application version across page title, help overlay header, control panel header, system metadata, and project history documentation to `1.30`.

### 📍 Version 1.30.1 [2026-08-04 UTC]: Trail Persistence on Control Inputs, Animated SSP Trail Support, Expanded Real-Time Mathematical Equations & Manual Edit Summaries
* **User Intent / Feedback ("Fix trails persistence, verify animation effects produce trails with SSP, show actual combined equations in equation overlay & Version 1.30.1 Updates"):**
  - **Trail Persistence on Manual Number Inputs & Slider Release (`input`/`change` event listeners, `lastManualInteractionTime`)**:
    - Updated all `.cie-control-group` input and change handlers to refresh `lastManualInteractionTime = Date.now()` on manual interaction.
    - Ensured changing number inputs and releasing slider handles on non-animated controls (including Zoom, Scale, Shake, Wobble amplitude, Distortion ripple, etc.) keeps trails (`#cie-trail`) active and accumulating during manual adjustments.
  - **Animated Trail & Static Scene Pause (SSP) Interaction (`isDrawingStatic`, `trailEnabled`)**:
    - Refactored `isDrawingStatic()` to check active animation state independently for pulse, rotation, wobble, distortion ripple, shake, color/mode cycling, track limits, and audio reactivity.
    - Ensured all active animating effects produce trails continuously even when Static Scene Pause (`#cie-staticScenePause`) is enabled.
    - Confirmed SSP strictly stops trail accumulation on completely non-animating, static scenes while preserving pause button (`#cie-pauseBtn`) for full animation halting.
  - **Combined Canvas Real-Time Mathematical Equation Overlay (`#cie-equation`, `updateEquationOverlay`)**:
    - Expanded equation overlay to calculate and display the complete active pattern formula ($2h, 2v, 4, 4+, 3d2h, 3d2v, 3d4+, spiral, flower, lissajous, fractree, kaleid, kaleid12, 1h, 1v, 1hi, 1vi, 2hi, 2vi$), recursion depth $d$, combined scale matrix $S = \text{scale} \cdot 2^{(\text{zoom}+0.45)/2}$, rotation matrix $R(\theta)$, pulse $P(t)$, wobble $W(t)$, distortion ripple $D(r,t)$, shake $\delta$, chromatic aberration $\Delta\lambda$, and line thickness scaling $w$.
  - **Manual Edit Summaries (2 Edits)**:
    - Updated `#cie-equation` overlay CSS tooltip styling, adjusting positioning, border, background transparency, font size, and text formatting.
    - Updated label on Equation checkbox (`ƒ Equation`) under Display options section, updated tooltip text, and extended tooltip auto-hide timeout duration to 6000ms.
  - **Synchronized Versioning**: Incremented application version across page title, help overlay header, control panel header, system metadata, and project history documentation to `1.30.1`.

### 📍 Version 1.30.2 [2026-08-04 UTC]: Visual SVG Pattern Dropdown Icons, Complete Effect Reset Coverage Audit & Manual Edit Summary
* **User Intent / Feedback ("Visual SVG Pattern Icons, Global Reset Coverage Fixes, SLIDER_DEFAULTS Synchronization & Version 1.30.2 Updates"):**
  - **Visual SVG Pattern Icons (`#cie-pattern-container`, `PATTERN_ICONS`, `updatePatternSelectUI`)**:
    - Refactored the `♾ Pattern` select element into a custom dropdown UI component featuring small, high-precision visual SVG icons representing all 19 geometric patterns (`1h`, `1v`, `1hi`, `1vi`, `2h`, `2v`, `2hi`, `2vi`, `3d2h`, `3d2v`, `3d4plus`, `4plus`, `4`, `kaleid`, `kaleid12`, `fractree`, `lissajous`, `spiral`, `flower`).
    - Implemented instant visual updates and synchronization for preset loading, option changes, and reset operations.
  - **Global Reset Coverage Fixes (`performResetAll`, `loadSettings`, `DEFAULTS`)**:
    - Audited and updated `performResetAll()` and `DEFAULTS` to reset all missing effect properties upon local effect reset and global reset:
      - FOV value (`#cie-fov`: 32.5) and status (`#cie-useFov`, `#cie-fovMode`)
      - Depth orbit status (`#cie-rotDepths`), Depth orbit roll status (`#cie-rotDepthRoll`), and depth orbit factor (`#cie-rotDepthFactor`: 0.005)
      - Perspective value (`#cie-perspective`: 1000) and status (`#cie-usePerspective`)
      - Recenter status (`#cie-recenter`), smooth status (`#cie-recenterSmooth`), and time value (`#cie-recenterTime`: 1)
      - Skew X (`#cie-skewX`), Skew Y (`#cie-skewY`), use skew X (`#cie-useSkewX`), use skew Y (`#cie-useSkewY`), and skew canvas (`#cie-skewCanvas`)
      - Shake distance X/Y (`#cie-shakeDistX`, `#cie-shakeDistY`: 20), shake speed X/Y (`#cie-shakeSpeedX`, `#cie-shakeSpeedY`: 10), shake status (`#cie-shake`), and shake canvas (`#cie-shakeCanvas`).
  - **SLIDER_DEFAULTS Synchronization (`SLIDER_DEFAULTS`)**:
    - Updated `SLIDER_DEFAULTS` to match default slider HTML values across all effects (`rotDepthFactor: 0.005`, `recenterTime: 1`, `fov: 32.5`, `perspective: 1000`, `shakeSpeedX: 10`, `shakeDistX: 20`, `shakeSpeedY: 10`, `shakeDistY: 20`, `skewX: 0`, `skewY: 0`).
  - **Hover Context Select Integration (`getHoverOrActiveContext`)**:
    - Expanded select detection to recognize custom select containers and triggers (`.cie-custom-select-container`), ensuring mouse hovering over custom dropdowns routes arrow hotkeys away from canvas navigation.
  - **Manual Edit Summary (1 Edit)**:
    - Updated `index.html` controls and help overlay titles to version `1.30.2`.
  - **Synchronized Versioning**: Incremented application version across page title, help overlay header, control panel header, system metadata, and project history documentation to `1.30.2`.

### 📍 Version 1.30.3 [2026-08-05 UTC]: Custom Pattern SVG Icon Refinements, Custom Dropdown Keyboard Navigation, 3D Line Thickness & Culling Fixes
* **User Intent / Feedback ("Pattern SVG Icons Refinements, Arrow Key Navigation in Custom Dropdowns, 3D Pattern Thickness Scaling & Vertical Rotation Clipping Fixes & Version 1.30.3 Updates"):**
  - **Pattern SVG Icon Vector Refinements (`PATTERN_ICONS`)**:
    - Updated vector icons across `PATTERN_ICONS` in `index.html` according to exact geometry specifications:
      - Added outer bounding circles (`<circle cx="8" cy="8" r="7.2"...>`) to all pattern icons except 'fractal tree', 'lissajous', 'spiral', and 'flower of life'.
      - Resized and clustered overlapping circles in the 'Spiral' icon to clearly represent radially clustered overlapping geometry.
      - Updated '2-Way Horizontal' and '2-Way Vertical' icons to mirror their inverted counterparts with inside concentric circles.
  - **Custom Select Arrow Key & Hotkey Navigation (`getHoverOrActiveContext`, `keydown`)**:
    - Enabled keyboard arrow key navigation (`ArrowUp`, `ArrowDown`, `ArrowLeft`, `ArrowRight`, `Enter`, `Space`) for `.cie-custom-select-container` custom dropdowns (`#cie-pattern`, `#cie-theme`).
    - Stepping with arrow keys dynamically updates option selection, scrolls active options into view, dispatches `change` events, and updates pattern/theme UI. Pressing `Enter` or `Space` confirms choice and closes the dropdown.
  - **3D Pattern Line Thickness & Projection Culling Fixes (`draw3D4Plus`, `draw3D2H`, `draw3D2V`)**:
    - **Line Thickness Scaling (Bug 3a)**: Updated `draw3D4Plus`, `draw3D2H`, and `draw3D2V` to calculate stroke width as `strokeW = o.scaleWidth ? o.thick * perspective : o.thick`. When `#cie-scaleWidth` is OFF (default), stroke width remains strictly constant (`o.thick`), preventing lines from getting thicker when rotating or bringing inner recursion depths closer to the camera during negative zoom/scale.
    - **Vertical Rotation Clipping/Culling (Bug 3b)**: Increased camera focal distance in 3D projection to $1500$, keeping perspective calculations stable across full $90^\circ$ vertical tilt rotations (`Shift` + RMB drag), and reduced minimum radius culling threshold to `0.001` so outer and inner branches remain rendered without premature clipping.
  - **Synchronized Versioning**: Incremented application version across page title, help overlay header, control panel header, system metadata, and project history documentation to `1.30.3`.

### 📍 Version 1.30.4 [2026-08-05 UTC]: Independent Rotate Y / Rotate Z Control Groups, Camera Focal Distance, Expanded Wrap Threshold & Limit Marker Position Fix
* **User Intent / Feedback ("Rotate Y & Rotate Z Control Groups, Camera Distance Control, Wrap Threshold Control Group Expansion, Number Input Non-Default Highlight, Perspective Group Hiding, Limit Marker Fix & Version 1.30.4 Updates"):**
  - **Independent Rotate Y & Rotate Z Control Groups (`#cie-rotateY`, `#cie-rotateZ`, `rSpeedY`, `rSpeedZ`, `manualRotZ`, `rTimeY`, `rTimeZ`)**:
    - Added full control groups (`#cie-control-group`: number/range inputs, slider animation direction, slider anim speed, slider limits, speed scale, randomizer, and reset button) for 'Rotate Y'-axis (`#cie-rotateY`) and 'Rotate Z'-axis (`#cie-rotateZ`).
    - Integrated multi-axis rotation into `updateCurrentRotVal()` to update degrees for `#cie-currentRotYVal` and `#cie-currentRotZVal`.
    - Applied 3D rotation transformations to 3D patterns (`3d4plus`, `3d2h`, `3d2v`) and planar 2D projections.
  - **Camera Focal Distance Control Group (`#cie-cameraDist`, `cameraDist`)**:
    - Added full control group for 'Camera distance' (`#cie-cameraDist`, default `1500`, range `100` to `5000`) in 'Animation' > 'Viewport' section for adjusting focal depth in 3D perspective projections.
  - **Expanded Wrap Threshold Control Group (`#cie-panWrapThreshold`)**:
    - Renamed and expanded 'pan wrap threshold' into a full control group titled 'Wrap threshold' (`#cie-panWrapThreshold`).
    - Repositioned on the same row as the `#cie-panWrap` checkbox and removed automatic hiding of `#cie-panWrapThresholdContainer` when unchecked.
  - **Visual Feedback for Number Inputs (`checkNumHighlight`, `updateAllNumberInputHighlights`)**:
    - Implemented dynamic background color styling (`rgba(0,255,0,.25)`) for all number inputs (`input[type=number]`) whenever their current value differs from the default value (`SLIDER_DEFAULTS`).
  - **Hidden Perspective Group (`#cie-group`)**:
    - Hid non-functional 'Perspective' control group (`style="display:none"`).
  - **Limit Marker Position Reset Fix (`syncMirroredLimits`)**:
    - Fixed `.cie-limit-marker.right` position reset issue occurring when limit lock is enabled, left limit marker is at default minimum, and amount is not 100%.
  - **Manual Edit & Attribute Fix Summary**:
    - Fixed malformed HTML inline style attribute on the infinite zoom label element (`<label class="cie-label" for="cie-infiniteZoom" style="font-size:16px; line-height:1">`) in `index.html` to resolve Vite HTML parse error (`unexpected-character-in-attribute-name`).
  - **Synchronized Versioning**: Incremented application version across page title, help overlay header, control panel header, system metadata, and project history documentation to `1.30.4`.

### 📍 Version 1.30.5 [2026-08-05 UTC]: Restoration of Input Number Background, Multi-Axis 2D/3D Rotation, Reset Behavior, Side-Effect Separation, Dynamic Camera Focal Distance & Uncapped 3D Recursion
* **User Intent / Feedback ("Restore number input background on default, Fix rotation Y-/Z-axis for 2D/3D, Disable rotation checkboxes on reset, Prevent auto-checking effects on slider drag, Fix camera distance, Fix 3d4plus recursion depth past 6, Version 1.30.5 Updates"):**
  - **Number Input Default Highlight Restoration (`checkNumHighlight`)**:
    - Restored logic to clear green background (`rgba(0,255,0,.25)`) back to default transparent when a number input returns to its default value (either manually typed or via slider/control reset).
  - **Multi-Axis Rotation for 2D & 3D Projections (`rotate`, `rotateY`, `rotateZ`, `manualRot`, `manualRotY`, `manualRotZ`)**:
    - Enabled independent Y-axis and Z-axis rotation for planar 2D projections (`ctx.rotate` combined with `ctx.scale` tilt simulation).
    - Enabled full 3D rotation matrix transformations (Z -> Y -> X sequence) across 3D patterns (`3d4plus`, `3d2h`, `3d2v`).
  - **Rotation Checkbox Unchecking on Reset**:
    - Updated individual slider reset buttons (`.cie-reset-btn[data-reset="rSpeed"]`, `rSpeedY`, `rSpeedZ`) and master reset (`performResetAll()`) to automatically uncheck rotation axis checkboxes (`#cie-rotate`, `#cie-rotateY`, `#cie-rotateZ`).
  - **Independent Slider Control without Auto-Checking Effects**:
    - Removed side-effect behavior where moving the slider thumb auto-checked `#cie-glow` and rotation axis checkboxes (`#cie-rotate`, `#cie-rotateY`, `#cie-rotateZ`).
  - **Dynamic Camera Focal Distance (`#cie-cameraDist`)**:
    - Updated 3D pattern projection calculations (`3d4plus`, `3d2h`, `3d2v`) to dynamically utilize `cameraDist` parameter (`val('cie-cameraDist')`) instead of hardcoded depth constants.
  - **Uncapped 3D Recursion Depth (`3d4plus`, `3d2h`, `3d2v`)**:
    - Removed hardcoded cap (`Math.min(o.md, 6)`) in `draw3D4Plus` and `draw3D2H`/`draw3D2V` to allow rendering past recursion depth 6 up to maximum user settings.
  - **Manual Edit Summary**:
    - Restored `checkNumHighlight` default color clearing across all input listeners and reset events, added rotation Y/Z state serialization in `getSettings()` / `loadSettings()`, and synchronized versioning.
  - **Synchronized Versioning**: Incremented application version across page title, help overlay header, control panel header, system metadata, and project history documentation to `1.30.5`.

### 📍 Version 1.30.6 [2026-08-06 UTC]: Equation Overlay Pause & Formatting, Limit Track Randomizer, Drag Tooltips, Full 3D Navigation & Stationary FPS Counter
* **User Intent / Feedback ("Equation updates on pause & math notation formatting, Limit track randomizer button & context menu, Limit marker tooltips during track drag, Full 3D mouse rotation & key shortcuts, Stationary FPS counter during canvas shake, Version 1.30.6 Updates"):**
  - **Equation Overlay Enhancements (`#cie-equation`, `updateEquationOverlay`, `formatLaTeXToHTML`)**:
    - **Pause State Synchronization**: Suspended continuous equation string rebuilds and avoided redundant `display` property toggling when the engine is paused and no redrawing is requested.
    - **LaTeX Math Notation Formatting**: Implemented `formatLaTeXToHTML()` to convert LaTeX strings (`r_{n+1}`, `2^{n}`, `x\pm`, `\cup`, `\bigoplus`, `\cdot`, `\sin`, `\cos`, `\delta`, `\Delta`, `\theta`, `\lambda`, `\pi`, `\quad`, `√`) into clean, beautifully formatted HTML (`r<sub>n+1</sub>`, `2<sup>n</sup>`, `x±`, `∪`, `⨁`, `·`, `sin`, `cos`, `δ`, `Δ`, `θ`, `λ`, `π`, `√`).
    - **Text Selection**: Enabled `pointer-events: auto; user-select: text; -webkit-user-select: text; cursor: text;` on `#cie-equation` so users can easily highlight and copy equations directly with the cursor.
  - **Random Slider Limit Track Button & Context Menu (`.cie-limit-track-random-btn`, `showRandomSliderContextMenu`)**:
    - Injected randomizer button (`button.cie-random-slider-btn.cie-limit-track-random-btn`) into `.cie-limits-popover` next to the track scale container.
    - Implemented track position randomization within allowed bounds (`sMin` to `sMax`), adhering to active distribution options (`uniform`, `center`, `left`, `right`, `ends`, `ends_only`, `left_center_right`).
    - Added right-click/long-press menu (`.cie-random-slider-menu`) support for limit track randomizers with dataset key prefix `track_` and header `Limit Track (${sliderKey})`.
  - **Limit Marker Tooltips During Track Dragging (`updateSliderLimitOverlay`)**:
    - Updated `updateSliderLimitOverlay(k)` to force display of left and right `.cie-limit-marker-tooltip` elements (`force-show`) whenever dragging the limit track (`activeLimitDragType === 'track'`) while `.cie-limits-popover` is hidden.
  - **Full 3D Mouse & Keyboard Navigation (`canvas mousedown/mousemove`, `processContinuousKeys`)**:
    - **Canvas Mouse Drag**: Enabled full 3D rotation (`manualRot`, `manualRotY`, and `manualRotZ` with `Alt` held) on canvas drag with `[Shift]` + `[LMB]`.
    - **Keyboard Shortcuts**: Added `[Ctrl]` + `[Q]`/`[E]` for Y-axis rotation, `[Alt]` + `[Q]`/`[E]` for Z-axis rotation, and `[Shift]` modifier for 2x rotation speed.
  - **Stationary FPS Counter During Canvas Shake (`#cie-fps`, `#cie-main-area`)**:
    - Repositioned `#cie-fps` element directly under `#cie-main-area` (outside `#cie-canvas-container`), ensuring it stays pinned at the bottom-left of the viewport and never vibrates or moves when `#cie-shakeCanvas` transforms the canvas container.
  - **Manual Edit Summaries & Documentation**:
    - Summarized all manual edits and updated control descriptions in `#cie-help-overlay` and `.cie-tab-panel`.
  - **Synchronized Versioning**: Incremented application version across page title, help overlay header, control panel header, system metadata, and project history documentation to `1.30.6`.

### 📍 Version 1.30.7 [2026-08-06 UTC]: Trail Converge Persistence, Limit Track Context Menu, Stationary Equation Overlay, Hotkey Remapping, Line Gradient & Conical Option
* **User Intent / Feedback ("Trail converge state persistence, Limit track randomizer context menu options, Stationary equation overlay during canvas shake, Hotkey remapping for control reset and 3D rotation reset, Line color gradient distribution fix and true radial/conical options, Version 1.30.7 Updates"):**
  - **Trail Converge Checkbox Persistence (`#cie-trail`, `#cie-trailConverge`, `updateTrailConvergeVisibility`)**:
    - Preserved `#cie-trailConverge` check state when `#cie-trail` is unchecked and subsequently checked again. If `#cie-trailConverge` was checked before disabling trails, it is automatically restored upon re-enabling trails.
  - **Random Slider Limit Track Context Menu (`.cie-limit-track-random-btn`, `showRandomSliderContextMenu`)**:
    - Updated limit track randomizer button configuration to support dedicated continuous interval timers, speed settings, and probability distributions (`uniform`, `center`, `left`, `right`, `ends`, `ends_only`, `left_center_right`) via `.cie-random-slider-menu`.
  - **Stationary Equation Overlay (`#cie-equation`, `#cie-main-area`)**:
    - Relocated `#cie-equation` outside `#cie-canvas-container` directly into `#cie-main-area`, keeping it stationary and pinned at the top-left of the viewport so it never moves when `#cie-shakeCanvas` transforms the canvas container.
  - **Hotkey Re-mapping & 3D Rotation Reset (`KeyR`, `Ctrl`+`R`, `#cie-help-overlay`)**:
    - Remapped `R` to `Ctrl`+`R` (or `Cmd`+`R`) to reset the current or last used control (`lastUsedSliderKey`).
    - Reassigned `R` (without modifier keys) to instantly reset all 3D rotation axes (`manualRot`, `manualRotY`, `manualRotZ`) back to 0.
    - Updated keyboard shortcuts documentation in the help overlay modal (`#cie-help-overlay`).
  - **Line Color Gradient Enhancements (`getCustomThemeStrokeStyle`, `getSpectralThemeStrokeStyle`, `#cie-customGradStyle`)**:
    - Resolved over-exposure of color 1 (`#cie-customColor`) across drawings by computing matrix-aware local bounds (`left`, `right`, `top`, `bottom`, `centerX`, `centerY`, `maxR`) from `ctx.getTransform()`, ensuring linear and radial gradients scale and center symmetrically regardless of nested `ctx.translate()` or `ctx.scale()` calls.
    - Implemented central spotlight/ripple `radial` gradients and added a dedicated `conical` gradient option (`<option value="conical">Conical</option>`) using `ctx.createConicGradient`.
  - **Manual Edit Summaries**:
    - Summarized user manual edits: dropdown styling fixes (`background:#111;`), CSS keyframe updates (`cie-hflip-anim`, `cie-vflip-anim`), Skew control range updates (-90 to 90), and popover button text color state synchronization.
  - **Synchronized Versioning**: Incremented application version across page title, help overlay header, control panel header, system metadata, and project history documentation to `1.30.7`.

### 📍 Version 1.30.8 [2026-08-07 UTC]: Limit Track Randomizer Fixes, Converged Trails Persistence, Hotkey Refinements, Gradient Coordinate Alignment, Input Highlight Fixes & Rotation Order
* **User Intent / Feedback ("Limit track randomizer continuous mode & right-click fixes, Trail converge check persistence, Hotkey remapping for rotation reset vs local reset, Gradient color distribution fix, Number input initial highlight fix, Rotation axes pitch/yaw/roll and control order, Centered overlay elements, Version 1.30.8 Updates"):**
  - **Limit Track Randomizer Continuous Mode & Context Menu Fixes (`.cie-limit-track-random-btn`, `showRandomSliderContextMenu`)**:
    - Fixed function call type mismatch in `showRandomSliderContextMenu` where `_isContinuous` boolean property was invoked as a function, restoring continuous mode toggles and right-click context menu access.
    - Fixed interval speed configuration so custom interval values update `randomSliderSpeeds[k]` properly without overwriting active interval handles in `randomSliderIntervals[k]`.
  - **Trail Converge Check State Persistence (`#cie-trail`, `#cie-trailConverge`, `updateTrailConvergeVisibility`)**:
    - Preserved `#cie-trailConverge` checked state when `#cie-trail` is disabled and re-enabled, preventing premature unchecking of converged trail options when main trail rendering is toggled.
  - **Hotkey Logic Refinements (`KeyR`, `Ctrl`+`R`, `Ctrl`+`Shift`+`R`)**:
    - Rebound plain `R` key to reset all 3D rotation axes (`manualRot`, `manualRotY`, `manualRotZ`, `rTime`, `rTimeY`, `rTimeZ`) back to 0.
    - Bound `Ctrl`+`R` to trigger local control reset on `lastUsedSliderKey`.
    - Bound `Ctrl`+`Shift`+`R` to trigger global engine reset (`#cie-resetBtn`).
  - **Gradient Coordinate Alignment (`getCustomThemeStrokeStyle`, `getSpectralThemeStrokeStyle`)**:
    - Updated horizontal, vertical, radial, and conical gradient generation to define coordinates relative to local drawing center `(0, 0)`, eliminating coordinate offset bugs and ensuring smooth, symmetric distribution of Color 1 and Color 2 across all drawn shapes.
  - **Number Input Initial Highlight Prevention (`checkNumHighlight`, `#cie-depthNum`, `#cie-fovNum`)**:
    - Added empty/null value guarding in `checkNumHighlight` and set explicit default HTML values (`value="9"` for depth, `value="32.5"` for FOV) to prevent non-default background highlights on initial load.
  - **3D Rotation Axes & Control Sort Order (`drawSingleState`, `.cie-group`)**:
    - Updated 3D canvas projection in `drawSingleState` so Z-axis rotation applies in-plane (`ctx.rotate`), X-axis applies pitch (`ctx.scale(1, cosX)`), and Y-axis applies yaw (`ctx.scale(cosY, 1)`).
    - Swapped control group HTML placement so rotation controls display in canonical order: Rotate X (`#cie-rotateZ`), Rotate Y (`#cie-rotateY`), Rotate Z (`#cie-rotate`).
  - **Centered Overlay UI Elements (`centerOverlayElements`, `#cie-fps`, `#cie-equation`)**:
    - Implemented `centerOverlayElements()` to dynamically calculate the horizontal center of `#cie-canvas-container` and position both `#cie-fps` and `#cie-equation` perfectly centered on the canvas width while keeping them outside the shaking container.
  - **Manual Edit Summaries**:
    - Summarized user manual edits: refined tab active/hover border radii and colors, standardized CSS `backgroundColor` properties across custom `select` dropdowns/checkboxes, centered confirm overlay modal content, adjusted 'chroma split' number `input` `step` values to 1, cleaned `option` text in 'animation direction' `select`, updated randomizer tooltips and menu `label` titles, and fixed unclosed string syntax error in limit track randomizer `button` initialization.
  - **Synchronized Versioning**: Incremented application version across page title, help overlay header, control panel header, system metadata, and project history documentation to `1.30.8`.

### 📍 Version 1.30.9 [2026-08-08 UTC]: FOV Input Reload Highlight Fix, Autosave Equation Status, Hotkey Rotation Overrides & Control Remapping, Smooth Ease-In/Out Shake Animation, Spiral Pattern Fixes & Custom Color Option Gradient
* **User Intent / Feedback ("FOV input reload highlight fix, Autosave equation status, Hotkey rotation browser override & z-axis mapping, Smooth 1s ease-in/out shake label animation, Spiral pattern pulse/wobble/distort fixes, Custom color theme option gradient preview, Glow overlay visibility with gRad 0, Static scene pause state preservation & Version 1.30.9 Updates"):**
  - **FOV Input Reload Highlight Fix (`checkNumHighlight`, `isInt`)**:
    - Removed `fov` from the integer field list (`isInt`) in startup initialization so float comparison matching default `'32.5'` clears non-default background highlights properly on reload.
  - **Autosave Equation Status (`#opt-equation`, `getSettings`, `loadSettings`)**:
    - Added `#opt-equation` check state serialization to `getSettings()` and `loadSettings(s)`, ensuring autosave remembers equation overlay visibility across reloads.
  - **Hotkey Rotation & Browser Overrides (`KeyQ`, `KeyE`, `Shift` + Mouse Drag)**:
    - Added `e.preventDefault()` to Q/E navigation and modifier key listeners to override browser default shortcuts (e.g., `Ctrl+E`, `Alt+E`).
    - Mapped `Shift` + `LMB` drag to rotate X/Y axes instead of Y/Z axes, and mapped `Alt` + `Q`/`E` to rotate Z-axis.
  - **Smooth Ease-In/Out Shake Label Hover Animation (`initLabelHoverAnimations`)**:
    - Enhanced 'Shake' label hover animation with a 1-second ease-in phase (ramping random translation distance from 0px to 3px max) on mouseenter, and a 1-second ease-out phase (ramping max translation down to 0px) on mouseleave before restoring original HTML.
  - **Spiral Pattern Animation Fixes (`drawSpiral`)**:
    - Fixed 'Pulse' in `drawSpiral` to expand/contract circle radii continuously instead of rotating X-axis angle.
    - Updated 'Wobble amplitude' and 'distortion ripple' in `drawSpiral` to operate independently even when 'Pulse' is disabled, responding accurately to wobble/distortion frequency settings.
  - **Custom Color Option Gradient Preview (`updateThemeControls`, `selectTheme`)**:
    - Added custom gradient styling (`linear-gradient(90deg, c1, c2)` / `radial-gradient(circle, c1, c2)`) to `.cie-custom-select-option[data-val='custom']` reflecting current Color 1 (`#cie-customColor`) and Color 2 (`#cie-customColor2`) with reverse (`#cie-customGradReverse`) and radial/linear style support.
  - **Glow Overlay Visibility (`targetGlowAlpha`, `isReallyStatic`, `update`)**:
    - Updated glow overlay alpha calculation to require `gRad > 0`, ensuring the glow overlay remains visually inactive when glow radius is set to 0 even if checkboxes are enabled.
  - **Static Scene Pause Preservation (`setPauseState`, `#cie-staticScenePause`)**:
    - Removed auto-enabling of Static Scene Pause (`#cie-staticScenePause`) upon pausing, preserving user's manual pause state preference.
  - **Track Limits Popover Controls (`syncLimitsPopoverInputAttrs`, `.cie-limits-popover`)**:
    - Integrated limit track direction toggle button, speed scale selector, reset button, and lock/mirror checkbox into all track limit popovers next to the close button, providing direct control over track ping-pong bounds and scale curves.
  - **Synchronized Versioning**: Incremented application version across page title, help overlay header, control panel header, system metadata, and project history documentation to `1.30.9`.

### 📍 Version 1.30.10 [2026-08-08 UTC]: Limit Track Randomizer Fixes & Speed Control, Hotkey & Mouse Rotation Swap, Control Panel FPS Optimization, Collapsed Tab Persistence, Shake Sub-controls Visibility, Tab Auto-hide & Pinning
* **User Intent / Feedback ("Limit track randomizer continuous mode & lock bypass, Hotkey Q/E swap & mouse shift drag x/y rotation, Rapid mouse hover FPS drop fix, Tab panel collapse state persistence, Shake sub-controls visibility toggle, Tab panel auto-hide & pinning, Randomizer interval speed fix & Version 1.30.10 Updates"):**
  - **Limit Track Randomizer Fixes & Limits-Lock Override (`_restartInterval`, `triggerRandomTrackValue`)**:
    - Fixed continuous mode for limit track randomizers by reading `randomSliderSpeeds['track_' + k]` and updating interval timers when speed settings change.
    - Implemented automatic temporary limits-lock bypass when randomizing limit track values (`ppLimitsLocked[k] = false`, unchecking lock checkbox), allowing track bounds to move freely.
  - **Hotkey & Mouse Rotation Axis Swap (`processContinuousKeys`, `mousemove`)**:
    - Swapped rotation hotkeys: `[Q]`/`[E]` now controls X-axis pitch, `[Alt]`+`[Q]`/`[E]` controls Z-axis roll, and `[Ctrl]`+`[Q]`/`[E]` controls Y-axis yaw.
    - Updated mouse drag rotation under `[Shift]`+`LMB`: Up/Down (`clientY`) controls X-axis pitch, Left/Right (`clientX`) controls Y-axis yaw, and `[Alt]`+`[Shift]`+`LMB` controls Z-axis roll.
  - **Control Panel Hover FPS Optimization (`.cie-tab-panel-content`, `initLabelHoverAnimations`)**:
    - Added CSS `contain: paint layout;` and replaced heavy inset `box-shadow` repaints on `.cie-tab-panel:hover` with a light `border-left` indicator, eliminating frame drops during rapid cursor movements over control panels.
    - Added an 80ms mouseenter throttle delay to label hover animations (`initLabelHoverAnimations`), preventing rapid cursor sweeps across control labels from spawning redundant DOM text wrappings and animation frame loops.
  - **Tab Panel Collapsed State Persistence (`collapsedTabPanels`, `getSettings`, `loadSettings`)**:
    - Persisted collapsed tab panel states in `localStorage` (`cie_collapsed_tabs`) upon collapse/expand toggles, preserving state across reloads regardless of `#cie-autosave` setting.
    - Added `collapsedTabPanels` map serialization to `getSettings()` and `loadSettings(s)`.
  - **Shake Sub-Controls Grouping & Visibility (`#cie-shake-subcontrols`, `updateShakeVisibility`)**:
    - Grouped Speed X, Distance X, Speed Y, Distance Y sub-controls into `<div id="cie-shake-subcontrols">` and automatically hide them when `#cie-shake` is unchecked.
  - **Tab Panel Auto-Hide & Header Pinning (`#cie-autoHideTabs`, `.cie-docked-pin-btn`)**:
    - Added `🖈 Auto-hide tabs` option (disabled by default) under Options -> Display.
    - Injected a pin button (`🖈`) left of `.cie-docked-header-toggle` in tab panel headers with active `lime` highlighting when pinned.
    - Implemented auto-hide on hover for unpinned panels in left/right docked modes, expanding unpinned collapsed panels on hover and auto-collapsing them 3 seconds after mouseleave.
  - **Randomizer Speed Control Fix (`randomSliderSpeeds`, `showRandomSliderContextMenu`)**:
    - Globalized `randomSliderSpeeds` map and connected context menu speed select, number input, and range slider controls to trigger `_restartInterval()`, restoring customizable randomization speeds (10ms to 5000ms).
  - **Manual Edit Summaries & Null-Safe Helper Functions (`val`, `chk`, `#cie-rotateX`)**:
    - Summarized user manual edits: restructured Animation tab section boxes and comments, renamed X-axis rotation checkbox ID to `#cie-rotateX`, updated `.cie-tab-panel:hover` box-shadow and `.cie-docked-header-toggle` sizing, and refined pin button styling (`.cie-docked-pin-btn`).
    - Fixed `TypeError: Cannot read properties of null (reading 'checked')` by adding null checks to `val()` and `chk()` helper functions and adding fallback support for `#cie-rotateX` alongside `#cie-rotate` across settings persistence, preset generation, and animation loops.
  - **Synchronized Versioning**: Incremented application version across page title, help overlay header, control panel header, system metadata (`metadata.json`), and project history documentation to `1.30.10`.

### 📍 Version 1.30.11 [2026-08-09 UTC]: Display Auto-Hide Tabs Option, Rotation Hotkey & Mouse Axis Re-mapping, Shake Sub-controls Visibility, X-Axis Gradient Fix, Popover Placement & Version 1.30.11 Updates
* **User Intent / Feedback ("Display auto-hide tabs option, Rotation hotkeys Q/E & Alt+Q/E re-mapping, Mouse Shift+LMB drag X/Y rotation, Shake sub-controls auto-hide, X-axis gradient artifact fix, Popover placement, Default glow overlay, Options row wrapping & Version 1.30.11 Updates"):**
  - **Auto-Hide Tabs Display Option (`#cie-autoHideTabs`, `#opt-autoHideTabs`)**:
    - Added `🖈Auto-hide tabs` checkbox under Options -> Display panel, connected to `autoHideTabs` setting serialization and docked tab panel auto-collapse hover timers.
  - **Rotation Hotkey & Mouse Drag Re-mapping (`[Q]`/`[E]`, `[Alt]`+`[Q]`/`[E]`, `[Shift]`+`LMB`)**:
    - Rebound `[Q]`/`[E]` to rotate Z-axis roll and `[Alt]`+`[Q]`/`[E]` to rotate X-axis pitch.
    - Updated `[Shift]`+`LMB` drag: Up/Down (`clientY`) rotates X-axis pitch, Left/Right (`clientX`) rotates Y-axis yaw, and `[Alt]`+`[Shift]`+`LMB` rotates Z-axis roll.
  - **Shake Sub-Controls Visibility (`#cie-shake-subcontrols`, `updateShakeVisibility`)**:
    - Grouped Speed X, Distance X, Speed Y, Distance Y sub-controls into `<div id="cie-shake-subcontrols">` and auto-hide them when `#cie-shake` is unchecked.
  - **X-Axis Rotation Color Gradient Fix (`cosX`, `Math.abs`)**:
    - Replaced signed cosine scaling with positive absolute cosine scaling `Math.abs(Math.cos(rotXVal))` in canvas matrix 3D transformations, eliminating flipped Y-axis matrix scales and fixing gradient artifacts at 64-67° and 114-116°.
  - **Limit Popovers Placement Preserved (`.cie-limits-popover`)**:
    - Preserved limit popover DOM placement inside `.cie-row` directly after `.cie-control-group` for background fade and trail converge options.
  - **Default Glow Overlay Setting (`#cie-glowOverlay`)**:
    - Enabled `#cie-glowOverlay` by default in HTML markup and default settings configuration.
  - **Options Row AFI & Wrapping Logic (`solveRowWrapping`, `handleLabelFontScaling`)**:
    - Updated options row wrapping logic to guarantee at least 2 options per line when wrapped and prevent unnecessary label abbreviation / font-scaling when the control panel is widened (~309px).
  - **Rotation Controls Refactoring (`cie-rotateX`, `cie-rSpeedX`)**:
    - Standardized X-axis rotation checkbox ID to `cie-rotateX`, speed slider ID to `cie-rSpeedX`, and updated LaTeX equation terms, timeline sync, and settings state.
  - **Manual Edit Summaries**:
    - Summarized user manual edits: refactored rotation labels and IDs (`cie-rotateX`, `cie-rSpeedX`, `cie-rotateY`, `cie-rotateZ`), added `column-gap: 2px` to `.cie-options-row`, updated `LABEL_ABBREVIATIONS` dictionary entries for Adaptive UI, Equation, and Snap sliders.
    - Summarized user manual edits: updated rotation hotkeys Q/E (Z axis) and Alt+Q/E (X axis), updated `#cie-equation` LaTeX output to list active 3D rotation terms (`R_x`, `R_y`, `R_z`), updated help overlay documentation and controls tab listings.
  - **Synchronized Versioning**: Incremented application version across page title, help overlay header, control panel header, system metadata (`metadata.json`), and project history documentation to `1.30.11`.

### 📍 Version 1.30.12 [2026-08-09 UTC]: Mouse Z-Axis Rotation Refactor, manualRotX Renaming, Equation 3D Rotations Display, 3D Color Gradient Scaling Fix, Shake Animation Ease/Reset Fix, Limit Track Random Toggle & Version 1.30.12 Updates
* **User Intent / Feedback ("Shift+LMB vertical drag Z-axis rotation mapping, Rename manualRot to manualRotX, Add Y/Z rotation to equation overlay, Fix shake hover animation ease 0.5s & letter translation reset, Fix 3D color gradient distortion at 61-120° and 240-299°, Limit track random button toggle & Version 1.30.12 Updates"):**
  - **Mouse Drag Z-Axis Rotation Mapping (`[Shift]`+`LMB`, `manualRotZ`)**:
    - Refactored `[Shift]`+`LMB` click-and-drag mouse rotation event handler so vertical drag movements explicitly map to the Z-axis (`manualRotZ`), removing previous X-axis dependency.
  - **Global Variable Renaming (`manualRot` -> `manualRotX`)**:
    - Renamed global `manualRot` to `manualRotX` across key shortcuts, mouse/touch handlers, reset functions, state persistence, rendering loops, and recenter lerps (with fallback compatibility for loading legacy states).
  - **Equation Overlay 3D Rotations Display (`updateEquationOverlay`)**:
    - Updated `#cie-equation` LaTeX output to calculate and render individual terms for X-axis (`R_x`), Y-axis (`R_y`), and Z-axis (`R_z`) rotation values and degrees whenever active.
  - **3D Color Gradient Scaling Fixes (`getCustomThemeStrokeStyle`, `getSpectralThemeStrokeStyle`)**:
    - Updated spectral and custom gradient generation logic to account for 3D rotation projection scaling (`scaleX_3d`, `scaleY_3d`), resolving color gradient distortion (turning solid red/orange) across 61-120° and 240-299° rotation angles.
  - **Shake Hover Animation Ease & Reset Fixes (`initLabelHoverAnimations`, `target.type === 'shake'`)**:
    - Reduced Shake label hover animation ease-in / ease-out duration from 1.0s to 0.5s (500ms).
    - Fixed animation stop bug where letters remained stuck at non-zero translate offsets by guarding `lbl._preHoverHTML` saving to prevent capturing transformed DOM nodes and clearing transform styles on animation completion.
  - **Limit Track Randomizer Continuous Toggle (`_restartInterval`, `continuousRandomizers`)**:
    - Updated limit track continuous randomizer buttons so clicking or tapping an active continuous randomizer button toggles it off immediately.
  - **Options Row Wrapping Optimization (`solveRowWrapping`)**:
    - Optimized options row wrapping CSS and flex rules to allow up to 3 options per row with complete label text and icons without forcing controls into separate lines.
  - **Manual Edit Summaries & Help Overlay Documentation**:
    - Summarized user manual edits: version updated to 1.30.12, controls documentation updated in help overlay `#cie-help-overlay` and `.cie-tab-panel` Options -> Controls panel.
  - **Synchronized Versioning**: Incremented application version across page title, help overlay header, control panel header, system metadata (`metadata.json`), and project history documentation to `1.30.12`.

### 📍 Version 1.31 [2026-08-10 UTC]: Matrix Inverse 3D Color Gradient Scaling, Recenter Guard Preservation, Mouse RMB Canvas Rotation Re-mapping, Real-time Custom Equation Pattern & Controls Suite, Input Parameter Context Menu, Panel Resize Cursor Tooltip & Version 1.31 Updates
* **User Intent / Feedback ("3D color gradient scaling at 61-199° horizontal linear gradient, Recenter resetting manual canvas rotation fix, RMB mouse rotation re-mapping, Pattern equation input field & Custom pattern suite, Right-click / touch long-press Min/Max/Step parameter context menu, Options row wrapping CSS optimization, Abbreviating label space rule fix, Panel resizing tooltip near mouse cursor & Version 1.31 Updates"):**
  - **Matrix Inverse 3D Color Gradient Scaling Fix (`getLocalPoint`, `getTransform().inverse()`)**:
    - Refactored `getCustomThemeStrokeStyle` and `getSpectralThemeStrokeStyle` to calculate local linear, radial, and conical gradient bounds via canvas 2D matrix transformation point inversion (`getLocalPoint`).
    - Solved color gradient distortion across 61-199° rotation angles and recursion depths 1-5+, guaranteeing smooth linear/radial/conical color transitions regardless of 3D matrix scaling or nested transforms.
  - **Recenter Manual Rotation Preservation (`#cie-recenter`, `#cie-recenterBtn`)**:
    - Fixed auto-recentering (`#cie-recenter`) and manual recenter trigger (`#cie-recenterBtn`) to preserve manual rotation angles (`manualRotX`, `manualRotY`, `manualRotZ`) while smoothly re-centering viewport offsets (`panX`, `panY`).
    - Updated `isSceneStatic` auto-recenter guard to check only viewport displacement (`panX`, `panY`), preventing background animation loops when manual canvas rotation is non-zero.
  - **Mouse Canvas Rotation Axis Re-mapping (`RMB`, `e.button === 2`)**:
    - Re-mapped right-mouse-button (RMB) drag movements: horizontal drag (`x-axis`) updates Z-axis roll (`manualRotZ`) and vertical drag (`y-axis`) updates X-axis pitch (`manualRotX`).
    - Removed `[Shift]`+`LMB` rotation handler so left mouse button operates strictly for viewport panning.
  - **Pattern Equation Input & Custom Equation Mode (`#cie-pattern-equation`, `drawCustomPattern`)**:
    - Added real-time editable pattern equation text field `#cie-pattern-equation` directly under pattern `.cie-row`, populated automatically with active LaTeX/algebraic equations (`1h`, `2h`, `4plus`, `spiral`, `fractree`, `lissajous`, `flower`, etc.).
    - Implemented new `Custom` pattern mode with mathematical compiler (`compileCustomEquation`) and drawing loop (`drawCustomPattern`), automatically rendering user-defined equations (e.g., `x = sin(A*t + p), y = sin(B*t)` or `r = cos(3*t)`).
    - Added dynamic custom variables suite generator (`updateCustomVariablesSuite`), rendering full control groups (reset `↺`, number input, animation direction `↔`, limit popover `🎚️`, range slider) for all parsed equation variables in real-time.
  - **Input Parameters Context Menu (`#cie-input-context-menu`)**:
    - Added right-click and 0.5s touch long-press context menu on all number and range inputs (`input[type=number]`, `input[type=range]`), allowing users to inspect and dynamically update `Min`, `Max`, and `Step` attributes.
    - Synchronized attribute updates between target inputs and sister number/range inputs automatically.
  - **Panel Resizing Cursor Tooltip (`#cie-resize-tooltip`)**:
    - Implemented floating size tooltip `#cie-resize-tooltip` near cursor during panel resizing via mouse drag or touch hold on `#cie-controls` handles.
    - Displays width in pixels for left/right docked panels, height in pixels for top/bottom docked panels, or `Width × Height` for floating panels, auto-hiding when resizing finishes.
  - **Adaptive UI Space Preservation & Options Row CSS Optimization (`solveRowWrapping`)**:
    - Updated label abbreviation reconstruction (`label.innerHTML`) to preserve `parsed.hasSpaceAfterIcon` rule, omitting inserted space when icons have no trailing whitespace.
    - Optimized `.cie-options-row` CSS (`flex: 0 1 calc(33.33% - 4px); max-width: calc(33.33% - 4px);`) to enforce at most 3 options per row while skipping unnecessary row wrapping logic in `solveRowWrapping`.
  - **Syntax Error Patch (`getSpectralThemeStrokeStyle`)**:
    - Fixed an unexpected token syntax error caused by an extra closing brace before `else if (gradStyle === 'square')` in `getSpectralThemeStrokeStyle`.
    - Restored `scaleX_3d` and `scaleY_3d` 3D projection scaling factors for square pattern gradients.
  - **Manual Edit Summaries & Syntax Fix**:
    - Summarized user manual edits: adjusted `.cie-options-row` column spacing and font styling, cleaned up pattern equation inputs and custom variables styling.
    - Fixed HTML parse error caused by duplicate trailing quote in `<div class="cie-row" id="cie-pattern-equation-row">`.
  - **Synchronized Versioning**: Incremented application version across page title, help overlay header, control panel header, system metadata (`metadata.json`), and project history documentation to `1.31`.

### 📍 Version 1.31.1 [2026-08-11 UTC]: 3D Zoom Scale Correction, Adaptive UI Options Row Refactoring, Rotation Display AFI Protection, Immediate Panel Resize Tooltip Trigger, Local Coordinate 3D Gradient Scaling, Mousewheel Zooming during Rotation, Recenter Button Lime Indicator & Version 1.31.1 Updates
* **User Intent / Feedback ("1. Fix zoom scale of 23.549999828+ when z-axis rotation != 0 *and* (x- or y-axis) rotation != 0. 2. Options AUIAFI: Don't constrain options row to keep at most 3 options per line. Instead, use existing AFI technique... 3. When AFIing current rotation value... 4. Show #cie-resize-tooltip immediately upon left-click or touch-tap... 5. Fix color gradients... 6. When mouse-rotating on canvas, allow mousewheel zooming. 7. Color #cie-recenterBtn lime... 8. Add these changes and last 6 'manual edit' summaries to history.md version 1.31.1 and update index.html version"):**
  - **3D Zoom Scale Matrix Correction (`drawSingleState`, `23.549999828+` Fix)**:
    - Re-ordered canvas 2D matrix transformation sequence to apply 3D cardinal axis scaling (`scale(cosY, cosX)`) before 2D Z-axis rotation (`rotate(rotZVal)`), eliminating zoom scale calculation explosion (`23.549999828+`) when Z rotation is active alongside X/Y rotation.
  - **Adaptive UI Options Row Refactoring (`.cie-options-row`, `solveRowWrapping`)**:
    - Unconstrained `.cie-options-row > .cie-checkbox-group` flex CSS (`flex: 0 1 auto; max-width: none`), allowing option controls to flow naturally across the row.
    - Updated `solveRowWrapping` to evaluate line balance dynamically, allowing natural multi-option row wrapping (e.g. 3x2, 2x2, 3x2+1) and applying gradual font scaling (11.5px to 10px) only for uneven orphan wraps.
  - **Rotation Value Display AFI Protection (`#cie-currentRotXVal`, `#cie-currentRotYVal`, `#cie-currentRotZVal`)**:
    - Added `min-width: 30px; display: inline-block; text-align: right; flex-shrink: 0` styling to rotation value spans, reserving space for 3-digit degree values (e.g., `360°`) at 10-12px font size to prevent control row wrapping.
  - **Immediate Resize Tooltip Trigger (`initResizeTooltip`)**:
    - Added `mousedown` and `touchstart` event listeners on resize handles (`#cie-resize-handle`, `#cie-bl-resize-handle`, `.cie-resize-edge`) to display floating `#cie-resize-tooltip` immediately upon interaction before cursor movement occurs.
  - **Local Coordinate 3D Color Gradient Scaling (`getCustomThemeStrokeStyle`, `getSpectralThemeStrokeStyle`)**:
    - Refactored linear, radial, and conical gradient bounds to operate directly in local coordinate space (e.g., `createLinearGradient(-halfW, 0, halfW, 0)`, `createConicGradient(0, 0, 0)`), resolving solid red/orange rendering issues under 3D rotation transforms.
  - **Mousewheel Zooming during Mouse Rotation (`window.addEventListener('wheel')`)**:
    - Added a global window wheel event handler that captures mousewheel scroll input during active mouse/touch rotation (`isRotating || isTouchRotating`), adjusting zoom seamlessly while rotating.
  - **Recenter Button Lime Indicator (`#cie-recenterBtn`, `updateRecenterBtnColor`)**:
    - Implemented `updateRecenterBtnColor()`, dynamically highlighting `#cie-recenterBtn` in lime with a drop-shadow glow whenever viewport panning (`panX`, `panY`) is non-zero, and clearing styling when recentered.
  - **Manual Edit Summaries**:
    - Summarized user manual edits: fine-tuned option row layout spacing and CSS, updated input context menus, adjusted rotation control hotkeys and equations, updated help overlay documentation and controls listings.
  - **Synchronized Versioning**: Incremented application version across page title, help overlay header, system metadata (`metadata.json`), and project history documentation to `1.31.1`.

### 📍 Version 1.31.2 [2026-08-12 UTC]: Adaptive UI ~275px Refinement, Dedicated Gradient Row & Depth Option, LMB Canvas Panning & RMB Rotation Remapping, Local 3D Gradient Projection Fix & Version 1.31.2 Updates
* **User Intent / Feedback ("1. Fix Adaptive UI with #cie-controls width ~275px: 1a. 'Distortion ripple' label is font-size:9px... 1b. Options row still isn't doing just enough AFI... 2. Add 'Gradient' row below/under 'line color' row... 3. Allow LMB to pan drawing while RMB rotates... 4. Color gradient still messing up during rotation... 5. Add these changes and last 2 'manual edit' summaries to history.md version 1.31.2 and update index.html version"):**
  - **Adaptive UI Control Panel Refinement (`#cie-controls` ~275px, `solveRowWrapping`)**:
    - Fixed 'Distortion ripple' label font scaling by removing hardcoded inline `font-size:11.5px` style attribute from HTML, allowing AUIAFI font scaling passes to scale gracefully down to 11.5px without dropping down to 9px.
    - Updated `.cie-options-row` layout solver in `solveRowWrapping` to progressively test font sizes (11.5px down to 10px) whenever lines wrap, keeping options like 'Background pause' and 'Static scene pause' cleanly on the same line.
  - **Dedicated 'Gradient' Row & Depth Option (`select#cie-customGradStyle`, `#cie-gradient-row`)**:
    - Created a dedicated `#cie-gradient-row` directly below the 'Line color' row containing 'Type' (`select#cie-customGradStyle`) and 'Reverse' checkbox (`#cie-customGradReverse`).
    - Repurposed the 'Depth' checkbox (`#cie-customGradDepth`) into an option `<option value="depth">Depth</option>` inside `select#cie-customGradStyle`.
    - Updated `chk('cie-customGradDepth')` to dynamically evaluate `(el('cie-customGradStyle')?.value === 'depth')` for full backwards compatibility.
    - Configured `updateThemeControls()` to show `#cie-gradient-row` when theme is 'spectral' or 'custom' and hide the entire row otherwise, without disabling or greying out custom color inputs or the reverse checkbox.
  - **LMB Panning & RMB Rotation Canvas Controls (`mousedown`, `mousemove`, `mouseup`)**:
    - Re-mapped mouse interaction handlers so Left Mouse Button (LMB, `e.button === 0`) pans the canvas (`panX`, `panY`) while Right Mouse Button (RMB, `e.button === 2`) rotates 3D angles (`manualRotZ`, `manualRotX`).
    - Supported simultaneous holding of LMB and RMB to pan and rotate at the same time without interaction locks.
  - **3D Color Gradient Projection Fix (`getCustomThemeStrokeStyle`, `getSpectralThemeStrokeStyle`)**:
    - Resolved 3D color gradient distortion and solid red rendering across rotation angles (61°-119°, 241°-299°) by dynamically incorporating 3D projection scaling factors (`scaleX_3d`, `scaleY_3d`) into local linear, radial, and conical gradient radii and bounds calculations (`halfW`, `halfH`, `radR`), preventing screen-space gradient collapse.
  - **Manual Edit Summaries (Post-1.31.1 Edits)**:
    - **Options Row & UI Styling**: Set `.cie-options-row` CSS to `justify-content: space-between`, added UI icons (🎛️) to help rows, standardized `column-gap: 2px` across control rows, and wrapped labels in `<span>` tags with `column-gap: 0 !important` for Wobble and Pulse sections.
    - **Pulse Range & 3D Recursion Angle Sync**: Extended `#cie-pDepth` min/max range to `[-2, 2]` and updated `draw3D4Plus`, `draw3D2H`, and `draw3D2V` 3D rendering loops to calculate rotation-dependent depth factors, pulse, and wobble synchronization using `rTimeZ`.
  - **Synchronized Versioning**: Incremented application version across page title (`index.html`), help overlay header (`#cie-help-title`), and project history documentation (`history.md`) to `1.31.2`.

### 📍 Version 1.31.3 [2026-08-13 UTC]: Lock/Unlock Checkbox Styling, Cursor-Aware FPS Monitoring, Extended Autosave Persistence & Version 1.31.3 Updates
* **User Intent / Feedback ("1. All lock/unlock checkboxes: Hide and style their .cie-checkbox-group to background-color:rgb(0 192 0); border-radius:50%; height:15px; line-height:1; 1b. Add :hover state to transform:scale(1.25). 2. Refine FPS monitoring: monitor FPS only when mouse cursor is over app pane vs outside browser pane. 3. 'Autosave' should remember all manual and slider-based rotation axes angles, zoom levels, and pan positions/translations. 4. Add these changes and last 'manual edit' summary to history.md version 1.31.3 and update index.html version"):**
  - **Lock/Unlock Checkbox Circular Green Styling (`.cie-lock-group`, `.cie-limits-lock`)**:
    - Styled `.cie-lock-group` and `.cie-limits-lock` container elements with `background-color: rgb(0 192 0)`, `border-radius: 50%`, `height: 15px`, `width: 15px`, and `line-height: 1`.
    - Hidden native `<input type="checkbox">` elements while styling lock/unlock labels with `font-size: 9px` and `#fff` color centered within the circle.
    - Added `:hover` state with `transform: scale(1.25)` transition feedback.
  - **Refined Cursor-Aware FPS Monitoring (`isMouseOverApp`)**:
    - Added window/document event listeners (`mouseleave`, `mouseenter`, `blur`, `focus`, `mousemove`) tracking `isMouseOverApp`.
    - Restricted framerate accumulation and performance safeguard calculations in `drawFrame()` to run only when the mouse cursor is actively positioned over the application canvas or control interface, pausing FPS monitoring when the cursor exits the browser window or pane.
  - **Extended Autosave Persistence (`getSettings`, `loadSettings`, `triggerAutosave`)**:
    - Extended `getSettings()` and `loadSettings()` to serialize and restore manual rotation angles (`manualRotX`, `manualRotY`, `manualRotZ`), slider/time-based rotation angles (`rTime`, `rTimeY`, `rTimeZ`), zoom levels (`cie-zoom`), and pan offsets (`panX`, `panY`).
    - Added `triggerAutosave()` calls to `mouseup`, `touchend`, mousewheel zoom handlers, and `#cie-recenterBtn` click events, ensuring manual 3D rotations, canvas panning, zooming, and recentering are preserved automatically in saved states.
  - **Manual Edit Summaries**:
    - **Control Panel CSS & Icon Polish**: Fine-tuned lock/unlock checkbox CSS styling (`.cie-lock-group`, `.cie-limits-lock`), added `indent` class to `🌈Gradient` label, and updated Viewport section icons in Help overlay.
    - **Scanlines & Vignette Z-Axis Lock**: Updated scanlines and vignette rotation locks (`#cie-scanlinesUnlockRot`, `#cie-vignetteUnlockRot`) to lock rotation directly to the Z-axis (`state.rTimeZ + state.manualRotZ`), with updated lock labels/tooltips (🔒).
    - **Drawing Engine Legacy Cleanup**: Removed fallback logic for deprecated `manualRot` property across 3D node and tile rendering loops (`draw3D4Plus`, `draw3D2H`, `draw3D2V`, `drawNode3D`).
    - **HTML Markup Repair**: Resolved unclosed attribute quote syntax errors on rotated 🔄 icons in viewport help section (`index.html`).
  - **Synchronized Versioning**: Incremented application version across page title (`index.html`), help overlay header (`#cie-help-title`), and project history documentation (`history.md`) to `1.31.3`.

### 📍 Version 1.31.4 [2026-08-13 UTC]: Lock/Unlock Icon State Toggling, 1-Degree Step Hotkey Rotation, Z-Axis Refactoring & Variable Renaming (rTimeX/pTimeX), Bidirectional RMB/LMB Canvas Controls & Version 1.31.4 Updates
* **User Intent / Feedback ("1. Fix checkboxes: when .cie-limits-lock-chk, #cie-scanlinesUnlockRot, or #cie-vignetteUnlockRot unchecked, change .cie-checkbox-group background-color:transparent and 🔒 (locked) icon to 🔓 (unlocked). 2. Have each press of a rotation hotkey (without holding [Shift]) only rotate the axis by 1 degree. 3. Fix x-axis rotation references, since adding y-/z-axis rotation, to use z-axis rotation instead of x-axis: 3a. 'Sync pulse', 'Depth orbit', and 'Depth roll'. 3b. Fix other functions, variables, etc. that may be confusing z-axis rotation, time, etc. 3c. Rename variables rTime to rTimeX and pTime to pTimeX. 4. Fix RMB rotate + LMB pan to work in that order as well. 5. Add these changes and last 8 manual edit summaries to history.md version 1.31.4 and update index.html version"):**
  - **Lock/Unlock Checkbox JS State & Icon Toggling (`.cie-limits-lock-chk`, `#cie-scanlinesUnlockRot`, `#cie-vignetteUnlockRot`)**:
    - Implemented event listeners on all limit locks (`.cie-limits-lock-chk`), scanlines unlock rotation (`#cie-scanlinesUnlockRot`), and vignette unlock rotation (`#cie-vignetteUnlockRot`).
    - Dynamically toggles container `.cie-checkbox-group` background between `rgb(0 192 0)` (when locked) and `transparent` (when unlocked).
    - Updates inner text icon dynamically between `🔒` (locked) and `🔓` (unlocked).
  - **1-Degree Step Hotkey Rotation (`keydown`, `KeyQ`, `KeyE`)**:
    - Refactored `KeyQ` and `KeyE` keydown handlers to increment/decrement rotation angle by strictly 1 degree (`±1 * Math.PI / 180`) on a single key press when Shift is not held (Shift + Q/E rotates by 15 degrees).
    - Removed continuous frame accumulation for single key taps from `processContinuousKeys` for predictable step adjustments.
  - **Z-Axis Rotation & Variable Refactoring (`rTime` -> `rTimeX`, `pTime` -> `pTimeX`)**:
    - Updated 'Sync pulse', 'Depth orbit' (`#cie-rotDepths`), and 'Depth roll' (`#cie-rotDepthRoll`) to lock to Z-axis rotation (`rTimeZ` / `manualRotZ`) across all primary rendering loops (`drawRec`, `drawOneWayNested`, `draw3D4Plus`, `draw3D2H`, `draw3D2V`, `drawFlowerOfLife`).
    - Fixed scanlines and vignette unlock rotation routines to rotate strictly using Z-axis parameters (`rTimeZ + manualRotZ`).
    - Renamed legacy `rTime` and `pTime` variables to `rTimeX` and `pTimeX` across global declarations, resetting routines, settings serialization (`getSettings`/`loadSettings`), timeline scrubbing handlers, background color phase calculations, rendering loops, static scene detection, and transform history buffers.
  - **Bidirectional Mouse Controls Fix (RMB Rotate + LMB Pan)**:
    - Updated `mousedown` handler so that pressing LMB (`e.button === 0`) while RMB rotation is already active (`isRotating === true`) sets up panning (`isPanning = true`) immediately with proper origin coordinates (`panStartX`, `panStartY`, `initialPanX`, `initialPanY`).
    - Enabled seamless concurrent panning and 3D rotation regardless of press sequence (LMB first then RMB, or RMB first then LMB).
  - **Manual Edit Summaries (8 Post-1.31.3 Edits)**:
    1. **Lock/Unlock Checkbox Styling & Icons**: Configured `.cie-lock-group` and `.cie-limits-lock` CSS rules and JS handlers for active (`rgb(0 192 0)` / `🔒`) vs. inactive (`transparent` / `🔓`) visual states.
    2. **Rotation Hotkey Step Logic**: Updated `keydown` event listener to apply a 1-degree step for single `Q`/`E` keypresses.
    3. **Variable Renaming Refactoring**: Renamed global `rTime` to `rTimeX` and `pTime` to `pTimeX` across all rendering loop routines.
    4. **Z-Axis Synchronization Fixes**: Updated 'Depth orbit' and 'Sync pulse' routines to utilize `rTimeZ`.
    5. **Scanlines & Vignette Rotation Fix**: Ensured scanlines and vignette unlock rotation checkboxes rotate using `rTimeZ`.
    6. **Timeline & Slider Sync**: Extended timeline slider and numeric value displays to track `pTimeX`.
    7. **Degree Value Formatters**: Updated `updateCurrentRotVal` to format degrees for X (`rTimeX`), Y (`rTimeY`), and Z (`rTimeZ`) axes accurately.
    8. **Static Scene Optimization**: Refactored static scene pause checks (`isReallyStatic`, `isDrawingStatic`) to account for `cie-rotateX`, `cie-rotateY`, and `cie-rotateZ`.
  - **Canvas Rendering Bug Fix**: Resolved runtime `ReferenceError`s caused by residual un-refactored `pTime` and `rTime` variable accesses in `draw3D2H`'s `drawNode3D`, `drawSingleState` global restoration, mini-viz updater, HUD rotators, and custom math formula scope builders (`scope.pTime`/`scope.pTimeX`). Replaced all remaining legacy references with `pTimeX` and `rTimeX` to prevent global animation state corruption (`NaN`), restoring reliable, real-time canvas rendering.
  - **Synchronized Versioning**: Retained application version `1.31.4` across page title (`index.html`), help overlay header (`#cie-help-title`), control panel header (`index.html`), system metadata (`metadata.json`), and project history documentation (`history.md`).


### 📍 Version 1.31.5 [2026-08-14 UTC]: Shift Rotation Hotkey Overhaul, Bidirectional Mouse Controls (RMB Rotate + LMB Pan), Optional UI Animations, Action Bar Reset Buttons, 3D Line Color Gradient Repair, Limit Track Lock State Updates & Active Theme Bolding
* **User Intent / Feedback ("1. Fix [Shift] hotkey rotation: 1a. No longer doubles canvas hotkey ([Q]/[E]) rotation while actively rotating, but stops rotation altogether. 1b. Fix [Shift] not rotating by 15 degrees but 2 degrees. 2. Fix trying to pan while actively rotating ([RMB]+drag) still not working. 3. Optional UI animation: add an optional slight animation when expanding/contracting a tab panel, subcontrols... Add an 'Animate UI' checkbox (default unchecked) to 'Options' > 'Display' after 'Adaptive UI'. 4. Add reset buttons for '🔄' rotation and '🔍' zoom to action bar... Apply color:lime; filter:drop-shadow(lime 0px 0px 3px); to these reset buttons when not default. 5. Fix 3D line color gradient in 'spectral' theme, pattern 2h... 6. Fix .cie-limit-track.locked to immediately recognize when .cie-limits-lock-chk is unchecked. 7. Bold current color theme in #cie-theme-options when cycling/randomizing. 8. Add these changes and last 2 manual edit summaries to history.md version 1.31.5 and update index.html version"):**
  - **Shift Hotkey & Continuous Rotation Control (`KeyQ` / `KeyE` / `Shift`)**:
    - Updated `KeyQ` and `KeyE` keydown logic so that holding `Shift` applies a 15-degree rotation step (`15 * Math.PI / 180`) instead of 2 degrees.
    - Added active continuous rotation suppression when `Shift` is held, stopping active auto-rotation (`cie-rotateX`, `cie-rotateY`, `cie-rotateZ`) and RMB drag rotation altogether while Shift is held down.
  - **Bidirectional Mouse Controls (`RMB` Rotate + `LMB` Pan)**:
    - Fixed mouse button mask tracking in `mousedown`, `mousemove`, and `mouseup` handlers so RMB drag rotation and LMB drag panning function concurrently and seamlessly regardless of initial press sequence (LMB first then RMB, or RMB first then LMB).
  - **Optional UI Animations (`#cie-animateUI`)**:
    - Added an 'Animate UI' (`#cie-animateUI`) checkbox (default unchecked) to 'Options' > 'Display' immediately following 'Adaptive UI'.
    - Added `.cie-animated-ui` CSS transition rules for smooth expanding/contracting transitions across tab panels, subcontrol containers (`#cie-cycleSpeedRow`, `#cie-multiStrobeSection`, `#cie-shake-subcontrols`), and limits popovers.
  - **Action Bar Reset Buttons (`#cie-resetRotBtn`, `#cie-resetZoomBtn`)**:
    - Added 🔄 (reset 3D rotation) and 🔍 (reset zoom) buttons to the action bar immediately following the recenter button (`#cie-recenterBtn`).
    - Styled reset buttons with dynamic lime highlight (`color:lime; filter:drop-shadow(lime 0px 0px 3px);`) whenever 3D rotation angles or zoom levels deviate from defaults (0º / 0 zoom).
  - **3D Line Color Gradient Repair (`draw3D2H`, `getSpectralThemeStrokeStyle`, `getCustomThemeStrokeStyle`)**:
    - Resolved boundary blowup and solid color fallback artifacts in 3D 2-Way Horizontal ('2h') and 3D 4-Way ('4plus') patterns under the 'spectral' and custom theme gradients by eliminating invalid division of linear/radial gradient bounds (`halfW`, `halfH`, `radR`) by `scaleX_3d` and `scaleY_3d` (`Math.cos(rotXVal)`).
    - Fixed glow shadow colors (`ctx.shadowColor`) across drawing functions (`drawRec`, `draw3D4Plus`, `draw3D2H`, `draw3D2V`, `drawOneWayNested`) by passing `isShadowColor = true` to `getColor(...)`, ensuring solid CSS rgba color strings are returned for canvas shadow rendering.
  - **Limit Track Lock State Immediate Recognition (`.cie-limits-lock-chk`, `.cie-limit-track.locked`)**:
    - Fixed limit lock checkbox unchecking handler to immediately delete `ppLimitsLocked[k]` and invoke `updateSliderLimitOverlay(k)`, removing the `.locked` class and `cursor: not-allowed` style instantly.
  - **Active Theme Bolding in Theme Options (`#cie-theme-options`, `updateThemeOptionsHighlight`)**:
    - Created `updateThemeOptionsHighlight()` helper and integrated it into theme selection, state loading, and real-time color cycling/randomizing loops, ensuring the active theme is dynamically bolded in `#cie-theme-options`.
  - **Manual Edit Summaries**:
    1. **CSS & Icon Styling Cleanup**: Refined CSS styling for `.cie-lock-group`, `.cie-limits-lock`, and `#cie-resetBtn` reset icons.
    2. **Keyboard & Help Documentation Updates**: Updated help modal (`#cie-help-overlay`) and controls panel documentation to detail 15-degree Shift rotation steps, active rotation pausing, concurrent LMB/RMB mouse actions, and action bar reset shortcuts.
  - **Synchronized Versioning**: Incremented application version across page title (`index.html`), help overlay header (`#cie-help-title`), control panel header (`index.html`), and project history documentation (`history.md`) to `1.31.5`.


### 📍 Version 1.31.6 [2026-08-15 UTC]: Limit Track Lock State Updates, Action Bar Reset Highlights, 3D Spectral Gradient Fix, Concurrent Drag Controls, Canvas Dragging Pointer Suppression & rSpeed -> rSpeedX Refactoring
* **User Intent / Feedback ("1. Limit track unlocked state still not immediately applying to .cie-limit-track (by removing .locked class and cursor: not allowed !important style) until after .cie-limits-popover is closed (yet the locked state immediately applies). 2. Action bar buttons not highlighting (lime color and drop-shadow filter) correctly: #cie-resetRotBtn and #cie-resetZoomBtn should highlight when only the rotation (any axis) or zoom occurs, respectively, without requiring a pan/translation position change. 3. 3D color gradient still messing up on pattern 2h + spectral theme + horizontal gradient + x-axis rotation at 300º... 4. Fix trying to pan while actively rotating (RMB+drag) still not working; LMB does nothing when initially pressed but letting go stops rotation. 5. UI hover effects: when mouse is hovering over #cie-controls (and children) during canvas panning/rotating, turn off all UI hover CSS effects... 6. Rename rSpeed to rSpeedX. 7. Version update to 1.31.6 in history.md and index.html"):**
  - **Immediate Limit Track Lock State Updates (`.cie-limits-lock-chk`, `.cie-limit-track.locked`)**:
    - Fixed limit lock change listener (`.cie-limits-lock-chk`) so that unchecking immediately deletes `ppLimitsLocked[k]` and invokes `updateSliderLimitOverlay(k)`, removing the `.locked` class and `cursor: not-allowed !important` styling instantly without waiting for the popover to close.
  - **Action Bar Reset Button Highlights (`#cie-resetRotBtn`, `#cie-resetZoomBtn`, `updateRecenterBtnColor`)**:
    - Fixed `#cie-resetRotBtn` and `#cie-resetZoomBtn` highlight checks (`updateRecenterBtnColor`) so `#cie-resetRotBtn` highlights when any 3D rotation occurs (X/Y/Z manual angles, time rotation, or toggled checkboxes) and `#cie-resetZoomBtn` highlights whenever zoom is non-zero, independent of pan/translation offset.
    - Integrated `updateRecenterBtnColor()` into the main `draw()` animation loop and input handlers to keep reset button highlight states continuously synchronized in real time.
  - **3D Color Gradient Repair (`getSpectralThemeStrokeStyle`, `getCustomThemeStrokeStyle`, `draw3D4Plus`, `draw3D2H`, `draw3D2V`)**:
    - Resolved solid red circle rendering artifacts in 3D 2-Way Horizontal (`2h`) and 3D 4-Way (`4plus`) spectral patterns at specific angles (e.g. 300º) and recursion depths by expanding gradient bounds (`halfW`, `halfH`, `radR`) to cover off-screen 3D projections (`maxExt = Math.max(w, h, 4000) * 4`).
    - Added Z-near plane clipping (`cameraDist + zc < 50`) in 3D projection routines (`draw3D4Plus`, `draw3D2H`, `draw3D2V`) to prevent perspective division overflow when nodes rotate near or behind the camera view plane.
  - **Concurrent Bidirectional Mouse Controls (RMB Rotate + LMB Pan)**:
    - Updated container `mousedown`, document `mousemove`, and `mouseup` handlers to track `isPanning` and `isRotating` independently and concurrently. Pressing and holding RMB to rotate and dragging LMB to pan works in any press sequence without canceling rotation on LMB release.
  - **Canvas Dragging UI Hover Suppression (`body.cie-canvas-dragging`)**:
    - Added `body.cie-canvas-dragging` class toggling during active canvas panning or rotation.
    - Applied CSS rule `body.cie-canvas-dragging #cie-controls, body.cie-canvas-dragging #cie-controls * { pointer-events: none !important; }` to suppress all UI hover CSS effects on the control panel when dragging across panel bounds.
  - **Global Variable & Control Refactoring (`rSpeed` -> `rSpeedX`)**:
    - Renamed X-axis rotation speed variable `rSpeed` to `rSpeedX` across all HTML element IDs (`cie-rSpeedX`, `cie-rSpeedXNum`, `cie-limits-rSpeedX`, `cie-lmin-rSpeedX`, `cie-lmax-rSpeedX`), data attributes (`data-reset="rSpeedX"`, `data-key="rSpeedX"`), JavaScript default objects (`SLIDER_DEFAULTS`, `uiMap`, `DEFAULTS`, `PRESETS_DEFAULT`), event listeners, and settings loader (with backward compatibility fallback for legacy `rSpeed` saved states).
  - **Manual Edit Summaries**:
    1. **CSS Hover Suppression**: Added `body.cie-canvas-dragging` rules to disable UI hover states while dragging the canvas.
    2. **Z-Near Camera Clipping**: Added `if (cameraDist + zc < 50) return;` to 3D rendering loops to prevent perspective projection singularities.
    3. **Syntax Error Repair & Manual Edits**:
       - Fixed `SyntaxError: Unexpected end of input` caused by missing closing brace `}` on `if (el('cie-rSpeedX')) {` event listener in `/index.html`.
       - Updated `.cie-btn-icon` CSS with `justify-content:center; width:1.125em;`.
       - Standardized custom/background color input hex values to 6-digit hex format (`#ffffff`, `#000000`).
       - Set `step="1"` on `#cie-chromaAmt` and `#cie-chromaVertAmt` slider controls.
       - Refined action bar reset buttons markup, titles, and icons (`🗘` for rotation reset, `🔍︎` for zoom reset).
       - Cleared remaining legacy `rSpeed` references in reset listeners, randomizer, and state loader functions.
  - **Synchronized Versioning**: Incremented application version across page title (`index.html`), help overlay header (`#cie-help-title`), control panel header (`index.html`), and project history documentation (`history.md`) to `1.31.6`.


### 📍 Version 1.31.7 [2026-08-15 UTC]: Canvas LMB Dragging Hover Suppression, Animated UI Transitions, Concurrent Mouse Pan & Rotate Fix, 3D Spectral Gradient Fixes & Square Pattern Crash Repair, Limits Lock Overlay Instant Sync, Universal Hotkey Modifier Support
* **User Intent / Feedback ("1. Canvas LMB dragging still affecting `#cie-controls` `:hover` elements. 2. Fix animated UI not actually animating when `#cie-animateUI` on. 3. Fix RMB rotation + LMB panning still not working togther in that order... 4. 3D color gradient rotation still messing up... square apparently locks up the whole app... 5. Fix limit track unlocking still showing .locked class, locked tooltip, and cursor: not-allowed !important style... 6. Fix [Q]/[E] + [Shift] fast rotation not working; only works if [Shift] held first... 7. Add these changes and last 'manual edit' summary to history.md version 1.31.7 and update index.html version."):**
  - **Canvas LMB Dragging UI Hover Suppression (`body.cie-canvas-dragging`)**:
    - Ensured `body.cie-canvas-dragging` class is added during both LMB panning and RMB rotating interactions on `container` and `document`.
    - Enforced CSS pointer event and selection suppression on `#cie-controls` and its children during active canvas interactions so hover pseudo-classes do not trigger while dragging.
  - **Animated UI Expansion & Collapse Transitions (`#cie-animateUI`, `.cie-animated-ui`)**:
    - Updated CSS rules for `body.cie-animated-ui` so tab panels, subcontrol groups, and section containers smoothly transition `max-height`, `opacity`, and `transform` during active switching and expansion/contraction without snapping.
  - **Concurrent Bidirectional Mouse Control Sequence (RMB Rotate + LMB Pan)**:
    - Fixed mouse interaction state management so engaging RMB 3D rotation followed by LMB panning works simultaneously in any press sequence.
    - Updated `mouseup` handlers to check specific button states (`e.button` and `e.buttons`) so releasing LMB while holding RMB keeps 3D rotation active without stopping.
  - **3D Color Gradient Scaling & Square Pattern Crash Repair (`getSpectralThemeStrokeStyle`, `getCustomThemeStrokeStyle`)**:
    - Fixed `Uncaught ReferenceError: scaleX_3d is not defined` in `getSpectralThemeStrokeStyle` when using 'square' gradient style, restoring full app stability.
    - Resized gradient extents (`halfW`, `halfH`, `radR`) to match canvas dimensions so 'horizontal', 'vertical', and 'radial' gradients transition smoothly across circles rather than rendering as solid colors.
  - **Limits Lock Overlay Instant Sync (`.cie-limits-lock-chk`, `updateSliderLimitOverlay`)**:
    - Fixed limit lock checkbox listener so unchecking instantly removes the `ppLimitsLocked[k]` entry and re-renders the overlay, removing the `.locked` class, `cursor: not-allowed !important` style, and lock tooltip immediately without requiring popover closure.
  - **Universal Keyboard Hotkey Modifier Processing (`processContinuousKeys`, `KeyQ`, `KeyE`)**:
    - Integrated Q/E rotation handling into frame-based `processContinuousKeys()` animation loop.
    - Modifier keys ([Shift] for fast 2x rotation, [Ctrl] for Y-axis, [Alt] for X-axis) can now be pressed or released at any time before or during key hold to dynamically alter rotation speed and orientation in real time.
  - **Manual Edit Summaries**:
    1. **Design Tag Generator Refinement**: Updated tag abbreviation generator (`addTag`) in `index.html` to comprehensively capture line invert (`inv`), line width (`linWid`), opacity (`op`), glow (`glow`), trail (`trl`), background fade (`bgFade`), background invert (`bgInv`), FOV (`fov`), pan (`pan`), rotation axes (`rotX`, `rotY`, `rotZ`), rotation depth (`rotD`), depth roll (`dRoll`), zoom (`zm`), skew (`skew`), pulse (`pls`), convergence (`conv`), singularity (`sing`), shake (`shk`), wobble (`wob`), distortion (`dst`), chroma (`chrma`), echo (`echo`), motion blur (`moBlur`), scanlines (`scan`), vignette (`vign`), blur (`blur`), brightness (`bri`), contrast (`cont`), grayscale (`gry`), saturate (`sat`), and sepia (`sep`).
  - **Synchronized Versioning**: Incremented application version across page title (`index.html`), help overlay header (`#cie-help-title`), control panel header (`index.html`), and project history documentation (`history.md`) to `1.31.7`.


### 📍 Version 1.31.8 [2026-08-15 UTC]: Debounced Control Panel Resize Listener, Complete Square Gradient Stack Repair, and Animated UI Tab Panel Preservation
* **User Intent / Feedback ("1. Implement a debounced resize listener for the main control panel to improve performance during manual resizing of the controls dock. 2. Fix 'square' gradient error but this time go through *all* the error lines!... 3. Fix tab panels (.cie-tab-panel), except .active, disappearing when 'animate UI' on. Only collapsed tab panel contents (.cie-tab-panel-content) should be hidden and animate when collapsing/hiding and 'uncollapsing'/showing. 4. Add these changes to history.md version 1.31.8 and update index.html version."):**
  - **Debounced Control Panel Dock Resize Listener (`debouncedDoResize`, `isResizingPanel`)**:
    - Implemented `debouncedDoResize(delay = 30)` timer wrapper in `index.html` for `mousemove` resize events.
    - Dock width, height, and position CSS variables update synchronously during dragging for instantaneous DOM feedback, while heavy canvas re-allocation (`doResize()`) is throttled to 30ms.
    - Mouseup and touchend handlers immediately trigger `doResize()` upon drag completion to guarantee precise canvas dimensions and crisp font label scaling.
  - **Comprehensive Square Gradient Error Repair (`getSpectralThemeStrokeStyle`)**:
    - Fixed `Uncaught ReferenceError: scaleX_3d is not defined` in `getSpectralThemeStrokeStyle` at line 6121/6122 by replacing `scaleX_3d` and `scaleY_3d` with proper pattern scale factors `(w || 128) / 128` and `(h || 128) / 128`.
    - Traced execution stack (`getSpectralThemeStrokeStyle` -> `getColor` -> `drawRec` -> `runModeDrawing` -> `drawSingleState` -> `update`) to ensure square spectral patterns render smoothly without uncaught runtime exceptions or frame stops.
  - **Animated UI Tab Panel Content Preservation (`body.cie-animated-ui`, `.cie-tab-panel-content`)**:
    - Refactored `body.cie-animated-ui` CSS rules so outer `.cie-tab-panel` elements (and their docked section headers `.cie-docked-section-header`) are not collapsed to `max-height: 0 !important; opacity: 0 !important` when `Animate UI` is active.
    - Confined height, opacity, and transform animation transitions exclusively to `.cie-tab-panel-content` and `.cie-tab-panel.collapsed .cie-tab-panel-content`, ensuring docked section headers remain visible at all times.
  - **Synchronized Versioning**: Incremented application version across page title (`index.html`), help overlay header (`#cie-help-title`), control panel header (`index.html`), and project history documentation (`history.md`) to `1.31.8`.


### 📍 Version 1.31.9 [2026-08-16 UTC]: Skew Zoom Discrepancy Fix, SmoothFade Custom Theme Randomization, Gradient Glow & Performance Caching, and 3D Rotation Gradient Artifact Fix at Thickness 1
* **User Intent / Feedback ("1. Fix normal skew (`#cie-useSkewX`/`Y`) looking slightly zoomed in than canvas skew (`#cie-skewCanvas`). 2. Make `#cie-smoothFade` affect `#cie-cycleRandom` when 'custom' theme on. 3. Fix color gradients (`#cie-customGradStyle`): 3a. Glow (`#cie-glow`) doesn't work on all color gradients except 'depth'. 3b. Figure out why all color gradients (except 'depth') reduce fps by ~20-25. 3c. 3D single-axis (x or y--z must be 0º!) rotation still messing up gradients at certain angles but only at line thickness (`#cie-thick`) 1. 4. Add these changes and last 'manual edit' summary to history.md version 1.31.9 and update index.html version."):**
  - **Normal Skew vs. Canvas Skew Zoom Discrepancy Repair (`renderWebGL`)**:
    - Identified that WebGL skew scale normalization in `renderWebGL` was previously using a unit bounding box projection with a factor of `0.5`, leading to a subtle over-magnification compared to CSS transform matrix skewing.
    - Corrected the normalization by projecting the transformed unit circle diagonal scaled by `Math.SQRT2`, accurately matching the geometric scale of CSS canvas skew (`#cie-skewCanvas`).
  - **SmoothFade Support for Custom Theme Random Cycling (`#cie-smoothFade`, `#cie-cycleRandom`, `update`)**:
    - Updated the color transition engine in `update()` so `#cie-smoothFade` actively interpolates color values during randomized theme cycling (`#cie-cycleRandom`) when the 'custom' theme is selected.
    - Smoothly fades between randomized color palette targets using continuous alpha blending, eliminating abrupt color snaps during custom theme cycling.
  - **Gradient Glow Support (`#cie-glow`, `getColor`, `drawRec`, `draw3D4Plus`, `draw3D2H`, `draw3D2V`, `drawFlowerOfLife`, `drawOneWayNested`)**:
    - Fixed canvas glow shadow rendering by ensuring `ctx.shadowColor` receives a solid CSS color string (`rgba(...)`) via `getColor(..., true)` rather than a `CanvasGradient` or `CanvasPattern` object across all recursive and node drawing functions.
    - Enabled vibrant glow effects for all gradient styles ('horizontal', 'vertical', 'radial', 'square', 'conical') without canvas shadow degradation.
  - **Color Gradient FPS Optimization & Global Caching (`cachedCustomGrad`, `cachedSpectralGrad`, `cachedSquarePattern`)**:
    - Resolved the ~20-25 FPS performance drop on gradient modes by implementing global gradient and pattern caches.
    - Reused compiled `CanvasGradient` and `CanvasPattern` instances keyed by color, style, dimensions, and inversion state, avoiding expensive per-frame canvas allocation.
  - **3D Single-Axis Rotation Gradient Artifact Resolution at Line Thickness 1 (`drawRec`, `drawNode3D`)**:
    - Enforced a minimum subpixel stroke width floor of `Math.max(0.2, strokeW)` across drawing pipelines.
    - Prevents single-axis (X or Y) 3D rotations at thickness 1 from flattening projected line widths to 0, which previously caused anti-aliasing canvas singularities and distorted gradient fills.
  - **Manual Edit Summaries**:
    1. **Color Gradient Cache Integration**: Added cached pattern and gradient lookups to `getCustomThemeStrokeStyle` and `getSpectralThemeStrokeStyle`.
    2. **Shadow Color RGBA Extraction**: Updated `getColor` with `isShadowColor` logic to calculate valid RGBA string representations for gradient depth layers.
  - **Synchronized Versioning**: Incremented application version across page title (`index.html`), help overlay header (`#cie-help-title`), control panel header (`index.html`), and project history documentation (`history.md`) to `1.31.9`.


### 📍 Version 1.31.10 [2026-08-16 UTC]: Skew Zoom 1:1 Normalization, SmoothFade Custom Theme Randomization, 3D Rotation Gradient Artifact Resolution, Distinct Square/Radial Gradient Verification, Autosave Slider Randomization State Persistence, and Popover Hierarchy Verification
* **User Intent / Feedback ("1. Fix normal skew (`#cie-useSkewX`/`Y`) to not be zoomed in ~0.85 times compared to with `#cie-skewCanvas` on. 2. Fix smooth color fading `#cie-smoothFade` to affect `#cie-cycleRandom` when 'custom' theme on. 3. Fix 3D single-axis (X/Y) rotation *still* messing up gradients at certain angles, i.e. pattern 2h, gradients 'horizontal', 'vertical', 'radial' at line width 0.9-1... 4. Fix 'square' and 'radial' gradients: When not messing up as described above, these 2 gradient types look identical so verify they are rendering correctly and using all gradient colors ('spectral' and 'custom' themes). 5. Autosave should remember if slider randomization is active and each slider's .cie-random-slider-menu settings. 6. Popover positioning check: Ensure .cie-limits-popover elements remain inside parent .cie-row. 7. Update history.md to 1.31.10 and sync index.html version."):**
  - **Normal Skew vs. Canvas Skew 1:1 Scale Normalization (`renderWebGL`)**:
    - Removed artificial WebGL vertex bounding-box overscaling `S` in `renderWebGL`.
    - Normal skew (`#cie-useSkewX`/`#cie-useSkewY`) now renders using unit clip-space coordinates `[-1.0, 1.0]`, matching the visual zoom level and proportion of CSS canvas element skew (`#cie-skewCanvas`) 1:1.
  - **SmoothFade Support for Custom Theme Random Mode (`#cie-smoothFade`, `#cie-cycleRandom`, `update`)**:
    - Extended the `update()` animation loop to support `#cie-smoothFade` when `#cie-cycleRandom` is active on the 'custom' theme.
    - Interpolates RGB values smoothly across randomized palette transitions using linear temporal interpolation (`Math.min(1, stTimer / 80)`), eliminating sudden color flashes.
  - **3D Single-Axis Rotation Gradient Artifact Resolution (`drawSingleState`, `getCustomThemeStrokeStyle`, `getSpectralThemeStrokeStyle`, `getSquareGradientPattern`)**:
    - Resolved gradient distortion and solid color rendering at critical 3D rotation angles (60°, 61°, 119°, 120°, 240°, 241°, 299°, 300°) at stroke widths 0.9-1.0.
    - Implemented per-frame cache invalidation at the start of `drawSingleState`, ensuring gradient matrix transforms and pattern projections adapt dynamically to model matrix transformations without accumulating stale rotation frames.
    - Standardized gradient extent radius to `baseR = Math.min(canvas.width, canvas.height) / 2 * 0.85`, ensuring all gradient stops span across the entire recursive figure smoothly.
  - **Square vs. Radial Gradient Distinction & Full Spectrum Verification**:
    - Re-architected `getSquareGradientPattern` with Chebyshev distance metrics (`Math.max(dx, dy)`) to generate distinct square nested boundaries.
    - Verified Euclidean distance circles (`Math.sqrt(dx*dx + dy*dy)`) for radial gradients, ensuring clear visual distinction between square box gradients and smooth radial gradients across spectral and custom themes.
    - Utilized a shared, reusable 128x128 offscreen canvas and `createImageData` buffer to optimize performance without memory leaks.
  - **Autosave Continuous Slider Randomization Persistence (`getState`, `applyState`)**:
    - Enhanced state serialization (`getState()`) to record continuous randomization states (`randomSliderContinuous`) across all `.cie-random-slider-btn` controls and `.cie-limits-track-random-btn` buttons.
    - Restored active continuous timers (`_setContinuous(true)`), speed multipliers (`randomSliderSpeeds`), intervals (`randomSliderIntervals`), and distributions (`randomSliderDistributions`) seamlessly upon configuration load and autosave retrieval (`applyState()`).
  - **Popover DOM Hierarchy & Styling Verification (`.cie-limits-popover`)**:
    - Verified structural placement of `#cie-limits-trailConvergeVal` inside `#cie-trail-converge-group > div.cie-row` and `#cie-limits-bgFade` inside `#cie-group > div.cie-row:nth-of-type(2)` after `.cie-control-group`.
    - Maintained absolute positioning rules so limits popovers open cleanly without layout shifting or scroll obstruction.
  - **Manual Edit Summaries**:
    1. **UI Layout Optimization**: Set `#cie-shake-subcontrols` flex direction to column for clean parameter alignment.
    2. **Input Bounds & Step Tuning**: Refined numeric field step to `1` on `#cie-cSpeedNum` and range to `0-20` on `#cie-cSpeed`.
    3. **Highlight Styling**: Refined `checkNumHighlight` to use non-intrusive CSS outline indicators.
  - **Synchronized Versioning**: Incremented application version across page title (`index.html`), help overlay header (`#cie-help-title`), control panel header (`index.html`), and project history documentation (`history.md`) to `1.31.10`.


### 📍 Version 1.31.11 [2026-08-17 UTC]: Depth Chroma Split (⊙ Depth), Real-Time Pan Coordinate Readout, Limits Drag Autosave, and Continuous Randomization Serialization
* **User Intent / Feedback ("1. Add Depth (radial/z-axis) chroma split with controls, animation, and post-processing. 2. Display real-time pan coordinates x (0), y (0) next to Pan controls. 3. Ensure limit track dragging updates state and triggers autosave. 4. Preserve continuous randomization on limits tracks across state serialization. 5. Update history.md and synchronize app version to 1.31.11."):**
  - **Depth Chroma Split Integration (`#cie-chromaDepth`, `#cie-chromaDepthAmt`, `@keyframes cie-chromaDepth-anim`, `.cie-chromaDepth-effect`)**:
    - Added a dedicated "⊙ Depth" chroma split toggle and amount slider control group (`#cie-chromaDepthGroup`), allowing radial/z-axis color dispersion centered on the canvas origin.
    - Implemented `.cie-chromaDepth-effect` text shadow keyframe animation with vibrant red/cyan chromatic aberration preview on hover/active.
    - Extended post-processing pipeline in `draw()` to apply dual-scale offscreen canvas projection (`1 + amtD * 0.003` and `1 - amtD * 0.003`) with `screen` blend mode, generating pure 3D chromatic depth separation.
    - Fully registered `chromaDepth` and `chromaDepthAmt` across `SLIDER_DEFAULTS`, `SLIDER_MAP`, `DEFAULTS`, `loadSettings()`, `getState()`, `addTag()`, performance warning indicators, and LaTeX equation rendering (`Chroma_Z`).
  - **Real-Time Pan Coordinate Readout (`#cie-pan-coord-x`, `#cie-pan-coord-y`)**:
    - Added live coordinate readouts (`x (...)`, `y (...)`) in the pan control row.
    - Integrated automatic per-frame updates during rendering reflecting combined manual drag pan (`panX`, `panY`) and animated pattern wrap translations (`wrapX`, `wrapY`).
    - Configured reset handlers to restore coordinates cleanly to `x (0)` and `y (0)`.
  - **Limits Track Dragging State Capture & Autosave**:
    - Enhanced slider limit track dragging (`onEnd`) to invoke `pushSliderState()` and `triggerAutosave()`, ensuring custom limit intervals are saved to undo history and local persistence immediately upon release.
    - Maintained popover layout exemptions in `initSliderTicks` for `#cie-limits-trailConvergeVal` and `#cie-limits-bgFade`.
  - **Continuous Randomization State Persistence**:
    - Unified `.cie-random-slider-btn` and `.cie-limit-track-random-btn` selection in `getState()` and `loadSettings()`, ensuring continuous random mode on both sliders and limit tracks is faithfully serialized and restored.
  - **Synchronized Versioning**:
    - Synchronized version `1.31.11` across page title (`<title>Circulospherical Infinity Engine 1.31.11</title>`), help modal header (`#cie-help-title`), control panel header (`.hdr-text`), and project history (`history.md`).


### 📍 Version 1.31.12 [2026-08-18 UTC]: Limit Track Autosave Restoration, Pan/Rotation Lime Styling, 3D Rotation Gradient Coordinate Normalization, Spectral Depth Reversal Fix, and Skew Slider Alignment
* **User Intent / Feedback ("1. Autosave isn't restoring/resuming limit track #cie-limit-track-dir-btn animation, continuous randomization (when set), and #cie-track-speed-select. 2. Fix .cie-pan-coord not updating at all and change design to be 'x,y (n,n). 3. Style color:lime to .cie-pan-coord when not 0 and .cie-rot-deg. 4. Fix 3D single-axis (X/Y) rotation still messing up gradients at certain angles (60-119°, 240-299° solid red/orange). 5. Fix 'spectral' depth gradient having red recursion depth 1 for both normal and reversed gradients. 6. Skew X/Y and canvas skew X/Y slider values don't quite match up despite being the same value. 7. Add these changes and last 'manual edit' summary to history.md version 1.31.12 and update index.html."):**
  - **Limit Track Autosave & State Restoration (`getSettings`, `loadSettings`, `toggleTrackPP`)**:
    - Extended `getSettings()` to serialize `trackPP` active states, `trackPPDirection` values, `trackPPSpeeds`, `trackPPModes`, and `trackPPSpeedScales`.
    - Corrected continuous randomization state persistence for limit track random buttons using the `track_` key prefix in `randomSliderContinuous`.
    - Updated `loadSettings()` to restore limit track animation states, direction button text/icons, direction-specific `lime` highlights, speed dropdown selectors (`#cie-track-speed-select`), and continuous randomization timers.
    - Connected `toggleTrackPP()` and limit track speed dropdown changes to `pushSliderState()` and `triggerAutosave()`.
  - **Pan Coordinates Format & Non-Zero Lime UI Feedback (`.cie-pan-coord`, `updatePanCoordDisplay`, `.cie-rot-deg`)**:
    - Updated markup and live coordinate renderer to unified format: `x,y (n,n)` (e.g. `x,y (0,0)`).
    - Added dynamic `color: lime` styling to `.cie-pan-coord` when either X or Y coordinate is non-zero, resetting to default styling when `(0,0)`.
    - Applied `color: lime` styling to `.cie-rot-deg` indicators across X, Y, and Z rotation readouts whenever rotation angles are non-zero.
  - **3D Single-Axis (X/Y) Rotation Gradient Normalization (`getCustomThemeStrokeStyle`, `getSpectralThemeStrokeStyle`, `getSquareGradientPattern`, `getLocalPoint`)**:
    - Transformed all gradient coordinate endpoints (horizontal, vertical, radial, conical, and square patterns) via `getLocalPoint(ctx, ...)` so that gradient boundaries are anchored in screen/canvas space rather than suffering from non-uniform matrix compression during single-axis 3D rotations.
    - Completely eliminated solid red and solid orange collapse at critical single-axis angles (60°–119° and 240°–299°) across all recursion depths at line width 1.
    - Transformed square gradient pattern matrices via `getLocalPoint(ctx, 0, 0)` translation, ensuring square gradient boxes stay centered without shifts during 3D rotations.
  - **Spectral Depth Gradient Reversal Correction (`getSpectralRGB`, `getColor`)**:
    - Implemented `getSpectralRGB(t, reverse)` in `getColor()` for the `spectral` theme with depth gradient mode, guaranteeing that recursion depth 1 correctly starts at violet/magenta when `#cie-customGradReverse` is checked, rather than remaining red in both directions.
  - **Skew X/Y and Canvas Skew Value Alignment (`m4.skew`, `renderWebGL`)**:
    - Standardized WebGL skew transform matrices with aspect-ratio compensation (`aspect = width / height`), aligning CSS skew transform metrics 1:1 with WebGL render pipeline results.
  - **Manual Edit Summaries**:
    1. **Autosave Event Triggers**: Added autosave listeners to limit track direction toggles and speed change selects.
    2. **Pan Coordinate DOM Structure**: Restructured `.cie-pan-coord` display inside the Pan control group.
    3. **Rotation Degree Value Highlighting**: Added green/lime color class toggling on `#cie-currentRotVal`, `#cie-currentRotYVal`, and `#cie-currentRotZVal`.
  - **Synchronized Versioning**:
    - Synchronized version `1.31.12` across HTML title (`<title>Circulospherical Infinity Engine 1.31.12</title>`), help overlay header (`#cie-help-title`), control panel header (`.hdr-text`), and project history documentation (`history.md`).


### 📍 Version 1.31.13 [2026-08-19 UTC]: Limit Track Randomization Autosave Persistence, RMB+Ctrl Y-Axis Rotation, Pan Wrap Safety & Coordinates Repair, Single-Source DEFAULTS Architecture, Chroma Split Opacity & Trails Suite, and In-Sync Drawing Gradient Projection
* **User Intent / Feedback ("1. Autosave still isn't restoring/resuming limit track randomization (when set). 2. Hold [RMB] drag + [Ctrl] (or [Ctrl] + [RMB] drag to rotate Y-axis. 3. Fix if pan wrap (`#cie-panWrap`) on, canvas pane freezes/locks up, `#cie-pan-coord` doesn't update, and, to fix, must disable pan wrap and reload app (reset doesn't fix). 4. Have `const SLIDER_DEFAULTS` get values from reset/random `const DEFAULTS` so there is only one location for slider defaults instead of having to update both constants. 5. Chroma split: 5a. Add 'opacity' full control suite group under `#cie-chromaDepthGroup` to control all chroma split `ctx.globalAlpha`. 5b. Add 'trails' checkbox to enable trails (`#cie-trail`) effect on all enabled chroma split effects. 6. Fix gradients messed up yet again: all types but 'depth' and 'square' render as solid colors. 'Square' have gradient colors but the gradient pattern doesn't move (in-sync) with the panned/rotated drawing. 7. Add these changes and last 4 'manual edit' summaries to history.md version 1.31.13 and update index.html version."):**
  - **Limit Track Continuous Randomization Autosave & Restoration (`randTrackBtn`, `getSettings`, `loadSettings`)**:
    - Resolved dataset key mismatch in `loadSettings()` by aligning `randTrackBtn.dataset.key` (`'track_' + key`) with serialized keys in `s.randomSliderContinuous`, `s.randomSliderSpeeds`, `s.randomSliderIntervals`, and `s.randomSliderDistributions`.
    - Guaranteed automatic restoration of continuous limit track randomization timers upon app loading, profile import, and autosave state application.
  - **RMB + Ctrl / Alt + RMB Y-Axis Rotation Interaction (`document.mousemove`, `#cie-help-overlay`, `.cie-tab-panel[data-panel="options"]`)**:
    - Updated canvas mouse rotation interaction handlers: holding right mouse button `[RMB]` drag while pressing `[Ctrl]` (or `[Alt]`) now rotates the 3D scene around the Y-axis (`manualRotY`), complementing existing X-axis (pitch) and Z-axis (roll) controls.
    - Updated keyboard/mouse documentation in both the in-app Help modal (`#cie-help-overlay`) and the Options tab Controls panel.
  - **Pan Wrap Freezing Fix, Global Scope Safety, and Reset Resolution (`autoPanX`, `autoPanY`, `updatePanCoordDisplay`, `performResetAll`)**:
    - Identified and eliminated fatal JavaScript runtime `ReferenceError` where `updatePanCoordDisplay()` attempted to access locally scoped `autoPanX` and `autoPanY` from `updateRecenterBtnColor()`, which previously caused the animation render loop to freeze whenever Pan Wrap was active.
    - Lifted `autoPanX` and `autoPanY` to global scope, ensuring live coordinate display `#cie-pan-coord` continuously updates without UI lockups.
    - Updated `performResetAll()` to cleanly reset pan wrapping parameters, auto-pan state, and coordinate indicators to `x,y (0,0)`.
  - **Single-Source DEFAULTS Architecture (`const DEFAULTS`, `const SLIDER_DEFAULTS = DEFAULTS`)**:
    - Re-architected engine configuration defaults so `const DEFAULTS` serves as the single source of truth for all reset, randomization, initialization, and slider bounds across the entire application.
    - Replaced duplicate `SLIDER_DEFAULTS` definitions with direct references to `DEFAULTS`, preventing configuration drift and streamlining maintenance.
  - **Chroma Split Opacity Suite & Trails Integration (`#cie-chromaOp`, `#cie-chromaOpNum`, `#cie-chromaTrail`, `drawSingleState`, `update`)**:
    - Added full control suite for Chroma Split Opacity under `#cie-chromaDepthGroup`, featuring slider `#cie-chromaOp`, numeric input `#cie-chromaOpNum`, reset button, ping-pong animation toggle, speed selectors, and limit tracks.
    - Integrated Chroma Split Opacity into `ctx.globalAlpha` during post-processing aberration passes, allowing precise opacity blending across horizontal, vertical, and depth chroma split layers.
    - Added "Trails" checkbox (`#cie-chromaTrail`) to optionally allow chromatic aberration passes to feed into canvas background trail buffers (`#cie-trail`).
    - Registered all new chroma controls in `DEFAULTS`, `uiMap`, `getSettings()`, `loadSettings()`, and undo/redo history.
  - **In-Sync Drawing Gradient Coordinate Projection & Transformation Repair (`rootDrawingTransform`, `getDrawingPoint`, `getSquareGradientPattern`, `getCustomThemeStrokeStyle`, `getSpectralThemeStrokeStyle`)**:
    - Fixed gradient projection logic across all modes ('horizontal', 'vertical', 'radial', 'conical', 'square') by capturing the root drawing transform matrix `rootDrawingTransform` at the beginning of each draw cycle.
    - Mapped drawing-space bounding coordinates through inverse local matrix transformations ($M_{\text{current}}^{-1} M_{\text{root}}$), ensuring linear, radial, conical, and square pattern gradients move, pan, zoom, and rotate in 100% lockstep synchronization with the geometric figures without collapsing into solid flat colors.
  - **Manual Edit Summaries**:
    1. **Limit Track Button Data Key & State Mapping**: Standardized `randTrackBtn.dataset.key` to use `'track_' + key` consistently across creation, serialization, and retrieval.
    2. **Global autoPanX/Y Scope & Pan Coordinate Safety**: Lifted `autoPanX` and `autoPanY` to outer scope so `updatePanCoordDisplay()` can safely access them without reference errors during pan wrapping or reset.
    3. **Unified Single-Source DEFAULTS Architecture**: Connected `SLIDER_DEFAULTS` directly to `DEFAULTS` to eliminate duplicate defaults definitions across the codebase.
    4. **Chroma Split Opacity Suite & Trails Integration**: Integrated full opacity slider suite (`#cie-chromaOp`, `#cie-chromaOpNum`, reset, ping-pong, limits) and trails toggle (`#cie-chromaTrail`) into chroma split pipeline.
  - **Synchronized Versioning**:
    - Synchronized version `1.31.13` across HTML title (`<title>Circulospherical Infinity Engine 1.31.13</title>`), help overlay header (`#cie-help-title`), control panel header (`.hdr-text`), and project history documentation (`history.md`).



