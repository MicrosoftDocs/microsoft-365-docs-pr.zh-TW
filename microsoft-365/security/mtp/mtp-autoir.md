---
title: Microsoft 威脅防護中的自動化調查和回應功能
description: Microsoft 威脅防護的自動化調查及回應功能的概
keywords: automated, investigation, alert, trigger, action, remediation, 自動化, 調查, 警示, 觸發, 動作, 補救
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 6ac6d74b027cc533f689c1d67c7fce246c73984f
ms.sourcegitcommit: 46644f9778bc70ab6d62783e0a1e60ba2eccc27f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/08/2020
ms.locfileid: "44166158"
---
# <a name="automated-investigation-and-response-air-capabilities-in-microsoft-threat-protection"></a>Microsoft 威脅防護中的自動化調查和回應（AIR）功能

**適用於：**
- Microsoft 威脅防護

在觸發安全性警示時，您的安全性運作小組會檢查這些警示，並採取步驟來保護您的組織。 優先處理和調查警示可能會非常耗時，特別是在調查進行時新警示持續出現。 安全性作業小組可能會對必須監控和防範的龐大威脅感到不知所措。 Microsoft 威脅防護中的自動化調查和回應（AIR）功能可能會有所説明。 AIR 就像是在安全性作業中心的虛擬分析員。

## <a name="your-virtual-analyst"></a>您的虛擬分析員

想像您的第 1 層 / 第 2 層安全性作業小組中有一個虛擬分析員。 虛擬分析員會模仿安全性作業要採取哪些理想步驟來調查和補救威脅。 虛擬助理可以全天候工作、提供無限能力，以及接受大量調查和威脅補救。 如此一來，虛擬助理可以大幅減少回應時間，讓您的安全性作業小組能夠進行其他重要的策略專案。 如果此案例好像是科學 fiction，就不是！ 這類虛擬分析員是屬於您的 Microsoft 威脅防護套件，其名稱為*自動化調查及回應* (AIR)。

AIR 可讓您的安全性作業小組大幅增加貴組織處理安全性警示和事件的能力。 透過 AIR，您可以降低處理調查和補救活動的成本，並充分利用威脅防護套件。 AIR 協助您的安全性作業小組：

1. 判斷是否要針對威脅採取動作；
2. 執行 (或建議) 任何必要補救動作；
3. 判斷應該要進行哪些其他調查；以及
4. 針對其他警示重複採取必要程序。

## <a name="the-automated-investigation-process"></a>自動化調查程序

**警示** > **事件** > **自動化調查** > **結果** > **補救動作**

觸發的警示會建立事件，以開始自動調查。 該調查會產生一或多個補救動作。 在 Microsoft 威脅防護中，每個自動化調查會與 Azure 進階威脅防護 (Azure ATP)、Microsoft Defender 進階威脅防護 (Microsoft Defender ATP) 和 Office 365 進階威脅防護 (Office 365 ATP) 的訊號有關聯，如下表所示： 

|實體 |威脅防護服務  |
|---------|---------|
|裝置 (也稱為端點)     |[Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)<br/>[Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) |      
|電子郵件內容 (信箱中的檔案和郵件)     |[Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)         |

每個調查都會針對每個證據調查產生 verdicts （未找到*惡意*、*可疑*或*無威脅*）。 根據威脅類型和產生的判定，您的組織的安全性運作小組會自動或核准執行修正動作。 待處理和已完成的操作會列在[重要訊息中心](mtp-action-center.md)。

> [!TIP]
> 如果您認為 Microsoft 威脅防護中的自動調查和回應功能已錯過或錯誤地偵測到某項功能，請告訴我們！ 請參閱[如何在 Microsoft 威脅防護中，以自動化調查和回應（AIR）功能來報告誤報/負片](mtp-autoir-report-false-positives-negatives.md)。

當調查進行時，出現的任何其他相關警示會新增到調查中，直到調查完成。 如果在其他地方看到受感染的實體，則自動化調查將擴大其範圍，以包括該實體，並且將執行一般安全性劇本。 

> [!NOTE]
> 並非每個警式都會觸發自動化調查，也不是每個調查都會產生自動化補救措施；這一切都取決於貴組織如何設定 AIR。 

## <a name="requirements-for-air-in-microsoft-threat-protection"></a>Microsoft 威脅防護的 AIR 需求

| | |
|--|--|
|訂閱需求 |下列其中之一： <br/>-Microsoft 365 E5 <br/>-Microsoft 365 A5 <br/>-Microsoft 365 E5 安全性<br/>-Microsoft 365 A5 安全性<br/>-Office 365 E5 plus Enterprise 可移動性 + Security E5 加上 Windows E5<br/><br/>請參閱[Microsoft 威脅防護授權的需求](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites?#licensing-requirements)。|
|網路需求 |- [Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)已啟用<br/>- [Microsoft 雲端 App 安全性](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) (MCAS) 已設定<br/>- [與 Azure ATP 整合的 MCAS](https://docs.microsoft.com/cloud-app-security/aatp-integration) |
|Windows 電腦需求 |-已設定下列威脅防護服務，已安裝 windows 10、版本1709或更新版本（請參閱[Windows 10 版本資訊](https://docs.microsoft.com/windows/release-information/)）：<br/>- [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) <br/>- [Windows Defender 防毒程式](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) |
|電子郵件內容和 Office 檔案的保護 |已設定[Office 365 高級威脅防護](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) |
|權限 |- 若要設定 AIR，您必須在 Azure Active Directory (https://portal.azure.com) 或 Microsoft 365 系統管理中心 ([https://admin.microsoft.com](https://admin.microsoft.com)) 中被指派[全域系統管理員](https://portal.azure.com)或安全性系統管理員角色。<br/><br/>- 若要使用 AIR 功能，請參閱[重要訊息中心的必要權限](mtp-action-center.md#required-permissions-for-action-center-tasks)。 |

## <a name="next-steps"></a>後續步驟

- [與自動化調查及回應相關的核准或拒絕動作](mtp-autoir-actions.md)
- [深入了解重要訊息中心](mtp-action-center.md)
