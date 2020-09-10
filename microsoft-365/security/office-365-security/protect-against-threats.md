---
title: 防範威脅
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 09/08/2020
search.appverid:
- MOE150
- MET150
ms.assetid: b10023f6-f30f-45d3-b3ad-b71aa4aa0d58
ms.collection:
- M365-security-compliance
description: 系統管理員可以深入瞭解 Microsoft 365 中的威脅防護，並設定如何將它用於您的組織。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8b96ba1735f94e80450fa4f604fc45dc60b80d12
ms.sourcegitcommit: 74ef7179887eedc696c975a82c865b2d4b3808fd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/09/2020
ms.locfileid: "47417119"
---
# <a name="protect-against-threats"></a>防範威脅

以下是將高級威脅防護設定中斷為區塊的快速入門手冊。 如果您是 Office 365 中威脅防護功能的新功能，請不要確定開始的位置，或者，如果您想要 *這麼做*，請使用本指導方針做為檢查清單和開始點。

> [!IMPORTANT]
> **每種原則都包含初始建議設定，但有許多選項可供使用，您可以調整設定，以符合特定組織的需求**。 允許大約30分鐘的原則或變更以透過您的資料中心來運作。

## <a name="requirements"></a>需求

### <a name="subscriptions"></a>訂閱

威脅防護功能包含在 *所有* Microsoft 或 Office 365 訂閱中;不過，有些訂閱具有高級功能。 下表列出本文所含的保護功能及最低訂閱需求。

> [!TIP]
> 請注意，除了開啟審計的指示 *之外，還會啟動反* 惡意程式碼、反網路釣魚和反垃圾郵件，並標示為 Office 365 Exchange Online Protection (**EOP**) 的一部分。 這在「高級威脅防護」文章中看起來會是奇怪的，直到您記得) 包含的高級威脅防護 (**ATP** 包含，並在 EOP 中建立。

****

|保護類型|訂閱需求|
|---|---|
|用於報表目的的審計記錄 () |[Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|反惡意程式碼保護|[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (**EOP**) |
|防網路釣魚保護|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|反垃圾郵件保護|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|電子郵件的零小時自動清除 () |[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|保護電子郵件和 Office 檔中的惡意 URLs 和檔案 (安全連結和安全附件) |[Office 365 高級威脅防護](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (**ATP**) |
|開啟 SharePoint、OneDrive 和 Microsoft 小組工作負載的 ATP| [Atp](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?view=o365-worldwide)|
|高級反網路釣魚保護|[Atp](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|

### <a name="roles-and-permissions"></a>角色及權限

若要設定 ATP 原則，您必須在 [安全性 & 規範中心](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)中獲指派適當的角色。 請參閱下表，以取得可以執行這些動作的角色。

****

|角色或角色群組|深入瞭解|
|---|---|
|全域管理員|[關於 Microsoft 365 系統管理員角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|
|安全性系統管理員|[Azure Active Directory 中的系統管理員角色權限](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Exchange Online 組織管理|[Exchange Online 中的權限](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) <br>和<br> [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)|
|

若要深入瞭解，請參閱 [安全性與 &amp; 合規性中心的許可權](permissions-in-the-security-and-compliance-center.md)。

## <a name="before-you-begin-turn-on-audit-logging-for-reporting-and-investigation"></a>開始之前，請開啟報告和調查的審計記錄

儘早開始您的審核記錄。 您 **必須執行** 下列步驟的審計。 在包含 [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)的訂閱中可使用審核記錄。 為了在威脅防護報告中查看資料，例如 [安全性儀表板](security-dashboard.md)、 [電子郵件安全性報告](view-email-security-reports.md)和 [Explorer](threat-explorer.md)，必須 *啟用*審核記錄。 若要深入瞭解，請參閱 [開啟或關閉審核記錄搜尋](../../compliance/turn-audit-log-search-on-or-off.md)。

## <a name="part-1---anti-malware-protection"></a>第1部分-反惡意程式碼保護

在包含[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)的訂閱中提供[反惡意程式碼保護](anti-malware-protection.md)。

1. 在 [[安全性 & 規範中心](https://protection.office.com)] 中，選擇 [**威脅管理**  >  **原則**  >  **反惡意**代碼]。

2. 按兩下 **預設** 原則，然後選擇 [ **設定**]。

3. 指定下列設定：

    - 在 [ **惡意程式碼偵測回應** ] 區段中，保留預設設定 [ **否**]。

    - 在 [ **一般附件類型篩選** ] 區段中，選擇 [ **開啟**]。

4. 按一下 **[儲存]**。

若要深入瞭解反惡意程式碼原則選項，請參閱 [設定反惡意程式碼原則](configure-anti-malware-policies.md)。

## <a name="part-2---anti-phishing-protection"></a>第2部分-反網路釣魚保護

[防網路釣魚]

您可以在包含[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)的訂閱中取得[反網路釣魚防護](anti-phishing-protection.md)。 您可以使用 [ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)中的高級反網路釣魚防護。

下列程式說明如何設定 ATP 反網路釣魚原則。 設定不含 ATP) 的反網路釣魚原則 (，步驟類似。

1. 在 [[安全性 & 規範中心](https://protection.office.com)] 中，選擇 [**威脅管理**  >  **原則**  >  **ATP 反網路釣魚**]。

2. 按一下 [ **預設原則**]。

3. 在 [ **類比** ] 區段中，按一下 [ **編輯**]，然後指定下列設定：

   - 在 [**新增要保護的使用者**] 索引卷*標上，開啟保護。* 然後新增使用者，例如貴組織的董事會成員、CEO、CFO 和其他資深領導人。  (您可以輸入個別的電子郵件地址，或按一下以顯示清單。 ) 

   - 在 [ **新增要保護的網域** ] 索引標籤上，開啟 [ **自動包含我擁有的網域**]。 如果您有自訂網域，請立即新增。

   - 在 [**動作**] 索引標籤上，選取 [隔離**使用者**和模擬的**網域**] 選項的 **[郵件**]。 此外，開啟類比安全提示。

   - 在 [ **信箱智慧** ] 索引標籤上，確認已開啟信箱智慧，並開啟信箱智慧類比保護。 在 [ **如果模擬使用者傳送電子郵件** ] 清單中，選擇 [ **隔離郵件**]。

   - 在 [ **新增信任的寄件者和網域** ] 索引標籤上，指定您要新增的任何信任寄件者或網域。

   - 檢查您的設定之後，請**儲存**在 [**檢查您的設定**] 索引標籤。

4. 在 [ **哄騙** ] 區段中，按一下 [ **編輯**]，然後指定下列設定：

   - 在 [ **哄騙篩選設定** ] 索引標籤上，確定已開啟反欺詐保護。

   - 在 [ **動作** ] 索引標籤上，選擇 [ **隔離郵件**]。

   - 在您檢查您的變更之後，請**儲存**在 [**檢查您的設定**] 索引標籤。  (如果您未進行任何變更，請 **取消**。 ) 

5. 關閉 [預設原則設定] 頁面。

若要深入瞭解您的反網路釣魚原則選項，請參閱 [設定 ATP 反網路釣魚原則](configure-atp-anti-phishing-policies.md)。

## <a name="part-3---anti-spam-protection"></a>第3部分-反垃圾郵件保護

您可以在包含[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)的訂閱中取得[反垃圾郵件保護](anti-spam-protection.md)。

1. 在 [[安全性 & 規範中心](https://protection.office.com)] 中，選擇 [**威脅管理**  >  **原則**]  >  **反垃圾郵件**。

2. 在 [ **自訂** ] 索引標籤上，開啟 [自訂設定]。

3. 展開 [ **預設垃圾郵件篩選原則**]，按一下 [ **編輯原則**]，然後指定下列設定：

   - 在 [ **垃圾郵件及大量動作** ] 區段中，將臨界值設為5或6。

   - 在 [ **允許清單** ] 區段中，複查 (和/或編輯) 允許的寄件者和網域。

4. 按一下 **[儲存]**。

若要深入瞭解您的反垃圾郵件原則選項，請參閱 [在 EOP 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。

## <a name="part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments"></a>第4部分-防範惡意 URLs 和檔案 (安全連結和安全附件) 

在包含 [Office 365 atp](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (atp) 的訂閱中，可使用從惡意 URLs 和檔案進行的點擊時間防護。 它是透過 [Atp 安全附件](atp-safe-attachments.md) 和 [atp 安全連結](atp-safe-links.md) 原則進行設定。

### <a name="atp-safe-attachments-policies"></a>ATP 安全附件原則

若要設定 [Atp 安全附件](atp-safe-attachments.md)，您必須至少定義一個 Atp 安全附件原則。

1. 在 [[安全性 & 規範中心](https://protection.office.com)] 中，選擇 [**威脅管理**  >  **原則**  >  **ATP 安全附件**]。

2. 選取 [為 **SharePoint、OneDrive 和 Microsoft 團隊開啟 ATP**] 選項。

3. 在 [ **保護電子郵件附件** ] 區段中，按一下加號 (**+**) 。

4. 指定下列設定：

   - 在 [ **名稱** ] 方塊中，輸入 `Block malware` 。

   - 在 [回應] 區段中，選擇 [ **封鎖**]。

   - 在 [重新 **導向附件** ] 區段中，選取 [ **啟用重新導向**] 選項。 指定組織的安全性系統管理員或操作員的電子郵件地址，誰會檢查偵測到的檔案。

   - 在 [套用 **于** ] 區段中，選擇 **[收件者網域是**]。 然後，選取您的網域，選擇 [ **新增**]，然後選擇 **[確定]**。

5. **儲存**。

6.  (**建議的其他步驟**) 為全域系統管理員或 SharePoint Online 管理員，請針對您的 Microsoft 365 環境，以**DisallowInfectedFileDownload**參數設定為*true* ，以執行**[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** Cmdlet。  (此方式可防止使用者開啟、移動、複製或共用偵測為惡意的檔案。 ) 

若要深入瞭解，請參閱 [設定 office 365 Atp 安全附件原則](set-up-atp-safe-attachments-policies.md) ，並 [為 SharePoint、OneDrive 和 Microsoft 團隊開啟 office 365 ATP](turn-on-atp-for-spo-odb-and-teams.md)。

### <a name="atp-safe-links-policies"></a>ATP 安全連結原則

若要設定 [ATP 安全連結](atp-safe-links.md)，請複查和編輯您的預設原則，並新增特定使用者的原則。

1. 在 [[安全性 & 規範中心](https://protection.office.com)] 中，選擇 [**威脅管理**  >  **原則**  >  **ATP 安全連結**]。

2. 連按兩下 **預設** 原則。

3. 在 [ **使用安全連結** ] 區段中，選取 [ **Microsoft 365 應用程式適用于企業，Office iOS 和 Android**]，然後按一下 [ **儲存**]。

4. 在 [套用 **至特定** 收件者的原則] 區段中，按一下加號 (**+**) 。

5. 指定下列設定：

   - 在 [ **名稱** ] 方塊中，輸入名稱，例如 `Safe Links` 。

   - 在 [選取動作]**** 區段中，選擇 [開啟]****。

   - 選取下列選項：

     - **使用安全附件掃描可下載的內容**

     - **對組織內傳送的電子郵件套用安全連結**

     - **不要讓使用者點擊至原始 URL 的安全連結**

   - 在 [套用 **于** ] 區段中，選擇 **[收件者網域是**]。 然後，選取您的網域，選擇 [ **新增**]，然後選擇 **[確定]**。

6. **儲存**。

若要深入了解，請參閱[設定 Office 365 ATP 安全連結原則](set-up-atp-safe-links-policies.md)。

## <a name="part-5---turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams-workloads"></a>第5部分-開啟 SharePoint、OneDrive 和 Microsoft 小組工作負載的 ATP

SharePoint、OneDrive 和小組等工作負載都是為了共同作業而建立的。 使用 ATP 可協助封鎖和偵測小組網站和文件庫中識別為惡意的檔案。 您可以在 [這裡](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams?view=o365-worldwide)進一步閱讀該功能的詳細資訊。

> [!IMPORTANT]
> **開始此程式之前，請確定已為您的 Microsoft 365 環境開啟了審核記錄**。 這項工作通常是由在 Exchange Online 中獲派稽核記錄角色的人員完成。 如需詳細資訊，請參閱 [開啟或關閉審核記錄搜尋](../../compliance/turn-audit-log-search-on-or-off.md)！

1. 移至 <https://protection.office.com> 然後以您的公司或學校帳戶登入。

2. 在 [安全性 & 規範中心] 的左功能窗格中，選擇 [ **威脅管理**] 底下的 [ **原則** \> **安全附件**]。

   ![在 [安全性 & 規範中心] 中，選擇 [威脅管理 \> 原則]](../../media/08849c91-f043-4cd1-a55e-d440c86442f2.png)

3. 選取 **[開啟適用於 SharePoint、OneDrive 與 Microsoft Teams 的 ATP]**。

   ![開啟適用於 SharePoint Online、商務用 OneDrive 與 Microsoft Teams 的進階威脅防護](../../media/48cfaace-59cc-4e60-bf86-05ff6b99bdbf.png)

4. **儲存**。

5. 檢閱 (並視需要編輯) 組織的 [[安全附件原則]](set-up-atp-safe-attachments-policies.md) 和 [[安全連結原則]](set-up-atp-safe-links-policies.md)。

6.  (建議) 成為全域系統管理員或 SharePoint Online 管理員，請執行 **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** Cmdlet，並將 _DisallowInfectedFileDownload_ 參數設定為 *true*。

   - 將參數設定為 *true* 可封鎖偵測到的檔案的所有動作 (刪除除外)。 使用者將無法開啟、移動、複製或共用偵測到的檔案。

   - 將參數設定為 *false* 可封鎖所有動作 (刪除和下載除外)。 使用者可以選擇接受風險並下載偵測到的檔案。
   > [!TIP] 若要深入瞭解搭配 Microsoft 365 使用 PowerShell，請參閱使用 [PowerShell 管理 Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-with-microsoft-365-powershell)。

7. 允許最多30分鐘的變更，以散佈至所有 Microsoft 365 資料中心。


#### <a name="now-set-up-alerts-for-detected-files"></a>現在，設定偵測到檔案的警示

若要在 SharePoint Online、商務用 OneDrive 或 Microsoft Teams 中的檔案被識別為惡意檔案時收到通知，您可以設定警示。

1. 在 [ [安全性 & 規範中心](https://protection.office.com)] 中，選擇 [ **警示**] [ \> **管理提醒**]。

2. 選擇 **[新警示原則]**。

3. 指定警示的名稱。 例如，您可以輸入「程式庫中的惡意檔案」。

4. 輸入警示描述。 例如，當您在 SharePoint Online、OneDrive 或 Microsoft Teams 中偵測到惡意檔案時，您可以輸入「通知系統管理員」。

5. 在 [ **傳送此警示** 的時機 ...] 區段中，設定：

   a. 在 **[活動]** 清單中，選擇 **[已偵測到檔案中的惡意程式碼]**。

   b. 將 **[使用者]** 欄位保留空白。

6. 在 **[傳送此通知到...]** 區段中，選取一或多位全域系統管理員、安全性系統管理員，或在偵測到惡意檔案時應收到通知的安全性讀者。

7. **儲存**。

若要深入瞭解提醒，請參閱 [在安全性 & 規範中心建立活動警示](../../compliance/create-activity-alerts.md)。

> [!NOTE]
> 當您完成設定時，請使用下列連結來開始工作負載調查：
>- [檢視在 SharePoint、OneDrive 或 Microsoft Teams 中偵測到的惡意檔案資訊](malicious-files-detected-in-spo-odb-or-teams.md)
>- [在 SharePoint 線上、OneDrive 或 Microsoft 小組中找到惡意檔案時，要執行的動作](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
>- [在 Microsoft 365 中以系統管理員身分管理被隔離的郵件和檔案](manage-quarantined-messages-and-files.md) 

## <a name="part-6---additional-settings-to-configure"></a>第6部分-要設定的其他設定

在設定惡意程式碼、惡意 URLs 和檔案、網路釣魚和垃圾郵件的防護時，建議您設定零小時自動清除。

### <a name="zero-hour-auto-purge-for-email-in-eop"></a>EOP 中的電子郵件的自動清除零小時

在包含[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)的訂閱中可使用[零小時自動清除](zero-hour-auto-purge.md) (ZAP) 。 此保護功能預設為開啟狀態;不過，保護生效的情況必須符合下列條件：

- 垃圾[訊息原則](anti-spam-protection.md)中的垃圾郵件動作會設定為**將郵件移至 [垃圾郵件] 資料夾**。

- 使用者保留其預設的 [垃圾郵件設定](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)，但未關閉垃圾郵件保護。

若要深入瞭解，請參閱 [零時自動清除-防護垃圾郵件和惡意](zero-hour-auto-purge.md)代碼。

## <a name="post-setup-tasks-and-next-steps"></a>安裝後的工作及後續步驟

設定威脅防護功能之後，請務必監視這些功能的運作方式！ 複查和修訂您的原則，讓他們能執行您所需的工作。 此外，請留意可增加價值的新功能和服務更新。

****

|處理方式|可深入了解的資源|
|---|---|
|查看您的組織如何使用威脅防護功能，以查看報告|[安全性儀表板](security-dashboard.md)<br/>[電子郵件安全性報告](view-email-security-reports.md)<br/>[Office 365 ATP 報告](view-reports-for-atp.md)<br/>[威脅總管](threat-explorer.md)|
|視需要定期複查和修正威脅防護原則|[安全分數](../mtp/microsoft-secure-score.md)<br/>[智慧報告和洞察力](reports-and-insights-in-security-and-compliance.md)<br/>[Microsoft 365 威脅調查和回應功能](keep-users-safe-with-office-365-ti.md)|
|監視新功能和服務更新|[標準及目標發行選項](https://docs.microsoft.com/microsoft-365/admin/manage/release-options-in-office-365)<br/>[訊息中心](https://docs.microsoft.com/microsoft-365/admin/manage/message-center)<br/>[Microsoft 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)<br/>[服務說明](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|深入瞭解 EOP 和 ATP 的建議標準和嚴格安全設定的詳細資料 | [EOP 和 Office 365 ATP 安全性的建議設定](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp?view=o365-worldwide) |
