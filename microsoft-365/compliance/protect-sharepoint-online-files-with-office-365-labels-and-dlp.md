---
title: 使用保留標籤與 DLP 來保護 SharePoint Online 檔案
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/27/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- SPO_Content
ms.custom:
- Ent_Solutions
ms.assetid: c9f837af-8d71-4df1-a285-dedb1c5618b3
description: 摘要：使用各種資訊保護層級，對 SharePoint Online 小組網站套用保留標籤和資料外洩防護 (DLP) 原則。
ms.openlocfilehash: ad333007b2efdcf577f1c31afc716c525a7abf7e
ms.sourcegitcommit: a53ec6ab7bf59983780ea7187cd5d56b8b1f4b33
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/07/2020
ms.locfileid: "41855372"
---
# <a name="protect-sharepoint-online-files-with-retention-labels-and-dlp"></a>使用保留標籤與 DLP 來保護 SharePoint Online 檔案

您可以使用本文中的步驟，為基準、機密和高度機密 SharePoint Online 小組網站設計及部署保留標籤和 DLP 原則。 如需這三種保護層級的詳細資訊，請參閱[保護 SharePoint Online 網站與檔案](../security/office-365-security/secure-sharepoint-online-sites-and-files.md)。
  
## <a name="how-this-works"></a>如何進行此作業

1. 建立需要的保留標籤並將它們發行。 發行這些標籤可能需要最多 12 小時的時間。
2. 針對所需的 SharePoint 網站，請編輯文件庫設定，將需要的保留標籤套用至文件庫中的項目。
3. 建立 DLP 原則，以根據保留標籤採取動作。

當使用者新增文件至文件庫時，依預設，文件會收到指派的保留標籤。 如有需要，使用者可以變更標籤。 當使用者共用組織外部的文件時，DLP 會檢查是否已指派標籤，並在 DLP 原則符合標籤時採取動作。 DLP 也會尋找其他原則相符項目，例如保護具有信用卡號碼的檔案 (如果已設定這類原則)。 

## <a name="retention-labels-for-your-sharepoint-online-sites"></a>適用於 SharePoint Online 網站的保留標籤

建立保留標籤並將其指派給 SharePoint Online 小組網站需要三個階段。
  
### <a name="phase-1-determine-the-retention-label-names"></a>階段 1：決定保留標籤名稱

在此階段中，您會為套用至 SharePoint Online 小組網站的四種資訊保護層級，決定其保留標籤的名稱。 下表列出每種層級的建議名稱。
  
|**SharePoint Online 小組網站保護層級**|**標籤名稱**|
|:-----|:-----|
|基準-公用  <br/> |內部公用  <br/> |
|基準-私人  <br/> |Private  <br/> |
|敏感性  <br/> |敏感性  <br/> |
|高度機密  <br/> |高度機密  <br/> |
   
### <a name="phase-2-create-the-retention-labels"></a>階段 2：建立保留標籤

在此階段中，您會為不同資訊保護層級建立所決定的標籤，然後將它發佈。
  
1. 使用具有安全性系統管理員或公司系統管理員角色的帳戶登入 [Microsoft 365 合規性入口網站](https://compliance.microsoft.com)。
    
2. 從瀏覽器的 [首頁 - Microsoft 365 合規性]**** 索引標籤，按一下 [分類] > [標籤]****。
    
3. 按一下 [保留標籤] > [建立標籤]****。
    
4. 在 [命名您的標籤]**** 窗格中，鍵入標籤名稱和系統管理員與使用者的描述，然後按 [下一步]****。

5. 在 [檔案計畫描述元]**** 窗格上，視需要填寫，然後按 [下一步]****。
    
6. 在 [標籤設定]**** 窗格中，視需要將 [保留]**** 設定為 [開啟]**** 並設定保留設定。 按 [下一步]****。
    
7. 在 [檢閱您的設定]**** 窗格中，按一下 [建立標籤]****。
    
8. 對於其他標籤，按一下 [建立標籤]****，然後視需要重複步驟 3-7。
    

### <a name="publish-your-new-labels"></a>發佈新標籤

接下來，使用下列步驟來發佈新的保留標籤。
  
1. 從 [標籤]**** 窗格，按一下 [保留標籤]**** 索引標籤，然後按一下 [發佈標籤]****。
    
2. 在 [選擇要發佈的標籤]**** 窗格上，按一下 [選擇要發佈的標籤]****。
    
3. 在 [選擇標籤]**** 窗格上，按一下 [新增]****，選取所有四個標籤，然後按一下 [新增]****。
    
4. 按一下 [完成]****。
    
5. 在 [選擇要發佈的標籤]**** 窗格上，按一下 [下一步]****。
    
6. 在 [選擇位置]**** 窗格中，按一下 [下一步]****。
    
7. 在 [命名您的原則]**** 窗格的 [名稱]**** 中，鍵入標籤集的名稱，然後按一下 [下一步]****。
    
8. 在 [檢閱您的設定]**** 窗格中，按一下 [發佈標籤]****，然後按一下 [關閉]****。

    
### <a name="phase-3-apply-the-retention-labels-to-your-sharepoint-online-sites"></a>階段 3：將保留標籤套用至 SharePoint Online 網站

使用下列步驟，將保留標籤套用至 SharePoint Online 小組網站的文件資料夾。
  
1. 登入 [Office 365 入口網站](https://www.office.com)，按一下 **SharePoint** App。
    
2. 在瀏覽器的新 [SharePoint]**** 索引標籤中，按一下需要指派保留標籤的網站。
    
3. 在瀏覽器的新 [SharePoint 網站] 索引標籤中，按一下 [文件]****。
    
4. 按一下設定圖示，然後按一下 [文件庫設定]****。
    
5. 在 [權限與管理]**** 下，按一下 [Apply label to items in this library]\(將標籤套用至此文件庫中的項目)****。
    
6. 在 [設定] - [套用標籤]**** 中，選取適當的保留標籤，然後按一下 [儲存]****。
    
7. 關閉 SharePoint Online 網站的索引標籤。
    
8. 重複步驟 2-8，將保留標籤指派給其他 SharePoint Online 網站。
    
以下是產生的組態。
  
![用於四種類型 SharePoint Online 小組網站的保留標籤。](media/e0a4fdd2-1c30-4d93-8af4-a6f0c6c29966.png)
  
## <a name="dlp-policies-for-your-sharepoint-online-sites"></a>適用於 SharePoint Online 網站的 DLP 原則

使用下列步驟來設定 DLP 原則，以在使用者共用組織外部 SharePoint Online 機密小組網站上的文件時通知使用者。

1. 使用具有安全性系統管理員或公司系統管理員角色的帳戶登入 [Microsoft 365 合規性入口網站](https://compliance.microsoft.com/)。
    
2. 在瀏覽器的新 [Microsoft 365 合規性]**** 索引標籤上，按一下 [原則] > [資料外洩防護]****。
    
3. 在 [首頁] > [資料外洩防護]**** 窗格中，按一下 [建立原則]****。
    
4. 在 [使用範本開始，或建立自訂原則]**** 窗格中，按一下 [自訂]****，然後按 [下一步]****。
    
5. 在 [命名您的原則]**** 窗格的 [名稱]**** 中，鍵入機密層級 DLP 原則的名稱，然後按一下 [下一步]****。
    
6. 在 [選擇位置]**** 窗格中，按一下 [讓我選擇一個特定位置]****，然後按 [下一步]****。
    
7. 在位置清單中，停用 [Exchange 電子郵件]****、[OneDrive 帳戶]**** 和 [Teams 聊天與通道訊息]**** 位置，然後按 [下一步]****。
    
8. 在 [自訂您要保護的內容類型]**** 窗格中，按一下 [編輯]****。
    
9. 在 [選擇要保護的內容類型]**** 窗格中，從下拉式方塊按一下 [新增]****，然後按一下 [保留標籤]****。
    
10. 在 [保留標籤]**** 窗格中，按一下 [新增]**** 並選取 [敏感性]**** 標籤，然後依序按一下 [新增]**** 和 [完成]****。
    
11. 在 [選擇要保護的內容類型]**** 窗格中，按一下 [儲存]****。
    
12. 在 [Customize the type of content you want to protect] (自訂您要保護的內容類型)**** 窗格中，按一下 [下一步]****。

13. 在 [What do you want to do if we detect sensitive info?]\(如果偵測到機密資訊要如何處理?)**** 窗格中，按一下 [Customize the tip and email]\(自訂提示和電子郵件)****。
    
14. 在 [Customize policy tips and email notifications]\(自訂原則提示和電子郵件通知)**** 窗格中，按一下 [Customize the policy tip text]\(自訂原則提示文字)****。
    
15. 在文字方塊中，根據您是否選擇使用敏感性標籤來保護敏感性檔案，請輸入或貼上下列其中一個提示：
    
  - 若要與組織外部的使用者共用，請下載檔案，然後將它開啟。 依序按一下 [檔案]、[保護文件] 和 [以密碼加密]，然後指定強式密碼。 以個別電子郵件或其他通訊方式傳送密碼。
  - 高度機密的檔案會受加密保護。只有獲得您 IT 部門授與權限的外部使用者可以讀取它們。
    
    或者，鍵入或貼上您自己的原則提示，以指示使用者如何共用組織外部的檔案。
    
16. 按一下 [確定]****。
    
17. 在 [What do you want to do if we detect sensitive info?]\(如果偵測到機密資訊要如何處理?)**** 窗格中，按一下 [下一步]****。
    
18. 在 [要先開啟原則或測試內容嗎?]**** 窗格中，按一下 [是]**** 立即將它開啟，然後按一下 [下一步]****。
    
19. 在 [檢閱您的設定]**** 窗格中，按一下 [建立]****，然後按一下 [關閉]****。
    
以下是敏感性 SharePoint Online 小組網站的設定結果。
  
![使用 [敏感性] 保留標籤之隔離 SharePoint Online 小組網站的 DLP 原則](media/2ff4cc53-87a8-43e3-b637-3068d88409f3.png)
  
接下來，使用下列步驟來設定 DLP 原則，以在使用者共用組織外部 SharePoint Online 高度機密小組網站上的文件時封鎖使用者。
  
1. 在瀏覽器的新 [Microsoft 365 合規性]**** 索引標籤上，按一下 [原則] > [資料外洩防護]****。
    
2. 在 [資料外洩防護]**** 窗格中，按一下 [建立原則]****。
    
3. 在 [從範本開始或建立自訂原則]**** 窗格中，按一下 [自訂]****，然後按一下 [下一步]****。
    
4. 在 [命名您的原則]**** 窗格的 [名稱]**** 中，鍵入高度機密層級 DLP 原則的名稱，然後按一下 [下一步]****。
    
5. 在 [選擇位置]**** 窗格中，按一下 [Let me choose specific locations]\(讓我選擇特定位置)****，然後按一下 [下一步]****。
    
6. 在位置清單中，停用 [Exchange 電子郵件]****、[OneDrive 帳戶]**** 和 [Teams 聊天與通道訊息]**** 位置，然後按 [下一步]****。
    
7. 在 [自訂要保護的敏感性資訊類型]**** 窗格中，按一下 [編輯]****。
    
8. 在 [選擇要保護的內容類型]**** 窗格中，從下拉式方塊按一下 [新增]****，然後按一下 [保留標籤]****。
    
9. 在 [保留標籤]**** 窗格中，按一下 [新增]****，並選取 [高度機密性]**** 標籤，然後依序按一下 [新增]**** 和 [完成]****。
    
10. 在 [Choose the types of content to protect]\(選擇要保護的內容類型)**** 窗格中，按一下 [儲存]****。
    
12. 在 [Customize the types of sensitive info you want to protect]\(自訂您要保護的機密資訊類型)**** 窗格中，按一下 [下一步]****。
    
13. 在 [What do you want to do if we detect sensitive info?]\(如果偵測到機密資訊要如何處理?)**** 窗格中，按一下 [Customize the tip and email]\(自訂提示和電子郵件)****。
    
14. 在 [Customize policy tips and email notifications]\(自訂原則提示和電子郵件通知)**** 窗格中，按一下 [Customize the policy tip text]\(自訂原則提示文字)****。
    
15. 在文字方塊中，鍵入或貼上下列內容：
    
  - 若要與組織外部的使用者共用，請下載檔案，然後將它開啟。 依序按一下 [檔案]、[保護文件] 和 [以密碼加密]，然後指定強式密碼。 以個別電子郵件或其他通訊方式傳送密碼。
    
    或者，鍵入或貼上您自己的原則提示，以指示使用者如何共用組織外部的檔案。
    
16. 按一下 [確定]****。
    
17. 在 [如果偵測到敏感性資訊，您要怎麼做?]**** 窗格中，於 [偵測是否一次共用特定數目的敏感性資訊]**** 下，按一下 [限制存取或加密內容]****，然後按 [下一步]****。
    
18. 在 [要先開啟原則或測試內容嗎?]**** 窗格中，按一下 [是]**** 立即將它開啟，然後按一下 [下一步]****。
    
19. 在 [檢閱您的設定]**** 窗格中，按一下 [建立]****，然後按一下 [關閉]****。
    
以下是高度機密 SharePoint Online 小組網站的設定結果。
  
![使用 [高度機密性] 保留標籤之隔離 SharePoint Online 小組網站的 DLP 原則](media/f705d3d0-23c9-4333-8b70-ad3b91f835ea.png)
  
## <a name="next-step"></a>下一步

[使用敏感度標籤來保護 SharePoint Online 檔案](protect-sharepoint-online-files-with-sensitivity-label.md)
    
## <a name="see-also"></a>另請參閱

[適用於政治活動、非營利組織和其他彈性組織的 Microsoft 安全性指南](../security/office-365-security/microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
  
[雲端採用和混合式解決方案](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)


