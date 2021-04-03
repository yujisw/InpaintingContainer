# InpaintingContainer

## ディレクトリ構成
InpaintingContainer/  
├ inpaint/  
│ ├ pb/hifill.pb: 学習済みパラメータファイル  
│ ├ Dockerfile  
│ ├ requirements.txt  
│ └ test.py: 推論スクリプト  
├ inputs/  
│ ├ imgset/: 入力画像  
│ └ maskset/: マスク画像  
├ results/: 出力画像  
├ .gitignore  
├ docker-compose.yml  
└ README.md  

## Setup Data
- inpaint/pb/以下にhifill.pbを入れる
- inputs/imgset/以下に入力画像を入れる
- inputs/maskset/以下にマスク画像を入れる
## Inference
```
docker-compose up -d
docker-compose exec inpaint-app bash
python test.py
```
results/以下に出力ファイルが出来上がります