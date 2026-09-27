# Voice acoustics during a short-term analog space mission

Nine analog astronauts recorded spoken video diaries every other day during two 14-day missions at the LunAres Research Station (62 recordings). The notebook takes the per-recording eGeMAPS feature table and reproduces every number, table and figure reported in the article:

1. mission-day index and cohort description;
2. greedy correlation filter (|r| > 0.80) with audit and two reinstated features (53 features);
3. random-intercept mixed-effects model of each feature on mission day, Benjamini-Hochberg correction (Figure 1);
4. leave-one-subject-out prediction of mission day with SVR, random forest, extra trees, XGBoost and MERF, with filtering and scaling inside each fold (Table 1, Figure 3);
5. variance decomposition with a 200-sample cluster bootstrap (Figure 2);
6. `results_manifest.json`, which records every reported value.

## Running

```bash
python3.11 -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt
# place the data file in data/ (see data/README.md)
python -c "import nbformat; from nbclient import NotebookClient; nb = nbformat.read('voice_isolation_analysis.ipynb', 4); NotebookClient(nb, timeout=1800, kernel_name='python3').execute(); nbformat.write(nb, 'voice_isolation_analysis_executed.ipynb')"
python verify_results.py
```

