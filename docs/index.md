## Welcome to GitHub Pages

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


## 静的メンバ変数

クラス固有の定数を実現するには、static const intを使用する



## 引数の渡し方

- 値渡し
- 参照渡し
- ポインタ渡し

関数の仮引数は、実引数のコピーとして初期化される。
これらのコピーはオブジェクトのコピーコンストラクタによって生成される。

# 継承

- オーバーライド
    - 基底クラスと同名の関数を派生クラスで再定義すること
    - 基底クラスの関数にvirtual
