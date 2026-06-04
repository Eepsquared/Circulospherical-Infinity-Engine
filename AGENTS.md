# Custom Agent Guidance (AGENTS.md)

1. **Persistent History Maintenance:** Keep the dynamic `/CHAT_HISTORY.md` updated at every milestone or when a new feature is requested and successfully implemented. Ensure no history of prior user features (e.g., wobble limits, keyboard pan shortcuts, SVG share buttons) is ever discarded.
2. **Framework Choice Preservation:** This application is configured as a fast, low-latency, React-free standard HTML5 Canvas/JS app. Always adhere strictly to this native JavaScript architecture; do not introduce complex client-side frameworks unless explicitly requested.
3. **Double-Buffered Performance:** When optimizing drawings or resolving canvas window resize issues, preserve off-screen image caching and double-buffered drawing buffers to avoid screen flashing or blanking.
