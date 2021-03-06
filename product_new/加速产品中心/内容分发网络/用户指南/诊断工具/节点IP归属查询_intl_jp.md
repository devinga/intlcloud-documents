## 機能の説明
Content Delivery Networkはお客様のためにIP帰属クエリーツールを提供しています。お客様はこのツールにより指定したIPがTencent Cloud CDNのグローバル加速ノードであるかどうか、IPの所在する加速サービスエリア、省及びキャリア情報を確認することができます。
## ユースケース
障害処理類のケースではこのツールは障害検出に使われることができます。ユーザーアクセスに異常が発生した場合は、クライアントが実際にアクセスをリクエストするIPをツールでクエリーを行います。
- Tencent Cloud CDNに帰属しない場合は、ドメイン名の解析構成は異常である可能性があります。ドメイン名の解析のサービスプロバイダーでCNAMEの構成が正常であるかどうかを確認します。
- Tencent Cloud CDNに帰属している場合は、ノードのサービス状態を照会することにより、ノードのオンライン/オフラインによるリクエスト中断があるかどうかを確認できます。

## 操作ガイド
### クエリーの方法
 [CDN コンソール](https://console.cloud.tencent.com/cdn)にログインし、左側のディレクトリの【診断ツール】>【IP 帰属クエリー】を選択し、機能ページに入ります。
![](https://main.qcloudimg.com/raw/7c72a39a1c0f33e633057d02af9c3a6f.png)

### ご利用の際の約束
- テキストボックスに検証する複数のIPアドレスを1行に1つずつ入力します。
- 最大20個のIPまでを一括検証できます。
- IPv4とIPv6アドレスの検証をサポートしています。
- グローバルにおける加速ノードの検証をサポートしています。中国国内のノードの場合は所在する省のキャリアのデータを戻し、海外のノードの場合は所在する国のデータを戻します。
- ノードの**過去3時間**のサービス状態の変動状況を確認できます。オンライン/オフラインの変動がある場合は、対応する操作時間を照会できます。

## 利用事例
### IPが中国国内に帰属する
![](https://main.qcloudimg.com/raw/92a04bfdc0905c9be0465d3dc4825dd3.png)
### IPが海外に帰属する
![](https://main.qcloudimg.com/raw/6a2e1b6f94362d5508ed98a52bd2d125.png)
### IPv6帰属クエリー
>! IPv6加速は内部テスト段階にあります。IPv6 加速の必要がある場合、 申請をサブミットをクリックしてください。
>
![](https://main.qcloudimg.com/raw/7e88553e81f01e86fd4325c3d433fbca.png)



