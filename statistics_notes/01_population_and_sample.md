# An overview of statistics

## Probability and statistics

| field | representation | assumption | unknown |
| ----- | - | ---------- | ------- |
| probability | $P(X \mid \theta)$ | parameter | data |
| frequentist statistical inference | $\hat{\theta}(X)$ | data | parameter |
| Bayesian statistical inference | $P(\theta \mid X)$ | prior, likelihood | posterior |

## Population and sample

| set |   | mean | variance |
| --- | - | ---- | -------- |
| population | $\\{ x_i \\}_{i=1}^N$ | $\mu=\mathbb{E}\left[X\right]$ | $\sigma^2=\frac{1}{N}\sum_{i=1}^N \left(x_i-\mu\right)^2=\mathbb{E}\left[X^2\right]-\mathbb{E}\left[X\right]^2$ |
| sample | $\\{ x_i \\}_{i=1}^n$ | $\bar{x}=\frac{1}{n}\sum_{i=1}^n x_i$ | $\hat{\sigma}^2=\frac{1}{n-1}\sum_{i=1}^n \left(x_i-\bar{x}\right)^2$ |

Random sampling assumes

- $\binom{N}{n}$ possible random samples
- no replacement

## Central limit theorem

$$
\bar{x}\sim \mathcal{N}\left(\mu,\frac{\sigma^2}{n}\right) \Leftrightarrow \frac{\bar{x}-\mu}{\sigma / \sqrt{n}}\sim \mathcal{N}\left(0,1\right)
$$

### Confidence intervals

$$
\mu \in \bar{x} \pm Z_{1-\alpha / 2} \text{SE}
$$

Use $\text{SE}=\frac{\sigma}{\sqrt{n}}$ and $Z_{1-\alpha /2}$ (if the variance is known), $\text{SE}=\frac{\hat{\sigma}}{\sqrt{n}}$ and $t_{1-\alpha /2, n-1}$ (if the variance is unknown). $1-\alpha / 2 \Rightarrow$ a two-sided confidence interval.
