---
title: Microsoft 365 企業版的資料分類測試環境
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/16/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: 使用此測試實驗室指南建立及使用 Office 365 標籤在 Microsoft 365 企業版測試環境中的文件。
ms.openlocfilehash: 33ac1fa8e26c0037882e6c240cc04ec19e6a6a7b
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/16/2019
ms.locfileid: "26866733"
---
# <a name="data-classification-for-your-microsoft-365-enterprise-test-environment"></a>Microsoft 365 企業版的資料分類測試環境

本文中的指示，您設定 Microsoft 365 企業版測試環境中使用 Office 365 保留標籤的資料分類。

![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> 按一下[這裡](https://aka.ms/m365etlgstack)(英文)，可查看 Microsoft 365 企業版測試實驗室指南堆疊中所有文章的視覺對應。
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>階段 1： 建立您的 Microsoft 365 Enterprise 的測試環境

如果只想要設定 Office 365 標籤具有的基本硬體需求的輕量型方式，請遵循[輕量型的基本組態](lightweight-base-configuration-microsoft-365-enterprise.md)中的指示。
  
如果您要設定模擬企業中的 Office 365 標籤，請遵循[通過驗證](pass-through-auth-m365-ent-test-environment.md)中的指示。
  
> [!NOTE]
> 測試 Office 365 標籤不需要模擬的企業測試環境中，其中包含連線至網際網路模擬內部網路和 Windows Server AD 樹系目錄同步處理。它會提供這裡是做為選項可以測試自動化授權和群組成員資格和代表的典型組織的環境中實驗。 

## <a name="phase-2-create-office-365-labels"></a>階段 2：建立 Office 365 標籤

在此階段中，您可以建立不同層級的 SharePoint Online 的文件資料夾的保留的標籤。
  
1. 必要時，使用專用的網際網路瀏覽器並登入 Office 入口網站以全域管理員帳戶。為了協助，請參閱 ＜[登入 Office 365 的位置](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4)。
    
2. 從 [Microsoft Office 的首頁]**** 索引標籤中，按一下 [管理]**** 磚。
    
3. 從瀏覽器的新 [Office 系統管理中心]**** 索引標籤中，按一下 [系統管理中心] > [安全性 &amp; 合規性]****。
    
4. 從新**首頁-安全性&amp;規範**] 索引標籤的瀏覽器中，按一下 [**分類 > 標籤**。從**首頁 > 標籤**] 窗格中，按一下 [**保留**] 索引標籤。
    
5. 按一下 [**建立的標籤**。
    
6. 在 [命名您的標籤]**** 窗格中，輸入 **內部公用**，然後按一下 [下一步]****。
    
7. 在 [標籤設定]**** 窗格中，按一下 [下一步]****。
    
8. 在 [檢閱您的設定]**** 窗格中，按一下 [建立此標籤]****，然後按一下 [關閉]****。
    
9. 重複步驟 5-8，逐一設定下列其他標籤：
    
  - Private
    
  - 敏感性
    
  - 高度機密
    
10. 從 [首頁] > [標籤]**** 窗格中，按一下 [Publish labels]\(發佈標籤)****。
    
11. 在 [選擇要發佈的標籤]**** 窗格中，按一下 [選擇要發佈的標籤]****。
    
12. 在 [Choose labels]\(選擇標籤)**** 窗格中，按一下 [新增]**** 並選取所有四個標籤。
    
13. 按一下 [完成]****。
    
14. 在 [選擇要發佈的標籤]**** 窗格上，按一下 [下一步]****。
    
15. 在 [選擇位置]**** 窗格中，按一下 [下一步]****。
    
16. 在 [命名您的原則]**** 窗格上，於 [名稱]**** 中輸入 **範例組織**，然後按一下 [下一步]****。
    
17. 在 [檢閱您的設定]**** 窗格中，按一下 [發佈標籤]****，然後按一下 [關閉]****。

請注意可能需要幾分鐘時間要發佈之標籤。

## <a name="phase-3-apply-office-365-retention-labels-to-documents"></a>階段 3： 將 Office 365 保留標籤套用至文件

在此階段中，您會發現 label 的預設行為的 SharePoint Online 網站的 [文件] 資料夾中的檔案與手動變更文件的標籤。

首先，建立機密層級 SharePoint Online 小組網站：
  
1. 本機電腦上使用瀏覽器中，Office 入口網站使用全域管理員帳戶登入。為了協助，請參閱 ＜[登入 Office 365 的位置](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4)。
    
2. 在磚清單中，按一下 [SharePoint]****。
    
3. 在 [新增**SharePoint** ] 索引標籤在瀏覽器中按一下 [**建立網站**。
    
4. 在 [建立網站]**** 頁面上，按一下 [小組網站]****。
    
5. 在**小組網站名稱**] 中輸入**SensitiveFiles**。
    
6. 在**小組網站描述**] 中，輸入**SharePoint 網站的機密檔案**。
    
7.  在 [隱私權設定]**** 中，選取 [私人 - 只有成員可以存取此網站]****，然後按一下 [下一步]****。
    
8. 在 [您想要新增誰?]**** 窗格上，按一下 [完成]****。
    
接下來，設定機密標籤 SensitiveFiles 小組網站的 [文件] 資料夾。
  
1. 在瀏覽器中的 [ **SensitiveFiles** ] 索引標籤中，按一下 [**文件**。
    
2. 按一下設定圖示，然後按一下 [文件庫設定]****。
    
3. 在 [權限與管理]**** 下，按一下 [Apply label to items in this library]\(將標籤套用至此文件庫中的項目)****。
    
4. 在**套用設定的標籤**、 下拉式方塊中，選取 [**機密**] 和 [**儲存**。

接下來，SensitiveFiles 網站中建立新的文件並變更其標籤。
    
1. 在 [文件] 資料夾中，按一下 [**新增 > Word 文件**。
    
2. 在空白的文件中輸入一些文字。等待儲存的文字。
    
3. 在功能表列中，按一下 [**共享文件**]。
    
4. 按一下 [Word 圖示旁**Document.docx**檔案名稱。
    
5. 在右窗格的 [**屬性**] 區段的 [**套用] 保留標籤**、 中記下文件已經有自動套用**敏感**標籤。
    
6. 按一下 [**編輯所有**。
    
7. 在**Document.docx**窗格**套用標籤**、 選取的**高度機密**的標籤和 [**儲存**。

請參閱[Configure 分類環境的](infoprotect-configure-classification.md)步驟中的資訊及連結至 Office 365 保留標籤在生產環境中的**資訊保護**階段。

## <a name="next-step"></a>下一步

探索測試環境的其他[資訊保護](m365-enterprise-test-lab-guides.md#information-protection)特色和功能。

## <a name="see-also"></a>另請參閱

[Microsoft 365 企業版測試實驗室指南](m365-enterprise-test-lab-guides.md)

[部署 Microsoft 365 企業版](deploy-microsoft-365-enterprise.md)

[Microsoft 365 企業版文件](https://docs.microsoft.com/microsoft-365-enterprise/)

 