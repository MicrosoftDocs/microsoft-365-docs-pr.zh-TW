---
title: 深入瞭解 Microsoft 365 中的資訊障礙
description: 使用資訊障礙，以確保在組織內使用 Microsoft Teams 來進行通訊法規遵從性。
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
localization_priority: None
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4ef3fce82a10792c8289a4a3c4e3cb5639a4d178
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051875"
---
# <a name="learn-about-information-barriers-in-microsoft-365"></a>深入瞭解 Microsoft 365 中的資訊障礙

Microsoft 雲端服務包括強大的通訊和共同作業功能。 不過，假設您想要限制兩個群組之間的通訊和共同作業，以避免組織中發生利益衝突。 或者，您可能想要限制組織內特定人員之間的通訊和共同作業，以保護內部資訊。 Microsoft 365 能夠跨群組和組織進行通訊及共同作業，所以有一個方法可以限制特定使用者群組之間的通訊和共同作業（必要時）？ 透過資訊障礙，您可以！

Microsoft Teams、SharePoint 線上及商務用 OneDrive 支援資訊障礙。 假設您的[訂閱](#required-licenses-and-permissions)包含資訊障礙、合規性管理員或資訊屏障管理員可以定義原則，以允許或防止 Microsoft Teams 中使用者群組之間的通訊。 資訊屏障原則可以用於下列情況：

- Day trader 群組中的使用者應該不會與行銷小組進行通訊或共用檔案
- 從事機密公司資訊的融資人員不應該與組織內的某些群組進行通訊或共用檔案
- 內部團隊使用貿易秘訣材料時，不應與組織內特定群組的人員線上通話或聊天
- 調查小組應只通話或與產品開發小組線上交談
- Day trader 群組的網站不得由 day trader 群組以外的任何人共用或存取

> [!IMPORTANT]
> 資訊障礙 ***只支援** _ 兩種方式限制。 單一的方式限制（例如，行銷）可以與日交易進行通訊及共同作業，但是 _不支援_ 使用「行銷」來進行通訊和合作

在所有上述範例案例中 (和更多) 時，可以定義資訊屏障原則，以防止或允許 Microsoft Teams 中的通訊及共同作業，SharePoint 線上及 OneDrive。 這類原則可以防止使用者不應該來電或與其聊天，或讓使用者只能與 Microsoft Teams 中的特定群組進行通訊。 透過資訊屏障原則，每當這些原則所涵蓋的使用者嘗試與 Microsoft Teams 中的其他使用者進行通訊及共同作業時，就會執行 SharePoint 線上或 OneDrive 檢查，以避免 (或允許) 的通訊及共同作業 (如資訊屏障原則所定義) 。

若要深入瞭解使用者對資訊障礙的經驗，請參閱：

- [Microsoft Teams 中的資訊屏障](/MicrosoftTeams/information-barriers-in-teams)
- [線上 SharePoint 的資訊障礙](/sharepoint/information-barriers)
- [OneDrive 中的資訊障礙](/onedrive/information-barriers)

> [!IMPORTANT]
> 目前資訊障礙不適用於電子郵件通訊。 此外，資訊障礙獨立于 [規範界限](set-up-compliance-boundaries.md)。<p> 在您定義及套用資訊屏障原則之前，請確定您的組織沒有作用中[Exchange 通訊錄原則](/exchange/address-books/address-book-policies/address-book-policies)。  (資訊障礙是以通訊錄原則為基礎。 ) 

## <a name="what-happens-with-information-barriers"></a>資訊障礙發生什麼事

當資訊屏障原則到位時，不應該與其他特定使用者通訊或共用檔案的使用者將無法找到、選取、聊天或呼叫這些使用者。 透過資訊障礙，檢查功能已到位，可防止未經授權的通訊和協同作業。 

資訊障礙適用于 Microsoft Teams (聊天和頻道) ，SharePoint 線上及 OneDrive。 在 Microsoft Teams 中，資訊屏障原則決定並防止以下種類的未經授權的通訊：

- 搜尋使用者
- 新增成員至團隊
- 開始與其他人的聊天工作階段
- 開始群組聊天
- 邀請其他人加入會議
- 共用螢幕
- 撥打電話
- 與其他使用者共用檔案
- 透過共用連結存取檔案

如果將相關人員包括在資訊屏障原則中以阻止活動，則他們將無法繼續進行。 此外，系統可能已將資訊屏障原則中包含的每個人封鎖，無法與 Microsoft Teams 中的其他人通訊。 當受到資訊屏障原則影響的人員屬於同一個小組或群組聊天時，系統可能會從這些聊天工作階段中移除這些人員，而且這些人可能無法與群組進一步通訊。

若要深入瞭解資訊障礙的使用者經驗，請參閱[Microsoft Teams 中的資訊障礙](/MicrosoftTeams/information-barriers-in-teams)。

在 SharePoint Online 和 OneDrive 中，資訊屏障原則會決定並防止下列類型的未授權共同作業：

- 將成員新增至網站
- 依使用者存取網站或內容
- 與其他使用者共用網站或內容
- 搜尋網站

若要深入瞭解資訊障礙的使用者經驗，請參閱[SharePoint Online 中的資訊障礙](/sharepoint/information-barriers)。

## <a name="required-licenses-and-permissions"></a>必要的授權和權限

資訊壁壘現在正在推出，並包含在訂閱中，例如：

- Microsoft 365 E5/A5
- Office 365E5/A5
- Office 365 進階合規性
- Microsoft 365規範 E5/A5
- Microsoft 365 內部風險管理

如需詳細資訊，請參閱[Microsoft 365 授權指南以取得安全性 & 相容性](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)。

若要 [定義或編輯資訊障礙原則](information-barriers-policies.md)，您必須被指派下列其中一個角色：

- Office 365 全域系統管理員
- Office 365 全域系統管理員
- 合規性管理員
- IB 合規性管理

 (若要深入瞭解角色和許可權，請參閱[Office 365 Security & 合規性中心的許可權](../security/defender-365-security/permissions-in-the-security-and-compliance-center.md)。 ) 

您必須熟悉 PowerShell Cmdlet，才能定義、驗證或編輯資訊障礙原則。 雖然我們在操作 [方法文章](information-barriers-policies.md)中提供了幾個 PowerShell Cmdlet 範例，但您將需要知道組織的其他詳細資料，例如參數。

## <a name="next-steps"></a>後續步驟

- [深入瞭解 Microsoft Teams 中的資訊障礙](/MicrosoftTeams/information-barriers-in-teams)
- [深入瞭解 SharePoint 線上中的資訊障礙](/sharepoint/information-barriers)
- [深入瞭解 OneDrive 中的資訊障礙](/onedrive/information-barriers)
- [請參閱可用於資訊障礙原則的屬性](information-barriers-attributes.md)
- [定義資訊屏障的原則](information-barriers-policies.md)
- [編輯 (或移除) 資訊屏障原則](information-barriers-edit-segments-policies.md)