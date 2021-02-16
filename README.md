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
