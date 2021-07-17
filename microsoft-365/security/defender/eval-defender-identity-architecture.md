---
title: 檢查架構需求和 Microsoft Defender for Identity、架構圖表、MDI 的技術架構
description: Microsoft Defender for identity in Microsoft 365 Defender 的技術圖表可協助您在建立試用實驗室或試驗環境之前，先瞭解 Microsoft 365 中的身分識別。
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
ms.date: 07/09/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 8f0c736d07a2a66420416d30ae2dc45ae5fee37a
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/15/2021
ms.locfileid: "53457888"
---
# <a name="review-architecture-requirements-and-key-concepts-for-microsoft-defender-for-identity"></a>審閱 Microsoft Defender 身分識別的架構需求和重要概念


**適用於：**
- Microsoft 365 Defender

本文是設定 Microsoft Defender 身分識別的評估環境過程中的 [步驟1之 3](eval-defender-identity-overview.md) 。 如需此程式的詳細資訊，請參閱 [概述文章](eval-defender-identity-overview.md)。

在啟用 Microsoft Defender 身分識別之前，請確定您瞭解架構並可滿足需求。

Microsoft Defender for Identity 使用 machine 教學和行為分析來識別內部部署網路中的攻擊，以及偵測和主動預防使用者登入與雲端身分識別相關聯的風險。 如需詳細資訊，請參閱 [什麼是 Microsoft Defender 身分識別？](/defender-for-identity/what-is)

用於身分識別的身分識別會保護您的內部部署 Active Directory 使用者和/或已同步處理至 Azure Active Directory (Azure AD) 的使用者。 若要保護只由 Azure AD 使用者所組成的環境，請參閱 [AZURE Ad Identity Protection](/azure/active-directory/identity-protection/overview-identity-protection)。

## <a name="understand-the-architecture"></a>了解架構

下圖說明用於身分識別的 Defender 的基準架構。 

![Microsoft Defender 身分識別的架構](../../media/defender/m365-defender-identity-architecture.png)

在此圖中：
- 安裝在 AD 網域控制站上的感應器會剖析記錄和網路流量，並將其傳送至 Microsoft Defender 以供分析和報告識別。
-  當 Azure AD 設定為使用同盟驗證時，感應器也可以分析 Active Directory Federation Services (AD FS)  (圖例) 中的虛線點線。 
- Microsoft Defender 身分識別共用的信號，可 Microsoft 365 Defender (XDR) 的延伸偵測和回應。


您可以在下列伺服器上直接安裝身分識別感應器的 Defender：

- 網域控制站：感應器會直接監視網域控制站流量，而不需要專用的伺服器或埠鏡像的設定。
- AD FS：感應器會直接監視網路流量和驗證事件。

若要深入瞭解身分識別的身分架構，包括與雲端 App 安全性整合，請參閱[Microsoft Defender for identity 架構](/defender-for-identity/architecture)。


## <a name="understand-key-concepts"></a>瞭解重要概念

下清單格識別重要概念，在評估、設定及部署 Microsoft Defender 身分識別時，請務必瞭解。


|概念  |描述 |其他資訊  |
|---------|---------|---------|
| 受監視活動 | 用於身分識別的 Defender 監控組織內部產生的信號，可偵測可疑或惡意的活動，並協助您判斷每個潛在威脅的有效性，以有效進行會審和回應。  |  [適用于身分識別監控活動的 Microsoft Defender](/defender-for-identity/monitored-activities)       |
| 安全性警示    | 用於身分識別安全性警示的 Defender 會說明網路上的感應器所偵測到的可疑活動，以及每個威脅中所涉及的演員和電腦。   | [Microsoft Defender 身分識別安全性警示](/defender-for-identity/suspicious-activity-guide?tabs=external)    |
| 實體設定檔    | 實體設定檔提供使用者、電腦、裝置及資源及其存取歷程記錄的全面深入調查。   | [瞭解實體設定檔](/defender-for-identity/entity-profiles)  |
| 側向移動路徑    | MDI 安全性深入瞭解的一個重要元件，是找出一種橫向移動路徑，攻擊者使用非機密帳戶來存取整個網路中的機密帳戶或電腦。  | [Microsoft Defender for Identity 橫向移動路徑 (LMPs) ](/defender-for-identity/use-case-lateral-movement-path)  |
| 網路名稱解析    |  網路名稱解析 (NNR) 是 MDI 功能的元件，它會根據網路流量、Windows 事件、ETW 等來捕獲活動，並將此原始資料關聯到每個活動中的相關電腦。       | [何謂網路名稱解析？](/defender-for-identity/nnr-policy)      |
| 報告    | 用於身分識別報告的 Defender 可讓您排程或立即產生及下載提供系統和實體狀態資訊的報告。  您可以建立您環境中偵測到的系統健康情況、安全性警示及可能的側面移動路徑報告。   | [Microsoft Defender 身分識別報告 ](/defender-for-identity/reports)       |
| 角色群組    | 當您組織的特定安全性和合規性需求（包括系統管理員、使用者和查看者）時，身分識別提供角色型群組和委派存取權，以保護資料。        |  [適用於身分識別的 Microsoft Defender 角色群組](/defender-for-identity/role-groups)       |
| 管理入口網站    |  除了 Microsoft 365 的安全性中心之外，身分識別入口網站的 Defender 也可以用來監視和回應可疑的活動。      | [使用 Microsoft Defender for Identity 入口網站](/defender-for-identity/workspace-portal)        |
| Microsoft Cloud App Security 整合   | Microsoft Cloud App Security 會與 Microsoft Defender for Identity 整合，以在混合式環境中提供使用者實體行為分析 (UEBA) -Cloud App 和內部部署   | Microsoft Defender 用於身分識別整合  |
| | | |


## <a name="review-prerequisites"></a>審查必要條件

身分識別需要一些必要的工作，以確保您的內部部署身分識別和網路元件符合基本需求。 請使用本文做為檢查，以確保您的環境做好準備： [Microsoft Defender 的身分識別必要條件](/defender-for-identity/prerequisites)。


## <a name="next-steps"></a>後續步驟

步驟2之3： [啟用評估環境 Defender 身分識別](eval-defender-identity-enable-eval.md)

回到概述以 [評估 Microsoft Defender 身分識別](eval-defender-identity-overview.md)

回到[評估與試驗 Microsoft 365 Defender](eval-overview.md)概述 