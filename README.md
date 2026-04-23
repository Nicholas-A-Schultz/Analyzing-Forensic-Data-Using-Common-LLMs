# Analyzing Forensic Data Using Common LLMs

This project explores whether commonly available large language models (LLMs) can assist with digital forensic analysis by identifying potentially incriminating patterns in browser history data. The repository contains curated browser-history datasets, model test outputs, and supporting project materials used to evaluate how well several popular LLMs distinguish between innocent, misleading, suspicious, and illegal searches.

## Overview

Digital forensic review can be time-consuming, repetitive, and vulnerable to human error. This project investigates whether common LLMs can serve as a useful first-pass tool for reviewing browser history evidence.

To test this, we created multiple browser-history datasets and evaluated how different LLMs classified search activity. The goal was to measure each model’s ability to:

- detect criminal or suspicious searches
- avoid flagging harmless searches
- resist false positives caused by red-herring searches
- perform consistently across mixed datasets

## Research Question

Can common LLMs reliably assist with forensic browser-history analysis by identifying criminal or suspicious search behavior while minimizing false positives?

## Models Evaluated

The project compares the performance of the following LLMs:

- ChatGPT
- Copilot
- Gemini
- Grok

These models were tested using their free/publicly available versions.

## Dataset Design

The datasets were built around four search categories:

- **Innocent searches**: normal, non-relevant searches with no forensic value
- **Red-herring searches**: harmless searches that may appear suspicious at first glance
- **Suspicious searches**: contextually concerning searches that are not directly illegal
- **Illegal searches**: searches that are directly incriminating or strongly indicative of criminal intent

### Dataset Groups

The repository includes two main dataset styles:

1. **Isolated / absolute datasets**
   - all criminal
   - all noncriminal
   - all red herring

2. **Mixed browser-history datasets**
   - five realistic browser history files containing a controlled mix of innocent, red-herring, and criminal searches

### Prompt

Please create a table (Date and Time | Search Entry | Suspicion Report) for the provided search history and record and print any suspicious search entries you find and provide a brief report for each individual entry recorded as to why that particular search entry is suspicious. If the searches are normal, ignore them.

## What Is in This Repository

### Browser Sets/
Contains the source browser-history datasets used in testing. These files represent both controlled and mixed scenarios.

### Test Cases/
Contains outputs, prompts, or supporting artifacts associated with each model’s evaluation.

### Report
A full project report will also be included in this repository. Once uploaded, it should be the best place to find:

- full methodology
- dataset definitions
- result breakdowns
- charts and figures
- interpretation and conclusions

## Methodology

The testing process followed these general steps:

1. Create realistic browser-history datasets with known category counts.
2. Submit those histories to each LLM.
3. Record which searches each model flagged as suspicious or criminal.
4. Compare model outputs against the known ground truth.
5. Measure performance in terms of:
   - criminal-search detection
   - false positives
   - consistency across datasets

To reduce unnecessary output size, the analysis focused primarily on flagged searches rather than requiring models to explain every innocent entry.

## Summary of Findings

The project found that common LLMs can be useful for identifying forensically relevant search patterns, but their reliability varies significantly.

General findings include:

- Some models performed very well on clearly criminal-only datasets.
- All models handled clearly noncriminal datasets well.
- Resistance to red-herring false positives varied by model.
- Performance on mixed, realistic browser histories was inconsistent.
- Some models were more conservative and missed criminal content.
- Others were more aggressive and occasionally introduced false positives.

Overall, the results suggest that LLMs may be useful as a support tool in forensic workflows, but they should not be trusted without human oversight.

## Key Takeaway

LLMs show potential for assisting with forensic triage and pattern detection, but they are not yet reliable enough to replace human investigators. Their best use is likely as a first-pass review aid rather than a final decision-maker.

## Possible Future Improvements

Future work could expand this project by:

- testing paid or higher-tier models
- using larger and more realistic browser-history datasets
- evaluating prompt engineering effects
- developing a forensic-specific LLM workflow
- measuring precision, recall, and F1 score formally
- testing whether specialized models outperform general-purpose chat models

## Authors

- Emmett Gilbert
- Nicholas Schultz

## Notes

This project is intended for research and educational purposes related to digital forensics, AI evaluation, and investigative workflow analysis.
