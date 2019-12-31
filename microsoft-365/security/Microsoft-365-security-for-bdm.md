---
title: 適用於商務決策者 (Bdm) 的 Microsoft 365 安全性
ms.author: bcarter
author: brendacarter
manager: johmar
audience: Admin
ms.topic: tutorial
ms.service: o365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: 最常見的威脅和攻擊案例目前面臨由其 Microsoft 365 的環境，組織，建議您降低這些風險的動作。
ms.openlocfilehash: 9ad9d05cf29dba5aa3a7d14063db6fa2b4dd3bc4
ms.sourcegitcommit: a1bfa92c637ce8af40d2b6edf36f702eb40eb692
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/30/2019
ms.locfileid: "40910134"
---
# <a name="microsoft-365-security-for-business-decision-makers-bdms"></a>適用於商務決策者 (Bdm) 的 Microsoft 365 安全性

本文討論的一些最常見的威脅與攻擊案例目前面臨的組織對於其 Microsoft 365 環境，並建議降低這些風險的動作。 雖然 Microsoft 365 隨附各種預先設定的安全性功能，它也需要您為客戶採取來保護您自己的身分識別、 資料及裝置用來存取雲端服務的責任。 本指南已 Kozeta 資料交換 （Microsoft 雲端安全性架構師） 和 Thiagaraj Sundararajan （Microsoft 資深顧問） 所開發。

本文章會依優先順序的工作，以保護用來管理最重要的服務和資產，例如您的租用戶、 電子郵件，以及 SharePoint 這些帳戶開始。 為達到安全性，並搭配下列的試算表可讓您可以追蹤自己的進度與專案關係人及小組整個組織提供有條理的方式： [Microsoft 365 安全性的 Bdm 試算表](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Microsoft-365-BDM-security-recommendations-spreadsheet.xlsx)。 

[![縮圖影像 Microsoft 365 BDM 安全性建議試算表](../downloads/microsoft-365-bdm-security-recommendations-spreadsheet-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Microsoft-365-BDM-security-recommendations-spreadsheet.xlsx)

Microsoft 提供您要自動分析您根據您的一般活動的安全性狀態在租用戶中的安全分數工具指派分數，以及改進建議提供安全性。 暫停之前本文中建議的動作，請記下您目前的分數和建議。 本文中建議的動作將會增加您的分數。 目標是未以達到最大的分數，但要注意的機會來保護您的環境中的方式，而不造成負面影響使用者產能。 請參閱 [Microsoft 安全分數](mtp/microsoft-secure-score.md)。

一件事之前開始。 . . 請確定已[開啟的 Office 365 稽核記錄檔](../compliance/search-the-audit-log-in-security-and-compliance.md)。 更新版本中，您需要調查事件或外洩事件，您會需要此資料。 

## <a name="protect-privileged-accounts"></a>保護特殊權限的帳戶

我們建議您為第一個步驟中，確保環境中的重要帳戶為這些帳戶具有存取和權限來管理和變更重要服務和資源，而產生負面影響整個組織中，指定額外的保護層如果危害。 保護特殊權限的帳戶是下列其中一個最有效的方法，以防止攻擊者提升入侵帳戶的權限至系統管理一個搜尋項目。 

|建議  |E3 |E5  |
|---------|---------|---------|
|強制執行所有系統管理帳戶的多重要素驗證 (MFA)。|![綠色核取記號](../images/green-check-mark.png)|![綠色核取記號](../images/green-check-mark.png)| 
|實作 Azure Active Directory (Azure AD) 特殊權限 Identity Management (PIM) 套用剛時間特殊權限存取 Azure AD 和 Azure 的資源。 您也可以找出誰可以存取，並檢閱特殊權限的存取。|         | ![綠色核取記號](../images/green-check-mark.png)|
|在 Office 365 來管理 Office 365 中的特殊權限的系統管理工作更精細的存取控制中實作特殊權限的存取管理。 |         | ![綠色核取記號](../images/green-check-mark.png)|
|設定及管理服務使用特殊權限存取工作站 （爪）。 不使用相同的工作站瀏覽網際網路並檢查不相關的管理帳戶的電子郵件。|  ![綠色核取記號](../images/green-check-mark.png)|![綠色核取記號](../images/green-check-mark.png) | 

下圖說明這些功能。
![建議的功能，以保護特殊權限的帳戶](../images/m365-security-bdm-illustrations-privileged-accounts.png)

其他建議：
- 請確定從內部部署同步處理的帳戶未被指派為雲端服務的系統管理員角色。 這有助於防止攻擊者利用系統管理存取雲端服務的內部部署帳戶。 
- 確定服務帳戶未被指派系統管理員角色。 這些帳戶通常不會監視，並設定不會過期的密碼。 首先，確保 AADConnect 和 ADFS 服務帳戶不是全域系統管理員預設。
- 移除系統管理員帳戶的授權。 除非有特定使用案例將授權指派給特定的系統管理員帳戶，從這些帳戶中移除授權。 

## <a name="reduce-the-surface-of-attack"></a>減少攻擊的風險

下一個區域中，焦點會減少受攻擊的面。 這可以完成與最少的人力和影響到您的使用者和服務。 藉由減少攻擊的表面區域，攻擊者會有較少的方式，來啟動您的組織攻擊。

以下為一些範例：
- 停用 POP3、 IMAP 及 SMTP 通訊協定。 大部分現代組織無法再使用這些較舊的通訊協定。 即可放心地停用這些並只在必要時，允許例外狀況。 
- 減少並租用戶中保留的全域系統管理員所需的絕對最小值。 直接，這可減少受攻擊面減為所有雲端應用程式。 
- 淘汰伺服器和應用程式的環境中不再使用。 
- 實作停用和刪除不再使用的帳戶的程序。 

## <a name="protect-against-known-threats"></a>防範已知的威脅

已知威脅還包括惡意程式碼、 遭入侵的帳戶和網路釣魚。 某些保護，防範這些威脅可以用來實作快速不會直接影響您的使用者，而有些則要求更多的規劃和使用者訓練。 

|建議  |E3  |E5  |
|---------|---------|---------|
|**設定多重要素驗證和使用建議的條件式存取原則，包括登入風險原則**。 Microsoft 建議您，並已測試的共同運作以保護所有雲端應用程式，包括 Office 365 和 Microsoft 365 服務的原則設定。 請參閱[身分識別與裝置存取設定](../enterprise/microsoft-365-policies-configurations.md)。 | |![綠色核取記號](../images/green-check-mark.png)|
|**需要為所有使用者的多重要素驗證**。 如果您不需要實作建議的條件式存取原則所需的授權，至少需要多重要素驗證的所有使用者。|![綠色核取記號](../images/green-check-mark.png)|![綠色核取記號](../images/green-check-mark.png)|
|**引發防範惡意程式碼在郵件中的層級**。 Office 365 或 Microsoft 365 環境包含防範惡意程式碼，但您可以增加此保護封鎖附件的常用的惡意程式碼的檔案類型。|![綠色核取記號](../images/green-check-mark.png)|![綠色核取記號](../images/green-check-mark.png)|
|**保護您的電子郵件從目標的網路釣魚攻擊**。 如果您已設定一或多個自訂的網域為您的 Office 365 或 Microsoft 365 環境，您可以設定目標的反網路釣魚保護。 ATP 防網路釣魚防護，Office 365 進階威脅防護，一部分可協助保護組織免於惡意模擬型網路釣魚攻擊和其他網路釣魚攻擊。 如果您未設定自訂的網域，您不需要執行這項操作。| |![綠色核取記號](../images/green-check-mark.png)|
|**保護電子郵件中的勒索軟體攻擊**。 勒索軟體採取立即存取您的資料加密檔案或鎖定的電腦畫面。 然後會嘗試從受害者勒索金錢，詢問 「 贖金，「 通常格式為 cryptocurrencies 像 Bitcoin，來存取返回您的資料。 您可以協助防禦勒索軟體，藉由建立一或多個郵件流程規則若要封鎖的檔案副檔名通常用於勒索軟體，或警告電子郵件接收這些附件的使用者。|![綠色核取記號](../images/green-check-mark.png)|![綠色核取記號](../images/green-check-mark.png)|
|**從不與您生意的國家/地區封鎖連線**。 建立 Azure AD 條件式存取原則來封鎖任何這些國家/地區，有效地建立您的租用戶周圍地理防火牆您引導過來的連線。| |![綠色核取記號](../images/green-check-mark.png)|

下圖說明這些功能。
![建議的功能，以保護免於已知的威脅](../images/m365-security-bdm-illustrations-known-threats.png)

## <a name="protect-against-unknown-threats"></a>防範未知的威脅

之後將額外的保護設定新增至您特殊權限的帳戶，並保護已知的攻擊，移動您注意到防範未知潛在威脅。 多決定，以及進階而不斷演進使用創新新，組織的攻擊的未知的方法。 使用 Microsoft 的算遙測的透過數十億的裝置、 應用程式和服務所收集的資料，我們就能在 Windows、 Office 365 和 Azure 零天的攻擊，防止執行進階威脅防護運用沙] 方塊中的環境中，和允許存取您的內容之前檢查其有效性。 


|建議  |E3  |E5  |
|---------|---------|---------|
|**設定 Office 365 進階的威脅防護 (ATP)**:<br>• ATP 安全附件<br>• ATP 安全連結<br>• ATP SharePoint、 OneDrive 及 Microsoft Teams<br>• ATP 防網路釣魚保護|         |![綠色核取記號](../images/green-check-mark.png) |
|**設定 Microsoft Defender 進階威脅防護功能**：<br>• Windows Defender 防毒軟體 <br>• 惡意探索防護 <br> • 攻擊縮減 <br> • 硬體型隔離 <br>• 控制資料夾存取權     |         |![綠色核取記號](../images/green-check-mark.png) |
|**使用 Microsoft Cloud App Security**可探索 SaaS 應用程式，並開始使用行為分析和異常偵測。 |         |![綠色核取記號](../images/green-check-mark.png) |

下圖說明這些功能。
![建議的功能，以防止不明的威脅](../images/m365-security-bdm-illustrations-unknown-threats.png)

其他建議：
- 安全合作夥伴通道通訊，例如電子郵件使用 TLS。
- 開啟小組同盟合作夥伴，才能與您進行通訊。
- 執行不 whitelist 寄件者網域，個別寄件者，或因為這可讓這些略過垃圾郵件和惡意程式碼檢查來源 Ip — 常見的作法與客戶自己公認的網域或多個電子郵件流程問題可能已被其他網域是核准清單報告。 請勿在垃圾郵件和連線篩選] 清單中加入網域，因為這可能會略過所有垃圾郵件檢查。 
- 啟用輸出垃圾郵件通知-啟用通訊群組清單內部服務台或 IT 系統管理員小組回報垃圾郵件如果任何內部使用者寄出電子郵件從外部輸出垃圾郵件通知。 這可能是帳戶已遭洩露的指標。
- 停用所有使用者的遠端 PowerShell-遠端 PowerShell 主要由系統管理員用來存取 Office 365 服務系統管理用途或 API 的程式設計存取。 我們建議您停用此選項，以避免偵察，除非有業務需求對其進行存取的非系統管理使用者。 
- 封鎖對 Microsoft Azure 管理入口網站所有的非系統管理員的存取。 您可以建立條件式存取規則，以封鎖所有使用者，但系統管理員來完成這項作業。 


## <a name="assume-breach"></a>假設資料外洩

雖然 Microsoft 會採用每個可能的考量，以避免潛在威脅及攻擊，我們建議努力下"假設資料外洩 」 想法。 即使攻擊者具有 managed 來插入到環境中，我們需要確認它們都是從環境無法 exfiltrate 資料或識別資訊。 基於這個理由，建議您啟用如身分證號碼、 信用卡號碼、 其他個人資訊和其他組織層級的機密資訊的敏感資料外洩防護。 

"假設資料外洩 」 想法需要實作零信任網路策略，這表示使用者不完全信任，只是因為它們是內部網路。 可以做哪些使用者授權的一部分，為指定的條件，而這類條件符合時，某些控制項強制執行。 裝置健全狀況狀態、 所存取的應用程式、 正在執行的作業與使用者風險，可能包含條件。 例如，裝置註冊動作應該一律會觸發 MFA 驗證，以確保沒有魯治裝置會新增至您的環境。 

零的信任網路策略也需要您知道您的資訊儲存位置，並套用適當的分類、 保護及保留的控制項。 若要有效保護您最重要且機密的資產您必須先識別這些的所在位置，並採取庫存，可能相當困難。 接下來，使用您的組織定義的控管策略。 定義組織和設定原則、 標籤和條件的分類結構描述需要仔細規劃和準備。 請務必了解這不是 IT 驅動程序。 請務必使用您的法律和法規遵循小組，以開發適當的分類和標籤貴組織的資料結構描述。

Microsoft 365 資訊保護功能可協助您了解哪些資訊您擁有的資訊，其中儲存，以及哪些資訊需要額外的保護。 資訊保護是連續的處理程序和 Microsoft 365 功能會將您提供的可視性使用者使用和散佈敏感資訊的方式，您目前儲存資訊，其中流通。 您也可以查看如何處理的資訊的使用者才能確定管制的適當的標籤和保護會套用。


|建議 |E3|E5 |
|---------|---------|---------|
|**檢閱並最佳化您的條件式存取和相關的原則，以符合您的目標為零的信任網路**。 保護免於已知的威脅，包括實作一組[建議的原則](../enterprise/microsoft-365-policies-configurations.md)。 檢閱這些原則，以確保您可以保護您的應用程式和資料獲得存取您網路的駭客免於實作。 請注意，適用於 Windows 10 建議的 Intune 應用程式保護原則可讓 Windows 資訊保護 (WIP)。 WIP 提供保護，避免意外的應用程式和服務，例如電子郵件，您的組織資料外洩社交媒體、 部署及公用雲端。 |         |![綠色核取記號](../images/green-check-mark.png)|
|**停用外部電子郵件轉寄功能**。 存取使用者信箱的駭客可以藉由設定來自動轉寄電子郵件信箱竊取您的郵件。 這可能會發生，即使不使用者的認知。 您可以防止發生這藉由設定郵件流程規則。|![綠色核取記號](../images/green-check-mark.png) |![綠色核取記號](../images/green-check-mark.png)|
|**停用匿名外部行事曆共用**。 預設允許外部的匿名行事曆共用。 [停用行事曆共用](https://docs.microsoft.com/exchange/sharing/sharing-policies/modify-a-sharing-policy)若要降低潛在的敏感資訊外洩。|![綠色核取記號](../images/green-check-mark.png) |![綠色核取記號](../images/green-check-mark.png)|
|**設定資料外洩防護原則的敏感資料**。 探索及保護機密資料，例如信用卡號碼、 社會安全號碼與銀行帳戶號碼在 Office 365 安全性與合規性中心建立資料外洩防護原則。 Office 365 資料外洩防護原則中包含您可以使用許多預先定義的敏感資訊類型。 您也可以建立您的環境自訂的敏感資料您自己的敏感資訊類型。 |![綠色核取記號](../images/green-check-mark.png)|![綠色核取記號](../images/green-check-mark.png)|
|**實作資料分類和資訊保護原則**。 在 Office 365 中實作敏感度標籤，並使用這些分類，並將保護套用至敏感資料。 您也可以使用這些標籤中的資料外洩防護原則。 如果您使用 Azure 資訊保護標籤，我們建議您避免在其他系統管理中心中建立新的標籤。|         |![綠色核取記號](../images/green-check-mark.png)|
|**協力廠商應用程式和服務使用雲端 App 安全性中的保護資料**。 設定跨協力廠商雲端應用程式，例如 Salesforce、] 方塊中或投寄箱保護敏感資訊的 Cloud App Security 原則。 您可以使用敏感資訊類型和 Office 365 中建立的 Cloud App Security 原則敏感度標籤，並套用這些跨 SaaS 應用程式。 <br><br>Microsoft Cloud App Security 可讓您以強制執行各種自動化程序。 原則可設為提供連續的相容性掃描，legal 的 eDiscovery 工作，DLP 敏感共用的內容公開，等等。 Cloud App Security 可監視任何超過 20 個中繼資料篩選 （例如，存取層級，檔案類型） 為基礎的檔案類型。 |         |![綠色核取記號](../images/green-check-mark.png)|
|**使用[Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/information-protection-in-windows-overview)來識別是否使用者儲存其 Windows 裝置上的敏感資訊**。 |         |![綠色核取記號](../images/green-check-mark.png)|
|**使用[AIP 掃描程式](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner)以識別及分類跨伺服器和檔案共用的資訊**。 使用 AIP 報告工具，來檢視結果，並採取適當的動作。|         |![綠色核取記號](../images/green-check-mark.png)|

下圖說明這些功能。
![建議的功能，以保護防止外洩](../images/m365-security-bdm-illustrations-assume-breach.png)

## <a name="continuous-monitoring-and-auditing"></a>持續監視和稽核

最後，但不至少持續監視和稽核以及 Windows 和裝置的 Microsoft 365 環境很重要確保能夠快速偵測並修復任何入侵。 例如安全分數、 資訊安全中心，以及 Microsoft 智慧型 Graph 的進階分析工具提供將您的租用戶的重要資訊和連結數量龐大的威脅智慧及安全性資料，以提供您獲致前所未有威脅保護及偵測。


|建議 |E3 |E5 |
|---------|---------|---------|
|確定已開啟的**Office 365 稽核記錄**。|![綠色核取記號](../images/green-check-mark.png)|![綠色核取記號](../images/green-check-mark.png)|
|**檢閱安全分數每週**— 安全分數是一個中央位置來存取您的 Office 365 租用戶的安全性狀態，並採取動作根據安全分數的建議。 建議您執行這項檢查每週。|![綠色核取記號](../images/green-check-mark.png)|![綠色核取記號](../images/green-check-mark.png)|
|使用**Office 365 ATP**工具：<br>• 威脅調查及回應功能<br> • 自動化調查及回應 |         |![綠色核取記號](../images/green-check-mark.png)|
|使用**Microsoft Defender ATP**:<br> •[端點偵測及回應](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response) <br> • 自動化的調查並修復安全分數 <br>•[進階狩獵](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview) <br>|         |![綠色核取記號](../images/green-check-mark.png)|
|使用**Microsoft Cloud App Security**來偵測異常行為之間雲端應用程式以識別勒索軟體，危害使用者或劣等應用程式、 分析高風險的使用狀況及自動修復，以限制組織的風險。|         |![綠色核取記號](../images/green-check-mark.png)|
|使用**Microsoft Azure 護衛巨像**] 或 [您目前的 SIEM 工具來監視威脅的整個環境。 |         |![綠色核取記號](../images/green-check-mark.png)|
|監視及防範威脅針對您內部部署 Active Directory 環境中**部署[Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) ** 。   |         |![綠色核取記號](../images/green-check-mark.png) |
|使用**Azure 資訊安全中心**來之間混合式部署與雲端工作負載監視威脅。 Azure 資訊安全中心包含功能的免費層和已支付根據資源小時或交易的功能的標準層。|         |         |

下圖說明這些功能。
![建議的功能，以連續監視和稽核](../images/m365-security-bdm-illustrations-monitoring-auditing.png)

建議您監視動作的頂端：
- **檢閱 Microsoft 安全分數每週**— 安全分數是一個中央位置存取您的 Office 365 租用戶的安全性狀態，以及根據上方建議採取動作。 建議您執行這項檢查每週。 安全分數包含建議透過 Azure AD，Intune、 Cloud App Security，和 Microsoft Defender 進階威脅防護，以及 Office 365。 
- **檢閱每週風險登入**-使用 Azure AD 系統管理中心來檢閱有風險的登入每週。 建議的身分識別與裝置存取規則集包含的原則以強制執行密碼變更有風險的登入。  
- **檢閱最上層惡意程式碼和 phished 使用者每週**— 使用 Office 進階威脅防護威脅總管檢閱已設定目標與惡意程式碼和釣魚程式的主要使用者並了解為什麼這些使用者會受到影響的根本原因。
