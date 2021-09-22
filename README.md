# Serverlessをやってみよう

ごめんなさい。今日テンパっていて資料が殆ど無くてほぼぶっつけ本番です。
ただ、最近使い倒しているので大丈夫だと思います！多分！

## Serverlessって？

- まず、サーバーはあるｗ
- サーバー管理しなくて良いって事。
- 色々なサービスが出ているけれど、まずやっとけってのが `AWS Lambda` です。
- AWS, GCP, Azure各社同じようなサービスがあります。
- 関数を実行してくれるサービス

## Lambda以外のサービス

AWSどっぷりなのでAWSしかよく分からないですが以下の様なサービスがあります。


https://aws.amazon.com/jp/serverless/


## LambdaでHello World

## Api Gatewayを接続してみる

## 前準備

### AWS CLIのインストール

https://docs.aws.amazon.com/ja_jp/cli/latest/userguide/cli-chap-install.html

### terraformのインストール

https://learn.hashicorp.com/tutorials/terraform/install-cli

### SAM CLIのインストール

https://docs.aws.amazon.com/ja_jp/serverless-application-model/latest/developerguide/serverless-sam-cli-install.html

#### SAMって？

https://docs.aws.amazon.com/ja_jp/serverless-application-model/latest/developerguide/what-is-sam.html


## SAMを使ってサムネイル製造機を作る


### SAMでアプリ初期化

```
% sam init
Which template source would you like to use?
	1 - AWS Quick Start Templates
	2 - Custom Template Location
Choice: ^CAborted!
taichi@219 work1 % aws-profile
Please enter container number.
0 default
1 commude_dev_taichi
2 asaichi
3 ec2-restart
4 nsj-s3
5 commude_amplify
6 commude_cdk
7 asaichi-taichi
8 asaichi-taichi1
9 cmd-premium-malts-cdk
10 cmd_taichi
11 artizon
12 jlm
13 kidsplus
14 rs-staging
15 together
16 media-lab
17 media-lab-s3
18 misumi
19 reed-dev
20 teg
21 mcf_taichi
22 teg-dev
23 chat-test
24 draken_taichi
7
taichi@219 work1 % aws-profile
Please enter container number.
0 default
1 commude_dev_taichi
2 asaichi
3 ec2-restart
4 nsj-s3
5 commude_amplify
6 commude_cdk
7 asaichi-taichi
8 asaichi-taichi1
9 cmd-premium-malts-cdk
10 cmd_taichi
11 artizon
12 jlm
13 kidsplus
14 rs-staging
15 together
16 media-lab
17 media-lab-s3
18 misumi
19 reed-dev
20 teg
21 mcf_taichi
22 teg-dev
23 chat-test
24 draken_taichi
7
taichi@219 work1 % sam init
Which template source would you like to use?
	1 - AWS Quick Start Templates
	2 - Custom Template Location
Choice: 1
What package type would you like to use?
	1 - Zip (artifact is a zip uploaded to S3)	
	2 - Image (artifact is an image uploaded to an ECR image repository)
Package type: 1

Which runtime would you like to use?
	1 - nodejs14.x
	2 - python3.9
	3 - ruby2.7
	4 - go1.x
	5 - java11
	6 - dotnetcore3.1
	7 - nodejs12.x
	8 - nodejs10.x
	9 - python3.8
	10 - python3.7
	11 - python3.6
	12 - python2.7
	13 - ruby2.5
	14 - java8.al2
	15 - java8
	16 - dotnetcore2.1
Runtime: 1

Project name [sam-app]: sam-work1

Cloning from https://github.com/aws/aws-sam-cli-app-templates

AWS quick start application templates:
	1 - Hello World Example
	2 - Step Functions Sample App (Stock Trader)
	3 - Quick Start: From Scratch
	4 - Quick Start: Scheduled Events
	5 - Quick Start: S3
	6 - Quick Start: SNS
	7 - Quick Start: SQS
	8 - Quick Start: Web Backend
Template selection: 5

    -----------------------
    Generating application:
    -----------------------
    Name: sam-work1
    Runtime: nodejs14.x
    Dependency Manager: npm
    Application Template: quick-start-s3
    Output Directory: .
    
    Next steps can be found in the README file at ./sam-work1/README.md
```


### CloudFormationって？

https://docs.aws.amazon.com/ja_jp/AWSCloudFormation/latest/UserGuide/Welcome.html

TerraformやCDKもあるよ。

### CloudFormation練習

```
aws cloudformation create-stack \
--stack-name create-s3-test \
--template-body file://s3Template.yml \
--parameters ParameterKey=S3BucketName,ParameterValue=taichi-hogehoge
```


