# なぜreadmeをここに作ったか
php-fpmの設定ファイルzzz-www.confにコメント書くとうまく動作しなかったから

# zzz-wwwにしている理由
php-fmpの設定ファイル名をzzz-wwwにしているのは
公式の設定ファイル名がzz-docker.confになっていてこれより後に呼ばれて
変更を反映されるようにするため
公式のphp-fmpの設定：https://github.com/docker-library/php/blob/f016f5dc420e7d360f7381eb014ac6697e247e11/7.0/fpm/alpine/Dockerfile#L136

# なぜwww-dataなのか
php-fpmのワーカ起動ユーザはwww-dataになっているため、nginxではなくこちらで設定しないといけない
https://qiita.com/kotarella1110/items/634f6fafeb33ae0f51dc
https://qiita.com/t_wkm2/items/910b4d7079b8413895a6
php-fpmでは原則あらかじめ1つないし複数のワーカープロセスを起動しておいて、webサーバーからの対応を迅速に行えるようにしている。
そのプロセスの立ち上げ権限があるのがwww-data?  https://hackers-high.com/linux/php-fpm-config/