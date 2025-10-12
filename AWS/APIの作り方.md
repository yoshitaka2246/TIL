# API処理の仕組み
今回は、AWSで簡単なAPIを作成することを通じて、API処理の仕組みについて解説していきます。
## GET処理
ブラウザや`fetch()`で以下のURLを叩くと、
```bash
https://xxxxxx.execute-api.ap-northeast-1.amazonaws.com/hello
```
↓こんなJSONが帰って来るAPIを作ります↓
```json
{"message":"Hello from AWS Lambda!:}
```
### ステップ１：Lambda関数を作成
1. AWSコンソールで**Lambda**を検索して開く
2. 「関数の作成」→「一から作成」
   1. 関数名：`helloJSHandler`
   2. ランタイム：**Node.js**
3. 作成後、コードエディタを開いて以下を貼り付け
```JavaScript
export const handler = async (event) => {
  // API Gatewayから送られてくるリクエスト情報をログで確認
  console.log("event:", event);

  // レスポンスを返す
  return {
    statusCode: 200,
    headers: {
      "Access-Control-Allow-Origin": "*", // CORS対応
    },
    body: JSON.stringify({
      message: "Hello from JavaScript Lambda!",
      method: event.httpMethod
    }),
  };
};
```
#### `handler`
Lambdaの実行環境は、**`handler`という名前のエクスポートされた関数**を探して実行するため、`handler`はLambdaが実行する「エントリーポイント（入り口）」となります。
ハンドラー関数の名前はLambdaで設定できますが、デフォルトでは`handler`が設定されています。そのため、Lambdaで実行したいエントリーポイントとなる関数の名前は必ず`handler`でなければなりません。
``` Javascript
export function handler(event){

}
```
#### `return`構成について
JavaScriptを用いて、AWS LambdaとAPI gatewayを組み合わせて**RESTful API**を構築する場合、関数が`return`するオブジェクトには、決まったフォーマットがあります。`return`されるオブジェクトは**HTTPレスポンス**としてwebブラウザに返されるための情報を含んでいる必要があるからです。
`return`オブジェクトの構造は、
1. `statusCode` (Number)
2. `headers` (Object)
3. `body` (String)
##### `statusCode(ステータスコード)
クライアント（ブラウザなど）に対して、リクエストが**どのような結果になったか**を伝えるための3桁の数字です。
|範囲|意味|値の例と構造|
|-----|----------------|----------------------------------------------|
|2xx|**成功**|`200`(OK):jリクエストが成功し、データが返される。<br>`201`(Created):新しいデータが作成された。|
|4xx|**クライアントエラー**||
||||
||||