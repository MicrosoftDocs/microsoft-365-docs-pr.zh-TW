---
title: Microsoft 365 群組、小組和 SharePoint 共同作業的相容性選項
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: 深入瞭解 Microsoft 365 群組、小組和 SharePoint 共同作業的規範選項。
ms.openlocfilehash: 88083d88b274e750e0fc6f1907268c996312163c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920889"
---
# <a name="compliance-options-for-microsoft-365-groups-teams-and-sharepoint-collaboration"></a>Microsoft 365 群組、小組和 SharePoint 共同作業的相容性選項

Microsoft 365 提供全套工具，以在您的使用者共同作業時維持法規遵從性。 請查看這些選項，並考慮其如何對應至您的業務需求、資料敏感度，以及您的使用者需要共同作業的人員範圍。

下表提供 Microsoft 365 中可用之相容性控制措施的快速參考。 以下各節提供進一步的資訊。

|類別|描述|參考|
|:-------|:----------|:--------|
|資訊保留|||
||保留郵件和 SharePoint 內容的群組|[了解 SharePoint 和 OneDrive 的保留原則](../compliance/retention-policies-sharepoint.md)|
||保留聊天和訊息|[了解 Microsoft Teams 的保留原則](../compliance/retention-policies-teams.md)|
|資訊分類|||
||分類群組和團隊|[使用敏感度標籤來保護 Microsoft Teams、Microsoft 365 群組和 SharePoint 網站中的內容](../compliance/sensitivity-labels-teams-groups-sites.md)|
||自動分類敏感內容|[自動將敏感度標籤套用到內容](../compliance/apply-sensitivity-label-automatically.md)|
||加密敏感內容|[使用敏感度標籤來套用加密以限制存取內容](../compliance/encryption-sensitivity-labels.md)|
|資訊保護|||
||避免機密資訊遺失|[資料外洩防護概觀](../compliance/data-loss-prevention-policies.md)|
||保護聊天中的機密資訊。|[資料遺失防護和 Microsoft 團隊](../compliance/dlp-microsoft-teams.md)|
||定義組織的機密資訊|[自訂敏感性資訊類型](../compliance/sensitive-information-type-learn-about.md)|
|使用者區隔|||
||限制使用者區段之間的通訊|[資訊屏障](../compliance/information-barriers.md)|

## <a name="information-retention"></a>資訊保留

保留原則可用於保留或刪除群組和團隊中用於共同作業的專案，包括檔案、郵件和郵件。 原則可以設定為保留和刪除、只保留或僅刪除。 當群組或小組到期或刪除時，保留原則所涵蓋的資訊便會受到保護。

設定 Microsoft 365 群組的保留原則涵蓋群組信箱和相關聯的 SharePoint 網站與檔案。

- [了解 SharePoint 和 OneDrive 的保留原則](../compliance/retention-policies-sharepoint.md)

小組保留原則保留聊天及通道訊息。 雖然聊天和通道郵件會儲存在 Exchange 信箱中，但不會受到 Exchange 保留原則的影響。 您必須設定保留原則，以套用至小組聊天和小組通道郵件。 

即使刪除使用者帳戶，也會無限期保留使用者聊天。 如果您不想要無限期保留此資料，請考慮使用保留原則，在指定的時間之後刪除使用者聊天，或在使用者刪除程式中包含這項刪除。

- [了解 Microsoft Teams 的保留原則](../compliance/retention-policies-teams.md)

- [Microsoft Teams 中的保留原則](/microsoftteams/retention-policies)

單一保留原則可以設定為套用至 Microsoft 365 群組、小組聊天及小組通道訊息。 

其他資源：

- [了解保留原則](../compliance/retention.md)

- Exchange 中的[保留標記和保留原則](/exchange/security-and-compliance/messaging-records-management/retention-tags-and-policies)

## <a name="information-classification"></a>資訊分類

您可以使用敏感度標籤來管理「來賓存取」、「群組」和「小組」隱私權，以及由群組和小組的非管理裝置存取。 套用標籤時，這些設定會自動設定為由標籤設定所指定的設定。

- [使用敏感度標籤來保護 Microsoft Teams、Microsoft 365 群組和 SharePoint 網站中的內容](../compliance/sensitivity-labels-teams-groups-sites.md)

您可以根據您指定的準則，將 Microsoft 365 設定為自動將敏感度標籤套用至檔案和電子郵件，包括偵測敏感資訊類型或與 trainable 的分類器相符的模式。

- [自動將敏感度標籤套用到內容](../compliance/apply-sensitivity-label-automatically.md)

您可以使用敏感度標籤加密檔案，只允許具有解密及讀取這些檔案的許可權。

- [使用敏感度標籤來套用加密以限制存取內容](../compliance/encryption-sensitivity-labels.md)

- [為小組設定安全性隔離](./secure-teams-security-isolation.md)

其他資源：

- [了解敏感度標籤](../compliance/sensitivity-labels.md)


## <a name="information-protection"></a>資訊保護

DLP 原則可以防止在 SharePoint、Exchange 及小組之間意外共用敏感資訊。 您可以建立原則，指定要採取的動作 (例如依一組規則封鎖存取) 。

- [資料外洩防護概觀](../compliance/data-loss-prevention-policies.md)

當小組中的機密資訊包含機密資訊的郵件時，該小組可以協助保護小組聊天和通道郵件中的機密資訊。

- [資料遺失防護和 Microsoft 團隊](../compliance/dlp-microsoft-teams.md)

如果您的組織有獨特的敏感資訊，例如 project code 名稱，您可以建立您自己的機密資訊類型，並將其套用至 DLP 原則，以保護群組、小組和 Sharepoint 中的內容。

- [自訂敏感性資訊類型](../compliance/sensitive-information-type-learn-about.md)

## <a name="user-segmentation"></a>使用者區隔

透過資訊壁壘，您可以將資料和使用者分割，以限制群組之間不需要的通訊和共同作業，並避免組織中的利益衝突。 資訊障礙可讓您建立原則，以允許或防止組織中的人員群組之間的檔案共同作業、聊天、通話或會議邀請。

- [資訊屏障](../compliance/information-barriers.md)

- [Microsoft 小組的資訊障礙](/microsoftteams/information-barriers-in-teams)

- [SharePoint 使用資訊障礙](/sharepoint/information-barriers)

## <a name="related-topics"></a>相關主題

[共同作業管理規劃逐步](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[建立共同作業管理計畫](collaboration-governance-first.md)

[Exchange Online 的安全性和合規性](/exchange/security-and-compliance/security-and-compliance)

[保護資訊](../compliance/information-protection.md)