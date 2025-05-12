Standard Work Combination Sheet Creator

Final project for the Building AI course

Summary

This project creates a digital tool for generating Standard Work Combination Sheets used in lean manufacturing. It helps visualize process flow, customer demand, takt time, net operating time, and manual vs automatic work distribution.

Background

Standard work documents are essential in lean environments, yet they’re often created manually in Excel or on paper. This:
	•	is time-consuming,
	•	prone to inconsistencies,
	•	and hard to update in real time.

As a lean professional, I’ve faced this challenge across industries. Automating this process with AI assistance saves time, improves accuracy, and boosts collaboration.

How is it used?

Users input the process steps, times (manual, automatic, walking), and production demands. The tool generates:
	•	a stacked time chart (Manual, Auto, Walk work breakdown)
	•	a cycle time breakdown with proportions
	•	takt time and total cycle time validation (pass/fail)
	•	(planned) exportable formats: PDF, SVG, CSV

It is used by lean engineers, supervisors, or frontline leaders conducting process improvement workshops.

Data sources and AI methods

Input data comes from user entry or integration with MES/ERP systems. This project uses:
	•	NumPy + Pandas for calculations
	•	Plotly for visual timeline and breakdown charts
	•	(optional) OCR (Tesseract or Azure Form Recognizer) for scanned standards

Advanced options may include predictive adjustments using historical data to forecast demand.

Features Implemented (MVP)
	•	Customer demand + net time input to calculate takt time
	•	Entry of manual, auto, walk time per step
	•	Generation of a stacked horizontal bar chart for time segments
	•	Proportional cycle time chart for each work type
	•	Takt time compliance check with pass/fail indicator

Challenges
	•	Accuracy of time study data (human-collected, subjective)
	•	Cannot auto-correct poor process design
	•	May oversimplify complex setups
	•	No real-time adaptation without deeper integration

What next?
	•	Exporting combination sheet as PDF or Excel
	•	Drag-and-drop or JSON import for editing steps
	•	Real-time sensor integration (IoT)
	•	Templates for different industries (e.g. machining, logistics)

Acknowledgments
	•	Inspired by Toyota Production System and Lean tools
	•	Conceptual format modeled on standard lean literature
	•	Thank you Reaktor and University of Helsinki for the Building AI course
