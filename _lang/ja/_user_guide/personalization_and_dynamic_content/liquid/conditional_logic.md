---
nav_title: 条件付きメッセージング・ロジック
article_title: 条件付きリキッドメッセージ・ロジック
page_order: 6
description: "この参考記事では、キャンペーンでタグをどのように使用できるか、また使用すべきかについて解説している。"

---

# 条件付きメッセージング・ロジック

> \[タグ][7] を使えば、メッセージング・キャンペーンにプログラミング・ロジックを含めることができる。タグは、条件文の実行だけでなく、変数の代入やコードブロックの反復のような高度なユースケースにも使うことができる。

{% raw %}
タグは`{% %}` で囲む必要がある。
{% endraw %}

{% alert tip %}
あなたの生活を少し楽にするために、Brazeはリキッド構文を正しくフォーマットした場合、緑と紫で起動するカラーフォーマットを搭載している。緑色の書式はタグを識別するのに役立ち、紫色の書式はパーソナライズされた部分を強調する。
<br><br>
もし条件付きメッセージングを使うのに苦労しているなら、カスタム属性や他のリキッド要素を挿入する前に、条件構文を書き出してみてほしい。
<br><br>
例えば、まずメッセージ・フィールドに以下を追加する：  
{% raw %}
```liquid
{% if X >0 %}
{% else %}
{% endif %}
```

緑色でハイライトされていることを確認し、`X` を選択したリキッドまたはコネクテッド・コンテンツに置き換え、メッセージ・フィールドの隅にある青色の`+` を使用し、`0` を希望する値に置き換える。
<br><br>
そして、`else` の条件文の間に、必要に応じてメッセージのバリエーションを追加する：
```liquid
{% if {{custom_attribute.${total_spend}}} >0 %}
Thanks for purchasing! Here's another 10% off!
{% else %}
Buy now! Would 5% off convince you?
{% endif %}
```
{% endraw %}
{% endalert %}

## 条件論理

][1] 、条件文のような多くのタイプの\[インテリジェント・ロジック]をメッセージに含めることができる。キャンペーンを国際化するために\[conditionals][8] ]を使用した次の例を参照のこと：
{% raw %}

```liquid
{% if ${language} == 'en' %}
This is a message in English from Braze!
{% elsif ${language} == 'es' %}
Este es un mensaje en español de Braze !
{% elsif ${language} == 'zh' %}
这是一条来自Braze的中文消息。
{% else %}
This is a message from Braze! This is going to go to anyone who did not match the other specified languages!
{% endif %}
```

### ステップ・バイ・ステップの例

この例では、"if"、"elsif"、"else "ステートメントを持つタグを使って、国際化されたコンテンツを配信している。

```liquid
{% if ${language} == 'en' %}
This is a message in English from Braze!
```
顧客の言語が英語の場合、最初の条件が満たされ、顧客は英語のメッセージを受け取る。

```liquid
{% elsif ${language} == 'es' %}
Este es un mensaje en español de Braze !
{% elsif ${language} == 'zh' %}
这是一条来自Braze的中文消息。
```

条件文はいくつでも指定できる。前の条件が満たされない場合、次の条件がチェックされる。この例では、顧客のデバイスが英語に設定されていない場合、このコードは顧客のデバイスがスペイン語または中国語に設定されているかどうかを確認する。顧客のデバイスがこれらの条件のいずれかに当てはまる場合、顧客は該当する言語でメッセージを受け取る。

```liquid
{% else %}
This is a message from Braze! This is going to go to anyone who did not match the other specified languages!
```

条件ロジックに`{% else %}` 。設定した条件のどれにも当てはまらない場合、`{% else %}` ステートメントで送信すべきメッセージを指定する。この場合、顧客の言語が英語、スペイン語、中国語でない場合、デフォルトは英語になる。

```liquid
{% endif %}
```

`{% endif %}` 、条件ロジックが終了したことを知らせる。を含めなければならない。
`{% endif %}`  タグを、条件付きロジックを持つメッセージに使用する。条件ロジックに`{% endif %}` タグを含めないと、Brazeがメッセージを解析できず、エラーになる。

{% endraw %}

## null、nil、および空白の属性値を処理する

条件ロジックは、ユーザープロファイルに設定されていない属性値を考慮するのに便利な方法である。

### NULL および NIL 属性値

nullまたはnil値は、カスタム属性の値が設定されていない場合に発生する。例えば、まだファーストネームを設定していないユーザーは、Brazeにファーストネームが記録されない。

状況によっては、ファーストネームを設定しているユーザーと設定していないユーザーとで、まったく異なるメッセージを送りたい場合もあるだろう。

以下のタグは、"first name "属性がNULLのユーザーに対するメッセージを指定することができる：

{% raw %}
```liquid
{% if ${first_name} == null %}
  ....
{% endif %}
```
{% endraw %} 

![][36]{: style="max-width:60%;"}

{% raw %}
```liquid
{% if ${first_name} == null %}
We're having a sale! Hurry up and get 10% off all items today only!
{% else %}
Hey {{${first_name} | default: 'there'}}, we're having a sale! Hurry up and get 10% off all items today only!
{% endif %}
```

したがって、上の例では、null属性値は設定されていないファーストネームを参照していることになる。

{% endraw %}

### 空白の属性値

空白の値は、ユーザープロファイルの属性が設定されていないか、空白文字列（` ` ）が設定されているか、`false` として設定されている場合に発生する。リキッド処理エラーを避けるため、ブランク値は他の変数より先にチェックすべきである。

以下のタグは、"first name "属性が空白のユーザーに対するメッセージを指定することができる。

{% raw %}
```liquid
{% if ${first_name} == blank %}
  ....
{% endif %}
```
{% endraw %} 

## カスタム属性を参照する

カスタム属性を作成\[][2]]したら、リキッドメッセージングでこれらのカスタム属性を参照できる。

条件付きロジックを使用する場合、正しい構文を使用していることを確認するために、カスタム属性のデータ型を知っておく必要がある。ダッシュボードの**カスタム属性**ページから、カスタム属性に関連するデータタイプを探し、各データタイプに記載されている以下の例を参照する。

![カスタム属性のデータ型を選択する。この例では、Favorite_Category属性のデータ型が文字列であることを示している。][20]{: style="max-width:80%;"}

{% alert tip %}
文字列と配列にはアポストロフィが必要だが、ブーリアンと整数にはアポストロフィはない。
{% endalert %}

#### ブール値

`registration_complete: true`[][9] はバイナリ値であり、`true` または`false` のいずれかに設定することができる。ブール値にはアポストロフィは付かない。

{% raw %}

```liquid
{% if {{custom_attribute.${registration_complete}}} == true %}
```

{% endraw %}

#### 数値

\[][10] は数値であり、整数または浮動小数点数である。例えば、ユーザーは`shoe_size: 10` や`levels_completed: 287` を持っているかもしれない。数値にはアポストロフィは付かない。

{% raw %}

```liquid
{% if {{custom_attribute.${shoe_size}}} == 10 %}
```

{% endraw %}

また、整数に対しては、小なり（<）や大なり（>）といった[基本的な演算子も](https://shopify.dev/docs/themes/liquid/reference/basics/operators)使える：

{% raw %}

```liquid
{% if {{custom_attribute.${flyer_miles}}} >= 500 %}
```

{% endraw %}

#### string

文字列][11] は英数字で構成され、ユーザーに関するデータの一部を保存する。例えば、`favorite_color: red` または`phone_number: 3025981329` 。文字列の値にはアポストロフィをつけなければならない。

{% raw %}

```liquid
{% if {{custom_attribute.${favorite_color}}} == 'blue' %}
```

{% endraw %}

文字列の場合、Liquidでは"=="と "contains "の両方を使うことができる。

#### 配列

配列][12] は、ユーザーに関する情報のリストである。例えば、ユーザーは`last_viewed_shows: stranger things, planet earth, westworld` を持っているかもしれない。配列の値はアポストロフィで囲む必要がある。

{% raw %}

```liquid
{% if {{custom_attribute.${last_viewed_shows}}} contains 'homeland' %}
```

{% endraw %}

配列の場合、"contains "を使わなければならず、"=="は使えない。 

#### 時刻

イベントが発生した時刻を示すタイムスタンプ。条件ロジックで使用するには、\[Time][13] value must have a \[math filter][5] on them.

{% raw %}

```liquid
{% assign expire = {{custom_attribute.${subscription_end_date}}} | plus: 0 %} 
```

{% endraw %}


[36]:{% image_buster /assets/img/value_null.png %}
[1]: http://docs.shopify.com/themes/liquid-documentation/basics
[2]: {{site.baseurl}}/user_guide/data_and_analytics/custom_data/custom_attributes/#managing-custom-attributes
[5]: {{site.baseurl}}/user_guide/personalization_and_dynamic_content/liquid/filters/#math-filters
[7]: https://docs.shopify.com/themes/liquid-documentation/tags
[8]: http://docs.shopify.com/themes/liquid-documentation/tags/control-flow-tags 「コントロール・フロー・タグ
[9]: {{site.baseurl}}/user_guide/data_and_analytics/custom_data/custom_attributes/#booleans
[10]: {{site.baseurl}}/user_guide/data_and_analytics/custom_data/custom_attributes/#numbers
[11]: {{site.baseurl}}/user_guide/data_and_analytics/custom_data/custom_attributes/#strings
[12]: {{site.baseurl}}/user_guide/data_and_analytics/custom_data/custom_attributes/#arrays
[13]: {{site.baseurl}}/user_guide/data_and_analytics/custom_data/custom_attributes/#time
[20]: {% image_buster /assets/img_archive/custom_attribute_data_type.png %}
