---
title: 建立小組網站 - 政治活動開發/測試環境
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/21/2018
audience: ITPro
ms.topic: article
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
localization_priority: Priority
search.appverid:
- MET150
ms.custom: seo-marvel-apr2020
ms.assetid: c2112ce8-1c4b-424f-b200-59e161db2d21
description: 摘要：在政治活動開發/測試環境中，建立公用、私用、敏感性及高度機密的 SharePoint Online 小組網站。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 80c975cd181f326fc2766c6ebfbd0d7f8a5164f2
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108148"
---
# <a name="create-team-sites-in-a-political-campaign-devtest-environment"></a>在政治活動開發/測試環境中建立小組網站

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**

- [適用於 Office 365 的 Microsoft Defender 方案 2](defender-for-office-365.md)

 **摘要：** 在政治活動開發/測試環境中，建立公用、私用、敏感性及高度機密的 SharePoint Online 小組網站。

使用本文所述指示來建立開發/測試環境，其中包含針對 [適用於政治活動、非營利組織和其他彈性組織的 Microsoft 安全性指南](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)解決方案的四種不同類型的 SharePoint Online 小組網站。這些網站會在主題 10 中詳細說明，主題 10 的標題為 **「SharePoint 和商務用 OneDrive」**。

## <a name="phase-1-create-your-political-campaign-devtest-environment"></a>階段 1：建立政治活動開發/測試環境

首先，請依照[設定政治活動開發/測試環境的群組和使用者](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md)中的指示來建立訂閱、使用者和群組。

## <a name="phase-2-create-labels"></a>階段 2：建立標籤

在這個階段中，您會為 SharePoint Online 小組網站的文件資料夾，建立不同安全性層級的標籤。

1. 如果需要，請使用試用訂閱的全域系統管理員帳戶認證來登入 Microsoft 365 系統管理中心 (<https://admin.microsoft.com>)。如需說明，請參閱[在何處登入 Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4)。

2. 從您開始所在的 [首頁 **]**，按一下 [顯示全部 **]**。 在顯示的 [系統管理中心 **]** 區段中，按一下 [合規性 **]**。

3. 從 Microsoft 365 合規性中心的 [首頁 **]**，前往 [解決方案 **]** 區段 \> [資訊保護 **]**。 若要直接前往 [資訊保護 **]** 頁面，請使用 <https://compliance.microsoft.com//informationprotection>。

4. 在 [資訊保護 **]** 頁面上，確認已選取 [標籤 **]** 標記，然後按一下 [建立標籤圖示![]](../../media/m365-cc-sc-create-icon.png) **建立標籤**。

5. [新增敏感度標籤 **]** 精靈隨即會開啟。 在 [名稱與描述 **]** 步驟上，輸入下列值：
   - **名稱**：輸入 **內部**。
   - **顯示名稱**
   - **給使用者的描述**

   完成後，按 [下一步 **]**。

6. 在 [標籤設定] 窗格中，按一下 [下一步]。

7. 在 [檢閱您的設定] 窗格中，按一下 [建立此標籤]，然後按一下 [關閉]。

8. 重複步驟 5-8，逐一設定下列其他標籤：

   - 私人
   - 敏感性
   - 高度機密

9. 從 [首頁] > [標籤] 窗格中，按一下 [Publish labels]\(發佈標籤)。

10. 在 [選擇要發佈的標籤] 窗格中，按一下 [選擇要發佈的標籤]。

11. 在 [Choose labels]\(選擇標籤) 窗格中，按一下 [新增] 並選取所有四個標籤。

12. 按一下 [完成]。

13. 在 [選擇要發佈的標籤] 窗格上，按一下 [下一步]。

14. 在 [選擇位置] 窗格中，按一下 [下一步]。

15. 在 [命名您的原則] 窗格上，於 [名稱] 中鍵入 **Campaign**，然後按一下 [下一步]。

16. 在 [檢閱您的設定] 窗格中，按一下 [發佈標籤]，然後按一下 [關閉]。

## <a name="phase-3-create-your-sharepoint-online-team-sites"></a>階段 3：建立 SharePoint Online 小組網站

在這個階段，您可以為政治活動建立及設定 SharePoint Online 小組網站，其對應到四種類型的 SharePoint Online 小組網站。

### <a name="campaign-wide-team-site"></a>整個活動的小組網站

若要建立公用的基準 SharePoint Online 小組網站，請執行下列作業：

1. 如果需要，請使用本機電腦上的瀏覽器，並使用全域管理員帳戶登入系統管理中心 (<https://admin.microsoft.com>)。

2. 在磚清單中，按一下 [SharePoint]。

3. 在瀏覽器的新 [SharePoint] 索引標籤上，按一下 [+ 建立網站]。

4. 在 [建立網站] 頁面上，按一下 [小組網站]。

5. 在 [網站名稱] 中，鍵入 **「整個活動」**。

6. 在 [小組網站描述] 中，鍵入 **「整個活動的 SharePoint 網站」**。

7. 在 [隱私權設定] 中，選取 [公用 - 組織中的任何人都可以存取此網站]，然後按一下 [下一步]。

8. 在 [您想要新增誰?] 窗格上，按一下 [完成]。

接下來，針對 [Internal]\(內部) 標籤設定整個活動小組網站的文件資料夾。

1. 在瀏覽器的 [Campaign wide-Home]\(整個活動 - 首頁) 索引標籤中，按一下 [文件]。

2. 按一下設定圖示，然後按一下 [文件庫設定]。

3. 在 [權限與管理] 下，按一下 [Apply label to items in this library]\(將標籤套用至此文件庫中的項目)。

4. 在 [設定 - 套用標籤] 中，選取 [Internal (內部)]，然後按一下 [儲存]。

### <a name="campaign-project-1-team-site"></a>活動專案 1 小組網站

若要為活動內部的專案建立私用的基準 SharePoint Online 小組網站，請執行下列作業：

1. 如果需要，請使用本機電腦上的瀏覽器，並使用全域管理員帳戶登入系統管理中心 (<https://admin.microsoft.com>)。

2. 在磚清單中，按一下 [SharePoint]。

3. 在瀏覽器的新 [SharePoint] 索引標籤上，按一下 [+ 建立網站]。

4. 在 [建立網站] 頁面上，按一下 [小組網站]。

5. 在 [網站名稱] 中，鍵入 **「活動專案 1」**。

6. 在 [小組網站描述] 中，鍵入 **「活動專案 1 的 SharePoint 網站」**。

7. 在 [隱私權設定] 中，選取 [私人 - 只有成員可以存取此網站]，然後按一下 [下一步]。

8. 在 [您想要新增誰?] 窗格上，按一下 [完成]。

接下來，為「活動專案 1」小組網站的文件資料夾設定「私用」標籤。

1. 在瀏覽器的 [Campaign project 1-Home (活動專案 1 - 首頁)] 索引標籤中，按一下 [文件]。

2. 按一下設定圖示，然後按一下 [文件庫設定]。

3. 在 [權限與管理] 下，按一下 [Apply label to items in this library]\(將標籤套用至此文件庫中的項目)。

4. 在 [設定 - 套用標籤] 中，選取 [私用]，然後按一下 [儲存]。

### <a name="campaign-marketing-team-site"></a>活動行銷小組網站

若要為活動行銷資源建立敏感性層級的隔離 SharePoint Online 小組網站，請執行下列作業：

1. 使用本機電腦上的瀏覽器，並以全域管理員帳戶登入系統管理中心 (<https://admin.microsoft.com>)。

2. 在磚清單中，按一下 [SharePoint]。

3. 在瀏覽器的新 [SharePoint] 索引標籤上，按一下 [+ 建立網站]。

4. 在 [建立網站] 頁面上，按一下 [小組網站]。

5. 在 [小組網站名稱] 中，鍵入 **「活動行銷」**。

6. 在 [小組網站描述] 中，鍵入 **「活動行銷 (敏感) 的 SharePoint 網站」**。

7. 在 [隱私權設定] 中，選取 [私人 - 只有成員可以存取此網站]，然後按一下 [下一步]。

8. 在 [您想要新增誰?] 窗格上，按一下 [完成]。

9. 在瀏覽器中新的 [活動行銷] 索引標籤上，在工具列中按一下設定圖示，然後按一下 [網站權限]。

10. 在 [網站權限] 窗格中，按一下 [進階權限設定]。

11. 在瀏覽器的新 [權限] 索引標籤中，按一下 [存取要求設定]。

12. 在 **[存取要求設定]** 對話方塊中，清除 **[允許成員共用網站以及個別檔案和資料夾]** 和 **[允許成員邀請其他人加入網站成員群組]** 核取方塊，在 **[傳送存取的所有要求]** 中鍵入 **ITAdmin1@**\<your organization name\>**.onmicrosoft.com**，然後按一下 **[確定]**。

13. 按一下清單中的 [活動行銷成員]。

14. 在 [人員與群組] 頁面上，按一下 [新增]。

15. 在 [共用] 對話方塊中，輸入 **Senior and strategic staff**，選取它，然後按一下 [共用]。

16. 為 **分析人員** 群組和 **Regular1** 使用者帳戶重複步驟 14 與 15。

17. 按一下瀏覽器上的 [上一頁] 按鈕。

18. 按一下清單中的 [活動行銷擁有者]。

19. 在 [人員與群組] 頁面上，按一下 [新增]。

20. 在 [共用] 對話方塊中，鍵入 **IT 人員**，並加以選取，然後按一下 [共用]。

21. 按一下瀏覽器上的 [上一頁] 按鈕。

22. 關閉瀏覽器中的 [人員與群組] 索引標籤，按一下瀏覽器中的 [活動行銷 - 首頁] 索引標籤，然後關閉 [網站權限] 窗格。

以下是設定權限的結果：

- **「活動行銷 - 成員」** 的 SharePoint 群組僅包含 **資深和策略人員** 群組 (其中包含 Candidate、ChiefOfStaff 和 Strategic1 使用者帳戶)、**活動行銷** 群組 (其中包含全域系統管理員使用者帳戶)、**分析人員** 群組 (其中包含 DataScientist1 使用者帳戶)，以及 **Regular1** 使用者帳戶。

- **「活動行銷 - 擁有者」** 的 SharePoint 群組僅包含 **IT 人員** 群組 (其中僅包含 ITAdmin1 和 ITAdmin2 使用者帳戶)。

- **「活動行銷 - 訪客」** 的 SharePoint 群組未包含任何群組或使用者帳戶。

- 成員無法修改網站層級的權限 (這只能由 **「活動行銷 - 擁有者」** 群組成員來執行)。

- 其他使用者帳戶無法存取網站或其資源，但可以將電子郵件傳送至 ITAdmin1 使用者帳戶信箱，以要求存取網站。

接下來，為「活動行銷」小組網站的文件資料夾設定「敏感性」標籤。

1. 在瀏覽器的 [活動行銷 - 首頁] 索引標籤中，按一下 [文件]。

2. 按一下設定圖示，然後按一下 [文件庫設定]。

3. 在 [權限與管理] 下，按一下 [Apply label to items in this library]\(將標籤套用至此文件庫中的項目)。

4. 在 [設定 - 套用標籤] 中，選取 [敏感性]，然後按一下 [儲存]。

接下來，設定一個資料外洩防護 (DLP) 原則，該原則會在使用者與組織外部共用具敏感性標籤的 SharePoint Online 小組網站上的文件時，即會通知使用者。此 DLP 原則會套用到活動行銷網站中的資源。

1. 從瀏覽器的 [Microsoft Office 首頁] 索引標籤，按一下 [安全性與合規性] 磚。

2. 在瀏覽器的新 [安全性與合規性] 索引標籤上，按一下 [資料外洩防護] > [原則]。

3. 在 [資料外洩防護] 窗格中，按一下 [+ 建立原則]。

4. 在 [從範本開始或建立自訂原則] 窗格中，按一下 [自訂]，然後按一下 [下一步]。

5. 在 [命名您的原則] 窗格的 [名稱] 中，鍵入 **Sensitive label SharePoint Online team sites**，然後按一下 [下一步]。

6. 在 [選擇位置] 窗格中，按一下 [Let me choose specific locations]\(讓我選擇特定位置)，然後按一下 [下一步]。

7. 在位置清單中，停用 [Exchange 電子郵件] 和 [OneDrive 帳戶] 位置，然後按一下 [下一步]。

8. 在 [Customize the types of sensitive info you want to protect]\(自訂您要保護的機密資訊類型) 窗格中，按一下 [編輯]。

9. 在 [選擇要保護的內容類型] 窗格中，從下拉式方塊按一下 [新增]，然後按一下 [標籤]。

10. 在 [標籤] 窗格中，按一下 [+ 新增] 並選取 [敏感性] 標籤，然後依序按一下 [新增] 和 [完成]。

11. 在 [Choose the types of content to protect]\(選擇要保護的內容類型) 窗格中，按一下 [儲存]。

12. 在 [Customize the types of sensitive info you want to protect]\(自訂您要保護的機密資訊類型) 窗格中，按一下 [下一步]。

13. 在 [What do you want to do if we detect sensitive info?]\(如果偵測到機密資訊要如何處理?) 窗格中，按一下 [Customize the tip and email]\(自訂提示和電子郵件)。

14. 在 [Customize policy tips and email notifications]\(自訂原則提示和電子郵件通知) 窗格中，按一下 [Customize the policy tip text]\(自訂原則提示文字)。

15. 在文字方塊中，鍵入或貼上下列內容：

    - 若要與組織外部的使用者共用，請下載檔案，然後將它開啟。 依序按一下 [檔案]、[保護文件] 和 [以密碼加密]，然後指定強式密碼。 以個別電子郵件或其他通訊方式傳送密碼。

16. 按一下 [確定]。

17. 在 [如果偵測到機密資訊要如何處理?] 窗格中，清除 [禁止人員共用及限制共用內容的存取] 核取方塊，然後按一下 [下一步]。

18. 在 [要先開啟原則或測試內容嗎?] 窗格中，按一下 [是] 立即將它開啟，然後按一下 [下一步]。

19. 在 [檢閱您的設定] 窗格中，按一下 [建立]，然後按一下 [關閉]。

### <a name="campaign-strategy-team-site"></a>活動策略小組網站

若要為活動策略資源建立高度機密層級的隔離 SharePoint Online 小組網站，請執行下列作業：

1. 如果需要，請使用本機電腦上的瀏覽器，並使用全域管理員帳戶登入系統管理中心 (<https://admin.microsoft.com>)。

2. 在磚清單中，按一下 [SharePoint]。

3. 在瀏覽器的新 [SharePoint] 索引標籤上，按一下 [+ 建立網站]。

4. 在 [建立網站] 頁面上，按一下 [小組網站]。

5. 在 [小組網站名稱] 中，鍵入 **「活動策略」**。

6. 在 [小組網站描述] 中，鍵入 **「活動策略的 SharePoint 網站 (高度機密)」**。

7. 在 [隱私權設定] 中，選取 [私人 - 只有成員可以存取此網站]，然後按一下 [下一步]。

8. 在 [您想要新增誰?] 窗格上，按一下 [完成]。

9. 在瀏覽器中新的 [活動策略] 索引標籤上，在工具列中按一下設定圖示，然後按一下 [網站權限]。

10. 在 [網站權限] 窗格中，按一下 [進階權限設定]。

11. 在瀏覽器的新 [權限] 索引標籤中，按一下 [存取要求設定]。

12. 在 [存取要求設定] 對話方塊中，清除 [允許成員共用網站以及個別檔案和資料夾] 和 [允許成員邀請其他人加入網站成員群組]\(亦即清除所有三個核取方塊)，然後按一下 [確定]。

13. 按一下清單中的 [活動策略成員]。

14. 在 [人員與群組] 頁面上，按一下 [新增]。

15. 在 [共用] 對話方塊中，輸入 **Senior and strategic staff**，選取它，然後按一下 [共用]。

16. 按一下清單中的 [活動策略擁有者]。

17. 在 [人員與群組] 頁面上，按一下 [新增]。

18. 在 [共用] 對話方塊中，鍵入 **IT 人員**，並加以選取，然後按一下 [共用]。

19. 按一下瀏覽器上的 [上一頁] 按鈕。

20. 關閉瀏覽器中的 [人員與群組] 索引標籤，按一下瀏覽器中的 [活動策略 - 首頁] 索引標籤，然後關閉 [網站權限] 窗格。

以下是設定權限的結果：

- **「活動策略 - 成員」** 的 SharePoint 群組僅包含 **資深和策略人員** 群組 (其中僅包含 Candidate、ChiefOfStaff 和 Strategic1 使用者帳戶) 和 **活動策略** 群組 (其中僅包含全域系統管理員使用者帳戶)。

- **「活動策略 - 擁有者」** 的 SharePoint 群組僅包含 **IT 人員** 群組 (其中僅包含 ITAdmin1 和 ITAdmin2 使用者帳戶)。

- **「活動策略 - 訪客」** 的 SharePoint 群組未包含任何群組或使用者帳戶。

- 成員無法修改網站層級的權限 (這只能由 **「活動策略 - 擁有者」** 群組成員來執行)。

- 其他使用者帳戶無法存取網站或其資源，或要求存取網站。網站的額外權限必須由全域管理員或 **「活動策略 - 擁有者」** 群組成員來執行。

接下來，為「活動策略」小組網站的文件資料夾設定「高度機密」標籤。

1. 在瀏覽器的 [活動策略 - 首頁] 索引標籤中，按一下 [文件]。

2. 按一下設定圖示，然後按一下 [文件庫設定]。

3. 在 [權限與管理] 下，按一下 [Apply label to items in this library]\(將標籤套用至此文件庫中的項目)。

4. 在 [設定 - 套用標籤] 中，選取 [高度機密]，然後按一下 [儲存]。

接下來，設定 DLP 原則；當使用者在組織外部共用具「高度機密」標籤之 SharePoint Online 小組網站上的文件時，即會封鎖使用者。此 DLP 原則會套用到活動策略網站中的資源。

1. 如果需要，請使用本機電腦上的瀏覽器，並使用具有安全性系統管理員或公司系統管理員角色的帳戶登入系統管理中心 (<https://admin.microsoft.com>)。

2. 從瀏覽器的 [Microsoft Office 首頁] 索引標籤，按一下 [安全性與合規性] 磚。

3. 在瀏覽器的新 [安全性與合規性] 索引標籤上，按一下 [資料外洩防護] > [原則]。

4. 在 [資料外洩防護] 窗格中，按一下 [+ 建立原則]。

5. 在 [從範本開始或建立自訂原則] 窗格中，按一下 [自訂]，然後按一下 [下一步]。

6. 在 [命名您的原則] 窗格的 [名稱] 中，鍵入 **Highly Confidential label SharePoint Online team sites**，然後按一下 [下一步]。

7. 在 [選擇位置] 窗格中，按一下 [Let me choose specific locations]\(讓我選擇特定位置)，然後按一下 [下一步]。

8. 在位置清單中，停用 [Exchange 電子郵件] 和 [OneDrive 帳戶] 位置，然後按一下 [下一步]。

9. 在 [Customize the types of sensitive info you want to protect]\(自訂您要保護的機密資訊類型) 窗格中，按一下 [編輯]。

10. 在 [選擇要保護的內容類型] 窗格中，從下拉式方塊按一下 [新增]，然後按一下 [標籤]。

11. 在 [標籤] 窗格中，按一下 [+ 新增]，並選取 [高度機密] 標籤，然後依序按一下 [新增] 和 [完成]。

12. 在 [Choose the types of content to protect]\(選擇要保護的內容類型) 窗格中，按一下 [儲存]。

13. 在 [Customize the types of sensitive info you want to protect]\(自訂您要保護的機密資訊類型) 窗格中，按一下 [下一步]。

14. 在 [What do you want to do if we detect sensitive info?]\(如果偵測到機密資訊要如何處理?) 窗格中，按一下 [Customize the tip and email]\(自訂提示和電子郵件)。

15. 在 [Customize policy tips and email notifications]\(自訂原則提示和電子郵件通知) 窗格中，按一下 [Customize the policy tip text]\(自訂原則提示文字)。

16. 在文字方塊中，鍵入或貼上下列內容：

    - 若要與組織外部的使用者共用，請下載檔案，然後將它開啟。 依序按一下 [檔案]、[保護文件] 和 [以密碼加密]，然後指定強式密碼。 以個別電子郵件或其他通訊方式傳送密碼。

17. 按一下 [確定]。

18. 在 [如果偵測到機密資訊要如何處理?] 窗格中，選取 [需要有業務上的正當理由才能覆寫]，然後按一下 [下一步]。

19. 在 [要先開啟原則或測試內容嗎?] 窗格中，按一下 [是] 立即將它開啟，然後按一下 [下一步]。

20. 在 [檢閱您的設定] 窗格中，按一下 [建立]，然後按一下 [關閉]。

遵循[使用 Office 365 系統管理中心啟用 Azure RMS](/information-protection/deploy-use/activate-office365) 中的指示。

接著，遵循下列步驟，為 Azure 資訊保護設定新的限域原則與子標籤，以提供保護及權限：

1. 使用具有安全性系統管理員或公司系統管理員角色的帳戶登入系統管理中心。如需說明，請參閱[在何處登入 Office 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4)。

2. 在您瀏覽器的個別索引標籤中，移至 Azure 入口網站 (<https://portal.azure.com>)。

3. 在搜尋窗格中，輸入 **[資訊]**，然後按一下 **Azure 資訊保護**。

4. 按一下 [標籤]。

5. 以滑鼠右鍵按一下 [高度機密] 標籤，然後再按一下 [新增子標籤]。

6. 在 [名稱] 中鍵入 **CampaignStrategy**，並在 [描述] 中鍵入 **活動策略小組網站中的文件標籤**。

7. 在 [為包含此標籤的文件與電子郵件設定權限] 中，按一下 [保護]。

8. 在 [保護] 區段中，按一下 [Azure (雲端金鑰)]。

9. 在 [保護] 刀鋒視窗中，按一下 [保護設定] 下的 [+ 新增權限]。

10. 在 [新增權限] 刀鋒視窗中，按一下 [指定使用者與群組] 下的 [+ 瀏覽目錄]。

11. 在 [AAD 使用者和群組] 窗格中，選取 [資深和策略人員]，然後按一下 [選取]。

12. 在 [選擇預設的權限，或設定自訂] 下，按一下 [自訂]，然後選取 [檢視權限]、[編輯內容]、[儲存]、[回覆]、[全部回覆] 核取方塊。

13. 按兩次 [確定]。

14. 在 [子標籤] 刀鋒視窗中，按一下 [儲存]，然後按一下 [確定]。

15. 在 [Azure 資訊保護] 刀鋒視窗中，按一下 [原則] > [+ 新增原則]。

16. 在 [名稱] 中鍵入 **CampaignStrategy**，並在 [描述] 中鍵入 **活動策略小組網站中的文件**。

17. 按一下 [選取取得此原則的使用者或群組] > [使用者/群組]，然後選取 [資深和策略人員]。

18. 按一下 **[選取]\> [確定]**。

19. 按一下 [新增或移除標籤]。在 [原則: 新增或移除標籤] 窗格中，按一下 [CampaignStrategy]，然後按一下 [確定]。

20. 按一下 [儲存]，然後按一下 [確定]。

您現在準備好開始建立這四個網站中的文件，以及使用不同的使用者帳戶來測試其存取。

若要使用 Azure 資訊保護和此新標籤來保護文件，您必須在測試電腦上 [安裝 Azure 資訊保護用戶端](/information-protection/rms-client/install-client-app)，並從系統管理中心安裝 Office，然後使用試用訂用帳戶 **「資深和策略人員」** 群組中的帳戶登入 Microsoft Word。

## <a name="see-also"></a>另請參閱

[適用於政治活動、非營利組織和其他彈性組織的 Microsoft 安全性指南](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)

[設定政治活動開發/測試環境的群組和使用者](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md)

[雲端採用測試實驗室指南 (TLG)](../../enterprise/cloud-adoption-test-lab-guides-tlgs.md)

[Microsoft 365 解決方案與架構中心](../../solutions/index.yml)
