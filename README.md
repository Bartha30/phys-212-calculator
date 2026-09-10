# PHYS 212 Mark Calculator

A single-page grade calculator for **PHYS 212 (Fall 2026)**. Enter the points
you've earned in each category and it estimates your current standing and a
projected letter grade.

## Usage

Open `index.html` in any web browser. No build step, no dependencies, no server —
it's one self-contained HTML file with inline CSS and vanilla JavaScript.

## How it works

- Uses the syllabus point totals (1000 points total, plus 25 optional bonus):

  | Category                | Max |
  |-------------------------|-----|
  | Prelectures             | 25  |
  | Checkpoints             | 25  |
  | Lecture (Participation) | 50  |
  | Homework                | 130 |
  | Discussion quizzes      | 130 |
  | Labs                    | 120 |
  | Hour exam 1             | 80  |
  | Hour exam 2             | 80  |
  | Hour exam 3             | 80  |
  | Final exam              | 280 |
  | Bonus (optional)        | 25  |

- Type the points you've earned per category. Values are clamped to `[0, max]`;
  blank or invalid entries count as 0.
- The results panel updates live with projected total points, percent, a
  projected letter grade (based on fixed point cutoffs: A+ ≥ 970, A ≥ 930,
  A- ≥ 900, … D- ≥ 600, F < 600), and a progress bar.
- **Fill example** loads a sample mid-semester scenario; **Reset** clears all
  inputs.
- A light/dark theme toggle in the header switches between the two themes and
  remembers your choice in `localStorage` (key `phys212-theme`), defaulting to
  dark mode on first visit.

## Notes and limitations

- Drop rules and late penalties are not modeled — enter whatever your gradebook
  currently shows.
- Bonus points add to the numerator but don't change the /1000 denominator.
- Nothing is saved or transmitted; there is no persistence and no network access.
