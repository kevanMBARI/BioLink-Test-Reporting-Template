# ONR BioLink — Test Report Template

> **How to use this file.** Copy this template into a new markdown file for each
> test (suggested name: `TR-<NN>_<short-title>.md`), fill in every field, and add
> a hyperlink to it from the relevant entry in the ICD. Delete the guidance text
> in *italics* as you go. Use the **Engineering** variant for TT1 (physical &
> fluidic) work and the **Chemistry** variant for TT2 (molecular & reagent) work;
> the header and the Purpose/Conclusions sections are shared so anyone — engineer
> or molecular biologist — can read a report from the other team and understand it.

---

## 1. Header (shared)

| Field | Entry |
|---|---|
| **Test ID** | *TR-NN (unique; referenced from the ICD)* |
| **Title** | *Short, plain-language description of the test* |
| **Date(s)** | *YYYY-MM-DD (start–end if multi-day)* |
| **Author / Owner** | *Name(s)* |
| **Tiger Team** | *TT1 Physical & Fluidic  /  TT2 Molecular & Reagent* |
| **ICD reference** | *Subsystem + interface this test informs (e.g., Sampler→MW fluidic). Add a back-link in the ICD to this file.* |
| **Requirement(s) addressed** | *"Shall" statement(s) this test validates, or "exploratory — no requirement yet"* |
| **Status** | *Planned / In progress / Complete* |
| **Version** | *v0.1, v0.2 … (bump on edits)* |

---

## 2. Purpose & rationale (shared — *do not skip*)

**Question being answered.**
*State, in one or two sentences, the specific question this test is asking. (e.g., "Does an unpolished field lysate inhibit PCR amplification relative to a 0.2 µm polished lysate?")*

**Why this test / why these conditions.**
*This is the part that gets lost over time, so capture it explicitly. If you ran a 1:5, 1:10, and 1:1000 dilution series, say why those points were chosen and what each is meant to reveal.*

**What is being isolated.**
*Name the single variable or step this test isolates, and what is being held constant. Helps a reader who isn't living in this experiment day-to-day.*

**Hypothesis / expected outcome.**
*What you expected before running it.*

---

## 3. Test design (use the variant that fits)

<details>
<summary><strong>3A. Engineering variant (TT1)</strong></summary>

**Setup / hardware configuration.**
*Chip version, dock/base module, pump(s), valves, fittings, sensors. Link to SolidWorks/CAD or a photo if helpful.*

**Variables & set points.**

| Parameter | Value / range | Notes |
|---|---|---|
| *Volume moved (point A → point B)* | | |
| *Flow rate / speed* | | |
| *Drive pressure (gas / hydraulic slug)* | | |
| *Temperature / thermal profile* | | |
| *Actuation (valve, injection loop)* | | |

**Procedure.**
*Numbered steps, or a link to the protocol / fluid-movement document. For fluidic moves, follow the "from A to B, volume, process" table convention so it stays interpretable.*

**Controls.**
*Blanks, dry runs, baseline configurations.*

</details>

<details>
<summary><strong>3B. Chemistry variant (TT2)</strong></summary>

**Samples / lysates.**

| Item | Detail |
|---|---|
| *Source (live cells / archived / field)* | |
| *Polished vs. unpolished* | |
| *Filter porosity (e.g., 5 µm, 0.2 µm)* | |
| *Freeze/thaw history* | |

**Reagents.**
*Polymerase (lyophilized? inhibitor sensitivity), lysis reagents, primer set (commercial vs. custom/integrated index), click-chemistry modification, amplicon length, lot numbers.*

**Conditions tested.**

| Parameter | Value / range | Notes |
|---|---|---|
| *Dilution(s)* | | |
| *Annealing temp (range tested)* | | |
| *Cycle profile* | | |
| *Other* | | |

**Procedure.**
*Numbered steps or link to protocol.*

**Controls.**
*NTC, no-template blank, bench-top comparison, etc.*

</details>

---

## 4. Data captured (shared)

| Field | Entry |
|---|---|
| **Data types** | *e.g., fragment-analysis traces, pressure logs, temperature curves, gel images, sequencing yield* |
| **Validation metric** | *The pass/fail or quality criterion (e.g., expected ~280 bp amplicon, target recovery %, leak threshold, ±20% volume precision)* |
| **Raw data location** | *Path / repo link / Box folder* |
| **Replicates** | *N and how counted* |

**Workbook links** — pick the source of truth and link the others as snapshots:

- **Live (Google Sheet, on the shared Drive):** [Test Data — Google Sheet](https://docs.google.com/spreadsheets/d/FILE_ID/edit)
  Deep-link to this test's rows with the tab gid + range, e.g. `…/edit#gid=TAB_GID&range=A2:Q3`. Opens live; requires Drive access; does not render inside GitHub.
- **Working file (repo, has dropdowns):** [`Test Data Workbook`](../data/BioLink_Test_Data_Workbook.xlsx) — downloads; no in-browser preview.
- **Browseable snapshot (repo CSVs):** [Chemistry Log](../data/chemistry_log.csv) · [Engineering Log](../data/engineering_log.csv) · [Test Register](../data/test_register.csv)
  CSVs render as searchable tables on GitHub. Deep-link a row by clicking its row number and copying the URL (e.g. `…/chemistry_log.csv#L2`).

> Use the **same link target in the ICD entry** for this test so the ICD, the report, and the data all point at one another. If the Google Sheet is the source of truth, a scheduled export (`…/export?format=csv&gid=TAB_GID`) keeps the repo CSVs in sync automatically.

---

## 5. Results (shared)

*Summarize in a table where possible; keep it interpretable for a reader outside the discipline.*

| Condition | Output / measurement | Pass against metric? |
|---|---|---|
| | | |
| | | |

*Add figures/plots with one-line captions explaining what to look at.*

---

## 6. Interpretation & conclusions (shared)

**Findings.**
*What the data showed, in plain language.*

**Against the requirement / spec.**
*Did it meet the "shall" statement or the validation metric? If exploratory, what did it tell us about the design space?*

**Implications & next steps.**
*What changes for the design, what the next test should be, who owns it.*

**Open questions.**
*Anything unresolved — including cross-team items (e.g., suspected polymerase × lysis-reagent incompatibility).*

---

*Template v1.0 — ONR BioLink Middleware Project. Linked from the ICD master index.*
