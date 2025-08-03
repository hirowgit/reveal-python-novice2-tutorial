# VPL01-FMB-L1S1
## Designing Symbol Variables (with Subscripts)
For more details, see:
<mark>[<1,1>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec.html)</mark>

Module import settings are as follows:
```python
import sympy as sym
import math
from sympy import sin, cos, tan, Matrix
from sympy.abc import *
```

<b>Level 1:</b>

For more details, see:
<mark>[<1,2>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec.html#/0/1)</mark>

Define the variable $n$ using sym.Symbol (the result will be stored in ans1).

<b>Level 2:</b>

For a detailed explanation, see:
<mark>[<1,3>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec.html#/0/2)</mark>

Similarly, define variables $a, b$ using sym.IndexedBase (the results are stored as a tuple in ans2; i.e., output in the form ans2=($a,b$)).

<b>Level 3:</b>

For a detailed explanation, see:
<mark>[<1,4>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec.html#/0/3)</mark>

Add subscripts 0 and 1 to a and b in Level 2, respectively, to define variables $a_0,b_1$. (The results are stored in ans3 as a tuple; i.e., output in the form ans3=($a_0,b_1$).)

--

# VPL01-FMB-L1S2
## Symbolic Arithmetic Expansion
<mark><1,5></mark>

Module import settings are as follows:
```python
import sympy as sym
import math
from sympy import sin, cos, tan, Matrix
from sympy.abc import *
```

<b>Level 1:</b>

For a detailed explanation, see:
<mark>[<1,6>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec.html#/0/5)</mark>

Define the sine function $\sin()$, taking $\theta$ as the variable (the result is stored in ans1).

<b>Level 2:</b>

For a detailed explanation, see:
<mark>[<1,7>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec.html#/0/6)</mark>

Use sym.expand to expand the expression defined in Level 1 by multiplying it by the expression $n+1$. (The result is stored in ans2; that is, the unexpanded result is stored in a and the expanded result is stored in b, as in ans2=(a,b).)

<b>Level 3:</b>

For a detailed explanation, see:
<mark>[<1,8>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec.html#/0/7)</mark>

Using sym.simplify, multiply the equation defined in Level 1 by the expression $\frac{n}{m}$ to obtain b1, and multiply it by the expression $\frac{1}{2m}$ to obtain b2. Reduce b1 + b2 by a factor of b1 + b2. (The result is stored in ans3; i.e., the output is ans2 = (b1, b1, b1 + b2, sym.simplify(b1 + b2)).)

--

# VPL01-FMB-L1S3
## Designing Equations
<mark><1,9></mark>

Module import settings are as follows:
```python
import sympy as sym
import math
from sympy import sin, cos, tan, Matrix
from sympy.abc import *
```

<b>Level 1:</b>

For a detailed explanation, see:
<mark>[<1,10>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec.html#/0/9)</mark>

Using sym.Eq, equate $a_n$ and $n\sin(n\theta)$, and define Eq1 as $a_n = n\sin(n\theta)$ (store the result in ans1).

<b>Level 2:</b>

For a detailed explanation, see:
<mark>[<1,11>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec.html#/0/10)</mark>

Use the .subs method to output the equation defined in Level 1, replacing $\theta$ with $2\phi$. (The result is stored in ans2; that is, the original value is output as a, and the resulting value is output as b, e.g., ans2=(a,b).)

<b>Level 3:</b>

For a detailed explanation, see:
<mark>[<1,12>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec.html#/0/11)</mark>

Use the .subs method to output the equation defined in Level 2 by substituting 3 for $n$. (The result is stored in ans2; that is, the result before substitution is stored in a and the result after substitution is stored in b, as in ans2=(a,b).)

--

---

# VPL01-FMB-L1S1
## Designing Symbol Variables (with Subscripts)
For more details, see:
<mark>[<1,1>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec.html)</mark>

Module import settings are as follows:
```python
import sympy as sym
import math
from sympy import sin, cos, tan, Matrix
from sympy.abc import *
```

<b>Level 1:</b>

For more details, see:
<mark>[<1,2>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec.html#/0/1)</mark>

Define the variable $n$ using sym.Symbol (the result will be stored in ans1).

<b>Level 2:</b>

For a detailed explanation, see:
<mark>[<1,3>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec.html#/0/2)</mark>

Similarly, define variables $a, b$ using sym.IndexedBase (the results are stored as a tuple in ans2; i.e., output in the form ans2=($a,b$)).

<b>Level 3:</b>

For a detailed explanation, see:
<mark>[<1,4>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec_eng.html#/0/3)</mark>

Add subscripts 0 and 1 to a and b in Level 2, respectively, to define variables $a_0,b_1$. (The results are stored in ans3 as a tuple; i.e., output in the form ans3=($a_0,b_1$).)
