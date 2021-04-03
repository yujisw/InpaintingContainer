# InpaintingContainer
Docker Container for Image Inpainting  
powered by https://github.com/Atlas200dk/sample-imageinpainting-HiFill
## ディレクトリ構成
<pre>
.
├── README.md
├── docker-compose.yml
├── inpaint
│   ├── Dockerfile
│   ├── pb/hifill.pb: 学習済みパラメータファイル
│   ├── requirements.txt
│   └── test.py: 推論スクリプト
├── inputs
│   ├── imgset/: 入力画像
│   └── maskset/: マスク画像
└── results/: 出力画像
</pre>

## Setup Data
- inpaint/pb/以下に[HiFillのレポジトリ](https://github.com/Atlas200dk/sample-imageinpainting-HiFill)の`GPU_CPU/pb/hifill.pb`を入れる
- inputs/imgset/以下に入力画像を入れる
- inputs/maskset/以下に対応したマスク画像を同じファイル名で入れる
## Inference
```
docker-compose up -d
docker-compose exec inpaint-app bash
python test.py
```
results/以下に出力ファイルが出来上がります