---
title: "Titlul Postării Matematice"
date: 2025-08-05
permalink: /posts/math/titlu-postare/
tags:
  - neural networks
  - mathematics
  - deep learning
categories:
  - Machine Learning
  - Mathematics
math: true
mermaid: true
toc: true
toc_sticky: true
layout: single-math
excerpt: "Descriere scurtă pentru preview"
header:
  teaser: /images/teaser-default.jpg
---

# Introducere

Text introductiv cu prima ecuație inline: $f(x) = \sigma(Wx + b)$.

## Sectiunea cu Matematică

### Ecuații Block

$$\begin{align}
\frac{\partial J}{\partial W} &= \frac{1}{m} X^T (A - Y) \\
\frac{\partial J}{\partial b} &= \frac{1}{m} \sum_{i=1}^{m} (a^{(i)} - y^{(i)})
\end{align}$$

### Tabele cu Formule

| Funcția | Formula | Derivata |
|---------|---------|----------|
| Sigmoid | $\sigma(z) = \frac{1}{1 + e^{-z}}$ | $\sigma'(z) = \sigma(z)(1 - \sigma(z))$ |
| ReLU | $\text{ReLU}(z) = \max(0, z)$ | $\text{ReLU}'(z) = \begin{cases} 1 & z > 0 \\ 0 & z \leq 0 \end{cases}$ |

### Diagrame

```mermaid
graph LR
    A[Input Layer] --> B[Hidden Layer 1]
    B --> C[Hidden Layer 2]
    C --> D[Output Layer]
    
    style A fill:#e1f5fe
    style D fill:#f3e5f5
