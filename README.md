# CIP-B107 Lab 01: IP-address evidence triage (Case ICDFA-DFIR-AI-026)

## Environment (Kali Linux, offline, no API key, no GPU)
```bash
cd ~/CIP-B107-LAB01
python3 -m venv .venv && source .venv/bin/activate
pip install pandas scikit-learn matplotlib notebook
pip freeze > outputs/requirements_versions.txt
```

## Layout
```
originals/   5 evidence files (read-only, chmod 444). Never modified.
work/        ip_lab.ipynb
outputs/     all generated files (manifest, review CSVs, predictions, metrics, figures)
```

## Reproduce
1. Hash the originals and save the output as `outputs/sha256.txt` (`sha256sum ... | tee ../outputs/sha256.txt`).
2. `cd work && jupyter notebook ip_lab.ipynb`, edit the `# >>> EDIT` cells (name, student ID), then Kernel -> Restart & Run All.
3. The notebook stops with an assertion error if any evidence hash differs from `sha256.txt`.

Random seed: 42 (fixed in the notebook). Package versions are written to `outputs/environment.json`.

## Not executed (by design)
The historical upload / create-job / status / prediction scripts were NOT run: they use obsolete API patterns and contain embedded credentials. No credentials are in this submission. No fine-tuned model was run; `result.csv` figures are historical and labelled as such.

## Outputs
evidence_manifest.csv, candidate_review.csv, predictions.csv, metrics.csv, analyst_review_worksheet.csv, figures/*.png, environment.json

## Demonstration
Recording: https://drive.google.com/file/d/192eZcuZ2YieXnMsLWENE8mOuv7dIHdYj/view?usp=drivesdk (see DEMO.md)
