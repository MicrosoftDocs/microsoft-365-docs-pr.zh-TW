---
title: 開啟 Microsoft Defender for Office 365-SharePoint、OneDrive、& 團隊
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 07e76024-0c80-40dc-8c48-1dd0d0f863cb
ms.collection:
- M365-security-compliance
- SPO_Content
description: 了解如何開啟適用於 SharePoint、OneDrive 和 Teams 的 ATP，包括如何為偵測到的檔案設定警示。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 44d487810156d5de5ae152e08040e8dccd2a4ee0
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/15/2020
ms.locfileid: "49682588"
---
# <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>開啟適用於 SharePoint、OneDrive 與 Microsoft Teams 的 ATP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

適用于 SharePoint、OneDrive 和 Microsoft 團隊的 microsoft Defender for Office 365，可防止您的組織意外共用惡意檔案。 如需詳細資訊，請參閱 [SharePoint、OneDrive 和 Microsoft 小組的 ATP](atp-for-spo-odb-and-teams.md)。

本文包含啟用及設定 SharePoint、OneDrive 和 Microsoft 小組之 ATP 的步驟。

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 您要在 <https://protection.office.com> 開啟安全性與合規性中心。 若要直接移至 [ **ATP 安全附件** ] 頁面，請開啟] <https://protection.office.com/safeattachmentv2> 。

- 若要為 SharePoint、OneDrive 和 Microsoft 團隊開啟 ATP，您必須是 [安全性 & 規範中心] 中「 **組織管理** 」或「 **安全性管理員** 」角色群組的成員。 如需詳細資訊，請參閱[安全性與合規性中心中的權限](permissions-in-the-security-and-compliance-center.md)。

- 若要使用 SharePoint 線上 PowerShell 以避免人員下載惡意檔案，您必須是 [全域系統管理員](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) 的成員或 Azure AD 中 [SharePoint 系統管理員](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) 角色。

- 確認已為您的組織啟用審核記錄。 如需詳細資訊，請參閱[開啟或關閉稽核記錄搜尋](../../compliance/turn-audit-log-search-on-or-off.md)。

- 允許最多30分鐘的設定才會生效。

## <a name="step-1-use-the-security--compliance-center-to-turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>步驟1：使用安全性 & 合規性中心開啟 SharePoint、OneDrive 和 Microsoft 小組的 ATP

1. 在 [安全性 & 規範中心] 中，移至 [ **威脅管理** \> **原則** \> **ATP 安全附件**]，然後按一下 [ **通用設定**]。

2. 在 [ **全域設定** ] 中顯示的 [飛出] 中，移至 [ **開啟 ATP] SharePoint、[OneDrive] 和 [Microsoft 小組** ] 設定。 將切換移至右 ![ 切換開啟， ](../../media/scc-toggle-on.png) 以開啟 SharePoint、OneDrive 和 Microsoft 小組的 ATP。

   完成後，按一下 [儲存]。

### <a name="use-exchange-online-powershell-to-turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>使用 Exchange Online PowerShell 開啟 SharePoint、OneDrive 和 Microsoft 小組的 ATP

如果您不想使用 PowerShell 開啟 SharePoint、OneDrive 和 Microsoft 小組的 ATP，請連線 [至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) 並執行下列命令：

```powershell
Set-AtpPolicyForO365 -EnableATPForSPOTeamsODB $true
```

如需詳細的語法及參數資訊，請參閱 [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)。

## <a name="step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files"></a>步驟2： (建議) 使用 SharePoint 線上 PowerShell 以避免使用者下載惡意檔

根據預設，使用者無法開啟、移動、複製或共用 ATP 所偵測到的惡意檔案。 不過，他們可以刪除及下載惡意檔案。

若要防止使用者下載惡意檔案，請 [連線至 SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) 並執行下列命令：

```powershell
Set-SPOTenant -DisallowInfectedFileDownload $true
```

**附註**：

- 這項設定會影響使用者和系統管理員。
- 人員仍可刪除惡意檔。

如需詳細的語法及參數資訊，請參閱 [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)。

## <a name="step-3-recommended-use-the-security--compliance-center-to-create-an-alert-policy-for-detected-files"></a>建議的步驟 3 () 使用安全性 & 合規性中心建立偵測到的檔案的警示原則

您可以建立警示原則，當 SharePoint、OneDrive 和 Microsoft 小組偵測到惡意檔案時，通知您及其他系統管理員。 若要深入瞭解提醒，請參閱 [在安全性 & 規範中心建立活動警示](../../compliance/create-activity-alerts.md)。

1. 在 [ [安全性 & 規範中心](https://protection.office.com)] 中，移至 [ **警示** \> **警示原則** ] 或 [開啟] <https://protection.office.com/alertpolicies> 。

2. 在 [ **警示原則** ] 頁面上，按一下 [ **新增警示原則**]。

3. **新的警示原則** 嚮導會在飛出時開啟。在 [**名稱您的提醒**] 頁面上，設定下列設定：

   - **名稱**：輸入唯一且具描述性的名稱。 例如，文件庫中的惡意檔案。
   - **描述**：輸入選用的描述。 例如，在 SharePoint 線上、OneDrive 或 Microsoft 小組中偵測到惡意檔案時，會通知系統管理員。
   - **嚴重性**：保持選取的預設值為 [ **低** ]，或選取 [ **中** ] 或 [ **高**]。
   - **選取類別**： [選取 **威脅管理**]。

   完成後，按 [下一步]。

4. 在 [ **建立警示設定** ] 頁面上，設定下列設定：

   - **您要在哪個專案上發出警示？：活動是**：選取 [檔案 **中偵測到惡意** 代碼]。
   - **您要如何觸發警示？**： **每次活動符合選取的規則時** ，請保留預設值。

   完成後，按 [下一步]。

5. 在 [ **設定您** 的收件者] 頁面上，設定下列設定：

   - **傳送電子郵件通知**：確認已選取此設定。 在 [ **電子郵件** 收件者] 方塊中，選取一或多個全域管理員、安全性管理員或安全性讀者，當偵測到惡意檔案時，應該會收到通知。
   - **每日通知限制**：保留預設值 **沒有選取限制** 。

   完成後，按 [下一步]。

6. 在 [ **複查您的設定** ] 頁面上，複查設定，然後按一下任何區段中的 [ **編輯** ] 進行變更。

   在 [ **您想要立即開啟原則嗎？** ] 區段中，保留預設值 **[是]，並將其立即開啟** 為 [選取]。

   完成後，請按一下 **[完成]**。

### <a name="use-security--compliance-powershell-to-create-an-alert-policy-for-detected-files"></a>使用安全性 & 合規性 PowerShell 建立偵測到的檔案的警示原則

如果您想要使用 PowerShell 建立與上一節所述相同的警示原則，請連線 [至 Security & 合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) ，並執行下列命令：

```powershell
New-ActivityAlert -Name "Malicious Files in Libraries" -Description "Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams" -Category ThreatManagement -Operation FileMalwareDetected -NotifyUser "admin1@contoso.com","admin2@contoso.com"
```

**附注**：預設 _嚴重性_ 值是 Low。 若要指定「中」或「高」，請在命令中包含 _嚴重性_ 參數和值。

如需詳細的語法及參數資訊，請參閱 [New-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/new-activityalert)。

### <a name="how-do-you-know-these-procedures-worked"></a>如何知道這些程序是否正常運作？

- 若要確認您是否已成功為 SharePoint、OneDrive 和 Microsoft 團隊開啟 ATP，請使用下列其中一個步驟：

  - 在 [ [安全性 & 規範中心](https://protection.office.com)] 中，移至 [ **威脅管理** \> **原則** \> **ATP 安全附件**]，選取 [ **通用設定**]，然後確認 [ **開啟 SharePoint、OneDrive 和 Microsoft 小組的 ATP** ] 設定的值。

  - 在 Exchange Online PowerShell 中，執行下列命令來驗證屬性設定：

    ```powershell
    Get-AtpPolicyForO365 | Format-List EnableATPForSPOTeamsODB
    ```

    如需詳細的語法及參數資訊，請參閱 [AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365)。

- 若要確認您是否已成功封鎖人員下載惡意檔案、開啟 SharePoint 線上 PowerShell，並執行下列命令，以確認屬性值：

  ```powershell
  Get-SPOTenant | Format-List DisallowInfectedFileDownload
  ```

  如需詳細的語法及參數資訊，請參閱 [Get-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)。

- 若要確認您是否已成功設定偵測到的檔案的警示原則，請使用下列任何一項步驟：

  - 在安全性 & 規範中心內，移至 **警示** \> **警示原則** \> 選取警示原則，然後驗證設定。

  - 在 [安全性 & 規範中心] PowerShell 中， \<AlertPolicyName\> 以警示原則的名稱取代，執行下列命令，並確認屬性值：

    ```powershell
    Get-ActivityAlert -Identity "<AlertPolicyName>"
    ```

    如需詳細的語法及參數資訊，請參閱 [set-activityalert](https://docs.microsoft.com/powershell/module/exchange/get-activityalert)。

- 使用「 [威脅防護狀態」報告](view-email-security-reports.md#threat-protection-status-report) 可查看 SharePoint、OneDrive 和 Microsoft 小組中偵測到檔案的相關資訊。 具體而言，您可以使用 **View 資料：內容 \> 惡意程式碼** 視圖。
