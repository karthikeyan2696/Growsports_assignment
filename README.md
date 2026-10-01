# WI vs IND 2nd ODI 2026 --- Ball-by-Ball Analysis

**Match:** West Indies vs India, 2nd ODI\
**Date:** 30 September 2026\
**Venue:** Barsapara Cricket Stadium, Guwahati\
**Result:** India won by 8 wickets\
**Player of the Match:** Shubman Gill

This project provides a reproducible ball-by-ball match analysis.

**Workflow:** `IndiaVsWI_2ndODI.csv` → `IndiaVsWI_2ndODI.ipynb` →
`IndiaVsWI_2ndODI_analysis.pdf`

## Project Files

  File                              Purpose
  --------------------------------- -------------------------------------------
  `IndiaVsWI_2ndODI.csv`            Final cleaned ball-by-ball input dataset
  `IndiaVsWI_2ndODI.ipynb`          Analysis notebook and PDF-generation code
  `IndiaVsWI_2ndODI_analysis.pdf`   Final generated analysis report

## Dataset

The CSV contains **585 delivery-event rows** and **27 columns**.

-   West Indies: **312 delivery events**, **300 legal balls**
-   India: **273 delivery events**, **261 legal balls**
-   Match total: **585 delivery events**, **561 legal balls**

Wides and no-balls are retained as delivery events, so **585 is not the
number of legal deliveries**.

The notebook uses `actual_delivery` for cricket over/ball notation and
identifies legal deliveries by excluding wides and no-balls.

## Verified Match Totals

  Metric           West Indies   India
  -------------- ------------- -------
  Score                  405/7   406/2
  Overs                   50.0    43.3
  Runs off bat             382     384
  Extras                    23      22
  Fours                     38      41
  Sixes                     12      15
  Wides                     20      17
  No-balls                   1       3

India completed the chase with **39 legal balls remaining**.

## Key Batting Performances

-   **Shubman Gill:** 223\* off 133 balls
-   **Rohit Sharma:** 101 off 75 balls
-   **A. Jangoo:** 114 off 77 balls
-   **Shai Hope:** 104 off 94 balls
-   **John Campbell:** 101 off 68 balls

## Key Partnerships

-   **Rohit Sharma -- Shubman Gill:** 255 runs from 157 balls
-   **Shubman Gill -- Virat Kohli:** 65 runs from 34 balls
-   **Shubman Gill -- Ruturaj Gaikwad:** 86 runs from 68 balls
-   **A. Jangoo -- Shai Hope:** 182 runs from 130 balls

## Bowling Notes

Bowler-conceded runs are calculated as **runs off the bat + wides +
no-balls**. Byes and leg-byes are excluded.

Key figures in the final analysis include:

-   **Gurnoor Brar:** 2/96
-   **Kuldeep Yadav:** 2/65
-   **Ravindra Jadeja:** 2/75
-   **Jayden Seales:** 1/78
-   **Shamar Joseph:** 1/52
-   **Vitel Lawes:** 0/73

## Notebook

`IndiaVsWI_2ndODI.ipynb` contains **68 cells** and performs the complete
workflow:

1.  Imports libraries and defines chart/report palettes
2.  Loads `IndiaVsWI_2ndODI.csv`
3.  Derives match metadata
4.  Pre-processes delivery data
5.  Identifies legal balls, wickets, dots and boundaries
6.  Assigns Powerplay, Middle and Death phases
7.  Calculates batting, bowling and phase statistics
8.  Calculates score progression and run rates
9.  Calculates fall of wickets and partnerships
10. Generates analytical charts
11. Builds the ReportLab report
12. Saves `IndiaVsWI_2ndODI_analysis.pdf`

### Calculation Definitions

-   **Legal ball:** neither a wide nor a no-ball
-   **Dot ball:** legal delivery on which the batting team scores zero
    runs
-   **Bowler runs conceded:** runs off bat + wides + no-balls; excludes
    byes and leg-byes
-   **Powerplay:** overs 1--10
-   **Middle:** overs 11--40
-   **Death:** overs 41--50

## Final PDF

Running the notebook generates `IndiaVsWI_2ndODI_analysis.pdf`.

The final report is **18 pages** and includes match summary, scoring
progression, over-by-over and phase analysis, batting and bowling
analysis, fall of wickets, partnerships, boundary/dot-ball analysis,
run-rate analysis, player comparisons, and match conclusions.

## How to Run

Keep these two input files in the same directory:

``` text
IndiaVsWI_2ndODI.csv
IndiaVsWI_2ndODI.ipynb
```

Open the notebook and run all cells from top to bottom. The notebook
uses:

``` python
MATCH = 'IndiaVsWI_2ndODI'
CSV_PATH = f'./{MATCH}.csv'
OUT_PDF = f'./{MATCH}_analysis.pdf'
```

After a successful run, the same directory will contain:

``` text
IndiaVsWI_2ndODI_analysis.pdf
```

## Reproducibility

The final project is designed as:

``` text
Final cleaned CSV
        ↓
Jupyter Notebook analysis
        ↓
Charts + calculated statistics
        ↓
18-page analysis PDF
```

Use the final CSV, notebook and generated PDF together.
