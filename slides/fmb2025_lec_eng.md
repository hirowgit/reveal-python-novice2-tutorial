# VPL01-FMB-L1S1
## Design of symbol variables (with subscripts) For a detailed explanation, <mark>[<1,1>](https://hirowgit.github.io/reveal-pytあまぞああ

h




o



n-


　
n






ovice2-tutorial/fmb2025_lec_eng.html) </mark>

The module import settings are:

```python
import sympy as sym
import math
from sympy import sin, cos, tan, Matrix
from sympy.abc import *
```

--

<b>Level 1:</b>

For a detailed explanation, see:
<mark>[<1,2>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec_eng.html#/0/1) </mark>

Define the variable $n$ using sym.Symbol.

```python
n =sym.Symbol('n')
```

--

<b>Level 2:</b>

For a detailed explanation, see
<mark>[<1,3>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec_eng.html#/0/2) </mark>

Similarly, define variables $a$ and $b$ using sym.IndexedBase.

```python
a=sym.IndexedBase('a')
b=sym.IndexedBase('b')
```

--

<b>Level 3:</b>

For a detailed explanation, see:
<mark>[<1,4>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lecc_eng.html#/0/3) </mark>

Add subscript numbers 0 and 1 to a and b in Level 2, respectively, to define variables $a\_0, b\_1$.

```python
a[0]
b[1]
```

--

# VPL01-FMB-L1S2
## Symbolic calculation expansion

<mark>[<1,5>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec_eng.html#/0/4) </mark>

The module import settings are:

```python
import sympy as sym
import math
from sympy import sin, cos, tan, Matrix
from sympy.abc import *
```
--

<b>Level 1:</b>

For a detailed explanation, see:
<mark>[<1,6>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec_eng.html#/0/5) </mark>

Define the sine function $\sin()$ with $\theta$ as a variable.

```python
sin(theta)
```

--

<b>Level 2:</b>

For a detailed explanation, see:
詳細解説はこちら：
<mark>[<1,7>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec_eng.html#/0/6) </mark>

Using sym.expand, we expand the expression defined in Level 1 by multiplying it by the expression $n+1$.

```python
a1=((n+1)*sin(theta))
sym.expand(a1)
```

--

<b>Level 3:</b>

For a detailed explanation, see:

<mark>[<1,8>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec.html#/0/7) </mark>

Using sym.simplify, multiply the equation defined in Level 1 by the expression $\frac{n}{m}$ to obtain b1, and multiply it by the expression $\frac{1}{2m}$ to obtain b2, and then reduce b1+b2 to a common denominator.

```python
m =sym.Symbol('m')
b1=n/m*sin(theta)
b2=1/(2*m)*sin(theta)
sym.simplify(b1+b2)
```

--

# VPL01-FMB-L1S3
##　Equation design

<mark>[<1,9>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec_eng.html#/0/8) </mark>

The module import settings are:

```python
import sympy as sym
import math
from sympy import sin, cos, tan, Matrix
from sympy.abc import *
```
--

<b>Level 1:</b>

For a detailed explanation, see:
<mark>[<1,10>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec_eng.html#/0/9) </mark>

Using sym.Eq, equate $a_n$ and $n\sin(n\theta)$ and define Eq1 as $a_n = n\sin(n\theta)$.

```python
Eq1=sym.Eq(a[n],sym.expand(n*sin(n*theta)))
```
--

<b>Level 2:</b>

For a detailed explanation, see:
<mark>[<1,11>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec_eng.html#/0/10) </mark>

Using the .subs method, we output the equation defined in Level 1 with $\theta$ replaced by $2\phi$.

```python
Eq1.subs({theta:2*phi})
```

--

<b>Level 3:</b>

For a detailed explanation, see:
<mark>[<1,12>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec_eng.html#/0/11) </mark>


Using the .subs method, we output an expression in which 3 is substituted for $n$ in the expression defined in Level 2.

```python
Eq2=Eq1.subs({n:3})
Eq2.subs({theta:2*phi})
```
--

---

# VPL02-FMB-L2S1

##　Calculating the limit. For a detailed explanation, see:
<mark>[<2,1>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec_eng.html#/1) </mark>

The module import settings are:

```python
import sympy as sym
import math
from sympy import sin, cos, tan, Matrix
from sympy.abc import *
from sympy.series.limitseq import limit_seq
```
--

<b>Level 1:</b>

For a detailed explanation, see:
<mark>[<2,2>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec_eng.html#/1/1) </mark>

Use sym.Symbol (however, set "integer=True" to limit $n$ to integers) to define the expression $n$, and use sym.limit to find its limit lim1.

```python
n = sym.Symbol('n', integer=True)
expr1 = n
lim1 = sym.limit(expr1, n, float('inf'))
```

--


<b>Level 2:</b>

For a detailed explanation, see: 
<mark>[<2,3>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec_eng.html#/1/2) </mark>

Use sym.Symbol (but set "integer=True" to make sure $n$ is an integer) to define the expression $\frac{1}{n}$, and use sym.limit to find its limit.

```python
n = sym.Symbol('n', integer=True)
expr2 = 1/n
lim2 = sym.limit(expr2, n, float('inf'))
```

--

<b>Level 3:</b>

For a detailed explanation, see:
<mark>[<2,4>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec_eng.html#/1/3) </mark>

Use sym.Symbol (but set "integer=True" to make sure $n$ is an integer) to define the expression $\frac{1}{n^2}$, and use sym.limit to find its limit.

```python
n = sym.Symbol('n', integer=True)
expr3 = 1/n**2
lim3 = sym.limit(expr3, n, float('inf'))
```

--


# VPL02-FMB-L2S2

## Calculating limits (part 2)

For a detailed explanation, see:
<mark>[<2,5>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec_eng.html#/1/4) </mark>

The module import settings are:

```python
import sympy as sym
import math
from sympy import sin, cos, tan, Matrix
from sympy.abc import *
from sympy.series.limitseq import limit_seq
```

--

<b>Level 1:</b>

For a detailed explanation, see:
<mark>[<2,6>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec_eng.html#/1/5) </mark>

Use sym.Symbol (but set "integer=True" to allow only integers for $n$) to define the equation $\frac{n + 1}{n^{2} + 1}$, and use sym.limit to find its limit lim1.


```python
n = sym.Symbol('n', integer=True)
expr1 = (n + 1)/(n**2 + 1)
lim1 = sym.limit(expr1, n, float('inf'))
```

--

<b>Level 2:</b>

For a detailed explanation, see:
<mark>[<2,7>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec_eng.html#/1/6) </mark>

Use sym.Symbol (but set "integer=True" so that $n$ is an integer only) to define the expression $\frac{2 n^{2} + 1}{n^{2} + 3}$, and use sym.limit to find its limit.

```python
n = sym.Symbol('n', integer=True)
expr2 = (2*n**2 + 1)/(n**2 + 3)
lim2 = sym.limit(expr2, n, float('inf'))
```

--

<b>Level 3:</b>

For a detailed explanation, see:
<mark>[<2,8>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec_eng.html#/1/7) </mark>

Use sym.Symbol (but set "integer=True" so that $n$ is an integer only) to define the expression $\frac{2 n^{3} + 1}{n^{2} + 5}$, and use sym.limit to find its limit.

```python
n = sym.Symbol('n', integer=True)
expr3 = (2*n**3 + 1)/(n**2 + 5)
lim3 = sym.limit(expr3, n, float('inf'))
```

--

# VPL02-FMB-L2S3

##　Verification of differentiability (equivalent of right and left derivatives)

For a detailed explanation, see:
<mark>[<2,9>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec_eng.html#/1/8) </mark>

The module import settings and the judgment function are as follows:

```python
import sympy as sym
import math
from sympy import sin, cos, tan, Matrix
from sympy.abc import *
from sympy.series.limitseq import limit_seq

vsTF=lambda rm,lm:(rm==lm) & ~(isinstance(rm,sym.AccumBounds))
tfFe=lambda rm,lm,x: 'This function is differentiable '+'at x = %d.'%(x) if vsTF(rm,lm) else 'This function is NOT differentiable'+' at x = %d.'%(x)
```

--

<b>Level 1:</b>

For a detailed explanation, see:
<mark>[<2,10>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec_eng.html#/1/9) </mark>

Using sym.Symbol (however, set "integer=True" and limit $n$ to integers only), define the expression $\frac{1}{n}$, and use sym.limit (expression, variable, location where the variable approaches (e.g., 0), for the right limit: dir='+', for the left limit: dir='-') to find the limit (right/left), and check whether it is differentiable from the agreement.

```python
n = sym.Symbol('n', integer=True)
expr1 = 1/n
right_lim1 = sym.limit(expr1, n, 0, dir='+') 
left_lim1 = sym.limit(expr1, n, 0, dir='-')
tf1 = tfFe(right_lim1,left_lim1,0)
```

--

<b>Level 2:</b>

For a detailed explanation, see:
<mark>[<2,11>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec_eng.html#/1/10) </mark>

Using sym.Symbol (however, set "integer=True" and limit $n$ to integers only), define the formula $\sin\frac{1}{n}$, and use sym.limit (formula, variable, location where the variable approaches (e.g., 0), for the right limit: dir='+', for the left limit: dir='-') to find the limit (right/left), and check whether it is differentiable from the agreement.

```python
n = sym.Symbol('n', integer=True)
expr2 = sin(1/n)
right_lim2 = sym.limit(expr2, n, 0, dir='+') 
left_lim2 = sym.limit(expr2, n, 0, dir='-')
tf2 = tfFe(right_lim2,left_lim2,0)
```

--

<b>Level 3:</b>

For a detailed explanation, see:
<mark>[<2,12>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec_eng.html#/1/11) </mark>

Using sym.Symbol (however, set "integer=True" and limit $n$ to integers only), define the formula $n \sin\frac{1}{n}$, and use sym.limit (formula, variable, location where the variable approaches (e.g., 0), for the right limit: dir='+', for the left limit: dir='-') to find the limit (right/left), and check whether it is differentiable from the agreement.

```python
n = sym.Symbol('n', integer=True)
expr3 = n*sin(1/n)
right_lim3 = sym.limit(expr3, n, 0, dir='+') 
left_lim3 = sym.limit(expr3, n, 0, dir='-')
tf3 = tfFe(right_lim3,left_lim3,0)
```

--

---

# VPL03-FMB-L3S1

##　Assembly division. 

Detailed explanation here:
<mark>[<3,1>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec_eng.html#/2) </mark>

The function settings are as follows:

```python
def synthetic_division_b(coeff,alpha):
    b=[coeff[0]]
    for s in coeff[1:]:
        b=b+[s+b[-1]*alpha]
    return np.array(b)
```

<b>Level 1:</b>

For a detailed explanation, see:
<mark>[<3,2>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec_eng.html#/2/1) </mark>

Using the above function synthetic\_division\_b, let coeff be the coefficient of the equation and alpha be the $\alpha$ of $f(\alpha)$. Here, we will find the calculation result for the equation $f(x)=2x^4-3x^3+4x^2+5x-6$ and $f(1.25)$.

```python
coeff1 = [2,-3,4,5,-6]
alpha1 = 1.25
synthetic_division_b(coeff1,alpha1)
```

--

<b>Level 2:</b>

For a detailed explanation, see: 
<mark>[<3,3>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec_eng.html#/2/2) </mark>

Using the above function synthetic\_division\_b, let coeff be the coefficient of the equation and alpha be the $\alpha$ of $f(\alpha)$. Here, we will find the calculation result for the equation $f(x)=3x^4-2x^3-10x^2+5x-6$ and $f(2)$.

```python
coeff2 = [3,-2,-10,5,-6]
alpha2 = 2
synthetic_division_b(coeff2,alpha2)
```

--

<b>Level 3:</b>

For a detailed explanation, see:
<mark>[<3,4>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec_eng.html#/2/3) </mark>

Using the above function synthetic\_division\_b, let coeff be the coefficient of the equation and alpha be the $\alpha$ of $f(\alpha)$. Here, we will find the calculation result for the equation $f(x)=5x^5-4x^4-3x^3+2x^2+x-6$ and $f(0.5)$.


```python
coeff3 = [5,-4,-3,2,1,-6]
alpha3 = 0.5
synthetic_division_b(coeff3,alpha3)
```


--

# VPL03-FMB-L3S2

##　Assembly division. 
Detailed explanation here:
<mark>[<3,5>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec_eng.html#/2/4) </mark>

The function settings are as follows:

```python
def synthetic_division_bc(coeff,alpha):
    b,c=[coeff[0]],[coeff[0]]
    for s in coeff[1:]:
        b=b+[s+b[-1]*alpha]
        c=c+[b[-1]+c[-1]*alpha]
    c=c[:-1]
    return np.array(b),np.array(c)
```

--

<b>Level 1:</b>

For a detailed explanation, see:
<mark>[<3,6>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec_eng.html#/2/5) </mark>

Using the above function synthetic\_division\_bc, where coeff is the coefficient of the equation and alpha is the $\alpha$ of $f(\alpha)$, we will calculate the results for the equations $f(x)=5x^5-4x^4-3x^3+2x^2+x-6$, $f(0.5)$, and $f'(0.5)$.

```python
coeff1 = [5,-4,-3,2,1,-6]
alpha1 = 0.5
synthetic_division_bc(coeff1,alpha1)
```

--

<b>Level 2:</b>

For a detailed explanation, see: 
<mark>[<3,7>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec_eng.html#/2/6) </mark>

Using the above function synthetic\_division\_bc, where coeff is the coefficient of the equation and alpha is the $\alpha$ of $f(\alpha)$, we will calculate the equations $f(x)=3x^5-28x^3+x^2+5$, $f(3)$, and $f'(3)$.

```python
coeff2 = [3,0,-28,1,0,5]
alpha2 = 3
synthetic_division_bc(coeff2,alpha2)
```

--

<b>Level 3:</b>

For a detailed explanation, see:
<mark>[<3,8>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec_eng.html#/2/7) </mark>

Using the above function synthetic\_division\_bc, where coeff is the coefficient of the equation and alpha is the $\alpha$ of $f(\alpha)$, we will calculate the results for the equations $f(x)=3x^5-28x^3+x^2+5$, $f(-2)$, and $f'(-2)$.

```python
coeff3 = [3,0,-28,1,0,5]
alpha3 = -2
synthetic_division_bc(coeff3,alpha3)
```

--


---

# VPL04-FMB-L4S1

##　Lagrange's interpolation coefficient function $L\_i(x)$ 
For a detailed explanation, see:
<mark>[<4,1>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec_eng.html#/3) </mark>

The function settings are as follows:

```python
def LiFgen(n0,i0):
    import sympy as sym
    n,i,j,k=sym.symbols('n i j k')
    x=sym.IndexedBase('x')
    xh=sym.Symbol('\hat{x}')
    exprP1 = sym.Piecewise((xh - x[k], sym.Ne(k, i)), (1, True))
    exprP2 = sym.Piecewise((x[i] - x[k], sym.Ne(k, i)), (1, True))
    prX7=sym.Product(exprP1/exprP2, (k, 0, n))
    Li=prX7.subs({n:n0,i:i0}).doit()
    return Li
```

--

<b>Level 1:</b>

For a detailed explanation, see:
<mark>[<4,2>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec_eng.html#/3/1) </mark>

Using the above function LiFgen, we give arguments $n$ and $i$ to obtain the Lagrange interpolation coefficient function $L_i(x)$. Here, we will find the calculation results for $n=5$ and $i=3$.


```python
n1,i1 = 5,3
LiFgen(n1,i1)
```

--

<b>Level 2:</b>

For a detailed explanation, see:
<mark>[<4,3>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec_eng.html#/3/2) </mark>

Using the above function LiFgen, we give arguments $n$ and $i$ to obtain the Lagrange interpolation coefficient function $L_i(x)$. Here, we will find the calculation results for $n=10$ and $i=7$.

```python
n2,i2 = 10,7
LiFgen(n2,i2)
```

--
<b>Level 3:</b>

For a detailed explanation, see:
<mark>[<4,4>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec_eng.html#/3/3) </mark>

Using the above function LiFgen, we give arguments $n$ and $i$ to obtain the Lagrange interpolation coefficient function $L_i(x)$. Here, we will find the calculation results for $n=15$ and $i=8$.

```python
n3,i3 = 15,8
LiFgen(n3,i3)
```

--
