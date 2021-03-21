---
title: 準備您的 Microsoft 365 Defender 試用實驗室環境
description: 在設定 Microsoft 365 Defender 試用實驗室或試驗環境時，準備利益相關者簽署、時程表、環境考慮和採用順序
keywords: MTP 試用準備，MTP 試驗準備，準備執行 MTP 試驗專案、執行試驗 MTP 專案、部署、準備工作、專案關係人、時程表、環境、端點、伺服器、管理、採用
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 6ce05cd5ec41a014035a6936c02292cc4017f125
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920441"
---
# <a name="prepare-your-microsoft-365-defender-trial-lab-or-pilot-environment"></a>準備您的 Microsoft 365 Defender 試用實驗室或試驗環境

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


適用於：
- Microsoft 365 Defender

建立 Microsoft 365 Defender 試驗實驗室或試驗環境並加以部署時，會有三個階段的處理常式：

|![階段1：準備](../../media/phase-diagrams/prepare.png)<br/>階段1：準備 |[![階段2：設定](../../media/phase-diagrams/setup.png)](setup-mtpeval.md)<br/>[階段2：設定](setup-mtpeval.md) |[![階段3：板載](../../media/phase-diagrams/onboard.png)](config-mtpeval.md)<br/>[階段3：板載](config-mtpeval.md) | [![回到試驗](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)<br/>[回到試驗行動手冊](mtp-pilot.md) |
|--|--|--|--|
|*您在這裡！* | || |

您目前是在準備階段。


準備工作是任何成功部署的關鍵。 本節會引導您在準備建立 Microsoft 365 Defender 部署的試用實驗室或試驗環境時，您需要考慮的事項。

## <a name="prerequisites"></a>必要條件
瞭解授權、硬體和軟體需求，以及其他設定，以提供和使用 Microsoft 365 Defender。 請參閱 [microsoft 365 defender](./prerequisites.md)、microsoft Defender for [Endpoint](/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements)、 [microsoft defender For Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)、 [Microsoft Defender for Identity](/azure-advanced-threat-protection/atp-prerequisites)、 [microsoft Cloud App Security](/azure-advanced-threat-protection/atp-prerequisites)的最低需求。

## <a name="stakeholders-and-sign-off"></a>利益關係人和簽署
找出專案中相關的所有利益關係人，以及可能需要登入、審查或通知的所有利益關係人，不論評估或執行試驗專案。

>[!NOTE]
>並非所有組織都可能具有這類角色的安全性組織成熟度。 在這種情況下，請與您的領導團隊聯繫，以複查和核准職責。

視您的組織而定，將相關者新增至下表。

-   SO = 在此專案上登出

-   R = 審閱此專案並提供輸入

-   I = 此專案的通知

| 姓名                 | 角色                                                                                                                                                                                                          | 動作 |
|----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|
| 輸入名稱和電子郵件 | **首席資訊安全性監察官 (CISO)** *成為新技術部署之組織內充當主管的執行代表。*                                                  | 所以     |
| 輸入名稱和電子郵件 | **網路防護運作中心的 Head (CDOC)** *CDOC 小組的代表，以定義如何將此變更與客戶的安全性作業小組中的處理常式對齊。*       | 所以     |
| 輸入名稱和電子郵件 | **安全性***小組中的代表負責定義如何將此變更與組織中的核心安全性架構對應。*                         | R      |
| 輸入名稱和電子郵件 | **工作場所***會為 IT 小組設計代表，以定義如何將此變更與組織中的核心工作區架構對齊。*                             | R      |
| 輸入名稱和電子郵件 | **安全性分析員***來自 CDOC 小組的代表，可提供偵測功能、使用者經驗，以及安全性作業觀點之變更的整體有用性的意見反應。* | I      |

## <a name="prepare-your-azure-active-directory"></a>準備您的 Azure Active Directory
如果您已啟用 Active Directory 和 Azure Active Directory 內部部署之間的同步處理，請略過此步驟。 從 Azure Active Directory 複查現有的最佳作法檔。 下列步驟經過優化，可以評估或執行 Microsoft 365 Defender 專案的試用版。

1. 移至 [Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade) 入口網站 > **azure AD Connect**。 
![Azure Active Directory 入口網站頁面的影像](../../media/mtp-eval-1.png) <br> 

2. 按一下 [從 **Microsoft Azure Active Directory 連線]** ，然後將它轉接至您的網域控制站。
![Azure Active Directoru Connect 下載頁面的圖像](../../media/mtp-eval-2.png) <br>

3. 在網域控制站上，遵循 Azure Active Directory Connect 嚮導。 閱讀授權條款和隱私權通知，如果您同意，請選取此核取方塊。 按一下 [繼續]。
![Azure AD Connect 歡迎頁面的圖像](../../media/mtp-eval-3.png) <br>

4. 流覽至 **Express 設定**。
![快速設定頁面的圖像](../../media/mtp-eval-4.png) <br>

5. 輸入您的全域系統管理員認證。 按 [下一步 **]**。
![您應輸入全域系統管理員認證的 [連線到 Azure AD] 頁面影像](../../media/mtp-eval-5.png) <br>

6. 輸入您的 Active Directory 網域服務企業系統管理員認證。 按 [下一步 **]**。
![您應輸入認證的 [連線到 AD DS] 頁面影像](../../media/mtp-eval-6.png) <br>

7. 按一下 [ **安裝** ] 以確認設定。
![設定確認頁面的影像](../../media/mtp-eval-7.png) <br>

8. 恭喜，您已成功設定 Azure Active Directory Connect。
![已成功設定 Azure Active Directory Connect 頁面的圖像](../../media/mtp-eval-8.png) <br>

您現在可以 [將使用者和群組新增至 Active Directory](/azure-advanced-threat-protection/atp-playbook-setup-lab#bkmk_hydrate) ，並 [設定 SAM-R 原則](/azure-advanced-threat-protection/atp-playbook-setup-lab#configure-sam-r-capabilities-from-contosodc)。  


## <a name="configuration-order"></a>設定順序
下表指出 Microsoft 建議為您的試用實驗室或試驗環境部署設定 Microsoft 365 Defender 元件的順序。

| 元件                               | 描述                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | 設定順序排名 |
|-----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------|
|適用於 Office 365 的 Microsoft Defender|適用於 Office 365 的 Microsoft Defender 可保護組織防範由電子郵件訊息、連結 (URL) 及共同作業工具所造成的惡意威脅。 <br> [瞭解更多資訊。](../office-365-security/office-365-atp.md)                                                                                                                                                                                                                                             | 1                   |
|適用於身分識別的 Microsoft Defender|Microsoft Defender for Identity 使用 Active Directory 信號來識別、偵測和調查您組織中的高級威脅、已遭破壞的身分識別，以及惡意的有問必答行為。 <br> [深入了解](/azure-advanced-threat-protection/)。| 2  |
|Microsoft 雲端 App 安全性| Microsoft Cloud App Security 是雲端存取安全性經紀人 (CASB) ，可在多個雲端上運作。 它可提供豐富的知名度、控制資料旅行和複雜的分析，以在所有雲端服務之間識別及打擊 cyberthreats。 <br> [深入了解](/cloud-app-security/)。                                                                                                                                                                                                                                                                                                                                                                       |3                    |
|適用於端點的 Microsoft Defender | 適用於端點的 Microsoft Defender 偵測和回應功能可提供近乎即時並可採取行動的進階攻擊偵測。 安全性分析人員可以有效地排定警示的優先順序、深入了解入侵的全貌，並採取回應動作來補救威脅。 <br> [瞭解更多資訊。](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)                                     |4                    |                                                                                                                                                                                                                                    

## <a name="next-step"></a>後續步驟
|![階段2：設定](../../media/setup.png) <br>[階段2：設定](setup-mtpeval.md) | 設定您的 Microsoft 365 Defender 試用實驗室或試驗環境
|:-------|:-----|