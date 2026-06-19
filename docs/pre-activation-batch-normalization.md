# Pre-Activation Batch Normalization

Pre-Activation BatchNorm applies normalization and activation before the weight/convolution layer.

## Mechanism
Layout: `BN -> Activation -> Weight`

## Mermaid Diagram
```mermaid
graph LR
    Input --> BN[Batch Normalization]
    BN --> Act[Activation (e.g. ReLU)]
    Act --> Weight[Weight Layer (e.g. Conv)]
    Weight --> Output
```

## Significance & Limitations
- **Significance:** Enables easier gradient flow and identity mapping propagation, which is vital for training extremely deep models.
- **Limitation:** Changes the initialization landscape, requiring adjustment of weights initialization.

[Back to README](../README.md)
