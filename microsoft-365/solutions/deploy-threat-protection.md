---
title: 在 Microsoft 365 部署網路安全性威脅防護
description: 瞭解如何在 Microsoft 365 E5 部署威脅防護服務和 IT 網路安全性功能。
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.audience: ITPro
ms.topic: article
ms.prod: m365-security
ms.technology: m365d
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-threatprotection
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: 79352aca2012e6615f41b19f4a77fc5cf125f4c4
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926747"
---
# <a name="deploy-threat-protection-capabilities-across-microsoft-365"></a>在 Microsoft 365 部署威脅防護功能

[惡意](https://docs.microsoft.com/windows/security/threat-protection/intelligence/understanding-malware)攻擊和複雜的網路攻擊 ，例如無檔案[](https://docs.microsoft.com/windows/security/threat-protection/intelligence/fileless-threats)威脅，都是很常見的情況。 企業需要以有效的 IT 網路安全性功能來保護本身和客戶。 這類攻擊可能會為貴組織造成重大問題，包括失去信任、財務問題、業務中斷等等。 防範威脅很重要，但可能難以判斷要專注于貴組織的時間、精力和資源。 

我們產品與服務內建 Microsoft 安全性解決方案。 自動化與機器學習功能可以減少您安全性小組的負載，以確保已處理正確的專案。 而 Microsoft 網路安全性解決方案的強大功能，也建立在我們每天處理之智慧型安全性 Graph 的 [訊號上](https://cloud-platform-assets.azurewebsites.net/intelligent-security-graph)。 Microsoft 365 安全性解決方案包括 [Microsoft 365 Defender，](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)這是一種能結合電子郵件、資料、裝置和身分身分之訊號的解決方案，以描繪貴組織的進層威脅圖片。


觀看這段影片以獲取部署程序概觀。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vsI7]

使用這篇文章做為執行威脅防護解決方案的指南。

## <a name="threat-protection-in-microsoft-365-e5"></a>Microsoft 365 E5 中的威脅防護

[Microsoft 365 E5](https://www.microsoft.com/microsoft-365/enterprise-e5-business-software?activetab=pivot%3aoverviewtab) 可讓您使用自適性、內建智慧來保護您的組織。 使用 Microsoft 365 E5 中的威脅防護功能，您可以偵測並調查內部部署和雲端環境中進一步威脅、身分識別遭到入侵和惡意動作。

在 Microsoft 365 E5 中，威脅防護功能預設為整合。 每個功能發出的訊號，都為偵測和回應威脅的整體能力增加強度。 相較于非 Microsoft 產品，結合一組功能可為組織 、特別是多國組織提供最佳的保護。 下列影像說明本文所述的 Microsoft 365 E5 威脅防護服務和功能。

![Microsoft 365 Defender 概觀](../media/solutions-architecture-center/deploy-threat-protection-across-m365-overview.png)

部署任一 Office 365 的 Defender 功能後，您即可以開啟 Microsoft 365 Defender，將訊號和資料放在同一個地方。 

![Microsoft 365 Defender 儀表板的概念性圖例](../media/solutions-architecture-center/deploy-threat-protection-across-m365-mtp.png)

下圖說明部署這些個別功能的建議路徑。 

![M365 威脅防護訊號](../media/solutions-architecture-center/deploy-threat-protection-across-m365.png)

|解決方案/功能  |說明  |
|---------|---------|
|多重要素驗證和條件式存取     |防範身分和裝置遭到入侵。 首先進行這項保護，因為這是基礎。 此指引中建議的組配置包括 Azure AD 身分識別保護做為先決條件。     |
|適用於身分識別的 Microsoft Defender     |  雲端式安全性解決方案，利用您的內部部署 Active Directory 訊號來識別、偵測和調查進一步威脅、身分識別已遭到入侵，以及針對貴組織所導向的惡意 Insider 動作。 接下來請專注于 Microsoft Defender 的身分識別，因為它能保護您的 On-prem 和雲端基礎結構、沒有相依性或先決條件，而且可以立即提供好處。       | 
|適用於 Office 365 的 Microsoft Defender     | 保護貴組織免受電子郵件訊息、連結和 URL (和) 所造成的惡意威脅。 惡意攻擊、網路釣魚、詐騙及其他攻擊類型的保護。 我們接下來建議使用設定 Office 365 的 Microsoft Defender，因為變更控制、從系統移移設定及其他考慮可能需要較長的時間部署。 <br><br>注意：請務必設定 Exchange Online Protection 的所有 Office 365 訂閱 (威脅防護) 。       |
|適用於端點的 Microsoft Defender    | 可協助防範、偵測、調查及回應進一步威脅的端點保護平臺。  端點的 Defender 可能需要一些時間進行部署，但可以與其他功能同時進行組組。   |
|Microsoft Cloud App Security     |   探索、調查及監管的雲端存取安全性工作。 您可以提早啟用 Microsoft Cloud App 安全性，以開始收集資料和深入見解。 在 SaaS App 中執行資訊和其他目標保護需要規劃，而且可能會花上更多時間。       | 

> [!TIP]
> 擁有多個安全小組的組織可以同時執行這些功能。

## <a name="deploy-your-threat-protection-solution"></a>部署您的威脅防護解決方案

若要確保貴組織有最佳的保護能力，請設定及部署您的安全性解決方案，以包含下列步驟：

1. [設定多重要素驗證和條件式存取策略](deploy-threat-protection-configure.md#step-1-set-up-multi-factor-authentication-and-conditional-access-policies)
2. [設定 Microsoft Defender 的身分識別](deploy-threat-protection-configure.md#step-2-configure-microsoft-defender-for-identity)
3. [開啟 Microsoft 365 Defender](deploy-threat-protection-configure.md#step-3-turn-on-microsoft-365-defender)
4. [設定 Office 365 的 Defender](deploy-threat-protection-configure.md#step-4-configure-microsoft-defender-for-office-365)
5. [設定 Microsoft Defender 端點](deploy-threat-protection-configure.md#step-5-configure-microsoft-defender-for-endpoint)
6. [設定 Microsoft Cloud App 安全性](deploy-threat-protection-configure.md#step-6-configure-microsoft-cloud-app-security)
7. [監控狀態並採取行動](deploy-threat-protection-configure.md#step-7-monitor-status-and-take-actions)
8. [訓練使用者](deploy-threat-protection-configure.md#step-8-train-users)

您可以同時設定您的威脅防護功能，因此如果您有多個負責不同服務的網路安全小組，他們可以同時設定貴組織的防護功能。 下圖說明部署威脅防護功能的高層級程式。 

![部署威脅防護功能的流程](../media/solutions-architecture-center/deploy-threat-protection-across-m365-grid.png) 
