# ___第5回特別課題___


## URLとは
&emsp;URLとは「___Uniform Resource Locator___」の略となっております。<br>
&emsp;私たちが普段、ブラウザで見ているサイト一つ一つにURLが振られており、「住所」に相当する情報になります。<br>
&emsp;URLの記載方法と構成は下記の通りです。

```
-サンプルURL-
http://yama.info/extension/index.html
```
      
```
-構成要素-
スキーム名（「http://」「https://」「ftp://」等）
　　　＋
　ホスト名、サブドメイン名（省略可能な場合もある）
　　　＋
　ドメイン名
　　　＋
　ポート番号（省略可能な場合もある）
　　　＋
　ファイルまでのパス
　　　＋
　ファイル名
```

## クエリ文字列とは
&emsp;サーバに情報を送るために送信先を指定するURLの末尾に特定の形式で付け足す文字列のことです。<br>
&emsp;クエリ文字列を導入する場合は下記のように「？」等の記号を使って、URLの最後に付け加えます。
```
-サンプルURL-
http://yama.info/extension/index.html/?q=udon
```
&emsp;クエリパラメータで使う基本的な記号と位置については、下表の通りです。
| 記号   |     目的     | 目的 |
| --- | ----------- | ------- |
| ?   |クエリパラメータを付与する |http://〇〇.jp/?▢=△ |
| =   | 名前と値を付与する | http://〇〇.jp/?▢=△  |
| &   | 複数のクエリパラメータを付与する | http://〇〇.jp/?▢=△&■=▲|
| #   | ページ内リンクを挿入する | http://〇〇.jp/?▢=△#◇◇|


## パスパラメーター（パス変数）とは
```
-サンプル-
http://example.com/user/yama
```
における「yama」の部分がパスパラメーター（パス変数）になります。
パスパラメータを指定することで特定の情報やサイトを表示させる事ができます。


## パスパラメーターとクエリ文字列との違い
&*;パスパラメーター：特定の情報まで辿っていくイメージ<br>
&emsp;クエリパラメーター：ユーザーが渡した値を元に関連する情報を引っ張り出すイメージ


## HTTPメソッドとは
&emsp;クライアントからサーバーへHTTPリクエストを発信しますが、「___どのリソース___」に対して「___何をしたいか___」を指示する必要があります。<br>
&emsp;この「何をしたいか」に対して指示する役割を担うのが、HTTPメソッドになります。<br>
&emsp;ちなみに「どのリソース」に対してはURLで決定されます。<br>

&emsp;そして、HTTPメソッドには、次のようなメソッドが用意されています。
| HTTPメソッド   |     働き     | 
| --- | ----------- | 
| GET |サーバーから特定の情報を引っ張り出す |
| POST | サーバーへ情報の新規追加を行う | 
| PUT | サーバー上にある既定情報には上書き更新される、無い場合は情報を新規追加 | 
| PATCH | サーバー上にある既定の情報に新しいものを付け足す | 
| DELETE | サーバー上にある情報で指定して削除する | 

## HTTPステータスコードとは
&emsp;リクエストに対して、サーバーからレスポンスされる際に内容を表現する3桁のコードです。<br>
&emsp;具体的なコードは下記の通りです。
| ステータスコード   |     働き     | 
| --- | ----------- | 
| - 200  |リクエストが正しく処理され、要求された内容が返信される |
| - 201  | リクエストが正しく処理され、新規作成された情報のURLが返信される | 
| - 400  | リクエスト内容が不適切により、サーバーから不当扱いされている状況 | 
| - 404  | リクエストしてもサーバー上に特定の情報がないため状況 | 
| - 500  | サーバー側で発生した問題によって、リクエストが処理されなかった状況 | 

## ホームページが表示する流れ
&emsp;パソコンの画面にホームページに表示するためには下記のような仕組みになっています。<br>
&emsp;&emsp;①クライアントからHTTPリクエストをサーバーへ発信(＝ホームページを表示するように要求)<br>
&emsp;&emsp;②サーバーがリクエストを受信、処理<br>
&emsp;&emsp;③サーバーからHTTPレスポンスを発信(＝画面にホームページ表示)<br>
![画像](https://github.com/yamahiro20639/SpecialAssignment5/assets/144509349/d530e5be-b7bb-4a3d-8c88-19d632273c39)　<br>
参考文献：ITをわかりやすく解説（https://medium-company.com/http%E3%81%A8https%E3%81%AE%E9%81%95%E3%81%84/）


## HTTPリクエストについて
&emsp;クライアントからサーバーへ指示する際にHTTPリクエストは用いられます。<br>
&emsp;先ほど記述しましたが、画面にホームページを表示させる際にも活用されています。
&emsp;また「___リクエストライン___」「___リクエストヘッダー___」「___リクエストボディ___」の３つの要素で構成されています。<br>
&emsp;下記がHTTPリクエストのイメージ図になります。<br>
![d000845-8](https://github.com/yamahiro20639/SpecialAssignment5/assets/144509349/28784a44-1789-4940-aeac-61cd2e9e29ea)<br>
参考文献：わわわ(https://wa3.i-3-i.info/word1841.html)

#### -リクエストライン-
&emsp;HTTPメソッドを含むざっくりなリクエスト部分<br>
```
-サンプル-
POST /search.html HTTP/1.1\r\n
```

#### -リクエストヘッダー-
&emsp;リクエストの追加情報やクライアント自身に関する詳細な情報(メタ情報)が入っています。<br>
```
-サンプル-
Host: wa3.i-3-i.info\r\n
Connection: keep-alive\r\n
Content-Length: 38\r\n
Cache-Control: max-age=0\r\n
Origin: http://wa3.i-3-i.info\r\n
Upgrade-Insecure-Requests: 1\r\n
User-Agent: うんちゃら\r\n
Content-Type: application/x-www-form-urlencoded\r\n
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,image/apng,*/*;q=0.8\r\n
Referer: http://wa3.i-3-i.info/index.html\r\n
Accept-Encoding: gzip, deflate\r\n
Accept-Language: ja,en-US;q=0.8,en;q=0.6\r\n
\r\n
q=test&submitSearch=%E6%A4%9C%E7%B4%A2
```

#### -リクエストボディ-
&emsp;サーバーに対して追加したいPOSTデータやファイルロードデータ等が入っています。<br>
```
-サンプル-
POST /search.html HTTP/1.1\r\n
```

## HTTPレスポンについて
&emsp;クライアントからリクエストを受けた後にサーバーから返答する際にHTTPレスポンが用いられます。<br>
&emsp;また「___ステータス行___」「___レスポンスヘッダー___」「___レスポンスボディ___」の３つの要素で構成されています。<br>
&emsp;下記がHTTPレスポンのイメージ図になります。<br>
![d000842-10](https://github.com/yamahiro20639/SpecialAssignment5/assets/144509349/c561e439-8ac2-41c3-8072-c4020430abb7)<br>
参考文献：わわわ(https://wa3.i-3-i.info/word1842.html)

#### -ステータス行-
&emsp;Hステータスコード含むを含むざっくりなレスポンス部分<br>
```
-サンプル-
HTTP/1.1 200 OK\r\n
```

#### -レスポンスヘッダー-
&emsp;ステータス行では表現しきれないサーバに関する情報や、URIで指定されたリソースに関する追加の情報が入っています。<br>
```
-サンプル-
Server: nginx\r\n
Date: Tue, 11 Jul 2017 09:23:07 GMT\r\n
Content-Type: text/html\r\n
Transfer-Encoding: chunked\r\n
Connection: keep-alive\r\n
```

#### -レスポンスボディ-
&emsp;リクエストで求めていた情報が入っています。例えば、HTMLデータなどもこちらに格納されます。
```
-サンプル-
<!DOCTYPE html>\r\n
<html lang="ja">\r\n
<head>\r\n
\t<meta http-equiv="content-type" content="text/html; charset=UTF-8" />\r\n
\t<meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1">\r\n
\r\n
\r\n
\t<meta name="keywords" content="\350\276\236\345\205\270,IT,\347\224\250\350\252\236,\345\210\235\345\277\203\350\200\205">\r\n
\t<meta name="author" content="Makoto Sasaki">\r\n
\t<meta name="copyright" content="Copyright PCS">\r\n
\r\n
\t<meta name="application-name" content="\343\202\217\343\202\217\343\202\217IT\347\224\250\350\252\236\350\276\236\345\205\270"/>\r\n
\t<link rel="stylesheet" href="css/style.css?ver=00109">\r\n
\t<link rel="stylesheet" href="css/search.css?ver=00109">\r\n
\t<script src="./js/jquery-1.7.2.min.js?ver=00109"></script>\r\n
\t<script src="./js/common.js?ver=00109"></script>\r\n
</head>\r\n
<body>\r\n

（中略）

</body>\r\n
</html>\r\n
\r\n
```

## JSONとは
&emsp;JSONとは「___JavaScript Object Notation___」の略となっております。<br>
&emsp;テキスト形式でデータを保存し色々な用途に活用できるファイルのフォーマット（書式）になります。<br>
&emsp;JSONの書き方は非常にシンプルで、以下の4つのルールに従うだけです。<br>
&emsp;&emsp;▼記載ルール▼<br>
&emsp;&emsp;①項目名と値のペアで記述する<br>
&emsp;&emsp;②項目名は「”（ダブルクオーテーション）」で囲む<br>
&emsp;&emsp;③複数のペアを指定するときは「,（カンマ）」で区切る<br>
&emsp;&emsp;④全体を{}（波カッコ） または[]（カギ角カッコ）で囲む<br>

&emsp;下記は参考コードになります。<br>
&emsp;このデータでは3名のユーザー情報を保持しています。<br>
&emsp;ユーザーの情報としては、以下の情報が格納されています。<br>

&emsp;&emsp;・name（名前）<br>
&emsp;&emsp;・age（年齢）<br>

&emsp;これらのユーザー情報が、配列として「users」の項目に格納されており、実際に格納されているユーザー数が「total」に格納されています。<br>


```
-サンプル-
{
  "total": 3,
  "users": [{
    "name": "田中",
    "age": 22
  }, {
    "name": "佐藤",
    "age": 18,
  }, {
    "name": "鈴木",
    "age": 21,
  }]
}
```
## 参考文献
&emsp;わわわ<br>
&emsp;https://wa3.i-3-i.info/index.html<br>
&emsp;クエリ文字列とは<br>
&emsp;https://online.dhw.co.jp/kuritama/query-string/<br>　
&emsp;クエリパラメータとは？URLの基本的な設定方法やコツを解説<br>
&emsp;https://be-marke.jp/articles/knowhow-queryparameter<br>
&emsp;URLの構造~ホスト名、パス、パラメータ、ハッシュの成り立ちとSEO<br>
&emsp;https://www.marketechlabo.com/url-structure-for-marketer/<br>
&emsp;パスパラメータとクエリパラメータの違い<br>
&emsp;https://zenn.dev/eri_agri/articles/859a3362db8386<br>
&emsp;クエリ文字列とは？- URLに含まれるパラメータの一部<br>
&emsp;https://the-simple.jp/what-is-a-query-string-some-of-the-parameters-included-in-the-url<br>
&emsp;URL / HTTPメソッドとは<br>
&emsp;https://diveintocode.jp/blogs/Technology/depUrlHttpMethod<br>
&emsp;POST, PUT, PATCHの違い<br>
&emsp;https://zenn.dev/sgtkuc1118/articles/c73587c674a4a2<br>
&emsp;PATCHとPUTの違いも解説<br>
&emsp;https://omathin.com/http-method/<br>
&emsp;HTTPステータスコードとは？種類とそれぞれの役割について<br>
&emsp;https://digital-marketing.jp/seo/http-status-code/<br>
&emsp;https://wa3.i-3-i.info/word1844.html<br>
&emsp;HTTPステータスコード一覧とリクエストとレスポンスの意味を解説<br>
&emsp;https://www.itmanage.co.jp/column/http-www-request-response-statuscode/<br>
&emsp;HTTPリクエストボディとは、その使い方の解説はこちら！<br>
&emsp;https://apidog.com/jp/blog/http-request-body/#:<br>
&emsp;JSONとは？概要からJSONファイルフォーマットまで解説！<br>
&emsp;https://and-engineer.com/articles/YfOfnBAAACEASwoR<br>
