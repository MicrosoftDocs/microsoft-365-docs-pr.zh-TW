---
title: 設定連接器以匯入人力資源資料
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: 管理員可以設定資料連線器，將員工資料從組織的人力資源（HR）系統匯入 Microsoft 365。 這可讓您使用「內幕風險管理」原則中的 HR 資料，協助您偵測可能會對組織造成內部威脅之特定使用者的活動。
ms.openlocfilehash: 0febd13003cdcb80867bd7f5b91ac482a463895a
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/30/2020
ms.locfileid: "46527585"
---
# <a name="set-up-a-connector-to-import-hr-data-preview"></a>設定連接器以匯入 HR 資料（預覽）

您可以設定 Microsoft 365 規範中心內的資料連線器，以匯入與事件相關的人力資源（HR）資料，例如使用者的辭職程度或使用者工作階層中的變更。 「[內部使用者風險管理」解決方案](insider-risk-management.md)會利用這種 HR 資料來產生風險指示器，以協助您識別組織內使用者可能的惡意活動或資料竊取。

設定資料指標以取得可供內幕風險管理原則用來產生風險指示器的工作，包含建立包含 HR 資料的 CSV 檔案。在 Azure Active Directory 中建立用於驗證的應用程式，並在 Microsoft 365 規範中心內建立 HR 資料連線器，然後在 CSV 檔案中以 ingests 的 HR 資料來執行腳本，使其可供內幕人士使用。風險管理解決方案。

## <a name="before-you-begin"></a>開始之前

- 決定要匯入 Microsoft 365 的人力資源案例和資料。 這將協助您決定需要建立的 CSV 檔案和 HR 連接器數目，以及如何產生及構造 CSV 檔案。 您所匯入的 HR 資料是由您想要執行的「內幕風險管理」原則所決定。 如需詳細資訊，請參閱步驟1。

- 決定如何從組織的 HR 系統（定期）取得或匯出資料，並將其新增至您在步驟1中建立的 CSV 檔案。 您在步驟4中執行的腳本會將 CSV 檔案中的 HR 資料上傳至 Microsoft 雲端。

- 您的組織必須同意允許 Office 365 匯入服務存取您組織中的資料。 若要同意此要求，請移至[此頁面](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)，使用 Microsoft 365 全域管理員的認證登入，然後接受要求。 您必須完成此步驟，才可在步驟3中成功建立 HR 連接器。

- 在步驟3中建立 HR 連接器的使用者，必須在 Exchange Online 中指派「信箱匯入匯出」角色。 依預設，此角色不會指派給 Exchange Online 內的任何角色群組。 您可以將信箱匯入匯出角色新增至 Exchange Online 中的「組織管理」角色群組。 或者，您可以建立新的角色群組、指派信箱匯入匯出角色，然後將適當的使用者新增為成員。 如需詳細資訊，請參閱「管理 Exchange Online 中的角色群組」一文中的 [[建立角色群組](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)或[修改角色群組](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)] 區段。

- 您在步驟4中執行的範例腳本會將您的 HR 資料上傳至 Microsoft 雲端，以供內部使用者風險管理解決方案使用。 在任何 Microsoft standard support 計畫或服務下，都不支援此範例腳本。 範例腳本是以不含任何類型擔保的方式提供。 Microsoft 另外不承擔任何明示或默示的擔保，包括但不限於適售性或適合某特定用途的默示擔保。 因使用或效能範例腳本及檔的整體風險，仍然保留給您。 Microsoft、其作者以及其他與建置、生產或交付程式碼相關的任何人在任何情況下皆完全不需對任何損失負責任，包括但不限於商業利潤損失、業務中斷、業務資訊損失、或其他錢財損失等因使用或無法使用範例指令碼或文件所發生的損失，即使 Microsoft 曾建議這些損失發生的可能性。

## <a name="step-1-prepare-a-csv-file-with-your-hr-data"></a>步驟1：使用 HR 資料準備 CSV 檔案

第一步是建立 CSV 檔案，該檔案包含連接器將匯入 Microsoft 365 的 HR 資料。 此資料將會由有問必答風險解決方案用來產生潛在的風險指示器。 下列 HR 案例的資料可匯入至 Microsoft 365：

- 員工辭職。 離開組織之使用者的相關資訊。

- 工作層級變更。 使用者工作層級變更的相關資訊，例如促銷及降級。

- 效能檢查。 使用者效能的相關資訊。

- 效能改進計畫。 有關使用者之效能改進計畫的資訊。

要匯入的 HR 資料類型，取決於您要執行的「內幕風險管理」原則和對應的原則範本。 下表顯示每個原則範本所需的 HR 資料類型：

| **原則範本**| **HR 資料類型**|
|:-----------------------------------------------|:---------------------------------------------------------------------|
| 由去聲使用者竊取資料                   | 員工 resignations                                                 |
| 一般資料洩漏                              | 不適用                                                        |
| 依優先使用者的資料洩漏                    | 不適用                                                        |
| 因不滿使用者的資料洩漏                 | 工作層級變更、效能檢查、效能改進計畫 |
| 一般安全性原則違規              | 不適用                                                        |
| 脫離使用者的安全性原則違規   | 員工 resignations                                                 |
| 依優先順序的使用者所破壞的安全性原則    | 不適用                                                        |
| 不滿的使用者違反安全性原則 | 工作層級變更、效能檢查、效能改進計畫 |
| 電子郵件中的冒犯性語言                     | 不適用                                                        |

如需有關有問必答風險管理之原則範本的詳細資訊，請參閱[有問必答風險管理原則](insider-risk-management-policies.md#policy-templates)。

針對每個 HR 案例，您必須在一或多個 CSV 檔案中提供對應的 HR 資料。 您的有問必答風險管理執行所要使用的 CSV 檔案數目，將于本節稍後討論。

使用必要的 HR 資料建立 CSV 檔案之後，請將它儲存在您在步驟4中執行腳本的本機電腦上。 您也應該執行更新策略，以確保 CSV 檔案永遠包含最新的資訊，以便您執行腳本時，最新的 HR 資料會上傳至 Microsoft 雲端，並可供內幕人員風險管理解決方案存取。

> [!IMPORTANT]
> 下列各節所述的資料列名稱不是必要參數，只是範例。 您可以在 CSV 檔案中使用任何欄名稱。 不過，當您在步驟3中建立 HR 連接器時，您在 CSV 檔案中使用的欄名*必須*對應至資料類型。 另外請注意，下列各節中的範例 CSV 檔案會顯示在 [記事本] 視圖中。 在 Microsoft Excel 中查看和編輯 CSV 檔案的方式很簡單。

下列各節說明每個 HR 案例所需的 CSV 資料。

### <a name="csv-file-for-employee-resignation-data"></a>員工辭職資料的 CSV 檔案

以下是員工辭職資料之 CSV 檔案的範例。

```text
EmailAddress,ResignationDate,LastWorkingDate
sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,2019-04-29T15:18:02.4675041+05:30
pilarp@contoso.com,2019-04-24T09:15:49Z,2019-04-29T15:18:02.7117540
```

下表說明 CSV 檔案中的每一欄，以取得員工辭職資料。

| **欄**  |  **描述**|
|:------------|:----------------|
|**EmailAddress**| 指定終止之使用者的電子郵件地址（UPN）。|
| **ResignationDate** | 指定使用者正式終止組織中使用者雇傭的日期。 例如，這可能是使用者提供有關離開組織之通知的日期。 此日期可能不同于人員的最後一天的工作日期。 您必須使用下列日期格式： `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm` ，也就是[ISO 8601 的日期和時間格式](https://www.iso.org/iso-8601-date-and-time-format.html)。|
| **LastWorkingDate** | 為終止的使用者指定最後一天的工作。 您必須使用下列日期格式： `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm` ，也就是[ISO 8601 的日期和時間格式](https://www.iso.org/iso-8601-date-and-time-format.html)。|
|||

### <a name="csv-file-for-job-level-changes-data"></a>用於工作層級變更資料的 CSV 檔案

以下是適用于工作層級變更資料的 CSV 檔案的範例。

```text
EmailAddress,EffectiveDate,OldLevel,NewLevel
sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,Level 61 – Sr. Manager,Level 60- Manager
pillar@contoso.com,2019-04-23T15:18:02.4675041+05:30,Level 62 – Director,Level 60- Sr. Manager
```

下表說明 CSV 檔案中的每一欄的工作層級變更資料。

| **欄**|**描述**|
|:--------- |:------------- |
| **EmailAddress**  | 指定使用者的電子郵件地址（UPN）。|
| **EffectiveDate** | 指定使用者工作層級正式變更的日期。 您必須使用下列日期格式： `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm` ，也就是[ISO 8601 的日期和時間格式](https://www.iso.org/iso-8601-date-and-time-format.html)。|
| **備註**| 指定評估程式所提供之工作層級變更的批註。 這是一個 text 參數，其限制為200個字元。 這是選用的參數。 您不需要將其包含在 CSV 檔案中。|
| **OldLevel**| 會指定使用者的工作層級之後變更。 這是自由 text 參數，可以包含您組織的階層式分類。 這是選用的參數。 您不需要將其包含在 CSV 檔案中。|
| **NewLevel**| 指定使用者在變更後的工作層級。 這是自由 text 參數，可以包含您組織的階層式分類。 這是選用的參數。 您不需要將其包含在 CSV 檔案中。|
|||

### <a name="csv-file-for-performance-review-data"></a>用於效能檢查資料的 CSV 檔案

以下是一個用於效能資料之 CSV 檔案的範例。

```text
EmailAddress,EffectiveDate,Remarks,Rating
sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,Met expectations but bad attitude,2-Below expectation
pillar@contoso.com,2019-04-23T15:18:02.4675041+05:30, Multiple conflicts with the team
```

下表說明用於效能檢查資料之 CSV 檔案中的每一欄。

| **欄**|**描述**|
|:----------|:--------------|
| **EmailAddress**  | 指定使用者的電子郵件地址（UPN）。|
| **EffectiveDate** | 指定使用者正式獲悉其效能檢查結果的日期。 這可以是效能考核週期結束的日期。 您必須使用下列日期格式： `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm` ，也就是[ISO 8601 的日期和時間格式](https://www.iso.org/iso-8601-date-and-time-format.html)。|
| **備註**| 指定評估程式為使用者提供的任何評語，以進行績效審查。 這是一個 text 參數，其限制為200個字元。 這是選用的參數。 您不需要將其包含在 CSV 檔案中。|
| **評級**| 會指定績效審查所提供的評級。 這是一個 text 參數，可以包含您的組織用來辨識評估的任何自由格式的文字。 例如，"3 符合預期" 或 "2 低於平均"。 這是文本參數，最大限制為25個字元。 這是選用的參數。 您不需要將其包含在 CSV 檔案中。|
|||

### <a name="csv-file-for-performance-improvement-plan-data"></a>效能改善計畫資料的 CSV 檔案

以下是性能改進計畫資料之資料的 CSV 檔案的範例。

```text
EmailAddress,EffectiveDate,ImprovementRemarks,PerformanceRating
sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,Met expectation but bad attitude,2-Below expectation
pillar@contoso.com,2019-04-23T15:18:02.4675041+05:30, Multiple conflicts with the team
```

下表說明用於效能檢查資料之 CSV 檔案中的每一欄。

| **欄**| **描述**|
|:----------|:---------------|
| **EmailAddress**  | 指定使用者的電子郵件地址（UPN）。|
| **EffectiveDate** | 指定使用者正式獲悉其績效改進計畫的日期。 您必須使用下列日期格式： `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm` ，也就是[ISO 8601 的日期和時間格式](https://www.iso.org/iso-8601-date-and-time-format.html)。|
| **備註**| 指定評估程式已提供有關效能改進計畫的任何批註。 這是一個 text 參數，其限制為200個字元。 這是選用的參數。 您不需要將其包含在 CSV 檔案中。 |
| **評級**| 會指定任何與效能檢查相關的評級或其他資訊。 效能改進計畫。 這是一個 text 參數，可以包含您的組織用來辨識評估的任何自由格式文字。 例如，"3 符合預期" 或 "2 低於平均"。 這是最大值為25個字元的 text 參數。 這是選用的參數。 您不需要將其包含在 CSV 檔案中。|
|||

### <a name="determining-how-many-csv-files-to-use-for-hr-data"></a>決定 HR 資料使用的 CSV 檔案數目

在步驟3中，您可以選擇為每個 HR 資料類型建立不同的連接器，也可以選擇為所有資料類型建立單一連接器。 您可以使用個別的 CSV 檔案，其中包含一個 HR 案例的資料（如先前各節所述 CSV 檔案的範例）。 或者，您可以使用單一 CSV 檔案，其中包含兩個或多個 HR 案例的資料。 以下是一些指導方針，可協助您判斷要用於 HR 資料的 CSV 檔案數目。

- 如果您想要執行的內幕風險管理原則需要多個 HR 資料類型，請考慮使用包含所有必要資料類型的單一 CSV 檔案。

- 產生或收集 HR 資料的方法可能會決定 CSV 檔案的數目。 例如，如果用來設定 HR 連接器的不同類型的 HR 資料位於組織的單一 HR 系統中，您可以將資料匯出到單一 CSV 檔案。 不過，如果資料分散在不同的 HR 系統，則將資料匯出至不同的 CSV 檔案可能會比較容易。 例如，員工辭職資料可能位於與工作層級或效能檢查資料不同的人力資源系統中。 在此情況下，使用個別的 CSV 檔案會比較容易，而不必手動將資料合併成單一 CSV 檔案。 因此，您從 HR 系統中取得或匯出資料的方式，可能會決定所需的 CSV 檔案數目。

- 一般來說，您需要建立的 HR 連接器數目取決於 CSV 檔案中的資料類型。 例如，如果 CSV 檔案包含支援您的有問必答風險管理執行所需的所有資料類型，則您只需要一個 HR 連接器。 不過，如果您有兩個不同的 CSV 檔案，每個檔案都包含單一資料型別，則必須建立兩個 HR 連接器。 例外情況是，如果您將**HRScenario**欄新增至 CSV 檔案（請參閱下一節），您可以設定單一 HR 連接器來處理不同的 CSV 檔案。

### <a name="configuring-a-single-csv-file-for-multiple-hr-data-types"></a>設定多個 HR 資料類型的單一 CSV 檔案

您可以將多個 HR 資料類型新增至單一 CSV 檔案。 如果您所執行的有問必答風險管理解決方案需要多個 HR 資料類型，或者資料類型位於組織中的單一 HR 系統中，這會很有用。 保留較少的 CSV 檔案，可讓您建立及管理較少的 HR 連接器。

以下是設定具有多種資料類型之 CSV 檔案的必要條件：

- 您必須針對每個資料類型和標頭列中對應的資料行名稱，新增必要的欄（和選用）。 如果資料類型未對應至資料行，您可以將該值保留空白。

- 若要使用具有多種 HR 資料類型的 CSV 檔案，HR 連接器必須知道 CSV 檔案中的哪些列包含 HR 資料類型。 若要完成此工作，可將其他**HRScenario**欄新增至 CSV 檔案。 此欄中的值會識別每一列中 HR 資料的類型。 例如，對應至四個 HR 案例的值可能會是 \` 辭職 \` 、 \` 工作層級變更 \` 、 \` 績效審查 \` 和 \` 效能改進計畫 \` 。

- 如果您有多個 CSV 檔案包含 HRScenario * * 欄，請確定每個檔案都使用相同的欄名稱及識別特定 HR 案例的相同值。

下列範例會顯示包含**HRScenario**欄的 CSV 檔案。 [HRScenario] 欄中的值會識別對應列中的資料類型。

```text
HRScenario,EmailAddress,ResignationDate,LastWorkingDate,EffectiveDate,Remarks,Rating,OldLevel,NewLevel
Resignation,sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,2019-04-29T15:18:02.4675041+05:30,,,,
Resignation,pilarp@contoso.com,2019-04-24T09:15:49Z,2019-04-29T15:18:02.7117540,,,,
Job level change,sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,,,,,Level 61 Sr. Manager, Level 60 Manager
Job level change,pillarp@contoso.com,2019-04-23T15:18:02.4675041+05:30,,,,,Level 62 Director,Level 60 Sr Manager
Performance review,sarad@contoso.com,,,2019-04-23T15:18:02.4675041+05:30,Met expectation but bad attitude,2 Below expectations,,
Performance review,pillarp@contoso.com,,,2019-04-23T15:18:02.4675041+05:30, Multiple conflicts with the team,,
Performance improvement plan,sarad@contoso.com,,,2019-04-23T15:18:02.4675041+05:30,Met expectations but bad attitude,2 Below expectations,,
Performance improvement plan,pillarp@contoso.com,,,2019-04-23T15:18:02.4675041+05:30,Multiple conflicts with the team,,
```

> [!NOTE]
> 您可以針對識別 HR 資料類型的欄使用任何名稱，因為您會將 CSV 檔案中欄的名稱對應為當您在步驟3中設定連接器時識別 HR 資料類型的資料行。 當您設定連接器時，也會對應用於 [資料類型] 欄的值。

### <a name="adding-the-hrscenario-column-to-a-csv-file-that-contains-a-single-data-type"></a>將 HRScenario 欄新增至包含單一資料類型的 CSV 檔案

根據組織的 HR 系統，以及如何將人力資源資料匯出至 CSV 檔案，您可能必須建立包含單一 HR 資料類型的多個 CSV 檔案。 在此情況下，您仍然可以建立單一 HR 連接器，以從不同的 CSV 檔案匯入資料。 若要這樣做，您只需要將 HRScenario 欄新增至 CSV 檔案，並指定 HR 資料類型。 然後，您可以針對每個 CSV 檔案執行腳本，但為連接器使用相同的工作識別碼。 請參閱[步驟 4](#step-4-run-the-sample-script-to-upload-your-hr-data)。

## <a name="step-2-create-an-app-in-azure-active-directory"></a>步驟2：在 Azure Active Directory 中建立應用程式

下一步是在 Azure Active Directory （AAD）中建立及註冊新的應用程式。 應用程式會對應至您在步驟3中建立的 HR 連接器。 建立此應用程式可讓 AAD 在執行時驗證 HR 連接器，並嘗試存取您的組織。 此應用程式也會用來驗證您在步驟4中執行的腳本，將 HR 資料上傳至 Microsoft 雲端。 在建立此 AAD 應用程式期間，請務必儲存下列資訊。 這些值將會在步驟3和步驟4中使用。

- AAD 應用程式識別碼（也稱為「*應用程式識別碼*」或「*用戶端識別碼*」）

- AAD 應用程式機密（也稱為*用戶端密碼*）

- 租使用者識別碼（也稱為*目錄識別碼*）

如需在 AAD 中建立應用程式的逐步指示，請參閱[使用 Microsoft identity Platform 註冊應用程式](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app)。

## <a name="step-3-create-the-hr-connector"></a>步驟3：建立 HR 連接器

下一步是在 Microsoft 365 規範中心內建立 HR 連接器。 在步驟4中執行腳本後，您建立的 HR 連接器會將 HR 資料從 CSV 檔案中攝取至您的 Microsoft 365 組織。 建立連接器之前，請確定您有一個 HR 案例清單，以及每個案例的對應 CSV 欄名稱。 設定連接器時，您必須將每個案例所需的資料對應到 CSV 檔案中的實際欄名稱。 或者，您可以在設定連接器時上傳範例 CSV 檔案，嚮導會協助您將欄的名稱對應至所需的資料類型。

完成此步驟後，請務必複製當您建立連接器時所產生的工作識別碼。 當您執行腳本時，您會使用工作識別碼。

1. 移至 [https://compliance.microsoft.com](https://compliance.microsoft.com/) ，然後按一下左側導覽中的 [**資料連線器**]。

2. 在 [**資料連線器（預覽）** ] 下的 [ **HR**] 頁面上，按一下 [ **View**]。

3. 在**HR 自訂**頁面上，按一下 [**新增連接器**]。

4. 在 [**安裝程式**] 頁面上，執行下列動作，然後按 **[下一步]**：

   a. 針對您在步驟2中建立的 Azure 應用程式，輸入或貼上 AAD 應用程式識別碼。

   b. 輸入 HR 連接器的名稱。

5. 在 [HR 案例] 頁面上，選取您要匯入資料的一或多個 HR 案例，然後按 **[下一步]**。

6. 在 [檔對應方法] 頁面上，選取下列其中一個選項，然後按 **[下一步]**。

   - **上傳範例**檔案。 如果您選取此選項，請按一下 **[上傳範例**檔案]，上傳您在步驟1中準備好的 CSV 檔案。 此選項可讓您快速從下拉式清單中選取 CSV 檔案中的欄名，將其對應至先前所選取之 HR 案例的資料類型。

   OR

   - **手動提供對應的詳細資料**。 如果您選取此選項，則必須在 CSV 檔案中輸入欄的名稱，才能將其對應至先前所選取之 HR 案例的資料類型。

7. 在 [檔案對應詳細資料] 頁面上，根據您上傳的範例 CSV 檔案，以及是否要設定單一 HR 案例或多個案例的連接器，執行下列其中一項作業。 如果您上傳的範例檔案，您不需要輸入欄名稱。 您可以從下拉式清單中選取。

    - 如果您在上一個步驟中選取了單一 HR 案例，請從您在步驟1中在每個適當的方塊中所建立的 CSV 檔案輸入欄標題名稱（也稱為*參數*）。 您輸入的資料列名稱不區分大小寫，但如果 CSV 檔案中的欄名稱包含空格，請務必要包含空格。 如先前所述，您在這些方塊中輸入的名稱必須符合 CSV 檔案中的參數名稱。 例如，下列螢幕擷取畫面顯示步驟1中所示的員工辭職 HR 案例之範例 CSV 檔案的參數名稱。

    - [！注意] 如果您在上述步驟中選取了 [多個資料類型]，則必須輸入識別碼欄名稱，以在 CSV 檔案中識別 HR 資料類型。 在輸入識別碼欄名稱後，請輸入識別此 HR 資料類型的值，然後輸入您在步驟1中為每個選取之資料類型的每個適當方塊中所建立之 CSV 檔所選取之資料類型的欄標頭名稱。 如先前所述，您在這些方塊中輸入的名稱必須符合 CSV 檔案中的欄名。

8. 在 [**複查**] 頁面上，複查您的設定，然後按一下 **[完成]** 以建立連接器。

   隨即會顯示 [狀態] 頁面，確認已建立連接器。 此頁面包含兩個重要事項，您必須完成下一個步驟，才可執行範例腳本以上傳 HR 資料。

   ![查看具有工作識別碼的頁面，並連結至 github 的範例腳本](../media/HRConnector_Confirmation.png)

   a. **工作識別碼。** 在下一個步驟中，您將需要此工作識別碼來執行腳本。 您可以從這個頁面或從 [連接器飛出] 頁面複製此頁面。

   b. **範例腳本的連結。** 按一下 [**這裡**] 連結，移至 GitHub 網站以存取範例腳本（此連結會開啟新的視窗）。 將此視窗保持開啟，以便您可以在步驟4中複製腳本。 或者，您也可以將目的地做成書簽或複製 URL，以便在您執行腳本時可再次存取它。 您也可以在 [連接器] 飛入頁面上使用此連結。

9. 按一下 **[完成]**。

   新的連接器會顯示在 [**連接器**] 索引標籤上的清單中。

10. 按一下剛才建立的 HR connector，以顯示飛出頁面，該頁面包含有關連接器的屬性及其他資訊。

   ![新 HR 連接器的飛出頁面](../media/HRConnectorWizard7.png)

若尚未這麼做，您可以複製**Azure 應用程式識別碼**和**連接器工作識別碼**的值。 您必須在下一個步驟中執行腳本。 您也可以從飛入頁面下載腳本（或在下一個步驟中使用連結加以下載）。

您也可以按一下 [**編輯**]，以變更 Azure 應用程式識別碼或您在 [檔案**對應**] 頁面上定義的欄標頭名稱。

## <a name="step-4-run-the-sample-script-to-upload-your-hr-data"></a>步驟4：執行範例腳本以上傳 HR 資料

設定 HR 連接器的最後一個步驟是執行範例腳本，將 CSV 檔案中所建立的 HR 資料上傳至 Microsoft 雲端。 具體說來，腳本會將資料上傳到 HR 連接器。 在您執行腳本後，您在步驟3中建立的 HR 連接器會將 HR 資料匯入至您的 Microsoft 365 組織，以供其他規範工具（例如有問必答風險管理解決方案）進行存取。 在您執行腳本後，請考慮排程任務每天定期執行它，使最新的員工終止資料上傳至 Microsoft 雲端。 請參閱[排程腳本自動執行](#optional-step-6-schedule-the-script-to-run-automatically)。

1. 移至您在上一個步驟中從左開啟的視窗，以利用範例腳本存取 GitHub 網站。 或者，您也可以開啟書簽網站或使用您複製的 URL。

2. 按一下 [**原始**] 按鈕，以在文字視圖中顯示腳本。

3. 複製範例腳本中的所有行，然後將其儲存至文字檔。

4. 如有需要，修改組織的範例腳本。

5. 使用檔案名尾碼，將文字檔儲存為 Windows PowerShell script file `.ps1` ; 例如， `HRConnector.ps1` 。

6. 在您的本機電腦上開啟命令提示字元，然後移至您用來儲存腳本的目錄。

7. 執行下列命令，將 CSV 檔案中的 HR 資料上傳至 Microsoft 雲端;例如：

    ```powershell
    .\HRConnector.ps1 -tenantId <tenantId> -appId <appId>  -appSecret <appSecret>  -jobId <jobId>  -csvFilePath '<csvFilePath>'
    ```

   下表說明與此腳本搭配使用的參數及其必要的值。 您在上述步驟中取得的資訊會用於這些參數的值。

   |**參數**|**描述**
   |:-----|:-----|:-----|
   |`tenantId`|這是您在步驟2中取得之 Microsoft 365 組織的識別碼。 您也可以在 Azure AD 系統管理中心的 [**一覽**] 邊欄中取得組織的承租人識別碼。 這是用來識別您的組織。|
   |`appId` |這是您在步驟2中，您在 Azure AD 中建立之應用程式的 AAD 應用程式識別碼。 當腳本嘗試存取您的 Microsoft 365 組織時，Azure AD 可用於驗證。 | 
   |`appSecret`|這是您在步驟2中您在 Azure AD 中建立之應用程式的 AAD 應用程式機密。 這也是用來進行驗證。|
   |`jobId`|這是您在步驟3中建立之 HR 連接器的工作識別碼。 這是用來將上傳至 Microsoft 雲端的 HR 資料與 HR connector 產生關聯。|
   |`csvFilePath`|這是您在步驟1中建立之 CSV 檔案（儲存于腳本所在的相同系統）的檔案路徑。 請嘗試避免檔路徑中的空格;否則請使用單引號。|
   |||

   以下是 HR 連接器腳本語法的範例，其中每個參數都使用實際值：

   ```powershell
    .\HRConnector.ps1 -tenantId d5723623-11cf-4e2e-b5a5-01d1506273g9 -appId 29ee526e-f9a7-4e98-a682-67f41bfd643e -appSecret MNubVGbcQDkGCnn -jobId b8be4a7d-e338-43eb-a69e-c513cd458eba -csvFilePath 'C:\Users\contosoadmin\Desktop\Data\employee_termination_data.csv'
    ```

   上載成功時，腳本會顯示**上傳成功**郵件。

## <a name="step-5-monitor-the-hr-connector"></a>步驟5：監視 HR 連接器

在您建立 HR 連接器並執行腳本以上傳 HR 資料之後，您可以在 Microsoft 365 規範中心中查看連接器和上傳狀態。 如果您安排定期定期執行腳本，您也可以在上次腳本執行後，查看目前的狀態。

1. 移至 [https://compliance.microsoft.com](https://compliance.microsoft.com) 並按一下左側導覽中的 [**資料連線器**]。

2. 按一下 [**連接器**] 索引標籤，然後選取 [HR connector] 以顯示飛出頁面，該頁面包含連接器的屬性和資訊。

   ![具有屬性和狀態的 HR connector 飛出頁面](../media/HRConnectorFlyout1.png)

3. 在 [**進行**中] 下，按一下 [**下載記錄**] 連結，以開啟（或儲存）連接器的狀態記錄。 此記錄檔包含每次腳本執行的相關資訊，並將該資料從 CSV 檔案上傳至 Microsoft 雲端。 

   ![HR connector 記錄檔顯示上傳的 CSV 檔案中的列數](../media/HRConnectorLogFile.png)

   此 `RecordsSaved` 欄位會指出上傳的 CSV 檔案中的列數。 例如，如果 CSV 檔案包含四列，則欄位的值 `RecordsSaved` 為4，如果腳本成功上傳 CSV 檔案中的所有列。

如果您未在步驟4中執行腳本，則 [**最後一次匯入**] 底下會顯示下載腳本的連結。 您可以下載腳本，然後依照步驟執行腳本。

## <a name="optional-step-6-schedule-the-script-to-run-automatically"></a>選步驟6：安排腳本自動執行

為了確保您的組織中的最新 HR 資料可用於像是「內部使用者風險管理」解決方案之類的工具，我們建議您排程腳本，使其定期定期執行，例如一天一次。 這也需要以類似（如果不相同）排程的方式，在 CSV 檔案中更新 HR 資料，使其包含離開組織之員工的最新資訊。 目標是上傳最新的 HR 資料，使 HR 連接器可供「內幕人員風險管理」解決方案使用。

您可以在 Windows 中的 [任務排程器] 應用程式每天自動執行腳本。

1. 在您的本機電腦上，按一下 [Windows**開始**] 按鈕，然後輸入 [**任務計畫程式**]。

2. 按一下 [工作排程器]**應用程式以**開啟它。

3. 在 [**動作**] 區段中，按一下 [**建立任務**]。

4. 在 [**一般**] 索引標籤上，輸入計畫任務的描述性名稱;例如， **HR Connector Script**。 您也可以新增選用的描述。

5. 在 [**安全性選項**] 底下，執行下列動作：

   a. 決定只有當您登入電腦或登入時執行腳本，才可執行腳本。

   b. 請確定已選取 [以**最高特權執行**] 核取方塊。

6. 選取 [**觸發器**] 索引標籤，按一下 [**新增**]，然後執行下列動作：

   a. 在 [**設定**] 底下，選取 [**每日**] 選項，然後選擇第一次執行腳本的日期和時間。 腳本每天會在相同的指定時間。

   b. 在 [**高級設定**] 下，確定已選取 [**啟用**] 核取方塊。

   c. 按一下 **[確定]**。

7. 選取 [**動作**] 索引標籤，按一下 [**新增**]，然後執行下列動作：

   ![為 HR connector 腳本建立新的排程任務的動作設定](../media/HRConnectorScheduleTask1.png)

   a. 在 [**動作**] 下拉式清單中，確定已選取 [**啟動程式**]。

   b. 在 [**程式/腳本**] 方塊中，按一下 **[流覽]**，然後移至下列位置，並選取該位置，以便在方塊中顯示路徑： `C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe` 。

   c. 在 [**新增引數（選用）** ] 方塊中，貼上您在步驟4中執行的相同指令碼命令。 例如，`.\HRConnector.ps1 -tenantId "d5723623-11cf-4e2e-b5a5-01d1506273g9" -appId "c12823b7-b55a-4989-faba-02de41bb97c3" -appSecret "MNubVGbcQDkGCnn"  -jobId "e081f4f4-3831-48d6-7bb3-fcfab1581458" -csvFilePath "C:\Users\contosoadmin\Desktop\Data\employee_termination_data.csv"`

   d. 在 [ **Start in （optional）** ] 方塊中，貼上您在步驟4中執行之腳本的資料夾位置。 例如，`C:\Users\contosoadmin\Desktop\Scripts`。

   e. 按一下 **[確定]** 儲存新動作的設定。

8. 在 [**建立**工作] 視窗中，按一下 **[確定**] 以儲存排程的任務。 您可能會收到提示，請輸入您的使用者帳號憑證。

   新任務會顯示在任務排程器文件庫中。

   ![新任務會顯示在任務排程器程式庫中](../media/HRConnectorTaskSchedulerLibrary.png)

   最後一次執行腳本及下次排程執行的時間隨即顯示。 您可以按兩下任務進行編輯。

   您也可以在規範中心的對應 HR 連接器的浮出頁面上，確認腳本上次執行的時間。

## <a name="existing-hr-connectors"></a>現有 HR 連接器

2020年7月20日，我們發行的是 HR 連接器支援的其他案例。 以下是本文先前所述的 HR 案例。 在此日期之前建立的任何 HR 連接器都只支援員工辭職案例。 如果您在2020年7月20日之前建立 HR 連接器，我們已將其遷移，以繼續將 HR 資料移轉至 Microsoft 雲端。 您不需要執行任何動作即可維護此功能。 您可以繼續使用連接器，而不會造成任何中斷。

如果您想要執行其他 HR 案例，請建立新的 HR 連接器，並針對所發行的其他 HR 案例加以設定。 您也需要建立一個或多個包含資料的新 CSV 檔案，以支援其他 HR 案例。 在您建立新的 HR 連接器之後，請使用新的連接器及 CSV 檔案的工作識別碼（包含其他 HR 案例的資料）來執行腳本。
