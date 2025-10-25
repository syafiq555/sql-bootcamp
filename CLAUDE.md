# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Purpose

This is a **SQL/MSSQL 2-Day Bootcamp** training materials repository containing:
- **Design document** (`README.md`): Comprehensive pedagogical framework covering learning progression, session breakdown, real-world use cases, and success metrics
- **Presentation** (`slides.html`): Self-contained reveal.js HTML presentation with 52 interactive slides

## Architecture Overview

### Presentation Structure (slides.html)

**Technology Stack:**
- **reveal.js** (CDN): Framework for slide deck creation
- **highlight.js** (CDN): SQL syntax highlighting
- **Mermaid** (CDN): Diagram rendering (for potential future enhancements)
- **Dark theme**: GitHub-dark code styling for visual appeal
- **No build process**: Single HTML file runs in any modern browser

**Content Organization:**
- **Session 1** (Day 1, 2.5hrs): SQL Foundations (SELECT, WHERE, ORDER BY, aggregates) - 12 slides
- **Session 2** (Day 1, 2.5hrs): Data Manipulation (JOINs, GROUP BY, CRUD) - 16 slides
- **Session 3** (Day 2, 2.5hrs): Database Design & Advanced Queries (normalization, CTEs, subqueries) - 12 slides
- **Session 4** (Day 2, 2.5hrs): Optimization & Real-World (indexes, window functions, capstone) - 12 slides

### Progressive Learning Flow

The bootcamp implements **SQLite → MSSQL progression**:
- **Day 1 (SQLite)**: Fundamentals with zero-friction setup (DB Browser)
- **Day 2 (MSSQL)**: Enterprise features and optimization
- Participants advance through all 4 sessions regardless of starting skill level (scaffolded exercises)

## Presentation Workflow

### Preview Slides
```bash
# Open directly in browser (no server required)
file:///C:\Users\f2tsb\OneDrive\Documents\bootcamp\slides.html
```

**Navigation:**
- Arrow keys / spacebar: Navigate slides
- 'S' key: Speaker notes view (with timings)
- 'ESC' key: Overview/grid view
- 'F' key: Full-screen mode

### Modify Content

**Direct HTML editing** in `slides.html`:
- Add/edit slides inside `<section>` elements
- Use existing CSS classes for consistency:
  - `.session-badge`: Time/session labels
  - `.note-box`: Content callout boxes (with optional style overrides)
  - `.two-column`: Side-by-side layout
  - `.sql-highlight`: Cyan color for SQL keywords
- Code blocks use `<pre><code class="language-sql">...</code></pre>`

### Responsive Design Considerations

**CSS Optimizations** (already applied):
- Code blocks: `font-size: 0.48em` with `overflow-x/y: auto` for scrollable long examples
- Two-column layouts: `font-size: 0.42em` for dense code
- Note boxes: `padding: 10px 12px` (tight spacing to prevent overflow)
- Tables: `font-size: 0.75em` for readability
- Max-heights: Code blocks capped at 350-450px with scroll support

**Key constraint:** Content must fit within slide boundaries. Test in browser before deploying.

## Key Design Decisions

1. **Single HTML File**: No deployment process; share file directly or host on web server
2. **No Local Dependencies**: All libraries via CDN; works offline once loaded
3. **Speaker Notes**: Every slide includes teaching guidance in `<aside class="notes">`
4. **Real-World Scenarios**: Each session anchors concepts in concrete examples (Netflix, e-commerce, library system)
5. **Quiz/Lab Slides**: Embedded checkpoints every ~20 minutes (per README pedagogy)

## Common Modifications

**Add a new slide:**
```html
<section>
    <h2>Slide Title</h2>
    <div class="note-box">
        <p><strong>Key point:</strong></p>
        <pre><code class="language-sql">SELECT * FROM example;</code></pre>
    </div>
    <aside class="notes">
        Speaker guidance for this slide...
    </aside>
</section>
```

**Adjust responsiveness:**
Edit `<style>` section for `.reveal pre`, `.note-box`, or `.two-column` as needed. Test font sizes in browser at actual presentation dimensions.

**Update speaker notes:**
Edit `<aside class="notes">` content on each slide (viewable with 'S' key).

## Integration with README.md

`README.md` documents:
- **Pedagogical rationale** for each design decision
- **Learning progression** and scaffolding strategy
- **Real-world use cases** mapped to sessions
- **Success metrics** and quiz targets

Refer to README when:
- Justifying content ordering or depth
- Understanding why specific examples were chosen
- Adjusting quiz difficulty or pacing

## Testing Before Presentation

1. Open `slides.html` in modern browser (Chrome, Edge, Firefox)
2. Navigate through all sessions (ensure no content overflow)
3. Press 'S' to verify speaker notes appear correctly
4. Check code highlighting renders properly
5. Test at expected presentation dimensions (16:9 or 4:3)

## Notes for Future Sessions

- **CSS Maintenance**: Font sizes tuned for readability + fit. Don't reduce below 0.42em in dense layouts
- **Speaker Notes**: Typically 2-3 sentences per slide (time budget ~2-3min per slide)
- **Lab Time**: Built-in 40-60min per session; slides flag lab sections
- **Quiz Frequency**: Every session ends with 10-15min quiz (diagnostic, not graded formally)
