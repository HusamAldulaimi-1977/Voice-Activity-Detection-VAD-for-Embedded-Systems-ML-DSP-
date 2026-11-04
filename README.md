## Cross-project evaluation

The [Android real-time implementation](https://github.com/HusamAldulaimi-1977/Real_time_VAD) captures microphone audio and produces speech/noise decisions. This repository documents the companion MATLAB evaluation workflow: VAD application output → CSV → manual ground truth → frame-aligned comparison → confusion matrix. The existing evaluation description does not identify the Android commit or export version used, so results cannot yet be attributed to a specific implementation revision.

### Workflow

1. Run the VAD application on the evaluation audio and export CSV decisions containing time, frame index, and binary speech/noise classification, as described in the evaluation workflow.
2. Load the same audio and CSV into MATLAB. Use the interactive labeling tool's **Start**, **noise**, and **speech+noise** controls to create manual ground-truth labels.
3. Select **Evaluate Now** to extract the CSV decision column and compare predictions with ground truth frame by frame. Treat speech (including speech+noise) as the positive class and noise as the negative class; verify the CSV encoding and time/frame alignment before scoring.

The MATLAB tool, example decision CSVs, and ground-truth labels are not yet included in this evaluation repository.

### Tested conditions and available results

The original evaluation description reports testing the following factors; it does not publish per-run settings or numerical outcomes. Android defaults and bundled audio are not evidence of completed evaluation runs.

| Factor reported as tested | Exact tested conditions | Measured results |
| --- | --- | --- |
| Signal-to-noise ratio (SNR) | SNR levels, noise sources, and evaluated recordings: not yet reported | Not yet reported |
| MSE percentile threshold | Tested percentiles and corresponding MSE thresholds: not yet reported | Not yet reported |
| Majority-voting window size | Tested window sizes and time equivalents: not yet reported | Not yet reported |

| Metric | Availability |
| --- | --- |
| True positives (TP), true negatives (TN), false positives (FP), false negatives (FN) | Computation described; counts and confusion matrices not yet reported |
| Accuracy, speech precision, recall, and F1 | Derivable from confusion counts; values not yet reported |

No numerical performance claim or best-performing configuration can currently be established from the published evaluation documentation.

### Planned experiments and reporting

Proposed next steps, not completed or measured results: publish the existing run settings, CSVs, labels, confusion matrices, and derived metrics; then run a reproducible comparison varying SNR, percentile, and voting-window size while holding the other settings fixed. Record the audio/noise source, SNR, threshold, window size, frame timing, Android commit, and device for each run. Any new experiment remains **planned** until its outputs and results are reported.
