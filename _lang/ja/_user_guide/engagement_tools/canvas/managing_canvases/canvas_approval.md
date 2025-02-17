---
nav_title: キャンバスの承認と権限
article_title: キャンバスの承認と権限 
page_order: 0.5
alias: "/canvas_approval/"
description: "この参考記事では、開始前にキャンバスを承認する方法と、関連するユーザー権限について説明します。"
tool: Canvas
---

# キャンバスの承認と権限

> キャンバスを承認することで、開始前のワークフローにレビュープロセスが追加されます。これにより、キャンバスを起動するために、それぞれの確認がアプリ確認されていることを確認できます。

## キャンバスの承認をオンにする

キャンバスの承認ワークフローをオンにするには、**\[ワークプレースの設定**] の \[**設定]**>\[**承認ワークフロー**] を選択します。デフォルトでは、この機能はオフになっています。

![アプリ範囲のワークフロー設定sでは、アプリ範囲のワークフローをキャンペーンとキャンバスに使用できます。][1]

{% alert tip %}
キャンバスを承認する適切な[ユーザー権限]({{site.baseurl}}/user_guide/administrative/app_settings/manage_your_braze_users/user_permissions/#managing-limited-and-team-role-permissions)を持っていることを確認してください。
{% endalert %}

### ユーザー権限の設定

キャンバスの承認ワークフローをオンにし 、 ［**設定**］>\[**会社ユーザー**］ で \[**キャンバスを承認および却下**］ を選択すると、特定のユーザーがキャンバスをすぐに承認・却下できます。この権限は、ワークスペースや[チーム]({{site.baseurl}}/user_guide/administrative/app_settings/manage_your_braze_users/teams/)に適用することも、[権限セット]({{site.baseurl}}/user_guide/administrative/app_settings/manage_your_braze_users/user_permissions/#permission-sets)に追加することもできます。

この権限を持つユーザは、キャンバスワークフローで次のいずれかの操作を実行できます。
- キャンバスを承認するが起動しない
- キャンバスをアプリローブするのではなくローンチする
- キャンバスの承認と起動
- アプリがキャンバスをローブしたり、ローンチしたりしない

![たとえば、アプリローブとキャンバス拒否権限のチェックボックスが選択されていない場合、このユーザーには権限 アプリローブやキャンバス拒否はありません。][3]{: style="max-width:70%" }

{% alert important %}
ライブキャンペーンを編集するには、「キャンペーンを承認および却下」権限が必要です。キャンペーンの下書きバージョンがまだ提供されていないため、ユーザーは変更を承認する必要があります。キャンバスの場合はこの限りではなく、ユーザーが変更を加えて下書きとして保存し、別のユーザーがキャンバスを承認して開始できます。
{% endalert %}

## 承認を使用する

「キャンバスを承認および却下」権限を持っている場合は、キャンバスビルダーの**概要**ステップにアクセスできます。このページでは、コンバージョンイベント、エントリスケジュール、キャンバス内のコンポーネントの種類と数量など、キャンバスの主な詳細を承認または却下するオプションがあります。キャンバス承認のデフォルトの状態は「**承認待ち**」であることに注意してください。

\[**概要**] ステップで承認ステータスを設定し、その後キャンバスに変更を加えると、保存時にすべての承認ステータスがリセットされます。これは、下書きキャンバスと開始後のキャンバスのいずれで行われた変更にも適用されます。例えば、ターゲットオーディエンスのみに変更を加えた場合、**要約**ステップでは、すべてのセクションの承認ステータスがデフォルトの状態 (承認待ち) に戻ります。

![たとえば、コンバージョンイベントとエントリースケジュールの詳細がアプリで確認済みとしてマークされているキャンバスアプリの承認ワークフローがあります。][2]{: style="max-width:85%" }

各セクションが承認されると、\[**開始**] ボタンが使用可能になり、キャンバスを開始できます。

[1]: {% image_buster /assets/img_archive/canvas_approval.png %}
[2]: {% image_buster /assets/img_archive/canvas_approval_summary.png %}
[3]: {% image_buster /assets/img_archive/canvas_approval_user_permissions.png %}