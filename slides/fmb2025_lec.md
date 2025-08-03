# VPL01-FMB-L1S1
##　シンボル変数（添字付き）の設計
詳細解説はこちら：
<mark>[<1,1>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec.html) </mark>

モジュールインポート設定は以下：
```python
import sympy as sym
import math
from sympy import sin, cos, tan, Matrix
from sympy.abc import *
```

$\sin,\cos,\tan$は、sym.をつけなくても呼び出せる。
ギリシャ文字（$\theta$など）も同様。

--

<b>Level 1:</b>

詳細解説はこちら：
<mark>[<1,2>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec.html#/0/1) </mark>

sym.Symbolを用いて、変数$n$を定義します。

```python
n =sym.Symbol('n')
```

--

<b>Level 2:</b>

詳細解説はこちら：
<mark>[<1,3>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec.html#/0/2) </mark>

同様に、sym.IndexedBaseを用いて、変数$a,b$を定義します。

```python
a=sym.IndexedBase('a')
b=sym.IndexedBase('b')
```
--

<b>Level 3:</b>

詳細解説はこちら：
<mark>[<1,4>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec.html#/0/3) </mark>


Level2のa,bに対して、添字番号0、1をそれぞれ加えて、変数$a_0,b_1$を定義します。

```python
a[0]
b[1]
```

--

# VPL01-FMB-L1S2
##　シンボル計算の展開
<mark><1,5></mark>

モジュールインポート設定は以下：
```python
import sympy as sym
import math
from sympy import sin, cos, tan, Matrix
from sympy.abc import *
```
--

<b>Level 1:</b>

詳細解説はこちら：
<mark>[<1,6>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec.html#/0/5) </mark>


$\theta$を変数とする、サイン関数$\sin()$を定義します。

```python
sin(theta)
```

--

<b>Level 2:</b>

詳細解説はこちら：
<mark>[<1,7>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec.html#/0/6) </mark>


sym.expandを用いて、Level 1で定義した式に、式$n+1$を掛け算した計算を展開します。

```python
a1=((n+1)*sin(theta))
sym.expand(a1)
```

--

<b>Level 3:</b>

詳細解説はこちら：
<mark>[<1,8>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec.html#/0/7) </mark>


sym.simplifyを用いて、Level 1で定義した式に、式$\frac{n}{m}$を掛け算した式をb1、式$\frac{1}{2m}$を掛け算した式をb2として、b1+b2を通分します。

```python
m =sym.Symbol('m')
b1=n/m*sin(theta)
b2=1/(2*m)*sin(theta)
sym.simplify(b1+b2)
```

--

# VPL01-FMB-L1S3
##　等式の設計
<mark><1,9></mark>

モジュールインポート設定は以下：
```python
import sympy as sym
import math
from sympy import sin, cos, tan, Matrix
from sympy.abc import *
```
--

<b>Level 1:</b>

詳細解説はこちら：
<mark>[<1,10>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec.html#/0/9) </mark>


sym.Eqを用いて、$a_n$と$n\sin(n\theta)$を等式にして、Eq1を$a_n = n\sin(n\theta)$として定義します。

```python
Eq1=sym.Eq(a[n],sym.expand(n*sin(n*theta)))
```
--

<b>Level 2:</b>

詳細解説はこちら：
<mark>[<1,11>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec.html#/0/10) </mark>


.subsメソッドを用いて、Level 1で定義した式の$\theta$を$ 2\phi$に置き換えた式を出力します。

```python
Eq1.subs({theta:2*phi})
```

--

<b>Level 3:</b>

詳細解説はこちら：
<mark>[<1,12>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec.html#/0/11) </mark>


.subsメソッドを用いて、Level 2で定義した式の$n$に3を代入した式を出力します。

```python
Eq2=Eq1.subs({n:3})
Eq2.subs({theta:2*phi})
```
--

---

# VPL02-FMB-L2S1
##　極限の計算
詳細解説はこちら：
<mark>[<2,1>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec.html#/1) </mark>

モジュールインポート設定は以下：
```python
import sympy as sym
import math
from sympy import sin, cos, tan, Matrix
from sympy.abc import *
from sympy.series.limitseq import limit_seq
```
---

<b>Level 1:</b>

詳細解説はこちら：
<mark>[<2,2>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec.html#/1/1) </mark>

sym.Symbol（但し、"integer=True"を設定して$n$は整数のみとする）を用いて、式$n$を定義して、sym.limitを用いて、その極限lim1を求めます。

```python
n = sym.Symbol('n', integer=True)
expr1 = n
lim1 = sym.limit(expr1, n, float('inf'))
```

--

<b>Level 2:</b>

詳細解説はこちら：
<mark>[<2,3>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec.html#/1/2) </mark>

sym.Symbol（但し、"integer=True"を設定して$n$は整数のみとする）を用いて、式$\frac{1}{n}$を定義して、sym.limitを用いて、その極限を求めます。

```python
n = sym.Symbol('n', integer=True)
expr2 = 1/n
lim2 = sym.limit(expr2, n, float('inf'))
```

--

<b>Level 3:</b>

詳細解説はこちら：
<mark>[<2,4>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec.html#/1/3) </mark>

sym.Symbol（但し、"integer=True"を設定して$n$は整数のみとする）を用いて、式$\frac{1}{n^2}$を定義して、sym.limitを用いて、その極限を求めます。

```python
n = sym.Symbol('n', integer=True)
expr3 = 1/n**2
lim3 = sym.limit(expr3, n, float('inf'))
```

--

# VPL02-FMB-L2S2
##　極限の計算（その２）

詳細解説はこちら：
<mark>[<2,5>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec.html#/1/4) </mark>

モジュールインポート設定は以下：
```python
import sympy as sym
import math
from sympy import sin, cos, tan, Matrix
from sympy.abc import *
from sympy.series.limitseq import limit_seq
```

--

<b>Level 1:</b>

詳細解説はこちら：
<mark>[<2,6>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec.html#/1/5) </mark>

sym.Symbol（但し、"integer=True"を設定して$n$は整数のみとする）を用いて、式$\frac{n + 1}{n^{2} + 1}$を定義して、sym.limitを用いて、その極限lim1を求めます。

```python
n = sym.Symbol('n', integer=True)
expr1 = (n + 1)/(n**2 + 1)
lim1 = sym.limit(expr1, n, float('inf'))
```

--

<b>Level 2:</b>

詳細解説はこちら：
<mark>[<2,7>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec.html#/1/6) </mark>

sym.Symbol（但し、"integer=True"を設定して$n$は整数のみとする）を用いて、式$\frac{2 n^{2} + 1}{n^{2} + 3}$を定義して、sym.limitを用いて、その極限を求めます。

```python
n = sym.Symbol('n', integer=True)
expr2 = (2*n**2 + 1)/(n**2 + 3)
lim2 = sym.limit(expr2, n, float('inf'))
```

--

<b>Level 3:</b>

詳細解説はこちら：
<mark>[<2,8>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec.html#/1/7) </mark>

sym.Symbol（但し、"integer=True"を設定して$n$は整数のみとする）を用いて、式$\frac{2 n^{3} + 1}{n^{2} + 5}$を定義して、sym.limitを用いて、その極限を求めます。

```python
n = sym.Symbol('n', integer=True)
expr3 = (2*n**3 + 1)/(n**2 + 5)
lim3 = sym.limit(expr3, n, float('inf'))
```

--

# VPL02-FMB-L2S3
##　微分可能性の検証（右側微分と左側微分の一致）

詳細解説はこちら：
<mark>[<2,9>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec.html#/1/8) </mark>

モジュールインポート設定と、判定関数は以下：
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

詳細解説はこちら：
<mark>[<2,10>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec.html#/1/9) </mark>

sym.Symbol（但し、"integer=True"を設定して$n$は整数のみとする）を用いて、式$\frac{1}{n}$を定義して、sym.limit (式, 変数, 変数が近づく場所（0など）, 右側極限の場合：dir='+', 左側極限の場合：dir='-') を用いて、その極限（右・左）を求め、その一致から微分可能かどうか調べます。

```python
n = sym.Symbol('n', integer=True)
expr1 = 1/n
right_lim1 = sym.limit(expr1, n, 0, dir='+') 
left_lim1 = sym.limit(expr1, n, 0, dir='-')
tf1 = tfFe(right_lim1,left_lim1,0)
```

--

<b>Level 2:</b>

詳細解説はこちら：
<mark>[<2,11>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec.html#/1/10) </mark>

sym.Symbol（但し、"integer=True"を設定して$n$は整数のみとする）を用いて、式$\sin\frac{1}{n}$を定義して、sym.limit (式, 変数, 変数が近づく場所（0など）, 右側極限の場合：dir='+', 左側極限の場合：dir='-') を用いて、その極限（右・左）を求め、その一致から微分可能かどうか調べます。

```python
n = sym.Symbol('n', integer=True)
expr2 = sin(1/n)
right_lim2 = sym.limit(expr2, n, 0, dir='+') 
left_lim2 = sym.limit(expr2, n, 0, dir='-')
tf2 = tfFe(right_lim2,left_lim2,0)
```

--

<b>Level 3:</b>

詳細解説はこちら：
<mark>[<2,12>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec.html#/1/11) </mark>

sym.Symbol（但し、"integer=True"を設定して$n$は整数のみとする）を用いて、式$n \sin\frac{1}{n}$を定義して、sym.limit (式, 変数, 変数が近づく場所（0など）, 右側極限の場合：dir='+', 左側極限の場合：dir='-') を用いて、その極限（右・左）を求め、その一致から微分可能かどうか調べます。

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
##　組立除法
詳細解説はこちら：
<mark>[<3,1>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec.html#/2) </mark>

関数の設定は以下：
```python
def synthetic_division_b(coeff,alpha):
    b=[coeff[0]]
    for s in coeff[1:]:
        b=b+[s+b[-1]*alpha]
    return np.array(b)
```

--

<b>Level 1:</b>

詳細解説はこちら：
<mark>[<3,2>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec.html#/2/1) </mark>

上記の関数synthetic_division_bを用い、coeffに方程式の各係数、alphaに$f(\alpha)$の$\alpha$を入れるものとする。ここで、式$f(x)=2x^4-3x^3+4x^2+5x-6$、$f(1.25)$についての計算結果を求めます。

```python
coeff1 = [2,-3,4,5,-6]
alpha1 = 1.25
synthetic_division_b(coeff1,alpha1)
```

--

<b>Level 2:</b>

詳細解説はこちら：
<mark>[<3,3>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec.html#/2/2) </mark>

上記の関数synthetic_division_bを用い、coeffに方程式の各係数、alphaに$f(\alpha)$の$\alpha$を入れるものとする。ここで、式$f(x)=3x^4-2x^3-10x^2+5x-6$、$f(2)$についての計算結果を求めます。

```python
coeff2 = [3,-2,-10,5,-6]
alpha2 = 2
synthetic_division_b(coeff2,alpha2)
```

--

<b>Level 3:</b>

詳細解説はこちら：
<mark>[<3,4>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec.html#/2/3) </mark>

上記の関数synthetic_division_bを用い、coeffに方程式の各係数、alphaに$f(\alpha)$の$\alpha$を入れるものとする。ここで、式$f(x)=5x^5-4x^4-3x^3+2x^2+x-6$、$f(0.5)$についての計算結果を求めます。

```python
coeff3 = [5,-4,-3,2,1,-6]
alpha3 = 0.5
synthetic_division_b(coeff3,alpha3)
```


--

# VPL03-FMB-L3S2
##　組立除法
詳細解説はこちら：
<mark>[<3,5>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec.html#/2/4) </mark>

関数の設定は以下：
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

詳細解説はこちら：
<mark>[<3,6>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec.html#/2/5) </mark>

上記の関数synthetic_division_bcを用い、coeffに方程式の各係数、alphaに$f(\alpha)$の$\alpha$を入れるものとする。ここで、式$f(x)=5x^5-4x^4-3x^3+2x^2+x-6$、$f(0.5)$、$f'(0.5)$についての計算結果を求めます。

```python
coeff1 = [5,-4,-3,2,1,-6]
alpha1 = 0.5
synthetic_division_bc(coeff1,alpha1)
```

--

<b>Level 2:</b>

詳細解説はこちら：
<mark>[<3,7>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec.html#/2/6) </mark>

上記の関数synthetic_division_bcを用い、coeffに方程式の各係数、alphaに$f(\alpha)$の$\alpha$を入れるものとする。ここで、式$f(x)=3x^5-28x^3+x^2+5$、$f(3)$、$f'(3)$についての計算結果を求めます。

```python
coeff2 = [3,0,-28,1,0,5]
alpha2 = 3
synthetic_division_bc(coeff2,alpha2)
```

--

<b>Level 3:</b>

詳細解説はこちら：
<mark>[<3,8>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec.html#/2/7) </mark>

上記の関数synthetic_division_bcを用い、coeffに方程式の各係数、alphaに$f(\alpha)$の$\alpha$を入れるものとする。ここで、式$f(x)=3x^5-28x^3+x^2+5$、$f(-2)$、$f'(-2)$についての計算結果を求めます。

```python
coeff3 = [3,0,-28,1,0,5]
alpha3 = -2
synthetic_division_bc(coeff3,alpha3)
```

--


---

# VPL04-FMB-L4S1
##　ラグランジュの補間係数関数 $L_i(x)$
詳細解説はこちら：
<mark>[<4,1>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec.html#/3) </mark>

関数の設定は以下：
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

詳細解説はこちら：
<mark>[<4,2>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec.html#/3/1) </mark>

上記の関数LiFgenを用い、引数に$n$,$i$を与えて、ラグランジュの補間係数関数 $L_i(x)$を得るものとする。ここで、$n=5$,$i=3$についての計算結果を求めます。

```python
n1,i1 = 5,3
LiFgen(n1,i1)
```

--

<b>Level 2:</b>

詳細解説はこちら：
<mark>[<4,3>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec.html#/3/2) </mark>

上記の関数LiFgenを用い、引数に$n$,$i$を与えて、ラグランジュの補間係数関数 $L_i(x)$を得るものとする。ここで、$n=10$,$i=7$についての計算結果を求めます。

```python
n2,i2 = 10,7
LiFgen(n2,i2)
```

--

<b>Level 3:</b>

詳細解説はこちら：
<mark>[<4,4>](https://hirowgit.github.io/reveal-python-novice2-tutorial/fmb2025_lec.html#/3/3) </mark>

上記の関数LiFgenを用い、引数に$n$,$i$を与えて、ラグランジュの補間係数関数 $L_i(x)$を得るものとする。ここで、$n=15$,$i=8$についての計算結果を求めます。

```python
n3,i3 = 15,8
LiFgen(n3,i3)
```

--
