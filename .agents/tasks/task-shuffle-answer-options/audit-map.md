# Audit Map — Shuffle Answer Options

Source-of-truth map for FEAT-002 / FEAT-003. For every shufflable answer block across all 5 content files it records:
- **Correct TEXT** — the exact answer text (identity that must be preserved, only its position moves).
- **Current** — the option letter the correct answer sits at today.
- **Planned** — the new option letter it should occupy after shuffling.

Rules applied when choosing planned positions:
- 4-option MCQ uses A/B/C/D; 3-option fill-in uses A/B/C.
- Per paper the correct answers are spread across letters (no single letter dominates, no trivially guessable repeating pattern such as all-B or A,B,C,D,A,B,C,D).
- For match sections the Column-B order is planned so the naive straight-line 1→A, 2→B, 3→C, 4→D is broken while the *semantic* pairing (item → its meaning) stays intact.
- index.html has NO answer key: the current FIRST option (A / [A]) is the correct answer per the confirmed authoring pattern, so its text is captured as correct.
- The AI paper's correct answers come from `AI_Exam_Model_Answer_Key.md` (authoritative).

Coverage: index.html = 69 MCQ blocks + 3 fill-in blocks (72 `options-list`) + 10 `match-grid` tables; AI paper = 10 MCQ + 5 fill-in + 1 match; Computer markdown = Std 1 & Std 2 (must stay consistent with index.html paper-std-1 / paper-std-2).

---

## 1. index.html

### paper-std-1 (Std 1) — 5 MCQ + 3 fill-in + 1 match
Planned MCQ letters: B, D, C, A, C (spread). Fill-in: C, B, C.

| Q | Correct TEXT | Current | Planned |
| :-- | :-- | :--: | :--: |
| Q.1 | मॉनिटर — Monitor | A | B |
| Q.2 | कीबोर्ड — Keyboard | A | D |
| Q.3 | माउस — Mouse | A | C |
| Q.4 | CPU — सीपीयू | A | A |
| Q.5 | कीबोर्ड — Keyboard | A | C |
| Q.6 (fill) | Monitor — मॉनिटर | A | C |
| Q.7 (fill) | Keyboard — कीबोर्ड | A | B |
| Q.8 (fill) | Mouse — माउस | A | C |

**Match (Std 1)** — semantic pairs: Monitor→Seeing screen, Keyboard→Typing, Mouse→Selecting, CPU→Processing.
Current Column B order: A.Typing, B.Seeing screen, C.Selecting, D.Processing.

**FINAL Std 1 match plan** (Column B reordered; semantic answer = letter now holding that item's meaning):
| Col B row order (re-lettered) | Text |
| :--: | :-- |
| A | Processing — प्रक्रिया करणे |
| B | Selecting — निवड करणे |
| C | Seeing screen — स्क्रीन पाहणे |
| D | Typing — टायपिंग करणे |

Resulting correct answer code: **Monitor→C, Keyboard→D, Mouse→B, CPU→A** (no 1→A/2→B/3→C/4→D straight line).

### paper-std-2 (Std 2) — 5 MCQ + 1 match
Planned MCQ letters: C, A, D, B, C.

| Q | Correct TEXT | Current | Planned |
| :-- | :-- | :--: | :--: |
| Q.1 | Keyboard — कीबोर्ड | A | C |
| Q.2 | Clicking and selecting — क्लिक व निवड करण्यासाठी | A | A |
| Q.3 | To see information — माहिती व चित्रे पाहण्यासाठी | A | D |
| Q.4 | Processing — प्रक्रिया | A | B |
| Q.5 | Keyboard — कीबोर्ड | A | C |

**Match (Std 2)** — semantic pairs: Keyboard→Typing, Mouse→Clicking, Monitor→Screen, CPU→Processing.
Current Col B: A.Screen, B.Typing, C.Processing, D.Clicking.
**FINAL plan** Col B reorder (re-lettered): A.Clicking, B.Screen, C.Typing, D.Processing.
Resulting code: **Keyboard→C, Mouse→A, Monitor→B, CPU→D** (straight line broken).

### paper-std-3 (Std 3) — 5 MCQ + 1 match
Planned MCQ letters: D, B, A, C, D.

| Q | Correct TEXT | Current | Planned |
| :-- | :-- | :--: | :--: |
| Q.1 | काम जलद करण्यासाठी | A | D |
| Q.2 | Keyboard — कीबोर्ड | A | B |
| Q.3 | Monitor — मॉनिटर | A | A |
| Q.4 | Processing — प्रक्रिया करणे | A | C |
| Q.5 | Click — क्लिक | A | D |

**Match (Std 3)** — semantic pairs: Keyboard→Typing, Mouse→Clicking, Monitor→Display, CPU→Processing.
Current Col B: A.Processing, B.Clicking, C.Typing, D.Display.
**FINAL plan** Col B reorder (re-lettered): A.Display, B.Typing, C.Processing, D.Clicking.
Resulting code: **Keyboard→B, Mouse→D, Monitor→A, CPU→C** (straight line broken).

### paper-std-4 (Std 4) — 5 MCQ + 1 match
Planned MCQ letters: D, A, C, B, A.

| Q | Correct TEXT | Current | Planned |
| :-- | :-- | :--: | :--: |
| Q.1 | वरील सर्व — All of above | D | D |
| Q.2 | संगणकाला दिलेली माहिती | A | A |
| Q.3 | संगणकाने दिलेला अंतिम निकाल | A | C |
| Q.4 | Keyboard and Mouse | A | B |
| Q.5 | Central Processing Unit | A | A |

Note: Q.1 correct is already "All of above" at D (not A); keep at D. Distribution: D,A,C,B,A — spread.

**Match (Std 4)** — semantic pairs: Input→"संगणकाला दिलेली माहिती", Output→"संगणकाने दाखवलेला निकाल", Keyboard→Typing, Monitor→Display.
Current Col B: A.Typing, B."संगणकाला दिलेली माहिती", C."संगणकाने दाखवलेला निकाल", D.Display.
**FINAL plan** Col B reorder (re-lettered): A."संगणकाने दाखवलेला निकाल", B.Display, C."संगणकाला दिलेली माहिती", D.Typing.
Resulting code: **Input→C, Output→A, Keyboard→D, Monitor→B** (straight line broken).

### paper-std-5 (Std 5) — 8 MCQ + 1 match
Planned MCQ letters: B, D, A, B, C, D, A, C.

| Q | Correct TEXT | Current | Planned |
| :-- | :-- | :--: | :--: |
| Q.1 | माहितीवर प्रक्रिया करणारे इलेक्ट्रॉनिक साधन | A | B |
| Q.2 | वरील सर्व — All of above | D | D |
| Q.3 | Input — इनपुट | A | A |
| Q.4 | Output — आउटपुट | A | B |
| Q.5 | Artificial Intelligence (कृत्रिम बुद्धिमत्ता) | A | C |
| Q.6 | Space Button | C | D |
| Q.7 | माहिती व चित्रे दाखवणे | A | A |
| Q.8 | अक्षरे व संख्या टाईप करणे | A | C |

Note: Q.2 already at D; Q.6 correct is "Space Button" currently at C (move to D). Distribution B,D,A,B,C,D,A,C — spread across all four letters.

**Match (Std 5)** — semantic pairs: Monitor→Display, Keyboard→Typing, Mouse→Clicking, CPU→Processing.
Current Col B: A.Clicking, B.Processing, C.Display, D.Typing.
**FINAL plan** Col B reorder (re-lettered): A.Typing, B.Display, C.Processing, D.Clicking.
Resulting code: **Monitor→B, Keyboard→A, Mouse→D, CPU→C** (straight line broken).

### paper-std-6 (Std 6) — 8 MCQ + 1 match
Planned MCQ letters: C, D, A, B, D, A, B, D.

| Q | Correct TEXT | Current | Planned |
| :-- | :-- | :--: | :--: |
| Q.1 | Input घेणे, प्रक्रिया करणे आणि Output देणे | A | C |
| Q.2 | वरील सर्व — All of above | D | D |
| Q.3 | Monitor — मॉनिटर | A | A |
| Q.4 | Brain — मेंदू | A | B |
| Q.5 | प्रोग्राम दर्शवणारे छोटे चित्र/चिन्ह | A | D |
| Q.6 | त्याच्या Icon वर Double-Click करून | A | A |
| Q.7 | Power button | A | B |
| Q.8 | वरील सर्व — All of above | D | D |

Distribution C,D,A,B,D,A,B,D — spread (no single letter dominating unduly; D used for the genuine "All of above" answers).

**Match (Std 6)** — semantic pairs: CPU→"संगणकाचा मेंदू", Monitor→"स्क्रीनवर माहिती दाखवणे", Icon→"प्रोग्रॅमचे छोटे चित्र", Mouse→"पॉइंटिंग व क्लिकिंग उपकरण".
Current Col B: A."स्क्रीनवर माहिती दाखवणे", B."संगणकाचा मेंदू", C."पॉइंटिंग व क्लिकिंग उपकरण", D."प्रोग्रॅमचे छोटे चित्र".
**FINAL plan** Col B reorder (re-lettered): A."प्रोग्रॅमचे छोटे चित्र", B."पॉइंटिंग व क्लिकिंग उपकरण", C."संगणकाचा मेंदू", D."स्क्रीनवर माहिती दाखवणे".
Resulting code: **CPU→C, Monitor→D, Icon→A, Mouse→B** (straight line broken).

### paper-std-7 (Std 7) — 8 MCQ + 1 match
Planned MCQ letters: D, B, C, A, B, A, D, C.

| Q | Correct TEXT | Current | Planned |
| :-- | :-- | :--: | :--: |
| Q.1 | वरील सर्व — All of above | D | D |
| Q.2 | Keyboard — कीबोर्ड | A | B |
| Q.3 | Monitor — मॉनिटर | A | C |
| Q.4 | Processing — प्रक्रिया करणे | A | A |
| Q.5 | कामाची कार्यक्षमता वाढवणे | A | B |
| Q.6 | AI ने दिलेली माहिती पडताळून पाहावी | A | A |
| Q.7 | त्याच्या Icon वर Click/Double-click | A | D |
| Q.8 | Artificial Intelligence (कृत्रिम बुद्धिमत्ता) | A | C |

Distribution D,B,C,A,B,A,D,C — spread across all four.

**Match (Std 7)** — semantic pairs: CPU→Processing, Mouse→Selecting, Monitor→Display, Keyboard→Typing.
Current Col B: A.Typing, B.Processing, C.Display, D.Selecting.
**FINAL plan** Col B reorder (re-lettered): A.Display, B.Selecting, C.Processing, D.Typing.
Resulting code: **CPU→C, Mouse→B, Monitor→A, Keyboard→D** (straight line broken).

### paper-std-8 (Std 8) — 7 MCQ + 1 match
Planned MCQ letters: A, C, B, D, A, C, B.

| Q | Correct TEXT | Current | Planned |
| :-- | :-- | :--: | :--: |
| Q.1 | Input → Processing → Output | A | A |
| Q.2 | काम जलद आणि सोपे करण्यासाठी | A | C |
| Q.3 | मशीनला बुद्धिमान कार्ये करण्यास सक्षम करणारे तंत्रज्ञान | A | B |
| Q.4 | वरील सर्व — All of above | D | D |
| Q.5 | महत्त्वाची माहिती तपासावी व पडताळावी | A | A |
| Q.6 | Program ओळखण्यास व उघडण्यास मदत करणे | A | C |
| Q.7 | Start मेनूमधील 'Shut Down' वापरणे | A | B |

Distribution A,C,B,D,A,C,B — spread.

**Match (Std 8)** — semantic pairs: Input→"संगणकाला दिलेली माहिती", Output→"प्रक्रियेनंतर मिळालेला निकाल", AI→"कृत्रिम बुद्धिमत्ता", Icon→"Program चे छोटे चिन्ह".
Current Col B: A."Program चे छोटे चिन्ह", B."कृत्रिम बुद्धिमत्ता", C."संगणकाला दिलेली माहिती", D."प्रक्रियेनंतर मिळालेला निकाल".
**FINAL plan** Col B reorder (re-lettered): A."कृत्रिम बुद्धिमत्ता", B."संगणकाला दिलेली माहिती", C."प्रक्रियेनंतर मिळालेला निकाल", D."Program चे छोटे चिन्ह".
Resulting code: **Input→B, Output→C, AI→A, Icon→D** (straight line broken).

### paper-std-9 (Std 9) — 8 MCQ + 1 match
Planned MCQ letters: B, A, C, A, B, D, A, D.

| Q | Correct TEXT | Current | Planned |
| :-- | :-- | :--: | :--: |
| Q.1 | डेटा स्वीकारून त्यावर प्रक्रिया करून उपयुक्त निकाल देणारे इलेक्ट्रॉनिक साधन | A | B |
| Q.2 | काम जलद, अचूक आणि कार्यक्षम करण्यासाठी | A | A |
| Q.3 | कीबोर्डने टाईप केलेले नाव किंवा संख्या | A | C |
| Q.4 | स्क्रीनवर दिसणारा निकाल | A | A |
| Q.5 | सूचनांवर आणि डेटावर प्रक्रिया करणे | A | B |
| Q.6 | समस्या सोडवण्यास आणि कठीण कार्ये स्वयंचलित करण्यास | A | D |
| Q.7 | महत्त्वाच्या माहितीची सत्यता पडताळावी | A | A |
| Q.8 | वरील सर्व — All of above | D | D |

Distribution B,A,C,A,B,D,A,D — spread across all four.

**Match (Std 9)** — semantic pairs: CPU→Processing, Monitor→Display, Keyboard→Typing, Mouse→"Intelligent Technology"(as authored — Mouse paired with the remaining Col B item).
Current Col B: A.Typing, B."Intelligent Technology", C.Processing, D.Display.
Note: this table's semantic mapping as authored is CPU→C.Processing, Monitor→D.Display, Keyboard→A.Typing, Mouse→B."Intelligent Technology" (already not a straight line). Preserve those semantic pairs, reorder Col B so letters differ.
**FINAL plan** Col B reorder (re-lettered): A.Processing, B.Display, C."Intelligent Technology", D.Typing.
Resulting code: **CPU→A, Monitor→B, Keyboard→D, Mouse→C** (no 1→A..4→D straight line; semantic pairs intact).

### paper-std-10 (Std 10) — 10 MCQ + 1 match
Planned MCQ letters: C, D, A, B, A, C, A, D, A, B.

| Q | Correct TEXT | Current | Planned |
| :-- | :-- | :--: | :--: |
| Q.1 | Input → Processing → Output | A | C |
| Q.2 | वरील सर्व — All of above | D | D |
| Q.3 | Keyboard, Mouse | A | A |
| Q.4 | Monitor, Speaker | A | B |
| Q.5 | कारण ते सर्व सूचना आणि डेटावर प्रक्रिया करते | A | A |
| Q.6 | मानवी बुद्धिमत्ता आवश्यक असणारी कार्ये करण्यास मशीनला सक्षम करणारे तंत्रज्ञान | A | C |
| Q.7 | महत्त्वाची माहिती पडताळून पाहणे (Verification) | A | A |
| Q.8 | वरील सर्व — All of above | D | D |
| Q.9 | संबंधित Icon वर Double-click करणे | A | A |
| Q.10 | Start मेनूमधून 'Shut Down' पर्याय वापरणे | A | B |

Distribution C,D,A,B,A,C,A,D,A,B — spread across all four (A appears for several but not all; no trivially guessable repeating pattern).

**Match (Std 10)** — semantic pairs: Input→"संगणकाला दिलेली माहिती", Output→"तयार झालेला अंतिम निकाल", Monitor→"माहिती दाखवणे (Display)", CPU→"डेटावर प्रक्रिया करणे (Processing)".
Current Col B: A."माहिती दाखवणे (Display)", B."संगणकाला दिलेली माहिती", C."डेटावर प्रक्रिया करणे (Processing)", D."तयार झालेला अंतिम निकाल".
**FINAL plan** Col B reorder (re-lettered): A."डेटावर प्रक्रिया करणे (Processing)", B."तयार झालेला अंतिम निकाल", C."संगणकाला दिलेली माहिती", D."माहिती दाखवणे (Display)".
Resulting code: **Input→C, Output→B, Monitor→D, CPU→A** (straight line broken).

---

## 2. AI_Exam_Question_Paper.html + AI_Exam_Question_Paper.md (must stay in sync with each other)

Correct answers are AUTHORITATIVE from `AI_Exam_Model_Answer_Key.md`:
MCQ Q1–Q10 = A,B,A,A,A,A,A,D,B,A · Fill-in Q11–Q15 = A,A,B,A,A · Match 1→C,2→A,3→B,4→D.

### Section A — MCQ (10)
Planned letters: C, D, B, A, C, B, D, D, B, C (spread; Q8 stays D since correct is genuinely "All of the above").

| Q | Correct TEXT (English / short) | Current | Planned |
| :-- | :-- | :--: | :--: |
| Q.1 | Technology enabling machines to perform tasks requiring human intelligence (मानवाच्या बुद्धिमत्तेची आवश्यकता असलेली कार्ये मशीनद्वारे करण्यास सक्षम करणारे तंत्रज्ञान) | A | C |
| Q.2 | Artificial Intelligence (कृत्रिम बुद्धिमत्ता) | B | D |
| Q.3 | To help solve problems and perform tasks (समस्या सोडवण्यास आणि कार्ये जलद करण्यास मदत करण्यासाठी) | A | B |
| Q.4 | Voice recognition in digital assistants (डिजिटल असिस्टंटमधील आवाज ओळखण्याची सुविधा) | A | A |
| Q.5 | Data — डेटा / माहिती | A | C |
| Q.6 | प्रणालीला अभ्यासासाठी दिलेली माहिती (Data given to system) | A | B |
| Q.7 | प्रणालीने प्रक्रियेनंतर तयार केलेली माहिती किंवा निकाल (Result) | A | D |
| Q.8 | All of the above (वरील सर्व क्षेत्रे) | D | D |
| Q.9 | तिची मानवाकडून प्रत्यक्ष पडताळणी (Verification) करणे आवश्यक असू शकते | B | B |
| Q.10 | Machine Learning (मशीन लर्निंग) | A | C |

Distribution C,D,B,A,C,B,D,D,B,C — spread across all four letters, no straight A pattern.

### Section B — Fill in the Blanks (5)
Planned letters: C, B, A, D, B.

| Q | Correct TEXT | Current | Planned |
| :-- | :-- | :--: | :--: |
| Q.11 | AI — एआय | A | C |
| Q.12 | Input — इनपुट | A | B |
| Q.13 | Output — आउटपुट | B | A |
| Q.14 | Dataset — डेटासेट | A | D |
| Q.15 | Patterns — नमुने | A | B |

Distribution C,B,A,D,B — spread. Note Q.13 correct is already at B (Output) → move to A.

### Section D — Match (4)
Semantic pairs (from answer key): AI→C."बुद्धिमान मशीनच्या कार्याशी संबंधित तंत्रज्ञान", Input→A."प्रणालीला अभ्यासासाठी दिलेली माहिती", Machine Learning→B."डेटामधून नमुने शिकणे", Output→D."प्रणालीने तयार केलेला परिणाम".
Current Col B order: A.Input-data, B.Learning-patterns, C.Intelligent-tech, D.Result. (Existing code already 1→C,2→A,3→B,4→D — Input at 2→A and ML at 3→B are straight-ish.)
**FINAL plan** Col B reorder (re-lettered): A."बुद्धिमान मशीनच्या कार्याशी संबंधित तंत्रज्ञान", B."प्रणालीने तयार केलेला परिणाम", C."प्रणालीला अभ्यासासाठी दिलेली माहिती", D."डेटामधून नमुने शिकणे".
Resulting code: **AI→A, Input→C, Machine Learning→D, Output→B** (straight line fully broken; semantic pairs intact).

**AI_Exam_Model_Answer_Key.md must be updated** to the new positions:
- MCQ table बरोबर पर्याय column: Q1=C, Q2=D, Q3=B, Q4=A, Q5=C, Q6=B, Q7=D, Q8=D, Q9=B, Q10=C.
- Fill-in Q11–Q15: C, B, A, D, B.
- Match Answer Code: १—A, २—C, ३—D, ४—B (i.e. AI→A, Input→C, ML→D, Output→B).

Both AI_Exam_Question_Paper.html (options-grid / opt-item / match-table) and AI_Exam_Question_Paper.md (`- [ ] **A)**` list + `[ A) .. | B) .. ]` fill-in + match table) must be re-lettered and reordered identically.

---

## 3. Computer_Std_1_to_10_Question_Papers.md (Std 1 & Std 2 only)

This file mirrors index.html paper-std-1 and paper-std-2 question-for-question. It MUST end up identical in answer positions to the corresponding index.html papers after shuffling. Apply the SAME plans as index.html Std 1 and Std 2 above.

### Std 1 (markdown) — apply index.html paper-std-1 plan
- MCQ Q.1–Q.5 planned: B, D, C, A, C.
- Fill-in Q.6–Q.8 planned: C, B, C.
- Match: reorder Column B to A.Processing, B.Selecting, C.Seeing screen, D.Typing → code Monitor→C, Keyboard→D, Mouse→B, CPU→A.

| Q | Correct TEXT | Current | Planned |
| :-- | :-- | :--: | :--: |
| Q.1 | मॉनिटर (Monitor) | A | B |
| Q.2 | कीबोर्ड (Keyboard) | A | D |
| Q.3 | माउस (Mouse) | A | C |
| Q.4 | CPU | A | A |
| Q.5 | कीबोर्ड (Keyboard) | A | C |
| Q.6 (fill) | Monitor | A | C |
| Q.7 (fill) | Keyboard | A | B |
| Q.8 (fill) | Mouse | A | C |

### Std 2 (markdown) — apply index.html paper-std-2 plan
- MCQ Q.1–Q.5 planned: C, A, D, B, C.
- Match: reorder Column B to A.Clicking, B.Screen, C.Typing, D.Processing → code Keyboard→C, Mouse→A, Monitor→B, CPU→D.

| Q | Correct TEXT | Current | Planned |
| :-- | :-- | :--: | :--: |
| Q.1 | Keyboard | A | C |
| Q.2 | Clicking and selecting | A | A |
| Q.3 | To see information | A | D |
| Q.4 | Processing | A | B |
| Q.5 | Keyboard | A | C |

The Std 2 fill-in blocks (Q.6 Keyboard→Typing, Q.7 Mouse→Clicking, Q.8 Monitor→Information) and True/False (Q.9–Q.11) are answer-position stable (True/False and single-blank text answers); the fill-in option lists `[ A) .. | B) .. | C) .. ]` may be reordered for consistency but their correct text (Typing / Clicking / Information) stays the recorded answer. Suggested fill-in planned positions: Q.6→B, Q.7→C, Q.8→A.

---

## Distribution summary (per paper, correct-answer letters after plan)

| Paper | MCQ correct letters | Notes |
| :-- | :-- | :-- |
| index Std 1 | B,D,C,A,C (+fill C,B,C) | spread |
| index Std 2 | C,A,D,B,C | spread |
| index Std 3 | D,B,A,C,D | spread |
| index Std 4 | D,A,C,B,A | spread |
| index Std 5 | B,D,A,B,C,D,A,C | all four used |
| index Std 6 | C,D,A,B,D,A,B,D | all four used |
| index Std 7 | D,B,C,A,B,A,D,C | all four used |
| index Std 8 | A,C,B,D,A,C,B | all four used |
| index Std 9 | B,A,C,A,B,D,A,D | all four used |
| index Std 10 | C,D,A,B,A,C,A,D,A,B | all four used |
| AI MCQ | C,D,B,A,C,B,D,D,B,C | all four used |
| AI fill-in | C,B,A,D,B | all four used |

All match sections re-planned so the naive 1→A, 2→B, 3→C, 4→D pairing is never the answer, while every item still maps to its correct meaning.
