# aws-challenge-demo
## aws-challengeとは
「aws-challenge」とは、 **AWS CloudFormation** や **Serverless Framework** を用いて構築されたAWS環境の不具合を見つけ解決しながらAWSに慣れ親しんでもらうことを目的とした学習課題です。

## イントロ 
なぜか動かないLambda!

API Gatewayの設定が悪いのか？

それとも

Lambdaの設定が悪いのか？

今回の課題は「動かないLambdaの謎を解き明かせ」

挑戦者求！

## 今回作成される環境
![aws-challenge-demo-environment](https://user-images.githubusercontent.com/11880332/61526205-f1aafb00-aa54-11e9-90b6-a2dea5b7fd28.png)

* Amazon API Gateway
* AWS Lambda

### 確認事項
* 作成されるLambda関数のhandler.jsには不具合はありません。

## 環境
環境構築に **Serverless Framework** を利用します。

> https://serverless.com/

**Serverless Framework** をインストールしていない場合
```
$ npm install -g serverless
```


```
$sls -v
1.44.1
```


## 環境構築方法
```
$git clone https://github.com/tomonoriminegishi/aws-challenge-demo.git
$cd aws-challenge-demo
$sls deploy
```

### パラメータオプション
sls deploy時にパラメータを設定できます。

| パラメータ | デフォルト値 |
----|---- 
| stage | dev |
| region | ap-northeast-1 |
| profile | default |

> stageパラメータにユニークな値を設定することで、同じアカウント内に複数の環境を構築することができます。

## 環境撤去方法
```
$cd aws-challenge-demo
$sls remove -v
```

## 課題確認方法

Serverless Frameworkでデプロイが完了するとAPI Gatewayのendpointsが出力されます。

まずは、ブラウザでendpointsにアクセスをしてください。

こんな感じ↓
![名称未設定](https://user-images.githubusercontent.com/11880332/61602690-8ab85c80-ac75-11e9-9f8b-f2ffc7998a49.png)

{key+}の部分は、「helloworld」に置き換えます。

すると、なんということでしょう！

エラーとなるはずです。

こんな感じ↓

<img width="335" alt="スクリーンショット 2019-07-22 11 43 02" src="https://user-images.githubusercontent.com/11880332/61602785-f8fd1f00-ac75-11e9-992f-6be33e79ecee.png">

ここからが課題のスタートです。

構築された環境の不具合を修正することにより、正常な画面が表示されます。

serverless.ymlを修正してもいいですし、AWSコンソールに入って調べてもかまいません。

解き方は自由です。

それでは、Let's enjoy!

## 注意事項

課題によっては、そのまま放置するとお金のかかるものもあります。きちんと環境は撤去するようにしてください。
