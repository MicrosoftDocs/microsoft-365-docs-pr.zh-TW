---
title: 在 Microsoft 365 合規性中心中搜尋稽核記錄
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: 0d4d0f35-390b-4518-800e-0c7ec95e946c
description: 使用 Microsoft 365 合規性中心來搜尋整合的稽核記錄，以檢視組織中的使用者和系統管理員活動。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 46f223953df65b75c0ecfe0d2c9fe92514b797ff
ms.sourcegitcommit: 5db5047c24b56f3af90c2bc5c830a7a13eeeccad
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/09/2021
ms.locfileid: "53341649"
---
# <a name="search-the-audit-log-in-the-compliance-center"></a>在合規性中心搜尋稽核記錄

需要了解是否有使用者已檢視特定文件或清除信箱中的項目嗎？ 如果是，您可以使用 Microsoft 365 合規性中心來搜尋整合的稽核記錄，以檢視組織中的使用者和系統管理員活動。 為什麼使用整合的稽核記錄？ 因為您可以在 Microsoft 365 中搜尋下列類型的[使用者和系統管理員活動](#audited-activities)：

- SharePoint Online 和商務用 OneDrive 中的使用者活動
- Exchange Online 中的使用者活動 (Exchange 信箱稽核記錄)
- SharePoint Online 中的系統管理員活動
- Azure Active Directory 中的系統管理員活動 (適用於 Microsoft 365 的目錄服務) 
- Exchange Online 中的系統管理員活動 (Exchange 系統管理員稽核記錄)
- 安全性與合規性中心中的電子文件探索活動
- Power BI 中的使用者和系統管理員活動
- Microsoft Teams 中的使用者和系統管理員活動
- Dynamics 365 中的使用者和系統管理員活動
- Yammer 中的使用者和系統管理員活動
- Microsoft Power Automate 中的使用者和系統管理員活動
- Microsoft Stream 中的使用者和系統管理員活動
- Microsoft 工作場所分析中的分析師和系統管理員活動
- Microsoft Power Apps 中的使用者和系統管理員活動
- Microsoft Flow 中的使用者和系統管理員活動
- 使用 SharePoint Online 或 Microsoft Teams 網站之敏感度標籤的使用者和系統管理員活動
- 簡報電子郵件和 MyAnalytics 中的系統管理員活動

## <a name="before-you-search-the-audit-log"></a>在您搜尋稽核記錄之前

開始搜尋稽核記錄前，請務必閱讀下列項目。

- 預設會開啟適用於 Microsoft 365 和 Office 365 企業組織的 [稽核記錄搜尋]。 若要驗證 [稽核記錄搜尋] 已開啟，您可以在 Exchange Online PowerShell 中執行下列命令：

  ```powershell
  Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
  ```

  *UnifiedAuditLogIngestionEnabled* 屬性為 `True` 值表示已開啟 [稽核記錄搜尋]。 如需詳細資訊，請參閱[開啟或關閉稽核記錄搜尋](turn-audit-log-search-on-or-off.md)。

- 您必須在 Exchange Online 中獲派為 [僅限檢視稽核記錄] 或 [稽核記錄] 角色，才能搜尋稽核記錄。 根據預設，這些角色會在 Exchange 系統管理員中心的 **[權限]** 頁面上，指派給 [法務遵循管理] 和 [組織管理] 角色群組。 系統會將 Office 365 和 Microsoft 365 中的全域系統管理員自動新增為 Exchange Online 中 [組織管理] 角色群組的成員。 若要提供讓使用者能夠搜尋稽核記錄的最低權限等級，您可以在 Exchange Online 中建立自訂角色群組、新增 [僅限檢視稽核記錄] 或 [稽核記錄] 角色，然後將使用者加入這個新的角色群組成為其中的成員。 如需詳細資訊，請參閱[管理 Exchange Online 中的角色群組](/Exchange/permissions-exo/role-groups)。

  > [!IMPORTANT]
  > 如果您在 Microsoft 365 合規性中心的 **[權限]** 頁面上，將 [僅限檢視稽核記錄] 或 [稽核記錄] 角色指派給使用者，使用者將無法搜尋稽核記錄。 您必須在 Exchange Online 中指派權限。 這是因為用來搜尋稽核記錄的基礎 Cmdlet 是 Exchange Online Cmdlet。

- 當使用者或系統管理員執行稽核的活動時，稽核記錄會隨即產生，並儲存在您組織的稽核記錄中。 稽核記錄的保留時間及可在稽核記錄中搜尋的時間長度，取決於您的 Office 365 或 Microsoft 365 企業版訂閱，具體來說，取決於指派給特定使用者的授權類型。

  - 對於獲指派 Office 365 E5 或 Microsoft 365 E5 授權的使用者 (或擁有 Microsoft 365 E5 合規性或 Microsoft 365 E5 電子文件探索和稽核附加元件授權的使用者)，Azure Active Directory、Exchange 和 SharePoint 活動的稽核記錄依預設會保留一年。 組織也可建立稽核記錄保留原則，以保留其他服務中的活動稽核記錄，最長一年。 如需詳細資訊，請參閱[管理稽核記錄保留原則](audit-log-retention-policies.md)。

    > [!NOTE]
    > 如果您的組織有參與一年期稽核記錄保留的私人預覽計畫，則將不會重設一般發行日期之前產生的稽核記錄保留期間。

  - 對於獲派其他任何 (非 E5) Office 365 或 Microsoft 365 授權的使用者，稽核記錄會保留 90 天。 如需支援整合稽核記錄的 Office 365 和 Microsoft 365 訂閱清單，請參閱[安全性與合規性中心服務描述](/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center) (部分機器翻譯)。

    > [!NOTE]
    > 即使信箱稽核預設為開啟狀態，您可能還是會發現某些使用者的信箱稽核事件在 Microsoft 365 合規性中心的稽核記錄搜尋中找不到，透過 Office 365 管理活動 API 也找不到。 如需詳細資訊，請參閱[信箱稽核記錄的相關資訊](enable-mailbox-auditing.md#more-information)。

- 如果您想要關閉組織的稽核記錄搜尋功能，您可以在與 Exchange Online 組織連線的遠端 PowerShell 中執行下列命令：

  ```powershell
  Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
  ```

    若要再次開啟稽核搜尋，您可以在 Exchange Online PowerShell 中執行下列命令：

  ```powershell
  Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
  ```

  如需詳細資訊，請參閱[關閉稽核記錄搜尋](turn-audit-log-search-on-or-off.md)。

- 如先前所述，用來搜尋稽核記錄的基礎 Cmdlet 是 Exchange Online Cmdlet，也就是 **Search-UnifiedAuditLog**。 這表示您可以使用此 Cmdlet 來搜尋稽核記錄，而不是使用 Microsoft 365 合規性中心中的 **[稽核記錄搜尋]** 頁面。 您必須在連線到 Exchange Online 組織的遠端 PowerShell，執行此 Cmdlet。 如需詳細資訊，請參閱 [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog)。

  若要了解如何將 **Search-UnifiedAuditLog** Cmdlet 所傳回的搜尋結果匯出為 CSV 檔案，請參閱 [匯出、設定及檢視稽核記錄檔的記錄](export-view-audit-log-records.md#tips-for-exporting-and-viewing-the-audit-log)中的＜匯出及檢視稽核記錄的秘訣＞一節。

- 如果您想要以程式設計方式從稽核記錄下載資料，我們建議您使用 Office 365 管理活動 API，而非使用 PowerShell 指令碼。 Office 365 管理活動 API 是一個 REST Web 服務，可用於為貴組織開發作業、安全性以及合規性的監控解決方案。 如需詳細資訊，請參閱 [Office 365 管理活動 API 參考](/office/office-365-management-api/office-365-management-activity-api-reference)。

- 發生事件後，對應的稽核記錄最多可能需要 30 分鐘或 24 小時的時間，才會在稽核記錄搜尋的結果中傳回。 下列表格顯示不同 Office 365 服務的所需時間。

  <br>

  ****

  |Microsoft 365 服務或功能|30 分鐘|24 小時|
  |---|:---:|:---:|
  |Office 365 防護和威脅情報|![核取記號](../media/checkmark.png)||
  |Azure Active Directory (使用者登入活動)||![核取記號](../media/checkmark.png)|
  |Azure Active Directory (系統管理員活動)||![核取記號](../media/checkmark.png)|
  |資料外洩防護|![核取記號](../media/checkmark.png)||
  |Dynamics 365 CRM||![核取記號](../media/checkmark.png)|
  |電子文件探索|![核取記號](../media/checkmark.png)||
  |Exchange Online|![核取記號](../media/checkmark.png)||
  |Microsoft Power Automate||![核取記號](../media/checkmark.png)|
  |Microsoft Project|![核取記號](../media/checkmark.png)||
  |Microsoft Stream|![核取記號](../media/checkmark.png)||
  |Microsoft Teams|![核取記號](../media/checkmark.png)||
  |Power Apps||![核取記號](../media/checkmark.png)|
  |Power BI|![核取記號](../media/checkmark.png)||
  |Microsoft 365 合規性中心|![核取記號](../media/checkmark.png)||
  |敏感度標籤||![核取記號](../media/checkmark.png)|
  |SharePoint Online 和商務用 OneDrive|![核取記號](../media/checkmark.png)||
  |工作場所分析|![核取記號](../media/checkmark.png)||
  |Yammer||![核取記號](../media/checkmark.png)|
  |Microsoft Forms|![核取記號](../media/checkmark.png)||
  |

- Azure Active Directory (Azure AD) 是適用於 Office 365 的目錄服務。 整合的稽核記錄包含 Microsoft 365 系統管理員中心或 Azure 管理入口網站中執行的使用者、群組、應用程式、網域及目錄活動。 如需 Azure AD 事件的完整清單，請參閱 [Azure Active Directory 稽核報告事件](/azure/active-directory/reports-monitoring/concept-audit-logs)。

- Power BI 的稽核記錄未預設為啟用。 若要在稽核記錄中搜尋 Power BI 活動，您必須在 Power BI 系統管理員入口網站中啟用稽核功能。 如需相關指示，請參閱 [Power BI 系統管理員入口網站](/power-bi/service-admin-portal#audit-logs)中的＜稽核記錄＞一節。

## <a name="search-the-audit-log"></a>搜尋稽核記錄

下列是在 Microsoft 365 中搜尋稽核記錄的流程。

[步驟 1：執行稽核記錄搜尋](#step-1-run-an-audit-log-search)

[步驟 2：檢視搜尋結果](#step-2-view-the-search-results)

[步驟 3：篩選搜尋結果](#step-3-filter-the-search-results)

[步驟 4：將搜尋結果匯出至檔案](#step-4-export-the-search-results-to-a-file)

### <a name="step-1-run-an-audit-log-search"></a>步驟 1：執行稽核記錄搜尋

1. 移至 <https://compliance.microsoft.com> 並登入。

    > [!TIP]
    > 使用私密瀏覽工作階段 (而非一般工作階段) 存取 Microsoft 365 合規性中心，藉此避免使用您目前登入的認證。若要在 Internet Explorer 或 Microsoft Edge 中開啟 InPrivate 瀏覽工作階段，只要按 CTRL+SHIFT+P 即可。若要在 Google Chrome 中開啟私密瀏覽工作階段 (稱為無痕式視窗)，請按 CTRL+SHIFT+N。

2. 在 Microsoft 365 合規性中心的左窗格中，按一下 **[稽核]**。

    **[稽核]** 頁面隨即顯示。

    ![設定準則，然後按一下 [搜尋] 即可執行報告](../media/AuditLogSearchPage1.png)

    > [!NOTE]
    > 如果顯示 **[開始記錄使用者和系統管理活動]** 連結，請按一下它以開啟稽核。 如果您沒有看到此連結，表示貴組織已開啟稽核。

3. 在 **[搜尋]** 索引標籤上，設定下列搜尋準則：

   1. **開始日期** 和 **結束日期**：根據預設會選取過去七天。 選取日期和時間範圍，以顯示該期間內已發生的事件。 日期和時間以當地時間顯示。 您可以指定的最大日期範圍為 90 天。 如果選定的日期範圍大於 90 天，則會顯示錯誤。

    > [!TIP]
    > 如果您使用的是 90 天的最大日期範圍，請為 **[開始日期]** 選取目前的時間。 否則，您會收到一則表示開始日期早於結束日期的錯誤。 如果您已開啟過去 90 天中的稽核，最大日期範圍不能在開啟稽核的日期之前開始。

   2. **活動**：按一下下拉式清單以顯示您可以搜尋的活動。 使用者和系統管理員活動會歸類成各種相關活動的群組。 您可以選取特定活動，或者也可以按一下活動群組名稱以選取該群組中的所有活動。 您也可以按一下選定的活動以清除選取。 執行搜尋後，只會顯示選定活動的稽核記錄項目。 選取 **[顯示所有活動的結果]** 會顯示選定使用者或使用者群組所執行的所有活動結果。<br/><br/>稽核記錄中會記錄超過 100 個使用者和系統管理員活動。 按一下本文主題的 **[已稽核活動]** 索引標籤，可查看不同服務中各項活動的描述。

   3. **使用者**：在此方塊中按一下，然後選取要顯示搜尋結果的一或多位使用者。 結果清單會顯示您在此方塊中選取的使用者所執行的選定活動之稽核記錄項目。 若要傳回貴組織中所有使用者 (及服務帳戶) 的項目，請將此方塊保留空白。

   4. **檔案、資料夾或網站**：輸入整個檔案或資料夾名稱的一部分，以搜尋含有特定關鍵字之資料夾的檔案相關活動。 您也可以指定檔案或資料夾的 URL。 如果您使用 URL，請確定您輸入了完整的 URL 路徑，或者，如果您只輸入部分 URL，請不要包含任何特殊字元或空格。<br/><br/>若要傳回貴組織中所有檔案和資料夾的項目，請將此方塊保留空白。

    > [!TIP]
    >
    > - 如果您要尋找與 **網站** 相關的所有活動，在 URL 後面加入萬用字元符號 (\*) 可傳回該網站的所有項目，例如 `"https://contoso-my.sharepoint.com/personal*"`。
    >
    > - 如果您要尋找與 **檔案** 相關的所有活動，在檔案名稱前面加入萬用字元符號 (\*) 可傳回該檔案的所有項目，例如 `"*Customer_Profitability_Sample.csv"`。

4. 按一下 **[搜尋]** 以使用您的搜尋準則執行搜尋。

   搜尋結果隨即載入，而它們在片刻之後會顯示在新的頁面上。 完成搜尋後，隨即顯示找到的結果數量。 系統會以 150 個事件為增量，最多顯示 5,000 個事件。 如果符合搜尋準則的事件超過 5,000 個，則會顯示最新的 5,000 個事件。

   ![搜尋完成後，會顯示結果數目。](../media/986216f1-ca2f-4747-9480-e232b5bf094c.png)

#### <a name="tips-for-searching-the-audit-log"></a>搜尋稽核記錄的祕訣

- 您可以按一下活動名稱，以選取要搜尋的特定活動。 或者您也可以按一下群組名稱，以搜尋群組中的所有活動 (例如 **[檔案和資料夾活動]**)。 如果已選取活動，您可以按一下它以取消選取。 您也可以使用搜尋方塊顯示含有您輸入的關鍵字之活動。

  ![按一下活動群組名稱以選取所有活動](../media/3cde97cb-6f35-47c0-8612-ecd9c6ac36a3.png)

- 您必須在 **[活動]** 清單中選取 **[顯示所有活動的結果]**，才能顯示來自 Exchange 系統管理員稽核記錄的事件。 來自此稽核記錄的事件會在結果的 [活動] 欄中顯示 Cmdlet 名稱 (例如 **Set-Mailbox**)。 如需詳細資訊，請按一下本主題中的 **[已稽核活動]** 索引標籤，然後按一下 **[Exchange 系統管理員活動]**。

  同樣地，也會有些稽核活動在 **[活動]** 清單中沒有對應的項目。 若您知道這些活動的作業名稱，即可搜尋所有活動，然後在 **[活動]** 欄的方塊中輸入作業名稱來篩選結果。 請參閱[步驟 3：篩選搜尋結果](#step-3-filter-the-search-results)，以了解更多有關篩選結果的資訊。

- 按一下 **[清除]** 以清除目前的搜尋準則。 日期範圍會回到過去七天的預設值。 您也可以按一下 **[清除全部以顯示所有活動的結果]**，以取消所有選定的活動。

- 如果找到 5,000 個結果，您可能可以假設有超過 5,000 個符合搜尋準則的結果。 您可以縮小搜尋準則的範圍，並重新執行搜尋以傳回更少的結果，或者也可以選取 **[匯出結果]** \> **[下載所有結果]**，以匯出所有搜尋結果。

### <a name="step-2-view-the-search-results"></a>步驟 2：檢視搜尋結果

稽核記錄搜尋的結果會顯示在 **[稽核記錄搜尋]** 頁面的 **[結果]** 底下。 如先前所述，系統最多可顯示 5,000 個 (最新) 事件，每向下捲動一次則可顯示 150 個事件。 若要顯示更多事件，您可以在 **[結果]** 窗格中使用捲軸列，或按 **Shift + End** 顯示後續 150 個事件。

結果會包含搜尋所傳回之每個事件的下列相關資訊：

- **日期**：事件發生時的日期和時間 (以當地時間顯示)。

- **IP 位址：** 記錄活動時所使用的裝置之 IP 位址。 IP 位址會以 IPv4 或 IPv6 位址格式顯示。

   > [!NOTE]
  > 針對某些服務，此欄位中顯示的值可能是代表使用者呼叫服務的受信任應用程式 (例如 Office 網頁版應用程式) 的 IP 位址，而不是執行活動的人員使用之裝置的 IP 位址。 此外，針對 Azure Active Directory 相關事件的系統管理員活動 (或由系統帳戶執行的活動)，不會記錄 IP 位址，且此欄位中顯示的值為 `null`。

- **使用者**：執行動作並觸發事件的使用者 (或服務帳戶)。

- **活動**：使用者執行的活動。 這個值對應您在 **[活動]** 下拉式清單中選取的活動。 若是來自 Exchange 系統管理員稽核記錄的事件，此欄中的這個值則是 Exchange Cmdlet。

- **項目**：已建立或修改為對應活動結果的物件。 例如，已檢視或修改的檔案或已更新的使用者帳戶。 並非所有活動在此資料行中都具有值。

- **詳細資料**：有關活動的其他詳細資訊。 同樣地，並非所有活動都會有值。

> [!TIP]
> 按一下 **[結果]** 底下的欄標頭以將結果排序。 您可以將結果排序為由 A 至 Z 或由 Z 至 A。按一下 **[日期]** 標頭以將結果排序為由最舊至最新或由最新至最舊。

#### <a name="view-the-details-for-a-specific-event"></a>檢視特定事件的詳細資料

您可以按一下搜尋結果清單中的事件記錄，以檢視更多事件相關的詳細資料。 含有事件記錄中詳細屬性的 **[詳細資料]** 頁面隨即顯示。 顯示的屬性視發生事件的服務而定。 若要顯示這些詳細資料，請按一下 **[更多資訊]**。 如需說明，請參閱[稽核記錄中的詳細屬性](detailed-properties-in-the-office-365-audit-log.md)。

![按一下 [更多資訊] 以檢視稽核記錄事件記錄的詳細屬性。](../media/6df582ae-d339-4735-b1a6-80914fb77a08.png)

### <a name="step-3-filter-the-search-results"></a>步驟 3：篩選搜尋結果

除了排序，您也可以篩選稽核記錄搜尋的結果。 這是一個可協助您快速篩選特定使用者或活動結果的絕佳功能。 您一開始可以建立廣泛的搜尋，然後再快速篩選結果以查看特定事件。 接著，您可以縮小搜尋準則的範圍，然後重新執行搜尋以傳回一組更小、更精簡的結果。

若要篩選結果：

1. 執行稽核記錄搜尋。

2. 當顯示結果時，按一下 **[篩選結果]**。

   關鍵字方塊隨即顯示在每個欄標頭底下。

3. 按一下欄標頭底下的其中一個方塊，然後輸入字詞或片語 (視您正在篩選的欄而定)。 結果將動態重新調整為顯示與您的篩選相符之事件。

   ![在篩選中輸入一個單字以顯示符合篩選的事件](../media/542dc323-a997-402c-934b-cc5e218e50bc.png)

4. 若要清除篩選，請按一下篩選方塊中的 **[X]**，或按一下 **[隱藏篩選]**。

> [!TIP]
> 若要顯示來自 Exchange 系統管理員稽核記錄的事件，請在 **[活動]** 篩選方塊中輸入 **-** (破折號)。 這會顯示那些顯示於 Exchange 系統管理員事件 **[活動]** 欄中的 Cmdlet 名稱。 接著，您可以將 Cmdlet 名稱依字母順序排序顯示。

### <a name="step-4-export-the-search-results-to-a-file"></a>步驟 4：將搜尋結果匯出至檔案

您可以將稽核記錄搜尋的結果匯出至您本機電腦上的逗點分隔值 (CSV) 檔案。 您可以在 Microsoft Excel 中開啟此檔案，並使用搜尋、排序、篩選，以及將單一欄 (含有多重屬性) 分割為多個欄等功能。

1. 執行稽核記錄搜尋，然後修改搜尋準則，直到您獲得想要的結果為止。

2. 按一下 **[匯出結果]**，然後選取下列其中一個選項：

   - **儲存載入的結果**：選擇此選項以僅匯出顯示在 **[稽核記錄搜尋]** 頁面 **[結果]** 底下的項目。 下載的 CSV 檔案會包含與頁面上顯示相同的欄 (及資料) (日期、使用者、活動、項目及詳細資料)。 CSV 檔案中包括一個額外的欄 (命名為 **[更多]**)，其中含有更多來自稽核記錄項目的資訊。 因為您正在匯出 **[稽核記錄搜尋]** 頁面上所載入的相同結果 (且可檢視)，因此最多可匯出 5,000 個項目。

   - **下載所有結果**：選擇此選項，可從符合搜尋準則的稽核記錄中匯出所有項目。 針對大量的搜尋結果，選擇此選項除了會下載 **[稽核記錄搜尋]** 頁面上顯示的 5,000 個稽核記錄以外，還會從稽核記錄下載所有項目。 此選項會從稽核記錄下載原始資料至 CSV 檔案，並且在一個命名為 **AuditData** 的欄中包含來自稽核記錄項目的其他資訊。 如果您選擇此匯出選項，下載檔案可能需要較久的時間。這是因為如果您選擇其他選項，檔案可能會遠大於下載的檔案。

     > [!IMPORTANT]
     > 您可以從單一稽核記錄搜尋下載最多 50,000 個項目至 CSV 檔案。 如果已下載 50,000 個項目至 CSV 檔案，您可能可以假設有超過 50,000 個符合搜尋準則的事件。 若要匯出的內容超過此限制，請嘗試使用日期範圍來縮小稽核記錄項目的數量。 您可能需要使用較小的日期範圍執行多次搜尋，以匯出 50,000 個以上的項目。

3. 選取匯出選項後，視窗底部就會顯示一則訊息，提示您開啟 CSV 檔案、將它儲存至 [下載] 資料夾，或將它儲存至特定資料夾。

#### <a name="more-information-about-exporting-and-viewing-audit-log-search-results"></a>有關匯出及檢視稽核記錄搜尋結果的更多資訊

- 如果您下載所有搜尋結果，CSV 檔案會包含一個命名為 **AuditData** 的欄，其中含有每個事件相關的其他資訊。 此欄資料包含的 JSON 物件具有稽核記錄中的多個屬性。 JSON 物件中的每個「屬性：值」配對都會以逗號分隔。 您可以在 Excel 的 Power Query 編輯器中使用 JSON 轉換工具，將 **AuditData** 欄分割成多個欄，好讓 JSON 物件中的每個屬性都有自己的欄。 這樣您就可以排序及篩選一或多個屬性。 如需使用 Power Query 編輯器轉換 JSON 物件的逐步指示，請參閱[匯出、設定及檢視稽核記錄檔的記錄](export-view-audit-log-records.md)。

  分割 [AuditData] 欄後，您可以在 [作業] 欄篩選，以顯示特定活動類型的詳細屬性。

- [下載所有結果] 選項會將稽核記錄中的原始資料下載至 CSV 檔案。 如果您選取 [儲存載入的結果] 選項，此檔案會包含與下載檔案不同的欄名稱 (CreationDate、UserIds、Operation、AuditData)。 在兩個不同的 CSV 檔案中，相同活動的值可能也會不一樣。 例如，CSV 檔案 [動作] 欄中的活動，以及可能會有與 [稽核記錄搜尋] 頁面的 [活動] 欄中顯示的「使用者易記」名稱不同的值。 例如，「MailboxLogin」與「使用者已登入信箱」。

- 當您從搜尋查詢下載所有結果時，如果搜尋查詢包含不同服務中的事件，則 CSV 檔案中的 [AuditData] 欄會包含不同的屬性，視在何種服務中執行動作而定。 例如，來自 Exchange 和 Azure AD 稽核記錄的項目包括命名為 **ResultStatus** 的屬性，它會指出執行的動作是否成功。 SharePoint 中的事件不包括此屬性。 同樣地，SharePoint 事件有一個屬性可用來識別網站 URL 中的檔案和資料夾相關活動。 若要減少此行為，請考慮使用不同的搜尋，以匯出來自單一服務的活動結果。

  如需下載所有結果時，CSV 檔案 [AuditData] 欄中列出的多個屬性描述，以及各個適用的服務，請參閱[稽核記錄中的詳細屬性](detailed-properties-in-the-office-365-audit-log.md)。

## <a name="audited-activities"></a>已稽核活動

本節中各表格說明的是 Office 365 中已稽核的活動。 您可以透過搜尋安全性與合規性中心中的稽核記錄來搜尋這些事件。

這些表格會將相關或來自特定服務的活動集合成一個群組。 這些表格包括 [活動] 下拉式清單中顯示的易記名稱，以及在稽核記錄詳細資訊中，或匯出搜尋結果時在 CSV 檔案中顯示的對應作業名稱。 如需詳細資訊的說明，請參閱[稽核記錄中的詳細屬性](detailed-properties-in-the-office-365-audit-log.md)。

請按一下下列其中一個連結，以移至特定表格。

:::row:::
    :::column:::
        [檔案和頁面活動](#file-and-page-activities)
    :::column-end:::
    :::column:::
        [資料夾活動](#folder-activities)
    :::column-end:::
    :::column:::
        [SharePoint 清單活動](#sharepoint-list-activities)
    :::column-end:::
:::row-end:::

:::row:::
    :::column:::
        [共用及存取要求活動](#sharing-and-access-request-activities)
    :::column-end:::
    :::column:::
        [同步處理活動](#synchronization-activities)
    :::column-end:::
    :::column:::
        [網站權限活動](#site-permissions-activities)
    :::column-end:::
:::row-end:::

:::row:::
    :::column:::
        [網站管理活動](#site-administration-activities)
    :::column-end:::
    :::column:::
        [Exchange 信箱活動](#exchange-mailbox-activities)
    :::column-end:::
    :::column:::
        [使用者管理活動](#user-administration-activities)
    :::column-end:::
:::row-end:::

:::row:::
    :::column:::
        [Azure AD 群組管理活動](#azure-ad-group-administration-activities)
    :::column-end:::
    :::column:::
        [應用程式管理活動](#application-administration-activities)
    :::column-end:::
    :::column:::
        [角色管理活動](#role-administration-activities)
    :::column-end:::
:::row-end:::

:::row:::
    :::column:::
        [目錄管理活動](#directory-administration-activities)
    :::column-end:::
    :::column:::
        [電子文件探索活動](#ediscovery-activities)
    :::column-end:::
    :::column:::
        [進階電子文件探索活動](#advanced-ediscovery-activities)
    :::column-end:::
:::row-end:::

:::row:::
    :::column:::
        [Power BI 活動](#power-bi-activities)
    :::column-end:::
    :::column:::
        [Microsoft 工作場所分析](#workplace-analytics-activities)
    :::column-end:::
    :::column:::
        [Microsoft Teams 活動](#microsoft-teams-activities)
    :::column-end:::
:::row-end:::

:::row:::
    :::column:::
        [Microsoft Teams 醫療保健活動](#microsoft-teams-healthcare-activities)
    :::column-end:::
    :::column:::
        [Microsoft Teams 班次活動](#microsoft-teams-shifts-activities)
    :::column-end:::
    :::column:::
        [Yammer 活動](#yammer-activities)
    :::column-end:::
:::row-end:::

:::row:::
    :::column:::
        [Microsoft Power Automate 活動](#microsoft-power-automate-activities)
    :::column-end:::
    :::column:::
        [Microsoft Power Apps 活動](#microsoft-power-apps-activities)
    :::column-end:::
    :::column:::
        [Microsoft Stream 活動](#microsoft-stream-activities)
    :::column-end:::
:::row-end:::

:::row:::
    :::column:::
        [內容總管活動](#content-explorer-activities)
    :::column-end:::
    :::column:::
        [隔離活動](#quarantine-activities)
    :::column-end:::
    :::column:::
        [Microsoft Teams 活動](#microsoft-forms-activities)
    :::column-end:::
:::row-end:::

:::row:::
    :::column:::
        [敏感度標籤活動](#sensitivity-label-activities)
    :::column-end:::
    :::column:::
        [保留原則和保留標籤活動](#retention-policy-and-retention-label-activities)
    :::column-end:::
    :::column:::
        [簡報電子郵件活動](#briefing-email-activities)
    :::column-end:::
:::row-end:::

:::row:::
    :::column:::
        [MyAnalytics 活動](#myanalytics-activities)
    :::column-end:::
    :::column:::
        [資訊屏障活動](#information-barriers-activities)
    :::column-end:::
    :::column:::
        [Exchange 系統管理員活動](#exchange-admin-audit-log)
    :::column-end:::
:::row-end:::

### <a name="file-and-page-activities"></a>檔案和頁面活動

下表說明 SharePoint Online 和商務用 OneDrive 的檔案和頁面活動。

|易記名稱|作業|描述|
|:-----|:-----|:-----|
|已存取檔案|FileAccessed|使用者或系統帳戶存取檔案。|
|(無)|FileAccessedExtended|這與「已存取檔案」(FileAccessed) 活動相關聯。當相同人員持續存取某個檔案一段時間 (最多 3 小時)，便會記錄 FileAccessedExtended 事件。 <br/><br/> 記錄 FileAccessedExtended 事件的目的在於減少持續存取某個檔案時，記錄 FileAccessed 事件的數目。 這有助於減少多個 FileAccessed 記錄的干擾，以了解哪些基本上是同樣的使用者活動，並讓您專注在初始 (且更重要的) FileAccessed 事件。|
|已變更檔案的保留標籤|ComplianceSettingChanged|保留標籤已在文件中套用或移除。 手動或自動將保留標籤套用到郵件時就會觸發此事件。|
|已將記錄狀態變更為鎖定|LockRecord|將文件歸類為記錄的保留標籤記錄狀態已鎖定。 這表示文件無法修改或刪除。 只有至少獲派網站參與者權限的使用者可以變更文件記錄狀態。|
|已將記錄狀態變更為解除鎖定|UnlockRecord|將文件歸類為記錄的保留標籤記錄狀態已解除鎖定。 這表示文件可修改或刪除。 只有至少獲派網站參與者權限的使用者可以變更文件記錄狀態。|
|已簽入檔案|FileCheckedIn|使用者簽入他們從文件庫簽出的文件。|
|已簽出檔案|FileCheckedOut|使用者簽出位於文件庫中的文件。使用者可以簽出及變更與他們共用的文件。|
|已複製檔案|FileCopied|使用者複製網站中的文件。已複製的檔案可以儲存至該網站上的其他資料夾。|
|已刪除檔案|FileDeleted|使用者刪除網站中的文件。|
|已刪除資源回收筒中的檔案|FileDeletedFirstStageRecycleBin|使用者從網站的資源回收筒中刪除檔案。|
|已刪除第二階段資源回收筒中的檔案|FileDeletedSecondStageRecycleBin|使用者從網站的第二階段資源回收筒中刪除檔案。|
|標示為記錄的已刪除檔案|RecordDelete|已刪除標示為記錄的文件或郵件。 將會把項標示為記錄的保留標籤套用至項時，就會將項目視為記錄。|
|偵測到的文件敏感度不相符|DocumentSensitivityMismatchDetected|使用者將文件上傳到受敏感度標籤保護的網站，且文件的敏感度標籤優先於網站的敏感度標籤。 例如，套用「機密」標籤的文件上傳到套用「一般」標籤的網站。 <br/><br/> 如果文件套用的敏感度標籤，其優先順序低於網站所套用的敏感度標籤，則不會觸發此事件。 例如，套用「一般」標籤的文件上傳到標記為「機密」的網站。 如需敏感度標籤優先順序的詳細資訊，請參閱[標籤優先順序 (順序很重要)](sensitivity-labels.md#label-priority-order-matters)。|
|在檔案中偵測到惡意程式碼|FileMalwareDetected|SharePoint 防毒引擎在檔案中偵測到惡意程式碼。|
|已捨棄檔案簽出|FileCheckOutDiscarded|使用者捨棄 (或復原) 已簽出的檔案。這表示會捨棄使用者在簽出時對檔案所做的任何變更，而且不會儲存至文件庫中的文件版本。|
|下載的檔案|FileDownloaded|使用者從網站下載文件。|
|已修改檔案|FileModified|使用者或系統帳戶修改網站上的文件內容或屬性。|
|(無)|FileModifiedExtended|這與「已修改檔案」(FileModified) 活動相關聯。 當相同人員持續修改某個檔案一段時間 (最多 3 小時)，便會記錄 FileModifiedExtended 事件。 <br/><br/> 記錄 FileModifiedExtended 事件的目的在於減少持續修改某個檔案時，記錄 FileModified 事件的數目。 這有助於減少多個 FileModified 記錄的干擾，以了解哪些基本上是同樣的使用者活動，並讓您專注在初始 (且更重要的) FileModified 事件。|
|已移動檔案|FileMoved|使用者將文件從它在網站上目前的位置移動至新的位置。|
|(無)|FilePreviewed|使用者預覽 SharePoint 或商務用 OneDrive 網站上的檔案。 這些事件通常發生在單一活動中有龐大數量時，例如檢視影像資源庫。|
|已執行的搜尋查詢|SearchQueryPerformed|使用者或系統帳戶在 SharePoint 或商務用 OneDrive 中執行搜尋。 在服務帳戶執行搜尋查詢的一些常見案例，包含將電子文件探索保留和保留原則套用至網站和 OneDrive 帳戶，以及將保留或敏感度標籤自動套用至網站內容。|
|已回收所有檔案次要版本|FileVersionsAllMinorsRecycled|使用者從檔案的版本歷程記錄中刪除所有的次要版本。 已刪除的版本會移至網站資源回收筒。|
|已回收所有檔案版本|FileVersionsAllRecycled|使用者從檔案版本歷程記錄中刪除所有版本。 已刪除的版本會移至網站資源回收筒。|
|已回收檔案版本|FileVersionRecycled|使用者從檔案版本歷程記錄中刪除版本。 已刪除的版本會移至網站資源回收筒。|
|已重新命名檔案|FileRenamed|使用者重新命名網站上的文件。|
|已還原檔案|FileRestored|使用者從網站的資源回收筒還原文件。|
|已上傳檔案|FileUploaded|使用者將文件上傳至網站上的資料夾。|
|已檢視頁面|PageViewed|使用者檢視網站上的檔案。 這不包括使用網頁瀏覽器檢視文件庫中的檔案。|
|(無)|PageViewedExtended|這與「已檢視頁面」(PageViewed) 活動相關聯。 當相同人員持續檢視某個網頁一段時間 (最多 3 小時)，便會記錄 PageViewedExtended 事件。 <br/><br/> 記錄 PageViewedExtended 事件的目的在於減少持續檢視某個頁面時，記錄 PageViewed 事件的數目。 這有助於減少多個 PageViewed 記錄的干擾，以了解哪些基本上是同樣的使用者活動，並讓您專注在初始 (且更重要的) PageViewed 事件。|
|用戶端發出的檢視訊號|ClientViewSignaled|使用者的用戶端 (例如網站或行動應用程式) 已發出訊號，指出使用者已檢視指示的頁面。 此活動通常會在頁面的 PagePrefetched 事件之後進行記錄。 <br/><br/>**請注意**：由於 ClientViewSignaled 事件會由用戶端發出訊號，而不是由伺服器，所以伺服器可能不會記錄事件，因此事件可能也不會出現在稽核記錄中。 稽核記錄中的資訊也可能不可靠。 不過，因為用來建立訊號的權杖會驗證使用者的身分識別，因此對應稽核記錄中所列的使用者身分識別會是正確的。 |
|(無)|PagePrefetched|使用者的用戶端 (例如網站或行動應用程式) 已要求指示的頁面在使用者瀏覽至此時，協助改善效能。 記錄此事件的目的是指出頁面內容已對使用者的用戶端提供服務。 此事件並非明確指示使用者已瀏覽到此頁面。 <br/><br/> 當用戶端呈現頁面內容時 (根據使用者的要求)，應該會隨即產生 ClientViewSignaled 事件。 並非所有用戶端都支援指出預先擷取活動，因此某些預先擷取的活動可能會記錄為 PageViewed 事件。|
||||

#### <a name="frequently-asked-questions-about-fileaccessed-and-filepreviewed-events"></a>FileAccessed 和 FilePreviewed 事件的常見問題集

**任何非使用者事件是否能觸發包含使用者代理程式 (如 "OneDriveMpc-Transform_Thumbnail") 的 FilePreviewed 稽核記錄？**

我們不知道有什麼案例可使得非使用者動作產生類似這樣的事件。 開啟使用者個人檔案卡片 (在 Outlook 網頁版的郵件中按一下其名稱或電子郵件地址) 之類的使用者動作會產生類似事件。

**對 OneDriveMpc-Transform_Thumbnail 的呼叫是否一律為使用者故意觸發？**

不是。 但類似事件可能由於瀏覽器預先擷取而加以記錄。

**如果我們看到來自 Microsoft 註冊 IP 位址的 FilePreviewed 事件，則表示該預覽已在使用者裝置的螢幕上顯示了嗎？**

不是。 該事件可能由於瀏覽器預先擷取而加以記錄。

**是否有使用者預覽文件會產生 FileAccessed 事件的案例？**

FilePreviewed 和 FileAccessed 事件都表示使用者的呼叫導致讀取檔案 (或讀取檔案的縮圖呈現)。 雖然這些事件旨在配合預覽與存取意圖，但事件差異並非使用者意圖的保證。

#### <a name="the-appsharepoint-user-in-audit-records"></a>稽核記錄中的 app\@sharepoint 使用者

在部分檔案活動 (以及其他 SharePoint 相關活動) 的稽核記錄中，您可能會注意到執行活動的使用者 ([User] 和 [UserId] 欄位中識別) 為 app@sharepoint。 這表示執行活動的「使用者」是應用程式。 在此情況下，應用程式會獲授與 SharePoint 中的權限，以代表使用者、系統管理員或服務執行整個組織的動作 (例如搜尋 SharePoint 網站或 OneDrive 帳戶)。 這種將權限授與應用程式的程序稱為 *僅限 SharePoint 應用程式* 存取權。 這表示向 SharePoint 呈現，可執行動作的驗證是由應用程式 (而不是使用者) 所建立。 這就是在特定稽核記錄中識別 app@sharepoint 使用者的原因。 如需詳細資訊，請參閱[授與使用僅限 SharePoint 應用程式的存取權](/sharepoint/dev/solution-guidance/security-apponly-azureacs) \(英文\)。

例如，app@sharepoint 通常會標示為「執行搜尋查詢」和「存取檔案」事件的使用者。 這是因為當您將保留原則套用至網站和 OneDrive 帳戶時，組織中擁有僅限 SharePoint 應用程式存取權的應用程式會執行搜尋查詢和存取檔案。

以下是一些其他案例，其中 app@sharepoint 在稽核記錄中可能會識別為執行活動的使用者：

- Microsoft 365 群組。 當使用者或系統管理員建立新群組時，系統會產生稽核記錄，以建立網站集合、更新清單，以及將成員新增至 SharePoint 群組。 這些工作是應用程式代表建立群組的使用者執行的。

- Microsoft Teams。與 Microsoft 365 群組類似，建立新小組時，系統會產生稽核記錄，以建立網站集合、更新清單，以及將成員新增至 SharePoint 群組。

- 合規性功能。 當系統管理員實作合規性功能時，例如保留原則、電子文件探索保留及自動套用靈敏度標籤。

在這些及其他案例中，您也會注意到以 app@sharepoint 作為指定之使用者的稽核記錄是在短時間內建立的，彼此之間的間隔通常為幾秒鐘。 這也表示這些稽核記錄可能是由相同使用者啟動的工作所觸發。 此外，稽核記錄中的 [ApplicationDisplayName] 和 [EventData] 欄位可協助您識別觸發此事件的案例或應用程式。

### <a name="folder-activities"></a>資料夾活動

下表說明 SharePoint Online 和商務用 OneDrive 的資料夾活動。 如先前所述，某些 SharePoint 活動的稽核記錄將會指出 app@sharepoint 使用者代表啟動動作的使用者或系統管理員執行了動作。 如需詳細資訊，請參閱[稽核記錄中的 app\@sharepoint 使用者](#the-appsharepoint-user-in-audit-records)。

|易記名稱|作業|描述|
|:-----|:-----|:-----|
|已複製資料夾|FolderCopied|使用者從網站複製資料夾至 SharePoint 或商務用 OneDrive 中的另一個位置。|
|已建立資料夾|FolderCreated|使用者在網站上建立資料夾。|
|已刪除資料夾|FolderDeleted|使用者刪除網站上的資料夾。|
|已刪除資源回收筒中的資料夾|FolderDeletedFirstStageRecycleBin|使用者從網站的資源回收筒中刪除資料夾。|
|已刪除第二階段資源回收筒中的資料夾|FolderDeletedSecondStageRecycleBin|使用者從網站的第二階段資源回收筒中刪除資料夾。|
|已修改資料夾|FolderModified|使用者修改網站上的資料夾。 這包括變更資料夾的中繼資料，例如變更標籤和屬性。|
|已移動資料夾|FolderMoved|使用者將資料夾移動至網站上的其他位置。|
|已重新命名資料夾|FolderRenamed|使用者在網站上重新命名資料夾。|
|已還原資料夾|FolderRestored|使用者從網站的資源回收筒中還原已刪除的資料夾。|
||||

### <a name="sharepoint-list-activities"></a>SharePoint 清單活動

下表說明使用者在 SharePoint Online 中與清單和清單項目互動時的相關活動。 如先前所述，某些 SharePoint 活動的稽核記錄將會指出 app@sharepoint 使用者代表啟動動作的使用者或系統管理員執行了動作。 如需詳細資訊，請參閱[稽核記錄中的 app\@sharepoint 使用者](#the-appsharepoint-user-in-audit-records)。

|易記名稱|作業|描述|
|:-----|:-----|:-----|
|已建立清單|ListCreated|使用者已建立 SharePoint 清單。|
|已建立清單欄|ListColumnCreated|使用者已建立 SharePoint 清單欄。 清單欄是連結至一個或多個 SharePoint 清單的欄位。|
|已建立清單內容類型|ListContentTypeCreated|使用者已建立清單內容類型。 清單內容類型是連結至一個或多個 SharePoint 清單的內容類型。|
|已建立清單項目|ListItemCreated|使用者已在現有的 SharePoint 清單中建立項目。|
|已建立網站欄|SiteColumnCreated|使用者已建立 SharePoint 網站欄。 網站欄是未連結到清單的欄位。 網站欄也是可由指定網頁中任何清單使用的中繼資料結構。|
|已建立網站內容類型|Site ContentType Created|使用者已建立網站內容類型。 網站內容類型是會連結到上層網站的內容類型。|
|已刪除清單|ListDeleted|使用者已刪除 SharePoint 清單。|
|已刪除清單欄|清單欄已刪除|使用者已刪除 SharePoint 清單欄。|
|已刪除清單內容類型|ListContentTypeDeleted|使用者已刪除清單內容類型。|
|已刪除清單項目|清單項目已刪除|使用者已刪除 SharePoint 清單項目。|
|已刪除網站欄|SiteColumnDeleted|使用者已刪除 SharePoint 網站欄。|
|已刪除網站內容類型|SiteContentTypeDeleted|使用者已刪除網站內容類型。|
|已回收清單項目|ListItemRecycled|使用者已將 SharePoint 清單項目移至資源回收筒。|
|已還原清單|ListRestored|使用者已從資源回收筒還原 SharePoint 清單。|
|已還原清單項目|ListItemRestored|使用者已從資源回收筒還原 SharePoint 清單項目。|
|已更新清單|ListUpdated|使用者已修改一個或多個屬性來更新 SharePoint 清單。|
|已更新清單欄|ListColumnUpdated|使用者已修改一個或多個屬性來更新 SharePoint 清單欄。|
|已更新清單內容類型|ListContentTypeUpdated|使用者已修改一個或多個屬性來更新清單內容類型。|
|已更新清單項目|ListItemUpdated|使用者已修改一個或多個屬性來更新 SharePoint 清單項目。|
|已更新網站欄|SiteColumnUpdated|使用者已修改一個或多個屬性來更新 SharePoint 網站欄。|
|已更新網站內容類型|SiteContentTypeUpdated|使用者已修改一個或多個屬性來更新網站內容類型。|
||||

### <a name="sharing-and-access-request-activities"></a>共用及存取要求活動

下表說明 SharePoint Online 和商務用 OneDrive 中的使用者共用和存取要求活動。 針對共用事件，[結果] 底下的 [詳細資料] 欄會識別共用項目的使用者或群組名稱，以及使用者或群組是否為您的組織中的成員或來賓。 如需詳細資訊，請參閱[在稽核記錄中使用共用稽核](use-sharing-auditing.md)。

> [!NOTE]
> 根據使用者物件的 UserType 屬性，使用者可以是成員或來賓。 成員通常是員工，而來賓通常是您的組織之外的共同作業者。 當使用者接受共用邀請時 (而且不屬於您的組織的一部分)，就會在您的組織目錄中為他們建立使用者帳戶。 一旦來賓使用者在您的目錄中擁有帳戶後，就可以直接與他們共用資源 (而不需要邀請)。

|易記名稱|作業|描述|
|:-----|:-----|:-----|
|已將權限等級新增至網站集合|PermissionLevelAdded|權限等級已新增至網站集合。|
|已接受存取要求|AccessRequestAccepted|已接受網站、資料夾或文件的存取要求，而提出要求的使用者已獲授與存取權。|
|已接受共用邀請|SharingInvitationAccepted|使用者 (成員或來賓) 已接受共用邀請，並獲授與資源的存取權。 此事件包括受邀的使用者，以及用來接受邀請的電子郵件地址 (它們可能不同) 之相關資訊。 此活動通常伴隨第二個事件，描述使用者如何獲授與資源的存取權。例如，將使用者新增至擁有資源存取權的群組。|
|已封鎖的共用邀請|SharingInvitationBlocked|貴組織使用者所傳送的共用邀請遭到封鎖，因為外部共用原則會根據目標使用者的網域允許或拒絕外部共用。在此案例中，共用邀請因下列原因而遭到封鎖： <br/> 允許的網域清單中不包含目標使用者的網域。 <br/> 或者 <br/> 封鎖的網域清單中包含目標使用者的網域。 <br/> 如需根據網域允許或封鎖外部共用的詳細資訊，請參閱[在 SharePoint Online 和商務用 OneDrive 中限制網域共用](/sharepoint/restricted-domains-sharing)。|
|已建立存取要求|AccessRequestCreated|使用者要求他們未擁有存取權限的網站、資料夾或文件之存取權。|
|已建立公司可共用連結|CompanyLinkCreated|使用者已建立資源的全公司連結。 全公司連結只能讓您組織中的成員使用。 來賓無法使用這些連結。|
|已建立匿名連結|AnonymousLinkCreated|使用者已建立資源的匿名連結。 任何人只要有此連結就可以存取資源，而不需要驗證。|
|已建立安全連結|SecureLinkCreated|已對此項目建立安全共用連結。|
|已建立共用邀請|SharingInvitationCreated|使用者與並非您組織目錄中的使用者共用 SharePoint Online 或商務用 OneDrive 中的資源。|
|已刪除安全連結|SecureLinkDeleted|安全共用連結已刪除。|
|已拒絕存取要求|AccessRequestDenied|已拒絕網站、資料夾或文件的存取要求。|
|已移除公司可共用連結|CompanyLinkRemoved|使用者已移除資源的全公司連結。 無法再使用此連結存取資源。|
|已移除匿名連結|AnonymousLinkRemoved|使用者已移除資源的匿名連結。 無法再使用此連結存取資源。|
|已共用的檔案、資料夾或網站|SharingSet|使用者 (成員或來賓) 已與並非您的組織目錄中的使用者共用 SharePoint 或商務用 OneDrive 中的檔案、資料夾或網站。 此活動的 [詳細資料] 欄中的值會識別已共用資源的使用者名稱，以及該使用者是否為成員或來賓。 <br/><br/> 此活動通常伴隨第二個事件，描述使用者如何獲授與資源的存取權。例如，將使用者新增至擁有資源存取權的群組。|
|已更新存取要求|AccessRequestUpdated|已更新項目的存取要求。|
|已更新匿名連結|AnonymousLinkUpdated|使用者已更新資源的匿名連結。 當您匯出搜尋結果時，EventData 屬性中會包括更新的欄位。|
|已更新共用邀請|SharingInvitationUpdated|已更新外部共用邀請。|
|已使用匿名連結|AnonymousLinkUsed|匿名使用者已使用匿名連結來存取資源。 使用者可能是未知的身分，但您可以取得其他詳細資料，例如使用者的 IP 位址。|
|已取消共用檔案、資料夾或網站|SharingRevoked|使用者 (成員或來賓) 已取消共用先前與另一個使用者共用的檔案、資料夾或網站。|
|已使用公司可共用連結|CompanyLinkUsed|使用者已使用全公司連結來存取資源。|
|已使用安全連結|SecureLinkUsed|使用者已使用安全連結。|
|使用者已新增至安全連結|AddedToSecureLink|使用者已新增至可使用安全共用連結的實體清單。|
|使用者已從安全連結中移除|RemovedFromSecureLink|使用者已從可使用安全共用連結的實體清單中移除。|
|已撤回共用邀請|SharingInvitationRevoked|使用者已撤回資源的共用邀請。|
||||

### <a name="synchronization-activities"></a>同步處理活動

下表列出 SharePoint Online 和商務用 OneDrive 中的檔案同步活動。

|易記名稱|作業|描述|
|:-----|:-----|:-----|
|已允許電腦同步處理檔案|ManagedSyncClientAllowed|使用者與網站成功建立同步處理關聯性。 同步關係成功，因為使用者的電腦是已新增至網域清單之網域的成員 (稱為「安全收件者清單」)，可以存取您的組織中的文件庫。 <br/><br/> 如需有關此功能的詳細資訊，請參閱[使用 Windows PowerShell Cmdlet 為安全收件者清單上的網域啟用 OneDrive 同步](/powershell/module/sharepoint-online/)。|
|已阻擋電腦同步處理檔案|UnmanagedSyncClientBlocked|使用者嘗試與網站建立同步關聯性，但作為連線來源的電腦並非您組織網域的成員或是未加入網域清單 (也稱為安全收件者清單) 中的網域成員，加入此清單者才可存取您組織中的文件庫。 不允許同步關係，並且禁止使用者的電腦同步、下載或上傳文件庫的檔案。 <br/><br/> 如需此功能的相關資訊，請參閱[使用 Windows PowerShell Cmdlet 為安全收件者清單上的網域啟用 OneDrive 同步](/powershell/module/sharepoint-online/)。|
|已下載檔案至電腦|FileSyncDownloadedFull|使用者建立同步處理關聯性，且初次從文件庫成功下載檔案至電腦。|
|已下載檔案變更至電腦|FileSyncDownloadedPartial|使用者從文件庫成功下載任何檔案變更。 此活動表示，對文件庫中檔案所做的任何變更都已下載至使用者的電腦。 因為使用者之前已下載文件庫，所以只會下載變更 (如 [已下載檔案至電腦]**** 活動所指出)。|
|已下載檔案至文件庫|FileSyncUploadedFull|使用者建立同步處理關聯性，且初次從電腦成功上傳檔案至文件庫。|
|已上傳檔案變更至文件庫|FileSyncUploadedPartial|使用者成功上傳變更至文件庫中的檔案。 此事件表示，對來自文件庫的本機版本檔案所做的任何變更已成功上傳至文件庫。 因為使用者之前已上傳這些檔案 (如 [已上傳檔案至文件庫] 活動所指出)，所以只會上傳變更。|
||||

### <a name="site-permissions-activities"></a>網站權限活動

下表列出在 SharePoint 中指派權限及使用群組提供 (及撤銷) 網站存取權的相關事件。 如先前所述，某些 SharePoint 活動的稽核記錄將會指出 app@sharepoint 使用者代表啟動動作的使用者或系統管理員執行了動作。 如需詳細資訊，請參閱[稽核記錄中的 app\@sharepoint 使用者](#the-appsharepoint-user-in-audit-records)。

|易記名稱|作業|描述|
|:-----|:-----|:-----|
|已新增網站集合系統管理員|SiteCollectionAdminAdded|網站集合系統管理員或擁有者新增一位人員來作為網站的網站集合管理員。 網站集合系統管理員擁有網站集合及所有子網站的完全控制權限。 當系統管理員讓自己可存取使用者的 OneDrive 帳戶時 (藉由在 SharePoint 系統管理中心編輯使用者設定檔，或[使用 Microsoft 365 系統管理中心](/office365/admin/add-users/get-access-to-and-back-up-a-former-user-s-data))，也會記錄此活動。|
|已將使用者或群組新增至 SharePoint 群組|AddedToGroup|使用者已新增成員或來賓至 SharePoint 群組。 這可能是刻意的動作，或另一個活動的結果 (例如共用事件)。|
|已中斷權限等級繼承|PermissionLevelsInheritanceBroken|項目已變更，因此無法從其上層項目繼承權限等級。|
|已中斷共用繼承|SharingInheritanceBroken|項目已變更，因此無法從其上層項目繼承共用權限。|
|已建立群組|GroupAdded|網站系統管理員或擁有者為網站建立群組，或執行導致建立群組的工作。例如，使用者第一次建立連結以共用檔案時，系統群組會新增至使用者的商務用 OneDrive 網站。此事件也可以是使用者透過編輯權限建立共用檔案的連結之結果。|
|已刪除群組|GroupRemoved|使用者刪除網站中的群組。|
|已修改存取要求設定|WebRequestAccessModified|已在網站上修改存取要求設定。|
|已修改「成員可共用」設定|WebMembersCanShareModified|網站上的「成員可共用」設定已修改。|
|已修改網站集合上的權限等級|PermissionLevelModified|已變更網站集合上的權限等級。|
|已修改網站權限|SitePermissionsModified|網站系統管理員或擁有者 (或系統帳戶) 變更已指派給網站上的群組之權限等級。如果已移除群組中的所有權限，也會記錄此活動。<br/><br/> **請注意**：此作業在 SharePoint Online 中已遭取代。 若要尋找相關事件，您可以搜尋其他權限相關活動，例如 [已新增網站集合管理員]、[已新增使用者或群組到 SharePoint 群組]、[已允許使用者建立群組]、[已建立群組] 及 [已刪除群組]。|
|已移除網站集合上的權限等級|PermissionLevelRemoved|權限等級已從網站集合移除。|
|已移除網站集合系統管理員|SiteCollectionAdminRemoved|網站集合系統管理員或擁有者移除了網站的一位網站集合管理員。 當系統管理員將自己從使用者 OneDrive 帳戶的網站集合系統管理員清單中移除時 (藉由在 SharePoint 系統管理員中心編輯使用者設定檔)，也會記錄此活動。  若要在稽核記錄搜尋結果中傳回此活動，您必須搜尋所有活動。|
|已從 SharePoint 群組中移除使用者或群組|RemovedFromGroup|使用者已移除 SharePoint 群組中的成員或來賓。 這可能是刻意的動作，或另一個活動的結果 (例如取消共用事件)。|
|要求的網站系統管理員權限|SiteAdminChangeRequest|使用者要求新增成為網站集合的網站集合系統管理員。網站集合系統管理員擁有網站集合及所有子網站的完全控制權限。|
|已還原共用繼承|SharingInheritanceReset|項目已變更，因此可從其上層項目繼承共用權限。|
|已更新群組|GroupUpdated|網站系統管理員或擁有者變更網站的群組之設定。這可以包括變更群組的名稱、誰能夠檢視或編輯群組成員資格，以及如何處理成員資格要求。|
||||

### <a name="site-administration-activities"></a>網站管理活動

下表列出 SharePoint Online 中的網站管理工作所產生的事件。 如先前所述，某些 SharePoint 活動的稽核記錄將會指出 app@sharepoint 使用者代表啟動動作的使用者或系統管理員執行了動作。 如需詳細資訊，請參閱[稽核記錄中的 app\@sharepoint 使用者](#the-appsharepoint-user-in-audit-records)。

|易記名稱|作業|描述|
|:-----|:-----|:-----|
|已新增允許的資料位置|AllowedDataLocationAdded|SharePoint 或全域系統管理員已在多地理位置環境中新增允許的資料位置。|
|已新增免除使用者代理程式|ExemptUserAgentSet|SharePoint 或全域系統管理員已將使用者代理程式新增至 SharePoint 系統管理員中心的免除使用者代理程式清單。|
|已新增地理位置系統管理員|GeoAdminAdded|SharePoint 或全域系統管理員已將使用者新增為某個位置的地理位置系統管理員。|
|已允許使用者建立群組|AllowGroupCreationSet|網站系統管理員或擁有者新增權限等級至網站，以允許獲派該權限的使用者為該網站建立群組。|
|已取消網站的地理位置移動|SiteGeoMoveCancelled|SharePoint 或全域系統管理員已成功取消 SharePoint 或 OneDrive 網站的地理位置移動。 多地理位置功能可讓組織橫跨多個 Microsoft 資料中心地理位置，這些地理位置稱為 geos。 如需詳細資訊，請參閱 [OneDrive 和 SharePoint Online 的多地理位置功能](../enterprise/multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md)。|
|已變更共用原則|SharingPolicyChanged|SharePoint 或全域系統管理員已使用 Microsoft 365 系統管理員入口網站、SharePoint 系統管理員入口網站或 SharePoint Online 管理命令介面變更了 SharePoint 共用原則。 將會記錄您的組織中的任何共用原則設定變更。 已變更的原則可在事件記錄詳細屬性中的 **ModifiedProperties** 欄位中找到。|
|已變更裝置存取原則|DeviceAccessPolicyChanged|SharePoint 或全域系統管理員已變更您組織中未受控裝置的原則。 此原則可針對未加入您組織的裝置控制 SharePoint、OneDrive 及 Microsoft 365 的存取權。 設定此原則需要 Enterprise Mobility + Security 訂閱。 如需詳細資訊，請參閱[控制未受管理裝置的存取權](/sharepoint/control-access-from-unmanaged-devices)。|
|已變更免除使用者代理程式|CustomizeExemptUsers|SharePoint 或全域系統管理員已自訂 SharePoint 系統管理中心的免除使用者代理程式清單。您可以指定要免除哪些使用者代理程式，以免於接收整個網頁進行索引。這表示當您已指定為免除的使用者代理程式遇到 InfoPath 表單，該表單將會以 XML 檔案的形式傳回，而不是整個網頁。這樣在進行 InfoPath 表單索引時會更迅速。|
|已變更網路存取原則|NetworkAccessPolicyChanged|SharePoint 或全域系統管理員已在 SharePoint 系統管理員中心中 (或是使用 SharePoint Online PowerShell) 變更位置存取原則 (又稱為受信任的網路邊界)。 此類原則可根據您指定的授權 IP 位址範圍，控制能存取您組織 SharePoint 和 OneDrive 資源的使用者。 如需詳細資訊，請參閱[根據網路位置控制 SharePoint Online 與 OneDrive 資料的存取權](/sharepoint/control-access-based-on-network-location)。|
|已完成網站的地理位置移動|SiteGeoMoveCompleted|已成功完成您組織全域系統管理員所排程的網站地理位置移動。 多地理位置功能可讓組織橫跨多個 Microsoft 資料中心地理位置，這些地理位置稱為 geos。 如需詳細資訊，請參閱 [Office 365 中 OneDrive 和 SharePoint Online 的多地理位置功能](../enterprise/multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md)。|
|已建立 [傳送至] 連線|SendToConnectionAdded|SharePoint 或全域系統管理員在 SharePoint 系統管理中心的 [記錄] 管理頁面上建立新的 [傳送至] 連線。[傳送至] 連線會指定文件存放庫或記錄中心的設定。當您建立 [傳送至] 連線時，[內容組合管理] 可提交文件至指定的位置。|
|已建立網站集合|SiteCollectionCreated|SharePoint 或全域系統管理員在您的 SharePoint Online 組織中建立了網站集合，或是使用者佈建了商務用 OneDrive 網站。|
|刪除孤立的中樞網站|HubSiteOrphanHubDeleted|SharePoint 或全域系統管理員已刪除孤立中樞網站，也就是未與任何站台建立關聯的中樞網站。 孤立中樞可能是因為刪除原始中樞網站所造成。|
|已刪除 [傳送至] 連線|SendToConnectionRemoved|SharePoint 或全域系統管理員在 SharePoint 系統管理員中心的 [記錄] 管理頁面上刪除「傳送至」連線。|
|已刪除網站|SiteDeleted|網站系統管理員刪除網站。|
|已啟用文件預覽|PreviewModeEnabledSet|網站系統管理員啟用網站的文件預覽。|
|已啟用舊版工作流程|LegacyWorkflowEnabledSet|網站管理員或擁有者將 SharePoint 2013 工作流程工作內容類型新增至網站。全域管理員也可以在 SharePoint 系統管理中心啟用整個組織的工作流程。|
|已啟用 Office on Demand|OfficeOnDemandSet|網站管理員啟用 Office on Demand，讓使用者存取最新版本的 Office 桌面應用程式。Office on Demand 是在 SharePoint 系統管理中心啟用，並且需要 Microsoft 365 訂閱，該訂閱包含完整、已安裝的 Office 應用程式。|
|已啟用 [人員搜尋] 的結果來源|PeopleResultsScopeSet|網站系統管理員建立網站的 [人員搜尋] 結果來源。|
|已啟用 RSS 摘要|NewsFeedEnabledSet|網站系統管理員或擁有者啟用網站的 RSS 摘要。全域系統管理員可以在 SharePoint 系統管理中心為整個組織啟用 RSS 摘要。|
|已聯結網站與中樞網站|HubSiteJoined|網站擁有者讓他們的網站與中樞網站互相關聯。|
|已註冊中樞網站|HubSiteRegistered|SharePoint 或全域系統管理員建立了一個中樞網站。 結果是網站會註冊為中樞網站。|
|已移除允許的資料位置|AllowedDataLocationDeleted|SharePoint 或全域系統管理員已在多個地理環境中移除允許的資料位置。|
|已移除地理位置系統管理員|GeoAdminDeleted|SharePoint 或全域系統管理員已移除某個位置的地理位置管理員。|
|已重新命名網站|SiteRenamed|網站系統管理員或擁有者重新命名網站|
|已排程網站的地理位置移動|SiteGeoMoveScheduled|SharePoint 或全域系統管理員已成功排定 SharePoint 或 OneDrive 網站的地理位置移動。 多地理位置功能可讓組織橫跨多個 Microsoft 資料中心地理位置，這些地理位置稱為 geos。 如需詳細資訊，請參閱 [Office 365 中 OneDrive 和 SharePoint Online 的多地理位置功能](../enterprise/multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md)。|
|已設定主機網站|HostSiteSet|SharePoint 或全域系統管理員將指定的網站變更為託管個人或商務用 OneDrive 網站。|
|為地理位置設定儲存空間配額|GeoQuotaAllocated|SharePoint 或全域系統管理員已在多地理位置環境中設定地理位置的儲存空間配額。|
|已解除網站與中樞網站的聯結|HubSiteUnjoined|網站擁有者讓他們的網站與中樞網站解除關聯。|
|取消註冊中樞網站|HubSiteUnregistered|SharePoint 或全域系統管理員取消將網站註冊為中樞網站。 取消註冊中樞網站時，該網站就不再具有中樞網站的功能。|
||||

### <a name="exchange-mailbox-activities"></a>Exchange 信箱活動

下表列出信箱稽核記錄可以記錄的活動。 信箱擁有者、指定使用者或管理員所執行的信箱活動會記錄在稽核記錄中達 90 天。 系統管理員可能會關閉組織中所有使用者的信箱稽核記錄功能。 在此情況下，任何使用者的信箱動作都不會記錄。 如需詳細資訊，請參閱[管理信箱稽核](enable-mailbox-auditing.md)。

 您也可以在 Exchange Online PowerShell 中使用 [Search-MailboxAuditLog](/powershell/module/exchange/search-mailboxauditlog) Cmdlet 來搜尋信箱活動。

|易記名稱|作業|描述|
|:-----|:-----|:-----|
|存取信箱項目|MailItemsAccessed|在信箱中讀取或存取郵件。 可以通過以下兩種方式之一觸發此事件的稽核記錄：當郵件客戶端 (例如 Outlook) 對郵件執行繫結作業時，或者當郵件通訊協定 (例如 Exchange ActiveSync 或 IMAP) 同步郵件文件夾中的項目時。 僅有 Office 365 或 Microsoft 365 E5 授權的使用者可記錄此事件。 在調查遭入侵的電子郵件帳戶時，分析此活動的稽核記錄相當實用。 如需詳細資訊，請參閱[進階稽核](advanced-audit.md#access-to-crucial-events-for-investigations)中的〈存取調查重要事件〉一節。 |
|已新增代理人信箱權限|Add-MailboxPermission|系統管理員已將另一名人員其信箱的 FullAccess 信箱權限指派給某個使用者 (亦稱為「代理人」)。 FullAccess 權限可讓代理人開啟該名人員的信箱，以及讀取和管理信箱的內容。|
|新增或移除具有行事曆資料夾代理人存取權的使用者|UpdateCalendarDelegation|已新增或移除作為另一個使用者信箱行事曆代理人的使用者。 行事曆代理可讓其他有相同組織權限的人來管理信箱擁有者的行事曆。|
|已新增資料夾的權限|AddFolderPermissions|資料夾權限已新增。 資料夾權限可控制組織中的哪些使用者可以存取信箱中的資料夾，以及這些資料夾中的郵件。|
|已複製郵件到另一個資料夾|Copy|郵件已複製到另一個資料夾。|
|建立的信箱項目|建立|在信箱的 [行事曆]、[連絡人]、[記事] 或 [工作] 資料夾中建立了項目。 例如，建立了新的會議邀請。 建立、傳送或接收郵件的動作並不會受到稽核。 此外，建立信箱資料夾的動作也不會受到稽核。|
|在 Outlook Web 應用程式中建立新的收件匣規則|New-InboxRule|信箱擁有者或其他有信箱存取權的使用者在 Outlook Web App 中建立了收件匣規則。|
|已刪除 [刪除的郵件] 資料夾中的郵件|SoftDelete|郵件已永久刪除或從 [刪除的郵件] 資料夾中刪除。 這些項目會移動至 [可復原的項目] 資料夾。 當使用者選取郵件並按 Shift+Delete **** 時，也會將郵件移動至 [可復原的項目] 資料夾。|
|已將郵件標示為記錄|ApplyRecordLabel|郵件已分類為記錄。 將內容歸類為記錄的保留標籤若手動或自動套用到郵件時，就會發生此事件。|
|已複製郵件至另一個資料夾|Move|郵件已移到另一個資料夾。|
|已移動郵件至 [刪除的郵件] 資料夾|MoveToDeletedItems|郵件已遭刪除並移至 [刪除的郵件] 資料夾。|
|已修改資料夾權限|UpdateFolderPermissions|資料夾權限已變更。 資料夾權限可控制組織中的哪些使用者可以存取信箱資料夾和資料夾中的郵件。|
|已從 Outlook Web App 中修改收件匣規則|Set-InboxRule|信箱擁有者或其他有信箱存取權的使用者已使用 Outlook Web App 修改了收件匣規則。|
|已清除信箱中的郵件|HardDelete|已清除 [可復原的項目] 資料夾中的郵件 (從信箱中永久刪除)。|
|已移除代理人信箱權限|Remove-MailboxPermission|系統管理員已將 FullAccess 權限 (先前已指派給代理人) 從人員的信箱移除。 移除 FullAccess 權限後，代理人即無法開啟該名人員的信箱或存取其中的任何內容。|
|已移除資料夾的權限|RemoveFolderPermissions|資料夾權限已移除。 資料夾權限可控制組織中的哪些使用者可以存取信箱中的資料夾，以及這些資料夾中的郵件。|
|傳送郵件|傳送|郵件已傳送、回覆或轉寄。 僅有 Office 365 或 Microsoft 365 E5 授權的使用者可記錄此事件。 如需詳細資訊，請參閱[進階稽核](advanced-audit.md#access-to-crucial-events-for-investigations)中的〈存取調查重要事件〉一節。|
|已使用 [傳送為] 權限傳送郵件|SendAs|已使用 [傳送為] 權限傳送郵件。 這表示，另一個使用者已傳送郵件，就像此郵件是來自信箱擁有者一樣。|
|已使用 [代理傳送者] 權限傳送郵件|SendOnBehalf|已使用 [代理傳送者] 權限傳送郵件。 這表示，另一個使用者已代表信箱擁有者傳送郵件。 此郵件會向收件者指出誰代理傳送郵件，以及實際上是誰傳送郵件。|
|已從 Outlook 用戶端更新收件匣規則|UpdateInboxRules|信箱擁有者或其他有信箱存取權的使用者已在 Outlook 用戶端中修改收件匣規則。|
|已更新郵件|Update|郵件或其屬性已變更。|
|使用者已登入信箱|MailboxLogin|使用者已登入其信箱。|
|將郵件標示為記錄||使用者對電子郵件訊息套用保留標籤，且該標籤已設定為將該項目標示為記錄。 |
||||

### <a name="user-administration-activities"></a>使用者管理活動

下表列出當系統管理員透過 Microsoft 365 系統管理員中心或 Azure 管理入口網站新增或變更使用者帳戶時，會記錄的使用者管理活動。

> [!NOTE]
> 下表的 [作業 **]** 欄中所列的作業名稱包含一個句點 (`.`)。 如果您在搜尋稽核記錄、建立稽核保留原則、建立警示原則或建立活動警示時，於 PowerShell 命令中指定作業，則必須在作業名稱中包括句號。 也請務必使用雙引號 (`" "`) 來含括作業名稱。

|活動|作業|描述|
|:-----|:-----|:-----|
|已新增使用者|新增使用者。|已建立使用者帳戶。|
|已變更使用者授權|變更使用者授權。|指派給使用者的授權已變更。 若要查看哪些授權已變更，請參閱對應的 [更新的使用者]**** 活動。|
|已變更使用者密碼|變更使用者密碼。|使用者變更其密碼。 為了讓使用者能夠重設自己的密碼，您必須為組織中的所有或選取的使用者啟用自助式密碼重設。 您也可以追蹤 Azure Active Directory 中的自助式密碼重設活動。 如需詳細資訊，請參閱 [Azure AD 密碼管理的報告選項](/azure/active-directory/authentication/howto-sspr-reporting)。
|已刪除使用者|刪除使用者。|已刪除使用者帳戶。|
|重設使用者密碼|重設使用者密碼。|系統管理員重設使用者的密碼。|
|已設定強制使用者變更密碼的屬性|設定強制變更使用者密碼。|系統管理員已設定強制使用者在使用者下次登入 Office 365 時變更密碼的屬性。|
|設定授權屬性|設定授權屬性。|系統管理員修改已指派給使用者的授權屬性。|
|已更新使用者|更新使用者。|系統管理員變更使用者帳戶的一個或多個屬性。 如需可更新的使用者屬性清單，請參閱 [Azure Active Directory 稽核報告事件](/azure/active-directory/reports-monitoring/concept-audit-logs)中的＜更新使用者屬性＞一節。|
||||

### <a name="azure-ad-group-administration-activities"></a>Azure AD 群組管理活動

下表列出當系統管理員或使用者建立或變更 Microsoft 365 群組時，或當系統管理員透過 Microsoft 365 系統管理員中心或 Azure 管理入口網站建立安全性群組時，會記錄的群組管理活動。 如需有關 Office 365 中的群組詳細資訊，請參閱[檢視、建立及刪除 Microsoft 365 系統管理員中心的群組](../admin/create-groups/create-groups.md)。

> [!NOTE]
> 下表的 [作業 **]** 欄中所列的作業名稱包含一個句點 (`.`)。 如果您在搜尋稽核記錄、建立稽核保留原則、建立警示原則或建立活動警示時，於 PowerShell 命令中指定作業，則必須在作業名稱中包括句號。 也請務必使用雙引號 (`" "`) 來含括作業名稱。

|易記名稱|作業|描述|
|:-----|:-----|:-----|
|已新增群組|新增群組。|已建立群組。|
|已將成員新增至群組中|將成員新增至群組。|已將成員新增至群組中。|
|已刪除群組|刪除群組。|已刪除群組。|
|已移除群組中的成員|移除群組的成員。|已移除群組中的成員。|
|已更新群組|更新群組。|已變更群組的屬性。|
||||

### <a name="application-administration-activities"></a>應用程式管理活動

下表列出當管理員新增或變更已在 Azure AD 中註冊的應用程式時，會記錄的應用程式系統管理活動。 任何依靠 Azure AD 進行驗證的應用程式都必須在目錄中註冊。

> [!NOTE]
> 下表的 [作業 **]** 欄中所列的作業名稱包含一個句點 (`.`)。 如果您在搜尋稽核記錄、建立稽核保留原則、建立警示原則或建立活動警示時，於 PowerShell 命令中指定作業，則必須在作業名稱中包括句號。 也請務必使用雙引號 (`" "`) 來含括作業名稱。

|易記名稱|作業|描述|
|:-----|:-----|:-----|
|已新增委派項目|新增委派項目。|已對 Azure AD 中的應用程式建立/授與驗證權限。|
|已新增服務主體|新增服務主體。|已在 Azure AD 中註冊應用程式。 應用程式在目錄中是由服務主體代表。|
|已新增認證至服務主體|新增服務主體認證。|已將認證新增至 Azure AD 中的服務主體。 服務主體代表目錄中的應用程式。|
|已移除委派項目|移除委派項目。|已移除 Azure AD 中的應用程式驗證權限。|
|已移除目錄中的服務主體|移除服務主體。|Azure AD 中的應用程式已刪除/移除註冊。 應用程式在目錄中是由服務主體代表。|
|已移除服務主體中的認證|移除服務主體認證。|已從 Azure AD 的服務主體中移除認證。 服務主體代表目錄中的應用程式。|
|設定委派項目|設定委派項目。|已更新 Azure AD 中的應用程式驗證權限。|
||||

### <a name="role-administration-activities"></a>角色管理活動

下表列出當系統管理員在 Microsoft 365 系統管理員中心或 Azure 管理入口網站中管理系統管理員角色時，會記錄的 Azure AD 角色管理活動。

> [!NOTE]
> 下表的 [作業 **]** 欄中所列的作業名稱包含一個句點 (`.`)。 如果您在搜尋稽核記錄、建立稽核保留原則、建立警示原則或建立活動警示時，於 PowerShell 命令中指定作業，則必須在作業名稱中包括句號。 也請務必使用雙引號 (`" "`) 來含括作業名稱。

|易記名稱|作業|描述|
|:-----|:-----|:-----|
|將成員新增至 [角色] 中|將成員新增至角色。|已將使用者新增至 Microsoft 365 中的系統管理員角色。|
|已從目錄角色中移除使用者|移除角色的成員。|已從 Microsoft 365 中的系統管理員角色中移除使用者。|
|設定公司連絡人資訊|設定公司連絡人資訊。|已更新您的組織之公司層級的連絡人喜好設定。 這包括 Microsoft 365 所傳送之訂閱相關電子郵件的電子郵件地址，以及有關服務的技術通知。|
||||

### <a name="directory-administration-activities"></a>目錄管理活動

下表列出當系統管理員在 Microsoft 365 系統管理員中心或 Azure 管理入口網站中管理其組織時，會記錄的 Azure AD 目錄和網域相關活動。

> [!NOTE]
> 下表的 [作業 **]** 欄中所列的作業名稱包含一個句點 (`.`)。 如果您在搜尋稽核記錄、建立稽核保留原則、建立警示原則或建立活動警示時，於 PowerShell 命令中指定作業，則必須在作業名稱中包括句號。 也請務必使用雙引號 (`" "`) 來含括作業名稱。

|易記名稱|作業|描述|
|:-----|:-----|:-----|
|已將網域新增至公司|將網域新增至公司。|已將網域新增至您的組織。|
|已將合作夥伴新增至目錄|將合作夥伴新增至公司。|已將合作夥伴 (委派系統管理員) 新增至您的組織。|
|已從公司中移除網域|移除公司的網域。|已從您的組織中移除網域。|
|已從目錄中移除合作夥伴|移除公司的合作夥伴。|已從您的組織中移除合作夥伴 (委派系統管理員)。|
|已設定公司資訊|設定公司資訊。|已更新您的組織的公司資訊。 這包括 Microsoft 365 所傳送之訂閱相關電子郵件的電子郵件地址，以及有關 Microsoft 365 服務的技術通知。|
|設定網域驗證|設定網域驗證。|已變更您的組織之網域驗證設定。|
|已更新網域的同盟設定|設定網域上的同盟設定。|已變更您的組織之同盟 (外部共用) 設定。|
|已設定密碼原則|設定密碼原則。|已變更您的組織中使用者密碼的長度和字元限制。|
|已開啟 Azure AD 同步|設定 DirSyncEnabled 旗標。|設定可為 Azure AD 同步啟用目錄的屬性。|
|已更新網域|更新網域。|已更新您的組織中的網域設定。|
|已驗證網域|驗證網域。|已驗證貴組織是網域的擁有者。|
|已驗證電子郵件已驗證網域|驗證電子郵件已驗證的網域。|使用電子郵件驗證來驗證貴組織是否為網域的擁有者。|
||||

### <a name="ediscovery-activities"></a>電子文件探索活動

在安全性與合規性中心中或透過執行對應 PowerShell Cmdlet 所進行的內容搜尋和電子文件探索相關活動，會記錄在稽核記錄中。 這包括下列活動：

- 建立及管理電子文件探索案件

- 建立、開啟及編輯 [內容搜尋]

- 執行 [內容搜尋] 動作，例如預覽、匯出及刪除搜尋結果

- 設定 [內容搜尋] 的權限篩選

- 管理電子文件探索系統管理員角色

如需已記錄電子文件探索活動的清單和詳細描述，請參閱[搜尋稽核記錄中的電子文件探索活動](search-for-ediscovery-activities-in-the-audit-log.md)。

> [!NOTE]
> **活動** 下拉式清單的 **電子文件探索活動** 和 **進階電子文件探索活動** 下方所列的活動結果事件，最多需要 30 分鐘才會顯示在搜尋結果中。 相反地，系統需要 24 小時才能在搜尋結果中顯示電子文件探索 Cmdlet 活動的對應事件。

### <a name="advanced-ediscovery-activities"></a>進階電子文件探索活動

您也可以在進階電子文件探索活動中搜尋活動的稽核記錄。 如需這些活動的描述，請參閱[在稽核記錄中搜尋電子文件探索活動](search-for-ediscovery-activities-in-the-audit-log.md#advanced-ediscovery-activities)中的”進階電子文件探索活動”一節。

### <a name="power-bi-activities"></a>Power BI 活動

您可以在 Power BI 中搜尋活動的稽核記錄。 如需 Power BI 活動的相關資訊，請參閱[在您組織內使用稽核功能](/power-bi/service-admin-auditing#activities-audited-by-power-bi)中的＜由 Power BI 進行稽核的活動＞一節。

Power BI 的稽核記錄未預設為啟用。 若要在稽核記錄中搜尋 Power BI 活動，您必須在 Power BI 系統管理員入口網站中啟用稽核功能。 如需相關指示，請參閱 [Power BI 系統管理員入口網站](/power-bi/service-admin-portal#audit-logs)中的＜稽核記錄＞一節。

### <a name="workplace-analytics-activities"></a>工作場所分析活動

工作場所分析可針對群組在組織間共同作業的方式提供見解。 下表列出在工作場所分析中獲派系統管理員角色或分析師角色的使用者所執行的活動。 獲派分析師角色的使用者具有所有服務功能的完整存取權，並可使用產品來進行分析。 獲派系統管理員角色的使用者可以設定隱私權設定與系統預設值，並可以準備、上傳及驗證工作場所分析中的組織資料。 如需詳細資訊，請參閱[工作場所分析](/workplace-analytics/index-orig)。

|易記名稱|作業|描述|
|:-----|:-----|:-----|
|已存取 OData 連結|AccessedOdataLink|分析師已存取查詢的 OData 連結。|
|已取消查詢|CanceledQuery|分析師已取消執行查詢。|
|已建立會議排除|MeetingExclusionCreated|分析師已建立會議排除規則。|
|已刪除結果|DeletedResult|分析師已刪除查詢結果。|
|已下載報表|DownloadedReport|分析師已下載查詢結果檔案。|
|已執行查詢|ExecutedQuery|分析師已執行查詢。|
|已更新資料存取設定|UpdatedDataAccessSetting|系統管理員已更新資料存取設定。|
|已更新隱私權設定|UpdatedPrivacySetting|系統管理員已更新隱私權設定；例如，群組大小的下限。|
|已上傳組織資料|UploadedOrgData|系統管理員已上傳組織資料檔案。|
|已檢視探索|ViewedExplore|分析師已檢視一個或多個探索頁面索引標籤中的視覺效果。|
||||

### <a name="microsoft-teams-activities"></a>Microsoft Teams 活動

您可以在 Microsoft Teams 中搜尋使用者和系統管理員活動的稽核記錄。 Teams 是 Office 365 中以聊天方式為主的工作區。 它能將小組的交談、會議、檔案及筆記存放在同一個位置。 如需受稽核的 Teams 活動描述，請參閱 [在 Microsoft Teams 的稽核紀錄中搜尋事件](/microsoftteams/audit-log-events#teams-activities)。

### <a name="microsoft-teams-healthcare-activities"></a>Microsoft Teams 醫療保健活動

如果貴組織正在 Microsoft Teams 中使用[病患應用程式](/MicrosoftTeams/expand-teams-across-your-org/healthcare/patients-app-overview)，則可以在稽核記錄中搜尋與病患應用程式相關的活動。 如果您的環境設定為支援病患應用程式，則 **活動** 選擇器清單中提供了這些活動的其他活動群組。

![活動選擇器清單中的 Microsoft Teams 醫療保健活動](../media/TeamsHealthcareAuditActivities.png)

如需有關病患應用程式活動的說明，請參閱[病患應用程式的稽核記錄](/MicrosoftTeams/expand-teams-across-your-org/healthcare/patients-audit)。

### <a name="microsoft-teams-shifts-activities"></a>Microsoft Teams 班次活動

如果貴組織正在 Microsoft Teams 中使用班次應用程式，則您可以在稽核記錄中搜尋與使用班次應用程式相關的活動。 如果您的環境設定為支援班次應用程式，則 **活動** 選擇器清單中提供了這些活動的額外活動群組。

如需班次應用程式活動的描述，請參閱 [在 Microsoft Teams 的稽核紀錄中搜尋事件](/microsoftteams/audit-log-events#shifts-in-teams-activities)。

### <a name="yammer-activities"></a>Yammer 活動

下表列出稽核記錄中記錄的 Yammer 使用者和系統管理員活動。 若要從稽核記錄傳回 Yammer 相關活動，您必須在 [活動] 清單中選取 [顯示所有活動的結果]。 使用 [日期範圍] 方塊與 [使用者] 清單來縮小搜尋結果。

|易記名稱|作業|描述|
|:-----|:-----|:-----|
|已變更資料保留原則|SoftDeleteSettingsUpdated|驗證系統管理員將網路資料保留原則的設定更新為 [實刪除] 或 [虛刪除]。 僅限驗證系統管理員可以執行這項作業。|
|已變更網路設定|NetworkConfigurationUpdated|網路或驗證系統管理員變更 Yammer 網路的設定。 這包括設定匯出資料的間隔和啟用聊天。|
|已變更網路設定檔設定|ProcessProfileFields|網路或驗證系統管理員變更網路使用者網路的成員個人檔案顯示資訊。|
|已變更私人內容模式|SupervisorAdminToggled|驗證系統管理員開啟或關閉「私人內容模式」。 這個模式可讓系統管理員檢視私人群組中的文章以及個別使用者 (或使用者群組) 之間的私人訊息。 僅限驗證系統管理員可以執行這項作業。|
|已變更安全性設定|NetworkSecurityConfigurationUpdated|驗證系統管理員更新 Yammer 網路的安全性設定。 這包括設定密碼過期原則及 IP 位址的限制。 僅限驗證系統管理員可以執行這項作業。|
|已建立檔案|FileCreated|使用者上傳檔案。|
|已建立群組|GroupCreation|使用者建立群組。|
|已刪除群組|GroupDeletion|從 Yammer 刪除群組。|
|已刪除訊息|MessageDeleted|使用者刪除訊息。|
|下載的檔案|FileDownloaded|使用者下載檔案。|
|已匯出資料|DataExport|驗證系統管理員匯出 Yammer 網路資料。 僅限驗證系統管理員可以執行這項作業。|
|已共用檔案|FileShared|使用者與其他使用者共用檔案。|
|已將網路使用者停權|NetworkUserSuspended|網路或驗證系統管理員將 Yammer 的使用者停權 (停用)。|
|已將使用者停權|UserSuspension|已將使用者帳戶停權 (已停用)。|
|已更新檔案描述|FileUpdateDescription|使用者變更檔案的描述。|
|已更新檔案名稱|FileUpdateName|使用者變更檔案的名稱。|
|已檢視檔案|FileVisited|使用者檢視檔案。|
||||

### <a name="microsoft-power-automate-activities"></a>Microsoft Power Automate 活動

您可以在 Power Automate (之前稱為 Microsoft Flow) 中搜尋活動的稽核記錄。 這些活動包括建立、編輯和刪除流程，以及變更流程權限。 如需有關 Power Automate 活動的稽核資訊，請參閱部落格：[Microsoft 365 合規性中心現在已有 Microsoft Flow 稽核事件](https://flow.microsoft.com/blog/security-and-compliance-center)。

### <a name="microsoft-power-apps-activities"></a>Microsoft Power Apps 活動

您可以在 Power Apps 中搜尋應用程式相關活動的稽核記錄。 這些活動包括建立、啟動和發佈應用程式。 將權限指派給應用程式也會經過稽核。 如需所有 Power Apps 活動的說明，請參閱 [Power Apps 的活動記錄](/power-platform/admin/logging-powerapps#what-events-are-audited)。

### <a name="microsoft-stream-activities"></a>Microsoft Stream 活動

您可以在 Microsoft Stream 中搜尋活動的稽核記錄。 這些活動包括使用者執行的視訊活動、群組頻道活動及系統管理員活動，例如管理使用者、管理組織設定及匯出報告。 如需這些活動的說明，請參閱 [Microsoft Stream 中的稽核記錄](/stream/audit-logs#actions-logged-in-stream) 中的「Stream 中記錄的動作」一節。

### <a name="content-explorer-activities"></a>內容總管活動

下表列出稽核記錄中記錄的內容總管活動。 內容總管可從 Microsoft 365 合規性中心的資料分類工具中存取。 如需詳細資訊，請參閱[使用資料分類內容總管](data-classification-content-explorer.md)。

|易記名稱|作業|描述|
|:-----|:-----|:-----|
|已存取的項目|LabelContentExplorerAccessedItem|系統管理員 (或身為內容總管內容檢視器角色群組成員的使用者) 可使用內容總管來檢視電子郵件訊息或 SharePoint/OneDrive 文件。|
||||

### <a name="quarantine-activities"></a>隔離活動

以下表格列出您可以在稽核記錄中搜尋的隔離活動。 如需關於隔離的詳細資訊，請參閱[在 Office 365 中隔離電子郵件](../security/office-365-security/quarantine-email-messages.md)。

|易記名稱|作業|描述|
|:-----|:-----|:-----|
|刪除隔離郵件|QuarantineDelete|使用者已刪除了被視為有害的電子郵件。|
|已匯出的隔離郵件|QuarantineExport|使用者已匯出了被視為有害的電子郵件。|
|預覽隔離郵件|QuarantinePreview|使用者已預覽了被視為有害的電子郵件。|
|已釋放隔離郵件|QuarantineRelease|使用者已釋放了被視為有害的電子郵件。|
|已檢視隔離郵件標題|QuarantineViewHeader|使用者已檢視了被視為有害電子郵件的標題。|
||||

### <a name="microsoft-forms-activities"></a>Microsoft Teams 活動

下表列出稽核記錄中記錄的 Microsoft Forms 使用者和系統管理員活動。 Microsoft Forms 是用來收集資料的表單/測驗/問卷工具，以進行資料分析。 

以下說明中指出部分作業包含的其他活動參數。

> [!NOTE]
> 如果 Forms 活動是由共同作者或匿名回應者執行，則記錄方式會稍有不同。 如需詳細資訊，請參閱[由共同作者和匿名回應者執行的 Forms 活動](#forms-activities-performed-by-coauthors-and-anonymous-responders)一節。

|易記名稱|作業|描述|
|:-----|:-----|:-----|
|已建立註解|CreateComment|表單擁有者為測驗新增註解或分數。|
|已建立表單|CreateForm|表單擁有者建立新表單。 <br><br>Property DataMode:string 指示若屬性值等於 DataSync，則目前的表單設定為與新的或現有的 Excel 活頁簿同步。 屬性 ExcelWorkbookLink:string 指示目前表單的關聯 Excel 活頁簿識別碼。|
|已編輯表單|EditForm|表單擁有者編輯表單，例如建立、移除或編輯問題。 屬性 *EditOperation:string* 指出編輯作業名稱。 可能的作業如下：<br/>- CreateQuestion<br/>- CreateQuestionChoice <br/>- DeleteQuestion <br/>- DeleteQuestionChoice <br/>- DeleteFormImage <br/>- DeleteQuestionImage <br/>- UpdateQuestion <br/>- UpdateQuestionChoice <br/>- UploadFormImage/Bing/Onedrive <br/>- UploadQuestionImage <br/>- ChangeTheme <br><br>FormImage 包含在表單中使用者可上傳影像的任何位置，例如在查詢中或做為背景佈景主題。|
|已移動表單|MoveForm|表單擁有者移動表單。 <br><br>屬性 DestinationUserId：字串表示移動表單人員的使用者識別碼。 屬性 NewFormId：字串是新複製表單的全新識別碼。 屬性 IsDelegateAccess:boolean 指示目前表單移動動作是透過系統管理員委派頁面執行。|
|已刪除表單|DeleteForm|表單擁有者刪除表單。 這包含 SoftDelete (刪除使用的選項和移至資源回收筒的表單) 與 HardDelete (清空資源回收筒)。|
|已檢視表單 (設計階段)|ViewForm|表單擁有者開啟現有表單以進行編輯。 <br><br>屬性 AccessDenied:boolean 指示目前表單的存取因權限檢查而遭拒絕。 屬性 FromSummaryLink:boolean 指示目前的要求來自摘要連結頁面。|
|已預覽表單|PreviewForm|表單擁有者使用 [預覽] 功能預覽表單。|
|已匯出表單|ExportForm|表單擁有者將結果匯出到 Excel。 <br><br>屬性 ExportFormat：字串表示 Excel 檔案為下載或線上。|
|允許複製共用表單|AllowShareFormForCopy|表單擁有者建立範本連結，以與其他使用者共用表單。 當表單擁有者按一下以產生範本 URL 時，系統會記錄此事件。|
|已禁止複製共用表單|DisallowShareFormForCopy|表單擁有者刪除範本連結。|
|已新增表單共同撰寫|AddFormCoauthor|使用者使用共同作業連結來協助設計/檢視回應。 當使用者使用共同作業 URL (而不是第一次產生共同作業 URL 時)，系統會記錄此事件。|
|已移除表單共同撰寫|RemoveFormCoauthor|表單擁有者刪除共同作業連結。|
|已檢視回應頁面|ViewRuntimeForm|使用者已開啟要檢視的回應頁面。 無論使用者是否提交回應，系統都會記錄此事件。|
|已建立回應|CreateResponse|類似於接收新回應。  使用者已提交表單的回應。 <br><br>屬性 ResponseId：字串和屬性 ResponderId：字串表示正在檢視哪項結果。 <br><br>針對匿名回應者，ResponderId 屬性將為 Null。|
|已更新回應|UpdateResponse|表單擁有者已在測驗上更新註解或分數。 <br><br>屬性 ResponseId：字串和屬性 ResponderId：字串表示正在檢視哪項結果。 <br><br>針對匿名回應者，ResponderId 屬性將為 Null。|
|已刪除所有回應|DeleteAllResponses|表單擁有者刪除所有回應資料。|
|已刪除回應|DeleteResponse|表單擁有者刪除一項回應。 <br><br>屬性 ResponseId：字串表示正刪除回應。|
|已檢視回應|ViewResponses|表單擁有者檢視回應的彙總清單。 <br><br>屬性 ViewType：字串表示表單擁有者是否正在檢視彙總詳細資料|
|已檢視回應|ViewResponse|表單擁有者檢視特定回應。 <br><br>屬性 ResponseId：字串和屬性 ResponderId：字串表示正在檢視哪項結果。 <br><br>針對匿名回應者，ResponderId 屬性將為 Null。|
|已建立摘要連結|GetSummaryLink|表單擁有者建立摘要結果連結以共用結果。|
|已刪除摘要連結|DeleteSummaryLink|表單擁有者刪除摘要結果連結。|
|已更新表單網路釣魚狀態|UpdatePhishingStatus|每當內部安全性狀態的詳細資料值變更時，系統就會記錄此事件，無論這是否會變更最後的安全性狀態 (例如，現在已關閉或開啟表單)。 這表示您可能會看到不具有最終安全性狀態變更的重複事件。 此事件的可能狀態值如下：<br/>- 記下 <br/>- 由系統管理員記下 <br/>- 系統管理員解除封鎖 <br/>- 自動封鎖 <br/>- 自動解除封鎖 <br/>- 客戶報告 <br/>- 重設客戶報告|
|更新的使用者網路釣魚狀態|UpdateUserPhishingStatus|每當使用者安全性狀態的值變更時，就會記錄此事件。 當使用者建立的網路釣魚表單已由 Microsoft Online 安全小組記下，即會將稽核記錄中使用者狀態的值 **確認為網路釣魚者**。 如果系統管理員解除封鎖該使用者，該使用者的狀態值會設定為 [重設為一般使用者 **]**。|
|已傳送 Forms Pro 邀請|ProInvitation|使用者按一下以啟用 Pro 試用版。|
|已更新表單設定|UpdateFormSetting|表單擁有者更新一或多個表單設定。 <br><br>屬性 FormSettingName:string 指示更新的敏感性設定名稱。 屬性 NewFormSettings:string 指示更新的設定名稱和新值。 屬性 thankYouMessageContainsLink:boolean 指示更新的 thankyou 訊息包含 URL 連結。|
|已編輯使用者設定|UpdateUserSetting|表單擁有者更新使用者設定。 <br><br>屬性 UserSettingName：字串表示設定的名稱和新值。|
|已列出表單|ListForms|表單擁有者正檢視表單清單。 <br><br>屬性 ViewType：字串表示表單擁有者正查看何種檢視：[所有表單]、[與我共用] 或 [群組表單]|
|已提交回應|SubmitResponse|使用者提交表單的回應。 <br><br>屬性 IsInternalForm：如果回應者與表單擁有者位於同一組織中，則會顯示布林值。|
|已啟用任何人都可以回應設定|AllowAnonymousResponse|表單擁有者開啟允許任何人回應表單的設定。|
|已停用任何人都可以回應設定|DisallowAnonymousResponse|表單擁有者關閉允許任何人回應表單的設定。|
|已啟用特定人員可以回應設定|EnableSpecificResponse|表單擁有者開啟只允許目前組織中特定人員或特定群組回應表單的設定。|
|已停用特定人員可以回應設定|DisableSpecificResponse|表單擁有者關閉只允許目前組織中特定人員或特定群組回應表單的設定。|
|已新增特定回應者|AddSpecificResponder|表單擁有者將新使用者或群組新增到特定回應者清單。|
|已移除特定回應者|RemoveSpecificResponder|表單擁有者將使用者或群組從特定回應者清單移除。|
|已停用共同作業|DisableCollaboration|表單擁有者關閉表單上的共同作業設定。|
|已啟用 Office 365 公司或學校帳戶共同作業|EnableWorkOrSchoolCollaboration|表單擁有者開啟設定，允許具有 Office 365 公司或學校帳戶的使用者檢視及編輯表單。|
|已啟用我組織中的人員共同作業|EnableSameOrgCollaboration|表單擁有者開啟設定，允許目前組織的使用者檢視及編輯表單。|
|已啟用特定人員共同作業|EnableSpecificCollaboaration|表單擁有者開啟只允許目前組織中特定人員或特定群組檢視及編輯表單的設定。|
|已連線至 Excel 活頁簿|ConnectToExcelWorkbook|已將表單連線至 Excel 活頁簿。 <br><br>屬性 ExcelWorkbookLink:string 指示目前表單的關聯 Excel 活頁簿識別碼。|
||||

#### <a name="forms-activities-performed-by-coauthors-and-anonymous-responders"></a>由共同作者和匿名回應者執行的 Forms 活動

在設計表單和分析回應時，Forms 支援共同作業。 表單共同作業者稱為 [共同作者]。 除了刪除或移動表單以外，共同作者可以執行表單擁有者可以執行的所有動作。 Forms 也可讓您建立可匿名回應的表單。 這表示回應者不需要登入您的組織就能回應表單。

下表說明共同作者和匿名回應者執行之活動的稽核記錄中的稽核活動和資訊。

|活動類型|內部或外部使用者|已登入的使用者識別碼|已登入的組織|Forms 使用者類型|
|:-----|:-----|:-----|:-----|:-----|
|共同撰寫活動|內部|UPN|表單擁有者的組織|共同作者|
|共同撰寫活動|外部|UPN<br>|共同作者的組織<br>|共同作者|
|共同撰寫活動|外部|`urn:forms:coauthor#a0b1c2d3@forms.office.com`<br>(識別碼的第二部分是雜湊，會因使用者而有所不同)|表單擁有者的組織<br>|共同作者|
|回應活動|外部|UPN<br>|回應者的組織<br>|回應者|
|回應活動|外部|`urn:forms:external#a0b1c2d3@forms.office.com`<br>(使用者識別碼的第二部分是雜湊，會因使用者而有所不同)|表單擁有者的組織|回應者|
|回應活動|匿名|`urn:forms:anonymous#a0b1c2d3@forms.office.com`<br>(使用者識別碼的第二部分是雜湊，會因使用者而有所不同)|表單擁有者的組織|回應者|
||||

### <a name="sensitivity-label-activities"></a>敏感度標籤活動

下表列出 SharePoint Online 和 Teams 網站套用標籤活動所產生的事件。

|易記名稱|作業|描述|
|:-----|:-----|:-----|
|已將敏感度標籤套用到網站|SensitivityLabelApplied|已將敏感度標籤套用到 SharePoint 或 Teams 網站。|
|已將敏感度標籤從網站移除|SensitivityLabelRemoved|已將敏感度標籤從 SharePoint 或 Teams 網站移除。|
|已將敏感度標籤套用到檔案|FileSensitivityLabelApplied|已使用 Office 網頁版或自動標籤原則將敏感度標籤套用到文件。|
|已變更套用到檔案的敏感度標籤|FileSensitivityLabelChanged|已使用 Office 網頁版或自動標籤原則將不同的敏感度標籤套用到文件。|
|已將敏感度標籤從檔案移除|FileSensitivityLabelRemoved|已使用 Office 網頁版、自動加上標籤原則，或使用 [Unlock-SPOSensitivityLabelEncryptedFile](/powershell/module/sharepoint-online/unlock-sposensitivitylabelencryptedFile) Cmdlet 來移除文件中的敏感度標籤。|
||||

### <a name="retention-policy-and-retention-label-activities"></a>保留原則和保留標籤活動

|易記名稱|作業|描述|
|:-----|:-----|:-----|
| 保留原則已配置的設定 |NewRetentionComplianceRule |系統管理員已設定新保留原則的保留設定。 保留設定包括保留項目的時間長度，以及當項目保留期間到期時，項目會發生的情況 (例如刪除項目、保留項目或保留然後刪除項目)。 此活動也與執行 [RetentionComplianceRule](/powershell/module/exchange/new-retentioncompliancerule) Cmdlet 對應。|
| 已建立保留標籤 |NewComplianceTag |系統管理員已建立新的保留標籤。|
| 已建立保留原則 |NewRetentionCompliancePolicy|系統管理員已建立新的保留原則。|
| 已從保留原則刪除設定| RemoveRetentionComplianceRule<br/>| 系統管理員已刪除保留原則的組態設定。 當系統管理員刪除保留原則或執行 [RetentionComplianceRule](/powershell/module/exchange/Remove-RetentionComplianceRule) Cmdlet 時，更可能會記錄此活動。|
| 已刪除保留標籤 |RemoveComplianceTag | 系統管理員已刪除保留標籤。|
| 已刪除保留原則 |RemoveRetentionCompliancePolicy<br/> |系統管理員已刪除保留原則。 |
| 已啟用保留標籤的法規記錄選項<br/> |SetRestrictiveRetentionUI |系統管理員已執行 [RegulatoryComplianceUI](/powershell/module/exchange/set-regulatorycomplianceui) Cmdlet，因此系統管理員可以選取保留標籤的 UI 設定選項，以將內容標示為法規記錄。|
| 保留原則已更新的設定 | SetRetentionComplianceRule | 系統管理員已變更現有保留原則的保留設定。 保留設定包括保留項目的時間長度，以及當項目保留期間到期時，項目會發生的情況 (例如刪除項目、保留項目或保留然後刪除項目)。 此活動也與執行 [Set-RetentionComplianceRule](/powershell/module/exchange/set-retentioncompliancerule) Cmdlet 對應。 |
| 已更新保留標籤 |SetComplianceTag  | 系統管理員已更新現有的保留標籤。|
| 已更新保留原則 |SetRetentionCompliancePolicy |系統管理員已更新現有的保留原則。 觸發此事件的更新包括新增或排除保留原則所套用的內容位置。|
||||

### <a name="briefing-email-activities"></a>簡報電子郵件活動

下表列出 Office 365 稽核記錄中記錄的簡報電子郵件活動。如需有關如何簡報電子郵件的詳細資訊，請參閱：

- [簡報電子郵件概觀](/Briefing/be-overview)

- [設定簡報電子郵件](/Briefing/be-admin)

|**易記名稱**|**作業**|**描述**|
|:-----|:-----|:-----|
|更新的組織隱私權設定|UpdatedOrganizationBriefingSettings|系統管理員會更新簡報電子郵件的組織隱私權設定。 |
|更新的使用者隱私權設定|UpdatedUserBriefingSettings|系統管理員會更新簡報電子郵件的使用者隱私權設定。
||||

### <a name="myanalytics-activities"></a>MyAnalytics 活動

下表列出 Office 365 稽核記錄中記錄的 MyAnalytics 活動。 如需有關 MyAnalytics 的詳細資訊，請參閱[適用於系統管理員的 MyAnalytics](/workplace-analytics/myanalytics/overview/mya-for-admins)。

|**易記名稱**|**作業**|**描述**|
|:-----|:-----|:-----|
|更新的組織 MyAnalytics 設定|UpdatedOrganizationMyAnalyticsSettings|系統管理員會更新 MyAnalytics 的組織層級設定。 |
|更新的使用者 MyAnalytics 設定|UpdatedUserMyAnalyticsSettings|系統管理員會更新 MyAnalytics 的使用者設定。|
||||

### <a name="information-barriers-activities"></a>資訊屏障活動

下表列出 Office 365 稽核記錄中記錄的資訊屏障活動。 如需資訊屏障的詳細資訊，請參閱[了解 Microsoft 365 中的資訊屏障](information-barriers.md)。

|**易記名稱**|**作業**|**描述**|
|:----------------|:------------|:--------------|
| 已新增區段至網站 | SegmentsAdded | SharePoint、全域系統管理員或網站擁有者已新增一或多個資訊屏障區段至網站。 |
| 已變更網站的區段 | SegmentsChanged | SharePoint 或全域系統管理員已變更一或多個網站的資訊屏障區段。 |
| 已從網站移除區段 | SegmentsRemoved | SharePoint 或全域系統管理員已從網站移除一或多個資訊屏障區段。 |
||||

### <a name="exchange-admin-audit-log"></a>Exchange 系統管理員稽核記錄

Exchange 系統管理員稽核記錄功能 (在 Office 365 中預設為啟用) 會在系統管理員 (或獲派管理權限的使用者) 在您的 Exchange Online 組織中進行變更時，將事件記錄在稽核記錄中。 使用 Exchange 系統管理員中心或執行 Exchange Online PowerShell 中的 Cmdlet 所做的變更會記錄在 Exchange 系統管理稽核記錄中。 以動詞 **Get-**、**Search-** 或 **Test-** 開頭的 Cmdlet 不會記錄在稽核記錄中。 如需有關 Exchange 系統管理員稽核記錄的詳細資訊，請參閱[系統管理員稽核記錄功能](/exchange/administrator-audit-logging-exchange-2013-help)。

> [!IMPORTANT]
> 未記錄在 Exchange 系統管理員稽核記錄 (或在稽核記錄中) 的某些 Exchange Online Cmdlet。 許多這些 Cmdlet 都與維護 Exchange Online 服務相關，並由 Microsoft 資料中心人員或服務帳戶執行。 之所以不記錄這些 Cmdlet，是因為這些 Cmdlet 會造成大量的「雜亂」稽核事件。 如果有 Exchange Online Cmdlet 未受到稽核，請傳送建議給[安全性與合規性的 User Voice 論壇](https://office365.uservoice.com/forums/289138-office-365-security-compliance)，並要求對其啟用稽核。 您也可以將設計變更要求 (DCR) 傳送到 Microsoft 支援服務。

以下是在搜尋稽核記錄時搜尋 Exchange 系統管理員活動的秘訣：

- 若要從 Exchange 系統管理員稽核記錄傳回項目，您必須在 [活動] 清單中選取 [顯示所有活動的結果]。 使用日期範圍方塊和 [使用者] 清單，以將由特定 Exchange 系統管理員執行的 Cmdlet 搜尋結果縮小為在特定日期範圍之內。

- 若要顯示來自 Exchange 系統管理員稽核記錄的事件，請篩選搜尋結果，並在 [活動] 篩選方塊中輸入 **-** (破折號)。 這會顯示那些顯示於 Exchange 系統管理員事件 [活動] 欄中的 Cmdlet 名稱。 接著，您可以將 Cmdlet 名稱依字母順序排序顯示。

  ![在 [活動] 方塊中輸入虛線以篩選 Exchange 系統管理員事件](../media/7628e7aa-6263-474a-a28b-2dcf5694bb27.png)

- 如需取得有關 Cmdlet 執行內容、使用哪些參數和參數值，以及影響哪些物件等相關資訊，您可以藉由選取 [下載所有結果] 選項來匯出搜尋結果。 如需詳細資訊，請參閱[匯出、設定及檢視稽核記錄檔的記錄](export-view-audit-log-records.md)。

- 您也可以藉由在 Exchange Online PowerShell 中使用 `Search-UnifiedAuditLog -RecordType ExchangeAdmin` 命令，只傳回 Exchange 系統管理員稽核記錄中的稽核記錄。 執行 Exchange Cmdlet 之後，可能需要 30 分鐘的時間，搜尋結果中才會傳回對應的稽核記錄項目。 如需詳細資訊，請參閱 [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog)。 若要了解如何將 **Search-UnifiedAuditLog** Cmdlet 所傳回的搜尋結果匯出為 CSV 檔案，請參閱 [匯出、設定及檢視稽核記錄檔的記錄](export-view-audit-log-records.md#tips-for-exporting-and-viewing-the-audit-log)中的＜匯出及檢視稽核記錄的秘訣＞一節。

- 您也可以使用 Exchange 系統管理員中心或在 Exchange Online PowerShell 中執行 **Search-AdminAuditLog**，來檢視 Exchange 系統管理員稽核記錄中的事件。 這在搜尋 Exchange Online 系統管理員所執行的活動中，是絕佳的方式。 如需詳細指示，請參閱：

  - [檢視系統管理員稽核記錄](/exchange/security-and-compliance/exchange-auditing-reports/view-administrator-audit-log)

  - [Search-AdminAuditLog](/powershell/module/exchange/search-adminauditlog)

   請記住，相同的 Exchange 系統管理員活動會同時記錄在 Exchange 系統管理員稽核記錄和稽核記錄中。

## <a name="frequently-asked-questions"></a>常見問題集

**目前稽核的各種 Microsoft 365 服務是什麼？**

最常使用的服務，例如 Exchange Online、SharePoint Online、商務用 OneDrive、Azure Active Directory、Microsoft Teams、Dynamics 365、Office 365 防護和 Power BI 都會進行稽核。 如需稽核的服務清單，請參閱[這篇文章的開頭](search-the-audit-log-in-security-and-compliance.md)。

**稽核服務在 Office 365 中稽核的活動為何？**

請參閱本文的[稽核活動](#audited-activities)一節，其中包含稽核的活動清單及描述。

**事件發生後多久才能使用稽核記錄？**

大部分稽核資料都可在事件發生後的 30 鐘內予以使用，但對應的稽核記錄項目最多可能需要 24 小時才會顯示在搜尋結果中。 請參閱本文的[在您搜尋稽核記錄之前](#before-you-search-the-audit-log)一節中的表格，其中顯示不同服務中事件所需的時間。

**稽核記錄可保留多久時間？**

如先前所述，由獲派 Office 365 E5 或 Microsoft E5 授權的使用者 (或擁有 Microsoft 365 E5 附加元件授權的使用者) 所執行活動的稽核記錄，會保留一年。 針對支援整合稽核記錄的其他所有訂閱，稽核記錄會保留 90天。

**我可以以程式設計方式存取稽核資料嗎？**

是。 Office 365 管理活動 API 可用來以程式設計方式擷取稽核記錄。  若要開始使用，請參閱[開始使用 Office 365 管理 API](/office/office-365-management-api/get-started-with-office-365-management-apis)。

**除了使用安全性與合規性中心或 Office 365 管理活動 API，有其他方法可取得稽核記錄嗎？**

否。 從稽核服務取得資料的方式只有兩種。

**針對想擷取稽核記錄的服務，我是否要為每項服務個別啟用稽核功能？**

在大部分的服務中，在您初次為貴組織開啟稽核功能之後，稽核功能就會預設為啟用狀態 (如本文中的[在您搜尋稽核記錄之前](#before-you-search-the-audit-log)一節中所述)。

**稽核服務支援刪除重複的記錄嗎？**

否。 稽核服務管線幾乎是即時的，因此並不支援刪除重複資料。

**稽核資料可在各個地理位置間流通嗎？**

否。 我們目前將稽核管線部署在 NA (北美洲)、EMEA (歐洲、中東及非洲) 和 APAC (亞太地區) 區域中。 不過，我們可以在這些區域間流通資料來達到負載平衡，並只能在即時網站期間才可這麼做。 當我們執行這些活動時，資料傳輸會經過加密處理。

**稽核資料會加密嗎？**

稽核資料會儲存在整合稽核管線部署所在位置中的 Exchange 信箱內 (靜態資料)。 靜態信箱資料未經 Exchange 加密。 不過，服務層級加密功能會加密所有信箱資料，因為 Microsoft 資料中心的 Exchange 伺服器是透過 BitLocker 進行加密。 如需詳細資訊，請參閱[商務用 Skype、商務用 OneDrive、SharePoint Online 與 Exchange Online 的 Office 365 加密](/compliance/assurance/assurance-encryption-for-microsoft-365-services)。

傳輸中的郵件資料一律會加密。
