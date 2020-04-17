---
title: 保護 Office 365 中的威脅
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
ms.date: ''
search.appverid:
- MOE150
- MET150
ms.assetid: b10023f6-f30f-45d3-b3ad-b71aa4aa0d58
ms.collection:
- M365-security-compliance
description: 請使用本文做為指南，以立即設定威脅防護功能。
ms.openlocfilehash: 34a89f9db0ca7424d90909f09f7a2bfb4fcf3b6a
ms.sourcegitcommit: 9ed3283dd6dd959faeca5c22613f9126261b9590
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2020
ms.locfileid: "43528554"
---
# <a name="protect-against-threats-in-office-365"></a>保護 Office 365 中的威脅

Office 365 包含各種威脅防護功能。 以下是一個快速入門手冊，您可以用來做為檢查清單，以確保為您的組織設定威脅防護功能。 如果您是 Office 365 中威脅防護功能的新功能，或您不確定開始的位置，請使用下列指南做為開始點。

> [!IMPORTANT]
> **每種原則都包含初始建議設定，但有許多選項可供使用，您可以調整設定，以符合特定組織的需求**。 允許大約30分鐘的原則或變更以透過您的資料中心來運作。

## <a name="requirements"></a>需求

### <a name="subscriptions"></a>訂閱

威脅防護功能包含在所有 Office 365 訂閱中;不過，某些訂閱包含更多的高級功能。 下表列出本文所含的保護功能及最低訂閱需求。

|||
|---|---|
|**保護類型**|**訂閱需求**|
|反惡意程式碼保護|[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description) （EOP）|
|保護電子郵件和 Office 檔中的惡意 URLs 和檔案|[Office 365 高級威脅防護](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)（ATP）|
|反網路釣魚保護|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)|
|高級反網路釣魚保護|[Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|
|反垃圾郵件保護|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)|
|自動清除零小時（電子郵件）|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)|
|審核記錄（用於報告目的）|[Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description)|
|

### <a name="roles-and-permissions"></a>角色及權限

您必須獲指派適當的角色，才能設定[安全性 & 合規性中心](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)的原則。 下表包括一些範例：

|||
|---|---|
|**角色或角色群組**|**深入瞭解**|
|Office 365 全域系統管理員|[關於 Office 365 系統管理員角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)|
|安全性系統管理員|[Azure Active Directory 中的系統管理員角色權限](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Exchange Online 組織管理|[Exchange Online 中的權限](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) <br>和<br> [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)|
|

若要深入瞭解，請參閱[Office 365 安全性&amp;與合規性中心的許可權](permissions-in-the-security-and-compliance-center.md)。

## <a name="part-1---anti-malware-protection"></a>第1部分-反惡意程式碼保護

在包含[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)的訂閱中提供[反惡意程式碼保護](anti-malware-protection.md)。

1. 在 [[安全性 & 規範中心](https://protection.office.com)] 中，選擇 [**威脅管理** > **原則** > **反惡意**代碼]。

2. 按兩下**預設**原則，然後選擇 [**設定**]。

3. 指定下列設定：

    - 在 [**惡意程式碼偵測回應**] 區段中，保留預設設定 [**否**]。

    - 在 [**一般附件類型篩選**] 區段中，選擇 [**開啟**]。

4. 按一下 [儲存]****。

若要深入瞭解反惡意程式碼原則選項，請參閱[設定反惡意程式碼原則](configure-anti-malware-policies.md)。

## <a name="part-2---protection-from-malicious-urls-and-files"></a>第2部分-防護惡意 URLs 和檔案

在包含[Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) （atp）的訂閱中，可使用從惡意 URLs 和檔案進行的時刻防護，並透過[atp 安全附件](atp-safe-attachments.md)和[atp 安全連結](atp-safe-links.md)原則進行設定。

### <a name="atp-safe-attachments-policies"></a>ATP 安全附件原則

若要設定[Atp 安全附件](atp-safe-attachments.md)，您必須至少定義一個 Atp 安全附件原則。

1. 在 [[安全性 & 規範中心](https://protection.office.com)] 中，選擇 [**威脅管理** > **原則** > **ATP 安全附件**]。

2. 選取 [為**SharePoint、OneDrive 和 Microsoft 團隊開啟 ATP**] 選項。

3. 在 [**保護電子郵件附件**] 區段中，按一下加號**+**（）。

4. 指定下列設定：

   - 在 [**名稱**] 方塊中`Block malware`，輸入。

   - 在 [回應] 區段中，選擇 [**封鎖**]。

   - 在 [重新**導向附件**] 區段中，選取 [**啟用重新導向**] 選項，然後指定組織之安全性管理員或操作員的電子郵件地址，以查看偵測到的檔案。

   - 在 [套用**于**] 區段中，選擇 **[收件者網域是**]。 然後，選取您的網域，選擇 [**新增**]，然後按一下 **[確定]**。

5. 按一下 [儲存]****。

6. （**建議的其他步驟**）以全域管理員或 SharePoint Online 管理員的身分，針對您的 Office 365 環境執行**[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** Cmdlet 並將**DisallowInfectedFileDownload**參數設定為*true* 。 （這樣可防止使用者開啟、移動、複製或共用偵測為惡意的檔案。）

若要深入瞭解，請參閱[設定 office 365 Atp 安全附件原則](set-up-atp-safe-attachments-policies.md)，並[為 SharePoint、OneDrive 和 Microsoft 團隊開啟 office 365 ATP](turn-on-atp-for-spo-odb-and-teams.md)。

### <a name="atp-safe-links-policies"></a>ATP 安全連結原則

若要設定[ATP 安全連結](atp-safe-links.md)，請複查和編輯您的預設原則，並新增特定使用者的原則。

1. 在 [[安全性 & 規範中心](https://protection.office.com)] 中，選擇 [**威脅管理** > **原則** > **ATP 安全連結**]。

2. 連按兩下**預設**原則。

3. 在 [**使用安全連結**] 區段中，選取 [ **office 365 ProPlus]、[iOS 和 Android 的 office**] 選項，然後按一下 [**儲存**]。

4. 在 [套用**至特定**收件者的原則] 區段中，按一下**+** 加號（）。

5. 指定下列設定：

   - 在 [**名稱**] 方塊中，輸入名稱，例如`Safe Links`。

   - 在 [選取動作]**** 區段中，選擇 [開啟]****。

   - 選取下列選項：

     - **使用安全附件掃描可下載的內容**

     - **對組織內傳送的電子郵件套用安全連結**

     - **不要讓使用者點擊至原始 URL 的安全連結**

   - 在 [套用**于**] 區段中，選擇 **[收件者網域是**]。 然後，選取您的網域，選擇 [**新增**]，然後按一下 **[確定]**。

6. 按一下 [儲存]****。

若要深入了解，請參閱[設定 Office 365 ATP 安全連結原則](set-up-atp-safe-links-policies.md)。

## <a name="part-3---anti-phishing-protection"></a>第3部分-反網路釣魚保護

[防網路釣魚]

您可以在包含[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)的訂閱中取得[反網路釣魚防護](anti-phishing-protection.md)。 您可以使用[ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)中的高級反網路釣魚防護。

下列程式說明如何設定 ATP 反網路釣魚原則。 步驟類似于設定反網路釣魚原則（沒有 ATP）。

1. 在 [[安全性 & 規範中心](https://protection.office.com)] 中，選擇 [**威脅管理** > **原則** > **ATP 反網路釣魚**]。

2. 按一下 [**預設原則**]。

3. 在 [**類比**] 區段中，按一下 [**編輯**]，然後指定下列設定：

   - 在 [**新增要保護的使用者**] 索引標籤上，開啟 [保護]。 然後新增使用者，例如貴組織的董事會成員、CEO、CFO 和其他資深領導人。 （您可以輸入個別的電子郵件地址，或按一下以顯示清單）。

   - 在 [**新增要保護的網域**] 索引標籤上，開啟 [**自動包含我擁有的網域**]。 如果您有自訂網域，請同時新增這些網域。

   - 在 [**動作**] 索引標籤上，選取 [隔離**使用者**和模擬的**網域**] 選項的 **[郵件**]。 此外，開啟類比安全提示。

   - 在 [**信箱智慧**] 索引標籤上，確認已開啟信箱智慧。 此外，開啟信箱智慧型類比保護。 在 [**如果模擬使用者傳送電子郵件**] 清單中，選擇 [**隔離郵件**]。

   - 在 [**新增信任的寄件者和網域**] 索引標籤上，指定您要新增的任何信任寄件者或網域。

   - 在 [**複查您的設定**] 索引標籤上，在您檢查好設定後，按一下 [**儲存**]。

4. 在 [**哄騙**] 區段中，按一下 [**編輯**]，然後指定下列設定：

   - 在 [**哄騙篩選設定**] 索引標籤上，確定已開啟反欺詐保護。

   - 在 [**動作**] 索引標籤上，選擇 [**隔離郵件**]。

   - 在 [**複查您的設定**] 索引標籤上，在您檢查好設定後，按一下 [**儲存**]。 （如果您未進行任何變更，請按一下 [**取消**]）。

5. 關閉 [預設原則設定] 頁面。

若要深入瞭解您的反網路釣魚原則選項，請參閱[在 Office 365 中設定 ATP 反網路釣魚原則](configure-atp-anti-phishing-policies.md)。

## <a name="part-4---anti-spam-protection"></a>第4部分-反垃圾郵件保護

您可以在包含[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)的訂閱中取得[反垃圾郵件保護](anti-spam-protection.md)。

1. 在 [[安全性 & 規範中心](https://protection.office.com)] 中，選擇 [**威脅管理** > **原則** > ]**反垃圾郵件**。

2. 在 [**自訂**] 索引標籤上，開啟 [**自訂設定**]。

3. 展開 [**預設垃圾郵件篩選原則**]，按一下 [**編輯原則**]，然後指定下列設定：

   - 在 [**垃圾郵件及大量動作**] 區段中，將臨界值設為5或6。

   - 在 [**允許清單**] 區段中，複查（必要時編輯）您允許的寄件者和網域。

4. 按一下 [儲存]****。

若要深入瞭解您的反垃圾郵件原則選項，請參閱[設定 Office 365 中的反垃圾郵件原則](configure-your-spam-filter-policies.md)。

## <a name="part-5---additional-settings-to-configure"></a>第5部分-要設定的其他設定

除了設定惡意程式碼保護、惡意 URLs 和檔案、網路釣魚和垃圾郵件之外，我們建議您設定零小時自動清除和審核記錄設定。

### <a name="zero-hour-auto-purge-for-email"></a>電子郵件自動清除零小時

在包含[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)的訂閱中，可以使用[零小時自動清除](zero-hour-auto-purge.md)（ZAP）。 此保護功能預設為開啟狀態;不過，保護生效的情況必須符合下列條件：

- 垃圾[訊息原則](anti-spam-protection.md)中的垃圾郵件動作會設定為**將郵件移至 [垃圾郵件] 資料夾**。

- 使用者保留其預設的[垃圾郵件設定](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)，但未關閉垃圾郵件保護。

若要深入瞭解，請參閱[零時自動清除-防護垃圾郵件和惡意](zero-hour-auto-purge.md)代碼。

### <a name="audit-logging-for-reporting-and-investigation"></a>報告和調查的審計記錄

在包含[Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description)的訂閱中可使用審核記錄。 為了在威脅防護報告中查看資料（如[安全性儀表板](security-dashboard.md)、[電子郵件安全性報告](view-email-security-reports.md)和[Explorer](threat-explorer.md)），必須為您的組織開啟審核記錄。 若要深入瞭解，請參閱[開啟或關閉 Office 365 審核記錄搜尋](../../compliance/turn-audit-log-search-on-or-off.md)。

## <a name="post-setup-tasks"></a>安裝後的工作

設定威脅防護功能之後，請務必監視這些功能的運作方式、視需要複查及修改原則，以及觀賞新功能和服務更新。

|||
|---|---|
|**處理方式**|**可深入了解的資源**|
|查看您的組織如何使用威脅防護功能，以查看報告|[安全性儀表板](security-dashboard.md)<br/>[電子郵件安全性報告](view-email-security-reports.md)<br/>[Office 365 ATP 報告](view-reports-for-atp.md)<br/>[威脅總管](threat-explorer.md)|
|視需要定期複查和修正威脅防護原則|[安全分數](../mtp/microsoft-secure-score.md)<br/>[智慧報告和洞察力](reports-and-insights-in-security-and-compliance.md)<br/>[Office 365 威脅調查和回應功能](keep-users-safe-with-office-365-ti.md)|
|監視新功能和服務更新|[標準及目標發行選項](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide)<br/>[訊息中心](https://docs.microsoft.com/office365/admin/manage/message-center?view=o365-worldwide)<br/>[Microsoft 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)<br/>[服務說明](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|
