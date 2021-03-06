---
title: Microsoft Viva 主題安全性和隱私權
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye, cjtan
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: 瞭解如何規劃 Microsoft Viva 主題安全性和隱私權
ms.openlocfilehash: b8c82b1914df739ea9086a4ce1585733a7b6d854
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925488"
---
# <a name="microsoft-viva-topics-security-and-privacy"></a>Microsoft Viva 主題安全性和隱私權

主題使用 Microsoft 365 中的現有內容安全性功能，以及系統管理控制，以控制向組織中的使用者顯示的 AI 產生的內容。 Microsoft 365 安全性設定的組合 (網站、檔案及資料夾的許可權) 和主題管理員設定，以判斷特定使用者可在主題中看到的內容。

設定主題不會修改組織中內容的任何現有存取控制。 使用者只會看到他們具有存取權的項目。

本文說明主題如何從安全性的角度，以及知識管理員和知識主管控制主題可見度的選項。 如需 [規劃主題](plan-topic-experiences.md)，請閱讀本文。

閱讀本文之前，您[](topic-experiences-overview.md)應該熟悉主題中心、[主題中心](topic-center-overview.md)及如何使用主題[中心的主題](manage-topics.md)。

## <a name="what-users-can-see-in-topics"></a>使用者可以在主題中看到的內容

若要查看主題，使用者必須：

- 具有 Viva 主題授權
- 是 [主題檢視器](topic-experiences-knowledge-rules.md#change-who-can-see-topics-in-your-organization)、 [投稿人或知識管理員](topic-experiences-user-permissions.md)

這兩個專案可讓使用者查看主題中心的存取權，並允許他們查看醒目提示和主題卡片。

主題參與者此外，還擁有主題的 [建立和編輯](topic-experiences-user-permissions.md) 許可權，而且知識管理員可以確認或移除主題。

第一次探索一個主題時，知識管理員可以在主題中心看到該主題。 根據主題的完整性與相關性，主題檢視器可能會顯示主題卡片中所述的主題，也可能看不到。

主題可以包含 AI 所產生的資訊，以及主題投稿者或知識主管新增或編輯的資訊。

- AI 新增的主題資訊只有擁有來源內容存取權的人才能看到。
- 由主題投稿人或知識管理員手動新增或編輯的文字，可供每個可以查看該主題的人看到。

主題檢視器和參與者可以在主題中心看到已確認及已發佈的主題清單，但特定人員可以查看的主題詳細資料，取決於他們對來源材質所擁有的許可權，以及是否已手動編輯該主題。

下表說明哪些使用者-主題查看者、投稿人和知識管理員-根據其許可權，可在指定的主題中查看。

|主題項目|使用者可以看到的內容|
|:---------|:------------------|
|主題名稱|使用者可以查看主題中心主題的主題名稱。 若使用者沒有來源內容的許可權或對使用者的關聯性很低，某些主題可能不會顯示。|
|主題描述|僅具有來源內容存取權限的使用者可以看到 AI 產生的描述。 所有使用者都可以看到手動輸入或編輯的描述。|
|人員|所有使用者都可以看到釘選人員。 僅具有來源內容存取權限的使用者可以看到建議人員。|
|檔案|僅具有來源內容存取權限的使用者可以看到檔案。|
|頁面|僅具有來源內容存取權限的使用者可以看到頁面。|
|網站|僅具有來源內容存取權限的使用者可以看到網站。|

## <a name="users-personal-and-private-data"></a>使用者的個人及私人資料

Viva 主題只會在您指定的 SharePoint 網站中探索主題。 不會包含使用者的個人儲存區，例如個人郵件或 OneDrive。

## <a name="best-practices"></a>最佳做法

主題根據使用者對內容的現有許可權，向使用者顯示資訊。 Microsoft 365 提供各種方式，以確保將敏感內容限制于適當的使用者。 除了標準小組或網站許可權之外，您還可以使用 [敏感度標籤](../compliance/sensitivity-labels.md) 或 [資料遺失防護](../compliance/dlp-learn-about-dlp.md) 來限制存取內容和 [存取權](/azure/active-directory/governance/access-reviews-overview) ，以定期查看使用者對機密資訊的存取權。

建議您使用這些工具，以確保您的內容許可權已在組織內適當地設定。 然後主題體驗可以為您的使用者提供實用且適當的資訊。

如果您想要從主題體驗完全排除的主題，您也可以：

- [從主題探索中排除敏感的 SharePoint 網站](topic-experiences-discovery.md#select-sharepoint-topic-sources)。 這些網站中的內容不會出現在主題體驗中。

- [依名稱排除主題](topic-experiences-discovery.md#exclude-topics-by-name)。 明確排除的主題不會出現在主題體驗中。

- 讓知識管理員移除主題中心的主題。

此外，我們建議採用下列最佳作法：

- 招聘組織中不同區域的知識經理。 具有各種專業知識的知識管理員和透過 AI 所使用之基礎內容的存取權，可協助您為使用者 curate 最有用的知識，以及移除機密資訊（如果找到的話）。

- 設定要求變更的工作流程。 知識管理員或小組或網站擁有者應該有一個程式，可讓使用者在組織內啟動新的專案時，或發現具有不適當權限設定的內容時，要求排除主題或網站。

- 建立主題描述時，請注意對象和資訊的敏感性。 沒有主題來源內容權限的使用者可能會看到這些描述。

雖然您可以變更個別主題頁面上的權限，以縮小特定使用者群組的存取權，但是因為需要高度的系統管理工作，所以我們不建議這個方法。

## <a name="see-also"></a>另請參閱

[為 Teams 設定三層保護](../solutions/configure-teams-three-tiers-protection.md)

[計劃主題體驗](plan-topic-experiences.md)

[設定主題體驗](set-up-topic-experiences.md)
