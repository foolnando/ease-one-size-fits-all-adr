# One Size Fits All? — Replication Package

This repository contains the replication package (study instruments, raw data, and analysis outputs) for an empirical study that investigates **Architecture Decision Record (ADR) documentation models/templates**, focusing on a comparison between the **Nygard** and **MADR** templates.

The study combines a **DESMET-based** feature analysis (used to select the templates evaluated) with a **controlled, within-subjects experiment** in which participants documented architectural decisions using both templates, followed by quantitative (Likert/DESMET-style) and qualitative (open-ended, axially coded) data collection.

> **Note on anonymization:** Some materials (e.g., `guideline_experiments.pdf`) reference platform/form links as `<link_anonymized>` and `<feedback_form_anonymized>`, and the consent form has researcher/supervisor emails redacted as `XXXXXXX@XXX.com`. These were removed for participant/institution privacy prior to publishing this package.

## Study overview

1. **Template pre-selection (DESMET feature analysis).** Five candidate ADR models — **MADR, Tyree, Arc42, Nygard,** and **Y-statement** — were scored by two independent evaluators (`eng_Auth01`, `eng_Auth02`) across two example architectural decisions, using a DESMET feature-analysis scheme with three feature sets:
   - **FS1 — Structural Completeness** (FS1.01–FS1.03, indicator weight 0.15)
   - **FS2 — Efficiency and Usability** (FS2.01–FS2.04, indicator weight 0.50)
   - **FS3 — Adoption Potential** (FS3.01/FS3.03, indicator weight 0.35)

   Each feature set produces a sub-score (`SFS1`, `SFS2`, `SFS3`) that is combined into an overall score (`OS`) per template. **MADR** and **Nygard** obtained the highest overall scores and were selected as the two templates compared in the subsequent experiment.

2. **Participant characterization.** Before the task, participants filled out a characterization form covering their software architecture / development background and prior experience with architectural decision-making.

3. **Experimental task.** Each participant produced ADRs using **both** templates (within-subjects design), assigned to one of two counterbalancing groups (`grupo_A` / `grupo_B`) that control the presentation order of MADR vs. Nygard. Steps followed by participants are in `guideline_experiments.pdf`.

4. **Post-task data collection.**
   - A **DESMET-based post-experimental questionnaire** (`post-experimental questionaire.pdf`) capturing perceived clarity, completeness, objectivity, effort, and likelihood to recommend each template (feature codes FS1.01–FS3.03, matching the pre-selection scheme). Answers were tabulated in `quantitative results.xlsx`.
   - A **research feedback questionnaire** (`feedback_questionaires_questions.pdf`) with open-ended questions comparing the two templates (overall preference, most/least useful or difficult fields, likes/dislikes). Answers were tabulated in `feedback_answer.xlsx`.

5. **Qualitative analysis.** Open-ended answers were analyzed via axial coding; coded quotes and derived codes/categories are in `results_axial_coding.pdf`.

6. **Training materials.** Participants were introduced to architectural decisions and ADRs through a lecture (`ADR_Lecture_en-US.pdf`) and two follow-up slide decks (`Architectural_decisions_day_01.pptx.pdf`, `Architectural_decisions_day_02.pptx.pdf`).

7. **Ethics.** Participation was voluntary and governed by an Informed Consent Form (`Consent Form - ICF.pdf`); participants confirmed they were 18+ and consented to anonymized use/publication of results.

## Repository structure

| File | Type | Description |
|---|---|---|
| `guideline_experiments.pdf` | Instrument | Step-by-step instructions given to participants to run the experimental task (access platform, produce the ADR, download log file, answer forms/feedback). |
| `Consent Form - ICF.pdf` | Instrument | Informed Consent Form describing the study, confidentiality terms, and participant rights. |
| `characterization_form.pdf` | Instrument | Pre-task questionnaire characterizing participants' software architecture / development experience. |
| `ADR_Lecture_en-US.pdf` | Training material | Introductory lecture slides on Architectural Decision Records. |
| `Architectural_decisions_day_01.pptx.pdf` | Training material | Day 1 slides on architectural decisions. |
| `Architectural_decisions_day_02.pptx.pdf` | Training material | Day 2 slides on architectural decisions. |
| `DESMET_metrics.xlsx - [eng_Auth01] Weight Calc.pdf` | Analysis (DESMET) | Feature-analysis scoring (Evaluator 1) used to select MADR/Nygard from the five candidate templates. |
| `DESMET_metrics.xlsx - [eng_Auth02] Weights Calc.pdf` | Analysis (DESMET) | Feature-analysis scoring (Evaluator 2), same purpose as above. |
| `post-experimental questionaire.pdf` | Instrument | DESMET-style post-task questionnaire on clarity/completeness/objectivity/effort/recommendation for the template used. |
| `quantitative results.xlsx` | Data | Tabulated numeric answers to the post-experimental questionnaire, one row per participant per template. |
| `quantitative_results.pdf` | Data (export) | PDF export of `quantitative results.xlsx`. |
| `feedback_questionaires_questions.pdf` | Instrument | Open-ended research feedback questionnaire comparing MADR vs. Nygard. |
| `feedback_answer.xlsx` | Data | Tabulated open-ended answers to the feedback questionnaire, one row per participant. |
| `feedback_ans.pdf` | Data (export) | PDF export of `feedback_answer.xlsx`. |
| `results_axial_coding.pdf` | Analysis (qualitative) | Axial coding of open-ended answers: quotes, comments, and derived codes/categories. |

## Data dictionary

### `quantitative results.xlsx` (66 rows = 33 participants × 2 templates)

| Column | Meaning |
|---|---|
| `Participant` | Participant identifier (`Participant 01`–`Participant 33`). |
| `FS1.01` | Post-task rating: clarity of the *decision* field (delimitation), from the DESMET post-questionnaire. |
| `FS1.02` | Post-task rating: clarity of the *context* field. |
| `FS1.03` | Post-task rating: clarity of the *consequences* field. |
| `FS2.04` | Post-task rating: perceived objectivity of the template (1–5 scale). |
| `FS3.01` | Post-task rating related to adoption potential (0–10 scale). |
| `Template` | Which template the row refers to: `MADR` or `Nygard`. |
| `FS2.01` (2 columns, as exported) | Log-derived metrics from the documentation platform (e.g., time-on-task / edit activity) referenced in the guideline as the "log file" upload step; consult `guideline_experiments.pdf` and `post-experimental questionaire.pdf` for the exact platform-side definitions, as the header duplication comes from the original source file. |
| `Group` | Counterbalancing group (`grupo_A` / `grupo_B`) controlling presentation order of the two templates. |

### `feedback_answer.xlsx` (31 rows = 31 participants)

| Column | Meaning |
|---|---|
| `Participant` | Participant identifier. |
| `Preference` | Overall preferred template (`MADR`, `Nygard`, or no preference). |
| `Justification` | Free-text justification for the preference. |
| `Differences` | Free-text: most notable differences noticed between templates. |
| `Suggestion` | Free-text improvement suggestions. |
| `Nygard: Hardest (and Why)` / `Nygard: Most Useful (and Why)` / `Nygard: Least Liked` / `Nygard: Most Liked` | Free-text answers specific to the Nygard template. |
| `MADR: Hardest (and Why)` / `MADR: Most Useful (and Why)` / `MADR: Least Liked` / `MADR: Most Liked` | Free-text answers specific to the MADR template. |

### DESMET weight-calculation sheets (`DESMET_metrics.xlsx - [eng_Auth0X] ... .pdf`)

Each evaluator scored the five candidate templates (`MADR`, `Tyree`, `Arc42`, `Nygard`, `Y-statement`) on two example decisions ("Decision #1", "Decision #2"), with columns:

- `FS1.01`, `FS1.02`, `FS1.03` — binary presence checks (Structural Completeness), aggregated into `SFS1`.
- `FS2.01`, `FS2.02`, `FS2.03` (normalized), `FS2.04` — usability/efficiency indicators (including a character-count column and normalized scores), aggregated into `SFS2`.
- `FS3.01` / `FS3.03` — adoption-potential indicator, aggregated into `SFS3`.
- `IL` — importance level of each indicator; `IW` — indicator weight per feature set (0.15 / 0.50 / 0.35 for FS1 / FS2 / FS3).
- `OS` — overall (weighted) score per template per decision.

## How to reproduce the study procedure

1. Read `Consent Form - ICF.pdf` and obtain informed consent from participants.
2. Have participants complete `characterization_form.pdf`.
3. Deliver the training materials (`ADR_Lecture_en-US.pdf`, `Architectural_decisions_day_01/02.pptx.pdf`).
4. Follow the steps in `guideline_experiments.pdf`: participants produce an ADR on the documentation platform for each template (order per `Group`), download the platform log file, then complete `post-experimental questionaire.pdf` and `feedback_questionaires_questions.pdf`.
5. Tabulate quantitative answers as in `quantitative results.xlsx` and open-ended answers as in `feedback_answer.xlsx`.
6. Analyze quantitative results (e.g., compare MADR vs. Nygard ratings within-subject) and code open-ended answers as in `results_axial_coding.pdf`.
7. If replicating the template-selection step, reproduce the DESMET feature analysis using the scoring sheets described above.

## Citation

If you use this replication package, please cite the associated publication.

```
[Add full citation / BibTeX entry once available]
```

## License

[Add license — e.g., CC-BY-4.0 for data/materials — before publishing.]

## Contact

For questions about this study or dataset, please contact the corresponding author(s) listed in the associated publication.
