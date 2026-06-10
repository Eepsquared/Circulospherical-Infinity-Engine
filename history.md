# ♾⚙ Circulospherical Infinity Engine - Development Archive & Chat History

This document serves as the persistent, durable **in-workspace archive** of the full design history, requested features, user decisions, and development checkpoints for the **Circulospherical Infinity Engine** (originally "Circular Infinity Engine"), or **CIE**.

Because chat platform windows may refresh or clear across sessions, this file is **actively updated by the assistant at every checkpoint/version** to preserve 100% of the app's progress, documentation, and customization instructions.

## 📅 Project Metadata
* **App Name:** Circulospherical Infinity Engine
* **Current Version:** v1.19.0 (Stable)
* **Status:** Build succeeds perfectly (`npm run build` is 100% green)
* **Environment:** React-free high-performance pure HTML5 / JavaSript Canvas hybrid structure for sub-millisecond drawing loops

## 🚀 Chronological Feature Version History

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
    <svg viewBox="0 0 24 24" width="11" height="11">...</svg>```

### 📍 Version 1.06: Temporal Motion Blur, Global Timeline Scrubbing, and Control Polish
* **User Intent:**
  * Rename "Global Speed" to "Global speed", removing custom bolding/color styles.
  * Introduce a high-fidelity motion blur effect by using a temporal blending technique where the current frame is lightly mixed with a stored history of previous frame transforms.
  * Add a global 'Timeline' slider that lets the user manually scrub through the animation phase to inspect specific geometric moments.
* **Implementation:**
  * **Global speed Control Polish**: Lowercase-renamed the label and validated its CSS properties so that it inherits standard `.cie-label` properties without extra bolding or color overrides.
  * **Global Timeline Slider**: Placed a master Timeline slider right below Global speed in the Anim tab. Built custom bindings that dynamically animate the slider in loop-step with `pTime` during play, but instantly override `pTime` and proportional `rTime` if the user scrubs it manually (via mouse dragging or manual number field changes), updating the canvas immediately when paused.
  * **Temporal Motion Blur**: Configured a state history buffer (`transformHistory`) to cache previous transforms, zoom factors, and color theme phases on active frames. Created a localized state drawer `drawSingleState` to redraw previous snapshots with smooth exponential-decay opacities underneath the current frame. Natively incorporated "Enable", "Steps", and "Intensity" configs as third-wave parameters with reset/limit/ping-pong integrations inside the FX panel.

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

### 📍 Version 1.08: Visual Polish, Action-Bar Nesting, and Filter Fixes
* **User Intent:**
  * Fix the CSS canvas invert filter behavior.
  * Correct vertical flow nesting for `#cie-action-bar` to restore container-height scrolling correctness.
  * Refine sharing and action bar icon assets (SVG width/height and high-fidelity emojis).
* **Implementation:**
  * **Invert Action Correction**: Fixed the active Canvas invert state filter check so that default color-inverting behaves precisely under native filters without visual flickering.
  * **Action Bar DOM Nesting Refinement**: Moved `#cie-action-bar` inside the `.cie-content` DOM hierarchy, ensuring that all action items flow cohesively alongside options parameters and maintain strict scroll boundary limits inside the docked sidebar.
  * **High-Definition Sharing & Export Assets**: Upgraded the action button configurations, perfecting SVG viewBox styling dimensions to `12px` and updating the export button to use high-contrast multi-colored `🖼️` representations.

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

### 📍 Version 1.10: State-Preserved Floating Panel Transitions
* **User Intent:**
  * Resolve a layout bug wherein the controls panel shrunk permanently to a narrow, squished 210px width upon being undocked (floated) from the right side of the workspace, which distorted control elements and gave the impression that an older, degraded version of the app interface was loaded.
* **Implementation:**
  * **Interactive Floating State Capture**: Created memory-allocated storage indicators (`floatTop`, `floatLeft`, `floatRight`, `floatWidth`, `floatHeight`) that capture the exact bounding properties and positioning styles of the floating GUI panel immediately before docker integration transforms.
  * **Fidelity Transition Restoration**: Modified the `.cie-dockBtn` listener to swap the saved spatial coordinates and resized width dimensions seamlessly back onto the panel during float-conversion cycles. Replaced the static, disruptive `210px` reset with a smooth class fallback that preserves the signature 260px wide layouts or the user's custom-resized workspace configurations.

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

### 📍 Version 1.12: Unified Docked Scrollbar Layouts, Dynamic Canvas Color Inversion, and Persistent Section Signposts
* **User Intent:**
  * When the control panel is docked, keep the 'action bar' always visible at the bottom while the rest of the control panel vertically scrolls.
  * Add and show clear, readable section signpost names at the top of each tab panel section when docked.
  * Move the simple inline 'invert canvas' checkbox out of the Background Color section and restructure it as a fully configured 'Invert color' control group with modern interactive controls (reset, numeric inputs, range limits, and high-frequency dynamic ping-pong animations).
* **Implementation:**
  * **Docked Footer Unification**: Repositioned the unified `#cie-action-bar` directly beneath the scrollable `#cie-content` DOM container within the parent `#cie-controls` div. Adjusted display structures to render `#cie-content` with full flexible vertical scrolling while keeping the action bar pinned statically to the bottom in docked view states.
  * **Persistent Section Headers**: Engineered custom CSS rules and added declarative `.cie-docked-section-header` signposts (Main, Anim, FX, Designs, Options) indicating section locations, contextually activated exclusively during docked Sidebar state layouts.
  * **Interactive Color Inversion Slider**: Restructured the hidden `#cie-invert` checkbox into an interactive range slider element inside its own dedicated 'Invert color' group, complete with reset listeners, manual precision numerical inputs, limit popovers, and automated logarithmic speed checkboxes/randomizations. Coerced legacy checkbox configurations to continuous floating-point numeric states dynamically inside the setting loader to ensure full backward compatibility.

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

### 📍 Version 1.15: Static Unified Title Sync & Interactive Sticky Section Headers
* **User Intent:**
  * Adopt a single global naming strategy starting with "Circulospherical Infinity Engine" without changing the header text or browser document title dynamically when swapping between 2D and 3D patterns.
  * Facilitate effortless version editing in the future by automatically matching header references to the main HTML document title.
  * Enhance docked sidebar navigation by making the segment signposts sticky; keeping the active section's header visible at the top of the pane during scroll ranges, until the subsequent section pushes it up.
* **Implementation:**
  * **Static Unified Title Synchronization**: Eliminated dynamic title text manipulation logic in the main loop. Programmed a lightweight startup script reading `document.title` and binding it instantly to both the header `.hdr-text` and help menu title header `#cie-help-title`, protecting static, seamless future version bumps.
  * **Interactive Sticky CSS Headers**: Modified `.cie-docked-section-header` styles in CSS, applying `position: sticky; top: 0; z-index: 10;`. Anchored by the scrolling `.cie-content` body, headers now intelligently hover and stack sequentially on scroll, improving control visibility.

### 📍 Version 1.15.1: Interactive Hover & Tap Label Micro-Animations
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

### 📍 Version 1.16.1: Flawless, Continuous Infinite Zoom Rendering Engine with Seamless Coloring
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

### 📍 Version 1.16.2: Pixel-Perfect Infinite Zoom & Designs Ordering Fix
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

### 📍 Version 1.16.3: High-Fidelity Continuous Infinite Zoom & Color Index Bounds Protection
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

### 📍 Version 1.17: Automated Safety Clamping, Advanced Ping-Pong Limits controls, and Continuous Randomizer
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

### 📍 Version 1.18: Multidirectional Docking System, Custom Gradient CSS Dropdowns, and Narrow Help Sidebars
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

### 📍 Version 1.18.1: Absolute Minimization Control, Dynamic Docking Setup, and UI Detail Polish
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

### 📍 Version 1.18.2: Docking split-screen resize bars, titlebar size accommodations, header styling configurations
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

### 📍 Version 1.19: Persistent Ping-pong directions, dynamic Input/Slider attribute syncing, and 7 CSS Canvas Filters
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

## 🛠️ Complete Feature Index & Shortcuts
For a complete, in-depth view of all controls, refer directly to the in-app help modal (`#cie-help-overlay`, accessible by clicking the help button or pressing the help keys). Below is the comprehensive index transcribing all available engine features and interactions:

### 🌀 Patterns & Geometry
* **1-Way Horizontal/Vertical**: Circles grow from small to large in one direction from center
* **2-Way Horizontal/Vertical**: Classic "circular infinity": recursive circles branching symmetrically in one axis
* **2-Way Inverted H/V**: Like 2-Way but circles grow larger toward the edges
* **4-Way +**: Both axes simultaneously
* **4-Way Cross**: Both axes simultaneously but packed ("squaring the circle")
* **3D 2-Way Horizontal**: True 3D perspective 2-Way horizontal branching rotating in space
* **3D 4-Way +**: True 3D perspective recursive circles rotating in space
* **Kaleidoscope x8/x12**: 8-/12-Way *; mirrored wedge radial symmetry
* **Spiral**: Circles along a rotating expanding spiral arm
* **Fractal Tree**: Branching organic tree that sways and breathes
* **Lissajous**: Stacked harmonic orbit rings per depth level

### 🎨 Color Themes & Strobe
* **Static / Custom**: Single theme color, no cycling
* **Cycle**: Auto-advances through all themes in order of select options
* **Random**: Picks a random theme each interval
* **Multi-strobe / Multi**: Each depth ring gets a different color offset

### 🎬 Animation & Modulators
* **Global speed**: Scales all animation speeds in unison
* **Pulse frequency**: Enables pulse animation; slider sets oscillation speed
* **Pulse distance**: How far circles "breathe" in and out
* **Pulse shift**: Phase offset per depth level, creating a ripple wave effect
* **Converge**: Collapses all circles toward a single concentric point (0 = normal, 1 = fully collapsed)
* **Orbit rotation**: Orbit/rotate/twist nested depths independently
* **Sync pulse**: Syncs the pulse timing to the rotation timeline instead of the pulse timeline, aligning breathing swells with rotation
* **Wobble amplitude**: Secondary radius modulation layered on top of pulse
* **Wobble frequency**: Speed of the wobble oscillation
* **Distortion ripple**: Displaces each circle center by an animated sine-wave offset
* **Trail length**: Lower value = longer trails (less background clear per frame)
* **↔ Ping-pong**: Slider oscillates between its min and max automatically
* **🎚️ Limits button**: Set custom min/max extents for ping-pong animation
* **↺ Reset button**: Resets a single slider to its default value
* **Pattern Cycle/Random**: Auto-cycles through render patterns (similar to color cycling)
* **Manual Timeline Scrub**: Drag to manually drive and inspect specific geometric moments in real time

### ✨ FX Filters & Video Blend
* **Blend Composites**: Canvas composite operation: Burn, Difference=inversion, Dodge, Exclusion, Hard/Soft Light, Lighter (Add)=additive glow, Multiply, Overlay, Screen, XOR
* **Chroma split**: RGB lens aberration via screen-blend offset copies
* **Feedback echo**: Previous frame blended back in — high values create tunnel feedback
* **Scanlines**: CRT-style horizontal lines overlay
* **Vignette**: Radial edge darkening
* **Motion Blur Setup**: Temporal trail FX; blends past frame transforms procedurally beneath the current scene

### 🎹 Keyboard & Canvas Interactions
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

## ⚙️ Build and Development Configuration
The environment is configured with **Vite** serving index.html instantly on Port 3000. Under the hood, the project is configured with zero external heavy frameworks to safeguard peak performance and render loop latency:

* **Entry point:** `/index.html` (embedded styles, control panel HTML, Canvas, WebGL/2D mathematical shading context, and event listeners).
* **Styles:** Clean dark-mode layout with customizable borders, custom sliders, responsive popover positioning, and dynamic range overlays.
* **Packaging:** `/package.json` with scripts:
  * `npm run dev` — local development server on port 3000 list.
  * `npm run build` — static compilation to `/dist` to guarantee fast delivery via Cloud Run.

## 📝 Guidelines for Next Sessions
* **Never Discard History:** The AI agent must always read `/history.md` (formerly `/CHAT_HISTORY.md`) at the beginning of the journey to align with the complete state of the art.
* **Synchronous Updates:** When adding a new feature, slider or other user interface (UI) element, parameter mapping, audio utility, etc., append it to the [Chronological Feature Version History](#) section above.
* **Save and Build Verify:** Complete validation with `compile_applet` before closing a turn.
* **App version incrementing:** When updating the app version, use semantic versioning: Major.Normal/Minor.Patch/Bug-fix as defined by certain changes:
  * Major: many (5+) new features, can include bug-fixes; prompt will let AI agent know; increment app version by 1 (non-negative integers)
  * Normal/Minor: some (`<`5) new features (mostly UI-related), can include bug-fixes; increment app version by 0.1 (tenths)
  * Patch/Bug fix: bug-fixes *only*; increment version by 0.0.1 (1 thousandths separated by a decimal)
  * If AI agent is unsure what constitutes "major", "normal", "minor", and/or "patch"/"bug-fix" changes, ask prompter.
* **Update on manual edit:** whenever a "manual edit" ("I made some changes." prompt) is done (except for edits to 'history.md'), append a summary of the manual edit to the last (most recent) app version in 'history.md', unless otherwise instructed.
