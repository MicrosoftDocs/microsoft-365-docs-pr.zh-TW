---
title: Office 365 安全性藍圖 - 前 30 天、90 天和之後的首要工作
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
description: 'Microsoft 網路安全性小組對於實作安全性功能以保護您 Office 365 環境的主要建議。 '
ms.openlocfilehash: c668bb736e6d9f788fe2c54e8a49adbfd4156f43
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598430"
---
# <a name="office-365-security-roadmap---top-priorities-for-the-first-30-days-90-days-and-beyond"></a>Office 365 安全性藍圖 - 前 30 天、90 天和之後的首要工作

本文包含 Microsoft 網路安全性小組對於實作安全性功能以保護您 Office 365 環境的主要建議。 本文改編自 Microsoft Ignite 工作階段 - [像網路安全性專業人員一般保護 Office 365：前 30 天、90 天和之後的首要工作](https://www.youtube.com/watch?v=luignzNyR-o)。 這個工作階段是由企業網路安全性架構師 Mark Simos 和 Matt Kemelhar 開發及展示。

本文內容：

- [藍圖結果](security-roadmap.md#Roadmap)

- [30 天 - 強力快速致勝](security-roadmap.md#Thirdaydays)

- [90 天 - 加強的保護](security-roadmap.md#Ninetydays)

- [以後](security-roadmap.md#Beyond)

## <a name="roadmap-outcomes"></a>藍圖結果
<a name="Roadmap"> </a>

這些藍圖建議橫跨有邏輯順序的三個階段，具有下列目標。

|||
|:-----|:-----|
| |結果
|30 天|快速設定：  <br/> • 基本系統管理保護  <br/> • 記錄和分析  <br/> • 基本身分識別保護  <br/> 租用戶設定  <br/>  準備專案關係人|
|90 天|進階保護：  <br/> • 系統管理員帳戶  <br/>  • 資料與使用者帳戶  <br/>  合規性、威脅及使用者需求的可見度  <br/>  改編和實作預設原則和保護|
|以後|調整及微調重要原則和控制項  <br/> 將保護延伸到內部部署相依性  <br/> 整合企業與安全性流程 (法律、測試人員威脅等等)|



## <a name="30-days--powerful-quick-wins"></a>30 天 - 強力快速致勝
<a name="Thirdaydays"> </a>

這些工作可以快速地完成，並且對使用者的影響小。

|||
|:-----|:-----|
|適用範圍|工作|
|安全性管理|• 檢查安全分數並記下您目前的分數 ([https://securescore.office.com](https://securescore.office.com))。  <br/>  • 開啟 Office 365 的稽核記錄。 請參閱[搜尋稽核記錄](../../compliance/search-the-audit-log-in-security-and-compliance.md)。  <br/> • [設定 Office 365 租用戶以提高安全性](tenant-wide-setup-for-increased-security.md)。  <br/>  • 定期檢閱 Microsoft 365 安全性中心和 Cloud App Security 中的儀表板和報告。|
|威脅防護|[將 Office 365 連線至 Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security) (部分機器翻譯)，開始使用預設的威脅偵測原則監視異常行為。 建立異常偵測的基準需要 7 天。  <br><br/>  針對系統管理員帳戶實作保護：  <br/> • 使用專用的系統管理員帳戶來執行系統管理活動。  <br/>  • 針對系統管理員帳戶強制執行多重要素驗證 (MFA)。  <br/>  • 使用[高度安全的 Windows 10 裝置](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-highly-secure) (部分機器翻譯) 進行系統管理活動。|
|身分識別和存取管理|• [啟用 Azure Active Directory Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable)。  <br/> • 針對同盟身分識別環境，強制執行帳戶安全性 (密碼長度、年限、複雜性等等)。|
|資訊保護| 檢閱範例資訊保護建議。 資訊保護需要跨組織進行協調。 使用下列資訊開始使用：  <br/> • [GDPR 的 Office 365 資訊保護](https://aka.ms/o365gdpr) <br/> • [保護 SharePoint Online 網站與檔案](https://docs.microsoft.com/Office365/enterprise/secure-sharepoint-online-sites-and-files) (包括共用、分類、資料外洩防護和 Azure 資訊保護)|

## <a name="90-days--enhanced-protections"></a>90 天 - 加強的保護
<a name="Ninetydays"> </a>

這個工作需要多一些時間來計劃及實作，但是可以大幅增加您的安全性狀態。

|||
|:-----|:-----|
|適用範圍|工作|
|安全性管理|• 檢查針對您環境建議動作的安全分數 ([https://securescore.office.com](https://securescore.office.com))。  <br/>  • 持續定期檢閱 Microsoft 365 安全性中心、Cloud App Security 和 SIEM 工具中的儀表板和報告。 <br/> • 尋找及實作軟體更新。 <br/> •使用 [攻擊模擬器](attack-simulator.md) (隨附於 [Office 365 威脅情報](office-365-ti.md)) 來進行魚叉式網路釣魚、密碼噴灑和暴力密碼破解攻擊的攻擊模擬。  <br/> • 藉由檢閱 Cloud App Security 中的內建報告 (在 [調查] 索引標籤上)，以尋找共用風險。 <br/> • 檢查[合規性分數](https://docs.microsoft.com/microsoft-365/compliance/compliance-score)」 來檢閱套用至組織 （例如 GDPR、 NIST 800-171) 的規定的狀態。|
|威脅防護| 針對系統管理員帳戶實作增強型防護： <br/> • 為系統管理活動設定[特殊權限存取工作站](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/privileged-access-workstations) (PAW)。 <br/> • 設定 [Azure AD Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)。 <br/> • 設定安全性資訊和事件管理 (SIEM) 工具，以收集 Office 365、Cloud App Security 及其他服務 (包括 AD FS) 的記錄資料。 Office 365 稽核記錄只會儲存 90 天的資料。 在 SIEM 工具中擷取這項資料，可讓您將資料儲存更長的時間。|
|身分識別和存取管理|• 為所有使用者啟用和強制執行 MFA。 <br/> • 實作一組[條件式存取及相關原則](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-policies-configurations) (部分機器翻譯)。 |
|資訊保護| 改編和實作資訊保護原則。 這些資源包括範例： <br/> • [GDPR 的 Office 365 資訊保護](https://aka.ms/o365gdpr) <br/> • [保護 SharePoint Online 網站與檔案](https://docs.microsoft.com/Office365/enterprise/secure-sharepoint-online-sites-and-files) <br/> <br> 針對儲存在 Office 365 (而不是 Cloud App Security) 的資料，使用 Office 365 中的資料外洩防護原則及監視工具。 <br><br>針對進階警示功能 (資料外洩防護以外的功能) 搭配使用 Cloud App Security 和 Office 365。|

## <a name="beyond"></a>以後
<a name="Beyond"> </a>

這些是以上述工作為基礎建置的安全性措施。

|||
|:-----|:-----|
|適用範圍|工作|
|安全性管理|• 使用安全分數 ([https://securescore.office.com](https://securescore.office.com)) 繼續規劃下一個動作。 <br/> • 持續定期檢閱 Microsoft 365 安全性中心、Cloud App Security 和 SIEM 工具中的儀表板和報告。 <br/> • 持續尋找及實作軟體更新。 <br/> • 將電子文件探索整合到您的法律和威脅回應程序中。|
|威脅防護|• 針對內部部署身分識別元件 (AD、AD FS) 實作[保護特殊權限存取](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/securing-privileged-access) (SPA)。 <br/> • 使用 Cloud App Security 來監視測試人員威脅。 <br/> • 使用 Cloud App Security 探索陰影 IT SaaS 使用。|
|身分識別和存取管理|• 精簡​​原則和操作程序。 <br/> • 使用 Azure AD Identity Protection 來識別測試人員威脅。|
|資訊保護| 精簡資訊保護原則： <br/> • Microsoft 365 和 Office 365 敏感度標籤和資料外洩防護 (DLP) 或 Azure 資訊保護。 <br/> • Cloud App Security 原則和警示。|

另請參閱：[如何減輕例如 Petya 和 WannaCrypt 的快速網路攻擊](https://cloudblogs.microsoft.com/microsoftsecure/2018/02/21/how-to-mitigate-rapid-cyberattacks-such-as-petya-and-wannacrypt/) (英文)。
