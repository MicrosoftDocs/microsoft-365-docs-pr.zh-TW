---
title: 設定連接器以匯入實體聲譽徽章授予資料
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: 管理員可以設定資料連線器，將資料從其組織的實體聲譽徽章授予系統匯入 Microsoft 365。 這可讓您使用「內幕風險管理」原則中的這項資料，協助您偵測特定使用者對實體辦公樓的存取權，這可能表示您的組織可能會發生內部威脅。
ms.openlocfilehash: c07dfcbefa338f7499f2c45f595bf2ccda6387fa
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911363"
---
# <a name="set-up-a-connector-to-import-physical-badging-data-preview"></a>設定連接器以匯入實體聲譽徽章授予資料 (預覽) 

您可以在 Microsoft 365 規範中心內設定資料連線器，以匯入實體聲譽徽章授予資料，例如員工的原始實體存取事件，或組織的聲譽徽章授予系統所產生的任何實體存取告警。 實體存取點的範例是組建的專案，或伺服器機房或資料中心的專案。 實體聲譽徽章授予資料可供 Microsoft 365 [有問必答風險管理解決方案](insider-risk-management.md) 使用，以協助保護您的組織免受惡意活動或組織內的資料竊取。

設定實體聲譽徽章授予連接器包含下列工作：

- 在 Azure Active Directory 中建立應用程式 (Azure AD) ，以存取可接受包含實體聲譽徽章授予資料之 JSON 負載的 API 端點。

- 使用實體聲譽徽章授予資料連線器定義的架構建立 JSON 負載。

- 在 Microsoft 365 規範中心內建立實體聲譽徽章授予資料連線器。

- 執行腳本，將實體聲譽徽章授予資料推入 API 端點。

- （選用）排程腳本，使其自動執行，以匯入目前的實體聲譽徽章授予資料。

## <a name="before-you-set-up-the-connector"></a>在您設定連接器之前

- 在步驟3中建立實體聲譽徽章授予連接器的使用者，必須在 Exchange Online 中指派「信箱匯入匯出」角色。 依預設，此角色不會指派給 Exchange Online 內的任何角色群組。 您可以將信箱匯入匯出角色新增至 Exchange Online 中的「組織管理」角色群組。 或者，您可以建立新的角色群組、指派信箱匯入匯出角色，然後將適當的使用者新增為成員。 如需詳細資訊，請參閱「管理 Exchange Online 中的角色群組」一文中的 [ [建立角色群組](/Exchange/permissions-exo/role-groups#create-role-groups) 或 [修改角色群組](/Exchange/permissions-exo/role-groups#modify-role-groups) ] 區段。

- 您必須決定如何每日 (檢索或匯出組織實體聲譽徽章授予系統中的資料) 並建立步驟2中所述的 JSON 檔案。 您在步驟4中執行的腳本會將 JSON 檔案中的資料推送至 API 端點。

- 您在步驟4中執行的範例腳本會將實體聲譽徽章授予資料從 JSON 檔案推入至連接器 API，使其可供有問必答風險管理解決方案使用。 在任何 Microsoft standard support 計畫或服務下，都不支援此範例腳本。 範例指令碼係依「現狀」提供，不含任何種類的擔保方式。 Microsoft 另外不承擔任何明示或默示的擔保，包括但不限於適售性或適合某特定用途的默示擔保。 使用或操作範例指令碼和文件發生的所有風險，皆屬於您的責任。 Microsoft、其作者以及其他與建置、生產或交付程式碼相關的任何人在任何情況下皆完全不需對任何損失負責任，包括但不限於商業利潤損失、業務中斷、業務資訊損失、或其他錢財損失等因使用或無法使用範例指令碼或文件所發生的損失，即使 Microsoft 曾建議這些損失發生的可能性。

## <a name="step-1-create-an-app-in-azure-active-directory"></a>步驟1：在 Azure Active Directory 中建立應用程式

第一步是在 Azure Active Directory (Azure AD) 中建立及註冊新的應用程式。 應用程式會對應至您在步驟3中建立的實體聲譽徽章授予連接器。 建立此應用程式可讓 Azure AD 驗證封裝含實體聲譽徽章授予資料之 JSON 負載的推入要求。 在建立此 Azure AD 應用程式期間，請務必儲存下列資訊。 這些值將會在後續步驟中使用。

- Azure AD 應用程式識別碼 (也稱為「 *應用程式識別碼* 」或「 *用戶端識別碼* 」) 

- Azure AD 應用程式機密 (也稱為 *用戶端密碼*) 

- 租使用者識別碼 (也稱為 *目錄識別碼*) 

如需在 Azure AD 中建立應用程式的逐步指示，請參閱 [使用 Microsoft identity Platform 註冊應用程式](/azure/active-directory/develop/quickstart-register-app)。

## <a name="step-2-prepare-a-json-file-with-physical-badging-data"></a>步驟2：使用實體聲譽徽章授予資料準備 JSON 檔案

下一步是建立 JSON 檔案，其中包含員工實體存取資料的相關資訊。 如「開始之前」一節所述，您必須決定如何從組織的實體聲譽徽章授予系統產生此 JSON 檔案。

JSON 檔案必須符合連接器所需的架構定義。 以下是 JSON 檔案的必要架構屬性說明：

| 屬性	 | 描述 | 資料類型 |
|:-----------|:--------------|:------------|
|UserId|員工可以在系統中有多個數位身分識別。 輸入必須已由來源系統解析 Azure AD 識別碼。 |UPN 或電子郵件地址|
|AssetId|實體資產或實體存取點的參考識別碼。| 數位元字串|
|AssetName|實體資產或實體存取點的易記名稱。|數位元字串|
|EventTime|存取的時間戳記。|日期和時間（UTC 格式）|
|AccessStatus|值 `Success` 或 `Failed`| 字串|
|||

以下是符合必要架構的 JSON 檔案範例：

```json
[
    {
        "UserId":"sarad@contoso.com"
        "AssetId":"Mid-Sec-7",
        "AssetName":"Main Building 1st Floor Mid Section",
        "EventTime":"2019-07-04T01:57:49",
        "AccessStatus":"Failed",
    },
    {
        "UserId":"pilarp@contoso.com",        
        "AssetId":"Mid-Sec-7",
        "AssetName":"Main Building 1st Floor Mid Section",
        "EventTime":"2019-07-04T02:57:49",        
        "AccessStatus":"Success",
    }
]
```
當您在步驟3中建立實體聲譽徽章授予連接器時，您也可以從嚮導下載下列 JSON 檔案的架構定義。

```text
{
    "title" : "Physical Badging Signals",
    "description" : "Access signals from physical badging systems",
    "DataType" : {
        "description" : "Identify what is the data type for input signal",
        "type" : "string",
    },
    "type" : "object",
    "properties": {
        "UserId" : {
            "description" : "Unique identifier AAD Id resolved by the source system",
            "type" : "string",
        },
        "AssetId": {
            "description" : "Unique ID of the physical asset/access point",
            "type" : "string",
        },
        "AssetName": {
            "description" : "friendly name of the physical asset/access point",
            "type" : "string",
        },
        "EventTime" : {
            "description" : "timestamp of access",
            "type" : "string",
        },
        "AccessStatus" : {
            "description" : "what was the status of access attempt - Success/Failed",
            "type" : "string",
        },
    }
    "required" : ["UserId", "AssetId", "EventTime" "AccessStatus"]
}
```

## <a name="step-3-create-the-physical-badging-connector"></a>步驟3：建立實體聲譽徽章授予連接器

下一步是在 Microsoft 365 規範中心內建立實體聲譽徽章授予連接器。 在步驟4中執行腳本後，您在步驟3中建立的 JSON 檔案會進行處理並推送至您在步驟1中設定的 API 端點。 在這個步驟中，請務必複製當您建立連接器時所產生的 JobId。 當您執行腳本時，您會使用 JobId。

1. 移至 [https://compliance.microsoft.com](https://compliance.microsoft.com/) ，然後按一下左側導覽中的 [ **資料連線器** ]。

2. 在 [**實際聲譽徽章授予**] 底下的 [**資料連線器**] 頁面上，按一下 [ **View**]。

3. 在 [ **實體聲譽徽章授予** ] 頁面上，按一下 [ **新增連接器**]。

4. 在 [ **驗證認證** ] 頁面上，執行下列動作，然後按 **[下一步]**：
  
   1. 針對您在步驟1中建立的 Azure 應用程式，輸入或貼上 Azure AD 應用程式識別碼。
  
   2. 下載參考的範例架構，以建立 JSON 檔案。
  
   3. 輸入實體聲譽徽章授予連接器的唯一名稱。

5. 在 [ **複查** ] 頁面上，複查您的設定，然後按一下 **[完成]** 以建立連接器。

6. 隨即會顯示 [狀態] 頁面，確認已建立連接器。 此頁面也包含工作識別碼。 您可以從此頁面或連接線的飛出頁面複製工作識別碼。 執行腳本時，您需要此工作識別碼。

   [狀態] 頁面也包含腳本的連結。 請參閱下列腳本，瞭解如何將 JSON 檔案張貼至 API 端點。

7. 按一下 [完成 **]**。

   新的連接器會顯示在 [ **連接器** ] 索引標籤上的清單中。

8. 按一下剛才建立的實體聲譽徽章授予連接器，以顯示飛出頁面，該頁面包含有關連接器的屬性及其他資訊。

## <a name="step-4-run-the-script-to-post-your-json-file-containing-physical-badging-data"></a>步驟4：執行腳本以發佈包含實體聲譽徽章授予資料的 JSON 檔案

設定實體聲譽徽章授予連接器的下一步是執行腳本，將您在步驟) 2 中建立的 JSON 檔案 (中所建立的實體聲譽徽章授予資料推送至您在步驟1中建立的 API 端點。 我們為您提供參考的範例腳本，您可以選擇使用它或建立您自己的腳本，將 JSON 檔案發佈至 API 端點。

在您執行腳本後，包含實體聲譽徽章授予資料的 JSON 檔案會被推入您的 Microsoft 365 組織，供內部使用者風險管理解決方案存取。 建議您每日發佈實體聲譽徽章授予資料。 若要執行此動作，您可以自動化從實體聲譽徽章授予系統每天產生 JSON 檔案的程式，然後排程腳本以推入資料。

> [!NOTE]
> 可由 API 處理的 JSON 檔案中的記錄數目上限為50000記錄。

1. 請移 [至此 GitHub 網站](https://github.com/microsoft/m365-hrconnector-sample-scripts/blob/master/upload_termination_records.ps1) 來存取範例腳本。

2. 按一下 [ **原始** ] 按鈕，以在文字視圖中顯示腳本

3. 複製範例腳本中的所有行，然後將其儲存至文字檔。

4. 如有需要，修改組織的範例腳本。

5. 使用檔案名尾碼（ps1）將文字檔儲存為 Windows PowerShell script 檔案;例如，PhysicalBadging.ps1。

6. 在您的本機電腦上開啟命令提示字元，然後移至您用來儲存腳本的目錄。

7. 執行下列命令，將 JSON 檔案中的實體聲譽徽章授予資料推送至 Microsoft 雲端;例如：

   ```powershell
   .\PhysicalBadging.ps1 -tenantId "<Tenant Id>" -appId "<Azure AD App Id>" -appSecret "<Azure AD App Secret>" -jobId "Job Id" -jsonFilePath "<records file path>"
   ```

   下表說明與此腳本搭配使用的參數及其必要的值。 您在上述步驟中取得的資訊會用於這些參數的值。

   | 參數 | 描述 |
   |:-------------|:--------------|
   |tenantId | 這是您在步驟1中取得之 Microsoft 365 組織的識別碼。 您也可以在 Azure AD 系統管理中心的 [ **一覽** ] 邊欄中取得組織的 tenantId。 這是用來識別您的組織。 |
   |標識 | 這是您在步驟1中您于 Azure AD 中所建立之應用程式的 Azure AD 應用程式識別碼。 當腳本嘗試存取您的 Microsoft 365 組織時，Azure AD 可用於驗證。                    |
   |appSecret | 這是您在步驟1中您在 Azure AD 中建立之應用程式的 Azure AD 應用程式機密。 這也是用來進行驗證。                                                        |
   |jobId | 這是您在步驟3中建立之實體聲譽徽章授予連接器的工作識別碼。 這是用來將推入 Microsoft 雲端的實體聲譽徽章授予資料與實體聲譽徽章授予連接器產生關聯。              |
   |JsonFilePath | 這是本機電腦上的檔案路徑， (您用來執行您在步驟2中建立之 JSON 檔案的腳本) 。 此檔案必須遵循步驟3中所述的範例架構。|
   |||

   以下是使用每個參數之實際值之實體聲譽徽章授予連接器腳本語法的範例：

   ```powershell
   .\PhysicalBadging.ps1 -tenantId d5723623-11cf-4e2e-b5a5-01d1506273g9 -appId 29ee526e-f9a7-4e98-a682-67f41bfd643e -appSecret MNubVGbcQDkGCnn -jobId b8be4a7d-e338-43eb-a69e-c513cd458eba -csvFilePath 'C:\Users\contosoadmin\Desktop\Data\physical_badging_data.json'
   ```

   上載成功時，腳本會顯示 **上傳成功** 郵件。

   如果您有多個 JSON 檔案，則必須針對每個檔案執行該腳本。

> [!NOTE]
> 您也可以選擇透過執行先前腳本的方法，將實體聲譽徽章授予資料推入 API 端點。 例如，以下是使用 Postman 將資料推送至 API 端點的範例。

## <a name="step-5-monitor-the-physical-badging-connector"></a>步驟5：監視實體聲譽徽章授予連接器

在您建立實體聲譽徽章授予連接器並推入實體聲譽徽章授予資料之後，您可以在 Microsoft 365 規範中心中查看連接器和上傳狀態。 如果您安排定期定期執行腳本，您也可以在上次腳本執行後，查看目前的狀態。

1. 移至 [https://compliance.microsoft.com](https://compliance.microsoft.com/) 並按一下左側導覽中的 [ **資料連線器** ]。

2. 按一下 [ **連接器** ] 索引標籤，然後選取實體聲譽徽章授予連接器以顯示飛出頁面。 此頁面包含連接器的屬性和資訊。

   ![實體聲譽徽章授予連接器的狀態彈出頁面](..\media\PhysicalBadgingStatusFlyout.png)

3. 在 [ **最後匯入**] 底下，按一下 [ **下載記錄** ] 連結，以開啟連接器的狀態記錄 (或儲存) 。 此記錄檔包含每次腳本執行的相關資訊，並將該資料從 CSV 檔案上傳至 Microsoft 雲端。

   ![實體聲譽徽章授予連接器記錄檔會顯示上傳的 JSON 檔案中的數位列](..\media\PhysicalBadgingConnectorLogFile.png)

   **RecordsSaved** 欄位會指出上傳的 CSV 檔案中的列數。 例如，如果 CSV 檔案包含四列，則 **RecordsSaved** 欄位的值為4，如果腳本成功上傳 CSV 檔案中的所有列。

如果您未在步驟4中執行腳本，則 [ **最後一次匯入**] 底下會顯示下載腳本的連結。 您可以下載腳本，然後依照步驟4中的步驟執行它。

## <a name="optional-step-6-schedule-the-script-to-run-automatically"></a> (選用) 步驟6：排程腳本自動執行

為了確保您的組織中的最新實體聲譽徽章授予資料可用於像「內部使用者風險管理」解決方案之類的工具，我們建議您安排腳本定期執行，例如一天一次。 這也需要在類似的 (上將實體聲譽徽章授予資料更新為 JSON 檔案（如果不是相同的) 排程），使其包含離開組織之員工的最新資訊。 目標是上傳最新的實體聲譽徽章授予資料，讓實體聲譽徽章授予連接器可供內幕人員風險管理解決方案使用。

您可以在 Windows 中的 [任務排程器] 應用程式每天自動執行腳本。

1. 在您的本機電腦上，按一下 [Windows **開始** ] 按鈕，然後輸入 [ **任務計畫程式**]。

2. 按一下 [工作排程器] **應用程式以** 開啟它。

3. 在 [ **動作** ] 區段中，按一下 [ **建立任務**]。

4. 在 [ **一般** ] 索引標籤上，輸入計畫任務的描述性名稱;例如， **實體聲譽徽章授予連接器腳本**。 您也可以新增選用的描述。

5. 在 [ **安全性選項**] 底下，執行下列動作：

   1. 決定只有當您登入電腦或登入時執行腳本，才可執行腳本。

   2. 請確定已選取 [以 **最高特權執行** ] 核取方塊。

6. 選取 [ **觸發器** ] 索引標籤，按一下 [ **新增**]，然後執行下列動作：

   1. 在 [ **設定**] 底下，選取 [ **每日** ] 選項，然後選擇第一次執行腳本的日期和時間。 腳本每天會在相同的指定時間。

   2. 在 [ **高級設定**] 下，確定已選取 [ **啟用** ] 核取方塊。

   3. 按一下 **[確定]**。

7. 選取 [ **動作** ] 索引標籤，按一下 [ **新增**]，然後執行下列動作：

   ![為實體聲譽徽章授予連接器腳本建立新的排程任務的動作設定](..\media\SchedulePhysicalBadgingScript1.png)

   1. 在 [ **動作** ] 下拉式清單中，確定已選取 [ **啟動程式** ]。

   2. 在 [ **程式/腳本** ] 方塊中，按一下 **[流覽]**，然後移至下列位置，並選取該位置，以便在方塊中顯示該路徑： C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe。

   3. 在 [ **新增引數 (選用)** ] 方塊中，貼上您在步驟4中執行的相同指令碼命令。 例如，.\PhysicalBadging.ps1-tenantId "d5723623-11cf-4e2e-b5a5-01d1506273g9"-appId "c12823b7-b55a-4989-faba-02de41bb97c3"-appSecret "MNubVGbcQDkGCnn"-e081f4f4-3831-48d6-7bb3-fcfab1581458 "-jsonFilePath" C:\Users\contosoadmin\Desktop\Data\physical_badging_data.csv "

   4. 在 [ **開始 (選用)** ] 方塊中，貼上您在步驟4中執行之腳本的資料夾位置。 例如，C:\Users\contosoadmin\Desktop\Scripts。

   5. 按一下 **[確定]** 儲存新動作的設定。

8. 在 [ **建立** 工作] 視窗中，按一下 **[確定** ] 以儲存排程的任務。 您可能會收到提示，請輸入您的使用者帳號憑證。

   新任務會顯示在任務排程器文件庫中。

   ![新任務會顯示在任務排程器程式庫中](..\media\SchedulePhysicalBadgingScript2.png)

最後一次執行腳本及下次排程執行的時間隨即顯示。 您可以按兩下任務進行編輯。

您也可以在「規範中心」的對應實體聲譽徽章授予連接器的浮出頁面上，驗證腳本上次執行的時間。