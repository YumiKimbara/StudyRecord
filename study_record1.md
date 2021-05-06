## Movie Theaterアプリの疑問点メモ

### 問題点1
moviesTitleをforEachで回して、検索アイコンのclass(form)をクリックした時に、映画タイトルと検索バーに入力した名前が一致していたら、fetchMovieというwebAPIからデータをfetchする関数を作成したかった。

```
const checkTitle = () => {
  moviesTitle.forEach((title, i) => {
    const index = movieIDs[i];
    form.addEventListener('submit', () => {
    if(title === sbSearchInput.value) {
    fetchMovie(index);
    localStorage.setItem('movietitle', JSON.stringify(sbSearchInput.value));
    localStorage.setItem('movieInfo', JSON.stringify(movies.results[i]))
    window.open("movieDetail.html")
     }
    });
  })
}
```
しかし、forEachを使用しているため、moviesTitleの数分イベントが登録されてしまう。つまりfetchMovie関数を一度に沢山呼び出すことで、failed to fetchとなりエラーが起こってしまう。
### 解決策1
forEachとaddEventListenerを別枠で記載すると良い。

### 問題点2
formのactionは何も設定しないと自分自身に返ってくる(画面遷移する)ため、
問題点1を解決した後もfailed to fetchのエラーが残ったままだった。
```
<form action="<自分自身>" method="GET">
 <input type="submit">Submit</input>
</form>
```
### 解決策2
自分自身に向かって画面遷移するのをpreventDefaultで防ぐ。
preventDefaultで本来の動きを止め、form要素の画面遷移(=本来の動き)を抑制する。
こちらが優先されてしまって、Failed to fetchになってしまっていた。

```
form.addEventListener('submit', (e) => {
  e.preventDefault();

  if (moviesTitle.includes(sbSearchInput.value)) {
    const index = moviesTitle.indexOf(sbSearchInput.value);
    const movieId = movieIDs[index];

    fetchMovie(movieId);
  }
});
```