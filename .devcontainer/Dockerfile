FROM python:3.8.12-slim

# システム依存パッケージ
RUN apt-get update && apt-get install -y --no-install-recommends \
    build-essential \
    python3-dev \
    git \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

# 作業ディレクトリ
WORKDIR /workspace

# requirements.txtをコピーしてインストール
COPY requirements.txt /workspace/
RUN pip install --no-cache-dir -r requirements.txt

# Jupyterカーネル（任意: VSCodeカーネルリストに表示）
RUN python -m ipykernel install --user --name combase_2022 --display-name "Python (ComBase_2022)"
