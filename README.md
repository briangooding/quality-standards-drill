# Quality Standards Drill

A single-page quiz for learning ISO 9001, IATF 16949 and measurement systems analysis (MSA), with a fourth deck on writing to those standards.

## Open the app

**https://briangooding.github.io/quality-standards-drill/**

That address works once GitHub Pages is turned on for this repository:

1. Go to **Settings → Pages** in this repository.
2. Under **Build and deployment**, set **Source** to **Deploy from a branch**.
3. Choose branch `main` and folder `/ (root)`, then **Save**.
4. Wait about a minute and reload the address above.

You can also run it without GitHub: download `index.html` and open it in any browser. It needs an internet connection only for its fonts, and falls back to system fonts without one.

To put it on a phone's home screen, open the address in the browser and choose **Add to Home Screen** from the share or browser menu.

## What is in it

| Deck | Multiple choice | Written prompts | Covers |
| --- | --- | --- | --- |
| ISO 9001 | 20 | 3 | Clause structure, terminology and core requirements of the 2015 edition |
| IATF 16949 | 22 | 3 | Automotive supplements, core tools, audit rules, PPAP |
| MSA | 20 | 3 | Gauge R&R, bias, linearity, stability, attribute studies, worked calculations |
| Writing to the standard | 15 | 2 | Requirement verbs, nonconformity statements, citations, reporting results |

## How to use it

### 1. Set up a session

- **Decks**: tap a deck to include or leave it out. The bar on each deck shows how many of its questions you have mastered.
- **Format**: *Multiple choice* or *Write it out*.
- **Questions**: 10, 20 or all available.
- **Include**: *Everything*, or *New and missed* to drill only questions you have not yet answered correctly.

Press **Start**.

### 2. Multiple choice

Pick one of four options by clicking it or pressing keys `1` to `4`. The app then shows whether you were right, a short explanation and the source clause. Press `Enter` or **Next question** to continue.

### 3. Write it out

Type your answer in the box as you would in a report or procedure. Press **Compare with model answer** to see a model answer and a list of the points a full answer includes. Then mark yourself: **Covered every point** or **Missed something**. The app does not grade your text, so the mark is only as honest as you are.

### 4. Results

The results screen shows your score, a breakdown by deck and every question you missed with its correct answer and clause. **Retry the missed** runs those questions again. **New session** returns to setup.

The strip of dots above each question tracks the session: a dot above the line is a correct answer, below the line is a miss.

## Progress and privacy

A question counts as **mastered** when your most recent answer to it was correct. The count in the page header covers multiple-choice questions only.

Progress is stored in your browser's local storage, on that device only. Nothing is sent anywhere, and there are no accounts. This also means:

- Progress does not carry between devices or browsers.
- Clearing site data, or using a private window, clears it.
- **Reset progress** on the setup screen clears it on purpose.

## Sources and accuracy

Questions are written against:

- ISO 9001:2015
- IATF 16949:2016
- AIAG Measurement Systems Analysis reference manual, 4th edition
- AIAG PPAP manual, 4th edition, and ISO 9000:2015 for definitions

The questions and clause references were written from working knowledge of these documents, not transcribed from them, and no standard text is reproduced. Before quoting a clause number in formal work, check it against your own copy of the standard, the edition your organisation is certified to, and current IATF Sanctioned Interpretations.

## Editing the questions

Everything lives in `index.html`. Near the top of the `<script>` block:

- `MC` holds the multiple-choice questions, grouped by deck (`iso`, `iatf`, `msa`, `write`). Each entry is:

  ```js
  ["Source clause", "Question text", ["Correct answer", "Wrong", "Wrong", "Wrong"], "Explanation"]
  ```

  The correct answer always goes first. The app shuffles the options when it shows them.

- `WR` holds the written prompts:

  ```js
  ["Source clause", "Prompt", "Model answer", ["Key point", "Key point"]]
  ```

Add new entries at the end of a deck. Saved progress is keyed by a question's position, so inserting or reordering entries would attach old results to the wrong questions.

Commit the change to `main` and GitHub Pages republishes the site within a minute or two.
