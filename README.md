# Angularjs チュートリアル感想

- tsファイルの編集 / angularの実装部分にフォーカスを当てているので、スクラッチで作成するときはチュートリアルと違う手順を踏む必要がある。
- reactと比較するとview部分だけに特化しているわけではないので、プロジェクトで使う場合angularにどっぷり浸かることになる。
    - バージョンが上がったときにどれだけ後方互換があるかを考えると1ライブラリで賄うangularのほうが、アップデートはしやすそう。
    - プラグインでさっと賄いたい機能を追加するのはしづらいっぽい 
        - reactなら react + 何かで副次的に知識を広げることができるけど、angularは難しそう

# flask メモ

- flask-mysqlはselect文の実行結果をsetで返すので、結果をdictに変換する必要がある。期待はずれ。
    - それがpythonic way らしい。

# flask mysql メモ

- autocommitがtrueになっていない場合、connector.commit() が必要
    - flask-MySQLのコンストラクタにautocommit=Trueで渡しても、mysqlのautocommitはtrueにならない
        - 原因不明。

# flask docker メモ

- `$ pip install -e APPPATH`はうまくいかない。
    - `$ python APPPATH/setup.py develop` でやりたいことは達成。
- docker-compose.ymlのcommandで flask run しても外部からアクセスできない。
    - appファイル内でmain() で動かす必要あり。


# docker-compose mysql メモ

- MYSQL_ROOT_PASSWORD, MYSQL_ALLOW_EMPTY_PASSWORD, MYSQL_RANDOM_ROOT_PASSWORDの設定だけではホストから接続できなかった
    - mysql57の初期設定でrootのlocalhost以外の接続が確かできないはずなので、そのせいかなと。

