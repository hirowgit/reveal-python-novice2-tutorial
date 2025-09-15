# L5M1S1

## map()関数

ここでは、map()関数について学びます。

* map()関数は、リストのような複数の値を持つ変数（iterable、イテラブル）に対して、同じ関数をそのすべての値に適用するものです。
* あとで学習するNumpyモジュールでは複数の値に自動的に適用されますが、通常関数は１つの値に適用するように設計されているため、関数の引数（入力）にリストなどを入れるとエラーが出ます。
* そのため、for文のような繰り返し処理で関数を一つずつ適用するか、map()関数を使う必要があります。
* 基本的な使い方：
  * func: 適用したい関数（既存の関数、自作関数、lambda 関数など）
  * iterable: 適用対象のリスト、タプル、ジェネレータなどの反復可能なオブジェクト
  * **使い方：map(func, iterable)**
  * 注意：funcが複数の引数（入力）を必要とする場合は、map(func, iterable1, iterable2)のように書きます。
* 戻り値: map オブジェクト（反復可能なオブジェクトの要素を一つずつ返すオブジェクト、つまりイテレータ）になります。print関数などで表示すると <map object at 0x...> となり、中身がすべて表示されません。
* 中身がすべて表示したい場合は list() や for で展開します。

<1,1>
--

<1,2>

1. map()関数を用いて、整数で定義されたリスト[1,2,3]を、実数のリスト[1.0, 2.0, 3.0]に変換し、ans1に入れます。

```python
#Level 1:
ans1 = ??(float,[1,2,3])
```

```python
ans1 = map(float,[1,2,3])
#print(list(ans1))
#ans1 = [1.0, 2.0, 3.0]
```

--

<1,3>

2. map()関数を用いて、整数で定義されたリスト[3,4,5]が、実数のリスト[3.0, 4.0, 5.0]に変換し、ans2に入れます。

```python
#Level 2:
ans2 = ??(??,[3,4,5])
```

```python
ans2 = map(float,[3,4,5])
#print(list(ans2))
#ans2 = [3.0, 4.0, 5.0]
```

--

<1,4>

3. map()関数を用いて数値のリスト[3,4,5]が、文字列のリスト['3', '4', '5']に変換し、ans3に入れます。

```python
#Level 3:
ans3 = ??(str,[3,4,5])
```

```python
ans3 = map(str,[3,4,5])
#print(list(ans3))
#ans3 = ['3', '4', '5']
```


--

# L5M1S2

## map()関数（発展）

ここでは、map()関数について、さらに学びます。

* 前述の内容に続いて、map()関数について理解します。
* ここではいろいろな既存関数（str, int, ordなど）を使ってみましょう。
* ここで、ord関数は文字に対して、アスキーコード（文字ごと紐付けられた番号）を返すものです。

<1,5>

1. map()関数を用いて、数値が文字列に変換されるように、関数を選んでコード記述を完成させて、ans1に入れます。

```python
#Level 1:
# str(1) => '1'
ans1 = map(??,[1,2,3])
```

```python
ans1 = map(str,[1,2,3])
#print(list(ans1))
#ans1 = ['1', '2', '3']
```

--

<1,6>

2. map()関数を用いて、文字列が数値に変換されるように、関数を選んでコード記述を完成させて、ans2に入れます。

```python
#Level 2:
# int(-1) => '3'
ans2 = map(??,['1','2','3'])
```

```python
ans2 = map(int,['1','2','3'])
#print(list(ans2))
#ans2 = [1, 2, 3]
```

--

<1,7>

3. map()関数を用いて、文字列がアスキーコードに変換される（['a','b','c']⇒[97, 98, 99]）ように、関数を選んでコード記述を完成させて、ans3に入れます。

```python
#Level 3:
# ord('a') => 97
ans3 = map(??,['a','b','c'])
```

```python
ans3 = map(ord,['a','b','c'])
#print(list(ans3))
#ans3 = [97, 98, 99]
```


--

---

# L5M2S1

## lambda 関数の定義

<2,1>
ここでは、無名（アノニマス）関数として、lambda 関数の定義について学びます。

* lambda 関数では、defで定義せずに、簡単に1行だけの関数を作ることができます。
* 一時的に使う関数によく用いられます。数式の定義と近い感覚で扱え、数学的な処理の組み込みにとても有効です。
* 基本的な使い方：**lambda 引数: 式**
  * 式に入れられるのは、算術演算、条件式（三項演算子）、関数呼び出し、メソッドのチェーン（定義済みのlambda関数も式の中に組み込むことができます）、リスト／辞書／集合の作成、内包表記（comprehension）、既存関数との組み合わせ（map, filter, sorted など）になります。
  * return は不要です。式の結果がそのまま返ります。
  * 基本的に1行で定義します。for や while のような繰り返し文はdef関数で使います（map関数と組み合わせて繰り返し処理を組み込む例もあります）。

<2,1>
--

<2,2>

1. 足し算を使って「引数に1を足す」lambda 式を設計し、返り値を ans1 に入れます。

```python
func1 = ?? x: x+1
ans1=func1(2)
#ans1 = 3
```

```python
func1 = lambda x: x+1
```

--

<2,3>

2. 掛け算を使って「引数を2倍する」lambda 式を設計し、返り値を ans2 に入れます。

```python
#Level 2:
func2 = ?? x: x*2
ans2=func2(2)
#ans2 = 4
```

```python
func2 = lambda x: x*2
```

--

<2,4>

3. 引き算を使って「引数から1を引く」lambda 式を設計し、返り値を ans3 に入れます。

```python
#Level 3:
func3 = ?? x: x-1
ans3=func3(2)
#ans3 = 1
```

```python
func3 = lambda x: x-1
```

--
# L5M2S2

## lambda 関数と数式

<2,5>
ここでは、引き続き無名関数、lambda 関数について学びます。

* 前述の内容に加え、数式のような形で、式を定義します。

1. 2+3=5を計算するlambda 式を定義し、その結果をans1 に入れます。

```python
#Level 1:
func1 = ?? x,y: x+y
ans1=func1(2,3)
#ans1 = 5
```

```python
func1 = lambda x,y: x+y
```

--

<2,6>

2. 2×3=6を計算するlambda 式を定義し、その結果をans2 に入れます。

```python
#Level 2:
func2 = ?? x,y: x*y
ans2=func2(2,3)
#ans2 = 6
```

```python
func2 = lambda x,y: x*y
```

--

<2,7>

3. 2-3=-1を計算するlambda 式を定義し、その結果をans3 に入れます。

```python
#Level 3:
func3 = ?? x,y: x-y
ans3=func2(2,3)
#ans3 = -1
```

```python
func3 = lambda x,y: x-y
```

--
---

# L5M3S1

## lambda 関数と条件式

<3,1>

ここでは、lambda 関数に条件式を入れる方法について学びます。

* lambda 関数には、比較演算子を使って、結果が真か偽かを判別する式を入れることが可能です。


1. 比較演算子 ">" を使って、引数が50より大きいかどうかを判別する lambda 式を定義し、結果をans1 に入れます。

```python
#Level 1:
func1 = lambda x: x?50
ans1=func1(60)
#ans1 = False
```

```python
func1 = lambda x: x>50
```

--

<3,2>

2. 比較演算子 "<" を使って、引数が50より小さいかどうかを判別する lambda 式を定義し、結果をans2 に入れます。

```python
#Level 2:
func2 = lambda x: x?50
ans2=func2(40)
#ans2 = True
```

```python
func2 = lambda x: x<50
```

--

<3,3>

3. 比較演算子 "==" を使って、引数が50と同じかどうかを判別する lambda 式を定義し、結果をans3 に入れます。

```python
#Level 3:
func3 = lambda x: x??50
ans3=func3(50)
#ans3 = True
```

```python
func3 = lambda x: x==50
```

--


---

# L5M4S1

## 条件によって返り値が異なるlambda 関数

<4,1>

ここでは、lambda 関数で、条件によって返り値が異なる式を入れる方法について学びます。

* if文を用いて、if else の条件によって、返す結果が変わる式を定義できます。
* 例１：lambda x: (**条件式1**が満たされた場合の返り値) if (**条件式1**) else (**条件式1**が満たされない場合の返り値)
* 例２：lambda x: (**条件式1**が満たすとき) if (**条件式1**) else (**条件式1**が満たさず、**条件式2**を満たすとき) if (**条件式2**) else (**条件式1**も**条件式2**も満たされないとき)
* 注：上述のように、ifとelseを右側に追加することで、複数の条件式を加えることができます。条件式は左から適用され、その条件を通過したら（満たす場合）、次の条件で評価されてifの前か、elseの後の値が返ります。


--

<4,2>

1. 引数が1と等しい時に1、それ以外は0を返すlambda 式があります。結果が1になるように、引数を入れ、結果を ans1 に入れます。

```python
#Level 1:
func1 = lambda x: 1 if x==1 else 0
ans1=func1(??)
#ans1 = 1
```

```python
ans1=func1(1)
```

--

<4,3>

2. 引数が1と等しい時に1、2に等しいときには2、それ以外は3を返すlambda 式があります。結果が2になるように、引数を入れ、結果を ans2 に入れます。

```python
#Level 2:
func2 = lambda x: 1 if x==1 else 2 if x==2 else 3
ans2=func2(??)
#ans2 = 2
```

```python
ans2=func2(2)
```

--

<4,4>

3. 引数が1と等しい時に1、2に等しいときには2、3に等しいときには3、それ以外は0を返すlambda 式があります。結果が3になるように、引数を入れ、結果を ans3 に入れます。

```python
#Level 3:
func3 = lambda x: 1 if x==1 else 2 if x==2 else 3 if x==3 else 0
ans3=func3(??)
#ans3 = 3
```

```python
ans3=func3(3)
```


--
---

# L5M5S1

## map関数と無名関数（lambda）の組み合わせ


<5,1>

ここでは、map関数と無名関数（lambda）の組み合わせを学びます。

* 与えられた iterable（リストやタプルなど） の各要素に、lambda（関数） を順番に適用して、その結果をまとめて返すことができます。
* 結果は map オブジェクト（イテレータ） となります。結果は list() に変換し、すべての要素を表示することができます。
* 基本的な使い方：
  * lambda関数: 適用したい関数（ここでは、lambda 関数）
  * iterable: 適用対象のリスト、タプル、ジェネレータなどの反復可能なオブジェクト
  * **使い方：map(lambda関数, iterable)**

--

<5,2>

1. 定義されたlambda関数を確認し、リスト[50,60,70]に対して、結果が [False, True, True] になるように、map 関数を完成させて、結果を ans1 に入れます。

```python
#Level 1:
x1 = [50,60,70]
f1 = lambda x: x>50
ans1 = list(map(?,?))
#ans1 = [False, True, True]
```

```python
ans1 = list(map(f1,x1))
```

--

<5,3>

2. 定義されたlambda関数を確認し、リスト[50,60,70]に対して、結果が[True, False, False]になるように、map 関数を完成させて、結果を ans2 に入れます。

```python
#Level 2:
x2 = [50,60,70]
f2 = lambda x: x<50
ans2 = list(map(?,?))
#ans2 = [True, False, False]
```

```python
ans2 = list(map(f2,x2))
```

--

<5,4>

3. 定義されたlambda関数を確認し、リスト[50,60,70]に対して、結果が[False, False,True]になるように、map 関数を完成させて、結果を ans3 に入れてます。

```python
#Level 3:
x3 = [50,60,70]
f3 = lambda x: x==70
ans3 = list(map(?,?))
#ans3 = [False, False, True]
```

```python
ans3 = list(map(f3,x3))
```


--
<5,5>

# L5M5S2

## 既存関数と無名関数（lambda）の組み合わせ

ここでは、既存関数と無名関数（lambda）の組み合わせを学びます。

* すでに定義したlambda関数やmap関数などを組み込んだ式を使って、新しいlambda関数を定義できます。
* sum()メソッドは、イテラブル（反復可能オブジェクト） に含まれる数値を合計して返します。
  * 基本的な使い方：**sum(iterable)**
* map で変換した結果は sum で合計することができます。

--

<5,6>

最初に、f = lambda x: False if x>=0 else Trueと定義し、マイナスの値のときに1を返すlambda関数を定義して以後使用します。

1. 新たに定義されたlambda関数を確認し、リスト[-1,0,1]に対し、結果が 0 になるようsum関数を用い、その結果をans1 に入れます。

```python
#Level 1:
f = lambda x: False if x>=0 else True
x1 =[-1,0,1]
# f(-1)=True or 1; f(0)=False or 0; f(1)=False or 0
func1 = lambda x: x if ??(map(f,x))!=1 else 0
# 1+0+0=1 is not equal to 1
ans1=func1(x1)
#ans1 = 0
```

```python
func1 = lambda x: x if sum(map(f,x))!=1 else 0
```

--

<5,7>

最初に、f = lambda x: False if x>=0 else Trueと定義し、マイナスの値のときに1を返すlambda関数を定義して以後使用します。

2. 新たに定義されたlambda関数を確認し、リスト[-1,0,1]に対し、リストの内容が返されるようにsum関数を用い、その結果をans2 に入れます。

```python
#Level 2:
f = lambda x: False if x>=0 else True
x2 =[1,-1,1]
# f(1)=False or 0; f(-1)=True or 1; f(1)=False or 0
func2 = lambda x: x if ??(map(f,x))==1 else 0
# 0+1+0=1 equal to 1, then return x as list
ans2=func2(x2)
#ans2 = [1, -1, 1]
```

```python
func2 = lambda x: x if sum(map(f,x))==1 else 0
```

--

<5,8>

最初に、f = lambda x: False if x>=0 else Trueと定義し、マイナスの値のときに1を返すlambda関数を定義して以後使用します。

3. 新たに定義されたlambda関数を確認し、リスト[1,-2,-1]に対し、リストの内容が返されるようにsum関数を用い、その結果を再度sum関数で合計してans3 に入れます。

```python
#Level 3:
f = lambda x: False if x>=0 else True
x3 =[1,-2,-1]
# f(1)=False or 0; f(-2)=True or 1; f(-1)=True or 1
func3 = lambda x: x if ??(map(f,x))>1 else 0
# 0+1+1=2>1, then return x as list
ans3=??(func3(x3))
# return its summation
#ans3 = -2
```

```python
func3 = lambda x: x if sum(map(f,x))>1 else 0
ans3=sum(func3(x3))
```


--

--

