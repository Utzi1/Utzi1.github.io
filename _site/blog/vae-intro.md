# Introduction to Variational Autoencoders (VAEs)

**Posted:** 2026-05-14

Variational Autoencoders (VAEs) are powerful generative models that combine ideas from deep learning and probabilistic inference. Let's break them down!

## What is a VAE?

A VAE is a neural network architecture that learns to encode data into a compressed latent space and then decode it back to the original format.

### Key Components

1. **Encoder** — Maps input data to a latent distribution
2. **Latent Space** — Low-dimensional representation
3. **Decoder** — Reconstructs data from latent codes

```
Input → [Encoder] → Latent Z ~ N(μ, σ) → [Decoder] → Reconstructed Output
```

## The Loss Function

A VAE is trained to minimize:

```
Loss = Reconstruction Loss + KL Divergence
L = E[log p(x|z)] - D_KL(q(z|x) || p(z))
```

- **Reconstruction Loss** — How well we can rebuild the input
- **KL Divergence** — How close our learned distribution matches the prior (standard normal)

## Applications

- **Image Generation** — Generate new images
- **Data Compression** — Efficient latent representations
- **Anomaly Detection** — Identify unusual patterns
- **Style Transfer** — Manipulate latent codes for effects

## Implementation Example (PyTorch)

```python
import torch
import torch.nn as nn

class VAE(nn.Module):
    def __init__(self, input_dim=784, latent_dim=20):
        super(VAE, self).__init__()
        
        # Encoder
        self.fc1 = nn.Linear(input_dim, 400)
        self.fc_mu = nn.Linear(400, latent_dim)
        self.fc_logvar = nn.Linear(400, latent_dim)
        
        # Decoder
        self.fc3 = nn.Linear(latent_dim, 400)
        self.fc4 = nn.Linear(400, input_dim)
    
    def encode(self, x):
        h = torch.relu(self.fc1(x))
        return self.fc_mu(h), self.fc_logvar(h)
    
    def decode(self, z):
        h = torch.relu(self.fc3(z))
        return torch.sigmoid(self.fc4(h))
    
    def reparameterize(self, mu, logvar):
        std = torch.exp(0.5 * logvar)
        eps = torch.randn_like(std)
        return mu + eps * std
    
    def forward(self, x):
        mu, logvar = self.encode(x)
        z = self.reparameterize(mu, logvar)
        return self.decode(z), mu, logvar
```

## Resources

- [Original VAE Paper](https://arxiv.org/abs/1312.6114)
- [Intuitively Understanding VAEs](https://towardsdatascience.com/intuitively-understanding-variational-autoencoders-1bfe67eb5daf)
- [Tutorial: Implementing VAE in TensorFlow](https://www.tensorflow.org/tutorials/generative/cvae)

---

[← Back to Blog](index.md) | [← Home](../index.md)
