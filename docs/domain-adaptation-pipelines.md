# Domain Adaptation Pipelines

Batch Normalization statistics can be frozen or adapted to handle shifts in data distribution between training (source) and test (target) domains.

## Mechanism
Adapt target statistics by calculating running mean and variance on target domain samples while keeping trained weights frozen.

## Mermaid Diagram
```mermaid
graph TD
    Source[Source Domain Model] --> FreezeWeights[Freeze Weight Parameters]
    FreezeWeights --> UpdateStats[Update BN Mean & Var on Target Domain]
    UpdateStats --> Adapted[Adapted Target Domain Model]
```

## Significance & Limitations
- **Significance:** Zero-parameter domain adaptation method (AdaBN) that quickly aligns feature distributions.
- **Limitation:** Only corrects for marginal distribution shifts, not complex conditional distribution shifts.

[Back to README](../README.md)
