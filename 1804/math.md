# 書くこと
- 4/26に発表する内容(群環体について)
-


## index
- 暗号とはなにか、なぜ数学を学ばなくてはいけないのか
- 共通鍵暗号と公開鍵暗号
- RSA暗号(素数、整数の性質がすごい！)
- 楕円暗号、上記より更にすごいあるごリズムが使われていてすごい！
- GCDやったよねって話
- 群環体について


## 方針
- 数学ガールから例をひっぱってくる(群環体)
- 抽象的 -> 具体的な例 -> コレでなにが嬉しいのかの流れでいけるとよい


## 1.暗号とはなにか、なぜ数学を学ばなくてはいけないのかう
数学理論は古代昔から一部マニアによって開発されていった


## 共通鍵暗号と公開鍵暗号
僕達がイメージしている暗号文
```
暗号文(ciphertext)
dibqmbc

平文(plaintext)
chaolab
```
↓

- シーザー暗号(本当は3文字のやつをいうらしい)　-> 共通鍵暗号
- 平文to暗号文の変換の仕方をアルゴリズムという。
- シーザ暗号は可能性が考うるすべての可能性を試すことができる。-> ブルート・フォース・アタック

---ここまでが僕が高校生くらいまでに思っていた暗号

現代
- コンピューターの発達により、幼稚なアルゴリズムは簡単に解かれるようになった
- 暗号を解く鍵を渡さなくてはいけないが、途中で盗まれるかもしれなく怖くて渡せない
- 現代では暗号のアルゴリズムはすべて公開されている
- え、じゃあ説かれるんじゃないの？？
- ここで素数(数学)の考えがでてくる

- 公開鍵 - 暗号化の鍵を持っているひとは誰でも暗号化できる。しかし、復号は復号化の鍵をもっている人だけ
- 送信者が必要なのは 暗号化 の鍵だけ
- 受信者が必要なのは 復号化　の鍵だけ
- 盗聴者にしられてこまるのは復号化の鍵
- 暗号化の鍵は盗聴者にしられてこまらない

- 使用の流れ
- ボブはキーペアをつくる
- public key をアリスに送る
- アリスはpublic key で暗号化し、おくる
- ボブはそれを復号化する



## modについて

7 * x = 1 (mod 12)
x = 7

これを言い換えると
1 / 7 は何ですか？という質問になる。整数では割れないのに不思議な世界。

mod の世界で逆数が存在するということは、公開鍵でのペアとなるものが存在するということにい行き着く!(すごい！)

![互いに素と逆数](./imgs/gcd-pare.png "互いに素と逆数")

離散来数
![互いに素と逆数](./imgs/risan-taisu.png "互いに素と逆数")


## RSA暗号(素数、整数の性質がすごい！)
RSAの名前は
RonRivest, AdiShamir, LeonardAdleman 3人の開発者の名前


```
# 暗号化
暗号文 = 平文^E mod N

EとNの組が公開鍵

# 復号化
平文 = 暗号文^D mod N
DとNの組が秘密鍵
```

RSAのアルゴリズム
![互いに素と逆数](./imgs/create-rsa.png "互いに素と逆数")

めっちゃかんけつにいうと、RSAは素数&&modの性質を使っていることにより、解読には現代のコンピューターを使っても物理的に時間がたらないので不可能！ -> 素数すげ〜


## 楕円暗号、上記より更にすごいあるごリズムが使われていてすごい！
- rsaより、鍵の長さが短い
## GCDやったよねって話
## 群環体について

### 群

#### 定義

```
- 演算 ○　について閉じている
- 任意の元について結合法則が成り立つ
- 単位元が存在する
- 任意の元に対して、その元に対する逆元が存在する
```

example

```
o整数集合Z 演算+
x奇数集合Z(x ∈　2n+1)  演算+ 演算で閉じていない
o偶数集合演算+
x整数集合演算* 逆元がない

最も要素が少ない群をなす集合は単位元のみの集合

{e}, eoe=e  

```

#### 同型な群

| o | e | a |
|:--:|:--:|:--:|
| e | e | a |
| a | a | e |

| o | 偶数 | 奇数 |
|:--:|:--:|:--:|
| 偶数 | 偶数 | 奇数 |
| 奇数 | 偶数 | 奇数 |

{ 1, -1 } など

#### アーベル群
交換法則を満たす群をアーベル群という


x^2 = 1
x^3 = 1
の解はアーベル群であり、解は円状になる
![互いに素と逆数](./imgs/arbel-circle.png "互いに素と逆数")


### 環

```
- 演算 ○　について閉じている
- 任意の元について結合、交換、分配法則が成り立つ
- 単位元が存在する

加法のみ
- 任意の元に対して、その元に対する逆元が存在する

環情報は逆元が存在しなくてもいいので、郡になっているとは限らない。
```
↓
整数の集合が一番美しい集合である。
Z/mZも剰余環でなす。


### 体
```
- 演算 ○　について閉じている
- 任意の元について結合、交換、分配法則が成り立つ
- 単位元が存在する

加法のみ
- 任意の元に対して、その元に対する逆元が存在する

乗法のみ
- 0以外のすべての要素に対して逆元が存在する。
```
↓
整数/整数
の集合であるということ。

代表は有理数体(Q)

剰余環は Z/mZ としたとき、mが素数の場合体をなす・

## 補足
## 1.
- アルファベット一文字ずつランダムにアルファベットを割り当てるアルゴリズムは単一換字
- これは鍵空間を大きくするばするほど、ブルートフォースアタックは困難になる
