# Kaggle House Prices

このリポジトリは、Kaggleの「[House Prices - Advanced Regression Techniques](https://www.kaggle.com/competitions/house-prices-advanced-regression-technique%3C/0%3Es/)」コンペティションを題材に、実験管理方法、 `polars` の使い方、探索的データ分析（EDA）、シンプルな機械学習モデルの構築を学ぶためのものです。



## 実験管理

以下のようなディレクトリ構成で実験を管理します。

```
.
├── README.md
├── data
│   ├── data_description.txt
│   ├── sample_submission.csv
│   ├── test.csv
│   └── train.csv
├── exp
│   ├── 000
│   │   ├── 00_download.ipynb
│   │   ├── 01_polars.ipynb
│   │   ├── 02_eda.ipynb
│   │   ├── 03_build_simple_moel.ipynb
│   │   ├── config
│   │   │   └── config.yaml
│   │   └── src
│   │       └── seed.py
│   ├── 001
│   └── 002
├── pyproject.toml
├── results
│   ├── 000
│   │   └── submission_000.csv
│   └── 001
│       └── submission_001.csv
└── uv.lock
```

dataディレクトリにはデータを格納します。train.csv, test.csv, sample_submission.csvはコンペからダウンロードしたデータです。

expディレクトリには実験ごとにサブディレクトリを作成し、各実験のコードや設定ファイルを格納します。  
resultsディレクトリには各実験の結果を格納します。expディレクトリのサブディレクトリ名は実験のバージョン番号とし、000, 001, 002...と増やしていきます。

`000/config/config.yaml`には実験の設定を記述します。  
`hydra`によって設定ファイルを読み込み、実験を実行します。



## 01_polars.ipynb

polarsの使い方を学びます。

polarsはpandasの代替として使えるデータフレームライブラリです。pandasよりも高速でメモリ効率が良いです。polarsはRustで実装されており、Pythonからも使えるようになっています。

## 02_eda.ipynb

EDAの仕方を学びます。EDAはExploratory Data Analysisの略で、データを探索的に分析することです。

データの分布や相関関係を調べることで、データの特徴を把握します。EDAは機械学習モデルの精度向上に役立ちます。

## 03_build_simple_model.ipynb

LightGBMを使ってシンプルなモデルを構築します。


001以降自分で特徴量加工による精度向上や、他のモデルとのアンサンブルを試してみてください。
