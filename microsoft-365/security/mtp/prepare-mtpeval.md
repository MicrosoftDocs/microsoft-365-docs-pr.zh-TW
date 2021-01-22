---
title: 準備您的 Microsoft 365 Defender 試用版實驗室環境
description: 設定 Microsoft 365 Defender 試用版實驗室或試驗環境時，準備專案關係人簽簽、時程表、環境考慮及採用訂單
keywords: MTP 試用版準備、MTP 試驗準備、執行 MTP 試驗專案的準備、執行 MTP 試驗專案、部署、準備、專案關係人、時程表、環境、端點、伺服器、管理、採用
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
ms.openlocfilehash: 35f1d3f0b5cefb0f14508571511449fc2c7d58a9
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930147"
---
# <a name="prepare-your-microsoft-365-defender-trial-lab-or-pilot-environment"></a>準備您的 Microsoft 365 Defender 試用版實驗室或試驗環境

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


適用於：
- Microsoft 365 Defender

建立 Microsoft 365 Defender 試用版實驗室或試驗環境並部署此為三階段程式：

|![階段 1：準備](../../media/phase-diagrams/prepare.png)<br/>階段 1：準備 |[![階段 2：設定](../../media/phase-diagrams/setup.png)](setup-mtpeval.md)<br/>[階段 2：設定](setup-mtpeval.md) |[![階段 3：上機](../../media/phase-diagrams/onboard.png)](config-mtpeval.md)<br/>[階段 3：上機](config-mtpeval.md) | [![返回試驗](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)<br/>[回到試驗手冊](mtp-pilot.md) |
|--|--|--|--|
|*您目前在這裡！* | || |

您目前正在準備階段。


準備是任何成功部署的關鍵。 本節將引導您完成準備為 Microsoft 365 Defender 部署建立試驗實驗室或試驗環境時需考慮哪些專案。

## <a name="prerequisites"></a>必要條件
瞭解授權、硬體與軟體需求，以及要提供和使用 Microsoft 365 Defender 的其他設定設定。 請參閱 Microsoft [365 Defender、](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites)[端點的 Microsoft Defender、Office](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements) [365 的 Microsoft Defender、](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)身分識別[的 Microsoft Defender、Microsoft](https://docs.microsoft.com/azure-advanced-threat-protection/atp-prerequisites) [Cloud App 安全性的最低需求](https://docs.microsoft.com/azure-advanced-threat-protection/atp-prerequisites)。

## <a name="stakeholders-and-sign-off"></a>專案關係人與簽簽
找出與專案有關的所有專案關係人，以及哪些人可能需要簽簽、審查或隨時瞭解資訊，無論是評估或執行試驗專案。

>[!NOTE]
>並非所有組織可能都有安全性組織已到期可擁有這類角色。 在這種情況下，請向您的領導小組諮詢審查與核准責任。

將專案關係人新增到下表，以適合您的組織。

-   SO = 此專案的簽簽

-   R = 請審查此專案並提供輸入

-   I = 已通知此專案

| 姓名                 | 角色                                                                                                                                                                                                          | 動作 |
|----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|
| 輸入名稱和電子郵件 | **C時間資訊安全性 (C您的組織)** 擔任組織中負責新技術部署之贊助商 *高主管。*                                                  | 所以     |
| 輸入名稱和電子郵件 | 網路威脅作業中心 **(CDOC)** CDOC 小組代表負責定義此變更如何與客戶安全性作業小組中的程式保持一 *致。*       | 所以     |
| 輸入名稱和電子郵件 | **安全性架構** 安全性小組代表負責定義此變更如何與組織的核心 *安全性架構一致。*                         | R      |
| 輸入名稱和電子郵件 | **工作場所架構** IT 小組的一位代表負責定義此變更如何與組織的核心 *工作場所架構一致。*                             | R      |
| 輸入名稱和電子郵件 | **來自** CDOC 小組的安全性分析師代表，可針對偵測功能、使用者體驗，以及此次變更的整體實用性，從安全性作業的觀點 *提供意見回饋。* | I      |

## <a name="prepare-your-azure-active-directory"></a>準備 Azure Active Directory
如果您已經在內部部署啟用 Active Directory 和 Azure Active Directory 之間的同步處理，請略過此步驟。 從 Azure Active Directory 中查看現有的最佳做法檔。 下列步驟已優化，可評估或執行試驗 Microsoft 365 Defender 專案。

1. 請前往 [Azure AD Connect >](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade) **Azure Active Directory 入口網站**。 
![Azure Active Directory 入口網站頁面的影像](../../media/mtp-eval-1.png) <br> 

2. 按一下 **[從** **Microsoft Azure Active Directory Connect 下載** ，然後傳輸至您的網域控制站。
![Azure Active Directoru Connect 下載頁面的影像](../../media/mtp-eval-2.png) <br>

3. 請遵循網域控制站上的 Azure Active Directory Connect 精靈。 閱讀授權條款和隱私權注意事項，並選取核取方塊以表示您同意。 按一下 [繼續]。
![Azure AD Connect 歡迎頁面的影像](../../media/mtp-eval-3.png) <br>

4. 流覽至 **Express 設定**。
![Express 設定頁面的影像](../../media/mtp-eval-4.png) <br>

5. 輸入您的全域系統管理員認證。 按 **[下一步]**。
![您應在此輸入全域系統管理員認證之 Azure AD 頁面的圖像](../../media/mtp-eval-5.png) <br>

6. 輸入您的 Active Directory Domain Services 企業系統管理員認證。 按 **[下一步]**。
![您應在此輸入認證之連接至 AD DS 頁面的圖像](../../media/mtp-eval-6.png) <br>

7. 按一下 **[安裝** > 以確認安裝。
![組配置確認頁面的影像](../../media/mtp-eval-7.png) <br>

8. 恭喜您，您已成功安裝 Azure Active Directory Connect。
![已順利配置的 Azure Active Directory Connect 頁面影像](../../media/mtp-eval-8.png) <br>

現在，[您可以將使用者和群組新增到 Active Directory，](https://docs.microsoft.com/azure-advanced-threat-protection/atp-playbook-setup-lab#bkmk_hydrate)[並設定為為設定為一個管理方式的設定](https://docs.microsoft.com/azure-advanced-threat-protection/atp-playbook-setup-lab#configure-sam-r-capabilities-from-contosodc)。  


## <a name="configuration-order"></a>組組順序
下表指出 Microsoft 針對您的試驗實驗室或試驗環境部署，建議之 Microsoft 365 Defender 元件之配置順序。

| 元件                               | 說明                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | 組組順序排名 |
|-----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------|
|適用於 Office 365 的 Microsoft Defender|適用於 Office 365 的 Microsoft Defender 可保護組織防範由電子郵件訊息、連結 (URL) 及共同作業工具所造成的惡意威脅。 <br> [瞭解更多資訊。](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)                                                                                                                                                                                                                                             | 1                    |
|適用於身分識別的 Microsoft Defender|Microsoft Defender for Identity 會使用 Active Directory 訊號來識別、偵測和調查進一步威脅、已盜用的身分識別，以及指向貴組織的惡意 Insider 動作。 <br> [深入了解](https://docs.microsoft.com/azure-advanced-threat-protection/)。| 2  |
|Microsoft Cloud App Security| Microsoft Cloud App Security 是一種雲端存取安全性的 (CASB) ，可在多個雲端上運作。 它提供豐富的可見度、控制資料旅行，以及精密的分析，以找出並對抗所有雲端服務中的網路威脅。 <br> [深入了解](https://docs.microsoft.com/cloud-app-security/)。                                                                                                                                                                                                                                                                                                                                                                       |3                   |
|適用於端點的 Microsoft Defender | Microsoft Defender 端點偵測與回應功能提供接近即時且可採取動作的進一步攻擊偵測。 安全性分析人員可以有效地排定警示的優先順序、深入了解入侵的全貌，並採取回應動作來補救威脅。 <br> [瞭解更多資訊。](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)                                     |4                    |                                                                                                                                                                                                                                    

## <a name="next-step"></a>下一步
|![階段 2：設定](../../media/setup.png) <br>[階段 2：設定](setup-mtpeval.md) | 設定您的 Microsoft 365 Defender 試用版實驗室或試驗環境
|:-------|:-----|

