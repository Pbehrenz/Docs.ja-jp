---
uid: web-forms/overview/ajax-control-toolkit/mutuallyexclusivecheckbox/creating-mutually-exclusive-checkboxes-vb
title: 相互に排他的なチェック ボックス (VB) を作成する |Microsoft Docs
author: wenz
description: '一連のオプションの 1 つだけが選択されるときに、オプション ボタンが通常使用されます。 ただし、欠点がある: グループ内の 1 つのオプション ボタンを選択すると、.'
ms.author: aspnetcontent
ms.date: 06/02/2008
ms.assetid: e9dd1d5a-a1db-4114-981d-6a91acb1d709
msc.legacyurl: /web-forms/overview/ajax-control-toolkit/mutuallyexclusivecheckbox/creating-mutually-exclusive-checkboxes-vb
msc.type: authoredcontent
ms.openlocfilehash: 6badd005ed4775cb248784f3e9991132db1b3969
ms.sourcegitcommit: b28cd0313af316c051c2ff8549865bff67f2fbb4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/05/2018
ms.locfileid: "37828800"
---
<a name="creating-mutually-exclusive-checkboxes-vb"></a>相互に排他的なチェック ボックス (VB) を作成します。
====================
によって[Christian Wenz](https://github.com/wenz)

[コードのダウンロード](http://download.microsoft.com/download/9/3/f/93f8daea-bebd-4821-833b-95205389c7d0/MutuallyExclusiveCheckBox0.vb.zip)または[PDF のダウンロード](http://download.microsoft.com/download/b/6/a/b6ae89ee-df69-4c87-9bfb-ad1eb2b23373/mutuallyexclusivecheckbox0VB.pdf)

> 一連のオプションの 1 つだけが選択されるときに、オプション ボタンが通常使用されます。 ただし、欠点がある: グループ内の 1 つのオプション ボタンを選択すると後、は、すべてのオプション ボタンをオフにすることはできません。 チェック ボックスは、ただし相互に排他的ではありません、いつでもチェックできます。 このチュートリアルでは、両方のアプローチの最適な: チェック ボックスは相互に排他的です。


## <a name="overview"></a>概要

一連のオプションの 1 つだけが選択されるときに、オプション ボタンが通常使用されます。 ただし、欠点がある: グループ内の 1 つのオプション ボタンを選択すると後、は、すべてのオプション ボタンをオフにすることはできません。 チェック ボックスは、ただし相互に排他的ではありません、いつでもチェックできます。 このチュートリアルでは、両方のアプローチの最適な: チェック ボックスは相互に排他的です。

## <a name="steps"></a>手順

ASP.NET AJAX Control Toolkit には、MutuallyExclusiveCheckBox エクステンダーが含まれています。 これにより、プログラマはグループ名にすべてのチェック ボックスを割り当てる (`Key`属性)。 同じグループ内のすべてのチェック ボックスは、1 つだけを一度に選択できます。

新しい ASP.NET ページに 2 つのチェック ボックスを配置することから始めましょう。 以上、存在することができますが、原則を示すためにそのうち 2 つで十分です。

[!code-aspx[Main](creating-mutually-exclusive-checkboxes-vb/samples/sample1.aspx)]

両方のチェック ボックスのページに MutuallyExclusiveCheckBoxExtender コントロールを配置する必要があります。 両方のキー属性は、HTML ラジオ ボタンの要素の属性は、所属するグループを示すのと同じである必要があります値と同様、同じ値を指定する必要があります。 エクステンダーの TargetControlID プロパティは、チェック ボックスの ID を指します。

[!code-aspx[Main](creating-mutually-exclusive-checkboxes-vb/samples/sample2.aspx)]

最後に、ASP.NET AJAX を含める`ScriptManager`ASP.NET AJAX Control Toolkit のすべての要素で必要です。

[!code-aspx[Main](creating-mutually-exclusive-checkboxes-vb/samples/sample3.aspx)]

保存し、ページの実行: を確認し、両方のチェック ボックスをオフにします。 ただしない時に両方のチェック ボックス チェックできます。


[![一度に 1 つだけのチェック ボックスをオンすることができます。](creating-mutually-exclusive-checkboxes-vb/_static/image2.png)](creating-mutually-exclusive-checkboxes-vb/_static/image1.png)

一度に 1 つだけのチェック ボックスをオンすることができます ([フルサイズの画像を表示する をクリックします](creating-mutually-exclusive-checkboxes-vb/_static/image3.png))。

> [!div class="step-by-step"]
> [前へ](creating-mutually-exclusive-checkboxes-cs.md)
