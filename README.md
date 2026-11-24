# Flight Telemetry Decision Dashboard

An interactive **Google Colab** engineering tool built with `ipywidgets`, `NumPy`, `Pandas`, and `Matplotlib` to inspect **recorded sensor data** and highlight **one meaningful flight decision** with clear visual thresholds and cause-and-effect reasoning[cite: 6].

## Overview

Rather than showing raw charts alone, an effective telemetry dashboard turns recorded sensor streams into one clear, actionable flight decision[cite: 6]. This notebook lets you explore recorded flight scenarios, adjust decision thresholds and telemetry noise, view a 2D flight profile alongside a detailed thresholded telemetry chart, and read why the highlighted decision was triggered[cite: 6].

### Included Telemetry Scenarios
- **Battery Sag & Low Voltage:** Monitors pack voltage (`[V]`) against a low-voltage threshold and highlights **TRIGGER RETURN-TO-HOME (RTH)** when breached.
- **Severe Wind Gust / G-Spike:** Monitors vertical load (`[g]`) against a load limit and highlights **ABORT CLIMB & EASE G-LOAD** when exceeded.
- **Nominal Flight Envelope:** Keeps sensor measurements inside safe margins and highlights **CONTINUE PLANNED MISSION**.

## Key Features

- **Interactive English UI (`ipywidgets`):** Choose a telemetry log scenario, adjust the `Decision Threshold` and `Telemetry Noise` sliders, and update live or via **Update Dashboard**.
- **2D Flight Profile & Detailed Telemetry Chart:** Shows the 2D altitude/distance path with the decision point on the left, and a detailed time-series plot with safe/action zones, threshold line, and trigger annotation on the right.
- **Highlighted Decision & Cause-and-Effect Verdict:** Features a prominent single flight decision banner paired with an explanation of which sensor value crossed which threshold and when[cite: 6].

## How to Run in Google Colab

1. Open a new notebook in [Google Colab](https://colab.research.google.com/).
2. Paste the telemetry dashboard code into a code cell and run it.
3. Select a scenario or adjust the decision threshold and noise sliders to see how the highlighted flight decision changes[cite: 6].

## Engineering Notes

- Real flight-test decision logic also accounts for hysteresis/debounce timers, multi-sensor cross-checks, battery internal resistance, and fail-safe state machines before autonomous or pilot execution.
