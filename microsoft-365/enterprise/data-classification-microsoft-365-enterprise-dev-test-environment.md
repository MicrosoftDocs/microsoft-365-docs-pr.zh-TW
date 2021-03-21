---
title: Microsoft 365 企業版測試環境的資料分類
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: 使用此測試實驗室指南，可在 Microsoft 365 for enterprise 測試環境中的檔上建立及使用保留標籤。
ms.openlocfilehash: 613aa3713b4d72eed1bc0b2d88f70a817d0e7cff
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919185"
---
# <a name="data-classification-for-your-microsoft-365-for-enterprise-test-environment"></a>Microsoft 365 企業版測試環境的資料分類

*此測試實驗室指南可用於 enterprise 和 Office 365 企業測試環境的 Microsoft 365。*

本文說明如何使用 Microsoft 365 for enterprise 測試環境中的保留標籤來設定資料分類。

分類測試環境中的資料包括三個階段：
- [階段1：組建您的 Microsoft 365 企業版測試環境](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [階段2：建立保留標籤](#phase-2-create-retention-labels)
- [階段3：將保留標籤套用至檔](#phase-3-apply-retention-labels-to-documents)

![Microsoft Cloud 的測試實驗室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> 如需 Microsoft 365 for enterprise 測試實驗室指南堆疊中所有文章的視覺對應，請移至 [microsoft 365 for Enterprise Test Lab Guide 堆疊](../downloads/Microsoft365EnterpriseTLGStack.pdf)。
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>階段1：組建您的 Microsoft 365 企業版測試環境

如果您只想以具有最低需求的輕量方式設定保留標籤，請遵循 [輕量基本](lightweight-base-configuration-microsoft-365-enterprise.md)設定中的指示。
  
如果您想要在模擬的企業中設定保留標籤，請依照 [傳遞驗證](pass-through-auth-m365-ent-test-environment.md)中的指示進行。
  
> [!NOTE]
> 測試保留標籤並不需要模擬的企業測試環境，其中包括連線到網際網路的模擬內部網路與目錄同步處理，以及 (AD DS) 樹系中的 Active Directory 網域服務的目錄同步處理。 它會以選項形式提供，以便您可以測試自動授權和群組成員資格，並在代表一般組織的環境中進行試驗。

## <a name="phase-2-create-retention-labels"></a>階段2：建立保留標籤

在這個階段中，針對 SharePoint 線上檔資料夾，建立不同保留層級的保留標籤：

1. 使用您的全域系統管理員帳戶登入 [Microsoft 365 的安全性中心](https://security.microsoft.com/homepage) 。
1. 從瀏覽器的 [**主版-Microsoft 365 安全性**] 索引標籤中，選取 [**分類**  >  **保留標籤**]。
1. 選取 [建立標籤]。
1. 在 [**命名您的標籤**] 窗格中，**輸入您標籤** 的 [**內部公用**]，然後選取 **[下一步]**。
1. 在 [ **檔計畫描述項** ] 窗格中，選取 **[下一步]**。
1. 在 [ **標籤設定** ] 窗格中，視需要將 **保留** 設定為 [ **開啟**]，然後選取 **[下一步]**。
1. 在 [ **複查您的設定** ] 窗格中，選取 [ **建立標籤**]。
1. 針對以下名稱的標籤，重複步驟 3-7：
  - 私人
  - 敏感性
  - 高度機密
1. 在 [ **保留標籤** ] 窗格中，選取 [ **發行標籤**]。
1. 在 [ **選擇要發佈的標籤** ] 窗格中，選取 **[選擇要發佈的標籤**]。
1. 在 [ **選擇標籤** ] 窗格中，選取 [ **新增** ]，然後選取所有四個標籤。
1. 選取 [ **新增**]，然後選取 [ **完成**]。
1. 在 [ **選擇要發佈的標籤** ] 窗格中，選取 **[下一步]**。
1. 在 [ **選擇位置** ] 窗格中，選取 **[下一步**]。
1. 在 [**命名您的原則**] 窗格的 **[名稱] 中輸入****範例組織**，然後選取 **[下一步]**。
1. 在 [ **複查您的設定** ] 窗格中，選取 [ **發行標籤**]。
 
可能需要幾分鐘的時間才能發佈保留標籤。

## <a name="phase-3-apply-retention-labels-to-documents"></a>階段3：將保留標籤套用至檔

在此階段中，您會探索 SharePoint Online 網站之 Documents 資料夾中檔案的預設保留標籤行為，並手動變更檔的保留標籤。

首先，建立機密層級 SharePoint Online 小組網站：
  
1. 使用您的瀏覽器的私人實例，使用您的全域系統管理員帳戶登入 [Microsoft 365 系統管理中心](https://admin.microsoft.com) 。
1. 在磚清單中，選取 [ **SharePoint**]。
1. 在瀏覽器的 [新增 **SharePoint** ] 索引標籤上，選取 [ **建立網站**]。
1. 在 [ **建立網站** ] 頁面上，選取 [ **小組網站**]。
1. 在 [ **小組網站名稱** ] 方塊中，輸入 **SensitiveFiles**。
1. 在 [ **小組網站描述** ] 方塊中，輸入 **機密檔的 SharePoint 網站**。
1. 在 [ **隱私權設定**] 中，選取 [ **僅私人成員可以存取此網站**]，然後選取 **[下一步]**。
1. 在 [ **您想要新增誰？** ] 窗格中，選取 **[完成]**。
    
接下來，針對敏感保留標籤設定 SensitiveFiles 小組網站的 Documents 資料夾。
  
1. 在瀏覽器的 [ **SensitiveFiles** ] 索引標籤中，選取 [ **檔**]。
1. 選取 [ **設定** ] 圖示，然後選取 [文檔 **庫設定**]。
1. 在 [ **許可權與管理**] 底下，選取 [ **將標籤套用至此清單或文件庫中的專案**]。 如果未顯示此選項，則您的保留標籤尚未發佈。 請稍後再嘗試此步驟。
1. 在 [設定]-[套用 **標籤**] 的下拉式方塊中，選取 [ **敏感** ]，然後選取 [ **儲存**]。

接下來，在 SensitiveFiles 網站中建立新的檔，並變更其保留標籤。
    
1. 在 [檔] 資料夾中，選取 [**新增**  >  **Word 檔**]。
1. 在空白檔中輸入一些文字。 等候文字的儲存。
1. 在功能表列上，選取 [ **共用檔**]。
1. 在 **Document.docx** 檔案名旁，選取垂直省略號，然後選取 [ **詳細資料**]。
1. 在右窗格的 [ **屬性** ] 區段中，于 [套用 **保留標籤**] 底下，請注意檔已自動套用 **敏感** 保留標籤。
1. 按一下 [ **全部編輯**]。
1. 在 [ **Document.docx** ] 窗格中的 [套用 **保留標籤**] 底下，選取 [ **高度機密** ] 標籤，然後選取 [ **儲存**]。

## <a name="next-step"></a>後續步驟

在您的測試環境中探索其他 [資訊保護](m365-enterprise-test-lab-guides.md#information-protection) 功能和功能。

## <a name="see-also"></a>另請參閱

[Microsoft 365 企業版測試實驗室指南](m365-enterprise-test-lab-guides.md)

[Microsoft 365 企業版概觀](microsoft-365-overview.md)

[Microsoft 365 企業版文件](/microsoft-365-enterprise/)