---
title: 使用 Microsoft 搜尋來尋找 Microsoft Viva 主題中的主題
ms.author: efrene
author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
localization_priority: None
description: 瞭解您可以在 Microsoft Viva 中搜尋主題的方式。
ms.openlocfilehash: 54a143ea0960bf56a0d1c5224658bea404c7621e
ms.sourcegitcommit: 58d74ff60303a879e35d112f10f79724ba41188f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/10/2021
ms.locfileid: "52301713"
---
# <a name="use-microsoft-search-to-find-topics-in-microsoft-viva-topics"></a>使用 Microsoft 搜尋來尋找 Microsoft Viva 主題中的主題

雖然 Viva 主題，使用者可以在其 SharePoint 網站中找到主題強調主題，也可以透過 Microsoft 搜尋找到這些主題。 

## <a name="topic-answer"></a>主題答案

當您在 Microsoft 搜尋 (中搜尋特定主題時（例如，"Saturn" ) ），如果有主題存在且找到該主題，則會以答案建議格式顯示結果。

主題答案會顯示：
- 主題名稱
- 替代名稱：主題的替代名稱或縮寫。
- 定義：由 AI 提供或人員手動新增的主題描述。
- 建議或已鎖定的人員：透過 AI 建議或由人員固定至主題的人員
- 建議或固定的資源：透過 AI 建議的檔案、頁面或網站，或由人員固定至主題。 

   ![搜尋中的主題](../media/knowledge-management/search-topic-answer.png) 

即使主題的答案卡未出現，也可以在搜尋結果中顯示 [主題] 頁面。

Word、PowerPoint Outlook 和 Excel 中的搜尋結果也會在找到一個主題時顯示主題答案。


## <a name="acronyms"></a>縮略字

在 Viva 主題中，您可以手動編輯主題，以包含其為 <b>替代名稱</b>的縮寫。 這可讓僅以該主題的首字母縮寫的使用者進行搜尋，以找出透過 Microsoft 搜尋的主題答案。

[縮寫的答案](/microsoftsearch/manage-acronyms) 是 Microsoft Search 所提供的功能，且與 Viva 主題分開管理。

## <a name="bookmarks-and-topics"></a>書簽和主題

[書簽](/microsoftsearch/manage-bookmarks)是 Microsoft 搜尋功能，可協助使用者快速尋找重要的網站及工具，只附帶搜尋 (例如，外部網站上的旅行預約工具會在其 Microsoft 365 承租人) 以外。 它們是由「Microsoft 365 系統管理中心」的搜尋管理員所建立。 

若要尋找可預約工作旅行之相關資訊的使用者：

- 如果有些使用者知道旅行工具名稱 (例如 "Concur" ) ，則建立書簽直接移至外部網站會比較容易。
- 針對一般搜尋「旅行」的使用者，在「旅行」上建立一個主題，該主題具有期望看到的資訊。 請考慮在主題的描述中新增 Concur 外部網站的連結。 如果連結改改為 Microsoft 365 租使用者所主控的內部旅行預約網站，您可以將其新增至「釘住的資源」。
 
### <a name="search-results-priority"></a>搜尋結果優先順序 
 
在使用者搜尋體驗中，當使用者搜尋類似「旅行」的字詞時，搜尋結果將會以 Microsoft 搜尋中的下列優先順序顯示。
1. 已發佈或已確認的主題 
2. 書籤
3. 建議的主題
