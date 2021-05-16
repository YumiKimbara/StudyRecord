# HTML Forms

### フォームタグ
|属性|用途|
|---|---|
|action|データの送信先ページを指定|
|method|データの送信方法の指定。主にgetかpostを入力|
|name|フォームの名前を指定|

```
<form action="example.php" method="post" name="contact-form">
   フォーム内容
</form>
```

### フォーム内で使うパーツ1 -  input form
#### 基本のinput
```
<input type="text" placeholder="名字 名前">
```
|属性値|用途|
|---|---|
|text|一行のテキスト(初期値)|
|search|検索するときのテキスト|
|email|メールアドレス|
|tel|電話番号|
|url|WebサイトのURL|


- 属性値を記載することで、ブラウザー上で正しい書式かどうかチェックしてくれる。
#### ラジオボタンのinput
|属性|用途|
|---|---|
|name|ラジオボタンの名前|
|value|送信される選択肢の値|
|checked|最初から選択されている状態にする時に指定|

```
<input type="radio" name="gender" value="男">男
<input type="radio" name="gender" value="女" checked>女
<input type="radio" name="gender" value="その他">その他
```

#### チェックボックスのinput
|属性|用途|
|---|---|
|name|チェックボックスの名前|
|value|送信される選択肢の値|
|checked|最初から選択されている状態にする時に指定|

```
<input type="checkbox" name="color" value="赤">赤
<input type="checkbox" name="color" value="青">青
<input type="checkbox" name="color" value="黄">黄
```

#### 送信ボタンのinput
|属性|用途|
|---|---|
|name|ボタンの名前|
|value|ボタンに表示するテキスト|
|src|ボタンに使用したい画像のファイルパス、ファイル名|
|alt|画像を説明するテキスト|

```
<input type="submit" value="送信する">
```
### フォーム内で使うパーツ2 -  select option
#### selectタグ
|属性|用途|
|---|---|
|name|セレクトボックスの名前|
|multiple|shiftまたはctrlキーで複数の項目を選択可能にする。|

#### optionタグ
|属性|用途|
|---|---|
|value|送信される選択肢の値｜
|selected|最初から選択されている状態にする時に指定|

```
<selected name="bloodtype">
<option value="A">A</option>
<option value="B">B</option>
<option value="O">O</option>
<option value="AB">AB</option>
<option value="不明">不明</option>
```

### フォーム内で使うパーツ3 - textarea
#### textareaタグ

```
<textarea name="message" placeholder="メッセージを入力"></textarea>
```

### フォーム内で使うパーツ4 - label
#### labelタグ
フォームパーツのidとラベルのforを関連ずけることで、テキストを含んだ選択項目全体がクリックできるようになる。特に小さなラジオボタンやチェックボックスをクリックするのが難しい人もいるため、ラベルで関連付けると良い。

```
<input type="checkbox" name="travel" value="日本国内" id="japan">
<label for="japan">日本国内</label>
```