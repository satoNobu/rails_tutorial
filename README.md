[参考URL]   
DockerでのRuby on Rails環境構築を一つずつ詳解する
https://qiita.com/daichi41/items/dfea6195cbb7b24f3419


docker-compose.ymlに以下追加
（本来はpasswaord追加するべきだが今回はチュートリアルのみ実施予定なので無理やり実行）
```
services:
  db:
    image: postgres
    environment:
      POSTGRES_HOST_AUTH_METHOD: 'trust'
      # POSTGRES_PASSWORD: 'postgres' ← envファイルに外出ししても良い
```

# Ruby on Rails チュートリアルのサンプルアプリケーション

これは、次の教材で作られたサンプルアプリケーションです。   
[*Ruby on Rails チュートリアル*](https://railstutorial.jp/)
[Michael Hartl](http://www.michaelhartl.com/) 著

## ライセンス

[Ruby on Rails チュートリアル](https://railstutorial.jp/)内にある
ソースコードはMITライセンスとBeerwareライセンスのもとで公開されています。
詳細は [LICENSE.md](LICENSE.md) をご覧ください。

## 使い方

このアプリケーションを動かす場合は、まずはリポジトリを手元にクローンしてください。
その後、次のコマンドで必要になる RubyGems をインストールします。

```
$ bundle install --without production
```

その後、データベースへのマイグレーションを実行します。

```
$ rails db:migrate
```

最後に、テストを実行してうまく動いているかどうか確認してください。

```
$ rails test
```

テストが無事に通ったら、Railsサーバーを立ち上げる準備が整っているはずです。

```
$ rails server
```

詳しくは、[*Ruby on Rails チュートリアル*](https://railstutorial.jp/)
を参考にしてください。