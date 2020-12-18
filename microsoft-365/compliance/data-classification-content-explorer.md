---
title: 開始使用內容總管
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: 內容總管可讓您本機檢視已套用標籤的項目。
ms.openlocfilehash: 9beeab0c0b00ac1ac37c9df53e14a2f3f2914422
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701150"
---
# <a name="get-started-with-content-explorer"></a><span data-ttu-id="2bbce-103">開始使用內容總管</span><span class="sxs-lookup"><span data-stu-id="2bbce-103">Get started with content explorer</span></span>

<span data-ttu-id="2bbce-104">資料分類內容總管可讓您本機檢視概觀頁面中摘要的項目。</span><span class="sxs-lookup"><span data-stu-id="2bbce-104">The data classification content explorer allows you to natively view the items that were summarized on the overview page.</span></span>

![內容總管摺疊的螢幕擷取畫面](../media/data-classification-content-explorer-1.png)

## <a name="prerequisites"></a><span data-ttu-id="2bbce-106">必要條件</span><span class="sxs-lookup"><span data-stu-id="2bbce-106">Prerequisites</span></span>

<span data-ttu-id="2bbce-107">每個存取並使用資料分類的帳戶，都必須有從下列其中一個訂閱中指派的授權：</span><span class="sxs-lookup"><span data-stu-id="2bbce-107">Every account that accesses and uses data classification must have a license assigned to it from one of these subscriptions:</span></span>

- <span data-ttu-id="2bbce-108">Microsoft 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="2bbce-108">Microsoft 365 (E5)</span></span>
- <span data-ttu-id="2bbce-109">Office 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="2bbce-109">Office 365 (E5)</span></span>
- <span data-ttu-id="2bbce-110">進階合規性 (E5) 附加元件</span><span class="sxs-lookup"><span data-stu-id="2bbce-110">Advanced Compliance (E5) add-on</span></span>
- <span data-ttu-id="2bbce-111">進階威脅情報 (E5) 附加元件</span><span class="sxs-lookup"><span data-stu-id="2bbce-111">Advanced Threat Intelligence (E5) add-on</span></span>
- <span data-ttu-id="2bbce-112">Microsoft 365 E5/A5 資訊保護和控管</span><span class="sxs-lookup"><span data-stu-id="2bbce-112">Microsoft 365 E5/A5 Info Protection & Governance</span></span>
- <span data-ttu-id="2bbce-113">Microsoft 365 E5/A5 合規性</span><span class="sxs-lookup"><span data-stu-id="2bbce-113">Microsoft 365 E5/A5 Compliance</span></span>


### <a name="permissions"></a><span data-ttu-id="2bbce-114">權限</span><span class="sxs-lookup"><span data-stu-id="2bbce-114">Permissions</span></span>

<span data-ttu-id="2bbce-115">若要存取內容總管索引標籤，帳戶必須在其中任一角色或角色群組中獲派成員資格。</span><span class="sxs-lookup"><span data-stu-id="2bbce-115">In order to get access to the content explorer tab, an account must be assigned membership in any one of these roles or role groups.</span></span> 

<span data-ttu-id="2bbce-116">[DLP 原則](data-loss-prevention-policies.md)有助於保護敏感性資訊 (已定義為 **敏感性資訊類型**)。</span><span class="sxs-lookup"><span data-stu-id="2bbce-116">A [DLP policy](data-loss-prevention-policies.md) can help protect sensitive information, which is defined as a **sensitive information type**.</span></span> <span data-ttu-id="2bbce-117">Microsoft 365 包括涵蓋許多不同區域的[許多常見敏感性資訊類型的定義](sensitive-information-type-entity-definitions.md)，可供您使用。</span><span class="sxs-lookup"><span data-stu-id="2bbce-117">Microsoft 365 includes [definitions for many common sensitive information types](sensitive-information-type-entity-definitions.md) across many different regions that are ready for you to use.</span></span> <span data-ttu-id="2bbce-118">例如，信用卡號碼、銀行帳戶號碼、國家/地區識別碼和 Windows Live ID 服務號碼。</span><span class="sxs-lookup"><span data-stu-id="2bbce-118">For example, a credit card number, bank account numbers, national ID numbers, and Windows Live ID service numbers.</span></span>

<span data-ttu-id="2bbce-119">**Microsoft 365 角色群組**</span><span class="sxs-lookup"><span data-stu-id="2bbce-119">**Microsoft 365 role groups**</span></span>

- <span data-ttu-id="2bbce-120">全域管理員</span><span class="sxs-lookup"><span data-stu-id="2bbce-120">Global administrator</span></span>
- <span data-ttu-id="2bbce-121">合規性系統管理員</span><span class="sxs-lookup"><span data-stu-id="2bbce-121">Compliance administrator</span></span>
- <span data-ttu-id="2bbce-122">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="2bbce-122">Security administrator</span></span>
- <span data-ttu-id="2bbce-123">合規性資料管理員</span><span class="sxs-lookup"><span data-stu-id="2bbce-123">Compliance data administrator</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2bbce-124">這些角色群組中的成員資格不允許您檢視內容總管中的項目清單，或檢視內容總管中的項目內容。</span><span class="sxs-lookup"><span data-stu-id="2bbce-124">Membership in these role groups does not allow you to view the list of items in content explorer or to view the contents of the items in content explorer.</span></span>

### <a name="required-permissions-to-access-items-in-content-explorer"></a><span data-ttu-id="2bbce-125">需要內容總管權限以存取項目</span><span class="sxs-lookup"><span data-stu-id="2bbce-125">Required permissions to access items in content explorer</span></span>

<span data-ttu-id="2bbce-126">內容總管的存取權限受到高度限制，因為該權限可讓您讀取掃描檔案的內容。</span><span class="sxs-lookup"><span data-stu-id="2bbce-126">Access to content explorer is highly restricted because it lets you read the contents of scanned files.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2bbce-127">這些權限取代本機指派之允許查看內容的項目權限。</span><span class="sxs-lookup"><span data-stu-id="2bbce-127">These permissions supercede permissions that are locally assigned to the items, which allows viewing of the content.</span></span> 

<span data-ttu-id="2bbce-128">有兩個角色可以將存取權授與內容總管：</span><span class="sxs-lookup"><span data-stu-id="2bbce-128">There are two roles that grant access to content explorer:</span></span>

- <span data-ttu-id="2bbce-129">**內容總管清單檢視器**：這個角色群組的成員資格可讓您在 [清單檢視] 中查看每個項目及其位置。</span><span class="sxs-lookup"><span data-stu-id="2bbce-129">**Content Explorer List viewer**: Membership in this role group allows you to see each item and its location in list view.</span></span> <span data-ttu-id="2bbce-130">`data classification list viewer` 角色已預先指派給此角色群組。</span><span class="sxs-lookup"><span data-stu-id="2bbce-130">The `data classification list viewer` role has been pre-assigned to this role group.</span></span>

- <span data-ttu-id="2bbce-131">**內容瀏覽器內容檢視器**：這個角色群組的成員資格可讓您檢視清單中每個項目的內容。</span><span class="sxs-lookup"><span data-stu-id="2bbce-131">**Content Explorer Content viewer**: Membership in this role group allows you to view the contents of each item in the list.</span></span> <span data-ttu-id="2bbce-132">`data classification content viewer` 角色已預先指派給此角色群組。</span><span class="sxs-lookup"><span data-stu-id="2bbce-132">The `data classification content viewer` role has been pre-assigned to this role group.</span></span>

<span data-ttu-id="2bbce-133">您用來存取內容瀏覽器的帳戶必須屬於其中一個或兩個角色群組。</span><span class="sxs-lookup"><span data-stu-id="2bbce-133">The account you use to access content explorer must be in one or both of the role groups.</span></span> <span data-ttu-id="2bbce-134">這些是獨立的角色群組，不會累計。</span><span class="sxs-lookup"><span data-stu-id="2bbce-134">These are independent role groups and are not cumulative.</span></span> <span data-ttu-id="2bbce-135">例如，如果您想要授與某個帳戶只能檢視項目及其位置的權限，請授與「內容瀏覽器清單檢視器」權限。</span><span class="sxs-lookup"><span data-stu-id="2bbce-135">For example, if you want to grant an account the ability to view the items and their locations only, grant Content Explorer List viewer rights.</span></span> <span data-ttu-id="2bbce-136">如果您想要讓該相同帳戶也能夠檢視清單中項目的內容，也請授與「內容瀏覽器內容檢視器」權限。</span><span class="sxs-lookup"><span data-stu-id="2bbce-136">If you want that same account to also be able to view the contents of the items in the list, grant Content Explorer Content viewer rights as well.</span></span>

<span data-ttu-id="2bbce-137">您也可以將一個或兩個角色指派給自訂角色群組，以量身打造內容瀏覽器的存取權。</span><span class="sxs-lookup"><span data-stu-id="2bbce-137">You can also assign either or both of the roles to a custom role group to tailor access to content explorer.</span></span>

<span data-ttu-id="2bbce-138">全域系統管理員、合規性系統管理員或資料系統管理員可以指派必要的內容總管清單檢視器和內容總管內容檢視器角色群組成員資格。</span><span class="sxs-lookup"><span data-stu-id="2bbce-138">A Global admin, Compliance admin, or Data admin can assign the necessary Content Explorer List Viewer, and Content Explorer Content Viewer role group membership.</span></span>

## <a name="content-explorer"></a><span data-ttu-id="2bbce-139">內容總管</span><span class="sxs-lookup"><span data-stu-id="2bbce-139">Content explorer</span></span>

<span data-ttu-id="2bbce-140">內容總管會顯示具有敏感度標籤、保留標籤或已分類為貴組織敏感性資訊類型之項目的目前快照。</span><span class="sxs-lookup"><span data-stu-id="2bbce-140">Content explorer shows a current snapshot of the items that have a sensitivity label, a retention label or have been classified as a sensitive information type in your organization.</span></span>

### <a name="sensitive-information-types"></a><span data-ttu-id="2bbce-141">敏感性資訊類型</span><span class="sxs-lookup"><span data-stu-id="2bbce-141">Sensitive information types</span></span>

<span data-ttu-id="2bbce-142">[DLP 原則](data-loss-prevention-policies.md)有助於保護敏感性資訊 (已定義為 **敏感性資訊類型**)。</span><span class="sxs-lookup"><span data-stu-id="2bbce-142">A [DLP policy](data-loss-prevention-policies.md) can help protect sensitive information, which is defined as a **sensitive information type**.</span></span> <span data-ttu-id="2bbce-143">Microsoft 365 包括涵蓋許多不同區域的[許多常見敏感性資訊類型的定義](sensitive-information-type-entity-definitions.md)，可供您使用。</span><span class="sxs-lookup"><span data-stu-id="2bbce-143">Microsoft 365 includes [definitions for many common sensitive information types](sensitive-information-type-entity-definitions.md) from across many different regions that are ready for you to use.</span></span> <span data-ttu-id="2bbce-144">例如，信用卡號碼、銀行帳戶號碼、國家/地區識別碼和 Windows Live ID 服務號碼。</span><span class="sxs-lookup"><span data-stu-id="2bbce-144">For example, a credit card number, bank account numbers, national ID numbers, and Windows Live ID service numbers.</span></span>

> [!NOTE]
> <span data-ttu-id="2bbce-145">內容總管目前不掃描 Exchange Online 中的敏感性資訊類型。</span><span class="sxs-lookup"><span data-stu-id="2bbce-145">Content explorer doesn't currently scan for sensitive information types in Exchange Online.</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="2bbce-146">敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="2bbce-146">Sensitivity labels</span></span>

<span data-ttu-id="2bbce-147">[敏感度標籤](sensitivity-labels.md)只是一個標記，指出您組織的項目值。</span><span class="sxs-lookup"><span data-stu-id="2bbce-147">A [sensitivity label](sensitivity-labels.md) is simply a tag that indicates the value of the item to your organization.</span></span> <span data-ttu-id="2bbce-148">可手動或自動套用。</span><span class="sxs-lookup"><span data-stu-id="2bbce-148">It can be applied manually, or automatically.</span></span> <span data-ttu-id="2bbce-149">一旦套用，即會將它內嵌在文件中，並在所有的位置追蹤。</span><span class="sxs-lookup"><span data-stu-id="2bbce-149">Once applied it gets embedded in the document and will follow it everywhere it goes.</span></span> <span data-ttu-id="2bbce-150">敏感性標籤會啟用各種防護行為，例如強制浮水印或加密。</span><span class="sxs-lookup"><span data-stu-id="2bbce-150">A sensitivity label enables various protective behaviors, such as mandatory watermarking or encryption.</span></span>

<span data-ttu-id="2bbce-151">SharePoint 和 OneDrive 中的檔案必須啟用敏感度標籤，以便在資料分類頁面中顯示對應資料。</span><span class="sxs-lookup"><span data-stu-id="2bbce-151">Sensitivity labels must be enabled for files that are in SharePoint and OneDrive in order for the corresponding data to surface in the data classification page.</span></span> <span data-ttu-id="2bbce-152">如需詳細資訊，請參閱[對 SharePoint 和 OneDrive 中的 Office 檔案啟用敏感度標籤](sensitivity-labels-sharepoint-onedrive-files.md)。</span><span class="sxs-lookup"><span data-stu-id="2bbce-152">For more information, see [Enable sensitivity labels for Office files in SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>

### <a name="retention-labels"></a><span data-ttu-id="2bbce-153">保留標籤</span><span class="sxs-lookup"><span data-stu-id="2bbce-153">Retention labels</span></span>

<span data-ttu-id="2bbce-154">[保留標籤](retention.md)可讓您定義保留標記的項目的時間長度，以及刪除它之前要採取的步驟。</span><span class="sxs-lookup"><span data-stu-id="2bbce-154">A [retention label](retention.md) allows you to define how long a labeled item is kept and the steps to be taken prior to deleting it.</span></span> <span data-ttu-id="2bbce-155">它們會透過原則來手動或自動套用。</span><span class="sxs-lookup"><span data-stu-id="2bbce-155">They are applied manually or automatically via policies.</span></span> <span data-ttu-id="2bbce-156">它們可以在協助您組織保持遵守法律和法規需求方面扮演一個角色。</span><span class="sxs-lookup"><span data-stu-id="2bbce-156">They can play a role in helping your organization stay in compliance with legal and regulatory requirements.</span></span>

### <a name="how-to-use-content-explorer"></a><span data-ttu-id="2bbce-157">如何使用內容總管</span><span class="sxs-lookup"><span data-stu-id="2bbce-157">How to use content explorer</span></span>

1. <span data-ttu-id="2bbce-158">開啟 **Microsoft 365 合規性中心**  > **資料分類** > **內容總管**。</span><span class="sxs-lookup"><span data-stu-id="2bbce-158">Open **Microsoft 365 compliance center**  > **Data classification** > **Content explorer**.</span></span>
2. <span data-ttu-id="2bbce-159">如果您知道標籤的名稱或敏感性資訊類型，便可在篩選方塊中輸入。</span><span class="sxs-lookup"><span data-stu-id="2bbce-159">If you know the name of the label, or the sensitive information type, you can type that into the filter box.</span></span>
3. <span data-ttu-id="2bbce-160">您也可以展開標籤類型，然後從清單選取標籤來瀏覽項目。</span><span class="sxs-lookup"><span data-stu-id="2bbce-160">Alternately, you can browse for the item by expanding the label type and selecting the label from the list.</span></span>
4. <span data-ttu-id="2bbce-161">在 **[所有位置]** 底下選取位置，並向下切入資料夾結構至項目。</span><span class="sxs-lookup"><span data-stu-id="2bbce-161">Select a location under **All locations** and drill down the folder structure to the item.</span></span>
5. <span data-ttu-id="2bbce-162">按兩下以在內容總管中於機開啟項目。</span><span class="sxs-lookup"><span data-stu-id="2bbce-162">Double-click to open the item natively in content explorer.</span></span>

### <a name="export"></a><span data-ttu-id="2bbce-163">匯出</span><span class="sxs-lookup"><span data-stu-id="2bbce-163">Export</span></span>
<span data-ttu-id="2bbce-164">**匯出** 控制項將建立包含任何列出顯示於 **[所有位置]** 窗格中項目的 .csv 檔案。</span><span class="sxs-lookup"><span data-stu-id="2bbce-164">The **export** control will create a .csv file that contains a listing of whatever is showing in the **All locations** pane.</span></span>

![資料分類匯出控制項](../media/data_classification_export_control.png)


### <a name="search"></a><span data-ttu-id="2bbce-166">搜尋</span><span class="sxs-lookup"><span data-stu-id="2bbce-166">Search</span></span>

<span data-ttu-id="2bbce-167">當您向下切入例如 Exchange 資料夾或 SharePoint 或 OneDrive 網站等位置時，就會顯示 **[搜尋]** 工具。</span><span class="sxs-lookup"><span data-stu-id="2bbce-167">When you drill down into a location, such as an Exchange folder, or a SharePoint or OneDrive site, the **search** tool appears.</span></span>

![內容總管搜尋工具](../media/data_classification_search_tool.png)


<span data-ttu-id="2bbce-169">搜尋工具的範圍是 **[所有位置]** 窗格中顯示的內容，並且您可以搜尋的內容依照所選位置而有所不同。</span><span class="sxs-lookup"><span data-stu-id="2bbce-169">The scope of the search tool is what is displaying in the **All locations** pane and what you can search on varies depending on the selected location.</span></span> 

<span data-ttu-id="2bbce-170">當 **[Exchange]** 為選取的位置時，您可以搜尋信箱的完整電子郵件地址，例如 `user@domainname.com`。</span><span class="sxs-lookup"><span data-stu-id="2bbce-170">When **Exchange** is the selected location, you can search on the full email address of the mailbox, for example `user@domainname.com`.</span></span>

<span data-ttu-id="2bbce-171">當選取位置為 **[SharePoint]** 或 **[OneDrive]** 時，系統會在您向下切入至網站名稱、資料夾和檔案時顯示搜尋工具。</span><span class="sxs-lookup"><span data-stu-id="2bbce-171">When either **SharePoint** or **OneDrive** are selected location, the search tool will appear when you drill down to site names, folders and files.</span></span> 

> [!NOTE]
> <span data-ttu-id="2bbce-172">**OneDrive** 我們收到了您在預覽計劃期間對 OneDrive 整合的寶貴意見反應。</span><span class="sxs-lookup"><span data-stu-id="2bbce-172">**OneDrive** We have listened to your valuable feedback on OneDrive integration during our preview program.</span></span> <span data-ttu-id="2bbce-173">根據該意見反應，OneDrive 功能將在所有修正程式都準備好之前保持為預覽。</span><span class="sxs-lookup"><span data-stu-id="2bbce-173">Based on that feedback, the OneDrive functionality will remain in preview till all fixes are in place.</span></span> <span data-ttu-id="2bbce-174">視您的租用戶而定，有些客戶可能不會看到 OneDrive 作為位置。</span><span class="sxs-lookup"><span data-stu-id="2bbce-174">Depending on your tenant, some customers may not see OneDrive as a location.</span></span> <span data-ttu-id="2bbce-175">非常感謝您的持續支持。</span><span class="sxs-lookup"><span data-stu-id="2bbce-175">We appreciate your continued support on this.</span></span>

<span data-ttu-id="2bbce-176">您可搜尋：</span><span class="sxs-lookup"><span data-stu-id="2bbce-176">You can search on:</span></span>


|<span data-ttu-id="2bbce-177">數值</span><span class="sxs-lookup"><span data-stu-id="2bbce-177">value</span></span>|<span data-ttu-id="2bbce-178">範例</span><span class="sxs-lookup"><span data-stu-id="2bbce-178">example</span></span>  |
|---------|---------|
|<span data-ttu-id="2bbce-179">完整網站名稱</span><span class="sxs-lookup"><span data-stu-id="2bbce-179">full site name</span></span>    |`https://contoso.onmicrosoft.com/sites/sitename`    |
|<span data-ttu-id="2bbce-180">根資料夾名稱 - 取得所有子資料夾</span><span class="sxs-lookup"><span data-stu-id="2bbce-180">root folder name - gets all subfolders</span></span>    | `/sites`        |
|<span data-ttu-id="2bbce-181">檔案名稱</span><span class="sxs-lookup"><span data-stu-id="2bbce-181">file name</span></span>    |    `RES_Resume_1234.txt`     |
|<span data-ttu-id="2bbce-182">檔案名稱開頭的文字</span><span class="sxs-lookup"><span data-stu-id="2bbce-182">text at the beginning of file name</span></span>| `RES`|
|<span data-ttu-id="2bbce-183">檔案名稱中以底線字元 ( _ ) 之後的文字</span><span class="sxs-lookup"><span data-stu-id="2bbce-183">text after an underscore character ( _ ) in file name</span></span>|<span data-ttu-id="2bbce-184">`Resume` 或 `1234`</span><span class="sxs-lookup"><span data-stu-id="2bbce-184">`Resume` or `1234`</span></span>| 
|<span data-ttu-id="2bbce-185">檔案副檔名</span><span class="sxs-lookup"><span data-stu-id="2bbce-185">file extension</span></span>|`txt`|


## <a name="see-also"></a><span data-ttu-id="2bbce-186">請參閱</span><span class="sxs-lookup"><span data-stu-id="2bbce-186">See also</span></span>

- [<span data-ttu-id="2bbce-187">了解敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="2bbce-187">Learn about sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="2bbce-188">瞭解保留原則和保留標籤</span><span class="sxs-lookup"><span data-stu-id="2bbce-188">Learn about retention policies and retention labels</span></span>](retention.md)
- [<span data-ttu-id="2bbce-189">敏感性資訊類型實體定義.md</span><span class="sxs-lookup"><span data-stu-id="2bbce-189">Sensitive information type entity definitions.md</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="2bbce-190">資料外洩防護概觀</span><span class="sxs-lookup"><span data-stu-id="2bbce-190">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
