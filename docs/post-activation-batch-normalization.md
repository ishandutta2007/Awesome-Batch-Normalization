# Post-Activation Batch Normalization

Post-Activation BatchNorm is the traditional layout where normalization is applied after the linear/convolutional layer but before or after the activation function.

## Mechanism
Layout: `Weight -> BN -> Activation` or `Weight -> Activation -> BN`

## Mermaid Diagram
```mermaid
graph LR
    Input --> Weight[Weight Layer (e.g. Conv)]
    Weight --> BN[Batch Normalization]
    BN --> Act[Activation (e.g. ReLU)]
    Act --> Output
```

## Significance & Limitations
- **Significance:** Standard design used in original ResNets and Inception networks.
- **Limitation:** May hinder identity mapping flow compared to pre-activation.

[Back to README](../README.md)
