---
title: 開啟 Office 365 ATP-SharePoint、OneDrive、& 團隊
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 02/06/2019
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
ms.openlocfilehash: 8a3a3939603d30e9024f43517ce23a87cf765b84
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/29/2020
ms.locfileid: "47308332"
---
# <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>開啟適用於 SharePoint、OneDrive 與 Microsoft Teams 的 ATP

> [!IMPORTANT]
> 本文適用於擁有 [Office 365 進階威脅防護](office-365-atp.md)的企業客戶。 如果您是家用版使用者且正在尋找 Outlook 中安全連結的相關資訊，請參閱[進階 Outlook.com 安全性](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)。

[適用於 SharePoint、OneDrive 和 Microsoft Teams 的 Office 365 ATP](atp-for-spo-odb-and-teams.md) 可防止組織不小心共用惡意檔案。 偵測到惡意檔案時，該檔案會遭到封鎖，因此在組織的安全性小組採取進一步動作之前，任何人都無法開啟、複製、移動或共用該檔案。 請參閱這篇文章以開啟適用於 SharePoint、OneDrive 和 Teams 的 ATP、設定通知以通知您偵測到的檔案，並採取後續步驟。

若要定義 (或編輯) ATP 原則，您必須獲派適當的角色。 下表中有一些範例描述：

****

|角色|指派位置/條件|
|---|---|
|全域管理員|簽署購買 Microsoft 365 的人員預設為全域系統管理員。  (請參閱 [關於 Microsoft 365 系統管理員角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) 以深入瞭解。 ) |
|安全性系統管理員|Azure Active Directory 系統管理中心 ([https://aad.portal.azure.com](https://aad.portal.azure.com))|
|Exchange Online 組織管理|Exchange 系統管理中心 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) <br>或 <br>  PowerShell Cmdlet (請參閱 [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell))|
|

## <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>開啟適用於 SharePoint、OneDrive 與 Microsoft Teams 的 ATP

**開始此程式之前，請確定已為您的 Microsoft 365 環境開啟了審核記錄**。 這項工作通常是由在 Exchange Online 中獲派稽核記錄角色的人員完成。 如需詳細資訊，請參閱[開啟或關閉稽核記錄搜尋](../../compliance/turn-audit-log-search-on-or-off.md)。

1. 移至 <https://protection.office.com> 然後以您的公司或學校帳戶登入。

2. 在 [安全性 & 規範中心] 的左功能窗格中，選擇 [ **威脅管理**] 底下的 [ **原則** \> **安全附件**]。

   ![在 [安全性 & 規範中心] 中，選擇 [威脅管理 \> 原則]](../../media/08849c91-f043-4cd1-a55e-d440c86442f2.png)

3. 選取 **[開啟適用於 SharePoint、OneDrive 與 Microsoft Teams 的 ATP]**。

   ![開啟適用於 SharePoint Online、商務用 OneDrive 與 Microsoft Teams 的進階威脅防護](../../media/48cfaace-59cc-4e60-bf86-05ff6b99bdbf.png)

4. 按一下 **[儲存]**。

5. 檢閱 (並視需要編輯) 組織的 [[安全附件原則]](set-up-atp-safe-attachments-policies.md) 和 [[安全連結原則]](set-up-atp-safe-links-policies.md)。

6.  (建議) 成為全域系統管理員或 SharePoint Online 管理員，請執行 **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** Cmdlet，並將 _DisallowInfectedFileDownload_ 參數設定為 *true*。

   - 將參數設定為 *true* 可封鎖偵測到的檔案的所有動作 (刪除除外)。 使用者將無法開啟、移動、複製或共用偵測到的檔案。

   - 將參數設定為 *false* 可封鎖所有動作 (刪除和下載除外)。 使用者可以選擇接受風險並下載偵測到的檔案。

7. 允許最多30分鐘的變更，以散佈至所有 Microsoft 365 資料中心。

8. (建議) 繼續為偵測到的檔案設定警示。

若要深入瞭解搭配 Microsoft 365 使用 PowerShell，請參閱使用 [PowerShell 管理 Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-with-microsoft-365-powershell)。

若要深入了解當檔案被偵測為惡意檔案時的使用者體驗，請參閱[在 SharePoint Online、OneDrive 或 Microsoft Teams 中找到惡意檔案時該怎麼做](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)。

## <a name="set-up-alerts-for-detected-files"></a>為偵測到的檔案設定警示

若要在 SharePoint Online、商務用 OneDrive 或 Microsoft Teams 中的檔案被識別為惡意檔案時收到通知，您可以設定警示。

1. 在 [ [安全性 & 規範中心](https://protection.office.com)] 中，選擇 [ **警示**] [ \> **管理提醒**]。

2. 選擇 **[新警示原則]**。

3. 指定警示的名稱。 例如，您可以輸入「程式庫中的惡意檔案」。

4. 輸入警示描述。 例如，當您在 SharePoint Online、OneDrive 或 Microsoft Teams 中偵測到惡意檔案時，您可以輸入「通知系統管理員」。

5. 在 **[下列情況時傳送此通知...]** 區段中，執行下列動作：

   a. 在 **[活動]** 清單中，選擇 **[已偵測到檔案中的惡意程式碼]**。

   b. 將 **[使用者]** 欄位保留空白。

6. 在 **[傳送此通知到...]** 區段中，選取一或多位全域系統管理員、安全性系統管理員，或在偵測到惡意檔案時應收到通知的安全性讀者。

7. 按一下 **[儲存]**。

若要深入瞭解提醒，請參閱 [在安全性 & 規範中心建立活動警示](../../compliance/create-activity-alerts.md)。

## <a name="next-steps"></a>後續步驟

1. [檢視在 SharePoint、OneDrive 或 Microsoft Teams 中偵測到的惡意檔案資訊](malicious-files-detected-in-spo-odb-or-teams.md)

2. [在 Microsoft 365 中以系統管理員身分管理被隔離的郵件和檔案](manage-quarantined-messages-and-files.md)
