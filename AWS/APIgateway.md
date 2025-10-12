# Amazon API gatewayについて
本記事では、Amazon API gatewayについて説明します。API gatewayとは、AWSが提供する「APIの作成および管理を簡単に行える」フルマネージドサービスです。Lambda や EC2、DynamoDB、S3 などと連携することが可能です。

今回は、URLにアクセスすると `"message": "Hello from Lambda!"` を返すAPIを作りながら出てきた概念についてまとめていきます。構成イメージは以下のとおりです。
```css
[Client]
   ↓  (HTTPリクエスト)
[API Gateway]
   ↓  (トリガー)
[Lambda Function]
   ↓  (レスポンス)
API Gateway → Client に返す
```

