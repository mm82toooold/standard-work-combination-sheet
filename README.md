Standard Work Combination Sheet Creator

Final project for the Building AI course

Summary

This project creates a digital tool for generating Standard Work Combination Sheets used in lean manufacturing. It helps visualize process flow, customer demand, takt time, net operating time, and manual vs automatic work distribution.

Background

Standard work documents are essential in lean environments, yet they're often created manually in Excel or on paper. This:

is time-consuming,

prone to inconsistencies,

and hard to update in real time.

As a lean professional, I've faced this challenge across industries. Automating this process with AI assistance saves time, improves accuracy, and boosts collaboration.

How is it used?

Users input the process steps, times (manual, automatic, walking), and production demands. The tool generates:

a time chart (visualizing walking/manual/automatic)

takt time and cycle time calculations

a printable standard work sheet (PDF, SVG)

It is used by lean engineers, supervisors, or frontline leaders conducting process improvement workshops.

Data sources and AI methods

Input data comes from user entry or integration with MES/ERP systems. This project uses:

NumPy + Pandas for calculations

Matplotlib or Plotly for visual timeline charts

Optional: OCR or form recognition (e.g. Tesseract or Azure Form Recognizer) if scanning handwritten standards

Advanced options may include predictive adjustments using historical data to forecast demand.

Challenges

Accuracy of time study data (human-collected, subjective)

Cannot auto-correct poor process design

May oversimplify complex setups

No real-time adaptation without deeper integration

What next?

Add support for multiple operators and process branches

Connect to real-time sensors or time tracking apps

Enable editing via drag-drop UI (like Lucidchart)

Add templates for different industries (e.g. machining, assembly, logistics)

Acknowledgments

Inspired by Toyota Production System and Lean tools

Image example from C. Nelson's standard work sheet

Conceptual format modeled on standard lean literature

Thank you Reaktor and University of Helsinki for the Building AI course.


