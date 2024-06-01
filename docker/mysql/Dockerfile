# MySQL公式イメージをベースにする
FROM mysql:8.0.37
LABEL maintainer "kazu"

# 環境変数を設定（オプション）
ENV MYSQL_ROOT_PASSWORD=root123!

COPY mysql.cnf /etc/mysql/conf.d/mysql.cnf
