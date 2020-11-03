---
title: 自動調查和回應 (AIR) -快速入門
keywords: AIR, autoIR, ATP, 自動化, 調查, 回應, 修正, 威脅, 進階, 威脅, 保護
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 09/29/2020
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: 開始使用 Microsoft Defender for Office 365 中的自動調查和回應功能。
ms.custom:
- air
- seo-marvel-mar2020
ms.openlocfilehash: 54dbd419380c18e23119887c93a71885c6f9ce7d
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/03/2020
ms.locfileid: "48845801"
---
# <a name="get-started-using-automated-investigation-and-response-air-in-office-365"></a>開始使用 Office 365 中的自動調查和回應 (AIR) 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

[Microsoft Defender For Office 365](office-365-atp.md) 包含強大的自動化調查和回應 (空氣) 功能，可節約您的安全性運作小組時間和工作。 當觸發警示時，您的安全性作業小組會檢查、優先順序及回應這些警示。 保持傳入提醒的數量非常驚人。 自動化某些部分可提供協助。 透過 AIR，您的安全性運作小組可以專注于優先順序較高的工作，而不會失去所觸發之警示的視線。

本文包括：
- 空氣的 [整體流向](#the-overall-flow-of-air) ;
- [如何取得空氣](#how-to-get-air);和 
- 設定或使用 AIR 功能 [所需的許可權](#required-permissions-to-use-air-capabilities) 。 

## <a name="the-overall-flow-of-air"></a>空氣的整體流動

在高層次上會觸發警示，安全性行動手冊會開始進行自動調查，進而會產生結果和建議。 以下是空氣的整體流動流程，逐步執行：

1. 自動調查是以下列其中一種方式啟動：

   - 由 Office 事件觸發 [警示](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) ，以建立事件。 根據事件種類而定， [安全性行動手冊](automated-investigation-response-office.md#security-playbooks) 會開始進行自動調查。 

     --- 或 ---
   
   - 安全分析員會在使用[威脅瀏覽器](threat-explorer.md)時[開始自動調查](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)。

2. 當自動調查執行時，它會收集有關電子郵件的其他資料，以及與該電子郵件相關的實體。 這類實體可以包含檔案、URLs 及收件者。  調查的範圍會隨著新的和相關的提醒觸發而增加。

3. 在自動調查的期間和之後，都可以查看 [詳細資料和結果](air-view-investigation-results.md) 。 結果包括可以採取以回應和修正任何找到之威脅的 [建議動作](air-remediation-actions.md) 。 此外，也可以使用 [行動手冊記錄](air-view-investigation-results.md#playbook-log) 來追蹤所有調查活動。

    如果您的組織使用自訂報告解決方案或協力廠商解決方案，您可以 [使用 Office 365 管理活動 API](air-custom-reporting.md) 來查看有關自動化調查和威脅的資訊。

4. 您的安全性運作小組會檢查 [調查結果和建議](air-view-investigation-results.md)，並 [批准或拒絕修正動作](air-review-approve-pending-completed-actions.md)。 

    當擱置的修復動作獲批准 (或拒絕) 時，自動調查即完成。

> [!NOTE]
> 在適用于 Office 365 的 Microsoft Defender 中，不會自動採取任何修正動作。 在組織的安全性小組核准後才能採取補救動作。 

在自動化調查程序期間及之後，您的安全性小組可以執行下列動作：

- [檢視與調查相關警示的詳細資料](air-view-investigation-results.md#view-details-about-an-alert-related-to-an-investigation)

- [查看調查的結果詳細資料](air-view-investigation-results.md#view-details-of-an-investigation)

- [根據調查的結果檢閱和核准動作](air-review-approve-pending-completed-actions.md)

> [!TIP]
> 如需詳細資訊，請參閱 [AIR 的運作方式](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office)。

## <a name="how-to-get-air"></a>如何取得空中

AIR 功能包含在 [適用于 Office 365 的 Microsoft Defender](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2)中。 不過，您 [必須設定](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats) 您的原則，AIR 才能如期運作。 此外，請務必複查並可能設定組織的 [警示原則](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)。 

Microsoft 365 提供許多內建的警示原則，可協助識別 Exchange 系統管理員許可權濫用、惡意程式碼活動、潛在的外部和內部威脅，以及資訊控管風險。 某些預設的 [報警原則](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#default-alert-policies) 可以觸發自動調查。 包括下列各項：

- 偵測到可能的惡意 URL 按一下

- 使用者將電子郵件訊息當做網路釣魚詐騙進行報告

- 傳遞後移除包含惡意程式碼的電子郵件

- 傳遞後移除包含網路釣魚 URLs 的電子郵件

- 偵測到可疑的電子郵件寄送模式

- 限制使用者傳送電子郵件

[深入瞭解警示和空中](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office)。

## <a name="required-permissions-to-use-air-capabilities"></a>使用 AIR 功能所需的許可權

許可權是透過特定角色授與的，如下表所述： 

|工作 |需要) 角色 ( |
|--|--|
|設定 AIR 功能 |下列其中一個角色： <br/>-全域管理員<br/>-安全性管理員 <br/>您可以在 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) 或 [Security & 合規性中心](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)指派這些角色。 |
|核准或拒絕建議的動作|在 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) 或 [Security & 合規性中心](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center) 內指派的下列其中一個角色) ：<br/>-全域管理員 <br/>-安全性管理員<br/>-安全性讀取器 <br/>--- 且 ---<br/>-搜尋和清除 (此角色只會指派在 [安全性 & 規範中心](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)。 您可能需要建立新的角色群組，並將搜尋和清除角色新增至該新的角色群組。 ) 

若要將[Microsoft Defender For Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2)授權指派給：
- 安全性管理員 (包括全域管理員) 
- 組織的安全性運作小組 (包括安全性讀者和具有搜尋和清除角色的使用者) 
- 使用者

此外，必須定義及套用 [Microsoft Defender For Office 365 原則](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) ，才能進行保護。

## <a name="next-steps"></a>後續步驟

- [查看自動調查的詳細資料和結果](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-view-investigation-results#view-details-of-an-investigation)

- [審閱及核准擱置的動作](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-remediation-actions)

## <a name="related-articles"></a>相關文章

- [Microsoft Defender for Endpoint 中的自動調查和修正](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Microsoft 365 Defender 的自動化調查和回應](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
