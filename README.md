# InpaintingContainer
Docker Container for Image Inpainting  
Powered by https://github.com/Atlas200dk/sample-imageinpainting-HiFill

|  Docker Service  |  Python Version  |  Tensorflow Version  |
| ---- | :---: | :---: |
|  inpaint-app  |  3.7  |  1.13.1  |
|  inpaint-app-v2  |  3.9  |  2.5.0  |

## ディレクトリ構成
<pre>
.
├── README.md
├── docker-compose.yml
├── inpaint
│   ├── Dockerfile
│   ├── requirements.txt
│   └── test.py: 推論スクリプト
├── inpaint_v2
│   ├── Dockerfile
│   ├── requirements.txt
│   └── test.py: 推論スクリプト
├── inputs
│   ├── pb/hifill.pb: 学習済みパラメータファイル
│   ├── imgset/: 入力画像
│   └── maskset/: マスク画像
└── results/: 出力画像
</pre>

## Setup Data
- ~~inputs/pb/以下に[HiFillのレポジトリ](https://github.com/Atlas200dk/sample-imageinpainting-HiFill)の`GPU_CPU/pb/hifill.pb`を入れる~~
- inputs/imgset/以下に入力画像を入れる
- inputs/maskset/以下に対応したマスク画像を同じファイル名で入れる
## Inference
```
docker-compose up -d [サービス名]
docker-compose exec [サービス名] bash
python test.py
```
[サービス名]にはinpaint-appまたはinpaint-app-v2を入れてください  
=> results/以下に出力ファイルが出来上がります
