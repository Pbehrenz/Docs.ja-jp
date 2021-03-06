---
uid: mvc/overview/releases/mvc51-release-notes
title: ASP.NET MVC 5.1 の新機能新機能 |Microsoft Docs
author: microsoft
description: ''
ms.author: aspnetcontent
ms.date: 02/27/2014
ms.assetid: 9a83a058-9b01-48aa-acce-ec041e694567
msc.legacyurl: /mvc/overview/releases/mvc51-release-notes
msc.type: authoredcontent
ms.openlocfilehash: d2e67f64e725e73c3bf9021295da3fe870079a45
ms.sourcegitcommit: b28cd0313af316c051c2ff8549865bff67f2fbb4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/05/2018
ms.locfileid: "37825649"
---
<a name="whats-new-in-aspnet-mvc-51"></a>ASP.NET MVC 5.1 の新機能新機能
====================
によって[Microsoft](https://github.com/microsoft)

このトピックでは、ASP.NET Web MVC 5.1 の新機能新機能について説明します。

- [ソフトウェアの要件](#SoftwareRequirements)
- [ダウンロード](#download)
- [ドキュメント](#documentation)
- [ASP.NET MVC 5.1 の新機能](#new-features)

    - [属性のルーティングが強化されました](#AttributeRouting)
    - [エディター テンプレートのブートス トラップのサポート](#Bootstrap)
    - [ビューでの列挙型のサポート](#Enum)
    - [控え目な検証 Minlength/maxlength 属性](#Unobtrusive)
    - [控えめな Ajax での 'this' コンテキストのサポート](#thisContext)
- [既知の問題と重大な変更](#KnownBreakingChanges)- [バグの修正](#bug-fixes)

<a id="SoftwareRequirements"></a>
## <a name="software-requirements"></a>ソフトウェア要件

- Visual Studio 2012: ダウンロード[ASP.NET および Web Tools 2013.1 for Visual Studio 2012](https://go.microsoft.com/fwlink/?LinkId=390062)します。
- Visual Studio 2013 の場合: ダウンロード[Visual Studio 2013 Update 1](https://go.microsoft.com/fwlink/?LinkId=390064)します。 ASP.NET MVC 5.1 の Razor ビューを編集するためには、この更新プログラムが必要です。

<a id="download"></a>
## <a name="download"></a>ダウンロード

ランタイムの機能は、NuGet ギャラリーでの NuGet パッケージとしてリリースされます。 次のすべてのランタイム パッケージ、[セマンティック バージョニング](http://semver.org/)仕様。 ASP.NET MVC 5.1 RTM の最新のパッケージは、次のバージョン:「5.1.2」。 インストールまたはを通じてこれらのパッケージを更新することができます[NuGet](http://www.nuget.org/packages/Microsoft.AspNet.Mvc/)します。 リリースには、NuGet での対応するローカライズされたパッケージも含まれています。

インストールまたは NuGet パッケージ マネージャー コンソールを使用して、リリースされた NuGet パッケージを更新できます。

[!code-console[Main](mvc51-release-notes/samples/sample1.cmd)]

<a id="documentation"></a>
## <a name="documentation"></a>ドキュメント

チュートリアルと ASP.NET MVC 5.1 RTM に関する他の情報は、ASP.NET web サイトから入手できます (https://www.asp.net)します。 

<a id="new-features"></a>
## <a name="new-features-in-aspnet-mvc-51"></a>ASP.NET MVC 5.1 の新機能

<a id="AttributeRouting"></a>

### <a name="attribute-routing-improvements"></a>属性のルーティングが強化されました

 ルートの選択を属性ルーティング現在のバージョン管理とヘッダーの有効化のサポートの制約に基づいています。 属性ルートの多くの側面が経由でカスタマイズ可能なようになりました、`IDirectRouteFactory`インターフェイスと`RouteFactoryAttribute`クラス。 ルート プレフィックスを使用して拡張が、`IRoutePrefix`インターフェイスと`RoutePrefixAttribute`クラス。 

<a id="Enum"></a>

### <a name="enum-support-in-views"></a>ビューでの列挙型のサポート

1. 新しい`@Html.EnumDropDownListFor()`ヘルパー メソッド。 式を評価する必要がありますに注意して HTML ヘルパーのほとんどのようにこれらを使用する必要があります、 [enum](https://msdn.microsoft.com/en-us/library/cc138362.aspx)型または[Nullable&lt;T&gt; ](https://msdn.microsoft.com/en-us/library/2cf62fcy.aspx)場所`T`は、[enum](https://msdn.microsoft.com/en-us/library/cc138362.aspx)型。 使用`EnumHelper.IsValidForEnumHelper()`をこれらの要件を確認します。
2. 新しい`EnumHelper.GetSelectList()`返すメソッドを`IList<SelectListItem>`します。 呼び出す、たとえば、前に、選択リストを操作する必要がある場合に便利ですが`@Html.DropDownListFor()`、名前を表示するとき、またはこれ`@Html.EnumDropDownListFor()`を示しています。

次のコードでは、これらの Api を示します。

[!code-cshtml[Main](mvc51-release-notes/samples/sample2.cshtml)]

完全な例を確認できます[ここ](https://aspnet.codeplex.com/SourceControl/latest#Samples/MVC/EnumSample/)します。

<a id="Bootstrap"></a>

### <a name="bootstrap-support-for-editor-templates"></a>エディター テンプレートのブートス トラップのサポート

HTML 属性に渡すことを許可しましたようになりました[EditorFor](https://msdn.microsoft.com/en-us/library/system.web.mvc.html.editorextensions.editorfor(v=vs.100).aspx)として、[匿名オブジェクト](https://msdn.microsoft.com/en-us/library/bb397696.aspx)します。

例えば:

[!code-cshtml[Main](mvc51-release-notes/samples/sample3.cshtml)]

<a id="Unobtrusive"></a>

### <a name="unobtrusive-validation-for-minlengthattribute-and-maxlengthattribute"></a>MinLengthAttribute と MaxLengthAttribute 控え目な検証

修飾されたプロパティの文字列および配列型のクライアント側の検証をサポートようになりましたが、 [MinLength](https://msdn.microsoft.com/en-us/library/system.componentmodel.dataannotations.minlengthattribute(v=vs.110).aspx)と[MaxLength](https://msdn.microsoft.com/en-us/library/system.componentmodel.dataannotations.maxlengthattribute(v=vs.110).aspx)属性。

<a id="thisContext"></a>

### <a name="supporting-the-this-context-in-unobtrusive-ajax"></a>控えめな Ajax での 'this' コンテキストのサポート

コールバック関数 (`OnBegin, OnComplete, OnFailure, OnSuccess`) を使用して呼び出し元の要素を見つけることになりますが、`this`コンテキスト。 例えば:

[!code-html[Main](mvc51-release-notes/samples/sample4.html)]

<a id="KnownBreakingChanges"></a>

## <a name="known-issues-and-breaking-changes"></a>既知の問題と重大な変更

### <a name="attribute-routing"></a>属性ルーティング

最初の一致を選択するのではなく、エラー、属性ルーティングの一致にあいまいさをレポートします。

属性ルートは、使用を禁止して、`{controller}`パラメーターを使用してと、`{action}`ルート パラメーターは、アクションに配置します。 これらのパラメーターの使用は、あいまいさをられる可能性が高くなります。 

### <a name="scaffolding-mvcweb-api-into-a-project-with-51-packages-results-in-50-packages-for-ones-that-dont-already-exist-in-the-project"></a>プロジェクトに 5.0 パッケージで 5.1 のパッケージの結果に MVC または Web API をプロジェクトに既に存在しないもののスキャフォールディング

ASP.NET MVC 5.1 RTM の NuGet パッケージを更新しても、ASP.NET スキャフォールディングなどの Visual Studio のツールや、ASP.NET Web アプリケーション プロジェクト テンプレートには更新されません。 ASP.NET ランタイム パッケージ (5.0.0.0) の以前のバージョンを使用します。 その結果、プロジェクトで使用されていない場合は、ASP.NET スキャフォールディングは、必要なパッケージの以前のバージョン (5.0.0.0) がインストールされます。 ただし、Visual Studio 2013 RTM や Update 1 での ASP.NET スキャフォールディングでは、プロジェクトで最新のパッケージは上書きされません。 Web API 2.1 または ASP.NET MVC 5.1 に、プロジェクトのパッケージを更新した後、ASP.NET スキャフォールディングを使用する場合は、Web API と ASP.NET MVC のバージョンでは、一貫性を確認します。 

### <a name="syntax-highlighting-for-razor-views-in-visual-studio-2013"></a>Visual Studio 2013 での Razor ビューの構文の強調表示

Visual Studio 2013 を更新することがなく、ASP.NET MVC 5.1 RTM に更新する場合は、Razor ビューの編集中に構文の強調表示の Visual Studio エディターのサポートを取得するはできません。 このサポートを受ける Visual Studio 2013 を更新する必要があります。 

### <a name="type-renames"></a>型名の変更

5.1 RTM でいくつか属性のルーティング拡張機能を使用する型の名前が変更されます。

| **以前の型名 (5.1 RC)** | **新しい型の名前 (5.1 RTM)** |
| --- | --- |
| IDirectRouteProvider | IDirectRouteFactory |
| RouteProviderAttribute | RouteFactoryAttribute |
| DirectRouteProviderContext | DirectRouteFactoryContext |

<a id="bug-fixes"></a>
## <a name="bug-fixes"></a>バグ修正

このリリースには、いくつかのバグ修正も含まれています。 完全な一覧をここにあります。

- [5.1.0 パッケージ](https://aspnetwebstack.codeplex.com/workitem/list/advanced?keyword=&amp;status=Closed&amp;type=All&amp;priority=All&amp;release=v5.1%20Preview|v5.1%20RTM&amp;assignedTo=All&amp;component=MVC&amp;sortField=AssignedTo&amp;sortDirection=Ascending&amp;page=0&amp;reasonClosed=Fixed)
- [5.1.1 パッケージ](https://aspnetwebstack.codeplex.com/workitem/list/advanced?keyword=&amp;status=All&amp;type=All&amp;priority=All&amp;release=v5.1.1%20RTM&amp;assignedTo=All&amp;component=MVC&amp;sortField=AssignedTo&amp;sortDirection=Ascending&amp;page=0&amp;reasonClosed=Fixed)

5.1.2、パッケージには、IntelliSense の更新プログラムがないバグの修正が含まれています。
