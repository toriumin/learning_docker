# wakaba

# run container

1. ディレクトリの作成と移動

  ```
  $ mkdir wakaba && $ cd wakaba
  ```

1. コンテナを作成する

  ```
  $ docker run -d -p 80:80 --name myapp -v $(pwd):/var/www/html php:7.0-apache
  ```

1. コンテナ一覧を見る

該当アプリの STATUS が Up になっていれば、コンテナが起動しているということ

  ```
  $ docker container ls

  CONTAINER ID    IMAGE           COMMAND                  CREATED          STATUS           PORTS                NAMES
  e4372319c189    php:7.0-apache  "docker-php-entrypoi…"   9 minutes ago    Up 9 minutes     0.0.0.0:80->80/tcp   myapp
  ```

1. `myapp` コンテナの中に入る
  ```
  $ docker exec -it myapp bash
  ```

1. php ファイルを作成する
  ```
  $ echo `<?php phpinfo();`> index.php
  ```

1. http://localhost にアクセスする

# exit container

```
control + p + q
```

# stop container

```
$ dokcer stop myapp
```

# remove container

```
$ dokcer rm myapp
```
