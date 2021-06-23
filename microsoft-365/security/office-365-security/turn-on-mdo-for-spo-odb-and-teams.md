---
title: 開啟適用於 SharePoint、OneDrive 和 Microsoft Teams 的安全附件
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 07e76024-0c80-40dc-8c48-1dd0d0f863cb
ms.collection:
- M365-security-compliance
- SPO_Content
description: 系統管理員可以瞭解如何開啟 SharePoint、OneDrive 和 Microsoft Teams 的保管庫附件，包括如何設定偵測到檔案的警示。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b64b3cfb29b3be999c9e26804e35dc4d02e48fbb
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083089"
---
# <a name="turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>開啟適用於 SharePoint、OneDrive 和 Microsoft Teams 的安全附件

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

適用于 SharePoint、OneDrive 和 Microsoft Teams 的 Microsoft Defender Office 365，可防止您的組織意外共用惡意檔案。 如需詳細資訊，請參閱[保管庫 SharePoint、OneDrive 和 Microsoft Teams 的附件](mdo-for-spo-odb-and-teams.md)。

本文包含啟用及設定 SharePoint、OneDrive 及 Microsoft Teams 的保管庫附件的步驟。

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 您於 <https://security.microsoft.com> 開啟 Microsoft 365 Defender 入口網站。 若要直接移至 [**保管庫附件**] 頁面，請開啟] <https://security.microsoft.com/safeattachmentv2> 。

- 若要開啟 SharePoint、OneDrive 和 Microsoft Teams 的保管庫附件，您必須是 Microsoft 365 Defender 入口網站中「**組織管理**」或「**安全性管理員**」角色群組的成員。 如需詳細資訊，請參閱 [Microsoft 365 Defender 入口網站中的權限](permissions-microsoft-365-security-center.md)。

- 若要使用 SharePoint 線上 PowerShell 以避免人員下載惡意檔案，您必須是[全域系統管理員](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator)的成員或 Azure AD 中[SharePoint 系統管理員](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator)角色。

- 確認已為您的組織啟用審核記錄。 如需詳細資訊，請參閱[開啟或關閉稽核記錄搜尋](../../compliance/turn-audit-log-search-on-or-off.md)。

- 允許最多30分鐘的設定才會生效。

## <a name="step-1-use-the-microsoft-365-defender-portal-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>步驟1：使用 Microsoft 365 Defender 入口網站開啟 SharePoint、OneDrive 及 Microsoft Teams 保管庫附件

1. 在 Microsoft 365 Defender 入口網站中，移至 [**原則 & 規則** 威脅原則原則] \>  \> 區段 \> **保管庫附件**。

2. 在 [**保管庫附件**] 頁面上，按一下 [**通用設定**]。

3. 在 [**全域設定**] 顯示的 [飛出] 中，移至 [SharePoint 中的 **檔、OneDrive 及 Microsoft Teams** ] 區段中的 [保護檔案]。

   移動 **SharePoint、OneDrive 及 Microsoft Teams** 切換至右開啟的 Office 365， ![ ](../../media/scc-toggle-on.png) 以開啟保管庫、SharePoint 和 OneDrive 的 Microsoft Teams 附件。

   完成後，按一下 [儲存]。

### <a name="use-exchange-online-powershell-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>使用 Exchange Online PowerShell 開啟 SharePoint、OneDrive 和 Microsoft Teams 保管庫附件

如果您不想使用 PowerShell 開啟 SharePoint、OneDrive 及 Microsoft Teams 的保管庫附件，請連線[至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) ，然後執行下列命令：

```powershell
Set-AtpPolicyForO365 -EnableATPForSPOTeamsODB $true
```

如需詳細的語法及參數資訊，請參閱 [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365)。

## <a name="step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files"></a>步驟2： (建議) 使用 SharePoint 線上 PowerShell 以避免使用者下載惡意檔

根據預設，使用者無法開啟、移動、複製或分享 <sup>\*</sup> 保管庫 SharePoint、OneDrive 及 Microsoft Teams 的附件所偵測到的惡意檔案。 不過，他們可以刪除及下載惡意檔案。

<sup>\*</sup> 如果使用者移至 [ **管理存取**]，則 [ **共用** ] 選項仍可供使用。

若要防止使用者下載惡意檔案，請[連線至 SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)並執行下列命令：

```powershell
Set-SPOTenant -DisallowInfectedFileDownload $true
```

**附註**：

- 這項設定會影響使用者和系統管理員。
- 人員仍可刪除惡意檔。

如需詳細的語法及參數資訊，請參閱 [Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant)。

## <a name="step-3-recommended-use-the-microsoft-365-defender-portal-to-create-an-alert-policy-for-detected-files"></a>建議的步驟 3 () 使用 Microsoft 365 Defender 入口網站來建立偵測到的檔案的警示原則

您可以建立警示原則，當 SharePoint、OneDrive 和 Microsoft Teams 的保管庫附件時，通知您和其他系統管理員偵測惡意檔案。 若要深入瞭解提醒，請參閱[在 Microsoft 365 Defender 入口網站中建立活動警示](../../compliance/create-activity-alerts.md)。

1. 在 Microsoft 365 Defender 入口網站中，移至 [**原則] & 規則** \> **警示原則**] 或 [開啟] <https://security.microsoft.com/alertpolicies> 。

2. 在 [ **警示原則** ] 頁面上，按一下 [ **新增警示原則**]。

3. **新的警示原則** 嚮導會在飛出時開啟。在 [**名稱您的提醒**] 頁面上，設定下列設定：
   - **名稱**：輸入唯一且具描述性的名稱。 例如，文件庫中的惡意檔案。
   - **描述**：輸入選用的描述。 例如，在 SharePoint 線上、OneDrive 或 Microsoft Teams 中偵測到惡意檔案時，會通知系統管理員。
   - **嚴重性**：從下拉式清單中選取 [ **低**]、[ **中**] 或 [ **高** ]。
   - **類別**：從下拉式清單中選取 [ **威脅管理** ]。

   完成後，按 [下一步 **]**。

4. 在 [ **建立警示設定** ] 頁面上，設定下列設定：
   - **您想要提醒什麼？** section \> **活動會** \> 從下拉式清單中選取 [ **在檔案中偵測到惡意** 代碼]。
   - **您要如何觸發警示？** 區段： **每次活動符合選取的規則時** 保留預設值。

   完成後，按 [下一步 **]**。

5. 在 [ **設定您** 的收件者] 頁面上，設定下列設定：
   - 確認已選取 [ **傳送電子郵件通知** ]。 在 [ **電子郵件** 收件者] 方塊中，選取一或多個全域管理員、安全性管理員或安全性讀者，當偵測到惡意檔案時，應該會收到通知。
   - **每日通知限制**：保留預設值 **沒有選取限制** 。

   完成後，按 [下一步 **]**。

6. 在 [ **複查您的設定** ] 頁面上，複查您的設定。 您可以在每個區段中選取 [編輯 **]**，以修改該區段內的設定。 或者，您可以按一下 [上一步] 或在精靈中選取特定頁面。

   在 [ **您想要立即開啟原則嗎？** ] 區段中，保留預設值 **[是]，並將其立即開啟** 為 [選取]。

   完成後，請按一下 **[完成]**。

### <a name="use-security--compliance-powershell-to-create-an-alert-policy-for-detected-files"></a>使用安全性 & 合規性 PowerShell 建立偵測到的檔案的警示原則

如果您想要使用 PowerShell 建立與上一節所述相同的警示原則，請連線 [至 Security & 合規性中心 PowerShell](/powershell/exchange/connect-to-scc-powershell) ，並執行下列命令：

```powershell
New-ActivityAlert -Name "Malicious Files in Libraries" -Description "Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams" -Category ThreatManagement -Operation FileMalwareDetected -NotifyUser "admin1@contoso.com","admin2@contoso.com"
```

**附注**：預設 _嚴重性_ 值是 Low。 若要指定「中」或「高」，請在命令中包含 _嚴重性_ 參數和值。

如需詳細的語法及參數資訊，請參閱 [New-ActivityAlert](/powershell/module/exchange/new-activityalert)。

### <a name="how-do-you-know-these-procedures-worked"></a>如何知道這些程序是否正常運作？

- 若要確認您是否已成功開啟 SharePoint、OneDrive 和 Microsoft Teams 的保管庫附件，請使用下列其中一個步驟：

  - 在 Microsoft 365 Defender 入口網站中，移 **&** 至 [原則] [規則 \> **威脅原則** 原則] \> 區段中 \> **保管庫附件**]，選取 [**通用設定**]，然後確認 [開啟 Office 365 的 Defender] 的值 **SharePoint、OneDrive 和 Microsoft Teams** 設定。

  - 在 Exchange Online PowerShell 中，執行下列命令來驗證屬性設定：

    ```powershell
    Get-AtpPolicyForO365 | Format-List EnableATPForSPOTeamsODB
    ```

    如需詳細的語法及參數資訊，請參閱 [AtpPolicyForO365](/powershell/module/exchange/get-atppolicyforo365)。

- 若要確認您是否已成功封鎖人員下載惡意檔案、開啟 SharePoint 線上 PowerShell，並執行下列命令，以確認屬性值：

  ```powershell
  Get-SPOTenant | Format-List DisallowInfectedFileDownload
  ```

  如需詳細的語法及參數資訊，請參閱 [Get-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant)。

- 若要確認您是否已成功設定偵測到的檔案的警示原則，請使用下列任何一項步驟：
  - 在 Microsoft 365 Defender 入口網站中，移至 [**原則] & 規則** \> **警示原則** \> 選取警示原則，然後驗證設定。
  - 在 Microsoft 365 Defender 入口網站 PowerShell 中， \<AlertPolicyName\> 以警示原則的名稱取代，執行下列命令，並確認屬性值：

    ```powershell
    Get-ActivityAlert -Identity "<AlertPolicyName>"
    ```

    如需詳細的語法及參數資訊，請參閱 [set-activityalert](/powershell/module/exchange/get-activityalert)。

- 使用 [[威脅防護狀態] 報告](view-email-security-reports.md#threat-protection-status-report)可查看 SharePoint、OneDrive 及 Microsoft Teams 中偵測到檔案的相關資訊。 具體而言，您可以使用 **View 資料：內容 \> 惡意程式碼** 視圖。
