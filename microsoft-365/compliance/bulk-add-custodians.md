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
# <a name="import-custodians-to-an-advanced-ediscovery-case"></a><span data-ttu-id="55c26-103">將保管人匯入至高級電子檔探索案例</span><span class="sxs-lookup"><span data-stu-id="55c26-103">Import custodians to an Advanced eDiscovery case</span></span>

<span data-ttu-id="55c26-104">針對涉及許多保管人的高級 eDiscovery 案例，您可以使用 CSV 檔（包含將其新增至案例所需的資訊）一次匯入多位保管人。</span><span class="sxs-lookup"><span data-stu-id="55c26-104">For Advanced eDiscovery cases that involve many custodians, you can import multiple custodians at once by using a CSV file that contains the information necessary to add them to a case.</span></span>

## <a name="import-custodians"></a><span data-ttu-id="55c26-105">匯入保管人</span><span class="sxs-lookup"><span data-stu-id="55c26-105">Import custodians</span></span>

1. <span data-ttu-id="55c26-106">開啟 [Advanced eDiscovery] 案例，然後選取 [ **資料來源** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="55c26-106">Open the Advanced eDiscovery case and select the **Data sources** tab.</span></span>

2. <span data-ttu-id="55c26-107">按一下 [**新增資料來源** 匯  >  **入保管人**]。</span><span class="sxs-lookup"><span data-stu-id="55c26-107">Click **Add data source** > **Import custodians**.</span></span>

3. <span data-ttu-id="55c26-108">在「匯 **入保管人** 」彈出頁面上，按一下 [ **下載空白範本** ] 以下載保管人範本 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="55c26-108">On the **Import custodians** flyout page, click **Download a blank template** to download a custodian template CSV file.</span></span>

   ![從匯入保管人飛入頁面下載 CSV 範本](../media/ImportCustodians1.png)

4. <span data-ttu-id="55c26-110">將 custodial 資訊新增至 CSV 檔案，並將其儲存到本機電腦。</span><span class="sxs-lookup"><span data-stu-id="55c26-110">Add the custodial information to the CSV file and save it to your local computer.</span></span> <span data-ttu-id="55c26-111">如需 CSV 檔案中所需之屬性的相關資訊，請參閱 [保管人 CSV](#custodian-csv-file) 檔案區段。</span><span class="sxs-lookup"><span data-stu-id="55c26-111">See the [Custodian CSV file](#custodian-csv-file) section for information about the required properties in the CSV file.</span></span>

5. <span data-ttu-id="55c26-112">使用保管人資訊準備好 CSV 檔案之後，請回到 [**資料來源**] 索引標籤，再按一下 [**新增資料來源** 匯  >  **入保管人**]。</span><span class="sxs-lookup"><span data-stu-id="55c26-112">After you've prepared the CSV file with the custodian information, go back to the **Data sources** tab, and click **Add data source** > **Import custodians** again.</span></span>

6. <span data-ttu-id="55c26-113">在「匯 **入保管人** 」彈出頁面上，按一下 **[流覽]** ，然後上傳包含保管人資訊的 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="55c26-113">On the **Import custodians** flyout page, click **Browse** and then upload the CSV file that contains the custodian information.</span></span>

   <span data-ttu-id="55c26-114">在上傳 CSV 檔案之後，會建立名為 **BulkAddCustodian** 的工作，並顯示在 [ **工作** ] 索引標籤上。工作會驗證保管人及其相關聯的資料來源，然後將其新增至案例的 [ **資料來源** ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="55c26-114">After the CSV file is uploaded, a job named **BulkAddCustodian** is created and displayed on the **Jobs** tab. The job validates the custodians and their associated data sources and then adds them to the **Data sources** page of the case.</span></span>

## <a name="custodian-csv-file"></a><span data-ttu-id="55c26-115">保管人 CSV 檔案</span><span class="sxs-lookup"><span data-stu-id="55c26-115">Custodian CSV file</span></span>

<span data-ttu-id="55c26-116">下載 CSV 保管人範本之後，您可以在每個資料列中新增保管人及其資料來源。</span><span class="sxs-lookup"><span data-stu-id="55c26-116">After you download the CSV custodian template, you can add custodians and their data source in each row.</span></span> <span data-ttu-id="55c26-117">請確定不要變更標頭列中的欄名稱。</span><span class="sxs-lookup"><span data-stu-id="55c26-117">Be sure not to change the column names in the header row.</span></span> <span data-ttu-id="55c26-118">使用 [工作負載類型] 和 [工作負載位置] 欄，將其他資料來源與保管人產生關聯。</span><span class="sxs-lookup"><span data-stu-id="55c26-118">Use the workload type and workload location columns to associate other data sources to a custodian.</span></span>

| <span data-ttu-id="55c26-119">欄名稱</span><span class="sxs-lookup"><span data-stu-id="55c26-119">Column name</span></span>|<span data-ttu-id="55c26-120">描述</span><span class="sxs-lookup"><span data-stu-id="55c26-120">Description</span></span>|
|:------- |:------------------------------------------------------------|
|<span data-ttu-id="55c26-121">**保管人 contactEmail**</span><span class="sxs-lookup"><span data-stu-id="55c26-121">**Custodian contactEmail**</span></span>     |<span data-ttu-id="55c26-122">管理員的 UPN 電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="55c26-122">The custodian's UPN email address.</span></span> <span data-ttu-id="55c26-123">例如，sarad@contoso.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="55c26-123">For example, sarad@contoso.onmicrosoft.com.</span></span>           |
|<span data-ttu-id="55c26-124">**已啟用 Exchange**</span><span class="sxs-lookup"><span data-stu-id="55c26-124">**Exchange Enabled**</span></span> | <span data-ttu-id="55c26-125">TRUE/FALSE 值可包含或不包含保管人的信箱。</span><span class="sxs-lookup"><span data-stu-id="55c26-125">TRUE/FALSE value to include or not include the custodian's mailbox.</span></span>      |
|<span data-ttu-id="55c26-126">**OneDrive 啟用**</span><span class="sxs-lookup"><span data-stu-id="55c26-126">**OneDrive Enabled**</span></span> | <span data-ttu-id="55c26-127">TRUE/FALSE 值可包含或不包含保管人的 OneDrive 商務帳戶。</span><span class="sxs-lookup"><span data-stu-id="55c26-127">TRUE/FALSE value to include or not included the custodian's OneDrive for Business account.</span></span> |
|<span data-ttu-id="55c26-128">**為 OnHold**</span><span class="sxs-lookup"><span data-stu-id="55c26-128">**Is OnHold**</span></span>        | <span data-ttu-id="55c26-129">TRUE/FALSE 值，表示是否要將保管人資料來源保留。</span><span class="sxs-lookup"><span data-stu-id="55c26-129">TRUE/FALSE value to indicate whether to place the custodian data sources on hold.</span></span>       |
|<span data-ttu-id="55c26-130">**Workload1 類型**</span><span class="sxs-lookup"><span data-stu-id="55c26-130">**Workload1 Type**</span></span>         |<span data-ttu-id="55c26-131">String 值，表示要與保管人關聯的資料來源類型。</span><span class="sxs-lookup"><span data-stu-id="55c26-131">String value indicating the type of data source to associate with the custodian.</span></span> <span data-ttu-id="55c26-132">可能的值包括：</span><span class="sxs-lookup"><span data-stu-id="55c26-132">Possible values include:</span></span> <br/><span data-ttu-id="55c26-133">- ExchangeMailbox</span><span class="sxs-lookup"><span data-stu-id="55c26-133">- ExchangeMailbox</span></span><br/> <span data-ttu-id="55c26-134">- SharePointSite</span><span class="sxs-lookup"><span data-stu-id="55c26-134">- SharePointSite</span></span><br/><span data-ttu-id="55c26-135">- TeamsMailbox</span><span class="sxs-lookup"><span data-stu-id="55c26-135">- TeamsMailbox</span></span><br/><span data-ttu-id="55c26-136">- TeamsSite</span><span class="sxs-lookup"><span data-stu-id="55c26-136">- TeamsSite</span></span><br/> <span data-ttu-id="55c26-137">- YammerMailbox</span><span class="sxs-lookup"><span data-stu-id="55c26-137">- YammerMailbox</span></span><br/><span data-ttu-id="55c26-138">- YammerSite</span><span class="sxs-lookup"><span data-stu-id="55c26-138">- YammerSite</span></span> |
|<span data-ttu-id="55c26-139">**Workload1 位置**</span><span class="sxs-lookup"><span data-stu-id="55c26-139">**Workload1 Location**</span></span>     | <span data-ttu-id="55c26-140">視您的工作量類型而定，這會是資料來源的位置。</span><span class="sxs-lookup"><span data-stu-id="55c26-140">Depending on your workload type, this would be the location of the data source.</span></span> <span data-ttu-id="55c26-141">例如，Exchange 信箱的電子郵件地址或 SharePoint 網站的 URL。</span><span class="sxs-lookup"><span data-stu-id="55c26-141">For example, the email address for an Exchange mailbox or the URL for a SharePoint site.</span></span> |
|||

<span data-ttu-id="55c26-142">以下是具有保管人資訊之 CSV 檔案的範例：</span><span class="sxs-lookup"><span data-stu-id="55c26-142">Here's an example of a CSV file with custodian information:</span></span><br/><br/>

|<span data-ttu-id="55c26-143">保管人 contactEmail</span><span class="sxs-lookup"><span data-stu-id="55c26-143">Custodian contactEmail</span></span>      | <span data-ttu-id="55c26-144">已啟用 Exchange</span><span class="sxs-lookup"><span data-stu-id="55c26-144">Exchange Enabled</span></span> | <span data-ttu-id="55c26-145">OneDrive 啟用</span><span class="sxs-lookup"><span data-stu-id="55c26-145">OneDrive Enabled</span></span> | <span data-ttu-id="55c26-146">為 OnHold</span><span class="sxs-lookup"><span data-stu-id="55c26-146">Is OnHold</span></span> | <span data-ttu-id="55c26-147">Workload1 類型</span><span class="sxs-lookup"><span data-stu-id="55c26-147">Workload1 Type</span></span> | <span data-ttu-id="55c26-148">Workload1 位置</span><span class="sxs-lookup"><span data-stu-id="55c26-148">Workload1 Location</span></span>             |
| ----------------- | ---------------- | ---------------- | --------- | -------------- | ------------------------------ |
|<span data-ttu-id="55c26-149">robinc@onmicrosoft.contoso.com</span><span class="sxs-lookup"><span data-stu-id="55c26-149">robinc@onmicrosoft.contoso.com</span></span> | <span data-ttu-id="55c26-150">TRUE</span><span class="sxs-lookup"><span data-stu-id="55c26-150">TRUE</span></span>             | <span data-ttu-id="55c26-151">TRUE</span><span class="sxs-lookup"><span data-stu-id="55c26-151">TRUE</span></span>             | <span data-ttu-id="55c26-152">TRUE</span><span class="sxs-lookup"><span data-stu-id="55c26-152">TRUE</span></span>      | <span data-ttu-id="55c26-153">SharePointSite</span><span class="sxs-lookup"><span data-stu-id="55c26-153">SharePointSite</span></span> | https://contoso.sharepoint.com |
|<span data-ttu-id="55c26-154">pillarp@onmicrosoft.contoso.com</span><span class="sxs-lookup"><span data-stu-id="55c26-154">pillarp@onmicrosoft.contoso.com</span></span> | <span data-ttu-id="55c26-155">TRUE</span><span class="sxs-lookup"><span data-stu-id="55c26-155">TRUE</span></span>             | <span data-ttu-id="55c26-156">TRUE</span><span class="sxs-lookup"><span data-stu-id="55c26-156">TRUE</span></span>             | <span data-ttu-id="55c26-157">TRUE</span><span class="sxs-lookup"><span data-stu-id="55c26-157">TRUE</span></span>      | |  |
||||||

## <a name="custodian-and-data-source-validation"></a><span data-ttu-id="55c26-158">保管人和資料來源驗證</span><span class="sxs-lookup"><span data-stu-id="55c26-158">Custodian and data source validation</span></span>

<span data-ttu-id="55c26-159">在您上傳保管人 CSV 檔案之後，Advanced eDiscovery 會執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="55c26-159">After you upload the custodian CSV file, Advanced eDiscovery does the following things:</span></span>

1. <span data-ttu-id="55c26-160">驗證保管人及其資料來源。</span><span class="sxs-lookup"><span data-stu-id="55c26-160">Validates the custodians and their data sources.</span></span>

2. <span data-ttu-id="55c26-161">在 CSV 檔案中的 OnHold 屬性設定為 TRUE) 時， **會** 為每個保管人的所有資料來源編制索引，並將其保留 (。</span><span class="sxs-lookup"><span data-stu-id="55c26-161">Indexes all data sources for each custodian and places them on hold (if the **Is OnHold** property in the CSV file is set to TRUE).</span></span>

### <a name="custodian-validation"></a><span data-ttu-id="55c26-162">保管人驗證</span><span class="sxs-lookup"><span data-stu-id="55c26-162">Custodian validation</span></span>

<span data-ttu-id="55c26-163">目前，我們只支援匯入您組織的 Azure Active Directory (Azure AD) 中所包含的保管人。</span><span class="sxs-lookup"><span data-stu-id="55c26-163">Currently, we only support importing custodians that are included in your organization's Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="55c26-164">保管人匯入工具會使用 CSV 檔案中的 **保管人 contactEmail** 欄中的 UPN 值，尋找並驗證保管人。</span><span class="sxs-lookup"><span data-stu-id="55c26-164">The custodian import tool finds and validates custodians using the UPN value in the **Custodian contactEmail** column in the CSV file.</span></span> <span data-ttu-id="55c26-165">已驗證的保管人會自動新增至案例，並列于案例的 [ **資料來源** ] 索引標籤上。</span><span class="sxs-lookup"><span data-stu-id="55c26-165">Custodians that are validated are automatically added to the case and listed on the **Data sources** tab of the case.</span></span> <span data-ttu-id="55c26-166">如果系統管理員無法驗證，則會在案例中的 [ **工作** ] 索引標籤上列出之 BulkAddCustodian 工作的錯誤記錄中列出。</span><span class="sxs-lookup"><span data-stu-id="55c26-166">If a custodian can't be validated, they are listed in the error log for the BulkAddCustodian job that is listed on the **Jobs** tab in the case.</span></span> <span data-ttu-id="55c26-167">Unvalidated 保管人不會加入到案例中或列于 [ **資料來源** ] 索引標籤上。</span><span class="sxs-lookup"><span data-stu-id="55c26-167">Unvalidated custodians are not added to the case or listed on the **Data sources** tab.</span></span>

### <a name="data-source-validation"></a><span data-ttu-id="55c26-168">資料來源驗證</span><span class="sxs-lookup"><span data-stu-id="55c26-168">Data source validation</span></span>

<span data-ttu-id="55c26-169">在驗證並新增保管人後，會新增每個與保管人相關聯的主要信箱和 OneDrive 帳戶。</span><span class="sxs-lookup"><span data-stu-id="55c26-169">After custodians are validated and added to the case, each primary mailbox and OneDrive account that's associated with a custodian is added.</span></span>

<span data-ttu-id="55c26-170">不過，如果找不到與系統管理員相關聯的任何其他資料來源 (例如 SharePoint 網站、Microsoft 團隊、Microsoft 365 群組或 Yammer) 群組，也不會將其指派給保管人，而且 **未驗證** 的值會顯示在 [**資料來源**] 索引標籤上的管理員旁的 [**狀態**] 欄中。</span><span class="sxs-lookup"><span data-stu-id="55c26-170">However, if any of the other data sources (such as SharePoint sites, Microsoft Teams, Microsoft 365 Groups, or Yammer groups) associated with a custodian can't be found, none of them are assigned to the custodian and the value **Not validated** is displayed in the **Status** column next to the custodian on the **Data sources** tab.</span></span>

<span data-ttu-id="55c26-171">若要為保管人新增已驗證的資料來源：</span><span class="sxs-lookup"><span data-stu-id="55c26-171">To add validated data sources for a custodian:</span></span>

1. <span data-ttu-id="55c26-172">在 [ **資料來源** ] 索引標籤上，選取包含未驗證之資料來源的系統管理員。</span><span class="sxs-lookup"><span data-stu-id="55c26-172">On the **Data sources** tab, select a custodian that contains data sources that aren't validated.</span></span>

2. <span data-ttu-id="55c26-173">在 [保管人彈出] 頁面上，滾動至 [ **Custodial 位置** ] 區段，以查看與保管人相關聯的已驗證和 unvalidated 資料來源。</span><span class="sxs-lookup"><span data-stu-id="55c26-173">On the custodian flyout page, scroll to the **Custodial locations** section to view both validated and unvalidated data sources that are associated with custodian.</span></span>

3. <span data-ttu-id="55c26-174">按一下彈出頁面頂端的 [ **編輯** ]，以移除不正確資料來源或新增新的資料來源。</span><span class="sxs-lookup"><span data-stu-id="55c26-174">Click **Edit** at the top of the flyout page to remove invalid data sources or add new ones.</span></span>

4. <span data-ttu-id="55c26-175">在您移除 unvalidated 資料來源或新增新的資料來源之後，作用中 **的值會** 顯示在 [**資料來源**] 索引標籤上的保管人的 [**狀態**] 欄中。若要新增先前似乎不正確來源，請遵循下列修復步驟，以手動將其新增至保管人。</span><span class="sxs-lookup"><span data-stu-id="55c26-175">After you remove unvalidated data sources or add a new one, the value **Active** is displayed in **Status** column for the custodian on the **Data sources** tab. To add sources that previously appeared to be invalid, follow the remediation steps below to manually add them to a custodian.</span></span>

### <a name="remediating-invalid-data-sources"></a><span data-ttu-id="55c26-176">修正不正確資料來源</span><span class="sxs-lookup"><span data-stu-id="55c26-176">Remediating invalid data sources</span></span>

<span data-ttu-id="55c26-177">若要手動新增和關聯先前不正確資料來源，請執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="55c26-177">To manually add and associate a data source that was previously invalid:</span></span>

1. <span data-ttu-id="55c26-178">在 [ **資料來源** ] 索引標籤上，選取管理員以手動新增和關聯先前不正確資料來源。</span><span class="sxs-lookup"><span data-stu-id="55c26-178">On the **Data sources** tab, select a custodian to manually add and associate a data source that was previously invalid.</span></span>

2. <span data-ttu-id="55c26-179">按一下彈出頁面頂端的 [ **編輯** ]，將信箱、網站、小組或 Yammer 群組與保管人建立關聯。</span><span class="sxs-lookup"><span data-stu-id="55c26-179">Click **Edit** at the top of the flyout page to associate mailboxes, sites, Teams, or Yammer groups to the custodian.</span></span> <span data-ttu-id="55c26-180">若要執行此動作，請按一下適當資料位置類型旁的 [ **編輯** ]。</span><span class="sxs-lookup"><span data-stu-id="55c26-180">Do this by clicking **Edit** next to the appropriate data location type.</span></span>

3. <span data-ttu-id="55c26-181">按 **[下一步]** 顯示 [ **保留設定** ] 頁面，並設定您新增之資料來源的 [保留] 設定。</span><span class="sxs-lookup"><span data-stu-id="55c26-181">Click **Next** to display the **Hold settings** page and configure the hold setting for the data sources you added.</span></span>

4. <span data-ttu-id="55c26-182">按 **[下一步]** 顯示 [ **複查保管人** ] 頁面，然後按一下 [ **提交** ] 以儲存您的變更。</span><span class="sxs-lookup"><span data-stu-id="55c26-182">Click **Next** to display the **Review custodians** page, and then click **Submit** to save your changes.</span></span>
