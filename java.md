今まで使っていたrubyは簡易的で作りやすくjavaは難しいけど高度な物を作成できる。

今のところjavaはrubyより細かく指示ができてclassの概念は一緒そうな気がした。

class Main {
   Javaのプログラムはクラス定義から始まります。ここではMainというクラスを定義しています。

  public static void main(String[] args) {
     これはJavaプログラムのエントリーポイントです。プログラムの実行が開始されるメソッドです。
     mainメソッドは必ずこの形で記述します。publicはアクセス修飾子で、staticはこのメソッドが
     クラスメソッドであることを示し、voidは戻り値がないことを示します。String[] argsは
    コマンドライン引数を受け取るためのパラメータです。

    int radius;
     整数型の変数radiusを宣言します。radiusは円の半径を表します。

    radius = 5;
     変数radiusに値5を代入しています。

    System.out.println(radius * radius * 3.14);
     半径5の円の面積を計算して出力しています。
     面積の計算は πr^2 で行います。ここではπ（パイ）の値を3.14としています。
     radiusが5なので、面積は 5 * 5 * 3.14 となります。
     計算結果を標準出力（コンソール）に出力します。
  }
}

確かにここまででruby以上に宣言するのが多いんだなと感じる。

型にはめない事を宣言する型varはその一種





格納する要素の数を最初に決める必要があり、かつ後で要素数を変更することができません。

 int[] scores;
    scores = new int[3];

    scores[0] = 1;
    scores[1] = 5;
    scores[2] = 10;

つまりこれは3行までの指定になる。





import java.util.ArrayList;これがあれば配列数を宣言しなくても良くなるって感じなのかな
自動でなんかリサイズするみたいな感じ




ruby

def hello
  puts "Hello, world!"
end

 メソッドを定義しただけでは何も表示されない

hello メソッドを呼び出す

これがjavaだと

class Main {
    public static void main(String[] args) {
        System.out.println("Hello, world!");
    }
}




メソッドを呼び出す指示がなくても出力される

Rubyでは、メソッド定義の開始を示す「def」という文字が必要でした。

アクセス修飾子 static修飾子 返り値のデータ型　メソッド名() {
  // 行いたい処理
}

Javaではそのような記述の代わりに、実行したい処理を「{」と「 }」で囲みます。

アクセス修飾子は、外部への公開範囲を設定するためのもので、以下の３種類があります。

・public
・protected
・private

要はこれはアクセス権限かな

staticは「静的」という意味の英単語です。静的とは、状態が変化しないことを意味します。

メソッドの定義の際に、staticをつけることで「静的メソッド」として定義されます。静的メソッドは、「クラスメソッド」とも呼ばれます。

static以外にも

final: 変更不可。クラス、メソッド、変数に使用。
abstract: 抽象的。クラス、メソッドに使用。
synchronized: 同期化。メソッドやブロックに使用。
volatile: 変わりやすい。フィールドに使用。

があるらしいけど現段階では何に使うかわからない

返り値のデータ型　

「中身がない」ことを意味する「void」等色々ありそう

メソッド名()は基本的にrubyとあまり変わらない感じがする。

オブジェクト指向でパート分けされてる。

@Controller
はrubyと同じような物でルーティングが
@GetMapping
("/表示したい場所"）かなSpring フレームワークの場合はこんな感じか

app/viewsかsrc/main/resources/templatesの違いだけかな.htmlの置き場は基本的にルビーとjavaの違いは

package in.techcamp.firstapp;

import lombok.Data;

@Data
public class PostForm {
    private String memo;がparamsと似たような感じってルビーっていかに簡潔か実感する

ルビーのパラメーターの扱いとの違いはルーティング設定をパラムスにもコントローラー名で指示する感じだ

javaはコントローラーでルーティング設定しなきゃいけない感じに思えてきた。ここがルビーとのかなり大きな違いに感じる。




