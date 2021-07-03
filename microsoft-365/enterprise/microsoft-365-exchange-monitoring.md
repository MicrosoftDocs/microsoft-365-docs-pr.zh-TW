---
title: 適用於 Microsoft 365 的 Exchange Online 監視
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/03/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- NOCSH
description: 在 Microsoft 365 中使用 Exchange Online 監視以取得電子郵件事件或建議的相關資訊。
ms.openlocfilehash: 3d88378449879d451b21ba8bf2a7b5c3032a2c07
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286438"
---
# <a name="exchange-online-monitoring-for-microsoft-365"></a>適用於 Microsoft 365 的 Exchange Online 監視

您可以在 Microsoft 365 系統管理中心使用 Exchange Online 監視，監視組織之 Microsoft 365 訂閱的 Exchange 服務健康情況。 Exchange Online 監視可為您提供下列類別的事件和建議相關資訊：

- **基礎結構**：在 Microsoft 擁有的 Microsoft 365 基礎結構中偵測問題，以提供定期更新並解決問題。 例如，因為 Exchange 或其他 Microsoft 365 雲端基礎結構問題，導致使用者無法存取 Exchange Online。
- **協力廠商基礎結構**：在組織依賴的協力廠商基礎結構中偵測問題，且需要組織採取措施才能解決。 例如，使用者驗證交易會受到協力廠商安全性權杖服務 (STS) 提供者的限制，防止使用者連線到 Exchange Online。
- **客戶基礎結構**：在您的組織基礎結構中偵測問題，且需要組織採取措施才能解決。 例如，使用者無法存取 Exchange Online，因為他們無法取得由貴組織託管的 STS 提供者提供的驗證權杖，因為該憑證已過期。

以下是 Microsoft 365 系統管理中心的 **[服務健康情況]** 頁面範例，可從 [健康情況] > **[服務健康情況]** 進入此頁面。

![Microsoft 365 系統管理中心的 [服務健康情況] 頁面](../media/microsoft-365-exchange-monitoring/service-health-dashboard-example.png)

**[狀態]** 欄的值會根據 Microsoft 所維護的雲端服務，指出服務是否健康或是否有建議或事件發生。 

**[您的組織和協力廠商問題]** 欄的值指出您組織的基礎結構，或協力廠商軟體影響到您的使用者使用 Exchange Online 的服務健康狀況。 *「您」* 必須採取行動才能解決建議或事件。

以下是 Microsoft 365 系統管理中心的 **[Exchange Online]** 監視頁面範例，可從 **[健康情況] > [服務健康情況]> [Exchange Online]** 進入此頁面。

![Microsoft 365 系統管理中心的 Exchange Online 監視頁面](../media/microsoft-365-exchange-monitoring/exhange-monitoring-example.png)

使用 **[Exchange Online]** 監視頁面，您可以查看 Exchange Online 服務是否健康，以及是否有任何相關的事件或建議。 透過 Exchange Online 監視，您可以查看特定電子郵件案例的服務健康情況，並檢視近即時訊號來判斷案例帶來的影響。 

## <a name="requirements"></a>需求

符合以下需求的客戶可以啟用此預覽： 

- 組織必須擁有至少 5,000 個授權數來自以下一項或多項產品: Office 365 E3、Microsoft 365 E3、Office 365 E5、Microsoft 365 E5。 

  例如，您的組織可以擁有 3,000 個 Office 365 E3 授權，以及 2,500 個 Microsoft 365 E5，總計為 5,500 個合格產品的授權。

- 您的組織每月至少需要有 50 位作用中 Exchange Online 使用者

使用 Exchange Online 監視，您可以根據電子郵件讀取活動檢視下列電子郵件用戶端的健康情況：

- Outlook 電腦版
- Outlook 網頁版
- iOS 和 Android 的原生郵件用戶端 
- iOS 和 Android 版 Outlook 行動裝置應用程式 
- Outlook Mac 用戶端

對於這些用戶端，您可以根據讀取電子郵件的使用者查看最近 30 分鐘的作用中使用者數量，以及儀表板中的事件和建議數量。 這個資料會與前一週相同間隔的資料進行比較，看看是否有問題。 

>[!Note]
> 作用中使用者計數是由單一活動來計算，例如，使用者讀取電子郵件。 僅限活動的最後 30 分鐘。
>

您也可以監視下列案例的 Exchange Online 健康情況：

- **郵件流程**：郵件到達 Microsoft 365 網路後，成功傳遞到信箱而不會有任何延遲的郵件數目。 
- **基本驗證和新式驗證**：在 Exchange Online 服務中成功驗證的使用者數目。

![針對郵件傳遞監視 Exchange 健康情況的範例](../media/microsoft-365-exchange-monitoring/exhange-monitoring-scenario-example.png)

對於所有這些案例，關鍵數目是主儀表板中最後 30 分鐘的數目。 這些案例中每一個案例的詳細檢視都顯示了與前一週相比，過去 7 天總計 30 分鐘的近即時趨勢。 

## <a name="send-us-feedback"></a>傳送意見反應給我們

有兩種方式可提供意見反應：

- 使用 Microsoft 365 系統管理中心中，每個頁面均提供的 **[提供意見反應]** 選項。
- 針對特定事件或建議，使用 **[此文章是否有幫助?]** 連結提交意見反應。

![特定事件或建議的  [此文章是否有幫助?] 連結](../media/microsoft-365-exchange-monitoring/exhange-monitoring-example-incident-feedback.png)

## <a name="frequently-asked-questions"></a>常見問題集

#### <a name="1-why-dont-i-see-exchange-online-monitoring-under-health-in-the-microsoft-365-admin-center"></a>1. 為什麼我在 Microsoft 365 系統管理中心沒看到「Exchange Online 監視」? 

首先，請確定您已在 Microsoft 365 系統管理中心的 **[首頁]** 頁面上啟用新的系統管理中心。 

然後，確定您符合下列兩個需求： 

- 組織必須擁有至少 5,000 個授權數來自以下一項或多項產品: Office 365 E3、Microsoft 365 E3、Office 365 E5、Microsoft 365 E5。 
- 您的組織每月至少需要有 50 位作用中 Exchange Online 使用者。

如果組織的授權數量少於 5,000 位使用者，且每月作用中使用者少於 50 位，則必須先符合這些需求，才會啟用 Exchange Online 監視。

#### <a name="2-the-active-user-count-in-the-dashboard-for-each-client-appears-to-be-low-we-have-a-lot-of-active-licenses-assigned-to-users-what-does-this-mean"></a>2. 儀表板中每個用戶端的作用中使用者數太低。 我們已將大量的作用中授權指派給使用者。 這代表什麼意思？ 

監視中顯示的作用中使用者數是以 30 分鐘為基礎，使用者在該時間內執行功能呼叫的活動。 不應將此與使用次數混淆。 若要檢視使用次數，請使用 Microsoft 365 系統管理中心的活動報告 (**[報告] > [使用狀況]**)。

#### <a name="3-will-there-be-other-monitoring-scenarios-for-other-services-such-as-teams-and-sharepoint"></a>3. Teams 和 SharePoint 等其他服務是否還有其他監視案例？ 

Microsoft 已在 Microsoft 365 系統管理中心的 [服務健康情況] 儀表板中直接整合了此體驗。 這將為 Microsoft 提供擴充其他服務監視案例的機會，而當有最新消息時，我們將予以公佈。 

#### <a name="4-what-is-the-plan-for-general-availability-of-this-experience"></a>4. 針對這項體驗有何正式發行計劃？ 

Microsoft 已在 Microsoft 365 系統管理中心的 **[服務健康情況]** 儀表板中直接整合 Exchange Online 監視功能。 

透過這項全新的整合體驗，Microsoft 計劃先收集您的意見反應，然後再定義正式發行的計劃。

#### <a name="5-is-this-a-free-included-or-paid-extra-feature"></a>5. 這是免費 (隨附) 或付費 (額外) 功能？ 

這項功能處於公開預覽階段，且僅適用於符合問題 1 中需求的客戶。

<!--
>[!Note]
>INTERNAL: That decision is pending
>
--> 

#### <a name="6-how-do-i-provide-feedback"></a>6. 如何提供意見反應？ 

一般意見反應，請使用 **[Exchange Online]** 監視頁面右下角的 **[提供意見反應]** 圖示。 

有關事件或建議的意見反應，請使用 **[此文章是否有幫助?]** 連結。

#### <a name="7-where-is-the-data-instrumented-for-the-scenarios-that-show-activity-trends"></a>7. 顯示活動趨勢的案例資料在哪裡檢測？

會在 Exchange Online 服務中檢測資料。如果在要求到達 Exchange Online 前發生錯誤，或 Exchange Online 發生錯誤，則活動訊號將會下降。
