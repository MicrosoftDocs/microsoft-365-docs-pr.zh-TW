---
title: Microsoft 365 安全性藍圖-頭等大事
f1.keywords:
- NOCSH
ms.author: bcarter
author: BrendaCarter
manager: laurawi
ms.date: 10/08/2018
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
ms.assetid: 28c86a1c-e4dd-4aad-a2a6-c768a21cb352
description: 'Microsoft cybersecurity 小組的最佳建議，用以實施安全性功能，以保護您的 Microsoft 365 環境。 '
ms.openlocfilehash: 089e63ad9c83aac0bc5e88da8a24184eb8bdee6e
ms.sourcegitcommit: fa8e488936a36e4b56e1252cb4061b5bd6c0eafc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/13/2020
ms.locfileid: "46656954"
---
# <a name="security-roadmap---top-priorities-for-the-first-30-days-90-days-and-beyond"></a>安全性藍圖-前30天、90天和之後的頭等大事

本文包含 Microsoft cybersecurity 小組的主要建議，用以實施安全性功能，以保護您的 Microsoft 365 環境。 本文適用于 Microsoft Ignite session （ [如 cybersecurity pro）安全的 microsoft 365：前30天、90天和之後的最高優先順序](https://www.youtube.com/watch?v=luignzNyR-o)。 這個工作階段是由企業網路安全性架構師 Mark Simos 和 Matt Kemelhar 開發及展示。

本文內容：

- [藍圖結果](security-roadmap.md#Roadmap)

- [30 天 - 強力快速致勝](security-roadmap.md#Thirdaydays)

- [90 天 - 加強的保護](security-roadmap.md#Ninetydays)

- [以後](security-roadmap.md#Beyond)

## <a name="roadmap-outcomes"></a>藍圖結果
<a name="Roadmap"> </a>

這些藍圖建議橫跨有邏輯順序的三個階段，具有下列目標。

****

|時間範圍|結果|
|---|---|
|30 天|快速設定：  <br/> * 基本系統管理員防護  <br/> * 記錄和分析  <br/> * 基本身分識別保護  <br/> 租用戶設定  <br/>  準備專案關係人|
|90 天|進階保護：  <br/> * 系統管理員帳戶  <br/>  * 資料 &amp; 使用者帳戶  <br/>  合規性、威脅及使用者需求的可見度  <br/>  改編和實作預設原則和保護|
|以後|調整及微調重要原則和控制項  <br/> 將保護延伸到內部部署相依性  <br/> 整合企業與安全性流程 (法律、測試人員威脅等等)|
|

## <a name="30-days--powerful-quick-wins"></a>30 天 - 強力快速致勝
<a name="Thirdaydays"> </a>

這些工作可以快速地完成，並且對使用者的影響小。

****

|適用範圍|工作|
|---|---|
|安全性管理|* 檢查安全分數，並記下您目前的分數 (<https://securescore.office.com>) 。  <br/>  * 開啟 Office 365 的審計記錄。 請參閱[搜尋稽核記錄](../../compliance/search-the-audit-log-in-security-and-compliance.md)。  <br/> * [設定 Microsoft 365，以提高安全性](tenant-wide-setup-for-increased-security.md)。  <br/>  * 定期查看 Microsoft 365 security center 和 Cloud App Security 中的儀表板和報告。|
|威脅防護|使用適用于反常行為的預設威脅偵測原則，[將 microsoft 365 連線至 Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security)以開始監控。 建立異常偵測的基準需要 7 天。  <br><br/>  針對系統管理員帳戶實作保護：  <br/> * 使用專用的系統管理員帳戶進行系統管理員活動。  <br/>  * 針對系統管理員帳戶，強制執行多重要素驗證 (MFA) 。  <br/>  * 使用 [具有高安全性的 Windows 10 裝置](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-highly-secure) 進行系統管理活動。|
|身分識別與存取管理|* [啟用 Azure Active Directory Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable)。  <br/> * 針對同盟身分識別環境，強制執行帳戶安全性 (密碼長度、年齡、複雜度等 ) 。|
|資訊保護|檢閱範例資訊保護建議。 資訊保護需要跨組織進行協調。 使用下列資訊開始使用：  <br/> * [適用于 GDPR 的 Office 365 資訊保護](https://aka.ms/o365gdpr) <br/> * [使用三種保護層級，設定小組](../../solutions/configure-teams-three-tiers-protection.md) (包括共用、分類、資料遺失防護和 Azure 資訊保護) |
|

## <a name="90-days--enhanced-protections"></a>90 天 - 加強的保護
<a name="Ninetydays"> </a>

這個工作需要多一些時間來計劃及實作，但是可以大幅增加您的安全性狀態。

****

|適用範圍|工作|
|---|---|
|安全性管理|* 檢查您環境的建議動作安全得分 ([https://securescore.office.com](https://securescore.office.com)) 。  <br/>  * 繼續定期查看 Microsoft 365 安全性中心、雲端 App Security 及 SIEM 工具中的儀表板和報告。 <br/> * 尋找並執行軟體更新。 <br/> * 使用 (包含在[Office 365 威脅情報](office-365-ti.md)) 中的[攻擊模擬器](attack-simulator.md)，進行攻擊模擬，以進行 spear 網路釣魚、密碼噴塗和暴力密碼攻擊。  <br/> * 在 [調查] 索引標籤) 上，查看 Cloud App Security (中的內建報告，以尋找共用風險。 <br/> * 檢查 [符合性分數](https://docs.microsoft.com/microsoft-365/compliance/compliance-score) ，以查看套用至您組織 (的規章狀態，例如 GDPR、NIST 800-171) 。|
|威脅防護| 針對系統管理員帳戶實作增強型防護： <br/> * 設定 PAWs) 以進行系統管理活動的「特殊許可權 [存取工作站](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/privileged-access-workstations) 」 (。 <br/> * 設定 [AZURE AD 特權身分識別管理](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)。 <br/> * 設定安全性資訊和事件管理 (SIEM) 工具，從 Office 365、雲端應用程式安全性及其他服務（包括 AD FS）收集記錄資料。 「審核記錄」只會將資料儲存在90天。 在 SIEM 工具中擷取這項資料，可讓您將資料儲存更長的時間。|
|身分識別和存取管理|* 為所有使用者啟用並強制執行 MFA。 <br/> * 會執行一組 [條件式存取和相關原則](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-policies-configurations)。 |
|資訊保護| 改編和實作資訊保護原則。 這些資源包括範例： <br/> * [適用于 GDPR 的 Office 365 資訊保護](https://aka.ms/o365gdpr) <br/> * [以三種保護層級來設定小組](../../solutions/configure-teams-three-tiers-protection.md) <br/> <br> 在 Microsoft 365 中使用資料遺失防護原則和監控工具，以取得 Microsoft 365 中儲存的資料，而不是 Cloud App Security)  (。 <br><br>使用 Cloud App Security 搭配 Microsoft 365 來執行高級警示功能 (不是資料遺失防護) 。|
|

## <a name="beyond"></a>以後
<a name="Beyond"> </a>

這些是以上述工作為基礎建置的安全性措施。

****

|適用範圍|工作|
|---|---|
|安全性管理|* 使用 () 的安全分數，繼續規劃下一個動作 [https://securescore.office.com](https://securescore.office.com) 。 <br/> * 繼續定期查看 Microsoft 365 安全性中心、雲端 App Security 及 SIEM 工具中的儀表板和報告。 <br/> * 繼續尋找並執行軟體更新。 <br/> * 將 eDiscovery 整合到您的法律和威脅回應流程。|
|威脅防護|* 針對內部部署 (AD、AD FS) 上的身分識別元件，執行安全的許可權 [存取](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/securing-privileged-access) (SPA) 。 <br/> * 使用 Cloud App Security 監控內部人員威脅。 <br/> * 探索使用 Cloud App Security SaaS 使用方式。|
|身分識別與存取管理|* 調整原則和工作處理程式。 <br/> * 使用 Azure AD Identity Protection 來識別內幕威脅。|
|資訊保護|精簡資訊保護原則： <br/> * Microsoft 365 和 Office 365 敏感度標籤與資料遺失防護 (DLP) 或 Azure 資訊保護。 <br/> * Cloud App Security 原則及警示。|
|

另請參閱：[如何減輕例如 Petya 和 WannaCrypt 的快速網路攻擊](https://cloudblogs.microsoft.com/microsoftsecure/2018/02/21/how-to-mitigate-rapid-cyberattacks-such-as-petya-and-wannacrypt/) (英文)。
