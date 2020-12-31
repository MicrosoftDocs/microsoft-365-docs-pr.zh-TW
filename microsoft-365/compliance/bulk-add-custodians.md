---
title: 將保管人匯入至高級電子檔探索案例
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
description: 使用匯入工具 dto 將多個保管人和其相關聯的資料來源快速新增至高級 eDiscovery 中的案例。
ms.openlocfilehash: 65ae932fac759896690e5fa65ec1d4173439ccb6
ms.sourcegitcommit: 36d12e02f6fda199ae7f2fb72fe52d7e2b5b4efd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/31/2020
ms.locfileid: "49740300"
---
# <a name="import-custodians-to-an-advanced-ediscovery-case"></a>將保管人匯入至高級電子檔探索案例

針對涉及許多保管人的高級 eDiscovery 案例，您可以使用 CSV 檔（包含將其新增至案例所需的資訊）一次匯入多位保管人。

## <a name="import-custodians"></a>匯入保管人

1. 開啟 [Advanced eDiscovery] 案例，然後選取 [ **資料來源** ] 索引標籤。

2. 按一下 [**新增資料來源** 匯  >  **入保管人**]。

3. 在「匯 **入保管人** 」彈出頁面上，按一下 [ **下載空白範本** ] 以下載保管人範本 CSV 檔案。

   ![從匯入保管人飛入頁面下載 CSV 範本](../media/ImportCustodians1.png)

4. 將 custodial 資訊新增至 CSV 檔案，並將其儲存到本機電腦。 如需 CSV 檔案中所需之屬性的相關資訊，請參閱 [保管人 CSV](#custodian-csv-file) 檔案區段。

5. 使用保管人資訊準備好 CSV 檔案之後，請回到 [**資料來源**] 索引標籤，再按一下 [**新增資料來源** 匯  >  **入保管人**]。

6. 在「匯 **入保管人** 」彈出頁面上，按一下 **[流覽]** ，然後上傳包含保管人資訊的 CSV 檔案。

   在上傳 CSV 檔案之後，會建立名為 **BulkAddCustodian** 的工作，並顯示在 [ **工作** ] 索引標籤上。工作會驗證保管人及其相關聯的資料來源，然後將其新增至案例的 [ **資料來源** ] 頁面。

## <a name="custodian-csv-file"></a>保管人 CSV 檔案

下載 CSV 保管人範本之後，您可以在每個資料列中新增保管人及其資料來源。 請確定不要變更標頭列中的欄名稱。 使用 [工作負載類型] 和 [工作負載位置] 欄，將其他資料來源與保管人產生關聯。

| 欄名稱|描述|
|:------- |:------------------------------------------------------------|
|**保管人 contactEmail**     |管理員的 UPN 電子郵件地址。 例如，sarad@contoso.onmicrosoft.com。           |
|**已啟用 Exchange** | TRUE/FALSE 值可包含或不包含保管人的信箱。      |
|**OneDrive 啟用** | TRUE/FALSE 值可包含或不包含保管人的 OneDrive 商務帳戶。 |
|**為 OnHold**        | TRUE/FALSE 值，表示是否要將保管人資料來源保留。       |
|**Workload1 類型**         |String 值，表示要與保管人關聯的資料來源類型。 可能的值包括： <br/>- ExchangeMailbox<br/> - SharePointSite<br/>- TeamsMailbox<br/>- TeamsSite<br/> - YammerMailbox<br/>- YammerSite |
|**Workload1 位置**     | 視您的工作量類型而定，這會是資料來源的位置。 例如，Exchange 信箱的電子郵件地址或 SharePoint 網站的 URL。 |
|||

以下是具有保管人資訊之 CSV 檔案的範例：<br/><br/>

|保管人 contactEmail      | 已啟用 Exchange | OneDrive 啟用 | 為 OnHold | Workload1 類型 | Workload1 位置             |
| ----------------- | ---------------- | ---------------- | --------- | -------------- | ------------------------------ |
|robinc@onmicrosoft.contoso.com | TRUE             | TRUE             | TRUE      | SharePointSite | https://contoso.sharepoint.com |
|pillarp@onmicrosoft.contoso.com | TRUE             | TRUE             | TRUE      | |  |
||||||

## <a name="custodian-and-data-source-validation"></a>保管人和資料來源驗證

在您上傳保管人 CSV 檔案之後，Advanced eDiscovery 會執行下列其中一項：

1. 驗證保管人及其資料來源。

2. 在 CSV 檔案中的 OnHold 屬性設定為 TRUE) 時， **會** 為每個保管人的所有資料來源編制索引，並將其保留 (。

### <a name="custodian-validation"></a>保管人驗證

目前，我們只支援匯入您組織的 Azure Active Directory (Azure AD) 中所包含的保管人。

保管人匯入工具會使用 CSV 檔案中的 **保管人 contactEmail** 欄中的 UPN 值，尋找並驗證保管人。 已驗證的保管人會自動新增至案例，並列于案例的 [ **資料來源** ] 索引標籤上。 如果系統管理員無法驗證，則會在案例中的 [ **工作** ] 索引標籤上列出之 BulkAddCustodian 工作的錯誤記錄中列出。 Unvalidated 保管人不會加入到案例中或列于 [ **資料來源** ] 索引標籤上。

### <a name="data-source-validation"></a>資料來源驗證

在驗證並新增保管人後，會新增每個與保管人相關聯的主要信箱和 OneDrive 帳戶。

不過，如果找不到與系統管理員相關聯的任何其他資料來源 (例如 SharePoint 網站、Microsoft 團隊、Microsoft 365 群組或 Yammer) 群組，也不會將其指派給保管人，而且 **未驗證** 的值會顯示在 [**資料來源**] 索引標籤上的管理員旁的 [**狀態**] 欄中。

若要為保管人新增已驗證的資料來源：

1. 在 [ **資料來源** ] 索引標籤上，選取包含未驗證之資料來源的系統管理員。

2. 在 [保管人彈出] 頁面上，滾動至 [ **Custodial 位置** ] 區段，以查看與保管人相關聯的已驗證和 unvalidated 資料來源。

3. 按一下彈出頁面頂端的 [ **編輯** ]，以移除不正確資料來源或新增新的資料來源。

4. 在您移除 unvalidated 資料來源或新增新的資料來源之後，作用中 **的值會** 顯示在 [**資料來源**] 索引標籤上的保管人的 [**狀態**] 欄中。若要新增先前似乎不正確來源，請遵循下列修復步驟，以手動將其新增至保管人。

### <a name="remediating-invalid-data-sources"></a>修正不正確資料來源

若要手動新增和關聯先前不正確資料來源，請執行下列操作：

1. 在 [ **資料來源** ] 索引標籤上，選取管理員以手動新增和關聯先前不正確資料來源。

2. 按一下彈出頁面頂端的 [ **編輯** ]，將信箱、網站、小組或 Yammer 群組與保管人建立關聯。 若要執行此動作，請按一下適當資料位置類型旁的 [ **編輯** ]。

3. 按 **[下一步]** 顯示 [ **保留設定** ] 頁面，並設定您新增之資料來源的 [保留] 設定。

4. 按 **[下一步]** 顯示 [ **複查保管人** ] 頁面，然後按一下 [ **提交** ] 以儲存您的變更。
