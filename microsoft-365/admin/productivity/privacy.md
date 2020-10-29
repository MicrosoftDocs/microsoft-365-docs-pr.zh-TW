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
ROBOTS: NOINDEX, NOFOLLOW
description: 隱私權對生產力分數的保護方式。
ms.openlocfilehash: 62ff3a9f0434421cbe1115f13376e92bd9f3cac9
ms.sourcegitcommit: fa26da0be667d4be0121c52b05488dc76c5d626c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/29/2020
ms.locfileid: "48794974"
---
# <a name="privacy-controls-for-productivity-score"></a>生產力分數的隱私權控制

生產力分數可協助組織使用可協助您衡量及改善人員和技術經驗的衡量標準，來變換工作的運作方式。 它可協助您深入瞭解貴組織的運作方式，提供可協助您專注于啟用改善體驗的計量。  您也可以將此度量值連接至動作，以協助您更新技能和系統，讓每個人都能進行最佳的工作。 分數會反映您組織的效能，也可讓您安全地比較您的分數與其他組織（如您的組織）。  如需詳細資訊，請參閱 [生產力評分一覽](productivity-score.md)。

您的隱私權對我們很重要。 若要瞭解如何保護您的隱私權，請參閱 [Microsoft 的隱私權聲明](https://privacy.microsoft.com/privacystatement)。 [生產力分數] 提供有關組織中的人員如何與控制項一起運作的重要資訊，以確保資訊可運作，而不會影響您在 Microsoft 中所做的信任。

在 [人員經驗] 區域內，組織層級提供計量，且包含您的 Microsoft 365 租使用者中的所有使用者。 這個區域透過查看內容共同作業、行動性、會議、團隊合作及通訊的類別，查看人員如何使用 Microsoft 365。 若要協助您促進訓練和認知，以促進可能需要支援的產品，我們也為您提供了個別層級上的資訊。 當我們提供這種透明度時，我們也可讓您使用多個控制項層級，以協助您符合內部隱私權原則需求。
下列控制項可提供您：

- 靈活的系統管理角色，控制誰可以查看以生產力排名顯示的資訊。
- 可取消識別使用者層級計量的功能。
- 可自願享受人員體驗的功能。
- 自願享受「人員經驗」區域的功能

## <a name="flexible-admin-roles-to-control-who-can-see-the-information-in-productivity-score"></a>靈活的系統管理角色，控制誰可以查看以生產力排名顯示的資訊

若要查看整個生產力評分（包括租使用者層級的計量和每個使用者的詳細資料），您的角色應為下列其中一個系統管理員角色：

- 全域系統管理員
- Exchange 系統管理員
- SharePoint 系統管理員
- 商務用 Skype 系統管理員
- Teams 系統管理員
- 全域讀取者
- 報告讀取者

將「報告讀取者」角色指派給負責變更管理和採用的任何人員。 此角色可讓他們存取完整的經驗，包括租使用者層級計量和每個使用者層級的詳細資料。

人員經驗報告包含每一組使用者的活動詳細資料頁面。 指派名為流量摘要報告讀取器的自訂角色。 (可從29年10月 2020) 取得，只允許存取人員經驗的匯總度量。 此角色必須透過 PowerShell Cmdlet 進行指派，直到它可從11/15/2020 上的 Microsoft 系統管理中心變為可指派。

指派使用狀況摘要報告讀取器角色與 PowerShell:

- 執行下列 PowerShell:

```powershell
Connect-AzureAD
$role=Get-AzureADDirectoryRole -Filter "roleTemplateId eq '75934031-6c7e-415a-99d7-48dbd49e875e'"
Get-AzureADDirectoryRoleMember -ObjectId $role.ObjectId
$u=Get-AzureADUser -ObjectId <user upn>
Add-AzureADDirectoryRoleMember -ObjectId $role.ObjectId -RefObjectId $u.ObjectId
```

</br>

:::image type="content" source="../../media/communicationspage.jpg" alt-text="生產力報告中的通訊頁面。":::

## <a name="de-identification-of-user-level-metrics"></a>取消識別使用者層級計量

若要讓所有報表匿名收集的資料，您必須是全域系統管理員。 此巨集指令會隱藏所有報告中的辨識資訊，例如使用者、群組和網站名稱–包括生產力分數和 Microsoft 365 使用量。

1. 在系統管理中心中，移至 [ **設定**   >   **組織設定** ]，然後在 [ **服務** ] 索引標籤上選擇 [ **報告** ]。
2. 選取 [  **報告** ]，然後選擇  **在 [生產力分數] 和 [使用方式報告] 中顯示使用者、群組和網站名稱的匿名識別碼** 。 此設定會同時套用至使用狀況報告和範本應用程式。
3. 選取 [  **儲存變更** ]。

:::image type="content" source="../../media/orgsettings_anonymous.jpg" alt-text="生產力報告中的通訊頁面。":::

## <a name="capability-to-opt-out-of-people-experiences"></a>自願享受人員體驗的功能

當生產力分數一般可供使用時，您也可以選擇 [人員經驗] 中的 [人員經驗] 區域。 如果您退出宣告，則組織中的任何人都無法查看這些計量，而且您的組織會從任何涉及通訊、會議、團隊合作、內容共同作業及行動性的計算中移除。

1. 在系統管理中心中，移至 [ **設定**   >   **組織設定** ]，然後在 [ **服務** ] 索引標籤上選擇 [ **報告** ]。
2. 選取 [  **報告** ]，然後取消勾選 [  **允許 Microsoft 365 使用方式資料用於人員經驗深入** ] 核取方塊。 若要瞭解如何在 Intune configuration manager 中修改端點分析的資料共用設定，請按一下 [ **深入瞭解** ]。
3. 選取 [  **儲存變更** ]。

:::image type="content" source="../../media/orgsettingspageoptout.jpg" alt-text="生產力報告中的通訊頁面。":::