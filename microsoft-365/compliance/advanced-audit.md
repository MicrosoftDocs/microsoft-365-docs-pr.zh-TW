---
title: Microsoft 365 中的進階稽核
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Microsoft 365 中的進階稽核提供新的稽核功能，以協助組織進行鑑識與合規性調查。
ms.openlocfilehash: 6fb42e9df35fe025c5c5f292238217aebb4098c7
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2020
ms.locfileid: "44141041"
---
# <a name="advanced-audit-in-microsoft-365"></a>Microsoft 365 中的進階稽核

Microsoft 365 中的[整合式稽核功能](search-the-audit-log-in-security-and-compliance.md)，可讓組織深入了解 Microsoft 365 中多種不同服務的多個類型的稽核活動。 現在隨著 Microsoft 365 中進階稽核的推出，我們會加入新的稽核功能，以協助組織進行鑑識與合規性調查。

> [!NOTE]
> 進階稽核可供具有 Office 365 E5 或 Microsoft 365 企業版 E5 訂閱的組織使用。 此外，當進階稽核功能需要針對每位使用者進行授權時，您可以將 Microsoft 365 E5 合規性附加元件授權指派給使用者，而針對稽核記錄和存取重要調查事件的長期保留也是如此。

本文提供這些進階稽核功能的概觀。

## <a name="long-term-retention-of-audit-logs"></a>長期保留稽核記錄

進階稽核會保留所有 Exchange、SharePoint 和 Azure Active Directory 稽核記錄，時間為一年。 這是透過預設的稽核記錄保留原則完成，它會保留包含 **Workload** 屬性 (這指出發生活動所在的服務) 的 **Exchange**、**SharePoint** 或 **AzureActiveDirectory** 的值的任何稽核記錄一年。 這可協助進行持續的鑑識或合規性調查。 如需詳細資訊，請參閱[管理稽核記錄保留原則](audit-log-retention-policies.md#default-audit-log-retention-policy)中的「預設稽核記錄保留原則」一節。

## <a name="audit-log-retention-policies"></a>稽核記錄保留原則

在其他服務中產生、未在預設稽核記錄保留原則涵蓋範圍的所有稽核記錄 (如前一節所述)，將會保留 90 天。 不過，您現在可以建立自訂的稽核記錄保留原則，以保留其他稽核記錄最多達一年。 您可以根據下列一或多項準則，建立用來保留稽核記錄的原則：

- 稽核活動發生所在的 Microsoft 365 服務

- 特定已稽核活動

- 執行已稽核活動的使用者

您也可以指定要保留符合原則的稽核記錄的時間長度和優先順序層級，以便特定原則可優先於其他原則。 另請注意，如果您需要為組織中的部分或所有使用者保留 Exchange、SharePoint 或 Azure Active Directory 稽核記錄少於一年，任何自訂稽核記錄保留原則都會優先於預設的稽核保留原則。 如需詳細資訊，請參閱[管理稽核記錄保留原則](audit-log-retention-policies.md)。

## <a name="access-to-crucial-events-for-investigations"></a>存取調查重要事件

重要安全性與合規性相關的稽核事件，可協助您調查可能外洩或其他與鑑識相關的調查。 我們要發佈的第一個重要事件是 *MailItemsAccessed* 信箱稽核動作。 當郵件通訊協定和郵件用戶端存取郵件資料時，即會觸發此動作。 MailItemsAccessed 動作可幫助調查人員識別資料外洩，並判斷可能已遭入侵的郵件範圍。 如果攻擊者取得電子郵件訊息，即使沒有明確訊號指出已實際讀取郵件 (也就是說，在稽核記錄中記錄了透過繫結或同步處理之類的存取類型)，將會觸發 MailItemsAccessed 動作。

新的 MailItemsAccessed 信箱動作會取代 Exchange Online 中信箱稽核記錄的 MessageBind，並提供下列改善：

- MessageBind 僅可針對 AuditAdmin 使用者登入類型設定；不適用於代理人或擁有者動作。 MailItemsAccessed 適用於所有登入類型。

- MessageBind 僅涵蓋透過郵件用戶端的存取。 並不適用同步處理活動。 MailItemsAccessed 事件會由繫結和同步處理存取類型觸發。

- 當存取相同的電子郵件訊息時，MessageBind 動作會觸發多個稽核記錄的建立，這會導致稽核的「雜訊」。 相反地，MailItemsAccessed 事件會彙總在較少的稽核記錄中。

如需有關 MailItemsAccessed 活動的稽核記錄資訊，請參閱[使用進階稽核調查遭入侵帳戶](mailitemsaccessed-forensics-investigations.md)。

### <a name="search-for-mailitemsaccessed-audit-records"></a>搜尋 MailItemsAccessed 稽核記錄

若要搜尋 MailItemsAccessed 稽核記錄，您可以在安全性與合規性中心的[稽核記錄搜尋工具](search-the-audit-log-in-security-and-compliance.md)中，在 [Exchange 信箱活動]**** 下拉式清單中搜尋 [已存取的信箱項目]**** 活動。

![在稽核記錄搜尋工具中搜尋 MailItemsAccessed 動作](../media/MailItemsAccessedSCC1.png)

您也可以在 Exchange Online PowerShell 中執行 [Search-UnifiedAuditLog -Operations MailItemsAccessed](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-unifiedauditlog) 或 [Search-MailboxAuditLog -Operations MailItemsAccessed](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-mailboxauditlog) 命令。

## <a name="high-bandwidth-access-to-the-office-365-management-activity-api"></a>Office 365 管理活動 API 的高頻寬存取權

透過 Office 365 管理活動 API 存取稽核記錄的組織，其節流限制會處於發行者層級。 這表示，針對代表多個客戶提取資料的發行者，此限制會由所有客戶所共用。

隨著進階稽核的推出，我們會將發行者層級限制移至租用戶層級限制。 結果是每個組織都會獲得自己完整配置的頻寬配額，以存取其稽核資料。 頻寬不是靜態、預先定義的限制，但是會以一些要素的組合模組化，其中包括組織中的基座數量，以及 E5 組織可獲得較非 E5 組織更多的頻寬。

所有組織一開始都會配置每分鐘 2,000 個要求的基準。 視組織的基座數和授權訂閱而定，此限制將會動態增加。 E5 組織可獲得的頻寬大約可達到非 E5 組織的兩倍。 最大頻寬也會有上限，以保護服務的健康情況。

如需詳細資訊，請參閱 [Office 365 管理活動 API 參考](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#api-throttling)中的「API 節流」一節。

## <a name="faqs-for-advanced-audit"></a>進階稽核的常見問題集

**我可以在哪裡存取進階稽核？**

在您的組織推出進階稽核之後，您就可以建立稽核記錄保留原則，並使用[安全性與合規性中心](https://protection.office.com)中的 [稽核記錄搜尋] 工具來搜尋 MailItemsAccessed 稽核記錄。 我們正努力在未來幾周內，在 [Microsoft 365 合規性中心](https://compliance.microsoft.com)推出進階稽核。

**每位使用者是否需要 E5 授權才能使用進階稽核？**

若要使用使用者層級的進階稽核功能，使用者必須獲指派 E5 授權。 部分功能會檢查是否有適當授權，才會開放功能供使用者使用。 例如，如果您正嘗試保留使用者的稽核記錄，但該使用者在 90 天內未獲指派 E5 授權，系統將會傳回錯誤訊息。

**為什麼即使已有 E5 訂閱，而使用者也已獲指派 E5 授權，在組織中仍看不到進階稽核？**

即使已具備正確的授權，您的組織可能仍無法使用 [進階稽核] 功能 (例如建立稽核記錄保留原則和記錄 MailItemsAccessed 稽核記錄的功能)。 如果您遇到此問題，這是因為進階稽核套件尚未部署至您的組織。 這是暫時的授權回填問題，應該很快會為受影響組織解決這個問題。 若要緩解此問題，請針對每個 E5 使用者執行下列步驟：

1. 在 Microsoft 365 系統管理中心，移至 [使用者] > [作用中的使用者]****，然後選取使用者。

2. 在 [使用者內容] 飛出頁面上，按一下 [授權和應用程式]****。

3. 展開 [應用程式]**** 區段，然後執行下列其中一項操作：

   a. 如果沒有選取 [Microsoft 365 進階稽核]**** 核取方塊，請選取它，然後按一下 [儲存變更]****。 此使用者的 MailItemsAccessed 動作的稽核記錄應可在 24 小時內提供搜尋。

   b. 如果已選取 [Microsoft 365 進階稽核]**** 核取方塊，請清除它，然後按一下 [儲存變更]****。 請參閱步驟 4。

4. 如果您已在步驟 3 中清除核取方塊，請稍候 60 分鐘，然後重複步驟 3a 來啟用 Microsoft 365 進階稽核應用程式。

針對使用以群組為基礎授權之指派授權至使用者群組的組織，請務必關閉該群組的 Microsoft 365 進階稽核授權指派。 儲存變更之後，請確認已關閉群組的 Microsoft 365 進階稽核。 然後重新開啟群組的授權指派。 如需以群組為基礎授權的相關指示，請參閱[在 Azure Active Directory 中以群組成員資格指派授權給使用者](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign) (英文)。

**如果我的組織處於私人預覽階段的一年稽核記錄保留，會發生什麼情況？**

只要您不以自訂稽核保留原則來覆寫和變更稽核保留原則，就可以保留預覽計畫中的審核保留原則。

**如果我的組織想要將稽核記錄保留一年以上，該怎麼辦？**

我們正在探索相關作法，讓我們可以為稽核記錄提供較長的保留期間。 您可以在 [Office 365 使用者意見](https://office365.uservoice.com/forums/289138-office-365-security-compliance?category_id=137187) (英文) 中提供關於稽核記錄較長保留時間的意見反應。

**我的組織擁有 E5 訂閱，我是否需要執行任何動作才能存取 MailItemsAccessed 事件的稽核記錄？**

針對符合資格的客戶，您不需要採取任何動作就能存取 MailItemsAccessed 事件。 不過，如本主題先前所述，由於授權回填問題所造成的延遲，可能會造成稽核記錄搜尋無法傳回 MailItemsAccessed 事件的稽核記錄。 如果發生這種情況，請按照 [搜尋 MailItemsAccessed 稽核記錄] 一節中的指示進行。

**您是否計畫在今年推出其他事件？**

是的，我們計畫在未來幾個月內推出對調查來說至關重要的新事件。 接近推出日期時，我們會在 [Microsoft 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap)中公告這些新事件的相關資訊。

**Office 365 管理活動 API 的進階稽核中是否有新的事件？**

是。 只要為具有適當授權的使用者產生稽核記錄，您就可以透過 Office 365 管理活動 API 存取這些記錄。

**頻寬較高代表延遲較好或更高的 SLA 嗎？**

目前，高頻寬可提供更好的管道，特別是具有大量稽核訊號和大量消費模式的組織。 這可能會導致更好的延遲。 不過，SLA 與高頻寬無關。 標準延遲已予以記錄，且在進階稽核推出時不會變更。
