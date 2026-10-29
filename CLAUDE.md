# INCLASS repo — INCLASS and RVW builds

Teacher-led, projected HTML builds for Richard's Cambridge IGCSE ESL classes (Grade 9 & 10, Royal International School, Vietnam). Two build types live here:

- **INCLASS** — stand-alone, teacher-led in-class activities (game shows, mysteries, debates, rankings, quizzes), usually tied to a grade and unit. Folders by grade/unit/activity.
- **RVW** — test-review slideshows rebuilt exactly from a source test (pptx, docx or PDF). In the `TEST-REVIEW/` folder.

Neither type is a student game: no name/class login, no scoreboard submission, no data sent anywhere, no Try Again.

## Repo layout
- INCLASS: `/G9/unit-03-food/<activity-name>/index.html` (mirrors the Lessons repo: two-digit unit number, lowercase hyphenated names).
- RVW: `/TEST-REVIEW/G9/unit-02-technology/index.html`.
- INSTRUCT (project/instruction slides; rules live in the GROUPS | INSTRUCT Builds project): `/INSTRUCTIONS/G10/unit-13-success-and-fame/<project-name>/index.html`, listed under the landing page's Instructions tab.
- GROUPS (teacher-run class-group tools; rules live in the GROUPS | INSTRUCT Builds project): `/GROUPS/G10/unit-13-success-and-fame/<project-name>-<class>/index.html`, listed under the landing page's Groups tab. Commit without asking.
- Root `index.html` is the landing page — always add new builds to it.
- Classes: G9 = 9A1, 9A2, 9A3; G10 = 10A1. Roster nicknames are built into each file — copy them from the most recent build of the same grade and keep them easy to edit.

## Commits
- **INCLASS:** ask before the first commit of a new build; commit later edits without asking. Format: `Add INCLASS: G9 Unit 3 Food – Food Mystery` / `Update INCLASS: …`.
- **RVW:** commit to `TEST-REVIEW/` without asking.
- Never commit API keys or other secrets.
- If a request clashes with these rules, ask before building.

## Shared across both types
- **SHARED is the master code for shared features** (mrrich-ai/SHARED; it replaces CONTROL, `_shared/control/control.html` in the Lessons repo, which is now frozen). Any feature these builds share with Lesson HTML is copied from the current SHARED code, never from an older build. Restyle it to the build's look, but keep its behaviour. Each shared feature's full rules are in its SHARED module README (pointers below). Whenever a shared feature is added or changed, update the module code, README and demo in SHARED in the same commit (SHARED/WORKFLOW.md).
- **Frames:** INCLASS uses the `inclass` frame, RVW the `rvw` frame (SHARED/control/variants/README.md).
- **Screen:** 16:9, rendered at 1920×1080 and scaled to fit any screen, no scrolling, high contrast, readable from the back of the room.
- **Navigation, REV (answer progression), click-to-pause:** see SHARED/control/README.md.
- **Delivery:** one self-contained HTML file.
- **EXPLAIN (light-bulb rule/pattern explainer):** see SHARED/features/explain/README.md (INCLASS and RVW bulb positions are listed there). RVW: not used unless Richard asks for it — don't list EXPLAIN candidates for RVW builds.

## Workflow: Step 1 (chat) and Step 2 (Claude Code)
Full workflow: SHARED/WORKFLOW.md. Tags and data blocks: SHARED/TAGGING.md. Applies to INCLASS, RVW and INSTRUCT builds.
- **Step 1 (chat): the main build only.** Unique slides, the tags and JSON data blocks from SHARED/TAGGING.md, and space reserved for the CONTROL frame. Ends with **one combined approval list** (the items that apply to the build type): CLUE candidates, EXPLAIN slides, GAMIFY options, PROVE for non-exam Reading. The quiz, Words from today and PROVE on Exam-style question sections are automatic where the build type uses them.
- **Step 2 (Claude Code)**, triggered by "Add CONTROL and approved FEATURES to <path>": copy the current code from SHARED (never from older builds); wire it to the tags and data blocks; build each GAMIFY game from `gamify-data` on top of the GAMIFY engine, class and solo versions, following the GAMIFY rules; render-check at 1920×1080; commit with no raw HTML pasted.

---

## INCLASS rules

### Before building
1. Content usually comes from Richard's prompt or files, tied to a grade and unit.
2. Suggest activity formats that suit the topic (game show, mystery, debate, ranking, quiz…) and wait for a pick.
3. Then present a menu of named visual styles (cinematic photo, 3D game show, premium flat illustration, painterly canvas, a look inspired by a show/app/game students know, etc.) with short descriptions. Wait for a pick before building anything.
4. Ask when extras would help: random student/group picker, sound effects with mute, round countdowns.

### Structure and look
- One self-contained file: eye-catching animated title screen in the chosen style, then activity slides, optional wrap-up slide.
- Never show "INCLASS" on slides — only the activity's own title. No page-number badge unless built directly on a book page. No "Open your book" transition unless Richard says it leads into book work.
- Energetic, kinetic layout and animation. Premium graphics: layered depth (foreground/midground/background), realistic lighting, shadows and textures, rich particle/light effects, real photos for people and places combined with detailed code-drawn SVG/canvas art — never plain flat shapes or emoji as the main graphics. Smooth on a classroom PC.
- Every build gets a brand-new design — never reuse an earlier INCLASS build, a Lessons warmer set, or non-book Lesson slides.
- Teacher procedures (setup, timings, sentence starters) never on slides; a small teacher-note icon opens a window with them.
- Bottom bar keeps the standard functions (Contents, Back, counter, Next) but is restyled to match each build's look.
- **Font size:** as large as the slide allows with no overflow; rearrange dense slides rather than shrink.

### Interactive features
- **REV** on every slide with fixed answers (see SHARED/control/README.md).
- **Drag-into-gap:** see SHARED/activities/drag-into-gap/README.md.
- **Choice buttons:** see SHARED/activities/choice-buttons/README.md.
- **Work timer and other interactive features:** depend on the content — do whatever is most intuitive for an in-class activity.

### Teacher tools
- **Roster picker 🎡** (in the bottom margin), **slide stopwatch ⏱** (in the bottom bar), **B / W keys** (no buttons), **first screen:** see SHARED/control/README.md (`inclass` frame).
- **Number teams (if a build uses them):** absent-student swap — see SHARED/features/gamify/README.md.

### Not used in INCLASS
CLUE/VISCLUE vocabulary cards, offline-font notice, student mode (?student/?zh), click-to-zoom, read-aloud, end-of-deck quiz, 5/6 break screens, ? sheet, presenter view, Words from today, VI toggle, flashcards, GAMIFY.

### Checking
Render every slide at 1920×1080; check overflow, every reveal, and that Contents matches the slides. Screenshot-and-refine pass on every slide.

---

## RVW rules (test reviews)
These replace the INCLASS look rules for RVW builds.

### Before building
- Read the whole source: every page/slide, speaker notes (context only, never shown), comments, alt text, embedded objects. Use hidden slides only if they contain answers.
- Answers come from the teacher key, speaker notes or hidden slides. Where a task has several acceptable answers, each gets its own reveal.
- List anything inferred, ambiguous or with several possible answers and wait for the key — never guess.
- OCR any text inside images (scanned pages, passages as pictures) and check it word for word against the source.
- Ask for the title if the source doesn't make it clear.

### Fidelity
- Match the source exactly: wording, order, colours, fonts, sizes, backgrounds, boxes, borders, underlined/bold headings, word banks and layout.
- Keep all branding and page furniture on every slide: logos, school names, title/marks/time headers, footer bars, page numbers.
- Exception: leave out Cambridge/publisher identification text — e.g. the running header "CAMBRIDGE IGCSE™ ENGLISH AS A SECOND LANGUAGE: UNIT X TEST" and the footer copyright line "Cambridge IGCSE™ … © Cambridge University Press …". Keep the footer bar and page numbers.
- Keep typos unchanged and list them; never fix them.
- Use the closest font where the original isn't available, list each substitution, and give web fonts an offline fallback.
- Rebuild text and tables as real HTML; use a rendered image only for elements that can't be matched; rebuild low-resolution graphics (e.g. footer bars) in HTML. Extract media at original resolution and embed as base64.

### Screen and mapping
- pptx: one source slide = one HTML slide. docx/PDF: portrait pages reflow into 16:9 slides, split at headings, question groups and natural breaks, keeping the source look.
- Never shrink text to fit. Each question or task stays whole on one slide. Long reading texts split at paragraph breaks, with the passage title on the first part only. When questions relying on a word bank or instructions move to a new slide, repeat that material there. On answer-heavy slides, rearrange (e.g. task left, reveals right) and move mark totals so nothing overlaps.

### Answers
- Every answer starts hidden; answer text at least about 36px; each reveal includes a short explanation shown only behind the reveal.
- REV progression on answer slides, plus Reveal all / Hide all on each slide: see SHARED/control/README.md.

### Evidence-window reveal (reading comprehension)
- See SHARED/features/prove/README.md (window: SHARED/activities/evidence-window/README.md). Multiple matching / multiple choice windows are not built yet.
- **NOTECLEANUP** (named feature — use only when Richard asks for it by name): see SHARED/features/notecleanup/README.md.

### No content additions
No new slides, activities, vocab cards, drag-and-drop or other interactive conversions; no added animations except the evidence-window highlights, the teacher tools below and approved EXPLAIN bulbs. Reproduce source pptx animations and click-builds as they are.

### Teacher tools (RVW)
All teacher tools are present (teacher-only; none change the source content).
- Header strip, header tools (🎡, ⏱, language sign, COPY/NOTE pencil ✏️), work timer, B / W, C, ?, P, cover boxes, click-to-zoom, first screen, click-to-pause: see SHARED/control/README.md (`rvw` frame).

### Not used in RVW
O key ("Open your book"), 5/6 break screens and shortcuts, EXPLAIN (unless Richard asks for it), CLUE/VISCLUE, GAMIFY, end-of-deck quiz, Words from today, warmers, student versions (?student/?zh, VI, read-aloud, flashcards).

### Navigation and media
- Discreet bottom bar (Contents, Reveal all, Back, slide counter, Next; arrows and Space): see SHARED/control/README.md (`rvw` frame). Contents labels every slide by its source slide/page and section.
- Links stay clickable; small audio/video embedded; ask about large or online-only media and flag anything that won't work offline.

### Checking and report
Render every slide at 1920×1080 with answers hidden and with all shown; confirm no overflow, each slide matches the source, every reveal and window step works, and Contents matches the slides. Give a short report: slide mapping, font substitutions, anything not reproduced exactly, typos left unchanged, layout decisions made to fit.
