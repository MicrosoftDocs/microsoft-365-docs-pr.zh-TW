---
title: 自動調查及回應 Office 365 中的威脅
keywords: AIR, autoIR, ATP, 自動化, 調查, 回應, 修正, 威脅, 進階, 威脅, 保護
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: 開始使用 Office 365 進階威脅防護方案 2 中的自動化調查及回應功能
ms.openlocfilehash: 3f13b1de2747dcb6672f56989ff73cdf485e49b6
ms.sourcegitcommit: 8c244b38c43dd00c4ef0102f8bed02ab36639a6b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/10/2019
ms.locfileid: "39967986"
---
# <a name="automatically-investigate-and-respond-to-threats-in-office-365"></a>自動調查及回應 Office 365 中的威脅

## <a name="overview"></a>概觀

視您的訂閱而定，[Office 365 進階威脅防護](office-365-atp.md)可以包括自動化調查和回應 (AIR) 功能，可節省您的安全性作業小組時間和處理警示和威脅的精力。

- 若要開始使用 Office 365 中的自動化調查及回應功能，請使用本文章。 
- 若要取得其運作方式的概觀，請參閱 [Office 365 中的自動化調查及回應](automated-investigation-response-office.md)。

> [!TIP]
> 您有 Microsoft 365 E5 或 Microsoft 365 E3 以及身分識別與威脅防護產品？ 考量嘗試 [Microsoft 威脅防護中的自動化調查及回應 (AIR)](../mtp/mtp-autoir.md)

使用自動化調查及回應功能，當觸發特定警示時，會起始一或多個安全性劇本，並且開始自動化調查程序。 在自動化調查程序期間及之後，您的安全性小組可以執行下列動作：

- [檢視調查的詳細資料](#view-details-of-an-investigation)
- [根據調查的結果檢閱和核准動作](#review-and-approve-actions) 
- [檢視與調查相關警示的詳細資料](#view-details-about-an-alert-related-to-an-investigation)

> [!IMPORTANT]
> 若要執行本文所述的工作，您必須獲指派適當的權限。 請參閱[使用 AIR 功能所需的權限](automated-investigation-response-office.md#required-permissions-to-use-air-capabilities)。

## <a name="view-details-of-an-investigation"></a>檢視調查的詳細資料

1. 移至 [https://protection.office.com](https://protection.office.com) 並登入。 這樣會帶您前往安全性與合規性中心。

2. 執行下列其中一項動作：

    - 移至 [威脅管理]****  >  [儀表板]**** 這樣會帶您前往[安全性儀表板](security-dashboard.md)。 您的 AIR 小工具會顯示在[安全性儀表板](security-dashboard.md)上方。 選取小工具，例如**調查摘要**。

    - 移至 [威脅管理]****  >  [調查]****。 

    這兩種方法都會帶您前往調查清單。

    ![AIR 的主要調查頁面](../media/air-maininvestigationpage.png) 

3. 在調查清單中，選取 [識別碼]**** 欄中的項目。 這樣會開啟調查詳細資料頁面，從檢視中的調查圖形開始。

    ![AIR 調查圖形頁面](../media/air-investigationgraphpage.png)

4. 使用各個索引標籤深入了解調查。

## <a name="review-and-approve-actions"></a>檢閱和核准動作

在 Office 365 中，自動化調查通常會導致一或多個建議的動作。 不過，在安全性操作小組核准之前，不會採取任何動作。 使用下列程序來檢閱和核准動作。

1. 移至 [https://protection.office.com](https://protection.office.com) 並登入。 

2. 移至 [威脅管理]****  >  [調查]****。

3. 在調查清單中，選取 [識別碼]**** 欄中的項目。 

3. 在調查詳細資料檢視上，選取 [動作]**** 索引標籤。以下列出等候核准的任何動作。

4. 選取清單中的項目。

5. 選取 [核准]**** 以採取建議的動作 (或選取 [拒絕]**** 關閉調查而不採取動作)。

## <a name="view-details-about-an-alert-related-to-an-investigation"></a>檢視與調查相關警示的詳細資料

某些類型的警示會在 Office 365 中觸發自動化調查。 若要深入了解，請參閱[警示](automated-investigation-response-office.md#alerts)。 使用下列程序來檢視與自動化調查相關聯警示的詳細資料。

1. 移至 [https://protection.office.com](https://protection.office.com) 並登入。 這樣會帶您前往安全性與合規性中心。

2. 移至 [威脅管理]****  >  [調查]****。

3. 在調查清單中，選取 [識別碼]**** 欄中的項目。 

4. 開啟調查詳細資料時，選取 [警示]**** 索引標籤。觸發調查的任何警示都會列在此處。

5. 選取清單中的項目。 隨即開啟一個飛出視窗，其中包含警示的詳細資料以及其他資訊和動作的連結。

6. 檢閱飛出視窗中的資訊，並視特定警示採取動作，例如**解決**、**隱藏**，或**通知使用者**。 

    - **解決**等同於關閉警示
    
    - **隱藏**會導致原則在指定時段不觸發警示
    
    - **通知使用者**會啟動電子郵件，並且已輸入使用者的電子郵件地址，讓您的安全性操作小組輸入要給這些使用者的訊息。 (這類似於使用[威脅總管](threat-explorer.md)將訊息傳送給收件者。)  

## <a name="use-the-office-365-management-activity-api-for-custom-or-third-party-reporting-solutions"></a>針對自訂或第三方報告解決方案使用 Office 365 管理活動 API

如果貴組織使用自訂或第三方報告解決方案，您可以使用 Office 365 管理活動 API 來檢視該解決方案中自動化調查的資訊。

使用下列資源進行設定：

|資源  |描述  |
|---------|---------|
|[Office 365 Management API 概觀](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview) (英文)     |Office 365 管理活動 API 提供 Office 365 和 Azure Active Directory 活動記錄中各種使用者、系統管理員、系統和原則動作及事件的相關資訊。         |
|[開始使用 Office 365 管理 API](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis) (英文)     |Office 365 管理 API 使用 Azure AD 來為您的應用程式提供驗證服務，以存取 Office 365 資料。 請依照本文中的步驟進行設定。          |
|[Office 365 管理活動 API 參考](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference) (英文)     |您可以使用 Office 365 管理活動 API，從 Office 365 和 Azure AD 活動記錄中擷取使用者、系統管理員、系統和原則動作及事件的相關資訊。 請閱讀本文以深入了解其運作方式。        |
|[Office 365 管理活動 API 架構](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema) (英文)     |取得[常見架構](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) (英文) 和 [Office 365 ATP 和威脅調查和回應架構](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) (英文) 的概觀，以深入了解 Office 365 管理活動 API 中可用的特定類型資料。         |

## <a name="next-steps"></a>後續步驟

- [了解如何取得 AIR 及查看所需權限](automated-investigation-response-office.md#how-to-get-air)
- [深入了解警示](../../compliance/alert-policies.md)
- [手動尋找並調查在 Office 365 中傳送的惡意電子郵件](investigate-malicious-email-that-was-delivered.md)
- [了解 Microsoft Defender ATP 中的 AIR](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations) (部分機器翻譯)
- [造訪 Microsoft 365 藍圖，查看即將推出的功能](https://www.microsoft.com/microsoft-365/roadmap?filters=)