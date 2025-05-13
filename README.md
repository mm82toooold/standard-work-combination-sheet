# Standard Work Combination Sheet Creator

**Final project for the Building AI course**

## Summary

This project creates a digital tool for generating Standard Work Combination Sheets used in lean manufacturing. It helps visualize process flow, customer demand, takt time, net operating time, and manual vs automatic work distribution.

## Background

Standard work documents are essential in lean environments, yet they’re often created manually in Excel or on paper. This:

* is time-consuming,
* prone to inconsistencies,
* and hard to update in real time.

As a lean professional, I’ve faced this challenge across industries. Automating this process with AI assistance saves time, improves accuracy, and boosts collaboration.

## How is it used?

Users input the process steps, times (manual, automatic, walking), and production demands. The tool generates:

* a stacked time chart (Manual, Auto, Walk work breakdown)
* a cycle time breakdown with proportions
* takt time and total cycle time validation (pass/fail)
* (planned) exportable formats: PDF, SVG, CSV

It is used by lean engineers, supervisors, or frontline leaders conducting process improvement workshops.

## Data sources and AI methods

Input data comes from user entry or integration with MES/ERP systems. This project uses:

* NumPy + Pandas for calculations
* Plotly for visual timeline and breakdown charts
* (optional) OCR (Tesseract or Azure Form Recognizer) for scanned standards

Advanced options may include predictive adjustments using historical data to forecast demand.

## Features Implemented (MVP)

* Customer demand + net time input to calculate takt time
* Entry of manual, auto, walk time per step
* Generation of a stacked horizontal bar chart for time segments
* Proportional cycle time chart for each work type
* Takt time compliance check with pass/fail indicator

## AI/Logic Snippet Example

The app applies logic-based rules to detect bottlenecks and assess step-level takt time compliance. Here's a simplified version of how each step is evaluated:

```python
for _, row in df.iterrows():
    step_total = row["Manual"] + row["Auto"] + row["Walk"]
    if step_total > takt_time:
        status = "❌ Over takt"
    else:
        status = "✅ Within takt"
    print(f"{row['Step']}: {step_total:.2f}s — {status}")
```

This logic is also used to recommend:

* Adding operators if manual time exceeds 7 hours per person
* Splitting steps that exceed takt
* Rearranging flow for efficiency

## Challenges

* Accuracy of time study data (human-collected, subjective)
* Cannot auto-correct poor process design
* May oversimplify complex setups
* No real-time adaptation without deeper integration

## What next?

The following features are planned for the next development phases:

* **Time Observation Sheet** for collecting actual time study data during process walkthroughs
* **Process Capacity Analysis** to estimate theoretical capacity and identify bottlenecks
* **EPEI (Every Part Every Interval) Calculator** for estimating optimal production scheduling intervals
* **Analytics Dashboard** for:

  * Graphical summary reports
  * Statistical process capability (Cp, Cpk)
  * Confidence intervals and histogram charts
  * Smart diagnostics with AI-powered suggestions when process steps exceed takt time, available operator capacity, or SWIP limits

Future updates will also include:

* Exporting standard work sheets as PDF, Excel, or SVG
* Real-time sensor or ERP system integrations
* Industry-specific templates (e.g. machining, logistics, assembly)
* Offline-desktop version for single-license SaaS model

## Acknowledgments

* Inspired by Toyota Production System and Lean tools
* Conceptual format modeled on standard lean literature
* Thank you Reaktor and University of Helsinki for the Building AI course

## Screenshots

### Process Breakdown & Takt Time Validation

<img src="/Screenshot 2025-05-13 at 21.46.34.png" width="600">

### Yamazumi Chart

<img src="/Screenshot 2025-05-13 at 21.47.13.png" width="600">

### Work Sequence Flow Visualization

<img src="/Screenshot 2025-05-13 at 21.47.21.png" width="600">

### Cycle Time Breakdown

<img src="/Screenshot 2025-05-13 at 21.47.32.png" width="600">
