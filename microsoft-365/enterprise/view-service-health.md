---
title: 如何檢查 Microsoft 365 服務健康情況
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365P_ServiceHealthModern
- O365M_ServiceHealthModern
- O365E_ViewStatusServices
- O365E_ServiceHealthModern
- seo-marvel-apr2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- BCS160
- IWA160
ms.assetid: 932ad3ad-533c-418a-b938-6e44e8bc33b0
description: 在撥打 support 之前，請先查看 Microsoft 365 服務的健康情況狀態，以查看是否有使用中的服務中斷狀態。
ms.openlocfilehash: 95ab260b4950d261eed1288b8fdf1f59883ff15f
ms.sourcegitcommit: 17d82e5617f0466eb825e15ab88594afcdaf4437
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/06/2021
ms.locfileid: "53300402"
---
# <a name="how-to-check-microsoft-365-service-health"></a>如何檢查 Microsoft 365 服務健康情況

[![[標籤] 可讓您知道系統管理中心正在變更，您可以在 aka.ms/aboutM365preview 取得更多詳細資料。](../media/O365-Admin-AdminCenterChanging.png)](/office365/admin/microsoft-365-admin-center-preview?preserve-view=true&view=o365-worldwide)

您可以在 [Microsoft 365 系統管理中心](https://go.microsoft.com/fwlink/p/?linkid=2024339)的 [**服務健康情況**] 頁面上，查看 Microsoft 服務的健康情況，包括 Office 網頁版、Yammer、Microsoft Dynamics CRM 及行動裝置管理雲端服務。 如果雲端服務發生問題，在您連絡支援人員或花時間進行疑難排解之前，可以查看服務健康情況，以確定是否為正在開發解決方法的已知問題。

如果您無法登入系統管理中心，您可以使用 [ [服務狀態] 頁面](https://status.office365.com) 檢查是否有已知的問題，使您無法登入您的租使用者。  此外，請在 Twitter 上的 [@MSFT365status](https://twitter.com/MSFT365Status) 上進行註冊，以查看特定事件的資訊。

## <a name="how-to-check-service-health"></a>如何查看服務健全狀態

1. 移至 Microsoft 365 系統管理中心 [https://admin.microsoft.com](https://go.microsoft.com/fwlink/p/?linkid=2024339) ，然後使用管理員帳戶登入。

    > [!NOTE]
    > 獲指派全域管理員或服務支援系統管理員角色的人員可查看服務健康情況。 若要允許 Exchange、SharePoint 以及商務用 Skype 管理員檢視服務健康情況，必須同時將服務系統管理員角色指派給他們。 如需可查看服務健康情況之角色的詳細資訊，請參閱 [關於系統管理員角色](../admin/add-users/about-admin-roles.md?preserve-view=true&view=o365-worldwide#commonly-used-microsoft-365-admin-center-roles)。

2. 若要查看服務健康情況，請在系統管理中心中，移至 [**健康** 情況  >  **服務健康** 情況]，或選取 **首頁儀表板** 上的 **服務健康** 情況卡片。 儀表板卡會指出是否有主動服務問題，以及詳細的 **服務健康** 情況頁面連結。

3. 在 [ **服務健康** 情況] 頁面上，每個雲端服務的健康狀態是以表格格式顯示。

   ![View of current issues in service health](../media/service-health-all-services.png)

[ **所有服務** ] 索引標籤 (預設 view) 會顯示所有服務、其目前的健康狀態，以及任何作用中的事件或諮詢。 [ **狀況** ] 欄中的圖示及狀態會指出每項服務的狀態。

如果有服務有作用中的事件或建議，其將會直接列在巢狀表格格中的服務名稱下。 您可以按一下服務名稱左側的 v 形圖示，以壓縮巢狀表格格以隱藏此視圖中的事件或諮詢。   

若要篩選您的視圖只顯示所有作用中的事件，請選取頁面頂端的 [ **事件** ] 索引標籤。 選取 [ **建議** ] 索引標籤只會顯示所有已發佈的主動建議。

[ **記錄** ] 索引標籤會顯示過去7天或30天內已解決的所有事件和提議。

如果您遇到 Microsoft 365 服務的問題，但您未在 [**服務健康** 情況] 頁面上看到該問題，請選取 [**報告問題**]，並完成簡寫表單，以告知我們。 我們將從其他組織查看相關資料和報告，以查看問題的程度，以及是否與我們的服務有關。 如果是的話，我們會將其新增為 [ **服務健康** 情況] 頁面上的新事件或建議，您可以在這裡追蹤其解決方法。 「 **報告的問題** 」頁面會顯示您租使用者從這個表單報告的所有問題及狀態。

若要自訂在儀表板上顯示服務的視圖，請選取 [**喜好** 設定  >  **自訂視圖**]，然後清除您要從服務健康情況儀表板視圖中篩選出之服務的核取方塊。 請確定已針對您要監視的每個服務選取此核取方塊。

若要註冊會影響租使用者的新事件的電子郵件通知，以及對使用中事件的狀態變更，請選取 [**喜好** 設定  >  **電子郵件**]，按一下 [**以電子郵件傳送我的服務 heath 通知**]，然後指定：

- 最多兩個電子郵件地址。
- 您是否需要事件或建議的通知
- 您要通知的服務

您也可以訂閱個別事件的電子郵件通知，而不是服務的每個事件。 若要這麼做，請選取您想要接收電子郵件通知更新的使用中問題，選取 [ **管理此問題的通知**]，然後指定： 
- 最多兩個電子郵件地址。

> [!NOTE]
> 每個系統管理員都可以設定其偏好設定，而每個系統管理員帳戶的上述限制為兩個電子郵件地址。

> [!TIP]
> 您也可以使用行動裝置上的[Microsoft 365 系統管理應用程式](https://go.microsoft.com/fwlink/p/?linkid=627216)來查看服務健康情況，這是使用推播通知保持最新狀態的絕佳方式。

### <a name="view-details-of-posted-service-health"></a>檢視已張貼的服務健康情況詳細資料

在 [ **所有服務** ] 視圖上，選取 [問題標題] 以查看 [問題詳細資料] 頁面，其中會顯示有關問題的詳細資訊，包括在處理方案時所發佈之所有訊息的摘要。 

[![顯示服務建議 ](../media/service-health-advisory.png) 的螢幕擷取畫面](../media/service-health-advisory.png#lightbox)

建議或事件摘要會提供下列資訊：

- **Title** -問題的摘要。
- **ID** -問題的數值識別碼。
- **服務** -受影響服務的名稱。
- **上次更新** 時間-上次更新服務狀況訊息的時間。
- **預估開始時間** -問題已開始的預估時間。
- **狀態** -此問題對服務的影響。
- **使用者影響** -此問題對使用者之影響的簡短描述。
- **所有更新** -我們經常發佈訊息，讓您知道我們在套用方案中所進行的進度。

![顯示問題詳細資料的螢幕擷取畫面](../media/service-health-advisory-detail.png)

### <a name="translate-service-health-details"></a>翻譯服務健康情況詳細資料

我們使用機器翻譯以您慣用的語言自動顯示郵件。 有關如何設定語言的詳細資訊，請閱讀 [郵件中心文章的語言翻譯](/microsoft-365/admin/manage/language-translation-for-message-center-posts) 。

### <a name="definitions"></a>定義

在大部分的情況下，服務會顯示為良好狀態，而不會進一步資訊。 如果服務發生問題，系統就會以建議或事件的方式表示發生問題，並顯示目前的狀態。

> [!TIP]
> 預定維修事件不會顯示在服務健康情況中。 您可以在 **郵件中心** 保持最新狀態，追蹤計畫的維護事件。 篩選至歸類為「規劃變更」 的訊息，即可了解何時要進行變更、變更的作用以及如何準備因應。 如需詳細資訊，請參閱[Microsoft 365 中的訊息中心](https://support.office.com/article/38fb3333-bfcc-4340-a37b-deda509c2093)。

### <a name="incidents-and-advisories"></a>事件和建議

| 圖示 | 描述 |
|:-----|:-----|
|![Information icon for advisory](../media/a7f5fd21-c760-4948-9bc1-50f7c8070e28.png)|如果系統針對某個服務顯示「建議」，表示我們發現了會對部分使用者造成影響的問題，但該服務仍可使用。建議中通常會提供問題的因應措施，且該問題可能是間歇發生，或其波及範圍和對使用者造成的影響並不大。  <br/> |
|![Exclamation point icon for incident](../media/a636db57-6083-44dc-bbd5-556850804f17.png)|如果系統針對某個服務顯示有作用中的「事件」，代表這是一個重大問題，且該服務或其主要功能無法使用。例如，使用者可能無法傳送和接收電子郵件，或者無法登入。事件會對使用者造成明顯影響。當有進行中的事件時，我們會在服務健康情況儀表板中提供更新資訊，讓您掌握調查和移轉作業的進度，以及確認解決方案。  <br/> |

### <a name="status-definitions"></a>狀態定義

| 狀態 | 定義 |
|:-----|:-----|
|**調查** | 我們已發現潛在問題，正在收集關於其原因和影響範圍的詳細資訊。 |
|**服務效能下降** | 我們已確認某個問題可能會對服務或功能的使用造成影響。舉例來說，如果某個服務的執行速度比平常慢、出現間歇性中斷，或者某個功能無法正常運作，您就會看見此狀態。 |
|**服務中斷** | 如果我們判斷某個問題會影響使用者存取服務的能力，您就會看見此狀態。這種情況表示問題相當嚴重，且在相同條件下會固定發生。 |
|**正在恢復服務** | 我們已經找出問題的成因，知道要採取什麼修正動作，且正在讓服務恢復到健康情況良好的狀態。 |
|**擴充的復原** | 此狀態表示我們正在進行矯正措施，以便為大多數使用者恢復服務，但需要一些時間才能讓所有受影響的系統恢復正常運作。如果我們在尚未進行永久修復期間先採用暫時修正方法以降低影響，您也可能會看到此狀態。 |
|**調查暫停** | 在我們詳細調查潛在問題後，如果需要客戶提供額外資訊以進行更深入的調查，您就會看到此狀態。如果我們需要您採取行動，我們會告知您我們所需的資料或記錄。 |
|**服務已恢復** | 我們確認矯正措施已解決根本問題，且服務也已恢復為健康情況良好的狀態。如需了解何處發生錯誤，請檢視問題詳細資料。 |
|**False 正值** | 在詳細調查之後，我們已確認服務狀況良好，且如設計方式運作。 不會對服務的影響，或從服務之外產生事件的原因。 |
|**發佈的事件後報告** | 我們已發佈一個包含根本原因資訊的特定問題的文章附隨報告及後續步驟，以確保不再發生類似的問題。 |

### <a name="message-post-types"></a>訊息發佈類型

| 類型 | 定義 |
|:-----|:-----|
|**快速更新** | 適用于廣泛影響的事件的簡短和經常性增量更新，可供所有客戶使用。 |
|**其他詳細資料** | 這些額外文章會提供更豐富的技術和解析度詳細資料，以提供對事件處理的深入瞭解。 這適用于符合[Exchange Online 監控](/microsoft-365/enterprise/microsoft-365-exchange-monitoring?view=o365-worldwide#requirements)所述相同需求的承租人。 |

### <a name="history"></a>歷程記錄

服務健康情況可讓您查看目前的健全狀態，並查看過去30天內，對租使用者造成影響的任何服務建議和事件的記錄。 若要查看所有服務的過去健康情況，請選取 [ **史** view]。

如需關於我們工作時間承諾的詳細資訊，請參閱[Microsoft 365 的透明作業](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity)。

## <a name="related-topics"></a>相關主題

[Microsoft 365 系統管理中心中的活動報告](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

[訊息中心喜好設定](../admin/manage/message-center.md?preserve-view=true&view=o365-worldwide#preferences)

[如何檢查系統管理中心的 Windows 版本健康情況](/windows/deployment/update/check-release-health)
