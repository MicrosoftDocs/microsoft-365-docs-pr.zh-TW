---
title: 將保管人大量新增至高級 eDiscovery 案例
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
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ROBOTS: NOINDEX, NOFOLLOW
description: 使用大量新增工具，將多個保管人及其相關聯的資料來源快速新增至高級 eDiscovery 中的案例。
ms.openlocfilehash: 921d4a1616d97f2adde7e40baa5c73f607c849b6
ms.sourcegitcommit: 956dd3f87adb4e6173517550a662c3bacc2d2d79
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44741639"
---
# <a name="bulk-add-custodians-to-an-advanced-ediscovery-case"></a>將保管人大量新增至高級 eDiscovery 案例

針對涉及許多保管人的高級 eDiscovery 案例，您可以一次匯入多個保管人，其中包含將其新增至案例的所有必要資訊。

## <a name="bulk-add-custodians"></a>大量新增保管人

1. 輸入 case，然後流覽至 [**來源**] 索引標籤。

2. 按一下 [匯**入保管人**]

3. 在飛入頁面上，按一下 [**下載空白範本**] 以下載 CSV 保管人範本檔案。

4. 將 custodial 資訊新增至 CSV 檔案，並將它儲存在您的本機電腦上。 如需 CSV 檔案中屬性的相關資訊，請參閱下一節。

5. 在 [**來源**] 索引標籤上，再次按一下 [匯**入保管人**]。 
6. 在飛入頁面上，按一下 **[流覽]** 並上傳您的 CSV 檔案。

   在上傳 CSV 檔案之後，會在 [**工作**] 索引標籤上建立並顯示 BulkAddCustodian 工作。工作會驗證保管人及其對應的資料來源，然後將其新增至案例的 [**來源**] 頁面上的 [**保管人**] 索引標籤。

## <a name="custodian-csv-file"></a>保管人 CSV 檔案

下載 CSV 範本之後，您可以在每個資料列中新增保管人及其資料來源。 請確定不要變更標頭列中的欄名稱。

| 欄名稱|描述|
|:------- |:------------------------------------------------------------|
|**保管人 ContactEmail**     | 保管人的 UPN 電子郵件。 範例： sarad@onmicrosoft.contoso.com           |
|**已啟用 Exchange** | TRUE/FALSE 值是否要新增保管人的信箱。      |
|**OneDrive 啟用** | TRUE/FALSE 值，表示是否要為商務帳戶新增保管人的 OneDrive。 |
|**為 OnHold**        | TRUE/FALSE 值，表示是否要將保管人置於保留狀態。       |
|**Workload1 類型**         | String 值，表示要與保管人關聯的資料來源類型。 <br />可能的值包括： <br />ExchangeMailbox, SharePointSite, TeamsMailbox, TeamsSite, YammerMailbox, YammerSite |
|**Workload1 位置**     | 視您的工作量類型而定，這會是工作負載的資料位置（例如，Exchange 信箱的電子郵件地址或 SharePoint 網站的 URL）。 |
|||

以下是具有保管人資訊之 CSV 檔案的範例：  

| ContactEmail      | 已啟用 Exchange | OneDrive 啟用 | 為 OnHold | Workload1 類型 | Workload1 位置             |
| ----------------- | ---------------- | ---------------- | --------- | -------------- | ------------------------------ |
|sarad@onmicrosoft.contoso.com | TRUE             | TRUE             | TRUE      | SharePointSite | https://contoso.sharepoint.com |
|pillarp@onmicrosoft.contoso.com | TRUE             | TRUE             | TRUE      | |  |
||||||

## <a name="custodian-and-data-source-validation"></a>保管人和資料來源驗證

當您上傳保管人 CSV 檔案時，Advanced eDiscovery 會執行下列作業：

1. 驗證保管人及其資料來源。 

2. 索引每個保管人的所有資料來源，並將其保留（如果 [是 OnHold] 屬性設定為 TRUE）。

### <a name="custodian-validation"></a>保管人驗證

目前，我們只支援匯入 Azure Active Directory （AAD）中的保管人。

我們會使用 CSV 檔案中 [**連絡人電子郵件**] 欄中的 UPN 值，驗證及尋找保管人。 已驗證的保管人會自動新增至案例，並列于案例的 [**來源**] 頁面上的 [**保管人**] 索引標籤上。 如果系統管理員無法驗證，則會在案例中的 [**工作**] 索引標籤上列出之 BulkAddCustodian 工作的錯誤記錄中列出。 Unvalidated 保管人不會新增至案例。

### <a name="data-source-validation"></a>資料來源驗證

在驗證並新增保管人後，每個與保管人相關聯的資料來源都會得到驗證。 如果找不到保管人的任何資料來源，則**未驗證**的值會顯示在該保管人的 [**保管人**] 索引標籤上的 [已**驗證**] 欄中。

### <a name="remediating-unvalidated-data-sources"></a>修正 unvalidated 資料來源

若要使用 unvalidated 資料來源修正保管人： 

1. 在 [**保管人**] 索引標籤上，選取未驗證的系統管理員。

2. 在 [保管人彈出] 頁面上，滾動至 [**資料來源**] 區段，以查看與保管人相關聯的資料來源。 已列出已驗證及 unvalidated 的資料來源。

3. 在 [**資料來源**] 區段中，按一下 [**編輯**]。

4. 在 [**選擇 custodial 位置**] 頁面上，移除 unvalidated 資料來源。

5. 在 [**選取其他位置**] 頁面上，按一下 [**更新**]，以新增保管人的其他資料來源。
