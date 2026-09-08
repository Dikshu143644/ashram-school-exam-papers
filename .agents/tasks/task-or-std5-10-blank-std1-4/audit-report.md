# Audit Report — FEAT-001

Task: Add mark-neutral `किंवा / OR` internal-choice pairs to Std 5-10 (B text sourced from PR#2 = commit `c8174d0`) and blank the `इयत्ता` value in the Std 1-4 student-info box. Single file edited: `index.html`.

## Part A — OR pairs for Std 5-10 (mark-neutral)

For each standard exactly ONE existing short-answer/theory question was converted to an `A / किंवा / B` pair. The (A) question keeps its original bilingual text and `q-marks-tag`; an `<div class="or-divider"><span>— किंवा / OR —</span></div>` is inserted; a new (B) `q-title` follows with the PR#2-sourced bilingual alternative carrying the SAME `q-marks-tag`; the single existing `answer-space` (with two `ruled-line` divs) is shared. The student answers only one of A/B, so marks are unchanged.

| Std | Section | Q-no | (A) target question (kept) | (B) OR-alternative (added, bilingual) | PR#2 citation | Marks (A)=(B) |
|-----|---------|------|----------------------------|----------------------------------------|---------------|---------------|
| 5 | विभाग E | Q.16 | माउसचा (Mouse) उपयोग काय आहे? / What is the use of a Mouse? | संगणक योग्य पद्धतीने बंद (Shut Down) कसा करावा? / How should a computer be shut down properly? | PR#2 Std 5 विभाग E Q.25 | [१ गुण] |
| 6 | विभाग E | Q.16 | Icon (आयकॉन) म्हणजे काय? / What is an Icon? | संगणकावर एखादा Program (प्रोग्राम) किंवा Application (ॲप्लिकेशन) कसे उघडाल? / How will you open a Program or Application on a computer? | PR#2 Std 6 विभाग E Q.24 | [१ गुण] |
| 7 | विभाग E | Q.16 | Icon (आयकॉन) म्हणजे काय? / What is an Icon? | YouTube (यूट्यूब) सारखे application (ॲप्लिकेशन) संगणकावर कसे उघडाल? पायऱ्या लिहा. / How will you open an application like YouTube on a computer? Write the steps. | PR#2 Std 7 विभाग E Q.23 | [१ गुण] |
| 8 | विभाग E | Q.16 | AI चा कोणत्याही दोन क्षेत्रांतील उपयुक्त वापर लिहा. / Write a useful application of AI in any two fields. | संगणकावर YouTube (यूट्यूब) उघडून व्हिडिओ कसा पाहाल? / How will you open YouTube on a computer and watch a video? | PR#2 Std 8 विभाग E Q.22 | [१ गुण] |
| 9 | विभाग E | Q.13 | CPU (सीपीयू) चे कार्य स्पष्ट करा. / Explain the function of the CPU. | Monitor (मॉनिटर) आणि Keyboard (कीबोर्ड) यांचे उपयोग स्पष्ट करा. / Explain the uses of a Monitor and a Keyboard. | PR#2 Std 9 विभाग E Q.26 | [१ गुण] |
| 10 | विभाग F | Q.14 | Artificial Intelligence ... म्हणजे काय? आपण AI चा वापर का करावा? कोणतीही दोन कारणे लिहा. / What is Artificial Intelligence? Why should we use AI? Write any two reasons. | शाळेत विद्यार्थ्यांच्या गरजेनुसार शिक्षणाला मदत करण्यासाठी AI चा वापर वैयक्तिकृत शिक्षण (Personalized Learning) म्हणून करणे का योग्य आहे? आपले मत स्पष्ट करा. / Why is it appropriate to use AI as Personalized Learning to support students according to their needs in school? Explain your opinion. | PR#2 Std 10 विभाग F Q.30 | [३ गुण] |

### Before/after 20-mark reconciliation

Because A and B in each pair carry an identical `q-marks-tag` and the student answers only ONE of them, the counted marks for the affected question are unchanged. No `sec-marks`, meta-chip (`एकूण गुण: २०`), marks-box (`/ २०`) or tab-subtext values were touched.

| Std | Affected Q marks before | Affected Q marks after (A or B, one answered) | Section total | Paper total before | Paper total after |
|-----|-------------------------|-----------------------------------------------|---------------|--------------------|-------------------|
| 5 | 1 | 1 | unchanged | 20 | 20 |
| 6 | 1 | 1 | unchanged | 20 | 20 |
| 7 | 1 | 1 | unchanged | 20 | 20 |
| 8 | 1 | 1 | unchanged | 20 | 20 |
| 9 | 1 | 1 | unchanged | 20 | 20 |
| 10 | 3 | 3 | unchanged | 20 | 20 |

Each Std 5-10 paper still shows `एकूण गुण: २०` (grep count = 6) and marks box `/ २०` (grep count = 6).

## Part B — Std 1-4 इयत्ता value blanked

The `इयत्ता:` label is kept; only the printed class value (`<strong>...</strong>`) was replaced with a blank fill line `<span class="info-line"></span>` matching the other blank fields (Name / हजेरी क्र. / तुकडी / दिनांक).

| Std | Before | After |
|-----|--------|-------|
| 1 | `<strong>१ ली</strong>` | `<span class="info-line"></span>` |
| 2 | `<strong>२ री</strong>` | `<span class="info-line"></span>` |
| 3 | `<strong>३ री</strong>` | `<span class="info-line"></span>` |
| 4 | `<strong>४ थी</strong>` | `<span class="info-line"></span>` |

Std 5-10 इयत्ता values remain printed unchanged (e.g. `<strong>५ वी (Std. 5)</strong>` ... `<strong>१० वी (Std. 10)</strong>`; grep count of `(Std. 5..10)` strong values = 6). No other Std 1-4 content (questions, options, images, marks) was changed — the full `git diff` shows only the four इयत्ता replacements in the Std 1-4 blocks.

## Verification results

- `grep -c '<div class="or-divider">' index.html` → **6** (new markup blocks; CSS definitions unchanged).
- `grep -o 'Q\.[0-9]* (A)' | wc -l` → **6**; `grep -o 'Q\.[0-9]* (B)' | wc -l` → **6**.
- `grep -c 'एकूण गुण: २०' index.html` → **6**; `grep -c '/ २०' index.html` → **6**.
- `grep -c '<strong>१ ली</strong>|<strong>२ री</strong>|<strong>३ री</strong>|<strong>४ थी</strong>'` → **0** (all Std 1-4 values blanked).
- `grep -c 'इयत्ता:'` → **10** (labels retained for all 10 papers).
- HTML parse sanity: `python3 -c "import html.parser; ..."` → **parsed-ok**.
- PR#2 source (`git show c8174d0:index.html`) confirmed to contain the referenced B-text tokens (Shut Down, कसे उघडाल, Personalized Learning, Monitor आणि Keyboard).
- `git diff --stat` → `index.html | 32 +++, 22 insertions(+), 10 deletions(-)` — changes limited to the 4 इयत्ता blankings and 6 OR pairs, nothing else.

All acceptance criteria satisfied. No MCQ options reordered; all answer captures remain blank; every OR-alternative is bilingual (Marathi primary + `<span class="q-en">English</span>`) with English technical tokens intact.
