FROM python:3.10
ARG DEBIAN_FRONTEND=noninteractive

# パッケージの追加とタイムゾーンの設定
# 必要に応じてインストールするパッケージを追加してください
RUN apt-get update && apt-get install -y \
    tzdata \
&&  ln -sf /usr/share/zoneinfo/Asia/Tokyo /etc/localtime \
&&  apt-get clean \
&&  rm -rf /var/lib/apt/lists/*

ENV TZ=Asia/Tokyo

# libenchant1c2a
RUN apt-get update && apt-get install -y \
    libwoff1 libopus0 libwebp6 libwebpdemux2  libgudev-1.0-0 libsecret-1-0 libhyphen0 libgdk-pixbuf2.0-0 libegl1 libnotify4 libxslt1.1 libevent-2.1-7 libgles2 libxcomposite1 libatk1.0-0 libatk-bridge2.0-0 libepoxy0 libgtk-3-0 libharfbuzz-icu0 libgstreamer-gl1.0-0 libgstreamer-plugins-bad1.0-0 gstreamer1.0-plugins-good gstreamer1.0-libav libnss3 libxss1 libasound2 fonts-noto-color-emoji libxtst6 libdbus-glib-1-2 libxt6 ffmpeg xvfb \
    cron vim less

RUN apt-get update && apt install fonts-ipafont-gothic fonts-ipafont-mincho

# JupyterLab関連のパッケージ（いくつかの拡張機能を含む）
# 必要に応じて、JupyterLabの拡張機能などを追加してください
RUN python3 -m pip install --upgrade pip \
&&  pip install --no-cache-dir \
    black \
    jupyterlab \
    jupyterlab_code_formatter \
    jupyterlab-git \
    lckr-jupyterlab-variableinspector \
    jupyterlab_widgets \
    ipywidgets \
    import-ipynb

# 基本パッケージ
# Pythonでよく利用する基本的なパッケージです
# JupyterLabの動作には影響しないので、必要に応じてカスタマイズしてください
RUN pip install --no-cache-dir \
    scrapy \
    scrapy-splash \
    pandas \
    beautifulsoup4 \
    scrapy_playwright
    # numpy \
    # matplotlib \
    # japanize_matplotlib
    # scipy \
    # scikit-learn \
    # pycaret \
    # mlxtend \
    # seaborn \
    # plotly \
    # requests \
    # Pillow \
    # opencv-python

# コマンド実行
RUN playwright install
# RUN crontab crontab.txt
# RUN service cron start


# # 追加パッケージ（必要に応じて）
# # 各環境に特化したパッケージがある場合、この部分に追加します
# RUN pip install --no-cache-dir \
#     pydeps \
#     graphviz \
#     pandas_profiling \
#     shap \
#     umap \
#     xgboost \
#     lightgbm