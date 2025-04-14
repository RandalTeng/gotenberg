FROM debian:12-slim

RUN set -e; \
    sed -i 's/deb.debian.org/mirrors.aliyun.com/g' /etc/apt/sources.list.d/debian.sources && \
    apt update && \
    apt-get install -y ca-certificates fonts-liberation libasound2 libatk-bridge2.0-0 libatk1.0-0 libatspi2.0-0 \
      libcairo2 libcups2 libcurl4 libdbus-1-3 libexpat1 libgbm1 libglib2.0-0 libgtk-4-1 libnspr4 libnss3 \
      libpango-1.0-0 libvulkan1 libx11-6 libxcb1 libxcomposite1 libxdamage1 libxext6 libxfixes3 libxkbcommon0 \
      libxrandr2 wget xdg-utils && \
    # 下载特殊处理CDP的 chromium.deb 包
    wget -c -o /opt/chromium.deb "https://image.3001.net/static/libs/chromium-browser-unstable_137.0.7119.0-1_amd64.deb" &&  \
    dpkg -i /opt/chromium.deb && \
    ln -sf /opt/chromium.org/chromium-unstable/chromium-browser-unstable /usr/bin/chromium && \
    chromium --version && \
    rm -rf /opt/chromium.deb /var/lib/apt/lists/* /tmp/* /var/tmp/*

CMD [ "sleep", "300" ]
