# Layer Normalization (LayerNorm)

Layer Normalization normalizes all features across the channel and hidden dimensions for each training sample independently.

## Mechanism
Unlike BatchNorm, LayerNorm computes statistics across the feature/channel dimension ($C$) for each sample individually.

## Mermaid Diagram
```mermaid
graph TD
    Input[Input Sample of Shape N x C x H x W] --> Split[Split into Samples]
    Split --> Compute[Compute Mean & Var across C, H, W for each Sample]
    Compute --> Normalize[Normalize Features]
    Normalize --> ScaleShift[Scale and Shift with Learnable Gamma and Beta]
    ScaleShift --> Output[Normalized Output]
```

## Significance & Limitations
- **Significance:** Excellent for sequence models (Transformers, RNNs/LSTMs) as it is independent of batch size.
- **Limitation:** Can be less effective than BatchNorm in CNNs due to spatial correlation ignoring.

[Back to README](../README.md)
