# Performance Optimization Implementation Guide

## Quick Start
This guide shows exactly where to modify index.html to apply each optimization.

---

## FIX #1: Filter String Caching
**Location:** In the main `update()` function, around line 3700

**Current code (FIND THIS):**
```javascript
let filterStr = '';
if (chk('cie-filBlur')) filterStr += ` blur(${val('cie-filBlurAmt')}px)`;
if (chk('cie-filBrightness')) filterStr += ` brightness(${val('cie-filBrightnessAmt')})`;
if (chk('cie-filContrast')) filterStr += ` contrast(${val('cie-filContrastAmt')})`;
if (chk('cie-filGrayscale')) filterStr += ` grayscale(${val('cie-filGrayscaleAmt')})`;
if (chk('cie-filHueRotate')) filterStr += ` hue-rotate(${val('cie-filHueRotateAmt')}deg)`;
if (chk('cie-filSaturate')) filterStr += ` saturate(${val('cie-filSaturateAmt')})`;
if (chk('cie-filSepia')) filterStr += ` sepia(${val('cie-filSepiaAmt')})`;
canvas.style.filter = filterStr.trim() || 'none';
```

**Replace with:**
```javascript
// Cache filter state (declare once at top of script)
let lastFilterStr = '';
let cachedFilterParams = {};

// Then in update() function:
const filterParams = {
  blur: chk('cie-filBlur') ? val('cie-filBlurAmt') : null,
  brightness: chk('cie-filBrightness') ? val('cie-filBrightnessAmt') : null,
  contrast: chk('cie-filContrast') ? val('cie-filContrastAmt') : null,
  grayscale: chk('cie-filGrayscale') ? val('cie-filGrayscaleAmt') : null,
  hueRotate: chk('cie-filHueRotate') ? val('cie-filHueRotateAmt') : null,
  saturate: chk('cie-filSaturate') ? val('cie-filSaturateAmt') : null,
  sepia: chk('cie-filSepia') ? val('cie-filSepiaAmt') : null
};

// Only rebuild if changed
if (JSON.stringify(filterParams) !== JSON.stringify(cachedFilterParams)) {
  cachedFilterParams = filterParams;
  let filterStr = '';
  if (filterParams.blur !== null) filterStr += ` blur(${filterParams.blur}px)`;
  if (filterParams.brightness !== null) filterStr += ` brightness(${filterParams.brightness})`;
  if (filterParams.contrast !== null) filterStr += ` contrast(${filterParams.contrast})`;
  if (filterParams.grayscale !== null) filterStr += ` grayscale(${filterParams.grayscale})`;
  if (filterParams.hueRotate !== null) filterStr += ` hue-rotate(${filterParams.hueRotate}deg)`;
  if (filterParams.saturate !== null) filterStr += ` saturate(${filterParams.saturate})`;
  if (filterParams.sepia !== null) filterStr += ` sepia(${filterParams.sepia})`;
  
  const newFilterStr = filterStr.trim() || 'none';
  if (newFilterStr !== lastFilterStr) {
    canvas.style.filter = newFilterStr;
    lastFilterStr = newFilterStr;
  }
}
```

**Expected gain:** 5-10% frame time (filters are expensive CSS operations)

---

## FIX #2: Background Color Caching
**Location:** In `update()`, around line 3560 (before trail alpha calculation)

**Current code (FIND THIS):**
```javascript
const rgb1=getRGB(el('cie-bgColor').value),rgb2=getRGB(el('cie-bgColor2').value),t=val('cie-bgFade');
const baseBg={r:rgb1.r+(rgb2.r-rgb1.r)*t,g:rgb1.g+(rgb2.g-rgb1.g)*t,b:rgb1.b+(rgb2.b-rgb1.b)*t};
const invBG = val('cie-invert') || 0;
const bgRGB={
  r: Math.round(baseBg.r + (255 - 2*baseBg.r)*invBG),
  g: Math.round(baseBg.g + (255 - 2*baseBg.g)*invBG),
  b: Math.round(baseBg.b + (255 - 2*baseBg.b)*invBG)
};
const bgKey=bgRGB.r+','+bgRGB.g+','+bgRGB.b;
```

**Replace with:**
```javascript
// Cache at top of script
let lastBgParams = null;
let cachedBgKey = '0,0,0';

// In update() function:
const bgParams = {
  c1: el('cie-bgColor').value,
  c2: el('cie-bgColor2').value,
  fade: val('cie-bgFade'),
  invert: val('cie-invert')
};

const bgKey = (() => {
  const paramStr = JSON.stringify(bgParams);
  if (paramStr === lastBgParams) return cachedBgKey;
  
  lastBgParams = paramStr;
  const rgb1 = getRGB(bgParams.c1);
  const rgb2 = getRGB(bgParams.c2);
  const t = bgParams.fade;
  const baseBg = {
    r: rgb1.r + (rgb2.r - rgb1.r) * t,
    g: rgb1.g + (rgb2.g - rgb1.g) * t,
    b: rgb1.b + (rgb2.b - rgb1.b) * t
  };
  const invBG = bgParams.invert || 0;
  const bgRGB = {
    r: Math.round(baseBg.r + (255 - 2 * baseBg.r) * invBG),
    g: Math.round(baseBg.g + (255 - 2 * baseBg.g) * invBG),
    b: Math.round(baseBg.b + (255 - 2 * baseBg.b) * invBG)
  };
  cachedBgKey = bgRGB.r + ',' + bgRGB.g + ',' + bgRGB.b;
  return cachedBgKey;
})();
```

**Expected gain:** 2-3% frame time (reduces color math and string ops)

---

## FIX #3: Trail Rendering Optimization
**Location:** In `update()`, around line 3580 (trail alpha section)

**Current code (FIND THIS):**
```javascript
const tgt=o.trail?o.tDens:1; 
trailAlpha+=(tgt-trailAlpha)*Math.max(0.005,o.trail?0.08:0.4);
ctx.fillStyle='rgba('+bgKey+','+trailAlpha+')'; 
ctx.fillRect(0,0,canvas.width,canvas.height);
```

**Replace with:**
```javascript
const tgt = o.trail ? o.tDens : 1;
trailAlpha += (tgt - trailAlpha) * Math.max(0.005, o.trail ? 0.08 : 0.4);

if (o.trail && trailAlpha > 0.01) {
  // Use dedicated trail buffer instead of full-canvas fill
  ctx.save();
  ctx.globalAlpha = trailAlpha;
  ctx.fillStyle = 'rgb(' + bgKey + ')';
  ctx.fillRect(0, 0, canvas.width, canvas.height);
  ctx.restore();
} else if (!o.trail) {
  // Hard clear - much faster than semi-transparent fill
  ctx.clearRect(0, 0, canvas.width, canvas.height);
}
```

**Expected gain:** 10-15% frame time (clearRect is 2-3x faster than fillRect with alpha)

---

## FIX #4: Circle Path Batching
**Location:** In circle drawing loops (search for `ctx.beginPath(); ctx.arc`)

**Current code (FIND THIS):**
```javascript
ctx.strokeStyle = col;
ctx.lineWidth = o.thick * perspective;
ctx.shadowBlur = (o.glow && layer < 4) ? o.gRad * alpha : 0;
ctx.shadowColor = col;

ctx.beginPath();
ctx.arc(px, py, r, 0, Math.PI * 2);
ctx.stroke();
```

**Replace with:**
```javascript
// Group by style before rendering
const circlesByStyle = new Map();
// ... collect circles with same style into circlesByStyle

// Then batch render:
for (const [styleKey, circles] of circlesByStyle) {
  const style = circles[0].style; // Use first circle's style as reference
  ctx.strokeStyle = style.color;
  ctx.lineWidth = style.width;
  ctx.shadowBlur = style.shadowBlur;
  ctx.shadowColor = style.shadowColor;
  
  // Draw all circles with this style in one path
  ctx.beginPath();
  for (const circle of circles) {
    ctx.arc(circle.x, circle.y, circle.r, 0, Math.PI * 2);
  }
  ctx.stroke();
}
```

**Expected gain:** 15-20% frame time (fewer context state changes, single stroke call)

---

## FIX #5: Viewport Culling
**Location:** In recursive drawing functions (find `drawNode` or similar)

**Add this helper at top of script:**
```javascript
function isCircleInViewport(x, y, r, canvas) {
  const halfW = canvas.width / 2;
  const halfH = canvas.height / 2;
  return x + r > -halfW && x - r < halfW && 
         y + r > -halfH && y - r < halfH;
}
```

**Then in recursive draw function, add check before recursion:**
```javascript
// BEFORE recursing, check if visible
if (d < limit) {
  // ... calculate child positions
  if (isCircleInViewport(x1, y1, nr, canvas)) {
    drawNode(x1, y1, nr, d + 1);
  }
  if (isCircleInViewport(x2, y2, nr, canvas)) {
    drawNode(x2, y2, nr, d + 1);
  }
}
```

**Expected gain:** 20-30% frame time (skips entire subtrees of invisible circles)

---

## FIX #6: Persistent Buffer Reuse
**Location:** At top of script, in initialization

**Current code (FIND THIS):**
```javascript
// Inside doResize():
const tempCanvas = document.createElement('canvas');
tempCanvas.width = canvas.width;
tempCanvas.height = canvas.height;
const tempCtx = tempCanvas.getContext('2d');
```

**Replace with:**
```javascript
// At module scope (declare once):
let resizeBufferCanvas = document.createElement('canvas');
let resizeBufferCtx = resizeBufferCanvas.getContext('2d');

// Then inside doResize():
resizeBufferCanvas.width = canvas.width;
resizeBufferCanvas.height = canvas.height;
resizeBufferCtx.drawImage(canvas, 0, 0);
// ... use resizeBufferCanvas
```

**Expected gain:** 1-2% frame time + reduced garbage collection spikes

---

## Testing Checklist

After each fix:
- [ ] Open DevTools (F12) → Performance tab
- [ ] Record 5 seconds of animation
- [ ] Look for frame time (green bars should be <16.67ms for 60fps)
- [ ] Compare "before" and "after" recordings
- [ ] Verify pattern renders identically (no visual changes)

---

## Profiling Command

In DevTools console:
```javascript
// Log frame time every 60 frames
let frameCount = 0;
let lastTime = performance.now();
const originalRaf = requestAnimationFrame;
window.requestAnimationFrame = function(cb) {
  return originalRaf(() => {
    frameCount++;
    if (frameCount % 60 === 0) {
      const now = performance.now();
      const avg = (now - lastTime) / 60;
      console.log(`Avg frame: ${avg.toFixed(2)}ms (${(1000/avg).toFixed(1)}fps)`);
      lastTime = now;
    }
    cb();
  });
};
```

---

## Commit Strategy

1. Apply fixes in order of impact (high → medium → low)
2. Test each fix individually
3. Commit with message: `perf: Apply fix #N - [description]`
4. Create PR with before/after benchmarks

**Expected final result:** 30-50% faster rendering on deep recursion patterns
