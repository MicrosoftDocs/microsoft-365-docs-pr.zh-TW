---
title: 針對 Microsoft 365 群組和 Microsoft 團隊規劃組織和生命週期管理
ms.reviewer: arvaradh
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
description: 有關 Microsoft 365 中的共同作業工具生命週期管理選項的精益
ms.openlocfilehash: 4d779701d241fc7178ab759063be1b8cdf2e960c
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613017"
---
# <a name="plan-organization-and-lifecycle-governance-for-microsoft-365-groups-and-microsoft-teams"></a>針對 Microsoft 365 群組和 Microsoft 團隊規劃組織和生命週期管理

Microsoft 365 群組具有一套豐富的工具，可實施組織所需的控管功能。 

下一節將說明功能、建議最佳作法，並提供指導方針，以判斷進行控管需求的適當問題，以及如何符合這些需求。

## <a name="control-who-can-create-microsoft-365-groups"></a>控制誰可以建立 Microsoft 365 群組

使用者可以從多個端點（包括 Outlook、SharePoint、小組及其他環境）建立群組。

![影像 desc](../media/04.png)

我們強烈建議使用自助功能群組擁有者，協助使用者更輕鬆地完成其工作。 限制群組和小組的建立會降低使用者的生產力，因為許多 Microsoft 365 服務都需要建立群組才能讓服務運作。

考慮建立群組的下列管理選項：

- 若要限制群組蔓延，請使用 [群組到期原則](microsoft-365-groups-expiration-policy.md) ，以自動刪除未使用的群組。
- 將群組建立功能限制為 [具有動態成員資格的安全性群組](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule) 成員，例如，所有的全職員工。
- 將群組建立限制在安全性群組中，並要求使用者在組織的群組使用原則中完成訓練，以便成為安全性群組的成員。

如果您想要限制誰可以建立群組，請參閱 [管理誰可以建立 Microsoft 365 群組](manage-creation-of-groups.md) ，以取得如何設定此內容的資訊。

## <a name="group-delete-restore-and-archiving"></a>群組刪除、還原及封存

刪除 Microsoft 365 群組時，預設會保留30天。 此 30 天期間稱為「虛刪除」，因為您仍可還原該群組。 30 天之後，該群組和關聯的內容將會被永久刪除，而且無法還原。

如果您有保留原則可保留聊天、檔案或郵件，將會在刪除群組之後保留這些專案。 如需詳細資訊，請參閱 [瞭解保留原則](https://docs.microsoft.com/microsoft-365/compliance/retention-policies) 。

如果您想要刪除群組，但保留一或多個群組聯機服務的內容，請參閱封存 [群組、小組和 Yammer](end-life-cycle-groups-teams-sites-yammer.md) 中的資訊。

## <a name="group-naming-policy"></a>群組命名原則

群組命名原則可協助您以兩種方式管理群組：

- 您可以使用首碼/尾碼命名原則，在組名的開頭或結尾（或其相關的電子郵件地址），強制執行固定字串或 Azure AD 屬性。 這樣一來，您就可以確保包含（例如，群組名稱中的部門名稱或地區名稱）。
- 「封鎖的字」原則可以確保在群組名稱中不會使用特定的字詞，例如主管的名稱。

當您從群組連線的任何服務建立群組時，會套用命名原則。

如果您決定使用群組的命名原則，請參閱 [Microsoft 365 群組命名原則](groups-naming-policy.md)。

## <a name="group-expiration-policy"></a>群組到期原則

您可以指定到期期限及任何超出該期間結束時間的群組，而且不會被更新。 到期期限是在建立群組時或在最後一次更新的日期時開始。

當您設定群組到期：
- 當到期臨近時，群組的擁有者會收到更新群組的通知。
- 自動更新主動群組。
- 任何未更新的群組都會被刪除。
- 任何刪除的群組可在30天內由群組擁有人或系統管理員復原。

到期原則是一種很好的方法，可確保刪除不再使用的群組，以限制群組大量蔓延。 如果您想要建立群組到期原則，請參閱 [Microsoft 365 群組到期原則](microsoft-365-groups-expiration-policy.md)。

## <a name="related-topics"></a>相關主題

[共同作業管理規劃逐步](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[建立共同作業管理計畫](collaboration-governance-first.md)
