---

copyright:
  years: 2016, 2017, 2018
lastupdated: "2018-11-28"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:tip: .tip}

# アプリの最初からの作成
{: #tutorial}

サービスとランタイムを使用してカスタム・アプリケーションを最初から作成できます。必要なツールをインストールして、アプリをビルドしてローカルで実行し、クラウドにデプロイする方法を確認できます。
{: shortdesc}

## ステップ 1. ツールのインストール
{: #install-tools}

[{{site.data.keyword.dev_cli_long}}](/docs/cli/index.html) をインストールします。

Docker は開発者ツールの一部としてインストールされます。 ビルド・コマンドが機能するためには、Docker が実行中でなければなりません。 Docker アカウントを作成して、Docker アプリを実行し、サインインする必要があります。

## ステップ 2. アプリを最初から作成する
{: #create-devex}

{{site.data.keyword.cloud}} ダッシュボードでカスタム・アプリを作成します。

1. [{{site.data.keyword.cloud}} ダッシュボード ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://{DomainName}) から、**「作成」**を選択して、カスタム・アプリケーションを作成します。

  {{site.data.keyword.dev_console}}の[「スターター・キット」 ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://{DomainName}/developer/appservice/starter-kits/) ページで、**「作成」**を選択してカスタム・アプリケーションを作成することもできます。
  {: tip}

2. アプリ名を入力します。 このチュートリアルでは、`CustomProject` を使用します。
3. 固有のホスト名 (例えば、`abc-devhost`) を入力します。このホスト名からアプリの経路 (`abc-devhost.mybluemix.net`) が作成されます。
4. ご使用の言語とフレームワークを選択します。 一部のスターター・キットは、1 つの言語でしか使用できない場合があります。
5. 価格プランを選択します。 このチュートリアルでは、無料オプションを使用できます。
6. **「作成」**をクリックします。

## ステップ 3. リソースの追加 (オプション)
{: #add-services}

Watson のコグニティブ機能でアプリを拡張するリソースを追加したり、モバイル・サービスやセキュリティー・サービスを追加したりできます。 このチュートリアルでは、データを管理する場所を追加します。

1. 「アプリ・サービス」ウィンドウで、**「リソースの追加」**をクリックします。
2. 必要なサービスの種類を選択します。 例えば、**「データ (Data)」**>**「次へ」**>**「Cloudant」**>**「次へ」**をクリックします。
3. 価格プランを選択します。 このチュートリアルでは、無料オプションを使用できます。
4. **「作成」**をクリックします。

## ステップ 4. DevOps ツールチェーンを使用したデプロイ
{: #add-toolchain}

ツールチェーンを有効にすると、アプリ用のチーム・ベースの開発環境が作成されます。 ツールチェーンの作成時に、アプリ・サービスによって Git リポジトリーが作成されます。このリポジトリーでは、ソース・コードの表示、アプリの複製、および問題の作成と管理を行うことができます。 また、専用の GitLab 環境と、継続的 Delivery Pipeline にアクセスすることもできます。 Kubernetes でも Cloud Foundry でも、選択したデプロイメント・プラットフォームに合わせてこれらはカスタマイズされています。

一部のアプリケーションでは継続的デリバリーは有効になっています。 継続的デリバリーを有効にして、Delivery Pipeline と GitHub を使用したビルド、テスト、およびデプロイメントを自動化することができます。

1. アプリの詳細ページで、**「クラウドにデプロイ (Deploy to Cloud)」**をクリックします。
2. デプロイメント方式を選択します。 選択した方式の説明に従って、デプロイメント方式をセットアップします。
  * Kubernetes クラスターにデプロイします。 高可用性のアプリケーション・コンテナーをデプロイして管理するためのワーカー・ノードというホスト・クラスターを作成します。 クラスターを作成したり、既存のクラスターにデプロイしたりすることができます。
  * Cloud Foundry を使用してデプロイします。この場合、基礎となるインフラストラクチャーを管理する必要はありません。
  * 仮想サーバー・インスタンスにデプロイします。

最後のステップでアプリをクラウドにデプロイすることで、ツールチェーンが自動的に作成されます。ツールチェーンによってアプリ用の Git リポジトリーが作成され、ユーザーはそこでコードを見つけることができます。詳しくは、[ツールチェーンの作成](/docs/services/ContinuousDelivery/toolchains_working.html)を参照してください。

## ステップ 5. アプリのビルドおよびローカルでの実行
{: #build-run}

アプリをクラウドにプッシュする前に、テスト用にアプリをローカルでビルドすることもできます。

1. 「アプリ・サービス」ウィンドウで、**「コードのダウンロード (Download Code)」**または**「リポジトリーの複製 (Clone your repo)」**をクリックして、コードをローカルで処理します。
2. 統合開発環境にアプリをインポートします。
3. コードを変更します。
4. パーソナル・アクセス・トークンを追加して、[Git 認証](/docs/services/ContinuousDelivery/git_working.html#git_authentication)をセットアップします。
5. {{site.data.keyword.Bluemix}} コマンド・ライン・インターフェースにログインします。 組織でフェデレーテッド・ログインを使用している場合は、`-sso` オプションを使用します。

  ```bash
  ibmcloud login -sso
  ```
  {: pre}

6. 組織とスペースのターゲットを設定します。

  ```bash
  ibmcloud target --cf
  ```
  {: pre}

7. 資格情報を取得します。

  ```bash
  ibmcloud dev get-credentials
  ```
  {: pre}

8. Docker が実行中であることを確認して、ディレクトリーからローカル開発コンテナーでアプリをビルドします。

  ```bash
  ibmcloud dev build
  ```
  {: pre}

9. ローカル開発コンテナーでアプリを実行します。

  ```bash
  ibmcloud dev run
  ```
  {: pre}

10. ご使用のブラウザーで `http://localhost:3000` を開きます。 ご使用のポート番号は、選択したランタイムによって異なる可能性があります。

## ステップ 6. アプリのデプロイ
{: #deploy}

### DevOps ツールチェーンを使用したデプロイ

アプリはいくつかの方法で {{site.data.keyword.cloud_notm}} にデプロイできますが、DevOps ツールチェーンが、実動アプリをデプロイする場合に最適な方法です。 DevOps ツールチェーンを使用すると、多数の環境へのデプロイメントを簡単に自動化して、成長するアプリの管理に役立つモニタリング、ロギング、およびアラートの各サービスを素早く追加することができます。

正しく構成されたツールチェーンを使用すると、リポジトリー内のマスター・ブランチへのマージが行われるたびに、ビルドとデプロイのサイクルが自動的に開始されます。 {{site.data.keyword.cloud_notm}} 開発者ダッシュボードから作成されたツールチェーンはすべて、自動デプロイメント用に構成されています。

DevOps ツールチェーンからアプリを手動でデプロイすることもできます。

1. 「アプリ詳細」ウィンドウから、**「ツールチェーンの表示」**をクリックします。
2. **「Delivery Pipeline」**をクリックします。ここで、ビルドの開始、デプロイメントの管理、およびログと履歴の表示を行うことができます。

詳しくは、[ビルドとデプロイ](/docs/services/ContinuousDelivery/pipeline_build_deploy.html)を参照してください。

### {{site.data.keyword.dev_cli_short}} を使用したデプロイ

アプリを Cloud Foundry にデプロイするには、以下のコマンドを入力します。
```
ibmcloud dev deploy
```
{: pre}

アプリを Kubernetes クラスターにデプロイするには、以下のコマンドを入力します。
```
ibmcloud dev deploy --target <container>
```
{: pre}

## ステップ 7. アプリが実行中であることの確認
{: #verify}

アプリのデプロイ後に、DevOps パイプラインまたはコマンド・ラインにアプリの URL (例えば、`abc-devhost.mybluemix.net`) が示されます。 ご使用のブラウザーでその URL にアクセスします。