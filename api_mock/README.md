# API Blueprint 環境構築
※nodeのバージョン v0.10.45で動作確認

## aglio / api-mock インストール
```
$ npm install
```

## HTML 生成
```
$ aglio -i xxx.md -o xxx.html

$ open xxx.html
```

## 変更監視
```
$ aglio -i api.md -s

$ open http://127.0.0.1:3000/
```

## モックサーバ起動
```
$ api-mock xxx.md --port 3001
```
