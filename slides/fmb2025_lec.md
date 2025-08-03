# VPL01-FMB-L1S1
##　シンボル変数（添字付き）の設計
<mark><1,1></mark>

モジュールインポート設定は以下：
```python
import sympy as sym
import math
from sympy import sin, cos, tan, Matrix
from sympy.abc import *
```

<mark><1,2></mark>
<b>Level 1:</b>

sym.Symbolを用いて、変数$n$を定義せよ（結果は、ans1に格納）。

<mark><1,3></mark>
<b>Level 2:</b>

同様に、sym.IndexedBaseを用いて、変数$a,b$を定義せよ（結果は、ans2にタプルで格納；つまり、ans2=($a,b$)のような形で出力）。

<mark><1,4></mark>
<b>Level 3:</b>

Level2のa,bに対して、添字番号0、1をそれぞれ加えて、変数$a_0,b_1$を定義せよ（結果は、ans3にタプルで格納；つまり、ans3=($a_0,b_1$)のような形で出力）。

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

<mark><1,6></mark>
<b>Level 1:</b>

$\theta$を変数とする、サイン関数$\sin()$を定義せよ（結果は、ans1に格納）。

<mark><1,7></mark>
<b>Level 2:</b>

sym.expandを用いて、Level 1で定義した式に、式$n+1$を掛け算した計算を展開せよ（結果は、ans2に格納；つまり、ans2=(a,b)のように、aに展開前、bに展開後を出力）。

<mark><1,8></mark>
<b>Level 3:</b>

sym.simplifyを用いて、Level 1で定義した式に、式$\frac{n}{m}$を掛け算した式をb1、式$\frac{1}{2m}$を掛け算した式をb2として、b1+b2を通分せよ（結果は、ans3に格納；つまり、ans2=(b1,b1,b1+b2,sym.simplify(b1+b2))のように結果出力）。

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

<mark><1,10></mark>
<b>Level 1:</b>

sym.Eqを用いて、$a_n$と$n\sin(n\theta)$を等式にして、Eq1を$a_n = n\sin(n\theta)$として定義せよ（結果は、ans1に格納）。

<mark><1,11></mark>
<b>Level 2:</b>

.subsメソッドを用いて、Level 1で定義した式の$\theta$を$ 2\phi$に置き換えた式を出力せよ（結果は、ans2に格納；つまり、ans2=(a,b)のように、aに置き換え前、bに置き換え後を出力）。

<mark><1,12></mark>
<b>Level 3:</b>

.subsメソッドを用いて、Level 2で定義した式の$n$に3を代入した式を出力せよ（結果は、ans2に格納；つまり、ans2=(a,b)のように、aに置き換え前、bに置き換え後を出力）。

--

---

# VPL01-FMB-L2S1
##　シンボル変数（添字付き）の設計
<mark><2,1></mark>

モジュールインポート設定は以下：
```python
import sympy as sym
import math
from sympy import sin, cos, tan, Matrix
from sympy.abc import *
```

<mark><1,2></mark>
<b>Level 1:</b>

sym.Symbolを用いて、変数$n$を定義せよ（結果は、ans1に格納）。

<mark><1,3></mark>
<b>Level 2:</b>

同様に、sym.IndexedBaseを用いて、変数$a,b$を定義せよ（結果は、ans2にタプルで格納；つまり、ans2=($a,b$)のような形で出力）。

<mark><1,4></mark>
<b>Level 3:</b>

Level2のa,bに対して、添字番号0、1をそれぞれ加えて、変数$a_0,b_1$を定義せよ（結果は、ans3にタプルで格納；つまり、ans3=($a_0,b_1$)のような形で出力）。
