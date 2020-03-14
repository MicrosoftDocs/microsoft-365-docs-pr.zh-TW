---
title: Office 365 中的自動化調查和回應（AIR）
keywords: AIR, autoIR, ATP, 自動化, 調查, 回應, 修正, 威脅, 進階, 威脅, 保護
f1.keywords:
- NOCSH
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
ms.custom: air
ms.openlocfilehash: c06874ea5d55334d9049d6c5d9d5c55a499dae06
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/13/2020
ms.locfileid: "42634021"
---
# <a name="automated-investigation-and-response-air-in-office-365"></a>Office 365 中的自動化調查和回應（AIR）

[Office 365 高級威脅防護](office-365-atp.md)方案2包含強大的自動化調查和回應（空氣）功能，可儲存您的安全性運作小組時間和工作。 觸發特定警示時，會啟動一或多個安全性行動手冊，並且自動調查過程開始。 這可讓您的安全性運作小組專注于高優先順序的工作，而不會失去所觸發之警示的視線。 

## <a name="the-overall-flow-of-air"></a>空氣的整體流動

會觸發警示，並會啟動安全性行動手冊，以啟動自動調查。 或者，安全性分析員會在使用威脅瀏覽器時觸發自動調查。 自動調查會執行，通常會識別某些修正動作。 這些動作會透過安全性作業小組進行審閱和核准，而且調查完成。 

下表逐步逐步整個氣流流程：

|步驟  |會發生什麼事  |
|---------|---------|
|1      |由 Office 事件觸發的警示和[安全性行動手冊](automated-investigation-response-office.md#security-playbooks)會為選取的提醒開始自動調查。 <br/><br/>或者，安全性分析員可以在使用[威脅瀏覽器](threat-explorer.md)時[觸發自動調查](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)。        |
|2      |當自動調查執行時，它會收集有關電子郵件和與該電子郵件相關之實體的其他資料–檔案、URLs 及收件者。  調查的範圍可能會增加，因為會觸發新的相關警示。         |
|3      |在自動調查的期間和之後，都可以查看[詳細資料和結果](air-view-investigation-results.md)。 結果包括可以採取以回應和修正任何找到之威脅的[建議動作](air-remediation-actions.md)。 此外，也可以使用[行動手冊記錄](air-view-investigation-results.md#playbook-log)來追蹤所有調查活動。<br/><br/>如果您的組織使用自訂報告解決方案或協力廠商解決方案，您可以[使用 Office 365 管理活動 API](air-custom-reporting.md)來查看有關自動化調查和威脅的資訊。         |
|4      |您的安全性運作小組會檢查[調查結果和建議](air-view-investigation-results.md)，並[核准修正動作](air-remediation-actions.md#approve-or-reject-pending-actions)。 在 Office 365 中，不會自動採取任何動作。 只有組織的安全小組核准時，才會採取補救措施。         |

在自動化調查程序期間及之後，您的安全性小組可以執行下列動作：

- [檢視與調查相關警示的詳細資料](air-view-investigation-results.md#view-details-about-an-alert-related-to-an-investigation)
- [查看調查的結果詳細資料](air-view-investigation-results.md#view-details-of-an-investigation)
- [根據調查的結果檢閱和核准動作](air-remediation-actions.md#approve-or-reject-pending-actions)

若要深入瞭解，請參閱[AIR 的運作方式](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office)。

## <a name="how-to-get-air"></a>如何取得空中

Office 365 AIR 現在包含在以下訂閱中：

- Microsoft 365 E5
- Office 365 E5
- Microsoft 威脅防護
- Office 365 進階威脅防護方案 2

如果您沒有上述任何訂閱，請[啟動免費試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279&culture=en-US&country=US)。

若要深入瞭解功能可用性，請流覽[各種高級威脅防護（ATP）方案中的功能可用性](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)。

## <a name="required-permissions-to-use-air-capabilities"></a>使用 AIR 功能所需的許可權

許可權是透過特定角色授與的，如下表所述： 

|工作 |需要角色 |
|--|--|
|設定 AIR 功能 |下列其中一個角色： <br/>- **全域管理員**<br/>- **安全性管理員** <br/>您可以在[Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)或[Office 365 Security & 合規性中心](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)指派這些角色。 |
|核准或拒絕建議的動作|在[Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)或[Office 365 Security & 合規性中心](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)中指派的下列其中一個角色：<br/>- **全域管理員** <br/>- **安全性管理員**<br/>- **安全性讀取器** <br/>--- 且 ---<br/>- **搜尋和清除**（此角色只會指派在[Office 365 安全性 & 合規性中心](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)。 您可能需要建立新的角色群組，並將搜尋和清除角色新增至該新的角色群組。）

## <a name="related-articles"></a>相關文章

- [Microsoft 威脅防護的自動化調查及回應](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)

- [Microsoft Defender 高級威脅防護中的自動化調查和修復](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)