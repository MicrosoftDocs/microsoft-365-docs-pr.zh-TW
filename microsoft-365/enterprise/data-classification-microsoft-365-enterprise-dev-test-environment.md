---
title: 資料分類您的 Microsoft 365 企業版測試環境
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
description: 使用此測試實驗室指南來建立及使用 Microsoft 365 企業版測試環境中的文件上的 Office 365 保留標籤。
ms.openlocfilehash: dba98ca7a38291c9ce22e9a275585975e6b840ee
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/19/2019
ms.locfileid: "40802048"
---
# <a name="data-classification-for-your-microsoft-365-enterprise-test-environment"></a>資料分類您的 Microsoft 365 企業版測試環境

*這個測試實驗室指南可用於 Microsoft 365 企業版和 Office 365 企業版兩種測試環境。*

透過本文中的指示，您可以設定 Microsoft 365 企業版測試環境中使用 Office 365 保留標籤的資料分類。

![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> 按一下[這裡](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) (英文)，可查看 Microsoft 365 企業版測試實驗室指南堆疊中所有文章的視覺對應。
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>階段 1：建置您的 Microsoft 365 企業版測試環境

如果您只想以具有最小需求的輕量型方式設定 Office 365 保留標籤，請遵循[輕量型基本組態](lightweight-base-configuration-microsoft-365-enterprise.md)中的指示。
  
如果您想要在模擬的企業中設定 Office 365 保留標籤，請遵循[通過驗證](pass-through-auth-m365-ent-test-environment.md)的指示進行。
  
> [!NOTE]
> 測試 Office 365 保留標籤不需要模擬的企業測試環境，其中包含連線至網際網路的模擬內部網路和目錄同步處理的 Active Directory 網域服務 (AD DS) 樹系。 它提供了此選項，讓您可以測試自動授權和群組成員資格與代表典型組織的環境中實驗。 

## <a name="phase-2-create-office-365-retention-labels"></a>階段 2： 建立 Office 365 保留標籤

在這個階段，您可以建立不同的層級的保留為 SharePoint Online 的文件資料夾的保留標籤。

1. [Microsoft 365 安全中心](https://security.microsoft.com/homepage)以全域系統管理員帳戶登入。
    
2. 從瀏覽器的 [**首頁-Microsoft 365 安全性**] 索引標籤中，按一下 [**分類 > 保留標籤**。
    
3. 按一下 **[建立標籤]**。
    
4. 在**名稱標籤**] 窗格中，輸入**內部公用**] 中，**您的標籤名稱**，然後按 [**下一步**。

5. 在 [**檔案計劃描述元**] 窗格中，按一下 [**下一步**]。
    
6. 在 [**標籤設定**] 窗格中，如有需要設定**保留**為**上**，，然後按一下 [**下一步**。
    
7. 在 [**檢閱您的設定**] 窗格中，按一下 [**建立標籤**。
    
8. 針對以下名稱的標籤，重複步驟 3-7：
    
  - 私人
    
  - 敏感性
    
  - 高度機密
  
9. 在 [**保留標籤**] 窗格中，按一下 [**發佈標籤**]。
    
10. 在 [**選擇要發佈標籤**] 窗格中，按一下 [**選擇来發佈標籤]**。
    
11. 在 [**選擇標籤**] 窗格中，按一下 [**新增**] 並選取所有四個標籤。
    
12. 按一下 [**新增**]，然後按一下 [**完成**。
    
13. 在 [選擇要發佈的標籤]**** 窗格上，按一下 [下一步]****。
    
14. 在 [選擇位置]**** 窗格中，按一下 [下一步]****。
    
15. 在 [命名您的原則]**** 窗格上，於 [名稱]**** 中輸入 **範例組織**，然後按一下 [下一步]****。
    
16. 在 [**檢閱您的設定**] 窗格中，按一下 [**發佈標籤**]。
 
請注意，可能需要幾分鐘的時間要發佈保留標籤。

## <a name="phase-3-apply-office-365-retention-labels-to-documents"></a>階段 3： 將 Office 365 保留標籤套用至文件

在這個階段，您探索的 SharePoint Online 網站的文件資料夾中檔案的預設保留標籤行為，並以手動方式變更文件的保留標籤。

首先，建立敏感性層級 SharePoint Online 小組網站：
  
1. 使用您的瀏覽器的私用執行個體，登入[Office 365 入口網站](https://portal.office.com)使用您的全域系統管理員帳戶。
    
2. 在磚清單中，按一下 [SharePoint]****。
    
3. 新**SharePoint**索引標籤上瀏覽器中，按一下 [**建立網站**]。
    
4. 在 [建立網站]**** 頁面上，按一下 [小組網站]****。
    
5. 在 [**小組網站名稱**] 中，輸入**SensitiveFiles**。
    
6. 在 [**小組網站描述**] 中，輸入**SharePoint 網站的敏感性檔案**。
    
7.  在 [隱私權設定]**** 中，選取 [私人 - 只有成員可以存取此網站]****，然後按一下 [下一步]****。
    
8. 在 [**您要新增誰？** ] 窗格中，按一下 [**完成]**。
    
接下來，設定敏感的保留標籤的 SensitiveFiles 小組網站的文件資料夾。
  
1. 在瀏覽器的 [ **SensitiveFiles** ] 索引標籤中，按一下 [**文件**]。
    
2. 按一下設定圖示，然後按一下 [文件庫設定]****。
    
3. 按一下 [**權限與管理**] 下的 [**將標籤套用到此清單或文件庫中的項目**。 如果未出現此選項，保留標籤尚未發佈。 嘗試在稍後執行這個步驟。
    
4. 在 [**設定-套用標籤**] 中，在下拉式方塊中，選取 [**敏感性**，然後按一下 [**儲存**。

接下來，在 SensitiveFiles 網站中建立新的文件，並變更其保留標籤。
    
1. 在 [文件] 資料夾中，按一下 [**新增 > Word 文件**。
    
2. 在空白的文件中輸入一些文字。 等待要儲存的文字。
    
3. 在功能表列中，按一下 [**共享文件**。
    
4. 按一下**Document.docx**檔案名稱] 旁邊的垂直省略符號，然後按一下 [**詳細資料**。
    
5. 在右窗格中，在 [**屬性**] 區段的 [**套用保留標籤**] 中，記下的文件已有**機密**的保留標籤自動套用。
    
6. 按一下 [**編輯所有**。
    
7. 在 [ **Document.docx** ] 窗格中，在**套用保留標籤**] 底下選取 [**高度機密**] 標籤，然後按一下 [**儲存**。

在**資訊保護**階段中的資訊，以及如何部署 Office 365 保留標籤在生產環境中的連結，請參閱[設定環境的分類](infoprotect-configure-classification.md)的步驟。

## <a name="next-step"></a>下一步

瀏覽額外的[資訊保護](m365-enterprise-test-lab-guides.md#information-protection)功能和測試環境中的功能。

## <a name="see-also"></a>另請參閱

[Microsoft 365 企業版測試實驗室指南](m365-enterprise-test-lab-guides.md)

[部署 Microsoft 365 企業版](deploy-microsoft-365-enterprise.md)

[Microsoft 365 企業版文件](https://docs.microsoft.com/microsoft-365-enterprise/)

 