---
title: 準備 Microsoft Defender for Endpoint 部署
description: 在部署 Microsoft Defender for Endpoint 時，準備專案關係人核准、時程表、環境考慮和採用順序
keywords: 部署、準備、專案關係人、時程表、環境、端點、伺服器、管理、採用
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-scenario
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 13748662f6e53db86352b903828978729f78e6a8
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842431"
---
# <a name="prepare-microsoft-defender-for-endpoint-deployment"></a>準備 Microsoft Defender for Endpoint 部署

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

為端點部署 Defender 是三個階段的處理常式：

| ![部署階段-準備](images/phase-diagrams/prepare.png)<br>階段 1：準備 | [![部署階段-安裝程式](images/phase-diagrams/setup.png)](production-deployment.md)<br>[階段 2：設定](production-deployment.md) | [![部署階段-板載](images/phase-diagrams/onboard.png)](onboarding.md)<br>[第 3 階段：導入](onboarding.md) |
| ----- | ----- | ----- |
|*您在這裡！* | ||


您目前在準備階段。


準備工作是任何成功部署的關鍵。 在本文中，您將指導您準備部署用於端點的 Defender 時所需考慮的事項。


## <a name="stakeholders-and-approval"></a>利益關係人和核准
下列章節可用於識別與專案相關的所有利益關係人，並需要核准、審查或及時瞭解。

視您的組織而定，將相關者新增至下表。

-   SO = 核准專案

-   R = 審閱此專案並提供輸入

-   I = 此專案的通知

| 名稱                 | 角色                                                                                                                                                                                                          | 動作 |
|----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|
| 輸入名稱和電子郵件 | **首席資訊安全性監察官 (CISO)** *成為新技術部署之組織內充當主管的執行代表。*                                                  | 所以     |
| 輸入名稱和電子郵件 | **網路防護運作中心的 Head (CDOC)** *CDOC 小組的代表，以定義如何將此變更與客戶的安全性作業小組中的處理常式對齊。*       | 所以     |
| 輸入名稱和電子郵件 | **安全性***小組中的代表負責定義如何將此變更與組織中的核心安全性架構對應。*                         | R      |
| 輸入名稱和電子郵件 | **工作場所***會為 IT 小組設計代表，以定義如何將此變更與組織中的核心工作區架構對齊。*                             | R      |
| 輸入名稱和電子郵件 | **安全性分析員***來自 CDOC 小組的代表，可提供偵測功能、使用者經驗和安全性作業的整體有用性。* | I      |


## <a name="environment"></a>環境 


本節可用以確保您的環境深入瞭解，其可協助識別技術或處理常式所需的潛在相依性和/或變更。

| 項目                                  | 描述 |
|---------------------------------------|-------------|
| 端點計數                        |    依作業系統的端點總計計數。         |
| 伺服器計數                          |    依作業系統版本的伺服器總數。    |
| 管理引擎                     |    管理引擎名稱及版本 (例如，System Center Configuration Manager 目前的 Branch 1803) 。         |
| CDOC 分配                     |    高層級 CDOC 結構 (例如，第1層外包至 Contoso、第2層和第3層內部散佈的內建跨歐洲和亞洲) 。         |
|  (SIEM 的安全性資訊和事件)  |    SIEM 技術正在使用中。         |


## <a name="role-based-access-control"></a>角色型存取控制

Microsoft 建議使用最低許可權的概念。 Defender for Endpoint 利用 Azure Active Directory 內的內建角色。 Microsoft 建議您 [複查可使用的不同角色](/azure/active-directory/active-directory-assign-admin-roles-azure-portal) ，並選擇適當的角色，為此應用程式的每個角色解決您的需求。 在完成部署後，可能需要暫時套用某些角色並加以移除。

| 角色                     | 角色 | 必要時，Azure AD Role ()  | 指派給 |
|------------------------------|-------|-----------------------------|-----------|
| 安全性系統管理員       |       |                             |           |
| 安全性分析員             |       |                             |           |
| 端點管理員       |       |                             |           |
| 基礎結構管理員 |       |                             |           |
| 業務負責人/專案關係人   |       |                             |           |

Microsoft 建議使用[Privileged Identity Management](/azure/active-directory/active-directory-privileged-identity-management-configure)來管理您的角色，以針對具有目錄許可權的使用者提供其他審核、控制和存取權審查。

Defender for Endpoint 支援兩種管理許可權的方式：

-   **基本版權管理**：將許可權設定為「完整存取」或「唯讀」。 在 Azure Active Directory 中具有全域管理員或安全性管理員角色的基本版權管理使用者，在安全性讀取者角色具有唯讀存取權的情況下，就會具有完整存取權。

-   以 **角色為基礎的存取控制 (RBAC)**：透過定義角色、指派 Azure AD 使用者群組和授予使用者群組存取裝置群組，來設定細微許可權。 以取得詳細資訊。 請參閱 [使用以角色為基礎的存取控制管理入口網站存取](rbac.md)。

Microsoft 建議利用 RBAC，以確保只有具備業務理由的使用者可以存取端點的 Defender。

您可以在 [這裡](/microsoft-365/security/defender-endpoint/user-roles#create-roles-and-assign-the-role-to-an-azure-active-directory-group)找到許可權準則的詳細資料。

下列範例表用以識別您環境中的「網路防護作業中心」結構，可協助您決定環境所需的 RBAC 結構。

| 層   | 描述                                                                                                                                                                                                 | 需要許可權 |
|--------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------|
| 第1層 | **本機安全作業小組/IT 小組**<br>此小組通常會 triages 並調查包含在其地理位置內的警示，並在需要使用中修復的情況下升級至第2層。                                              |                     |
| 第2層 | **區域安全性運作小組**<br>此小組可以查看其地區的所有裝置，並執行修正動作。                                                                                                                        |        查看資料               |
| 第3層 | **全域安全性運作小組**<br>此小組由安全性專家組成，有權從入口網站查看及執行所有動作。 | 查看資料 <br>  警示調查作用中的修復動作 <br> 警示調查作用中的修復動作 <br> 管理入口網站系統設定 <br> 管理安全性設定 |



## <a name="adoption-order"></a>採用順序
在許多情況下，組織會適當使用現有的端點安全性產品。 每個組織最低應為防病毒解決方案。 但在某些情況下，組織可能也已經 implanted EDR 解決方案。

過去，由於緊密的掛鉤進入應用層和基礎結構相依性，因此取代任何耗時且難於達到的安全性解決方案。 不過，因為將 Defender for Endpoint 內置於作業系統，所以現在可輕鬆取代協力廠商解決方案。

選擇要使用的 Defender for Endpoint 元件，並移除不適用的 Endpoint。 下表指出 Microsoft 建議如何啟用端點安全性套件的順序。

| 元件                               | 描述                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | 採用訂單排名 |
|-----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------|
| 端點偵測 & 回應 (EDR)      | Defender for Endpoint endpoint 偵測和回應功能提供接近即時及可行動的高級攻擊偵測。 安全性分析人員可以有效地排定警示的優先順序、深入了解安全性缺口的完整範圍，並採取回應動作來補救威脅。 <br> [瞭解更多資訊。](/windows/security/threat-protection/windows-defender-atp/overview-endpoint-detection-response)                                                                                                                                                                                                                                             | 1                   |
|威脅 & 弱點管理 (TVM) |威脅 & 漏洞管理是 Microsoft Defender for Endpoint 的元件，並提供安全性管理員和具有唯一值的安全性作業小組，包括： <br> -即時端點偵測與回應 (EDR) 與端點弱點相關的洞察力 <br> -事件調查期間的重要裝置弱點內容 <br> 透過 Microsoft Intune 和 Microsoft System Center Configuration Manager 內建的修復程式 <br> [深入了解](https://techcommunity.microsoft.com/t5/Windows-Defender-ATP/Introducing-a-risk-based-approach-to-threat-and-vulnerability/ba-p/377845)。| 第 |
| 下一代保護 (NGP)         | Microsoft Defender 防毒軟體是內建的反惡意程式碼解決方案，可為桌上型電腦、便攜機和伺服器提供下一代保護。 Microsoft Defender 防毒軟體包括： <br> -提供雲端式防護，以進行近乎即時的偵測，並封鎖新的和新興的威脅。 除了機器學習和 Intelligent Security Graph，雲端提供的防護功能也是新一代技術的一部分，可加強 Microsoft Defender 防毒軟體的功能。   <br> -Always on 掃描使用高級檔案和程式列為監控和其他試探法 (也稱為「即時保護」 ) 。 <br> 專用的保護更新，取決於機器教育、人工和自動化大量資料分析，以及深層威脅抵觸調查。 <br> [深入了解](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)。                                                                                                                                                                                                                                                                                                                                                                       |個                   |
|  (ASR) 的攻擊面減少          | Microsoft Defender for Endpoint 中的攻擊面降減功能可協助保護組織中的裝置和應用程式免受新的和新興的威脅。 <br> [瞭解更多資訊。](/windows/security/threat-protection/windows-defender-atp/overview-attack-surface-reduction)                                                                                                                                                                                                                                                                                                                                                                                       | 4                    |
|  (AIR) 的自動調查 & 修復  | Microsoft Defender for Endpoint 使用自動調查以大幅減少需要個別調查的警示量。 「自動調查」功能會利用各種檢查演算法和分析員所使用的處理常式 (例如行動) ，以檢查提醒並採取立即修正動作來解決違規行為。 這會大幅降低警示量，讓安全性操作專家能夠專注于更複雜的威脅和其他高價值的方案。 <br>[瞭解更多資訊。](/windows/security/threat-protection/windows-defender-atp/automated-investigations-windows-defender-advanced-threat-protection) | 不適用      |
| Microsoft 威脅專家 (MTE)           | Microsoft 威脅專家是一個受管理的搜尋服務，可讓安全性運作中心 (SOCs) 與專家級的監控和分析，以協助其確保獨特環境中的重大威脅不會遭到錯過。 <br>[瞭解更多資訊。](/windows/security/threat-protection/windows-defender-atp/microsoft-threat-experts)                                                                                                                                                                                                                                                                                                                     | 不適用      |

## <a name="next-step"></a>下一步

![階段 2：設定](images/setup.png) <br>[階段2：安裝程式](production-deployment.md) |設定 Microsoft Defender for Endpoint 部署

