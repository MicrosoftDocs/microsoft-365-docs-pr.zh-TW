---
title: 在 Microsoft Defender 中防禦威脅，以供 Office 365、反惡意程式碼、反網路釣魚、反垃圾郵件、保管庫連結、保管庫附件、零小時自動清除 (ZAP) ，MDO 的安全性設定
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: overview
localization_priority: Normal
ms.date: 06/22/2021
search.appverid:
- MOE150
- MET150
ms.assetid: b10023f6-f30f-45d3-b3ad-b71aa4aa0d58
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 系統管理員可以深入瞭解 Microsoft 365 中的威脅防護，並設定如何將它用於您的組織。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 31ca7c27e3be20e20c16004490bd2ecd5ca4ae05
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083677"
---
# <a name="protect-against-threats"></a>防範威脅

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

以下是將 Office 365 的 Defender 設定中斷為區塊的快速入門手冊。 如果您是 Office 365 中威脅防護功能的新功能，請不要確定開始的位置，或者，如果您想要瞭解，請使用本指導 *方針做為* 檢查清單和開始點。

> [!IMPORTANT]
> **每種原則都包含初始建議設定，但有許多選項可供使用，您可以調整設定，以符合特定組織的需求**。 允許大約30分鐘的原則或變更以透過您的資料中心來運作。
>
> 若要在 Office 365 中略過大多數原則的手動設定，您可以使用標準或嚴格層級的預先設定安全性原則。 如需詳細資訊，請參閱[EOP 和 Microsoft Defender for Office 365 中的預先設定安全性原則](preset-security-policies.md)。

## <a name="requirements"></a>需求

### <a name="subscriptions"></a>訂閱

威脅防護功能包含在 *所有* Microsoft 或 Office 365 訂閱中;不過，有些訂閱具有高級功能。 下表列出本文所含的保護功能及最低訂閱需求。

> [!TIP]
> 請注意，除了開啟審計的指示之外，還 *會啟動反* 惡意程式碼、反網路釣魚和反垃圾郵件，並標示為 Office 365 Exchange Online Protection (**EOP**) 的一部分。 這在 Office 365 文章的 defender 中看起來會是奇怪的，直到您記得 (**Defender for Office 365**) 包含]，並建立 EOP。

<br>

****

|保護類型|訂閱需求|
|---|---|
|用於報表目的的審計記錄 () |[Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|反惡意程式碼保護|[Exchange Online Protection](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (**EOP**) |
|防網路釣魚保護|[EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|反垃圾郵件保護|[EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|保護電子郵件中的惡意 URLs 和檔案，以及 Office 檔中的檔 (保管庫連結及保管庫附件) |[適用於 Office 365 的 Microsoft Defender](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|

### <a name="roles-and-permissions"></a>角色及權限

若要設定 Office 365 原則的 Defender，您必須獲指派適當的角色。 請參閱下表，以取得可以執行這些動作的角色。

<br>

****

|角色或角色群組|深入瞭解|
|---|---|
|全域管理員|[關於 Microsoft 365 系統管理員角色](../../admin/add-users/about-admin-roles.md)|
|安全性系統管理員|[Azure Active Directory 中的系統管理員角色權限](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Exchange Online 組織管理|[Exchange Online 中的權限](/exchange/permissions-exo/permissions-exo)|
|

若要深入瞭解，請參閱[Microsoft 365 Defender 入口網站中的許可權](permissions-microsoft-365-security-center.md)。

### <a name="turn-on-audit-logging-for-reporting-and-investigation"></a>開啟報告和調查的審計記錄

- 儘早開始您的審核記錄。 您必須執行下列其中一個 **步驟的審計** 。 您可以在包含[Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)的訂閱中使用審核記錄。 為了在威脅防護報告、 [電子郵件安全性報告](view-email-security-reports.md)和 [Explorer](threat-explorer.md)中查看資料，必須 *啟用* 審核記錄。 若要深入瞭解，請參閱 [開啟或關閉審核記錄搜尋](../../compliance/turn-audit-log-search-on-or-off.md)。

## <a name="part-1---anti-malware-protection-in-eop"></a>第1部分-EOP 中的反惡意程式碼保護

如需有關反惡意程式碼建議設定的詳細資訊，請參閱 [EOP 防盜-惡意程式碼原則設定](recommended-settings-for-eop-and-office365.md#eop-anti-malware-policy-settings)。

1. 在 Microsoft 365 Defender 入口網站中，開啟 [**反惡意** 代碼] 頁面 <https://security.microsoft.com/antimalwarev2> 。

2. 在 [ **反惡意** 代碼] 頁面上，透過按一下名稱，選取名為 **default (default)** 的原則。

3. 在開啟的 [原則詳細資料] 浮出視窗中，按一下 [ **編輯保護設定**]，然後設定下列設定：
   - **保護設定** 區段：
     - 選取 **[啟用通用附件篩選** ] 以開啟通用附件篩選器。 按一下 [ **自訂檔案類型** ]，以新增更多檔案類型。
     - **為惡意程式碼啟用零小時自動清除**：確認已選取此設定。 如需有關惡意程式碼之 ZAP 的詳細資訊，請參閱 [零小時自動清除 (zap) 惡意](zero-hour-auto-purge.md#zero-hour-auto-purge-zap-for-malware)代碼。
   - **通知** 區段：確認未選取任何通知設定。

   完成後，按一下 [儲存]。

4. 回到原則詳細資料飛出視窗，按一下 [關閉 **]**。

如需設定反惡意程式碼原則的詳細指示，請參閱 [在 EOP 中設定反惡意程式碼原則](configure-anti-malware-policies.md)。

## <a name="part-2---anti-phishing-protection-in-eop-and-defender-for-office-365"></a>第2部分-EOP 和 Defender for Office 365 中的反網路釣魚防護

您可以在包含[EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)的訂閱中取得[反網路釣魚防護](anti-phishing-protection.md)。 [Office 365 的 Defender](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)中提供高級反網路釣魚防護。

如需有關反網路釣魚原則建議設定的詳細資訊，請參閱 EOP 的 Microsoft Defender 中的[反網路釣魚原則設定](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings)和[反網路釣魚原則設定，以取得 Office 365](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)。

下列程式說明如何設定預設的反網路釣魚原則。 Office 365 中只會有明確標示的設定。

1. 在 Microsoft 365 Defender 入口網站中開啟 [**反網路釣魚**] 頁面，網址為 <https://security.microsoft.com/antiphishing> 。

2. 在 [ **反網路釣魚** 網頁] 頁面上，選取名為 **Office365 AntiPhish default 的原則 (預設)** ，方法是按一下名稱。

3. 在出現的 [原則詳細資料] 浮出視窗中，設定下列設定：
   - **網路釣魚閥值 & 保護** 區段：按一下 [ **編輯防護設定** ]，並在開啟的浮出控制項中設定下列設定：
     - **網路釣魚電子郵件閥值** <sup>\*</sup> ：選取 **2-嚴格** (標準) 或 **3 個** 嚴格 (嚴格) 。
     - **類比** 區段 <sup>\*</sup> ：設定下列值：
       - 選取 [ **允許使用者進行保護**]，然後按一下所出現的 [ **管理 (nn) 寄件者 (])** 連結，然後新增內部和外部寄件者，以防止假冒，例如組織的董事會成員、CEO、CFO 和其他資深領導人。
       - 選取 [ **啟用要保護的網域**]，然後設定出現下列設定：
         - 選取 [ **包含我擁有的網域** ]，以保護您公認的網域中的內部寄件者 (可見，請按一下 [ **View my** domain) 類比]。
         - 若要保護其他網域中的寄件者，請選取 [ **包含自訂網域**]，然後按一下所出現的 [ **管理 (nn) 自訂網域 (])** 連結，然後新增其他網域，以防止假冒。
     - **新增信任的寄件者和網域** 區段 <sup>\*</sup> ：按一下 [ **管理 (nn) 信任的寄件者] (s) 和網域 ()** ，設定寄件者和寄件者網域例外狀況，以根據需要設定模擬保護
     - 信箱智慧設定 <sup>\*</sup> ：確認已選取 [ **啟用信箱智慧** ] 和 [ **啟用類比保護的智慧** ]。
     - **哄騙** 區段：確認已選取 [ **啟用欺騙智慧** ]。

     完成後，按一下 [儲存]。

   - **動作** 區段：按一下 [ **編輯動作** ]，並在開啟的飛入視窗中設定下列設定：
     - **郵件動作** 區段：設定下列設定：
       - **如果偵測到郵件為模仿的使用者** <sup>\*</sup> ：選取 **[隔離郵件**]。
       - **如果偵測到郵件為類比的網域** <sup>\*</sup> ：請選取 **[隔離郵件**]。
       - **如果信箱智慧偵測到模仿的使用者** <sup>\*</sup> ：選取 **[將郵件移至收件者的垃圾郵件資料夾**] (標準) 或 **隔離郵件** (Strict) 。
       - **如果偵測到郵件為欺騙**：請選取 **[將郵件移至收件者的垃圾郵件資料夾** ] (標準) 或 **隔離郵件** (Strict) 。
     - **安全性秘訣 & 指示** 區段：設定下列設定：
       - **顯示第一個連絡人安全提示**：選取 [ (開啟) ]。
       - **顯示使用者模擬安全提示** <sup>\*</sup> ：選取 (開啟) ]。
       - **顯示網域模擬安全提示** <sup>\*</sup> ：選取 (開啟) ]。
       - **顯示使用者模擬不尋常的字元安全提示** <sup>\*</sup> ：選取 (開啟) 。
       - **顯示 (？ ) 以取得未驗證之寄件者的欺騙**：選取 (開啟) 。
       - **顯示「透過」標記**：選取 (開啟) 。

     完成後，按一下 [儲存]。

   <sup>\*</sup>此設定僅適用于 Office 365 的 Defender。

4. 按一下 [**儲存**]，然後按一下 [**關閉**]

如需設定反網路釣魚原則的詳細指示，請參閱[在 EOP 中設定反網路釣魚原則](configure-anti-phishing-policies-eop.md)及[設定 Microsoft Defender 中的反網路釣魚原則，以供 Office 365](configure-mdo-anti-phishing-policies.md)。

## <a name="part-3---anti-spam-protection-in-eop"></a>第3部分-EOP 中的反垃圾郵件保護

如需有關反垃圾郵件建議設定的詳細資訊，請參閱 [EOP 反垃圾郵件原則設定](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)。

1. 在 Microsoft 365 Defender 入口網站中開啟 **反垃圾郵件原則** 頁面，網址為 <https://security.microsoft.com/antispam> 。

2. 在 [ **反垃圾郵件原則** ] 頁面上，從清單中選取名稱為 [ **反垃圾郵件輸入原則 (預設)** ] 的原則。

3. 在出現的 [原則詳細資料] 浮出視窗中，設定下列設定：
   - **大量電子郵件閾值 & 垃圾郵件屬性** ] 區段：按一下 [ **編輯垃圾郵件閾值和屬性**]。 在出現的浮出控制項中，設定下列設定：
     - **大量電子郵件閥** 值：將此值設為 5 (Strict) 或 6 (Standard) 。
     - 保留其他設定的預設值 (**Off** 或 **None**) 。

     完成後，按一下 [儲存]。

   - **動作** 區段：按一下 [ **編輯動作**]。 在出現的浮出控制項中，設定下列設定：
     - **郵件動作** 區段：
       - **垃圾郵件**：確認已選取 [ **將郵件移至垃圾郵件資料夾** ] (標準) 或選取 [ **隔離郵件** (Strict) ]。
       - **高度信賴的垃圾郵件**：選取 **隔離郵件**。
       - **網路釣魚**：選取 **隔離郵件**。
       - **高信賴網路釣魚**：確認已選取 **隔離郵件** 。
       - **大量**：確認已選取 [ **將郵件移至垃圾郵件資料夾** ] (標準) 或選取 [ **隔離郵件** (Strict) ]。
     - **在隔離期間保留這數天的垃圾郵件**：確認 **30** 天的值。
     - **啟用垃圾郵件安全提示**：確認已選取此設定 (開啟) 。
     - **啟用以零小時自動清除 (ZAP)**：確認已選取此設定 (開啟) 。
       - **啟用網路釣魚郵件**：確認已選取此設定 (開啟) 。 如需詳細資訊，請參閱 [零小時自動清除 (用於網路釣魚的 ZAP) ](zero-hour-auto-purge.md#zero-hour-auto-purge-zap-for-phishing)。
       - **啟用垃圾郵件訊息**：確認已選取此設定 (開啟) 。 如需詳細資訊，請參閱 [零小時自動清除 (用於垃圾郵件的 ZAP) ](zero-hour-auto-purge.md#zero-hour-auto-purge-zap-for-spam)。
     - **通知** 區段：
       - 選取 [ **啟用使用者垃圾郵件通知**]。
         - **每 (天) 傳送一次使用者垃圾郵件通知**：確認 **3** 天的值。
         - **語言**：確認值為 [ **預設** 值] 或 [選取語言]。

     完成後，按一下 [儲存]。

   - **允許與封鎖的寄件者和網域** 區段：如 EOP 中的 [ [建立封鎖的寄件者清單](create-block-sender-lists-in-office-365.md) ] 或 [ [在 EOP 中建立安全的寄件者清單](create-safe-sender-lists-in-office-365.md)] 中所述，查看或編輯允許的

     完成後，按一下 [儲存]。

4. 完成時，請按一下 [關閉]。

如需設定反垃圾郵件原則的詳細指示，請參閱 [在 EOP 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。

## <a name="part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365"></a>第4部分-從惡意 URLs 和檔案 (在 Office 365 的 Defender 中保管庫連結及保管庫附件進行防護) 

在包含[Microsoft Defender for Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)的訂閱中，可使用從惡意 URLs 和檔案進行時間的防護。 它是透過[保管庫附件](safe-attachments.md)和[保管庫連結](safe-links.md)原則進行設定。

### <a name="safe-attachments-policies-in-microsoft-defender-for-office-365"></a>保管庫Microsoft Defender 中 Office 365 的附件原則

如需保管庫附件建議設定的詳細資訊，請參閱。[保管庫附件設定](recommended-settings-for-eop-and-office365.md#safe-attachments-settings)。

1. 開啟 Microsoft 365 Defender 入口網站中的 [**保管庫附件**] 頁面，網址為 <https://security.microsoft.com/safeattachmentv2> 。

2. 在 [**保管庫附件**] 頁面上，按一下 [**通用設定**]，然後在出現的快顯視窗上設定下列設定：
   - **針對 SharePoint、OneDrive 及 Microsoft Teams 開啟 Office 365 的 Defender**：開啟此設定， (上的 [開啟] ![ ](../../media/scc-toggle-on.png) 。

     > [!IMPORTANT]
     > 在 **您開啟 SharePoint、OneDrive 及 Microsoft Teams 的保管庫附件之前，請確認已開啟組織中的審計記錄**。 此項動作通常是由已在 Exchange Online 中指派「審計記錄」角色的人員所執行。 如需詳細資訊，請參閱 [開啟或關閉審核記錄搜尋](../../compliance/turn-audit-log-search-on-or-off.md)！

   - **開啟 Office 用戶端的保管庫檔**：開啟此設定 (![ 開啟 ](../../media/scc-toggle-on.png)) 。 請注意，這項功能只有 Microsoft 365 E5 或 Microsoft 365 E5 安全性授權才能使用且有意義。
   - **即使保管庫檔識別為惡意的檔案，也可讓使用者依序按一下 [受保護的檢視**]：確認已關閉此設定 (![) 關閉] ](../../media/scc-toggle-off.png) 。

   完成後，請按一下 [儲存]。

3. 回到 [**保管庫附件**] 頁面上，按一下 [ ![ 建立圖示] ](../../media/m365-cc-sc-create-icon.png) 。

4. 在開啟的 [**建立保管庫附件原則**] 嚮導中，設定下列設定：
   - [**命名您的原則**] 頁面：
     - **名稱**：輸入一些獨特且具描述性的描述。
     - **描述**：輸入選擇性描述。
   - [**使用者和網域**] 頁面：由於這是您的第一個原則，您可能想要最大化覆蓋範圍，請考慮在 [**網域**] 方塊中輸入 [公認的網域](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)。 否則，您可以使用 [ **使用者** 和 **群組** ] 方塊，以進行更精細的控制。 您可以選取 [ **排除這些使用者、群組和網域** ]，並輸入值，以指定例外狀況。
   - **設定** 頁面：
     - **保管庫附件未知的惡意程式碼回應**： Select **Block**。
     - **以偵測到的附件重新導向附件** ： **Enable 重新導向**：開啟此設定 (選取) 並輸入電子郵件地址來接收偵測到的郵件。
     - **如果掃描無法完成 (超時或錯誤，請套用保管庫附件偵測回應)**：確認已選取此設定。

5. 完成後，請按一下 [ **提交**]，然後按一下 [ **完成**]。

6.  (建議) 成為全域系統管理員或 SharePoint online 管理員，請執行 **[Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant)** Cmdlet，並將 _DisallowInfectedFileDownload_ 參數設定為 `$true` SharePoint 線上 PowerShell。
   - `$true` 封鎖針對偵測到的檔案 (刪除) 以外的所有動作。 使用者無法開啟、移動、複製或共用偵測到的檔案。
   - `$false` 封鎖除 Delete 和下載中心以外的所有動作。 使用者可以選擇接受風險並下載偵測到的檔案。

7. 允許最多30分鐘的變更，以散佈至所有的 Microsoft 365 資料中心。

如需設定保管庫附件的保管庫附件原則及全域設定的詳細指示，請參閱下列主題：

- [在 Microsoft Defender 中設定 Office 365 的保管庫附件原則](set-up-safe-attachments-policies.md)
- [開啟適用於 SharePoint、OneDrive 和 Microsoft Teams 的安全附件](turn-on-mdo-for-spo-odb-and-teams.md)
- [Microsoft 365 E5 中的安全文件](safe-docs.md)

### <a name="safe-links-policies-in-microsoft-defender-for-office-365"></a>保管庫Microsoft Defender 中 Office 365 的連結原則

如需保管庫連結之建議設定的詳細資訊，請參閱[保管庫連結設定](recommended-settings-for-eop-and-office365.md#safe-links-settings)。

1. 開啟 Microsoft 365 Defender 入口網站中的 [**保管庫連結**] 頁面，網址為 <https://security.microsoft.com/safelinksv2> 。

2. 在 [**保管庫連結**] 頁面上，按一下 [**通用設定**]，然後在出現的快顯視窗上設定下列設定：
   - **適用于支援的 Office 365 應用程式區段中的內容的設定**：
     - **使用 Office 365 應用程式中的保管庫連結**：確認此設定已開啟 (![) 上的 [切換] ](../../media/scc-toggle-on.png) 。
     - **當使用者在 Office 365 應用程式中按一下受保護連結時，請勿追蹤**：關閉此設定 (關閉 ![ ](../../media/scc-toggle-off.png)) 
     - **請勿讓使用者在 Office 365 應用程式中按原始 URL**：確認此設定已開啟 ![) 上 (開啟] ](../../media/scc-toggle-on.png) 。

   完成後，請按一下 [儲存]。

3. 回到 [**保管庫連結**] 頁面上，按一下 [ ![ 建立圖示] ](../../media/m365-cc-sc-create-icon.png) 。

4. 在開啟的 [**建立保管庫連結原則**] 嚮導中，設定下列設定：
   - [**命名您的原則**] 頁面：
     - **名稱**：輸入一些獨特且具描述性的描述。
     - **描述**：輸入選擇性描述。
   - [**使用者和網域**] 頁面：由於這是您的第一個原則，您可能想要最大化覆蓋範圍，請考慮在 [**網域**] 方塊中輸入 [公認的網域](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)。 否則，您可以使用 [ **使用者** 和 **群組** ] 方塊，以進行更精細的控制。 您可以選取 [ **排除這些使用者、群組和網域** ]，並輸入值，以指定例外狀況。
   - [**保護設定**] 頁面：
     - **在郵件中選取未知可能惡意 URLs 的動作** **：開啟此設定。**
     - **選取 Microsoft Teams 內未知或可能惡意 URLs 的動作** **：開啟此設定。** 從3月2020起，此設定是在預覽中，且僅適用 Microsoft Teams 技術採用計畫的成員 (點擊) 。
     - **對指向檔案的可疑連結和連結套用即時 URL 掃描**：選取此設定 (開啟) 。
       - **等候 URL 掃描完成後傳遞郵件**：選取此設定 (開啟) 。
     - 套用 **保管庫連結至組織內傳送的電子郵件**：選取此設定 (開啟) 。
     - **請勿追蹤使用者點擊**：請確認未選取此設定 (關閉) 。
     - **請勿讓使用者依序按一下原始 URL**：確認此設定已開啟選取的)  (。
     - **在通知和警告頁面上顯示組織商標**：選取此設定 (會在您已遵循 [自訂群組織的 Microsoft 365 主題](../../admin/setup/customize-your-organization-theme.md)，以上傳公司徽標之後，才將其開啟) 。
     - **請勿重新寫入下列 URLs**：我們沒有此設定的特別建議。 如需詳細資訊，請參閱[保管庫連結原則中的「不要重新寫入下列 URLs」清單](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)。
   - **通知** 頁面：
     - **您要如何通知使用者？** 區段：您也可以選取 [ **使用自訂通知文字** ] 來輸入要使用的自訂通知文字。 您也可以選取 [**使用 Microsoft 翻譯工具以進行自動當地語系化**，將自訂通知文字轉譯為使用者語言。 否則，請選取 **[使用預設的通知文字** ]。

5. 完成後，請按一下 [ **提交**]，然後按一下 [ **完成**]。

如需設定保管庫連結的保管庫連結原則及全域設定的詳細指示，請參閱下列主題：

- [在 Microsoft Defender 中設定 Office 365 的保管庫連結原則](set-up-safe-links-policies.md)
- [針對 Office 365 設定 Microsoft Defender 中保管庫連結的全域設定](configure-global-settings-for-safe-links.md)

### <a name="now-set-up-alerts-for-detected-files-in-sharepoint-online-or-onedrive-for-business"></a>現在在 SharePoint Online 或商務用 OneDrive 中設定偵測到檔案的警示

若要在 SharePoint Online 中的檔案或商務用 OneDrive 識別為惡意的檔案時收到通知，您可以依照本節所述來設定警示。

1. 在 Microsoft 365 Defender 入口網站上 <https://security.microsoft.com> ，移至 **電子郵件 &** 共同作業原則 \> **& 規則** \> **警示原則**。

2. 在 [ **警示原則** ] 頁面上，按一下 [ **新增警示原則**]。

3. [ **新增警示原則** ] 嚮導隨即開啟。 在 [ **名稱** ] 頁面上，設定下列設定：
   - **名稱**：輸入唯一且具描述性的名稱。 例如，您可以輸入「程式庫中的惡意檔案」。
   - **描述**：輸入選擇性描述。
   - **嚴重性**：選取 [ **低**]、[ **中** ] 或 [ **高**]。
   - **類別**：選取 **威脅管理**。

   完成後，請按 **[下一步]**

4. 在 [ **建立警示設定** ] 頁面上，設定下列設定：
   - **您想要提醒什麼？** section： **活動** 偵測 \> **到檔中的惡意** 代碼。
   - **您要如何觸發提醒** ] 區段： **每次活動符合規則** 時請驗證。

   完成後，請按 **[下一步]**

5. 在 [ **設定您** 的收件者] 頁面上，設定下列設定：
   - **傳送電子郵件通知**：請確認此設定為 selcted。
   - **電子郵件** 收件者：選取一或多個全域管理員、安全性管理員或安全性讀者，當偵測到惡意檔案時，應該會收到通知。
   - **每日通知限制**：請確認 **未選取限制** 。

   完成後，請按 **[下一步]**

6. 在 [ **複查您的設定** ] 頁面上，複查您的設定，並確認 **[是]，已選取 [立即開啟** ]，然後按一下 **[完成]**

若要深入瞭解警示原則，請參閱[Microsoft 365 合規性中心中的警示原則](../../compliance/alert-policies.md)。

> [!NOTE]
> 當您完成設定時，請使用下列連結來開始工作負載調查：
>
>- [威脅防護狀態報告](view-email-security-reports.md#threat-protection-status-report)
>- [使用 Microsoft 365 Defender 入口網站管理 Defender 中的隔離檔案 Office 365](manage-quarantined-messages-and-files.md#use-the-microsoft-365-defender-portal-to-manage-quarantined-files-in-defender-for-office-365)
>- [在 SharePoint 線上、OneDrive 或 Microsoft Teams 中找到惡意檔案時要執行的動作](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
>- [在 Microsoft 365 中以系統管理員身分管理被隔離的郵件和檔案](manage-quarantined-messages-and-files.md)

## <a name="post-setup-tasks-and-next-steps"></a>安裝後的工作及後續步驟

設定威脅防護功能之後，請務必監視這些功能的運作方式！ 複查和修訂您的原則，讓他們能執行您所需的工作。 此外，請留意可增加價值的新功能和服務更新。

<br>

****

|處理方式|可深入了解的資源|
|---|---|
|查看您的組織如何使用威脅防護功能，以查看報告|[電子郵件安全性報告](view-email-security-reports.md) <p> [Microsoft Defender for Office 365 報告](view-reports-for-mdo.md) <p> [威脅總管](threat-explorer.md)|
|視需要定期複查和修正威脅防護原則|[安全分數](../defender/microsoft-secure-score.md) <p> [Microsoft 365 威脅調查和回應功能](./office-365-ti.md)|
|監視新功能和服務更新|[標準及目標發行選項](../../admin/manage/release-options-in-office-365.md) <p> [訊息中心](../../admin/manage/message-center.md) <p> [Microsoft 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection) <p> [服務說明](/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|
