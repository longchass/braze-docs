---
nav_title: クエリテンプレート
article_title: クエリビルダーテンプレート
page_order: 0
page_type: reference
toc_headers: h2
description: "このリファレンス記事では、Query BuilderでSnowflakeのBrazeデータを使用して作成できるレポートの種類を一覧表示します。"
tool: Reports
---

# クエリビルダーのテンプレート

> レポートを作成する際に[クエリビルダー]({{site.baseurl}}/user_guide/data_and_analytics/query_builder/)テンプレートにアクセスするには、**クエリテンプレート**を選択します。すべてのテンプレートは過去60日間のデータを表示しますが、エディターでその値や他の値を直接編集できます。

## チャネルテンプレート

<style>
table th:nth-child(1) {
    width: 30%;
}
table th:nth-child(2) {
    width: 70%;
}
table td {
    word-break: break-word;
}
</style>

| クエリ名 | 説明 | 
| --- | --- | 
| チャネルエンゲージメントと収益 | このレポートは、各チャネルごとに、すべてのエンゲージメント指標（開封数やクリック数など）、収益、取引数、および平均価格を示しています。{::nomarkdown}<ul> <li> <i>取引数:</i>購入イベント数 </li> <li> <i>平均価格:</i>取引によって分けられた収益 </li> </ul> {:/} ![]({% image_buster /assets/img_archive/channel_engagement_revenue.png %}) |
| セグメント別の購入と収益 | このレポートは、特定のセグメントに送信されたメッセージのメトリクスを示しています。<br><br> 購入指標は報告期間全体で一意です。1人のユーザーは、最大で1回の購入を生成できます。収益は、報告期間中のすべての購入を考慮に入れます。 |
| セグメント別のバリアントまたはステップの購入と収益 | このレポートは、各セグメントに送信されたメッセージのバリアントまたはキャンバスステップのメトリクスを示しています。<br><br> 購入指標は報告期間全体で一意です。1人のユーザーは、最大で1回の購入を生成できます。収益は、報告期間中のすべての購入を考慮に入れます。 |
| 購入のためのトップ/ボトムメッセージング | このレポートは、上位または下位のキャンペーン、キャンバス、またはキャンバスステップの購入指標を示しています。各行はキャンペーン、キャンバス、またはキャンバスステップです。トップパフォーマーまたはボトムパフォーマーを表示するかどうか、およびこの分析を実行する特定の指標（例えば、*受領時のユニーク購入数*、*受領時の収益*、*ユニーク受信者数*）を指定する必要があります。<br><br> トップパフォーマーレポートの行は、最高から最悪の順に並べられ、ボトムパフォーマーレポートの行は、最悪から最高の順に並べられます。 |
{: .reset-td-br-1 .reset-td-br-2 }

## キャンペーンテンプレート

| クエリ名 | 説明 | 
| --- | --- | 
| 国別のキャンペーン収益 | このレポートは、特定のキャンペーンにおける国ごとの収益を示しています。このレポートを実行するには、キャンペーンのAPI識別子を指定する必要があります。キャンペーンのAPI識別子は、そのキャンペーンの詳細ページの下部にあります。<br><br> このレポートは、各国の収益額、注文数、返品数、純収益、および総収益を示しています。<br><br> {::nomarkdown}<ul> <li> <i>注文:</i>購入イベント数 </li> <li><i> 戻り値:</i>負の収益値を持つ購入イベントの数 </li> <li><i> 純収益:</i>すべての非返品の収益 </li> <li><i> 総収入:</i>返品の価値を含む収益 </li></ul>{:/} ![]({% image_buster /assets/img_archive/campaign_revenue_country.png %}){: style="max-width:70%;"} |
{: .reset-td-br-1 .reset-td-br-2 }

## キャンバステンプレート

| クエリ名 | 説明 | 
| --- | --- | 
| 国別のキャンバス収益 | このレポートは、特定のキャンバスの国ごとの収益を示しています。このレポートを実行するには、キャンバスのAPI識別子を指定する必要があります。**Analyze Variants**の下にキャンバスAPI識別子があります。<br><br> このレポートは、各国の収益額、注文数、返品数、純収益、および総収益を示しています。<br><br> {::nomarkdown}<ul> <li> <i>注文:</i>購入イベント数 </li> <li><i> 戻り値:</i>負の収益値を持つ購入イベントの数 </li> <li><i> 純収益:</i>すべての非返品の収益 </li> <li><i> 総収入:</i>返品の価値を含む収益 </li></ul>{:/} ![]({% image_buster /assets/img_archive/canvas_revenue_country.png %}){: style="max-width:70%;"} |
{: .reset-td-br-1 .reset-td-br-2 }

## メールテンプレート

| クエリ名 | 説明 | 
| --- | --- | 
| ドメインごとのメールのバウンス | メールドメインごとのバウンス数を、総バウンス数、ハードバウンス数、ソフトバウンス数に分けて示します。<br> ![]({% image_buster /assets/img_archive/query_builder_q4.png %}){: style="max-width:60%;"} |
| 日ごとのメール配信指標 | このレポートは、各日に送信されたメッセージのメトリクスを示しており、送信されたメールの数、配信されたメールの数、ソフトバウンスの数、ハードバウンスの数などが含まれています。<br><br> すべての指標は報告期間を通じて一意です。例えば、11月21日にウェルカムメールが1回ソフトバウンスし、11月22日に2回ソフトバウンスし、一度も配信されなかった場合: {::nomarkdown}<ul><li> 11月21日の<i>ソフトバウンス</i>メトリックが1つ増加します。</li><li> 11月22日の<i>ソフトバウンス</i>メトリックには影響がありません。</li></ul>{:/} ![]({% image_buster /assets/img_archive/email_delivery_day.png %})|
|  セグメント別のメールエンゲージメント指標 | このレポートは、各セグメントに送信されたメッセージのメトリクスを示しています。例えば、送信されたメールの数、配信されたメールの数、ソフトバウンスの数、ハードバウンスの数などです。<br><br> すべての指標は報告期間を通じて一意です。例えば、11月21日にウェルカムメールが1回ソフトバウンスし、11月22日に2回ソフトバウンスし、一度も配信されなかった場合: {::nomarkdown}<ul><li> 11月21日の<i>ソフトバウンス</i>メトリックが1つ増加します。</li><li> 11月22日の<i>ソフトバウンス</i>メトリックには影響がありません。</li></ul>{:/} ![]({% image_buster /assets/img_archive/email_engagement_segment.png %}) |
| セグメント別のバリアントまたはステップのメールエンゲージメント指標 | このレポートは、各セグメントに送信されたメッセージのバリアントまたはキャンバスステップのメトリクスを示しています。これらの指標には、送信されたメールの数、配信されたメールの数、ソフトバウンスしたメールの数、およびハードバウンスしたメールの数が含まれます。<br><br> すべての指標は報告期間を通じて一意です。例えば、11月21日にウェルカムメールが1回ソフトバウンスし、11月22日に2回ソフトバウンスし、一度も配信されなかった場合: {::nomarkdown}<ul><li> 11月21日の<i>ソフトバウンス</i>メトリックが1つ増加します。</li> <li> 11月22日の<i>ソフトバウンス</i>メトリックには影響がありません。</li></ul> {:/} |
| 国別のメールパフォーマンス | このレポートは、各国の送信数、間接開封率、および直接開封率のメトリクスを示しています。国はプッシュ送信時のユーザーの国です。<br><br> ![]({% image_buster /assets/img_archive/query_builder_q3.png %}) |
| メールサブスクリプション変更ログ | このレポートは、各ユーザーのサブスクリプション変更に関して記録されたメトリクスを示しています。例えば、メールアドレス、サブスクリプションステータス、ステータスが変更された時間、および関連するキャンバスまたはキャンペーンなどです。 |
| メールサブスクリプショングループのオプトインとオプトアウト | このレポートは、各週の任意のメールサブスクリプショングループに対するユニークなユーザーのオプトインおよびオプトアウトの数を示しています。<br><br> ![]({% image_buster /assets/img_archive/query_builder_q2.png %}){: style="max-width:70%;"} |
| メールURLクリック | このレポートは、メール内の各リンクのクリック数を示しています。このレポートを実行するには、キャンペーンまたはキャンバスの API 識別子を指定する必要があります。キャンペーンのAPI識別子は、そのキャンペーンの詳細ページの下部にあり、キャンバスAPI識別子は**Analyze Variants**の下にあります。<br><br> このレポートは、非パーソナライズされたリンクと各リンクのクリック数を示しています。CSVダウンロードには、クリックしたすべてのユーザーのユーザーID、クリックしたリンク、およびクリックした時刻のタイムスタンプが含まれます。<br><br> *パーソナライズされていないURL:*Liquidタグが削除されたURL。<br><br> ![]({% image_buster /assets/img_archive/query_builder_q5.png %}){: style="max-width:70%;"} |
| トップ/ボトムメッセージングによるメールエンゲージメント | このレポートは、トップまたはボトムのキャンペーン、キャンバス、またはキャンバスステップのメールエンゲージメント指標を示しています。トップまたはボトムのパフォーマーを表示するかどうか、およびこの分析を実行する特定の指標（*送信*、*ソフトバウンス*、*ユニークオープン*など）を指定する必要があります。<br><br> トップパフォーマーレポートの行は、最高から最悪の順に並べられ、ボトムパフォーマーレポートの行は、最悪から最高の順に並べられます。<br><br> ![]({% image_buster /assets/img_archive/top-bottom-email.png %}) |
{: .reset-td-br-1 .reset-td-br-2 }

## モバイルテンプレート

| クエリ名 | 説明 | 
| --- | --- | 
| デバイスキャリア | デバイスキャリアごとのユーザー数（VerizonやT-Mobileなど）。<br><br> ![]({% image_buster /assets/img_archive/device_carriers.png %}){: style="max-width:50%;"} |
| デバイスモデル | デバイスモデルごとのユーザー数、例えばiPhone 15 ProやPixel 7。<br><br> ![]({% image_buster /assets/img_archive/device_models.png %}){: style="max-width:50%;"} |
| デバイスのオペレーティングシステム | オペレーティングシステムごとのユーザー数（17.4やAndroid 14など）。<br><br> ![]({% image_buster /assets/img_archive/os_version.png %}){: style="max-width:50%;"} |
| デバイス画面解像度 | デバイス画面解像度ごとのユーザー数、例えば1179x2556や750x1334。<br><br> ![]({% image_buster /assets/img_archive/device_screen_resolutions.png %}){: style="max-width:40%;"} |
| SMSエラーコード | このレポートは、各SMSエラーコードのエラータイプとエラー数を示しています。<br><br>![]({% image_buster /assets/img_archive/sms_errors.png %}){: style="max-width:50%;"} |
| SMSユーザーによるエラーの提供 | このレポートは特定のユーザーのSMSエラーコードを表示します。 |
{: .reset-td-br-1 .reset-td-br-2 }

## テンプレートを押す

| クエリ名 | 説明 | 
| --- | --- | 
| 国ごとのパフォーマンスを押し上げる | このレポートは、各国の配信数、開封率、およびクリック率を示しています。国は、メール送信時のユーザーの国です。<br><br> ![]({% image_buster /assets/img_archive/query_builder_q7.png %}){: style="max-width:70%;"} |
{: .reset-td-br-1 .reset-td-br-2 }

## セグメントの内訳

| クエリ名 | 説明 |
| -- | -- |
| セグメント別のメールエンゲージメント指標 | このレポートは、キャンペーンまたはキャンバスレベルでセグメント別に分けられたメールのパフォーマンス指標を示しています。 |
| セグメント別の購入と収益 | このレポートは、特定のキャンペーンまたはキャンバスのセグメントごとに分類された購入および収益の指標を示しています。 |
| トップ/ボトムメッセージングによるメールエンゲージメント | このレポートは、指定されたメールエンゲージメント指標に対して最も高いまたは低いパフォーマンスを示したキャンペーン、キャンバス、またはキャンバスステップを示しています。|
| 購入のためのトップ/ボトムメッセージング | このレポートは、指定された購入または収益の指標に対して、最も高いまたは最も低いパフォーマンスを示したキャンペーン、キャンバス、またはキャンバスステップを示しています。 |
| セグメントごとのパフォーマンスを押し上げる | このレポートは、セグメントごとに分類されたプッシュメトリクスを示しています。|
{: .reset-td-br-1 .reset-td-br-2 }