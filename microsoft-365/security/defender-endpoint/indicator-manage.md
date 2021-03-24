---
title: 管理指示器
ms.reviewer: ''
description: 管理檔雜湊、IP 位址、URLs 或網域的指標，以定義實體的偵測、預防和排除。
keywords: import，標記，list，ioc，csv，管理，允許，封鎖，封鎖，clean，惡意，檔案雜湊，ip 位址，url，網域
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6edb4ddf764788a11ea3b6f1863dd95e694f1849
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060115"
---
# <a name="manage-indicators"></a><span data-ttu-id="45e76-104">管理指示器</span><span class="sxs-lookup"><span data-stu-id="45e76-104">Manage indicators</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="45e76-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="45e76-105">**Applies to:**</span></span>
- [<span data-ttu-id="45e76-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="45e76-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="45e76-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="45e76-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="45e76-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="45e76-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="45e76-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="45e76-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)


1. <span data-ttu-id="45e76-110">在功能窗格中，選取 [**設定**  >  **指示器**]。</span><span class="sxs-lookup"><span data-stu-id="45e76-110">In the navigation pane, select **Settings** > **Indicators**.</span></span>

2. <span data-ttu-id="45e76-111">選取您想要管理之實體類型的索引標籤。</span><span class="sxs-lookup"><span data-stu-id="45e76-111">Select the tab of the entity type you'd like to manage.</span></span>  

3. <span data-ttu-id="45e76-112">更新指示器的詳細資料，然後按一下 [ **儲存** ]，如果您想要從清單中移除該實體，請按一下 [ **刪除** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="45e76-112">Update the details of the indicator and click **Save** or click the **Delete** button if you'd like to remove the entity from the list.</span></span>

## <a name="import-a-list-of-iocs"></a><span data-ttu-id="45e76-113">匯入 IoCs 清單</span><span class="sxs-lookup"><span data-stu-id="45e76-113">Import a list of IoCs</span></span>

<span data-ttu-id="45e76-114">您也可以選擇上載 CSV 檔，以定義指示器的屬性、要採取的動作和其他詳細資料。</span><span class="sxs-lookup"><span data-stu-id="45e76-114">You can also choose to upload a CSV file that defines the attributes of indicators, the action to be taken, and other details.</span></span>

<span data-ttu-id="45e76-115">下載範例 CSV，以瞭解支援的欄屬性。</span><span class="sxs-lookup"><span data-stu-id="45e76-115">Download the sample CSV to know the supported column attributes.</span></span>

1. <span data-ttu-id="45e76-116">在功能窗格中，選取 [**設定**  >  **指示器**]。</span><span class="sxs-lookup"><span data-stu-id="45e76-116">In the navigation pane, select **Settings** > **Indicators**.</span></span>

2. <span data-ttu-id="45e76-117">選取您要匯入指示器之實體類型的索引標籤。</span><span class="sxs-lookup"><span data-stu-id="45e76-117">Select the tab of the entity type you'd like to import indicators for.</span></span>

3. <span data-ttu-id="45e76-118">選取 [匯 **入**  >  **選擇** 檔案]。</span><span class="sxs-lookup"><span data-stu-id="45e76-118">Select **Import** > **Choose file**.</span></span> 

4. <span data-ttu-id="45e76-119">選取 [匯入]。</span><span class="sxs-lookup"><span data-stu-id="45e76-119">Select **Import**.</span></span> <span data-ttu-id="45e76-120">針對您想要匯入的所有檔案執行這項操作。</span><span class="sxs-lookup"><span data-stu-id="45e76-120">Do this for all the files you'd like to import.</span></span> 

5. <span data-ttu-id="45e76-121">選取 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="45e76-121">Select **Done**.</span></span>

<span data-ttu-id="45e76-122">下表顯示支援的參數。</span><span class="sxs-lookup"><span data-stu-id="45e76-122">The following table shows the supported parameters.</span></span>

<span data-ttu-id="45e76-123">參數</span><span class="sxs-lookup"><span data-stu-id="45e76-123">Parameter</span></span> | <span data-ttu-id="45e76-124">類型</span><span class="sxs-lookup"><span data-stu-id="45e76-124">Type</span></span>    |   <span data-ttu-id="45e76-125">描述</span><span class="sxs-lookup"><span data-stu-id="45e76-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="45e76-126">indicatorType</span><span class="sxs-lookup"><span data-stu-id="45e76-126">indicatorType</span></span> | <span data-ttu-id="45e76-127">Enum</span><span class="sxs-lookup"><span data-stu-id="45e76-127">Enum</span></span> | <span data-ttu-id="45e76-128">指標的類型。</span><span class="sxs-lookup"><span data-stu-id="45e76-128">Type of the indicator.</span></span> <span data-ttu-id="45e76-129">可能的值為： "FileSha1"、"FileSha256"、"IpAddress"、"DomainName" 和 "Url"。</span><span class="sxs-lookup"><span data-stu-id="45e76-129">Possible values are: "FileSha1", "FileSha256", "IpAddress", "DomainName" and "Url".</span></span> <span data-ttu-id="45e76-130">**Required**</span><span class="sxs-lookup"><span data-stu-id="45e76-130">**Required**</span></span>
<span data-ttu-id="45e76-131">indicatorValue</span><span class="sxs-lookup"><span data-stu-id="45e76-131">indicatorValue</span></span> | <span data-ttu-id="45e76-132">字串</span><span class="sxs-lookup"><span data-stu-id="45e76-132">String</span></span> | <span data-ttu-id="45e76-133">[指示器](ti-indicator.md)實體的身分識別。</span><span class="sxs-lookup"><span data-stu-id="45e76-133">Identity of the [Indicator](ti-indicator.md) entity.</span></span> <span data-ttu-id="45e76-134">**Required**</span><span class="sxs-lookup"><span data-stu-id="45e76-134">**Required**</span></span>
<span data-ttu-id="45e76-135">action</span><span class="sxs-lookup"><span data-stu-id="45e76-135">action</span></span> | <span data-ttu-id="45e76-136">Enum</span><span class="sxs-lookup"><span data-stu-id="45e76-136">Enum</span></span> | <span data-ttu-id="45e76-137">將在組織中探索指示器時所採取的動作。</span><span class="sxs-lookup"><span data-stu-id="45e76-137">The action that will be taken if the indicator will be discovered in the organization.</span></span> <span data-ttu-id="45e76-138">可能的值為： "Alert"、"AlertAndBlock" 和 "允許"。</span><span class="sxs-lookup"><span data-stu-id="45e76-138">Possible values are: "Alert", "AlertAndBlock", and "Allowed".</span></span> <span data-ttu-id="45e76-139">**Required**</span><span class="sxs-lookup"><span data-stu-id="45e76-139">**Required**</span></span>
<span data-ttu-id="45e76-140">標題</span><span class="sxs-lookup"><span data-stu-id="45e76-140">title</span></span> | <span data-ttu-id="45e76-141">String</span><span class="sxs-lookup"><span data-stu-id="45e76-141">String</span></span> | <span data-ttu-id="45e76-142">指示器警示標題。</span><span class="sxs-lookup"><span data-stu-id="45e76-142">Indicator alert title.</span></span> <span data-ttu-id="45e76-143">**Required**</span><span class="sxs-lookup"><span data-stu-id="45e76-143">**Required**</span></span>
<span data-ttu-id="45e76-144">描述</span><span class="sxs-lookup"><span data-stu-id="45e76-144">description</span></span> | <span data-ttu-id="45e76-145">字串</span><span class="sxs-lookup"><span data-stu-id="45e76-145">String</span></span> |  <span data-ttu-id="45e76-146">標記的描述。</span><span class="sxs-lookup"><span data-stu-id="45e76-146">Description of the indicator.</span></span> <span data-ttu-id="45e76-147">**Required**</span><span class="sxs-lookup"><span data-stu-id="45e76-147">**Required**</span></span>
<span data-ttu-id="45e76-148">expirationTime</span><span class="sxs-lookup"><span data-stu-id="45e76-148">expirationTime</span></span> | <span data-ttu-id="45e76-149">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="45e76-149">DateTimeOffset</span></span> | <span data-ttu-id="45e76-150">指示器的到期時間，格式為 YYYY-MM-DDTHH： MM： SS。0Z。</span><span class="sxs-lookup"><span data-stu-id="45e76-150">The expiration time of the indicator in the following format YYYY-MM-DDTHH:MM:SS.0Z.</span></span> <span data-ttu-id="45e76-151">**Optional**</span><span class="sxs-lookup"><span data-stu-id="45e76-151">**Optional**</span></span>
<span data-ttu-id="45e76-152">嚴重性</span><span class="sxs-lookup"><span data-stu-id="45e76-152">severity</span></span> | <span data-ttu-id="45e76-153">Enum</span><span class="sxs-lookup"><span data-stu-id="45e76-153">Enum</span></span> | <span data-ttu-id="45e76-154">指標的嚴重性。</span><span class="sxs-lookup"><span data-stu-id="45e76-154">The severity of the indicator.</span></span> <span data-ttu-id="45e76-155">可能的值為：「資訊」、「低」、「中」和「高」。</span><span class="sxs-lookup"><span data-stu-id="45e76-155">Possible values are: "Informational", "Low", "Medium" and "High".</span></span> <span data-ttu-id="45e76-156">**Optional**</span><span class="sxs-lookup"><span data-stu-id="45e76-156">**Optional**</span></span>
<span data-ttu-id="45e76-157">recommendedActions</span><span class="sxs-lookup"><span data-stu-id="45e76-157">recommendedActions</span></span> | <span data-ttu-id="45e76-158">字串</span><span class="sxs-lookup"><span data-stu-id="45e76-158">String</span></span> | <span data-ttu-id="45e76-159">TI 指標警示建議的動作。</span><span class="sxs-lookup"><span data-stu-id="45e76-159">TI indicator alert recommended actions.</span></span> <span data-ttu-id="45e76-160">**Optional**</span><span class="sxs-lookup"><span data-stu-id="45e76-160">**Optional**</span></span>
<span data-ttu-id="45e76-161">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="45e76-161">rbacGroupNames</span></span> | <span data-ttu-id="45e76-162">字串</span><span class="sxs-lookup"><span data-stu-id="45e76-162">String</span></span> | <span data-ttu-id="45e76-163">標記將套用到的 RBAC 群組名稱的以逗號分隔的清單。</span><span class="sxs-lookup"><span data-stu-id="45e76-163">Comma-separated list of RBAC group names the indicator would be applied to.</span></span> <span data-ttu-id="45e76-164">**Optional**</span><span class="sxs-lookup"><span data-stu-id="45e76-164">**Optional**</span></span>
<span data-ttu-id="45e76-165">類別</span><span class="sxs-lookup"><span data-stu-id="45e76-165">category</span></span> | <span data-ttu-id="45e76-166">字串</span><span class="sxs-lookup"><span data-stu-id="45e76-166">String</span></span> | <span data-ttu-id="45e76-167">警示的類別。</span><span class="sxs-lookup"><span data-stu-id="45e76-167">Category of the alert.</span></span> <span data-ttu-id="45e76-168">範例包括：執行和憑證存取。</span><span class="sxs-lookup"><span data-stu-id="45e76-168">Examples include: Execution and credential access.</span></span> <span data-ttu-id="45e76-169">**Optional**</span><span class="sxs-lookup"><span data-stu-id="45e76-169">**Optional**</span></span>
<span data-ttu-id="45e76-170">mitretechniques</span><span class="sxs-lookup"><span data-stu-id="45e76-170">mitretechniques</span></span>| <span data-ttu-id="45e76-171">字串</span><span class="sxs-lookup"><span data-stu-id="45e76-171">String</span></span> | <span data-ttu-id="45e76-172">MITRE 以逗號分隔)  (的技術代碼/識別碼。</span><span class="sxs-lookup"><span data-stu-id="45e76-172">MITRE techniques code/id (comma separated).</span></span> <span data-ttu-id="45e76-173">如需詳細資訊，請參閱 [Enterprise 戰術](https://attack.mitre.org/tactics/enterprise/)。</span><span class="sxs-lookup"><span data-stu-id="45e76-173">For more information, see [Enterprise tactics](https://attack.mitre.org/tactics/enterprise/).</span></span> <span data-ttu-id="45e76-174">**選用** 建議您在 MITRE 技術時新增類別中的值。</span><span class="sxs-lookup"><span data-stu-id="45e76-174">**Optional** It is recommended to add a value in category when a MITRE technique.</span></span>

<span data-ttu-id="45e76-175">如需詳細資訊，請參閱 [Microsoft Defender 的端點警示類別現在已與 MITRE ATT&CK！](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/microsoft-defender-atp-alert-categories-are-now-aligned-with/ba-p/732748)。</span><span class="sxs-lookup"><span data-stu-id="45e76-175">For more information, see [Microsoft Defender for Endpoint alert categories are now aligned with MITRE ATT&CK!](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/microsoft-defender-atp-alert-categories-are-now-aligned-with/ba-p/732748).</span></span>


## <a name="see-also"></a><span data-ttu-id="45e76-176">另請參閱</span><span class="sxs-lookup"><span data-stu-id="45e76-176">See also</span></span>
- [<span data-ttu-id="45e76-177">建立指示器</span><span class="sxs-lookup"><span data-stu-id="45e76-177">Create indicators</span></span>](manage-indicators.md)
- [<span data-ttu-id="45e76-178">建立檔案的指示器</span><span class="sxs-lookup"><span data-stu-id="45e76-178">Create indicators for files</span></span>](indicator-file.md)
- [<span data-ttu-id="45e76-179">為 IPs 和 URLs/網域建立指示器</span><span class="sxs-lookup"><span data-stu-id="45e76-179">Create indicators for IPs and URLs/domains</span></span>](indicator-ip-domain.md)
- [<span data-ttu-id="45e76-180">根據憑證建立指示器</span><span class="sxs-lookup"><span data-stu-id="45e76-180">Create indicators based on certificates</span></span>](indicator-certificates.md)
