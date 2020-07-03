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
ms.openlocfilehash: ab9626be01814fa95a959141433b431df9bf7724
ms.sourcegitcommit: 51a9f34796535309b8ca8b52da92da0a3621327b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/02/2020
ms.locfileid: "45024663"
---
# <a name="bulk-add-custodians-to-an-advanced-ediscovery-case"></a><span data-ttu-id="514ff-103">將保管人大量新增至高級 eDiscovery 案例</span><span class="sxs-lookup"><span data-stu-id="514ff-103">Bulk-add custodians to an Advanced eDiscovery case</span></span>

<span data-ttu-id="514ff-104">針對涉及許多保管人的高級 eDiscovery 案例，您可以一次匯入多個保管人，其中包含將其新增至案例的所有必要資訊。</span><span class="sxs-lookup"><span data-stu-id="514ff-104">For Advanced eDiscovery cases that involve a lot of custodians, you can import multiple custodians at once by a CSV file that contains all the information necessary to add them to a case.</span></span>

## <a name="bulk-add-custodians"></a><span data-ttu-id="514ff-105">大量新增保管人</span><span class="sxs-lookup"><span data-stu-id="514ff-105">Bulk-add custodians</span></span>

1. <span data-ttu-id="514ff-106">輸入 case，然後流覽至 [**來源**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="514ff-106">Enter case and navigate to the **Sources** tab.</span></span>

2. <span data-ttu-id="514ff-107">按一下 [匯**入保管人**]</span><span class="sxs-lookup"><span data-stu-id="514ff-107">Click **Import custodians**</span></span>

3. <span data-ttu-id="514ff-108">在飛入頁面上，按一下 [**下載空白範本**] 以下載 CSV 保管人範本檔案。</span><span class="sxs-lookup"><span data-stu-id="514ff-108">On the flyout page, click **Download a blank template** to download a CSV custodian template file.</span></span>

4. <span data-ttu-id="514ff-109">將 custodial 資訊新增至 CSV 檔案，並將它儲存在您的本機電腦上。</span><span class="sxs-lookup"><span data-stu-id="514ff-109">Add the custodial information to the CSV file and save it on your local computer.</span></span> <span data-ttu-id="514ff-110">如需 CSV 檔案中屬性的相關資訊，請參閱下一節。</span><span class="sxs-lookup"><span data-stu-id="514ff-110">See the next section for information about the properties in the CSV file.</span></span>

5. <span data-ttu-id="514ff-111">在 [**來源**] 索引標籤上，再次按一下 [匯**入保管人**]。</span><span class="sxs-lookup"><span data-stu-id="514ff-111">On the **Sources** tab, click **Import Custodians** again.</span></span>

6. <span data-ttu-id="514ff-112">在飛入頁面上，按一下 **[流覽]** 並上傳您的 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="514ff-112">On flyout page, click **Browse** and the upload your CSV file.</span></span>

   <span data-ttu-id="514ff-113">在上傳 CSV 檔案之後，會在 [**工作**] 索引標籤上建立並顯示 BulkAddCustodian 工作。工作會驗證保管人及其對應的資料來源，然後將其新增至案例的 [**來源**] 頁面上的 [**保管人**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="514ff-113">After the CSV file is uploaded, a BulkAddCustodian job is created and displayed on the **Jobs** tab. The job validates the custodians and their corresponding data sources and then adds them to the **Custodians** tab on the **Sources** page of the case.</span></span>

## <a name="custodian-csv-file"></a><span data-ttu-id="514ff-114">保管人 CSV 檔案</span><span class="sxs-lookup"><span data-stu-id="514ff-114">Custodian CSV file</span></span>

<span data-ttu-id="514ff-115">下載 CSV 範本之後，您可以在每個資料列中新增保管人及其資料來源。</span><span class="sxs-lookup"><span data-stu-id="514ff-115">After you download the CSV template, you can add custodians and their data source in each row.</span></span> <span data-ttu-id="514ff-116">請確定不要變更標頭列中的欄名稱。</span><span class="sxs-lookup"><span data-stu-id="514ff-116">Be sure not to change the column names in the header row.</span></span>

| <span data-ttu-id="514ff-117">欄名稱</span><span class="sxs-lookup"><span data-stu-id="514ff-117">Column name</span></span>|<span data-ttu-id="514ff-118">描述</span><span class="sxs-lookup"><span data-stu-id="514ff-118">Description</span></span>|
|:------- |:------------------------------------------------------------|
|<span data-ttu-id="514ff-119">**保管人 ContactEmail**</span><span class="sxs-lookup"><span data-stu-id="514ff-119">**Custodian ContactEmail**</span></span>     | <span data-ttu-id="514ff-120">保管人的 UPN 電子郵件。</span><span class="sxs-lookup"><span data-stu-id="514ff-120">UPN email of custodian.</span></span> <span data-ttu-id="514ff-121">範例： sarad@onmicrosoft.contoso.com</span><span class="sxs-lookup"><span data-stu-id="514ff-121">Example: sarad@onmicrosoft.contoso.com</span></span>           |
|<span data-ttu-id="514ff-122">**已啟用 Exchange**</span><span class="sxs-lookup"><span data-stu-id="514ff-122">**Exchange Enabled**</span></span> | <span data-ttu-id="514ff-123">TRUE/FALSE 值是否要新增保管人的信箱。</span><span class="sxs-lookup"><span data-stu-id="514ff-123">TRUE/FALSE value on whether to add custodian's mailbox.</span></span>      |
|<span data-ttu-id="514ff-124">**OneDrive 啟用**</span><span class="sxs-lookup"><span data-stu-id="514ff-124">**OneDrive Enabled**</span></span> | <span data-ttu-id="514ff-125">TRUE/FALSE 值，表示是否要為商務帳戶新增保管人的 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="514ff-125">TRUE/FALSE value on whether to add custodian's OneDrive for Business account.</span></span> |
|<span data-ttu-id="514ff-126">**為 OnHold**</span><span class="sxs-lookup"><span data-stu-id="514ff-126">**Is OnHold**</span></span>        | <span data-ttu-id="514ff-127">TRUE/FALSE 值，表示是否要將保管人置於保留狀態。</span><span class="sxs-lookup"><span data-stu-id="514ff-127">TRUE/FALSE value on whether to place custodian on hold.</span></span>       |
|<span data-ttu-id="514ff-128">**Workload1 類型**</span><span class="sxs-lookup"><span data-stu-id="514ff-128">**Workload1 Type**</span></span>         | <span data-ttu-id="514ff-129">String 值，表示要與保管人關聯的資料來源類型。</span><span class="sxs-lookup"><span data-stu-id="514ff-129">String value indicating the type of data source to associate with the custodian.</span></span> <br /><span data-ttu-id="514ff-130">可能的值包括：</span><span class="sxs-lookup"><span data-stu-id="514ff-130">Possible values include:</span></span> <br /><span data-ttu-id="514ff-131">ExchangeMailbox, SharePointSite, TeamsMailbox, TeamsSite, YammerMailbox, YammerSite</span><span class="sxs-lookup"><span data-stu-id="514ff-131">ExchangeMailbox, SharePointSite, TeamsMailbox, TeamsSite, YammerMailbox, YammerSite</span></span> |
|<span data-ttu-id="514ff-132">**Workload1 位置**</span><span class="sxs-lookup"><span data-stu-id="514ff-132">**Workload1 Location**</span></span>     | <span data-ttu-id="514ff-133">視您的工作量類型而定，這會是工作負載的資料位置（例如，Exchange 信箱的電子郵件地址或 SharePoint 網站的 URL）。</span><span class="sxs-lookup"><span data-stu-id="514ff-133">Depending on your workload type, this would be the data location of your workload (for example, the email address of an Exchange mailbox or the URL for a SharePoint site).</span></span> |
|||

<span data-ttu-id="514ff-134">以下是具有保管人資訊之 CSV 檔案的範例：</span><span class="sxs-lookup"><span data-stu-id="514ff-134">Here's an example of a CSV file with custodian information:</span></span>  

| <span data-ttu-id="514ff-135">ContactEmail</span><span class="sxs-lookup"><span data-stu-id="514ff-135">ContactEmail</span></span>      | <span data-ttu-id="514ff-136">已啟用 Exchange</span><span class="sxs-lookup"><span data-stu-id="514ff-136">Exchange Enabled</span></span> | <span data-ttu-id="514ff-137">OneDrive 啟用</span><span class="sxs-lookup"><span data-stu-id="514ff-137">OneDrive Enabled</span></span> | <span data-ttu-id="514ff-138">為 OnHold</span><span class="sxs-lookup"><span data-stu-id="514ff-138">Is OnHold</span></span> | <span data-ttu-id="514ff-139">Workload1 類型</span><span class="sxs-lookup"><span data-stu-id="514ff-139">Workload1 Type</span></span> | <span data-ttu-id="514ff-140">Workload1 位置</span><span class="sxs-lookup"><span data-stu-id="514ff-140">Workload1 Location</span></span>             |
| ----------------- | ---------------- | ---------------- | --------- | -------------- | ------------------------------ |
|<span data-ttu-id="514ff-141">sarad@onmicrosoft.contoso.com</span><span class="sxs-lookup"><span data-stu-id="514ff-141">sarad@onmicrosoft.contoso.com</span></span> | <span data-ttu-id="514ff-142">TRUE</span><span class="sxs-lookup"><span data-stu-id="514ff-142">TRUE</span></span>             | <span data-ttu-id="514ff-143">TRUE</span><span class="sxs-lookup"><span data-stu-id="514ff-143">TRUE</span></span>             | <span data-ttu-id="514ff-144">TRUE</span><span class="sxs-lookup"><span data-stu-id="514ff-144">TRUE</span></span>      | <span data-ttu-id="514ff-145">SharePointSite</span><span class="sxs-lookup"><span data-stu-id="514ff-145">SharePointSite</span></span> | https://contoso.sharepoint.com |
|<span data-ttu-id="514ff-146">pillarp@onmicrosoft.contoso.com</span><span class="sxs-lookup"><span data-stu-id="514ff-146">pillarp@onmicrosoft.contoso.com</span></span> | <span data-ttu-id="514ff-147">TRUE</span><span class="sxs-lookup"><span data-stu-id="514ff-147">TRUE</span></span>             | <span data-ttu-id="514ff-148">TRUE</span><span class="sxs-lookup"><span data-stu-id="514ff-148">TRUE</span></span>             | <span data-ttu-id="514ff-149">TRUE</span><span class="sxs-lookup"><span data-stu-id="514ff-149">TRUE</span></span>      | |  |
||||||

## <a name="custodian-and-data-source-validation"></a><span data-ttu-id="514ff-150">保管人和資料來源驗證</span><span class="sxs-lookup"><span data-stu-id="514ff-150">Custodian and data source validation</span></span>

<span data-ttu-id="514ff-151">當您上傳保管人 CSV 檔案時，Advanced eDiscovery 會執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="514ff-151">When you upload the custodian CSV file, Advanced eDiscovery does the following things:</span></span>

1. <span data-ttu-id="514ff-152">驗證保管人及其資料來源。</span><span class="sxs-lookup"><span data-stu-id="514ff-152">Validates the custodians and their data sources.</span></span> 

2. <span data-ttu-id="514ff-153">索引每個保管人的所有資料來源，並將其保留（如果 [是 OnHold] 屬性設定為 TRUE）。</span><span class="sxs-lookup"><span data-stu-id="514ff-153">Indexes all data sources for each custodian and places them on hold (if the Is OnHold property is set to TRUE).</span></span>

### <a name="custodian-validation"></a><span data-ttu-id="514ff-154">保管人驗證</span><span class="sxs-lookup"><span data-stu-id="514ff-154">Custodian validation</span></span>

<span data-ttu-id="514ff-155">目前，我們只支援匯入 Azure Active Directory （AAD）中的保管人。</span><span class="sxs-lookup"><span data-stu-id="514ff-155">Currently, we only support importing custodians that are in Azure Active Directory (AAD).</span></span>

<span data-ttu-id="514ff-156">我們會使用 CSV 檔案中 [**連絡人電子郵件**] 欄中的 UPN 值，驗證及尋找保管人。</span><span class="sxs-lookup"><span data-stu-id="514ff-156">We validate and find custodians using the UPN value in the **Contact Email** column in the CSV file.</span></span> <span data-ttu-id="514ff-157">已驗證的保管人會自動新增至案例，並列于案例的 [**來源**] 頁面上的 [**保管人**] 索引標籤上。</span><span class="sxs-lookup"><span data-stu-id="514ff-157">Custodians that are validated are automatically added to the case and listed on the **Custodian** tab on the **Sources** page of the case.</span></span> <span data-ttu-id="514ff-158">如果系統管理員無法驗證，則會在案例中的 [**工作**] 索引標籤上列出之 BulkAddCustodian 工作的錯誤記錄中列出。</span><span class="sxs-lookup"><span data-stu-id="514ff-158">If a custodian can't be validated, they are listed in the error log for the BulkAddCustodian job that is listed on the **Jobs** tab in the case.</span></span> <span data-ttu-id="514ff-159">Unvalidated 保管人不會新增至案例。</span><span class="sxs-lookup"><span data-stu-id="514ff-159">Unvalidated custodians are not added to the case.</span></span>

### <a name="data-source-validation"></a><span data-ttu-id="514ff-160">資料來源驗證</span><span class="sxs-lookup"><span data-stu-id="514ff-160">Data source validation</span></span>

<span data-ttu-id="514ff-161">在驗證並新增保管人後，每個與保管人相關聯的資料來源都會得到驗證。</span><span class="sxs-lookup"><span data-stu-id="514ff-161">After custodians are validated and added to the case, each data source that's associated with a custodian is validated.</span></span> <span data-ttu-id="514ff-162">如果找不到保管人的任何資料來源，則**未驗證**的值會顯示在該保管人的 [**保管人**] 索引標籤上的 [已**驗證**] 欄中。</span><span class="sxs-lookup"><span data-stu-id="514ff-162">If any data source for a custodian can't be found, the value **Not validated** would be displayed in the **Validated** column on the **Custodian** tab for that custodian.</span></span>

### <a name="remediating-unvalidated-data-sources"></a><span data-ttu-id="514ff-163">修正 unvalidated 資料來源</span><span class="sxs-lookup"><span data-stu-id="514ff-163">Remediating unvalidated data sources</span></span>

<span data-ttu-id="514ff-164">若要使用 unvalidated 資料來源修正保管人：</span><span class="sxs-lookup"><span data-stu-id="514ff-164">To remediate custodians with unvalidated data sources:</span></span> 

1. <span data-ttu-id="514ff-165">在 [**保管人**] 索引標籤上，選取未驗證的系統管理員。</span><span class="sxs-lookup"><span data-stu-id="514ff-165">On the **Custodian** tab, select a custodian who isn't validated.</span></span>

2. <span data-ttu-id="514ff-166">在 [保管人彈出] 頁面上，滾動至 [**資料來源**] 區段，以查看與保管人相關聯的資料來源。</span><span class="sxs-lookup"><span data-stu-id="514ff-166">On the custodian flyout page, scroll to the **Data sources** section to view the data sources that are associated with custodian.</span></span> <span data-ttu-id="514ff-167">已列出已驗證及 unvalidated 的資料來源。</span><span class="sxs-lookup"><span data-stu-id="514ff-167">Both validated and unvalidated data sources are listed.</span></span>

3. <span data-ttu-id="514ff-168">在 [**資料來源**] 區段中，按一下 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="514ff-168">In the **Data sources** section, click **Edit**.</span></span>

4. <span data-ttu-id="514ff-169">在 [**選擇 custodial 位置**] 頁面上，移除 unvalidated 資料來源。</span><span class="sxs-lookup"><span data-stu-id="514ff-169">On the **Choose custodial locations** page, remove an unvalidated data source.</span></span>

5. <span data-ttu-id="514ff-170">在 [**選取其他位置**] 頁面上，按一下 [**更新**]，以新增保管人的其他資料來源。</span><span class="sxs-lookup"><span data-stu-id="514ff-170">On the **Select additional locations** page, click **Update** to add additional data sources for a custodian.</span></span>
