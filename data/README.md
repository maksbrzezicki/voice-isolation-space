# Data

The analysis reads one file, which is not included in this repository:

    data/results_20260101_223957.csv

It is available from the corresponding author on reasonable request (see the Data Availability Statement of the article). Audio recordings are not shared.

Expected file: 62 rows (one per recording), 97 columns, SHA-256
`90400d410923a81f4f48dbc38d0e0ddfcb270e9294503028a8ac02f24e3f497e`.

| Column | Content |
|---|---|
| `filename` | Recording file name used by the analysis; the leading `DD.MM` gives the session date from which the mission-day index is computed |
| `filename_AsWritten` | Original file name |
| `subject_ID` | Pseudonymised participant code (AA01 to AA09) |
| 88 eGeMAPS columns | Acoustic parameters from openSMILE, extended Geneva Minimalistic Acoustic Parameter Set (column names as returned by openSMILE) |
| `mel_spec_mean`, `mel_spec_std`, `mel_spec_max`, `mel_spec_min`, `mel_plot_path` | Spectrogram summaries from the extraction step; not used in the analysis |
