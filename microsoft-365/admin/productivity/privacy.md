---
title: Microsoft 生產力分數-隱私權
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
monikerRange: o365-worldwide
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
description: 隱私權對生產力分數的保護方式。
ms.openlocfilehash: b522c40cba746f3a4ede2404cf671607d62a3282
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406557"
---
# <a name="privacy-controls-for-productivity-score"></a>生產力分數的隱私權控制

生產力分數透過使用 Microsoft 365 和支援 it 的技術體驗，提供您組織的數位轉換旅程的洞察力。  組織的分數反映人員和技術經驗度量，可與類似組織的基準進行比較。 如需詳細資訊，請查看 [生產力排名一覽](productivity-score.md)。

您的隱私權對 Microsoft 很重要。 若要瞭解如何保護您的隱私權，請參閱 [Microsoft 的隱私權聲明](https://privacy.microsoft.com/privacystatement)。 生產力分數可讓您成為貴組織的 IT 系統管理員、存取隱私權設定，以協助確保您所能行動的任何生產力分數資訊，但不會危及您的組織對 Microsoft 的信任。

在 [人員經驗] 區域內，只可在組織層級取得度量。 這個區域透過查看內容共同作業、行動性、會議、團隊合作及通訊的類別，查看人員如何使用 Microsoft 365。 我們可讓您使用數種控制層級，協助您符合內部隱私權原則需求。
這些控制項提供下列專案：

- 靈活的系統管理角色，控制誰可以查看以生產力排名顯示的資訊。
- 自願享受「人員經驗」區域的功能。

## <a name="flexible-admin-roles-to-control-who-can-see-the-information-in-productivity-score"></a>靈活的系統管理角色，控制誰可以查看以生產力排名顯示的資訊

若要查看整個生產力分數，您必須是下列其中一個系統管理員角色：

- 全域系統管理員
- Exchange 系統管理員
- SharePoint 系統管理員
- 商務用 Skype 系統管理員
- Teams 系統管理員
- 全域讀取者
- 報告讀取者
- 使用狀況摘要報告閱讀程式

將「報告讀取者」或「使用狀況摘要報告讀取者」角色指派給負責變更管理和採用的任何人員，但不一定是 IT 管理員。 此角色可讓他們存取 Microsoft 365 系統管理中心的完整生產力評分體驗。

使用摘要報告讀取器角色必須透過 PowerShell Cmdlet 進行指派，直到它可從 Microsoft 365 admin center （2020之後）變為可指派。

指派使用狀況摘要報告讀取器角色與 PowerShell:

- 執行下列 PowerShell:

```powershell
Connect-AzureAD
Enable-AzureADDirectoryRole -RoleTemplateId '75934031-6c7e-415a-99d7-48dbd49e875e'
$role=Get-AzureADDirectoryRole -Filter "roleTemplateId eq '75934031-6c7e-415a-99d7-48dbd49e875e'"
Get-AzureADDirectoryRoleMember -ObjectId $role.ObjectId
$u=Get-AzureADUser -ObjectId <user upn>
Add-AzureADDirectoryRoleMember -ObjectId $role.ObjectId -RefObjectId $u.ObjectId
```

</br>


## <a name="capability-to-opt-out-of-people-experiences"></a>自願享受人員體驗的功能

您也可以選擇 [人員經驗] 中的 [人員經驗] 區域。 如果您退出宣告，您組織中的任何人都無法查看這些計量，而且您的組織將會從任何涉及通訊、會議、團隊合作、內容共同作業及行動性的計算中移除。 您必須是全域系統管理員，才可選擇您的組織體驗報告。

若要取消選擇：

1. 在系統管理中心中，移至 [**設定**] [   >   **組織設定**]  >  ****。
2. 取消選取 [  **允許 Microsoft 365 使用方式資料以供人員經驗深入使用**] 方塊。 若要瞭解如何在 Intune configuration manager 中修改端點分析的資料共用設定，請選取 [ **深入瞭解**]。
3. 選取 [  **儲存**]。

:::image type="content" source="../../media/orgsettingspageoptout.png" alt-text="[組織設定] 頁面，您可以在其中選擇從人員經驗。":::
