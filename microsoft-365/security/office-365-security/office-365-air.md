---
title: 自動化調查和回應（AIR）
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
ms.openlocfilehash: 3b7ddd88161b695e8929b749dac61d7947392a0d
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634541"
---
# <a name="automated-investigation-and-response-air"></a>自動化調查和回應（AIR）

[Office 365 高級威脅防護](office-365-atp.md)（OFFICE 365 ATP）方案2包含強大的自動化調查和回應（空氣）功能，可儲存您的安全性運作小組時間和工作。 當觸發警示時，您的安全性作業小組會檢查、優先順序及回應這些警示。 保持傳入提醒的數量非常驚人。 自動化某些部分可提供協助。 透過 AIR，您的安全性運作小組可以專注于優先順序較高的工作，而不會失去所觸發之警示的視線。

本文說明空氣的[整體流動](#the-overall-flow-of-air)，[如何取得 air](#how-to-get-air)，以及設定或使用 AIR 功能[所需的許可權](#required-permissions-to-use-air-capabilities)。 

## <a name="the-overall-flow-of-air"></a>空氣的整體流動

在高層次，會觸發警示，安全性行動手冊會開始和自動調查，進而會產生結果和建議。 以下是空氣的整體流動流程，逐步執行：

1. 自動調查是以下列其中一種方式啟動：

   - 由 Office 事件觸發[警示](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)，以建立事件。 根據事件種類而定，[安全性行動手冊](automated-investigation-response-office.md#security-playbooks)會開始進行自動調查。 

     --- 或 ---
   
   - 安全分析員會在使用[威脅瀏覽器](threat-explorer.md)時[開始自動調查](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)。

2. 當自動調查執行時，它會收集有關電子郵件的其他資料，以及與該電子郵件相關的實體。 這類實體可以包含檔案、URLs 及收件者。  調查的範圍會隨著新的和相關的提醒觸發而增加。

3. 在自動調查的期間和之後，都可以查看[詳細資料和結果](air-view-investigation-results.md)。 結果包括可以採取以回應和修正任何找到之威脅的[建議動作](air-remediation-actions.md)。 此外，也可以使用[行動手冊記錄](air-view-investigation-results.md#playbook-log)來追蹤所有調查活動。

    如果您的組織使用自訂報告解決方案或協力廠商解決方案，您可以[使用 Office 365 管理活動 API](air-custom-reporting.md)來查看有關自動化調查和威脅的資訊。

4. 您的安全性運作小組會檢查[調查結果和建議](air-view-investigation-results.md)，並[批准或拒絕修正動作](air-review-approve-pending-completed-actions.md)。 

    當未決修正動作經核准（或拒絕）時，自動調查完成。

> [!NOTE]
> 在 Office 365 ATP 中，不會自動採取任何修正動作。 只有組織的安全小組核准時，才會採取補救措施。 

在自動化調查程序期間及之後，您的安全性小組可以執行下列動作：

- [檢視與調查相關警示的詳細資料](air-view-investigation-results.md#view-details-about-an-alert-related-to-an-investigation)

- [查看調查的結果詳細資料](air-view-investigation-results.md#view-details-of-an-investigation)

- [根據調查的結果檢閱和核准動作](air-review-approve-pending-completed-actions.md)

> [!TIP]
> 如需詳細資訊，請參閱[AIR 的運作方式](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office)。

## <a name="how-to-get-air"></a>如何取得空中

Office 365 的 AIR 功能包含在[office 365 高級威脅防護方案 2](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2)。 不過，您[應設定 Office 365 ATP 原則](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)，讓 AIR 如預期般運作。 此外，請務必複查並可能設定組織的[警示原則](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)。 

Microsoft 365 提供許多內建的警示原則，可協助識別 Exchange 系統管理員許可權濫用、惡意程式碼活動、潛在的外部和內部威脅，以及資訊控管風險。 某些預設的[報警原則](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#default-alert-policies)可以觸發自動調查。 包括下列各項：

- 偵測到可能的惡意 URL 按一下

- 使用者將電子郵件訊息當做網路釣魚詐騙進行報告

- 傳遞後移除包含惡意程式碼的電子郵件

- 傳遞後移除包含網路釣魚 URLs 的電子郵件

- 偵測到可疑的電子郵件寄送模式

- 限制使用者傳送電子郵件

[深入瞭解警示和空中](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office)。

## <a name="required-permissions-to-use-air-capabilities"></a>使用 AIR 功能所需的許可權

許可權是透過特定角色授與的，如下表所述： 

|工作 |需要角色 |
|--|--|
|設定 AIR 功能 |下列其中一個角色： <br/>-全域管理員<br/>-安全性管理員 <br/>您可以在[Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)或[Security & 合規性中心](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)指派這些角色。 |
|核准或拒絕建議的動作|在[Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)或[Security & 合規性中心](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)內指派的下列角色之一：<br/>-全域管理員 <br/>-安全性管理員<br/>-安全性讀取器 <br/>--- 且 ---<br/>-搜尋和清除（此角色只會指派在[安全性 & 合規性中心](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)。 您可能需要建立新的角色群組，並將搜尋和清除角色新增至該新的角色群組。）

## <a name="next-steps"></a>後續步驟

- [查看自動調查的詳細資料和結果](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-view-investigation-results#view-details-of-an-investigation)

- [審閱及核准擱置的動作](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-remediation-actions)

## <a name="related-articles"></a>相關文章

- [Microsoft Defender 高級威脅防護中的自動化調查和修復](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Microsoft 威脅防護的自動化調查及回應](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
