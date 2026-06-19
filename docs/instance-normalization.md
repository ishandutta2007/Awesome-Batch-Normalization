# Instance Normalization (InstanceNorm)

Instance Normalization normalizes features purely across the spatial dimensions ($H \times W$) for each individual channel and sample.

## Mechanism
The normalization statistics are computed independently for each channel in each sample.

## Mermaid Diagram
```mermaid
graph TD
    Input[Input Sample of Shape N x C x H x W] --> Split[Split into Sample-Channel pairs]
    Split --> Compute[Compute Mean & Var across H, W for each channel per sample]
    Compute --> Normalize[Normalize Features]
    Normalize --> ScaleShift[Scale and Shift with Learnable Gamma and Beta]
    ScaleShift --> Output[Normalized Output]
```

## Significance & Limitations
- **Significance:** Acts as a style-normalization step, making it highly effective for style transfer and GANs.
- **Limitation:** Not suitable for tasks requiring absolute feature scale representation.

[Back to README](../README.md)
