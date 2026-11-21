# PsychReportAgent

**A modular multi-agent system for student assessment reporting**

PsychReportAgent turns structured psychological and cognitive assessment scores into illustrated Chinese-language PDF reports. The prototype helps families and students understand what an assessment measured and identify practical next steps.

[Report preview](#report-preview) · [System architecture](#system-architecture) · [Project contributions](#project-contributions)

## Report preview

The pages below were rendered by the prototype with invented scores and scripted demonstration text.

<p>
  <a href="preview/assessment-overview.png"><img src="preview/assessment-overview.png" width="48%" alt="Synthetic junior-high assessment overview with a score profile chart and narrative"></a>
  <a href="preview/growth-suggestions.png"><img src="preview/growth-suggestions.png" width="48%" alt="Synthetic report page showing three growth and career exploration suggestions"></a>
</p>

[Open the assessment overview](preview/assessment-overview.png) · [Open the growth suggestions](preview/growth-suggestions.png)

## System architecture

```mermaid
flowchart LR
    A["Assessment JSON"] --> B["Validate input and apply scoring rules"]
    B --> C["Retrieve metric references and expert writing patterns"]
    C --> D["Plan and draft the report"]
    D --> E{"Check structure and evidence"}
    E -->|Targeted revision| D
    E -->|Passes internal checks| F["Render PDF and charts"]
    E -->|Unresolved issues| G["Human review"]
```

Python handles score bands, input validation, and workflow orchestration. DeepSeek drafts the report text with school-stage-specific instructions. A local retrieval library provides writing references. Playwright renders the structured report with HTML and SVG charts.

## Project contributions

- Built the report workflow and a local console for batch generation and review.
- Organized 30 expert-revised reports, four writing guides, and 30 sets of expert annotations into reusable writing instructions, evaluation criteria, and local retrieval references.
- Built checks for score-band consistency, indicator coverage, and unsupported claims, with targeted revision for flagged sections. The reference catalog covers 26 assessment indicators.

The reports are designed for educational use and provide non-diagnostic feedback.
