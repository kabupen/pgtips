## Welcome to GitHub Pages

# Git 

- [git workflow](git.html)

# クラス変数

- public
    - インスタンスからアクセスできる。
- private
    - インスタンスからアクセスできない。クラス内メソッドからのみアクセスできる。
- protected


```cpp
class TestClass{
    public:
        int val_public;
    private:
        int val_private;
};

int main() {

    TestClass tc;
    tc.val_public = 1;  // 代入できる
    tc.val_private = 1; // 代入できない　'val_private' is a private member of 'TestClass'　

    return 0;
}
```


# 静的メンバ変数

クラス固有の定数を実現し、オブジェクト間で共有するために静的メンバを使用することができる。

```cpp
class TestClass{
    public:
        static int val_public = 1; // コンパイルエラー
};
```

`non-const static`メンバは、クラス外で初期化される必要がある。

```cpp
class TestClass{
    public:
        static int val_public;
};

int TestClass::val_public = 1;

int main() {
    std::cout << TestClass::val_public << std::endl;
    ...
}
```

この場合、`TestClass`のインスタンスを作成せずに静的メンバにアクセスすることができる。
また、`const static`にすれば以下のようにも動作させることができる。

```cpp
class TestClass{
    public:
        const static int val_public = 1; // 宣言時に初期化
};

int main() {
    std::cout << TestClass::val_public << std::endl;
}
```

`private`変数にすれば外から見えず、かつクラス固有の（異なる`TestClass`オブジェクトで共通の）値を実現することもできる。
（古いコンパイラであれば宣言時に初期化することができないこともある。）


# ポインタ

定義された変数はメモリ上に保存されている。
C++ではそのメモリ上の位置、アドレスを明示的に使用することで効率の良いプログラミングが可能となる。

- アドレス演算子 : `&a` オブジェクトaへのポインタ（先頭アドレス）を返す
- 間接演算子：`*a` ポインタaが指しているオブジェクトを返す

# メモリ領域

- ヒープ：動的メモリ割り当てを行うための領域。ユーザーが欲しいサイズだけほしいタイミングでメモリの確保を行うための領域。`new`演算子で確保されるのがこの領域。
- スタック：



# 引数の渡し方

- 値渡し
- 参照渡し
- ポインタ渡し

関数の仮引数は、実引数のコピーとして初期化される。
これらのコピーはオブジェクトのコピーコンストラクタによって生成される。

# 継承

- オーバーライド
    - 基底クラスと同名の関数を派生クラスで再定義すること
    - 基底クラスの関数にvirtual
