---
title: 深入瞭解資訊障礙
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/08/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: 使用資訊障礙，以確保您的組織內的 Microsoft 小組能夠進行通訊法規遵從性。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f723885a366e6f92f29faccfb632677c6e0028c8
ms.sourcegitcommit: 583fd1ac1f385c58b93bda648907a1bd8e0a1950
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/28/2020
ms.locfileid: "45430221"
---
# <a name="information-barriers"></a>資訊屏障

Microsoft 雲端服務包含強大的通訊和協同作業功能。 不過，假設您想要限制兩個群組之間的通訊和共同作業，以避免組織中發生利益衝突。 或者，您可能想要限制組織內特定人員之間的通訊和共同作業，以保護內部資訊。 Microsoft 365 可跨群組和組織進行通訊及共同作業，所以有一種方式可以限制特定使用者群組之間的通訊和共同作業（必要時）？ 透過資訊障礙，您可以！ 

資訊障礙現在已在 Microsoft 小組、SharePoint 線上和商務 OneDrive 支援。 假設您的[訂閱](#required-licenses-and-permissions)包含資訊障礙，合規性管理員或資訊屏障管理員可以定義原則，以允許或防止 Microsoft 小組中的使用者群組之間的通訊。 資訊屏障原則可以用於下列情況：

- Day trader 群組中的使用者應該不會與行銷小組進行通訊或共用檔案
- 從事機密公司資訊的融資人員不應該與組織內的某些群組進行通訊或共用檔案
- 內部團隊使用貿易秘訣材料時，不應與組織內特定群組的人員線上通話或聊天
- 調查小組應只通話或與產品開發小組線上交談

> [!IMPORTANT]
> 資訊障礙***只支援***兩種方式限制。 一種方式限制，例如「行銷」可以與日商貿通訊，但無法與行銷進行***通訊。***

針對上述所有範例案例（等等），您可以定義資訊屏障原則，以防止或允許 Microsoft 小組中的通訊。 這類原則可以防止使用者不應該來電或與其聊天，或讓使用者只能與 Microsoft 小組中的特定群組進行通訊。 透過資訊屏障原則，只要這些原則所涵蓋的使用者嘗試與 Microsoft 小組中的其他使用者通訊，便會進行檢查，以防止（或允許）通訊（如資訊屏障原則所定義）。 若要深入瞭解使用者對資訊障礙的經驗，請參閱[Microsoft 小組中的資訊障礙](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)。

> [!IMPORTANT]
> 目前資訊障礙不適用於電子郵件通訊。 此外，資訊障礙獨立于[規範界限](set-up-compliance-boundaries.md)。<p>在您定義及套用資訊屏障原則之前，請確定您的組織沒有有效的[Exchange 通訊錄原則](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies)。 （資訊障礙是以通訊錄原則為基礎）。 

## <a name="what-happens-with-information-barriers"></a>資訊障礙發生什麼事

當資訊屏障原則到位時，不應該與其他特定使用者通訊或共用檔案的使用者將無法找到、選取、聊天或呼叫這些使用者。 透過資訊障礙，檢查功能已到位，可防止未經授權的通訊。

資訊障礙最初隻適用于 Microsoft 小組聊天與通道。 在 Microsoft 小組中，資訊障礙原則決定並防止下列未授權的通訊類型：

- 搜尋使用者
- 新增成員至團隊
- 與某人開始聊天會話
- 開始群組聊天
- 邀請某人加入會議
- 共用畫面
- 撥打電話
- 與其他使用者共用檔案
- 透過共用連結存取檔案 

如果納入資訊屏障原則中的人員可防止活動，他們將無法繼續進行。 此外，包含在資訊屏障原則中的每一位使用者都有可能封鎖為與 Microsoft 小組中的其他人員進行通訊。 當以資訊障礙原則影響的人員屬於同一個小組或群組聊天時，可能會從這些聊天會話中移除，並且可能不允許與群組進一步通訊。

若要深入瞭解使用者對資訊障礙的經驗，請參閱[Microsoft 小組中的資訊障礙](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)。

## <a name="required-licenses-and-permissions"></a>必要的授權和權限

資訊壁壘現在正在推出，並包含在訂閱中，例如：

- Microsoft 365 E5/A5
- Office 365 E5/A5
- Office 365 進階合規性
- Microsoft 365 規範 E5/A5
- Microsoft 365 有問必答風險管理

如需詳細資訊，請參閱[規範解決方案](https://products.office.com/business/security-and-compliance/compliance-solutions)。

若要[定義或編輯資訊障礙原則](information-barriers-policies.md)，您必須被指派下列其中一個角色：

- Microsoft 365 全域系統管理員
- Office 365 全域系統管理員
- 合規性管理員
- IB 相容性管理（這是新的角色！）

（若要深入瞭解角色和許可權，請參閱[Office 365 Security & 合規性中心的許可權](../security/office-365-security/protect-against-threats.md)。）

您必須熟悉 PowerShell Cmdlet，才能定義、驗證或編輯資訊障礙原則。 雖然我們在操作[方法文章](information-barriers-policies.md)中提供了幾個 PowerShell Cmdlet 範例，但您將需要知道組織的其他詳細資料，例如參數。

## <a name="next-steps"></a>後續步驟

- [深入瞭解 Microsoft 小組中的資訊障礙](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)
- [請參閱可用於資訊障礙原則的屬性](information-barriers-attributes.md)
- [定義資訊障礙的原則](information-barriers-policies.md)
- [編輯（或移除）資訊屏障原則](information-barriers-edit-segments-policies.md)
- [深入瞭解 SharePoint 線上中的資訊障礙](https://docs.microsoft.com/sharepoint/information-barriers)
- [深入瞭解 OneDrive 商務中的資訊障礙](https://docs.microsoft.com/onedrive/information-barriers)