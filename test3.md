![download](https://github.com/user-attachments/assets/8b93cf86-9a6f-46c4-9871-5a2dc5a0b6f3)

**Part a)**

We need to show that $\int_{-\pi}^{\pi} \cos(3x) \cos(4x) \, dx = 0$.

We use the product-to-sum trigonometric identity:
$\cos A \cos B = \frac{1}{2} [\cos(A+B) + \cos(A-B)]$

Let $A=4x$ and $B=3x$. Then:
$\cos(3x) \cos(4x) = \frac{1}{2} [\cos(4x+3x) + \cos(4x-3x)] = \frac{1}{2} [\cos(7x) + \cos(x)]$

Now, we integrate this expression from $-\pi$ to $\pi$:
$\int_{-\pi}^{\pi} \cos(3x) \cos(4x) \, dx = \int_{-\pi}^{\pi} \frac{1}{2} [\cos(7x) + \cos(x)] \, dx$
$= \frac{1}{2} \int_{-\pi}^{\pi} (\cos(7x) + \cos(x)) \, dx$

We find the antiderivative:
$= \frac{1}{2} \left[ \frac{\sin(7x)}{7} + \frac{\sin(x)}{1} \right]_{-\pi}^{\pi}$

Now we evaluate the antiderivative at the limits:
Upper limit ($x=\pi$): $\frac{\sin(7\pi)}{7} + \sin(\pi) = \frac{0}{7} + 0 = 0$
Lower limit ($x=-\pi$): $\frac{\sin(7(-\pi))}{7} + \sin(-\pi) = \frac{\sin(-7\pi)}{7} + \sin(-\pi) = \frac{- \sin(7\pi)}{7} - \sin(\pi) = \frac{-0}{7} - 0 = 0$

So the value of the integral is:
$= \frac{1}{2} [ (0) - (0) ] = 0$

Thus, we have shown directly by integration that $\int_{-\pi}^{\pi} \cos(3x) \cos(4x) \, dx = 0$. This demonstrates the orthogonality of $\cos(3x)$ and $\cos(4x)$ on the interval $[-\pi, \pi]$.

**Part b)**

We need to compute $I(\epsilon) = \int_{-\pi-\epsilon}^{\pi+\epsilon} \cos(3x) \cos(4x) \, dx$.

Using the same antiderivative from part (a):
$I(\epsilon) = \frac{1}{2} \left[ \frac{\sin(7x)}{7} + \sin(x) \right]_{-\pi-\epsilon}^{\pi+\epsilon}$

Evaluate at the limits:
Upper limit ($x=\pi+\epsilon$): $\frac{\sin(7(\pi+\epsilon))}{7} + \sin(\pi+\epsilon)$
Lower limit ($x=-\pi-\epsilon$): $\frac{\sin(7(-\pi-\epsilon))}{7} + \sin(-\pi-\epsilon)$

Simplify using trigonometric identities:
$\sin(\theta + \pi) = -\sin(\theta)$
$\sin(\theta + k\pi) = (-1)^k \sin(\theta)$ for integer k
$\sin(-\theta) = -\sin(\theta)$

Upper limit:
$\sin(7(\pi+\epsilon)) = \sin(7\pi + 7\epsilon) = \sin(\pi + 7\epsilon + 6\pi) = \sin(\pi + 7\epsilon) = -\sin(7\epsilon)$
$\sin(\pi+\epsilon) = -\sin(\epsilon)$
So, the upper limit value is $\frac{-\sin(7\epsilon)}{7} - \sin(\epsilon)$.

Lower limit:
$\sin(7(-\pi-\epsilon)) = \sin(-7\pi - 7\epsilon) = -\sin(7\pi + 7\epsilon) = -(-\sin(7\epsilon)) = \sin(7\epsilon)$
$\sin(-\pi-\epsilon) = -\sin(\pi+\epsilon) = -(-\sin(\epsilon)) = \sin(\epsilon)$
So, the lower limit value is $\frac{\sin(7\epsilon)}{7} + \sin(\epsilon)$.

Now compute the definite integral:
$I(\epsilon) = \frac{1}{2} [ (\text{Upper limit value}) - (\text{Lower limit value}) ]$
$I(\epsilon) = \frac{1}{2} \left[ \left(\frac{-\sin(7\epsilon)}{7} - \sin(\epsilon)\right) - \left(\frac{\sin(7\epsilon)}{7} + \sin(\epsilon)\right) \right]$
$I(\epsilon) = \frac{1}{2} \left[ -\frac{\sin(7\epsilon)}{7} - \sin(\epsilon) - \frac{\sin(7\epsilon)}{7} - \sin(\epsilon) \right]$
$I(\epsilon) = \frac{1}{2} \left[ -2 \frac{\sin(7\epsilon)}{7} - 2 \sin(\epsilon) \right]$
$I(\epsilon) = - \left( \frac{\sin(7\epsilon)}{7} + \sin(\epsilon) \right)$

This is the exact value of the integral for an arbitrary $\epsilon$.

**Numerical estimate for $\epsilon = 10^{-4}$:**

Since $\epsilon = 10^{-4}$ is very small, we can use the small-angle approximation $\sin \theta \approx \theta$ (for $\theta$ in radians).
$\sin(7\epsilon) \approx 7\epsilon$
$\sin(\epsilon) \approx \epsilon$

Substitute these approximations into the expression for $I(\epsilon)$:
$I(10^{-4}) \approx - \left( \frac{7\epsilon}{7} + \epsilon \right) = - (\epsilon + \epsilon) = -2\epsilon$
$I(10^{-4}) \approx -2 \times 10^{-4}$

The numerical estimate for $\epsilon = 10^{-4}$ is $-0.0002$.

**Orthogonality comment:**

Two functions $f(x)$ and $g(x)$ are orthogonal on an interval $[a, b]$ if $\int_a^b f(x) g(x) \, dx = 0$.
In part (a), we showed $\int_{-\pi}^{\pi} \cos(3x) \cos(4x) \, dx = 0$, so $\cos(3x)$ and $\cos(4x)$ are orthogonal on $[-\pi, \pi]$.
In part (b), we found $\int_{-\pi-\epsilon}^{\pi+\epsilon} \cos(3x) \cos(4x) \, dx = - \left( \frac{\sin(7\epsilon)}{7} + \sin(\epsilon) \right)$.
This integral is generally not zero if $\epsilon \neq 0$ and $\epsilon$ is not an integer multiple of $\pi$. For our small $\epsilon = 10^{-4}$, the integral is approximately $-2 \times 10^{-4} \neq 0$.
Therefore, $\cos(3x)$ and $\cos(4x)$ are not orthogonal on the interval $[-\pi-\epsilon, \pi+\epsilon]$ unless $\epsilon=0$ or $\epsilon=k\pi$ for some integer $k$. This calculation explicitly shows that changing the interval slightly (by $\epsilon$) from $[-\pi, \pi]$ breaks the orthogonality property.
