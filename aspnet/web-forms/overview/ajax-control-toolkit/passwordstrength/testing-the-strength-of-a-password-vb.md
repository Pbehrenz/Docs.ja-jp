---
uid: web-forms/overview/ajax-control-toolkit/passwordstrength/testing-the-strength-of-a-password-vb
title: (VB) のパスワードの強度をテスト |Microsoft Docs
author: wenz
description: パスワードが限定的なユーザーが簡単に解読される単純なパスワードを選択する傾向があるように、ほぼどこにでも必要です。 ASP で PasswordStrength コントロール。N..
ms.author: aspnetcontent
ms.date: 06/02/2008
ms.assetid: 9215a37f-3133-4887-8ed2-3689f3a53551
msc.legacyurl: /web-forms/overview/ajax-control-toolkit/passwordstrength/testing-the-strength-of-a-password-vb
msc.type: authoredcontent
ms.openlocfilehash: 7073a06186ba3ff6c6a12d558445d75d9301589a
ms.sourcegitcommit: b28cd0313af316c051c2ff8549865bff67f2fbb4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/05/2018
ms.locfileid: "37805902"
---
<a name="testing-the-strength-of-a-password-vb"></a>(VB) のパスワードの強度をテスト
====================
によって[Christian Wenz](https://github.com/wenz)

[コードのダウンロード](http://download.microsoft.com/download/9/3/f/93f8daea-bebd-4821-833b-95205389c7d0/PasswordStrength0.vb.zip)または[PDF のダウンロード](http://download.microsoft.com/download/2/d/c/2dc10e34-6983-41d4-9c08-f78f5387d32b/passwordstrength0VB.pdf)

> パスワードが限定的なユーザーが簡単に解読される単純なパスワードを選択する傾向があるように、ほぼどこにでも必要です。 PasswordStrength コントロール、ASP.NET AJAX Control Toolkit では、パスワードは、どの程度適切かを確認できます。


## <a name="overview"></a>概要

パスワードが限定的なユーザーが簡単に解読される単純なパスワードを選択する傾向があるように、ほぼどこにでも必要です。 `PasswordStrength` ASP.NET AJAX Control Toolkit でコントロールをどの程度適切かパスワードが確認できます。

## <a name="steps"></a>手順

`PasswordStrength`コントロールがテキスト ボックスを拡張し、パスワードで十分かどうかを確認します。 豊富な属性を使用してオプションを提供していますそれらのほんの一部を次に示します。

- `MinimumNumericCharacters` パスワードに必要な数字の最小数
- `MinimumSymbolCharacters` パスワードに必要な記号文字 (文字と数字ではない) の最小数
- `PreferredPasswordLength` パスワードの最小の長さ
- `RequiresUpperAndLowerCaseCharacters` かどうか、パスワードは、大文字と小文字の両方の文字を使用する必要があります。

`StrengthIndicatorType`にテキストとして、パスワードの強度を表示する方法の情報を提供します (値`"Text"`) または進行状況バーの一種として (値`"BarIndicator"`)。 `DisplayPosition`情報が表示される場所を構成する属性。 ASP.NET AJAX を含む、完全な例を次に示します`ScriptManager`コントロール、`PasswordStrength`コントロールとテキスト ボックス、ユーザーがパスワードを入力できます。 デモンストレーションのため、後者フォーム フィールドは通常のテキスト フィールドと [パスワード] フィールドではない入力内容を開発中に表示できるようにします。

[!code-aspx[Main](testing-the-strength-of-a-password-vb/samples/sample1.aspx)]

ページを実行し、離れた入力: のみ、小文字、大文字、数字および記号を入力したら、パスワードは、unbreakable と判断します。


[![パスワードが (かなり) 良いようになりました](testing-the-strength-of-a-password-vb/_static/image2.png)](testing-the-strength-of-a-password-vb/_static/image1.png)

パスワードは (かなり) 良い ([フルサイズの画像を表示する をクリックします](testing-the-strength-of-a-password-vb/_static/image3.png))。

> [!div class="step-by-step"]
> [前へ](testing-the-strength-of-a-password-cs.md)
