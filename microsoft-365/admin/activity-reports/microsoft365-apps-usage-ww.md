---
title: Admin center 中的 microsoft 365 報告-Microsoft 365 應用程式使用量
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
description: 瞭解如何使用 microsoft 365 系統管理中心的 [Microsoft 365 報告] 儀表板，取得 Microsoft 365 應用程式的使用方式報告。
ms.openlocfilehash: d41a1680b46709c3f41b5238d309794c68101cee
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2021
ms.locfileid: "51860746"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-365-apps-usage"></a>Admin center 中的 microsoft 365 報告-Microsoft 365 應用程式使用量

Microsoft 365 **報告** 儀表板會向您顯示組織中各產品的活動概況。 此功能可讓您深入了解個別產品層級報表，更加深入解析各產品內的活動。 請參閱[報告概觀主題](activity-reports.md)。

 例如，您可以查看使用者在應用程式中的活動，以及如何在平臺上使用這些應用程式，來瞭解每個使用者授權使用 Microsoft 365 App 應用程式的活動。


 > [!NOTE]
 > 您必須是 Microsoft 365 或 Exchange、SharePoint 或商務用 Skype 系統管理員的全域系統管理員、全域讀取器或報告讀取器，才能查看報告。 這份報告中並未包含共用電腦啟用。

## <a name="how-to-get-to-the-microsoft-365-apps-usage-report"></a>如何取得 Microsoft 365 應用程式使用方式報告

1. 在系統管理中心中，移至 **[報告]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">[使用量]</a> 頁面。 
2. 在 [儀表板] 主頁上，按一下 [作用中使用者]-Microsoft 365 App 卡片上的 [ **View more** ] 按鈕。

## <a name="interpret-the-microsoft-365-apps-usage-report"></a>解讀 Microsoft 365 應用程式使用方式報告

您可以查看 [ **使用者** ] 和 [ **平臺** ] 圖表，以取得使用者的 Microsoft 365 應用程式活動。

> [!div class="mx-imgBorder"]
> ![Microsoft 365 應用程式使用方式報告](../../media/0bcf67e6-a6e4-4109-a215-369f9f20ad84.png)

|項目|描述|
 |:-----|:-----|
 |1. <br/> |**Microsoft 365 應用程式使用方式** 報告可查看過去7天、30天、90天或180天的趨勢。 不過，如果您在報告中選取某一天，則 table (7) 會從目前的日期顯示最多28天的資料， (不是) 產生報表的日期。 <br/> |
 |2. <br/> |每個報告中的資料通常最多涵蓋過去兩天。 每隔六天，我們會以次要更新重新整理報告，以確保資料品質。 <br/> |
 |3. <br/> |[ **使用者** ] 視圖會顯示每個應用程式的作用中使用者數目的趨勢-Outlook、Word、Excel、PowerPoint、OneNote 和團隊。 「作用中使用者」是指任何在這些應用程式中執行任何故意動作的使用者。 <br/> |
 |4. <br/> |[ **平臺** ] 視圖會顯示每個平臺（Windows、Mac、Web 及行動裝置）上的每個應用程式中使用中使用者的趨勢。 <br/> |
 |5.<br/>|在 [ **使用者** ] 圖表上，Y 軸是個別應用程式的唯一作用中使用者數目。 在 [ **平臺**]   圖表上，Y 軸是個別平臺的唯一使用者數目。 這兩張圖表的 X 軸都是在指定的平臺上使用應用程式的日期。<br/>|
 6.<br/>|您可以選取圖例中的專案，以篩選您在圖表上看到的數列。 例如，在 [ **使用者** ] 圖表上，選取 [Outlook]、[Word]、[PowerPoint Excel]、[OneDrive] 或 [小組]，以查看只與各項相關的資訊。 變更此選取專案並不會變更下方格線表格中的資訊。|
 |7.<br/>|表格顯示每個使用者層級的資料明細。 您可以新增或移除表格中的欄位。 <br/><br/>**Username** 是在 Microsoft app 上執行活動之使用者的電子郵件地址。<br><br/>**上次啟用日期 (UTC)** 是使用者啟用其 Microsoft 365 應用程式訂閱的最晚日期。<br/><br/>**上次活動日期 (UTC)** 是使用者執行有意活動的最晚日期。 若要查看特定日期發生的活動，請直接選取圖表中的日期。<br/><br/>其他欄會識別使用者在該平臺上是否有作用中的使用者，該應用程式 (于所選期間365內) 中的應用程式。 |
 |8.<br/>|選取 [ **選擇欄** ] 圖示，以新增或移除報告中的欄。|
 |9.<br/>|您也可以選取 [ **匯出** ] 連結，將報告資料匯出至 Excel .csv 檔案。 這會匯出所有使用者的資料，並可讓您進行簡單的匯總、排序及篩選，以進行進一步分析。 如果您的使用者少於100，您可以在報表本身的資料表中進行排序和篩選。 如果您有超過100的使用者，為了進行篩選和排序，您將需要匯出資料。|
