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
ms.openlocfilehash: 8bee0f368edc91b6f926eb6cb3e0a2f8dad81e9b
ms.sourcegitcommit: 9b79701eba081cd4b3263db7a15c088d92054b4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/17/2020
ms.locfileid: "42692650"
---
# <a name="learn-about-information-barriers"></a>深入瞭解資訊障礙

## <a name="overview"></a>概觀

Microsoft 雲端服務包含強大的通訊和協同作業功能。 不過，假設您想要限制兩個群組之間的通訊，以避免組織中發生利益衝突。 或者，您可能想要限制組織內特定人員之間的通訊，以保護內部資訊。 Microsoft 365 可跨群組和組織進行通訊及共同作業，所以有沒有方法可以限制特定使用者群組之間的通訊（必要時）？ 透過資訊障礙，您可以！ 

立即開始從 Microsoft 小組開始的資訊壁壘。 假設您的[訂閱](#required-licenses-and-permissions)包含資訊障礙，合規性管理員或資訊屏障管理員可以定義原則，以允許或防止 Microsoft 小組中的使用者群組之間的通訊。 資訊屏障原則可以用於下列情況：

- 天 trader 無法呼叫行銷小組的人員
- 從事機密公司資訊的融資人員無法從組織內的特定群組接收通話
- 內部團隊使用交易機密材料時，無法與組織內特定群組的人員線上通話或聊天
- 調查小組只能呼叫或與產品開發小組線上交談

針對上述所有範例案例（等等），您可以定義資訊屏障原則，以防止或允許 Microsoft 小組中的通訊。 這類原則可以防止使用者不應該來電或與其聊天，或讓使用者只能與 Microsoft 小組中的特定群組進行通訊。 透過資訊屏障原則，只要這些原則所涵蓋的使用者嘗試與 Microsoft 小組中的其他使用者通訊，便會進行檢查，以防止（或允許）通訊（如資訊屏障原則所定義）。 若要深入瞭解使用者對資訊障礙的經驗，請參閱[Microsoft 小組中的資訊障礙](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)。

> [!IMPORTANT]
> 目前，資訊障礙不會套用到電子郵件通訊或透過 SharePoint 線上或 OneDrive 共用檔案。 此外，資訊障礙獨立于[規範界限](set-up-compliance-boundaries.md)。<p>在您定義及套用資訊屏障原則之前，請確定您的組織沒有有效的[Exchange 通訊錄原則](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies)。 （資訊障礙是以通訊錄原則為基礎）。 

## <a name="what-happens-with-information-barriers"></a>資訊障礙發生什麼事

當資訊屏障原則到位時，不應與其他特定使用者通訊的使用者將無法找到、選取、聊天或呼叫這些使用者。 透過資訊障礙，檢查功能已到位，可防止未經授權的通訊。

資訊障礙最初隻適用于 Microsoft 小組聊天與通道。 在 Microsoft 小組中，資訊障礙原則決定並防止下列未授權的通訊類型：
- 搜尋使用者
- 新增成員至團隊
- 與某人開始聊天會話
- 開始群組聊天
- 邀請某人加入會議
- 共用畫面
- 撥打電話 

如果納入資訊屏障原則中的人員可防止活動，他們將無法繼續進行。 此外，包含在資訊屏障原則中的每一位使用者都有可能封鎖為與 Microsoft 小組中的其他人員進行通訊。 當以資訊障礙原則影響的人員屬於同一個小組或群組聊天時，可能會從這些聊天會話中移除，並且可能不允許與群組進一步通訊。

若要深入瞭解使用者對資訊障礙的經驗，請參閱[Microsoft 小組中的資訊障礙](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)。

## <a name="required-licenses-and-permissions"></a>必要的授權和權限

資訊壁壘現在正在推出，並包含在訂閱中，例如：

- Microsoft 365 E5
- Office 365 E5
- Office 365 進階合規性
- Microsoft 365 E5 資訊保護和合規性

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
