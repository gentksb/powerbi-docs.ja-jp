## <a name="general"></a>全般
**質問:** 実際の Windows サービスは何と呼ばれますか?  
**回答:** [サービス] では、ゲートウェイは On-premises data gateway サービスという名前で示されます。

**質問:** ゲートウェイの要件は何ですか?  
**回答:** 主要な[ゲートウェイの記事](../service-gateway-onprem.md)にある要件のセクションを参照してください。

**質問:** ゲートウェイでどのようなデータ ソースがサポートされていますか?  
**回答:** 主要な[ゲートウェイの記事](../service-gateway-onprem.md)にあるデータ ソースの表を参照してください。

**質問:** Azure SQL Database などのクラウド データ ソース用にゲートウェイは必要でしょうか?  
**回答:** いいえ。 ゲートウェイなしでサービスはそのデータ ソースに接続できます。

**質問:** クラウドからゲートウェイへの着信接続はあるのでしょうか?  
**回答:** いいえ。 ゲートウェイは、Azure Service Bus への発信接続を使用します。

**質問:** 発信接続をブロックすると、どうなりますか?  何を開く必要がありますか?  
**回答:** ゲートウェイで使用する[ポートの一覧](../service-gateway-onprem.md#ports)とホストの一覧を参照してください。

**質問:** ゲートウェイはデータ ソースと同じコンピューターにインストールする必要がありますか?  
**回答:** いいえ。 ゲートウェイは、指定された接続情報を使用してデータ ソースに接続します。 この意味では、ゲートウェイをクライアント アプリケーションと考えることができます。 ゲートウェイに必要なのは、指定されたサーバー名に接続できることだけです。

**質問:** ゲートウェイからデータ ソースへのクエリを実行するための待機時間はどれぐらいですか?  最適なアーキテクチャは何でしょうか?  
**回答:** ネットワークの遅延を避けるため、ゲートウェイをできるだけデータ ソースの近くに配置することをお勧めします。 実際のデータ ソース上にゲートウェイをインストールできれば、発生する待機時間は最小限に抑えられます。 データ センターの配置先についても検討してください。 たとえば、サービスで米国西部のデータ センターを使用しており、SQL Server を Azure VM でホストしている場合は、Azure VM も米国西部に配置することをお勧めします。 そうすることで待機時間が最小化され、Azure VM での送信料金を抑えることができます。

**質問:** ネットワーク帯域幅についての要件はありますか?  
**回答:** ネットワーク接続用に十分なスループットを確保することをお勧めします。 環境はどれも異なり、送信されるデータの量によっても必要な帯域幅が異なります。 ExpressRoute を使用すると、オンプレミスと Azure データ センター間のスループットのレベルを保証するために役立ちます。

サード パーティの [Azure Speed Test アプリ](http://azurespeedtest.azurewebsites.net/) を使用してスループットを測定できます。

**質問:** ゲートウェイ Windows サービスを Azure Active Directory アカウントで実行できますか?  
**回答:** いいえ。 Windows サービスには有効な Windows アカウントが必要です。 既定では、サービスの SID (*NT SERVICE\PBIEgwService*) で実行されます。

**質問:** 結果はクラウドにどのように返されますか?  
**回答:** 結果は Azure Service Bus を使用して返されます。 詳細については、「[機能方法](../service-gateway-onprem.md#how-the-gateway-works)」を参照してください。

**質問:** 資格情報はどこに保存されますか?  
**回答:** データ ソースに対して入力した資格情報は、暗号化されてゲートウェイ クラウド サービスに保存されます。 資格情報はオンプレミスのゲートウェイで復号化されます。

**質問:** ゲートウェイを境界ネットワーク (DMZ、非武装地帯、スクリーン サブネット) に配置できますか?  
**回答:** ゲートウェイはデータ ソースに接続する必要があります。 データ ソースが境界ネットワーク内でアクセス可能でない場合、ゲートウェイはデータ ソースに接続できない可能性があります。 たとえば、SQL Server が境界ネットワーク内にない場合があります。 また、境界ネットワークから SQL Server には接続できません。 ゲートウェイを境界ネットワークに配置した場合、ゲートウェイは SQL Server にアクセスできなくなります。

**質問:** Azure Service Bus とのトラフィックに TCP ではなく HTTPS を使用するようにゲートウェイに強制することはできますか。  
**回答:** はい。 ただし、これによりパフォーマンスが大幅に低下します。 *Microsoft.PowerBI.DataMovement.Pipeline.GatewayCore.dll.config* ファイルを変更する必要があります。 値を `AutoDetect` から `Https` に変更します。 このファイルは、既定では *C:\Program Files\On-premises data gateway* にあります。

**質問:** Azure データ センター IP リストをホワイトリストに登録する必要がありますか? どこでリストを取得できますか?  
**回答:** 送信 IP トラフィックをブロックしている場合は、ホワイトリストへの Azure データ センター IP リストの登録が必要になることがあります。 現在、ゲートウェイは、完全修飾ドメイン名に加えて IP アドレスを使って Azure Service Bus と通信します。 Azure データ センター IP リストは毎週更新されます。 [Microsoft Azure データ センター IP リスト](https://www.microsoft.com/download/details.aspx?id=41653)をダウンロードできます。

```
<setting name="ServiceBusSystemConnectivityModeString" serializeAs="String">
    <value>Https</value>
</setting>
```

## <a name="high-availabilitydisaster-recovery"></a>高可用性と障害復旧
**質問:** ゲートウェイで高可用性のシナリオを実現するためのプランはありますか?  
**回答:** はい、これは Power BI チームが積極的に力を注いでいる分野です。 この機能の今後の更新については、[Power BI のブログ](https://powerbi.microsoft.com/blog/)に注目していてください。

**質問:** ディザスター リカバリーにはどのオプションを使用できますか。  
**回答:** 回復キーを使ってゲートウェイを復元または移動できます。 ゲートウェイをインストールするときに回復キーを指定してください。

**質問:** 回復キーの利点は何ですか?  
**回答:** ゲートウェイの設定を移行または回復する方法を提供します。 ディザスター リカバリーにも使用されます。

## <a name="troubleshooting"></a>トラブルシューティング
**質問:** ゲートウェイ ログはどこにありますか?  
**回答:** [トラブルシューティングに関する記事](../service-gateway-onprem-tshoot.md#tools-for-troubleshooting)にあるツールのセクションを参照してください。

**質問:** オンプレミスのデータ ソースにどのようなクエリが送信されているかを確認する方法を教えてください。  
**回答:** クエリ トレースを有効にすることができます。  このトレースには、送信されるクエリが含まれます。 トラブルシューティングが完了したら、忘れずに元の値に戻してください。 クエリ トレースを有効にすると、ログの容量が大きくなります。

データ ソースに用意されているクエリ追跡用のツールを検討することもできます。 たとえば、SQL Server と Analysis Services に拡張イベントや SQL Profiler を使用できます。

