---
title: ASP.NET Core アプリで生成済みページを更新する
author: rick-anderson
description: ASP.NET Core アプリで生成済みページを更新する方法について説明します。
monikerRange: '>= aspnetcore-2.0'
ms.author: riande
ms.date: 05/30/2018
uid: tutorials/razor-pages/da1
ms.openlocfilehash: 55ff98712da314e28e50a1b1b1e04530d5b3fedd
ms.sourcegitcommit: b8a2f14bf8dd346d7592977642b610bbcb0b0757
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2018
ms.locfileid: "38186232"
---
# <a name="update-the-generated-pages-in-an-aspnet-core-app"></a>ASP.NET Core アプリで生成済みページを更新する

作成者: [Rick Anderson](https://twitter.com/RickAndMSFT)

ムービー アプリは上々の滑り出しでしたが、表示が理想的ではありません。 時刻の表示が好ましくなく (下の画像の 12:00:00 AM)、**ReleaseDate** は **Release Date** (2 つの単語) にするべきです。

![ムービー データが表示された、Chrome で開かれているムービー アプリケーション](sql/_static/m55.png)

## <a name="update-the-generated-code"></a>生成されたコードの更新

*Models/Movie.cs* ファイルを開き、下のコードで強調表示されている行を追加します。

::: moniker range="= aspnetcore-2.0"
[!code-csharp[](~/tutorials/razor-pages/razor-pages-start/sample/RazorPagesMovie/Models/MovieDate.cs?name=snippet_1&highlight=10-11)]
::: moniker-end

::: moniker range=">= aspnetcore-2.1"
[!code-csharp[](~/tutorials/razor-pages/razor-pages-start/sample/RazorPagesMovie21/Models/MovieDate.cs?name=snippet_1&highlight=10-11,15)]
::: moniker-end

赤の波線を右クリックし、**[クイック アクションとリファクタリング]** を選択します。

  ![コンテキスト メニューに **[クイック アクションとリファクタリング]** が表示されます。](da1/qa.png)

`using System.ComponentModel.DataAnnotations;` を選択します。

  ![一覧の一番上にある System.ComponentModel.DataAnnotations を使用する](da1/da.png)

  Visual Studio により `using System.ComponentModel.DataAnnotations;` が追加されます。

[!INCLUDE [model1](~/includes/RP/da2.md)]

> [!div class="step-by-step"]
> [前: SQL Server LocalDB の使用](xref:tutorials/razor-pages/sql)
> [検索の追加](xref:tutorials/razor-pages/search)
