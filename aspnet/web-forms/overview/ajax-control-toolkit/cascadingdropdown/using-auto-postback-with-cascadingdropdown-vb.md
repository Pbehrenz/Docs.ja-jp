---
uid: web-forms/overview/ajax-control-toolkit/cascadingdropdown/using-auto-postback-with-cascadingdropdown-vb
title: 自動ポストバックを使用する (VB) |Microsoft Docs
author: wenz
description: CascadingDropDown コントロール、AJAX Control Toolkit では、anoth 内の値が 1 つの DropDownList の読み込みの変更に関連付けられているように DropDownList コントロールを拡張しています.
ms.author: aspnetcontent
ms.date: 06/02/2008
ms.assetid: 0b34f7f6-a0cc-4b9f-9761-643fb0bb3ece
msc.legacyurl: /web-forms/overview/ajax-control-toolkit/cascadingdropdown/using-auto-postback-with-cascadingdropdown-vb
msc.type: authoredcontent
ms.openlocfilehash: f0ed4c88789504c09649254ea98a89b01bdd20c5
ms.sourcegitcommit: b28cd0313af316c051c2ff8549865bff67f2fbb4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/05/2018
ms.locfileid: "37813842"
---
<a name="using-auto-postback-with-cascadingdropdown-vb"></a>自動ポストバックを使用する (VB)
====================
によって[Christian Wenz](https://github.com/wenz)

[コードのダウンロード](http://download.microsoft.com/download/9/0/7/907760b1-2c60-4f81-aeb6-ca416a573b0d/cascadingdropdown3.vb.zip)または[PDF のダウンロード](http://download.microsoft.com/download/2/d/c/2dc10e34-6983-41d4-9c08-f78f5387d32b/cascadingdropdown3VB.pdf)

> CascadingDropDown コントロール、AJAX Control Toolkit では、もう 1 つの DropDownList の値が 1 つの DropDownList の読み込みの変更に関連付けられているように、DropDownList コントロールを拡張します。 ただし、ASP CascadingDropDown コントロールを使用する場合。NET の DropDownList コントロール AutoPostBack 機能が機能しませんので、リストにデータを非同期的に読み込む自体 (不要な)、ポストバックを生成します。 いくつかの JavaScript コードでは、この影響を回避できます。


## <a name="overview"></a>概要

CascadingDropDown コントロール、AJAX Control Toolkit では、もう 1 つの DropDownList の値が 1 つの DropDownList の読み込みの変更に関連付けられているように、DropDownList コントロールを拡張します。 (たとえば、1 つのリストは、私たちの状態の一覧を提供します。 し、[次へ] の一覧は、その状態の主な都市で埋められます)。ただし、ASP CascadingDropDown コントロールを使用する場合。NET の DropDownList コントロール AutoPostBack 機能が機能しませんので、リストにデータを非同期的に読み込む自体 (不要な)、ポストバックを生成します。 いくつかの JavaScript コードでは、この影響を回避できます。

## <a name="steps"></a>手順

ASP.NET AJAX Control Toolkit の機能をアクティブ化するために、`ScriptManager`コントロールは、ページのどこでも配置する必要があります (ただし内、 &lt; `form` &gt;要素)。

[!code-aspx[Main](using-auto-postback-with-cascadingdropdown-vb/samples/sample1.aspx)]

次に、DropDownList コントロールが必要です。

[!code-aspx[Main](using-auto-postback-with-cascadingdropdown-vb/samples/sample2.aspx)]

このリストの CascadingDropDown エクステンダーが追加になり、web サービスの URL とメソッドの情報を提供します。

[!code-aspx[Main](using-auto-postback-with-cascadingdropdown-vb/samples/sample3.aspx)]

CascadingDropDown エクステンダー非同期的に呼び出して、次のメソッド シグネチャを持つ web サービス。

[!code-vb[Main](using-auto-postback-with-cascadingdropdown-vb/samples/sample4.vb)]

CascadingDropDown 値の型の配列を返します。 リスト項目のキャプションとし、値型のコンス トラクターが最初に必要です (HTML`value`属性)。

[!code-aspx[Main](using-auto-postback-with-cascadingdropdown-vb/samples/sample5.aspx)]

ブラウザーでページの読み込みが挿入されますをドロップダウン リストに 3 つのベンダーでは、あらかじめ選択されている 2 つ目。 また、ASP.NET の定義、 `__doPostBack()` JavaScript メソッド。 ページが読み込まれると、この JavaScript 呼び出しはのみにある場合の要素には、ドロップダウン リストに追加されます。 場合は、リスト内の要素がない、Control Toolkit が現在読み込んでいる、ため、JavaScript コードは、タイムアウトを使用し、0.5 秒後にもう一度試みます。

[!code-html[Main](using-auto-postback-with-cascadingdropdown-vb/samples/sample6.html)]

この方法では、ポストバックは、リスト内に実際に要素が、ユーザーがエントリを選択してにのみ実行されます。


[![ポストバックを発生させるリスト要素の選択](using-auto-postback-with-cascadingdropdown-vb/_static/image2.png)](using-auto-postback-with-cascadingdropdown-vb/_static/image1.png)

リスト要素を選択すると、ポストバックを発生させる ([フルサイズの画像を表示する をクリックします](using-auto-postback-with-cascadingdropdown-vb/_static/image3.png))。

> [!div class="step-by-step"]
> [前へ](presetting-list-entries-with-cascadingdropdown-vb.md)
