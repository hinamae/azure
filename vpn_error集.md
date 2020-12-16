# vpn

## vpn gateway作成方法

https://docs.microsoft.com/ja-jp/azure/vpn-gateway/vpn-gateway-howto-point-to-site-resource-manager-portal

## 自己署名ルート証明書の作成andクライアント証明書の生成

https://docs.microsoft.com/ja-jp/azure/vpn-gateway/vpn-gateway-certificates-point-to-site


証明書マネージャ　certmgr.msc

## クライアント証明書のインストール

https://docs.microsoft.com/ja-jp/azure/vpn-gateway/point-to-site-how-to-vpn-client-install-azure-cert

## 自己署名ルート証明書の登録

https://docs.microsoft.com/ja-jp/azure/vpn-gateway/vpn-gateway-howto-point-to-site-resource-manager-portal



## 証明書情報

自己署名ルート証明書：P2SRootCert(消してよい。エクスポート用だから、ローカルに残しておく必要はなし。)
クライアント証明書：P2SChildCert(VPN接続に必要。ローカルにインストールしておく必要あり。)


## error

- 仮想マシンを作成したときのエラー
SSH 秘密キーをダウンロードできませんでした
サブスクリプションが名前空間 'Microsoft.Compute' を使用するように登録されていません。サブスクリプションを登録する方法については、https://aka.ms/rps-not-found をご覧ください。 エラーの詳細: サブスクリプションが名前空間 'Microsoft.Compute' を使用するように登録されていません。サブスクリプションを登録する方法については、https://aka.ms/rps-not-found をご覧ください。 エラーの詳細: [object Object]

- 解決
    - Azure ポータルにアクセスします。
    - [サブスクリプション] 、使っているサブスクリプション、 [リソース プロバイダ]の順に選びます。
    - リソース プロバイダーの一覧で、 [Microsoft.Compute] に対して [登録] を選びます。 リソース プロバイダーを登録するには、サブスクリプションの共同作成者または所有者のロールが必要です。



1.自己証明書とクライアント証明書の発行(2と順不同)
2.Vnet、GatewaySubnet、VPNゲートウェイの構築
3.自己証明書をVPNゲートウェイに渡し、VPNクライアントソフトをダウンロード
4.VPN接続トライ(完成)


- 仮想ネットワークゲートウェイを仮想ネットワークに紐づけようとしたときに「使用中」となって、紐づけられないエラー

- 仮想ネットワークの範囲内にゲートウェイサブネットが収まっていない。
もしくは、仮想マシンが存在していたらダメ？

仮想ネットワーク：10.1.0.0/16
仮想ネットワークゲートウェイサブネット：10.1.255.0/27　(10.1.255.0~10.1.255.31の32アドレス)
にした。


- 証明書マネージャにpowershellでエクスポートした証明書がなぜか表示されないエラー

- windowsの証明書マネージャを立ち上げなおすと反映される




ワンちゃんWSLを有効化したらうまくいく？？？？？？？？？？
