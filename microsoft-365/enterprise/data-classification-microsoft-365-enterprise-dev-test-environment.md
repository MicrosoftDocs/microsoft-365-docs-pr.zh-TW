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
ms.openlocfilehash: 171fcb74b09a1f2e5c80f23e010640dce55660bc
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686403"
---
# <a name="data-classification-for-your-microsoft-365-for-enterprise-test-environment"></a>Microsoft 365 企業版測試環境的資料分類

*此測試實驗室指南可用於 enterprise 和 Office 365 企業測試環境的 Microsoft 365。*

透過本文中的指示，您可以使用 Microsoft 365 for enterprise test 環境中的保留標籤來設定資料分類。

![Microsoft Cloud 的測試實驗室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> 按一下[這裡](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)，可查看企業用 Microsoft 365 測試實驗室指南堆疊中所有文章的視覺對應。
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>階段1：組建您的 Microsoft 365 企業版測試環境

如果您只想以具有最低需求的輕量方式設定保留標籤，請遵循 [輕量基本](lightweight-base-configuration-microsoft-365-enterprise.md)設定中的指示。
  
如果您想要在模擬的企業中設定保留標籤，請依照 [傳遞驗證](pass-through-auth-m365-ent-test-environment.md)中的指示進行。
  
> [!NOTE]
> 測試保留標籤並不需要模擬的企業測試環境，其中包括連線至網際網路的模擬內部網路與目錄同步處理，以及 Active Directory 網域服務 (AD DS) 樹系的目錄同步處理。 這裡是以選項形式提供，可讓您測試自動授權和群組成員資格，並在代表一般組織的環境中實驗。 

## <a name="phase-2-create-retention-labels"></a>階段2：建立保留標籤

在此階段中，您會為 SharePoint 線上檔資料夾，建立不同保留層級的保留標籤。

1. 使用您的全域系統管理員帳戶登入 [Microsoft 365 的安全性中心](https://security.microsoft.com/homepage) 。
    
2. 從瀏覽器的 [ **主版-Microsoft 365 安全性** ] 索引標籤中，按一下 [ **分類 > 保留標籤**]。
    
3. 按一下 [建立標籤]****。
    
4. 在 [**命名您的標籤**] 窗格中，**輸入您標籤**的 [**內部公用**]，然後按 **[下一步]**。

5. 在 [ **檔計畫描述項** ] 窗格中，按 **[下一步]**。
    
6. 在 [ **標籤設定** ] 窗格中，視需要將 **保留** 設定為 [ **開啟**]，然後按 **[下一步]**。
    
7. 在 [ **複查您的設定** ] 窗格中，按一下 [ **建立標籤**]。
    
8. 針對以下名稱的標籤，重複步驟 3-7：
    
  - 私人
    
  - 敏感性
    
  - 高度機密
  
9. 在 [ **保留標籤** ] 窗格中，按一下 [ **發佈標籤**]。
    
10. 在 [ **選擇要發佈的標籤** ] 窗格中，按一下 **[選擇要發佈的標籤**]。
    
11. 在 [ **選擇標籤** ] 窗格中，按一下 [ **新增** ]，然後選取所有四個標籤。
    
12. 按一下 [新增]****，然後按一下 [完成]****。
    
13. 在 [選擇要發佈的標籤]**** 窗格上，按一下 [下一步]****。
    
14. 在 [選擇位置]**** 窗格中，按一下 [下一步]****。
    
15. 在 [命名您的原則]**** 窗格上，於 [名稱]**** 中輸入 **範例組織**，然後按一下 [下一步]****。
    
16. 在 [ **複查您的設定** ] 窗格上，按一下 [ **發佈標籤**]。
 
請注意，保留標籤可能需要幾分鐘的時間才能發行。

## <a name="phase-3-apply-retention-labels-to-documents"></a>階段3：將保留標籤套用至檔

在此階段中，您會探索 SharePoint Online 網站之 Documents 資料夾中檔案的預設保留標籤行為，並手動變更檔的保留標籤。

首先，建立機密層級 SharePoint Online 小組網站：
  
1. 使用您的瀏覽器的私人實例，使用您的全域系統管理員帳戶登入 [Microsoft 365 系統管理中心](https://admin.microsoft.com) 。
    
2. 在磚清單中，按一下 [SharePoint]****。
    
3. 在瀏覽器的 [新增 **SharePoint** ] 索引標籤上，按一下 [ **建立網站**]。
    
4. 在 [建立網站]**** 頁面上，按一下 [小組網站]****。
    
5. 在 [ **小組網站名稱**] 中，輸入 **SensitiveFiles**。
    
6. 在 [ **小組網站描述**] 中，輸入 **機密檔的 SharePoint 網站**。
    
7.  在 [隱私權設定]**** 中，選取 [私人 - 只有成員可以存取此網站]****，然後按一下 [下一步]****。
    
8. 在 [ **您想要新增誰？** ] 窗格中，按一下 **[完成]**。
    
接下來，針對敏感保留標籤設定 SensitiveFiles 小組網站的 Documents 資料夾。
  
1. 在瀏覽器的 [ **SensitiveFiles** ] 索引標籤中，按一下 [ **檔**]。
    
2. 按一下設定圖示，然後按一下 [文件庫設定]****。
    
3. 在 [ **許可權與管理**] 底下，按一下 [ **對此清單或文件庫中的專案套用標籤**]。 如果未顯示此選項，則您的保留標籤尚未發行。 請稍後再嘗試此步驟。
    
4. 在 [設定]-[套用 **標籤**] 的下拉式方塊中，選取 [ **敏感** ]，然後按一下 [ **儲存**]。

接下來，在 SensitiveFiles 網站中建立新的檔，並變更其保留標籤。
    
1. 在 [檔] 資料夾中，按一下 [ **新增 > Word 檔**]。
    
2. 在空白檔中輸入一些文字。 等候文字的儲存。
    
3. 在功能表列中，按一下 [ **共用檔**]。
    
4. 按一下 **Document.docx** 檔案名旁邊的垂直省略號，然後按一下 [ **詳細資料**]。
    
5. 在右窗格的 [ **屬性** ] 區段中，于 [套用 **保留標籤**] 底下，請注意檔已自動套用 **敏感** 保留標籤。
    
6. 按一下 [ **全部編輯**]。
    
7. 在 [ **Document.docx** ] 窗格中的 [套用 **保留標籤**] 底下，選取 [ **高度機密** ] 標籤，然後按一下 [ **儲存**]。

## <a name="next-step"></a>下一步

在您的測試環境中探索其他 [資訊保護](m365-enterprise-test-lab-guides.md#information-protection) 功能和功能。

## <a name="see-also"></a>請參閱

[Microsoft 365 企業版測試實驗室指南](m365-enterprise-test-lab-guides.md)

[Microsoft 365 企業版概觀](microsoft-365-overview.md)

[適用于企業的 Microsoft 365 檔](https://docs.microsoft.com/microsoft-365-enterprise/)

 
