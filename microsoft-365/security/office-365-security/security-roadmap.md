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
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
ms.assetid: 28c86a1c-e4dd-4aad-a2a6-c768a21cb352
description: Microsoft cybersecurity 小組的主要建議，用以實施安全性功能，以保護您的 Microsoft 365 環境。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 67febc328706121360b2b34e054ae8e208355b89
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879251"
---
# <a name="security-roadmap---top-priorities-for-the-first-30-days-90-days-and-beyond"></a>安全性藍圖-前30天、90天和之後的頭等大事

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


本文包含 Microsoft cybersecurity 小組的主要建議，用以實施安全性功能，以保護您的 Microsoft 365 環境。 本文適用于 Microsoft Ignite session- [Secure Microsoft 365，例如 cybersecurity 專業人員：前30天、90天和之後的最高優先順序](https://www.youtube.com/watch?v=luignzNyR-o)。 這個工作階段是由企業網路安全性架構師 Mark Simos 和 Matt Kemelhar 開發及展示。

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
|30 天|快速設定： <ul><li>基本系統管理員防護。</li><li>記錄和分析。</li><li>基本身分識別保護。</li></ul> <p> 租使用者設定。 <p> 準備利益關係人。|
|90 天|進階保護： <ul><li>系統管理員帳戶。</li><li>資料和使用者帳戶。</li></ul> <p> 深入瞭解規範、威脅和使用者需求。 <p> 修改及實施預設原則及保護。|
|以後|調整和調整重要原則和控制。 <p> 將保護擴充至內部部署相依性。 <p> 整合商務及安全性程式 (法律、內幕威脅等 ) 。|
|

## <a name="30-days--powerful-quick-wins"></a>30 天 - 強力快速致勝
<a name="Thirdaydays"> </a>

這些工作可以快速地完成，並且對使用者的影響小。

****

|適用範圍|工作|
|---|---|
|安全性管理|<ul><li>請檢查安全分數，並記下您目前的分數 (<https://securescore.office.com>) 。</li><li>開啟 Office 365 的審計記錄。 請參閱[搜尋稽核記錄](../../compliance/search-the-audit-log-in-security-and-compliance.md)。</li><li>[設定 Microsoft 365 以提高安全性](tenant-wide-setup-for-increased-security.md)。</li><li>定期查看 Microsoft 365 Defender 入口網站和雲端 App 安全性中的儀表板和報告。</li></ul>|
|威脅防護|[連線 Microsoft 365 Microsoft Cloud App Security](/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security)使用反常行為的預設威脅偵測原則開始監控。 建立異常偵測的基準需要 7 天。 <p>  針對系統管理員帳戶實作保護：<ul><li>使用專用的系統管理員帳戶進行系統管理員活動。</li><li>針對系統管理員帳戶，強制執行多重要素驗證 (MFA) 。</li><li>使用[高度安全的 Windows 10 裝置](/windows-hardware/design/device-experiences/oem-highly-secure)進行系統管理活動。</li></ul>|
|身分識別與存取管理|<ul><li>[啟用 Azure Active Directory 身分識別保護](/azure/active-directory/active-directory-identityprotection-enable)。</li><li>針對同盟身分識別環境，強制執行帳戶安全性 (密碼長度、年齡、複雜度等 ) 。</li></ul>|
|資訊保護|檢閱範例資訊保護建議。 資訊保護需要跨組織進行協調。 使用下列資訊開始使用：<ul><li>[GDPR 的 Office 365 資訊保護](/compliance/regulatory/gdpr)</li><li>[使用三種保護層級，設定 Teams](../../solutions/configure-teams-three-tiers-protection.md) (包含共用、分類、資料遺失防護和 Azure 資訊保護) </li></ul>|
|

## <a name="90-days--enhanced-protections"></a>90 天 - 加強的保護
<a name="Ninetydays"> </a>

這個工作需要多一些時間來計劃及實作，但是可以大幅增加您的安全性狀態。

****

|適用範圍|工作|
|---|---|
|安全性管理|<ul><li>檢查 () 環境的建議動作安全得分 <https://securescore.office.com> 。</li><li>繼續定期查看 Microsoft 365 Defender 入口網站、雲端 App 安全性和 SIEM 工具中的儀表板和報告。</li><li>尋找並執行軟體更新。</li><li>使用[Office 365 威脅智慧](office-365-ti.md)) 中包含的[攻擊模擬器](attack-simulator.md) (，進行攻擊模擬，以進行 spear 網路釣魚、密碼噴塗和暴力密碼攻擊。</li><li>在 [調查] 索引標籤) 上的雲端 App 安全性 (中查看內建報表，以尋找共用風險。</li><li>檢查 [合規性管理員](../../compliance/compliance-manager.md) 以查看適用于貴組織 (的規章狀態，例如 GDPR、NIST 800-171) 。</li></ul>|
|威脅防護|針對系統管理員帳戶實作增強型防護： <ul><li>設定 PAWs) 管理活動的特殊許可權 [存取 (工作站](/security/compass/privileged-access-devices) 。</li><li>設定[AZURE AD Privileged Identity Management](/azure/active-directory/active-directory-privileged-identity-management-configure)。</li><li>設定安全性資訊和事件管理 (SIEM) 工具，從 Office 365、雲端 App 安全性及其他服務（包括 AD FS）收集記錄資料。 「審核記錄」只會將資料儲存在90天。 在 SIEM 工具中擷取這項資料，可讓您將資料儲存更長的時間。</li></ul>|
|身分識別和存取管理|<ul><li>為所有使用者啟用並強制執行 MFA。</li><li>實施一組 [條件式存取和相關原則](microsoft-365-policies-configurations.md)。</li></ul>|
|資訊保護| 改編和實作資訊保護原則。 這些資源包括範例： <ul><li>[GDPR 的 Office 365 資訊保護](/compliance/regulatory/gdpr)</li><li>[為 Teams 設定三層保護](../../solutions/configure-teams-three-tiers-protection.md)</li></ul> <p> 針對 Microsoft 365 (中儲存的資料，使用 Microsoft 365 中的資料遺失防護原則和監視工具，而不是雲端 App 安全性) 。 <p> 使用雲端 App 安全性搭配 Microsoft 365，以進行高級警示功能 (以外的資料遺失防護) 。|
|

## <a name="beyond"></a>以後
<a name="Beyond"> </a>

這些是以上述工作為基礎建置的安全性措施。

****

|適用範圍|工作|
|---|---|
|安全性管理|<ul><li>使用安全分數 () ，繼續規劃下一個動作 <https://securescore.office.com> 。</li><li>繼續定期查看 Microsoft 365 Defender 入口網站、雲端 App 安全性和 SIEM 工具中的儀表板和報告。</li><li>繼續尋找並執行軟體更新。</li><li>將 eDiscovery 整合到您的法律和威脅回應流程。</li></ul>|
|威脅防護|<ul><li>針對內部部署 (AD、AD FS) 上的身分識別元件，執行安全的許可權 [存取](/windows-server/identity/securing-privileged-access/securing-privileged-access) (SPA) 。</li><li>使用雲端 App 安全性監視內部擁有者威脅。</li><li>使用雲端 App 安全性探索陰影 SaaS 的使用方式。</li></ul>|
|身分識別與存取管理|<ul><li>調整原則及工作處理程式。</li><li>使用 Azure AD Identity Protection 來識別內幕威脅。</li></ul>|
|資訊保護|精簡資訊保護原則： <ul><li>Microsoft 365 和 Office 365 敏感性標籤與資料遺失防護 (DLP) 或 Azure 資訊保護。</li><li>雲端 App 安全性原則及警示。</li></ul>|
|

另請參閱：[如何減輕例如 Petya 和 WannaCrypt 的快速網路攻擊](https://cloudblogs.microsoft.com/microsoftsecure/2018/02/21/how-to-mitigate-rapid-cyberattacks-such-as-petya-and-wannacrypt/) (英文)。
