# INCLASS repo — INCLASS and RVW builds

Teacher-led, projected HTML builds for Richard's Cambridge IGCSE ESL classes (Grade 9 & 10, Royal International School, Vietnam). Two build types live here:

- **INCLASS** — stand-alone, teacher-led in-class activities (game shows, mysteries, debates, rankings, quizzes), usually tied to a grade and unit. Folders by grade/unit/activity.
- **RVW** — test-review slideshows rebuilt exactly from a source test (pptx, docx or PDF). In the `TEST-REVIEW/` folder.

Neither type is a student game: no name/class login, no scoreboard submission, no data sent anywhere, no Try Again.

## Repo layout
- INCLASS: `/G9/unit-03-food/<activity-name>/index.html` (mirrors the Lessons repo: two-digit unit number, lowercase hyphenated names).
- RVW: `/TEST-REVIEW/G9/unit-02-technology/index.html`.
- Root `index.html` is the landing page — always add new builds to it.
- Classes: G9 = 9A1, 9A2, 9A3; G10 = 10A1. Roster nicknames are built into each file — copy them from the most recent build of the same grade and keep them easy to edit.

## Commits
- **INCLASS:** ask before the first commit of a new build; commit later edits without asking. Format: `Add INCLASS: G9 Unit 3 Food – Food Mystery` / `Update INCLASS: …`.
- **RVW:** commit to `TEST-REVIEW/` without asking.
- Never commit API keys or other secrets.
- If a request clashes with these rules, ask before building.

## Shared across both types
- **Screen:** 16:9, rendered at 1920×1080 and scaled to fit any screen, no scrolling, high contrast, readable from the back of the room.
- **Navigation:** Next/Back, arrow keys, slide counter, Contents listing every slide (scrolls inside its window, opens with the current slide in view).
- **REV (answer progression):** blank click / Space / → reveals the next hidden answer, one answer per step (never several at once; drag-and-drop sorters/matches place one item per step in reading order; never wire REV to Check answers / Reveal all); once all show, it advances. ← hides the last revealed; with none revealed, goes back. Individual answers still toggle; progression skips opened ones. Bottom Next/Back always change slides immediately. Returning keeps answers as left. Highlighting text (drag-select or double-click) never counts as a click. Non-REV slides: Space/arrows change slides, blank clicks do nothing.
- **Click-to-pause:** every timer or countdown pauses/resumes when the timer itself is clicked.
- **Delivery:** one self-contained HTML file.

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
- **REV** on every slide with fixed answers.
- **Drag-into-gap:** word-bank gap fills; on reveal a correct guess turns green ✓, a wrong one is crossed out red and the correct word slides in. Clear button. Single-use banks grey out placed words; reusable banks stay available.
- **Choice buttons:** "A or B" items get vote buttons; correct turns green, a wrong pick shakes red.
- **Work timer and other interactive features:** depend on the content — do whatever is most intuitive for an in-class activity.

### Teacher tools
- **Roster picker 🎡** (in the bottom margin): first click asks which class (skipped if only one roster has names or a class was already chosen anywhere in the file); "Change class" beside the class name; later clicks reuse it until the file closes. Pick: 2-s animation scrolling fast, then slowing to a stop, with digital ticking (no mute). Picked name quickly enlarges and glows, then shrinks; the window fades, leaving only the name by the icon until clicked again or the slide changes. No "click to pick again" text. Picked students are left out of later picks; no absentee feature.
- **Slide stopwatch ⏱** (in the bottom bar): click offers 1, 2, 3, 4, 5, 7.5, 10, 12, 15 min; chosen time shows as a glowing digital display; click the display to start/pause/resume; click the icon again to change the time. Last 10%: red pulsing digits, silent. At zero: a random sound plays for 3 s and TIME'S UP flashes for 3 s, then stays (not flashing) until clicked. Changing slides stops and clears it. Sound pool (random, never the same twice in a row): digital alarm clock, game-show buzzer, boxing bell, 8-bit victory jingle, gong, school bell, arcade fanfare, spaceship alert, xylophone run, air horn, cuckoo clock, drum roll + cymbal, train whistle, doorbell, laser zaps, wind chimes, sad trombone.
- **B / W keys** (no buttons): B = black screen "Eyes on me 👀" with a looping "shhhh" until B/Esc; W = plain white, silent.
- **First screen:** shown still and dimmed until clicked, no prompt text.
- **Number teams (if a build uses them):** absent-student swap — hovering a team member's name shows a small ✕; one click (no confirmation) removes them and a 2-s spin picks a replacement from students on neither team, preferring those who haven't played that lesson. Only affects that team in that game. Not for whole-class "full" teams.

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
- REV progression on answer slides, plus Reveal all / Hide all on each slide.

### Evidence-window reveal (reading comprehension)
- One step per click (click/Space/→ forward, ← back). The window pops up over the other questions with the rest of the slide dimmed; the question being answered stays visible and outlined; if there isn't room on one side, panels split above and below the question; text may drop slightly in size only if it still won't fit.
- **Multiple matching / multiple choice (4 steps):** (1) window opens with the full paragraph containing the answer plus one paragraph containing a red-herring distractor, in source order; (2) distractor line highlighted light red; (3) correct answer sentence highlighted yellow; (4) window closes and the answer shows with a trimmed excerpt, key words highlighted.
- **Note-making / short answer (4 steps):** (1) window opens with the answer's full paragraph; (2) the part paraphrasing the question or heading highlighted light blue; (3) answer words highlighted yellow and bold; (4) window closes and the answer shows with a trimmed excerpt labelled with its paragraph number.
- Claude picks the distractors; only when more than one plausible distractor is found for a question, ask before building. Reveal all skips the windows; leaving a slide mid-window resets that question to hidden.
- **NOTECLEANUP (named feature — use only when Richard asks for it by name; replaces the note-making steps above for that build):** teaches that notes should be short. The window shows the answer's paragraph with the note form (heading/prompt + answer line) below it, outlined. Steps, one per click: (1) window opens on the paragraph, answer line empty; (2) the answer **and its justification** highlighted yellow in the paragraph; (3) that whole yellow span is written onto the answer line word by word; (4) light blue on the heading/prompt words and on the words in the written answer that paraphrase or repeat them; (5) those written words get a red highlight and a red strikethrough, leaving the short answer; (6) window closes and the note line keeps the crossed-out version (struck words red, short answer bold blue on yellow) with a one-line explanation (paragraph number + what the struck words repeat). If an answer has no prompt/answer paraphrase, steps 4–5 are skipped. Reveal all skips windows; ← steps back; Esc or leaving the slide mid-window resets that line. First used: TEST-REVIEW/G10/unit-13-success-and-fame (Oct 26 2026).

### No content additions
No new slides, activities, vocab cards, drag-and-drop or other interactive conversions; no added animations except the evidence-window highlights and the teacher tools below. Reproduce source pptx animations and click-builds as they are.

### Teacher tools (RVW)
All teacher tools are present (teacher-only; none change the source content).
- **Header strip:** a thin strip above the source slide holds the header tools; the source slide is scaled down slightly so nothing covers it or its page furniture.
- **Header tools:** roster picker 🎡 and slide stopwatch ⏱ (as in INCLASS above, but in the header strip); language sign; COPY/NOTE pencil ✏️.
  - **Language sign:** dormant = small faded England flag (St George's cross, not the UK flag) next to the 🎡. Click: enlarges to the centre with flag + "ENGLISH ONLY", glows ~1 s, returns to the strip keeping flag + text (vivid). Later clicks flip between English and Vietnamese flag + "ĐƯỢC DÙNG TIẾNG VIỆT"; clicking the enlarged sign switches it too; a quick double click on the strip sign returns it to the faded flag. Resets on every slide change. Flags as built-in SVG, never emoji.
  - **COPY/NOTE pencil ✏️** (faded, beside the ⏱): 1st click "Copy into your notebook" strip slides down over the slide header; 2nd "Make your notes. Only key words/phrases"; 3rd "Add ideas to your notebook"; 4th hides. The strip glows, pulses and wobbles slightly; resets on slide change; no progress bar. The pencil glows faintly once answers are revealed where copying clearly fits — the strip never appears by itself.
- **Work timer:** reading exercises get a countdown (10 and 15 min presets, start/pause/reset; click the time to start/pause), red near the end. Once started it stays on screen (small, time + pause only) on every slide; ↺ ends it.
- **B / W keys:** as in INCLASS.
- **C key "Close your books":** the shared animation from the Lessons repo (_shared/close-your-books/snippet.html); click skips to the stamp; click / C / Esc returns to the slide.
- **? key:** cheat sheet of every shortcut.
- **P key:** presenter view in a second window (current + next slide, all answers and explanations), kept in step with the projector.
- **Cover boxes:** hold the right mouse button and drag (or Shift + left-drag) to draw solid white boxes over any part of a slide (right-click menu off); left-click a box to remove it; never triggers REV; cleared on slide change.
- **Click-to-zoom:** small magnifier on reading texts and images opens them full screen, keeping their look with a solid background; answers in gaps can be revealed while zoomed.
- **First screen:** shown still and dimmed until clicked.
- **Click-to-pause:** every timer pauses/resumes when clicked.

### Not used in RVW
O key ("Open your book"), 5/6 break screens and shortcuts, CLUE/VISCLUE, GAMIFY, end-of-deck quiz, Words from today, warmers, student versions (?student/?zh, VI, read-aloud, flashcards).

### Navigation and media
- Discreet bottom bar: Contents, Reveal all, Back, slide counter, Next; arrows and Space also work. Contents labels every slide by its source slide/page and section.
- Links stay clickable; small audio/video embedded; ask about large or online-only media and flag anything that won't work offline.

### Checking and report
Render every slide at 1920×1080 with answers hidden and with all shown; confirm no overflow, each slide matches the source, every reveal and window step works, and Contents matches the slides. Give a short report: slide mapping, font substitutions, anything not reproduced exactly, typos left unchanged, layout decisions made to fit.
