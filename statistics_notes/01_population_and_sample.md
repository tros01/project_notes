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

## Evaluation criteria

### Unbiasedness

$$
\mathbb{E}\left[\theta\right]=\theta
$$

Which implies bias,

$$
b\left(\hat{\theta}\right)=\mathbb{E}\left[\theta\right]-\theta
$$

### Asymptotic unbiasedness

$$
b\left(\hat{\theta}\right) \to 0 \text{ as } n \to \infty
$$

### Mean squared error

$$
\begin{align}
MSE
&=\mathbb{E}\left[\left(\hat{\theta}-\theta\right)^2\right] \\
&=\mathbb{E}\left[\left(\hat{\theta} \pm \mathbb{E}\left[\hat{\theta}\right] -\theta\right)^2\right] \\
&=\text{Var}\left(\hat{\theta}\right)+b^2\left(\hat{\theta}\right)
\end{align}
$$

### Relative efficiency

$$
\frac{MSE\left(\hat{\theta}_1\right)}{MSE\left(\hat{\theta}_2\right)}
$$

Where $MSE\left(\hat{\theta}_1\right) > MSE\left(\hat{\theta}_2\right)$ suggests $\hat{\theta}_2$ is preferrable.

### Consistency

$$
\mathbb{E}\left[\left(\hat{\theta}-\theta\right)^2\right] \to 0 \text{ as } n \to \infty
$$

## Expected value and variance of the sample mean

### Unbiasedness of $\bar{x}$

$$
\begin{align}
\mathbb{E}\left[\bar{x}\right] &= \mu \\
\mathbb{E}\left[\frac{1}{n}\sum_{i=1}^n x_i\right] &= \mu \\
\frac{n}{n}\mathbb{E}\left[x_i\right] &= \mu \\
\mu &= \mu
\end{align}
$$

### Small sample variance

$$
\begin{align}
\text{Var}\left(\bar{x}\right) &= \text{Cov}\left(\bar{x},\bar{x}\right) \\
&= \text{Cov}\left(\frac{1}{n}\sum_{i=1}^n x_i,\frac{1}{n}\sum_{j=1}^n x_j\right) \\
&= \frac{1}{n^2} \sum_{i=1}^n \sum_{j=1}^n \text{Cov}\left(x_i,x_j\right) \\
&= \frac{1}{n^2} \left[ \sum_{i=1}^n \text{Cov}\left(x_i,x_j\right) + \sum_{i \neq j} \text{Cov}\left(x_i,x_j\right) \right] \\
&= \frac{1}{n^2} \left[ n \text{Var}\left(x_i\right) + n(n-1)\left(-\frac{\sigma^2}{N-1}\right) \right] \\
&= \frac{1}{n^2} \left[ n\sigma^2-\frac{n(n-1)}{N-1}\sigma^2 \right] \\
&= \frac{\sigma^2}{n} \left[ 1-\frac{(n-1)}{N-1} \right]
\end{align}
$$


### Large sample variance ($n \gg 1$)

$$
\begin{align}
\text{Var}\left(\bar{x}\right) &= \frac{1}{n^2} \text{Var}\left(x_1,\cdot,x_n\right) \\
&\approx \frac{\sigma^2}{n}
\end{align}
$$
