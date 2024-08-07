## データ取得

SELECT * FROM users　これは全ユーザーのデータ取得アスタリスクを使う<br>

SELECT　name カラム名<br>
FROM　　テーブル名　　　　　　　これで指定したテーブルとカラムの情報を取れる

SELECT　name ASで名前変えられる。
SELECT DISTINCT（）で重複データを避けていける。（）に名前を入れる。<br>

SELECT　name カラム名<br>
FROM　　テーブル名　　　　　　　これで指定したテーブルとカラムの情報を取れる<br>
WHERE ここで条件指定で情報を取れる。<br>

orはどちらかを満たす。andはどちらも該当する。<br>

BETWENはこの間までと指定できる。<br>

IN()で条件を指定できる。<br>

NOTINはまとめて否定できて（）以外のデータが取得できる。

LIKE ”ア％”；これで曖昧検索　アメリカやアフリカは引っかかるが先頭がアからが条件なのでオアフは引っかからない。（前方一致）<br>
後方一致LIKE ”％ア”；これは語尾がアを探すので何も引っかからない。


ワイルドカード”％ア％”；これならばオアフも引っかかる。

NULL空のレコードを取得する。

LIMITレコードを制限しつつ取る指示LIMIT　2;なら2マスレコードから情報取ってくる。

ORDER BY 並び替え　昇順

DESC  並び替え　　降順

SQLの書き方　予約語は大文字で書く

予約語の後は場合によって改行する。（わかりやすさでエラーを減らす。）

SELECTやLIMITで何を引き出すか指定すると速い動きになる。（データ量が減る為）

## GROUP BY  テーブル結合（INNER/OUTERJOIN)

SERCT COUNT（カラム名）これでレコード数か数えられ
FROM  テーブル名
WHERE レコード名＝'20日';これで２０日のレコードを取り出せる。

GROUP BY　　同じ値でまとめられる。もし20日ならば

GROUP BYでのエラーは詳細な指示をしてない事で起きるパターンがある。
エラーが起きる場合軸になるものは全てGROUP BYで指定する。
感覚的にはSELECTに記入したものと合わせてる感じ

集計関数を使うと集計ができる。Excelみたいなもの
例　SELECT カラム名,AVG()MAX()
みたいな感じで使う（）内は数字が入ってるカラム名

テーブル結合（INNER/OUTERJOIN)
使い分けJOINは２つのテーブルを軸に出来る。
SELECT*
FROMカラム名AS m
INNERJOIN結合したいテーブル。AS　h ON 結合条件

SELECTでa.カラム名b.カラム名こう分けてあげると整理しやすいなぜならテーブルで名前が被る時があるから

LEFTOUTERJOINは必要な情報以外も持ってくる。のであまり使わない

## CASE式

SELECT CASE WHEN 条件　値<br>
WHEN 条件　THEN 値<br>
FROM テーブル名<br>

| country_name | the price of the item |
| ------------ | --------------------- |
| アメリカ     | 1000                  | 
| カナダ       | 1100                  |
| ドイツ       | 700                   |
| イタリア     | 800                   |

SELECT CASE WHEN country_name　IN（'アメリカ’,'カナダ')THEN 'アメリカ大陸’<br>
WHEN country_name　IN（'ドイツ’,'イタリア')THEN 'ユーラシア大陸’<br>
ELSE NULL<br>
END AS continent<br>
the price of the item<br>
FROM <br>
the price of the items;この指示を与えると<br>

| continent | the price of the item |
| ------------ | --------------------- |
| アメリカ大陸     | 1000                  | 
| アメリカ大陸| 1100                  |
| ユーラシア大陸      | 700                   |
| ユーラシア大陸    | 800                   |

こうなる。

SELECT <br>
CASE WHEN country_name　IN（'アメリカ’,'カナダ')THEN 'アメリカ大陸’<br>
WHEN country_name　IN（'ドイツ’,'イタリア')THEN 'ユーラシア大陸’<br>
ELSE NULL<br>
END AS continent<br>
sum(the price of the item)<br>
FROM <br>
the price of the items;<br>
GROUP BY <br>
CASE WHEN country_name　IN（'アメリカ’,'カナダ')THEN 'アメリカ大陸’<br>
WHEN country_name　IN（'ドイツ’,'イタリア')THEN 'ユーラシア大陸’<br>
ELSE NULL<br>
END;

| continent | the price of the item |
| ------------ | --------------------- |
| アメリカ大陸     | 2100                  | 
| ユーラシア大陸      | 1500                  |

この様な形で大陸事に計算が出来る。<br>
まとめて計算が出来る

## サブクエリ

サブクエリ（副問い合わせ）はSQLクエリの中で使用して、別のクエリの中で計算やフィルタリングを行うことができる。


サブクエリ未使用　　アイテムの値段の平均を割り出す時<br>
SELECT AVG(the price of the item）<br>
FROM the price of the item；<br>
//1900<br>

SELECT　*<br>
FROM the price of the item<br>
WHERE the price of the item >= 1900;<br>

サブクエリ使用

SELECT　*<br>
FROM the price of the item<br>
WHERE the price of the item >= （SELECT AVG(the price of the item）<br>
　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　FROM the price of the item）；



































