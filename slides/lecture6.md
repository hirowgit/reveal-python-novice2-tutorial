# L6M1S1

## リストの結合・編集処理
ここでは、リスト型の取り扱い（振り返り）を学びます。

* リスト型で要素の追加やリストの結合を行う場合、.extend()メソッドで、リストを関数の入力として与えると階層型リスト( [L2M5S1](https://hirowgit.github.io/reveal-python-novice2-tutorial/lecture2.html#/4)として返すことができます。
* リスト型では、+演算子の他に、.appendメソッド（関数の一種）を使って要素の追加やリストの結合 [L2M4S1](https://hirowgit.github.io/reveal-python-novice2-tutorial/lecture2.html#/3)として返すことができます。

<1,1>
--

<1,2>

1. .extendメソッドを用いて[1,2,3]と[4,5,6]を結合し、[1, 2, 3, 4, 5, 6]にして、ans1に入れます。

```python
#Level 1:
x = [1, 2, 3]
y = [4, 5, 6]

ans1 = [ ]
ans1.??(x)
ans1.??(y)
#ans1 = [1, 2, 3, 4, 5, 6]
```

```python
ans1.extend(x)
ans1.extend(y)
```

--

<1,3>

2. .extendメソッドと.appendメソッドを用いて[1,2,3]と[4,5,6]を結合し、[1, 2, 3, [4, 5, 6]]にして、ans2に入れます。

```python
#Level 2:
x = [1, 2, 3]
y = [4, 5, 6]

ans2 = [ ]
ans2.??(x)
ans2.??(y)
#ans2 = [1, 2, 3, [4, 5, 6]]
```

```python
ans2.extend(x)
ans2.append(y)
```

--

<1,4>

3. .appendメソッドを用いて[1,2,3]と[4,5,6]を結合し、[[1, 2, 3], [4, 5, 6]]にして、ans3に入れます。

```python
#Level 3:
x = [1, 2, 3]
y = [4, 5, 6]

ans3 = [ ]
ans3.??(x)
ans3.??(y)
#ans3 = [[1, 2, 3], [4, 5, 6]]
```

```python
ans3.append(x)
ans3.append(y)
```


--

# L6M1S2

##　リスト型のスライシング

ここでは、リスト型のスライシングを学びます。

* スライス(slice)、またはスライシング（slicing）では、リスト、文字列、タプルなどの順序を持つデータ型で、一部の区間を切り取ることができます。
* 基本講文
  シーケンス[start:stop:step]
  start : 開始インデックス（デフォルト = 0）
  stop : 終了インデックス（この位置の要素は含まれない）
step : 間隔（デフォルト = 1; 省略可能）
* for文は、リスト、文字列、数の範囲などに対して、1つずつ取り出して繰り返して、range()の括弧内に指定した数だけ繰り返して、加算の結果を出力 [L3M4S1](https://hirowgit.github.io/reveal-python-novice2-tutorial/lecture3.html#/3)できます。
* 反復計算と配列を組み合わせたリスト内包表記（ List Comprehension ）の具体的な活用例 [L3M7S2](https://hirowgit.github.io/reveal-python-novice2-tutorial/lecture3.html#/6/3)として返すことができます。


<1,5>

1. スライス(slice)メソッドを用いて[1,2,3,4,5,6,7,8,9]をリストの要素を3つずつ区切って、2次元リストの[[1, 2, 3], [4, 5, 6], [7, 8, 9]]にして、ans1に値(自然数)入れます。

```python
#Level 1:
A = [1,2,3,4,5,6,7,8,9]
ans1 = [A[0:3], A[?:?], A[6:9]]
#ans1 = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
```

```python
ans1 = [A[0:3], A[3:6], A[6:9]]
```

--

<1,6>

2. ans2が[[1, 2, 3], [4, 5, 6], [7, 8, 9]]になるように、ans2にどの値(自然数)を入力すればよいかを考え、適切な値をans2に入れます。

```python
#Level 2:
A = [1,2,3,4,5,6,7,8,9]
ans2 = []
for i in range(0, len(A), ?):
    ans2.append(A[i:i+3])
#ans2 = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
```

```python
for i in range(0, len(A), 3):
    ans2.append(A[i:i+3])
```

--

<1,7>

3. ans3が[[1, 2, 3], [4, 5, 6], [7, 8, 9]]になるように、リスト内包表記をどのように設計すればよいかを考え、適切な値(自然数)をans3に入れます。

```python
#Level 3:
A = [1,2,3,4,5,6,7,8,9]
ans3 = [A[i:i+3] for i in range(0, len(A), ?)]
#ans3 = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
```

```python
ans3 = [A[i:i+3] for i in range(0, len(A), 3)]
```


--

---

# L6M2S1

## リスト型の和の計算

ここでは、リスト内の値を合計する関数を学びます。

* sum() は、数値で構成された複数の値をすべて合計した結果を求める組み込み関数の具体的な活用例を学びます（sum()の基本は [L5M5S2](https://hirowgit.github.io/reveal-python-novice2-tutorial/lecture5.html#/4/4)を見てください）。

<2,1>
--

<2,2>

1. sum()関数を用いて、一次元のリスト [1,2,3,4,5,6,7,8,9]の要素の合計した結果が、45になるように、ans1に入れます。

```python
#Level 1:
A = [1,2,3,4,5,6,7,8,9]

ans1 = ??(A)
#ans1 = 45
```

```python
ans1 = sum(A)
```

--

<2,3>

2. sum()関数を用いて、二次元のリスト [[1, 2, 3], [4, 5, 6], [7, 8, 9]]の0番目の要素の合計が、6になるように、ans2に入れます。

```python
#Level 2:
A = [
[1, 2, 3],
[4, 5, 6],
[7, 8, 9]
]

ans2 = ??(A[0])
#ans2 = 6
```

```python
ans2 = sum(A[0])
```

--

<2,4>

3. sum()関数を用いて、二次元のリスト [[1, 2, 3], [4, 5, 6], [7, 8, 9]]の2番目の要素の合計が、6になるように、ans3に入れます。

```python
#Level 3:
A = [
[1, 2, 3],
[4, 5, 6],
[7, 8, 9]
]

ans3 = ??(A[2])
#ans3 = 24
```

```python
ans3 = sum(A[2])
```

--
# L6M2S2

## 二次元リストの計算

<2,5>
* 2次元リスト（リストの中にリスト）を用いることで、行列計算を行い、行列（matrix）のようにデータを扱うことができます。
* sum() は、数値で構成された複数の値をすべて合計した結果を求める組み込みメソッドの具体的な活用例を学びます（sum()の基本は [L5M5S2](https://hirowgit.github.io/reveal-python-novice2-tutorial/lecture5.html#/4/4)を見てください）。

1. 'A'という二次元のリスト中で、何番目の行の合計すると結果が、12になる値（自然数）をans1に入れます。

```python
#Level 1:
A = [
[1, 2, 3],
[4, 5, 6],
[7, 8, 9]
]

ans1 = sum(row[?] for row in A)
#ans1 = 12
```

```python
ans1 = sum(row[0] for row in A)
```

--

<2,6>

2. 'A'という二次元のリスト中で、何番目の行の合計すると結果が、15になる値（自然数）をans2に入れます。

```python
#Level 2:
A = [
[1, 2, 3],
[4, 5, 6],
[7, 8, 9]
]

ans2 = sum(row[?] for row in A)
#ans2 = 15
```

```python
ans2 = sum(row[1] for row in A)
```

--

<2,7>

3. 'A'という二次元のリスト中で、何番目の行の合計すると結果が、18になる値（自然数）をans3に入れます。

```python
#Level 3:
A = [
[1, 2, 3],
[4, 5, 6],
[7, 8, 9]
]

ans3 = sum(row[?] for row in A)
#ans3 = 18
```

```python
ans3 = sum(row[2] for row in A)
```

--
---

# L6M3S1

## オブジェクトのデータ型の確認方法

<3,1>

ここでは、オブジェクトのデータ型の確認方法を学びます。

* type()メソッドは、与えられた値（オブジェクト）がどのデータ型であるかを示します。
* 返されるのは、データ型そのもの（int、str、list など）です。


1. type()メソッドを用いて、データ型が 'int' と表示されるように、ans1に入れます。

```python
#Level 1:
a = 10
ans1 = (??(a))   
#ans1 = <class 'int'>
```

```python
ans1 = (type(a))   
```

--

<3,2>

2. type()メソッドを用いて、データ型が 'float' と表示されるように、ans2に入れます。

```python
#Level 2:
b = 3.14
ans2 = (??(b))   
#ans2 = <class 'float'>
```

```python
ans2 = (type(b))   
```

--

<3,3>

3. type()メソッドを用いて、データ型が 'str' と表示されるように、ans3に入れます。

```python
c = "hello"
ans3 = (??(c))   
#ans3 = <class 'str'>
```

```python
ans3 = (type(c))   
```

--


---

# L6M4S1

## 混在リストの取り扱い（数字型）

<4,1>

ここでは、混在リストの取り扱い（数字型）を学びます。

* 異なるデータ型（データタイプ）を同時に含んでいるリストを扱います。
* リストは、柔軟なデータ構造として、同じリストの中に多種のデータ型を同時に格納できます。
* 数学的な行列（matrix）やデータ分析用の配列として利用する場合は、データ型が統一されている方が計算上効率的です（Numpyモジュールなど）。
* 反復計算と配列を組み合わせたリスト内包表記（ List Comprehension ）の具体的な活用例を学びます（リスト内包表記の基本は、[L4M1S1](https://hirowgit.github.io/reveal-python-novice2-tutorial/lecture4.html)を見てください）。

--

<4,2>

1. 混在リストの中で、数字型データだけ取り出すために、データ型がint型か, float型のときだけ、データを取り出すように、結果として[1,2,3]になるようにリスト内包表記を完成させ、その結果をans1に入れます。

```python
#Level 1:
List = [1, 'a', 2, 'b', 3, 'c']

ans1 = [x for x in List if type(x) in (??, float)]
#ans1 = [1, 2, 3]
```

```python
ans1 = [x for x in List if type(x) in (int, float)]
```

--

<4,3>

2. 混在リストの中で、数字型データだけ取り出すために、データ型がint型か, float型のときだけ、データを取り出すように、結果として[4,5,6]になるように、ans2に入れます。

```python
#Level 2:
List = [4, 'a', 5, 'b', 6, 'c']

ans2 = [x for x in List if type(x) in (??, float)]
#ans2 = [4, 5, 6]
```

```python
ans2 = [x for x in List if type(x) in (int, float)]
```

--

<4,4>

3. 混在リストの中で、数字型データだけ取り出すために、データ型がint型か, float型のときだけ、データを取り出すように、結果として[10.0,20.0,30.0]になるように、ans3に入れます。

```python
#Level 3:
List = [10.0, 'a', 20.0, 'B', 30.0, 'c']

ans3 = [x for x in List if type(x) in (int, ??)]
#ans3 = [10.0, 20.0, 30.0]
```

```python
ans3 = [x for x in List if type(x) in (int, float)]
```


--
# L6M4S2

## 混在リストの取り扱い（文字型）

<4,5>

ここでは、混在リストの取り扱い（文字型）を学びます。

* 異なるデータ型（データタイプ）を同時に含んでいるリストを扱います。
* リストは、柔軟なデータ構造として、同じリストの中に多種のデータ型を同時に格納できます。
* 数学的な行列（matrix）やデータ分析用の配列として利用する場合は、データ型が統一されている方が計算上効率的です（Numpyモジュールなど）。
* 反復計算と配列を組み合わせたリスト内包表記（ List Comprehension ）の具体的な活用例を学びます（リスト内包表記の基本は、[L4M1S1](https://hirowgit.github.io/reveal-python-novice2-tutorial/lecture4.html)を見てください）。

--

<4,6>

1. 混在リストの中で、文字型データだけ取り出すために、データ型がstr型のときだけ、データを取り出すように、結果として['a', 'b', 'c']になるようにリスト内包表記を完成させ、その結果をans1に入れます。

```python
#Level 1:
List = [1, 'a', 2, 'b', 3, 'c']

ans1 = [x for x in List if type(x) == ??]
#ans1 = ['a', 'b', 'c']
```

```python
ans1 = [x for x in List if type(x) == str]
```

--

<4,7>

2. 混在リストの中で、文字型データだけ取り出すために、データ型がstr型のときだけ、データを取り出すように、結果として ['apple', 'banana', 'cherry']になるようにリスト内包表記を完成させ、その結果をans2に入れます。

```python
#Level 2:
List = [1, "apple", 2, "banana", 3, "cherry"]

ans2 = [x for x in List if type(x) == ??]
#ans2 = ['apple', 'banana', 'cherry']
```

```python
ans2 = [x for x in List if type(x) == str]
```

--

<4,8>

3. 混在リストの中で、文字型データだけ取り出すために、データ型がstr型のときだけ、データを取り出すように、結果として ['a', 'b', 'c', 'apple', 'banana', 'cherry']になるようにリスト内包表記を完成させ、その結果をans3に入れます。

```python
#Level 3:
List = [1, 2, 3, 'a', 'b', 'c', "apple", "banana", "cherry"]

ans3 = [x for x in List if type(x) == ??]
#ans3 = ['a', 'b', 'c', 'apple', 'banana', 'cherry']
```

```python
ans3 = [x for x in List if type(x) == str]
```


--




---

# L6M5S1

## lambda 関数を使った混在リストの取り扱い（数字型）


<5,1>

ここでは、lambda 関数を使った混在リストの取り扱い（数字型）を学びます。

* defで定義せずに、簡単に1行だけの関数を作ることができlambda 関数の具体的な活用例を学びます（lambda 関数の基本は、[L5M2S1](https://hirowgit.github.io/reveal-python-novice2-tutorial/lecture5.html#/1)を見てください）。

--

<5,2>

1. 数字型だけを取り出す処理できる lambda式を設計し、[1, None, 2, None, 3, None] が出るように、ans1 に入れます。

```python
#Level 1:
data = [1, 'a', 2, 'b', 3, 'c']

ans1 = list(map(?? x: x if type(x) in (int, float) else None, data))
#ans1 = [1, None, 2, None, 3, None]
```

```python
ans1 = list(map(lambda x: x if type(x) in (int, float) else None, data))
```

--

<5,3>

2. 数字型だけを取り出す処理できる lambda式を設計し、[4, None, 5, None, 6, None] が出るように、ans2 に入れます。

```python
#Level 2:
data = [4, 'a', 5, 'b', 6, 'c']

ans2 = list(map(?? x: x if type(x) in (int, float) else None, data))
#ans2 = [4, None, 5, None, 6, None]
```

```python
ans2 = list(map(lambda x: x if type(x) in (int, float) else None, data))
```

--

<5,4>

3. 数字型だけを取り出す処理できる lambda式を設計し、[10.0, None, 20.0, None, 30.0, None] が出るように、ans3 に入れてます。

```python
#Level 3:
data = [10.0, 'a', 20.0, 'b', 30.0, 'c']

ans3 = list(map(?? x: x if type(x) in (int, float) else None, data))
#ans3 = [10.0, None, 20.0, None, 30.0, None]
```

```python
ans3 = list(map(lambda x: x if type(x) in (int, float) else None, data))
```


--
<5,5>

# L6M5S2

## lambda 関数を使った混在リストの取り扱い（文字型）

ここでは、lambda 関数を使った混在リストの取り扱い（文字型）を学びます。

* リストのような複数の値を持つ変数（iterable、イテラブル）に対して、同じ関数をそのすべての値に適用できるmap()関数の具体的な活用例を学びます（map()関数の基本は、[L5M1S1](https://hirowgit.github.io/reveal-python-novice2-tutorial/lecture5.html)を見てください）。

--

<5,6>

1. map() 関数を用いて、文字型だけを取り出す処理の無名関数（lambda）式の中で、混在リスト全体に適用し、結果が [None, 'a', None, 'b', None, 'c'] となるように ans1 に入れます。

```python
#Level 1:
data = [1, 'a', 2, 'b', 3, 'c']

ans1 = list(??(lambda x: x if type(x) == str else None, data))
#ans1 = [None, 'a', None, 'b', None, 'c']
```

```python
ans1 = list(map(lambda x: x if type(x) == str else None, data))
```

--

<5,7>


2. map() 関数を用いて、文字型だけを取り出す処理の無名関数（lambda）式の中で、混在リスト全体に適用し、結果が [None, 'apple', None, 'banana', None, 'cherry'] となるように ans2 に入れます。

```python
#Level 2:
data = [1, "apple", 2, "banana", 3, "cherry"]

ans2 = list(??(lambda x: x if type(x) == str else None, data))
#ans2 = [None, 'apple', None, 'banana', None, 'cherry']
```

```python
ans2 = list(map(lambda x: x if type(x) == str else None, data))
```

--

<5,8>


3. map() 関数を用いて、文字型だけを取り出す処理の無名関数（lambda）式の中で、混在リスト全体に適用し、結果が [None, None, None, 'a', 'b', 'c', 'apple', 'banana', 'cherry'] となるように ans3 に入れます。

```python
#Level 3:
data = [1, 2, 3, 'a', 'b', 'c', "apple", "banana", "cherry"]

ans3 = list(??(lambda x: x if type(x) == str else None, data))
#ans3 = [None, None, None, 'a', 'b', 'c', 'apple', 'banana', 'cherry']
```

```python
ans3 = list(map(lambda x: x if type(x) == str else None, data))
```


--

---

# L6M6S1

## zip () 関数の使い方


<6,1>

ここでは、zip () 関数の使い方を学びます。

* zip ()メソッドは、複数のリスト（やタプルなど）を まとめてペアにして、for文などのループで使うことができます。
* 同じ位置（インデックス）の要素どうしを タプル にしてくれます。
* 結果は zipオブジェクト になり、通常は list() を使って中身を確認できます。

--

<6,2>

1. zip ()メソッドを用いて、["mikawa", "seiko", "yamada"]と[85, 92, 78]をペアにして、[('mikawa', 85), ('seiko', 92), ('yamada', 78)]になるように、ans1に入れます。

```python
#Level 1:
names = ["mikawa", "seiko", "yamada"]
scores = [85, 92, 78]

ans1 = ??(names, scores)
#print(list(ans1))
#ans1 = [('mikawa', 85), ('seiko', 92), ('yamada', 78)]
```

```python
ans1 = zip(names, scores)
```

--

<6,3>

2. zip ()メソッドを用いて、["mikawa", "kuruda", "yamada"]と[85, 88, 78]をペアにして、[('mikawa', 85), ('kuruda', 88), ('yamada', 78)]になるように、ans2に入れます。

```python
#Level 2:
names = ["mikawa", "kuruda", "yamada"]
scores = [85, 88, 78]

ans2 = ??(names, scores)
#print(list(ans2))
#ans2 = [('mikawa', 85), ('kuruda', 88), ('yamada', 78)]
```

```python
ans2 = zip(names, scores)
```

--

<6,4>

3. zip ()メソッドを用いて、["mikawa", "seiko", "yamada", "kuruda"]と[85, 92, 78, 88]をペアにして、[('mikawa', 85), ('seiko', 92), ('yamada', 78), ('kuruda', 88)]になるように、ans3に入れてます。

```python
#Level 3:
names = ["mikawa", "seiko", "yamada", "kuruda"]
scores = [85, 92, 78, 88]

ans3 = ??(names, scores)
#print(list(ans3))
#ans3 = [('mikawa', 85), ('seiko', 92), ('yamada', 78), ('kuruda', 88)]
```

```python
ans3 = zip(names, scores)
```


--
<6,5>

# L6M6S2

## zip () 関数とループ処理の融合

ここでは、zip () 関数とループ処理の融合を学びます。

* zip() 関数をリスト内包表記の中に入れることで、新しいリストを簡単に作成することができます。
* 文字列は、「+」演算子を使うことで、リストの要素同様に、結合して新たな文字列を作ることができます。
* 例：x + '=' + str(y) は、x='abc'、y=5のとき、'abc=5'と出力されます。

--

<6,6>

1. str ()メソッドを用いて、["mikawa", "seiko", "yamada", "kuruda"]と[85, 92, 78, 88]をペアにして、['mikawa85', 'seiko92', 'yamada78', 'kuruda88']になるように、ans1に入れます。

```python
#Level 1:
names = ["mikawa", "seiko", "yamada", "kuruda"]
scores = [85, 92, 78, 88]

ans1 = [x + ?(y) for x, y in zip(names, scores)]
#ans1 = ['mikawa85', 'seiko92', 'yamada78', 'kuruda88']
```

```python
ans1 = [x + str(y) for x, y in zip(names, scores)]
```

--

<6,7>


2. '=' 記号を用いて、["mikawa", "seiko", "yamada", "kuruda"]と[85, 92, 78, 88]をペアにして、['mikawa=85', 'seiko=92', 'yamada=78', 'kuruda=88']になるように、ans2に入れます。

```python
#Level 2:
names = ["mikawa", "seiko", "yamada", "kuruda"]
scores = [85, 92, 78, 88]

ans2 = [x + '?' + str(y) for x, y in zip(names, scores)]
#ans1 = ['mikawa=85', 'seiko=92', 'yamada=78', 'kuruda=88']
```

```python
ans2 = [x + '=' + str(y) for x, y in zip(names, scores)]
```

--

<6,8>


3. zip ()メソッドを用いて、関数のイテレータnamesとscoresをペアにして、['name: mikawa, score: 85', 'name: seiko, score: 92', 'name: yamada, score: 78', 'name: kuruda, score: 88']になるように、ans3に入れます。

```python
#Level 3:
names = ["mikawa", "seiko", "yamada", "kuruda"]
scores = [85, 92, 78, 88]

ans3 = ["name: " + x + ", score: " + str(y) for x, y in zip(??, ??)]
#ans3 = ['name: mikawa, score: 85', 'name: seiko, score: 92', 'name: yamada, score: 78', 'name: kuruda, score: 88']
```

```python
ans3 = ["name: " + x + ", score: " + str(y) for x, y in zip(names, scores)]
```


--

---

