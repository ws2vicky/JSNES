FROM nginx:1.19.9-alpine

ENV TZ=Asia/Shanghai
COPY src/ /opt/nes-game-web/
COPY lib/ /opt/nes-game-web/lib/
COPY roms/ /opt/nes-game-web/roms/
COPY default.conf /etc/nginx/conf.d/default.conf

HEALTHCHECK --interval=10s --timeout=3s CMD curl --fail http://localhost:80/
