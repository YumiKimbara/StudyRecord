# CSS Float
### floatとは
- CSSでブロック要素を左右どちらか横並びにしたい時に使用するプロパティ。
### floatプロパティの指定

- ```float: none;``` 要素は移動しない。  
- ```float: left;``` ブロックの左側に移動する。
- ```float: right;``` ブロックの右側に移動する。
- ```float: inline-start;``` ブロックの始端側に移動する。 ltr 表記では左側、 rtl 表記では右側になる。
- ```float: inline-end;``` ブロックの終端側に移動する。 ltr 表記では右側、 rtl 表記では左側になる。

### 記述サンプル
```
div {
    width: 100px;
    height: 100px;
    float: left;
}
```