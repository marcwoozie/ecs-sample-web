FROM nginx:1.13.3

# インクルード用のディレクトリ内を削除
RUN rm -f /etc/nginx/conf.d/*

# Nginxの設定ファイルをコンテナにコピー
ADD nginx/nginx.conf /etc/nginx/conf.d/nginx.conf

RUN apt-get update -qq

# ビルド完了後にNginxを起動
CMD /usr/sbin/nginx -g 'daemon off;' -c /etc/nginx/nginx.conf

ENV APP /app
RUN mkdir $APP
WORKDIR $APP

COPY src $APP