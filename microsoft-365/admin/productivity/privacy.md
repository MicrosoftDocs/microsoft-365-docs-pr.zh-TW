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
ms.openlocfilehash: 799d532ca1f0abd5fa6234052d4875a79d629601
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/26/2020
ms.locfileid: "48287244"
---
# <a name="privacy-controls-for-productivity-score"></a>生產力分數的隱私權控制

生產力分數可協助組織轉換工作如何使用 Microsoft 365 的相關資訊，以及支援這些功能的技術體驗。 分數會反映您的組織&#39;員工和技術經驗的效能，並與您的組織（如您的組織）比較您的分數。 如需詳細資訊，請參閱 [生產力評分一覽表](productivity-score.md) 主題。

您的隱私權對我們來說很重要，您可以在 [這裡](https://privacy.microsoft.com/privacystatement)查看 Microsoft 的隱私權聲明。 在生產力分數中，有重要的資訊可提供給組織中的人員運作方式。 這樣一來，我們也會提供您的控制，以確保資訊以有意義的方式操作，但不會危及我們所用的信任。

我們提供下列控制項，以允許更安全的資料處理：

- 靈活的系統管理角色，控制誰可以查看以生產力排名顯示的資訊。
- 使用者層級計量的匿名。
- 可選擇無員工經驗的功能。

## <a name="flexible-admin-roles-to-control-who-can-see-the-information-in-productivity-score"></a>靈活的系統管理角色，控制誰可以查看以生產力排名顯示的資訊

若要以系統管理員角色（包括租使用者層級真知灼見和每個使用者層級的詳細資料）來查看整個生產力評分的經驗，您的角色應為下列其中一項：

- 全域系統管理員
- Exchange 系統管理員
- SharePoint 系統管理員
- 商務用 Skype 系統管理員
- Teams 系統管理員
- 全域讀取者
- 報告讀取者

若要邀請負責變更管理和採用但不是 IT 系統管理員的人員進入體驗，並讓他們能夠存取整個經驗（包括租使用者層級真知灼見和每個使用者層級的詳細資料），您可以將其提供給他們的報表讀者角色。

在員工經驗內，我們會針對每個類別詳細資料頁面，為格線格式提供每一使用者層級的活動詳細資料。 因為這一層級的詳細資料不適用於生產力分數的所有潛在訪客，所以我們已在 Azure AD 中建立自訂角色–使用摘要報告讀取器角色–可讓您的組織內的一組廣泛的訪問者存取，只會收集量值，而且不會在經驗中的每一層級的詳細資料。

:::image type="content" source="../../media/communicationspage.jpg" alt-text="生產力報告中的通訊頁面。":::

## <a name="anonymization-of-user-level-metrics"></a>使用者層級計量的匿名

若要讓所有報表匿名收集的資料，您必須是全域系統管理員。 這會隱藏所有報告中的辨識資訊，例如使用者、群組和網站名稱，包括生產力分數和 Microsoft 365 使用量。

1. 在系統管理中心中，移至 [**設定**   >   **組織設定**]，然後在 [**服務**] 索引標籤上選擇 [**報告**]。
2. 選取 [  **報告** ]，然後選擇  **在 [生產力分數] 和 [使用方式報告] 中顯示使用者、群組和網站名稱的匿名識別碼**。 此設定會同時套用至使用狀況報告和範本應用程式。
3. 選取 [  **儲存變更**]。

:::image type="content" source="../../media/orgsettings_anonymous.jpg" alt-text="將使用者資訊設定為匿名的報表。":::

## <a name="capability-to-opt-out-of-employee-experience"></a>選擇不需要員工經驗的功能

我們也會提供一種功能，以在正式供貨時選擇不會以生產力評分為員工經驗區。 開啟此設定會使組織中的任何人都無法查看這些計量，並從涉及通訊、會議、團隊合作的內容共同作業及行動性的任何計算中移除您的組織。

1. 在系統管理中心中，移至 [**設定**   >   **組織設定**]，然後在 [**服務**] 索引標籤上選擇 [**報告**]。
2. 選取 [  **報告** ]，然後取消勾選 [  **分享您的組織&#39;的資料與生產力分數員工經驗深入**瞭解。 若要瞭解如何在 Intune configuration manager 中修改端點分析的資料共用設定，請按一下 [ **深入瞭解**]。
3. 選取 [  **儲存變更**]。

:::image type="content" source="../../media/orgsettingspageoptout.jpg" alt-text="[組織設定] 頁面，您可以在其中選擇從員工經驗。":::