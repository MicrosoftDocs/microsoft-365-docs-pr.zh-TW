---
title: 管理多地理位置環境
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.collection:
- Strat_SP_gtc
- SPO_Content
localization_priority: Normal
description: 系統管理員可以瞭解如何在多地理位置環境中管理 SharePoint 和 OneDrive 服務。
ms.openlocfilehash: 4c5215b855b8ca1840035b39fcfbddde419c13d8
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362315"
---
# <a name="administering-a-multi-geo-environment"></a><span data-ttu-id="5875d-103">管理多地理位置環境</span><span class="sxs-lookup"><span data-stu-id="5875d-103">Administering a multi-geo environment</span></span>

<span data-ttu-id="5875d-104">查看 Microsoft 365 服務在多地理位置環境中的運作方式。</span><span class="sxs-lookup"><span data-stu-id="5875d-104">Here's a look at how Microsoft 365 services work in a multi-geo environment.</span></span>

## <a name="administrator-experience"></a><span data-ttu-id="5875d-105">管理員經驗</span><span class="sxs-lookup"><span data-stu-id="5875d-105">Administrator experience</span></span>

<span data-ttu-id="5875d-106">[SharePoint 系統管理中心](https://admin.microsoft.com/sharepoint)的左側導覽中有 [**地理位置**] 索引標籤，可讓您查看和管理您的地理位置。</span><span class="sxs-lookup"><span data-stu-id="5875d-106">The [SharePoint admin center](https://admin.microsoft.com/sharepoint) has a **Geo locations** tab in the left navigation which features a geo locations map where you can view and manage your geo locations.</span></span> <span data-ttu-id="5875d-107">使用此頁面來新增或刪除租使用者的地理位置。</span><span class="sxs-lookup"><span data-stu-id="5875d-107">Use this page to add or delete geo locations for your tenant.</span></span>

## <a name="audit-log-search"></a><span data-ttu-id="5875d-108">稽核記錄檔搜尋</span><span class="sxs-lookup"><span data-stu-id="5875d-108">Audit log search</span></span>

<span data-ttu-id="5875d-109">可以從 Microsoft 365 稽核記錄搜索頁面取得所有衛星位置的統一[稽核記錄](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c)。</span><span class="sxs-lookup"><span data-stu-id="5875d-109">A unified [Audit log](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c) for all your satellite locations is available from the Microsoft 365 audit log search page.</span></span> <span data-ttu-id="5875d-110">您可以看到跨地理位置的所有稽核記錄項目，例如，北美洲與歐洲使用者的活動會在一個組織視圖中顯示，然後您可以套用現有的篩選器，以查看特定使用者的活動。</span><span class="sxs-lookup"><span data-stu-id="5875d-110">You can see all the audit log entries from across geo locations, for example, NAM & EUR users' activities will show up in one org view and then you can apply existing filters to see specific user's activities.</span></span>

## <a name="bcs-secure-store-apps"></a><span data-ttu-id="5875d-111">BCS、Secure Store、應用程式</span><span class="sxs-lookup"><span data-stu-id="5875d-111">BCS, Secure Store, Apps</span></span>

<span data-ttu-id="5875d-112">BCS、Secure Store 及應用程式在每個衛星位置中都有個別的執行個體，因此 Sharepoint Online 系統管理員應該從每個衛星位置中個別管理及設定這些服務。</span><span class="sxs-lookup"><span data-stu-id="5875d-112">BCS, Secure Store, and Apps all have separate instances in each satellite location, therefore the SharePoint Online administrator should manage and configure these services separately from each satellite location.</span></span>

## <a name="compliance-admin-center"></a><span data-ttu-id="5875d-113">合規性系統管理中心</span><span class="sxs-lookup"><span data-stu-id="5875d-113">Compliance admin center</span></span>

<span data-ttu-id="5875d-114">有一個適用于多地理位置租使用者的中央合規性中心： [Microsoft 365 合規性系統管理中心](https://compliance.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="5875d-114">There is one central compliance center for a multi-geo tenant: [Microsoft 365 Compliance admin center](https://compliance.microsoft.com/).</span></span>

## <a name="ediscovery"></a><span data-ttu-id="5875d-115">eDiscovery</span><span class="sxs-lookup"><span data-stu-id="5875d-115">eDiscovery</span></span>

<span data-ttu-id="5875d-116">根據預設，多地理位置租用戶的電子文件探索管理員或系統管理員只能在該租用戶的中央位置進行電子文件探索。</span><span class="sxs-lookup"><span data-stu-id="5875d-116">By default, an eDiscovery Manager or Administrator of a multi-geo tenant will be able to conduct eDiscovery only in the central location of that tenant.</span></span> <span data-ttu-id="5875d-117">Office 365 全域系統管理員必須指派電子文件探索管理員權限，以允許其他人執行電子文件探索，並在其適用的合規性安全性篩選中指派「地區」參數，以將進行電子文件探索的區域指定為衛星位置，否則將不會為該衛星位置執行任何電子文件探索。</span><span class="sxs-lookup"><span data-stu-id="5875d-117">The Office 365 global administrator must assign eDiscovery Manager permissions to allow others to perform eDiscovery and assign a "Region" parameter in their applicable Compliance Security Filter to specify the region for conducting eDiscovery as satellite location, otherwise no eDiscovery will be carried out for the satellite location.</span></span> <span data-ttu-id="5875d-118">若要設定地區的法規遵循安全性篩選器，請參閱[設定 Office 365 多地理位置電子文件探索](multi-geo-ediscovery-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="5875d-118">To configure the Compliance Security Filter for a Region, see [Configure Office 365 Multi-Geo eDiscovery](multi-geo-ediscovery-configuration.md).</span></span>

## <a name="exchange-mailboxes"></a><span data-ttu-id="5875d-119">Exchange 信箱</span><span class="sxs-lookup"><span data-stu-id="5875d-119">Exchange mailboxes</span></span>

<span data-ttu-id="5875d-120">如果使用者的 PDL 變更，系統會自動移動使用者的 Exchange 信箱。</span><span class="sxs-lookup"><span data-stu-id="5875d-120">Users' Exchange mailboxes are moved automatically if their PDL is changed.</span></span> <span data-ttu-id="5875d-121">建立新的信箱時，如果使用者的 PDL 未設定任何值，信箱會佈建到使用者的 PDL 或中央位置。</span><span class="sxs-lookup"><span data-stu-id="5875d-121">When a new mailbox is created, it is provisioned to the user's PDL or to the central location if no value has been set for the user's PDL.</span></span>

## <a name="information-protection-ip-data-loss-prevention-dlp-policy"></a><span data-ttu-id="5875d-122">資訊保護 (IP) 資料遺失防護 (DLP) 原則</span><span class="sxs-lookup"><span data-stu-id="5875d-122">Information Protection (IP) Data Loss Prevention (DLP) policy</span></span>

<span data-ttu-id="5875d-123">您可以視整個租用戶或適用使用者的需求，在安全性和合規性中心為商務用 OneDrive、SharePoint 和 Exchange 設定 IP DLP 原則和範圍原則。</span><span class="sxs-lookup"><span data-stu-id="5875d-123">You can set your IP DLP policies for OneDrive for Business, SharePoint, and Exchange in the Security and Compliance center, scoping policies as needed to the whole tenant or to applicable users.</span></span> <span data-ttu-id="5875d-124">例如：如果您想為衛星位置的使用者選取原則，請選取將原則套用到特定 OneDrive 並輸入使用者的 OneDrive URL。</span><span class="sxs-lookup"><span data-stu-id="5875d-124">For example: If you wish to select a policy for a user in a satellite location, select to apply the policy to a specific OneDrive and enter the user's OneDrive url.</span></span> <span data-ttu-id="5875d-125">如需建立 DLP 原則的一般指導方針，請參閱[資料外洩防護原則概觀](https://support.office.com/article/1966b2a7-d1e2-4d92-ab61-42efbb137f5e)。</span><span class="sxs-lookup"><span data-stu-id="5875d-125">See [Overview of data loss prevention policies](https://support.office.com/article/1966b2a7-d1e2-4d92-ab61-42efbb137f5e) for general guidance in creating DLP policies.</span></span>

<span data-ttu-id="5875d-126">系統會根據 DLP 原則對每個地理位置的適用性來自動同步處理這些原則。</span><span class="sxs-lookup"><span data-stu-id="5875d-126">The DLP policies are automatically synchronized based on their applicability to each geo location.</span></span>

<span data-ttu-id="5875d-127">對某個地理位置中的所有使用者執行資訊保護和資料外洩防護原則，不是 UI 中的可用選項，您反而必須選取該原則適用的帳戶，或將該原則全域套用至所有帳戶。</span><span class="sxs-lookup"><span data-stu-id="5875d-127">Implementing Information Protection and Data Loss prevention policies to all users in a geo location is not an option available in the UI, instead you must select the applicable accounts for the policy or apply the policy globally to all accounts.</span></span>

## <a name="microsoft-powerapps"></a><span data-ttu-id="5875d-128">Microsoft PowerApps</span><span class="sxs-lookup"><span data-stu-id="5875d-128">Microsoft PowerApps</span></span>

<span data-ttu-id="5875d-129">為衛星位置建立的 PowerApps 將使用位於該租用戶中央位置的端點。</span><span class="sxs-lookup"><span data-stu-id="5875d-129">PowerApps created for the satellite location will use the end point located in the central location for the tenant.</span></span> <span data-ttu-id="5875d-130">Microsoft PowerApps 不是多地理位置服務。</span><span class="sxs-lookup"><span data-stu-id="5875d-130">Microsoft PowerApps is not a Multi-Geo service.</span></span> 

## <a name="power-automate"></a><span data-ttu-id="5875d-131">Power Automate</span><span class="sxs-lookup"><span data-stu-id="5875d-131">Power Automate</span></span>

<span data-ttu-id="5875d-132">為衛星位置建立的流程將使用位於該租用戶預設地理位置的端點。</span><span class="sxs-lookup"><span data-stu-id="5875d-132">Flows created for the satellite location will use the end point located in the default geo location for the tenant.</span></span>  <span data-ttu-id="5875d-133">Power Automate 不是多地理位置服務。</span><span class="sxs-lookup"><span data-stu-id="5875d-133">Power Automate is not a Multi-Geo service.</span></span> 

## <a name="sharepoint-storage-quota"></a><span data-ttu-id="5875d-134">SharePoint 儲存空間配額</span><span class="sxs-lookup"><span data-stu-id="5875d-134">SharePoint storage quota</span></span>

<span data-ttu-id="5875d-135">根據預設，多重地理環境的所有地理位置會共用可用的租用戶儲存空間配額。</span><span class="sxs-lookup"><span data-stu-id="5875d-135">By default, all geo locations of a multi-geo environment share the available tenant storage quota.</span></span>  <span data-ttu-id="5875d-136">您也可以為特定的地理位置分配特定配額，以管理儲存空間配額。</span><span class="sxs-lookup"><span data-stu-id="5875d-136">You can also manage the storage quota by allocating a specific quota for a particular geo location.</span></span> <span data-ttu-id="5875d-137">如需詳細資訊，請參閱[多地理位置環境中的 SharePoint 儲存空間配額](sharepoint-multi-geo-storage-quota.md)。</span><span class="sxs-lookup"><span data-stu-id="5875d-137">For more information, see [SharePoint storage quotas in multi-geo environments](sharepoint-multi-geo-storage-quota.md).</span></span>

## <a name="sharing"></a><span data-ttu-id="5875d-138">共用</span><span class="sxs-lookup"><span data-stu-id="5875d-138">Sharing</span></span>

<span data-ttu-id="5875d-139">系統管理員可以設定並管理每個位置的共用原則。</span><span class="sxs-lookup"><span data-stu-id="5875d-139">Administrators can set and manage sharing policies for each of their locations.</span></span> <span data-ttu-id="5875d-140">每個地理位置中的 OneDrive 和 SharePoint 網站只會遵守對應的地理位置特定的共用設定。</span><span class="sxs-lookup"><span data-stu-id="5875d-140">The OneDrive and SharePoint sites in each geo location will honor only the corresponding geo specific sharing settings.</span></span> <span data-ttu-id="5875d-141">(例如，您可以允許在中央位置[外部共用](https://support.office.com/article/C8A462EB-0723-4B0B-8D0A-70FEAFE4BE85)，但不能在衛星位置外部共用，反之亦然。) 請注意，共用設定不允許在地理位置之間設定共用限制。</span><span class="sxs-lookup"><span data-stu-id="5875d-141">(For example, you can allow [external sharing](https://support.office.com/article/C8A462EB-0723-4B0B-8D0A-70FEAFE4BE85) for your central location, but not for your satellite location or vice versa.) Note that the sharing settings do not allow configuring sharing limitations between geo locations.</span></span>

## <a name="stream"></a><span data-ttu-id="5875d-142">Stream</span><span class="sxs-lookup"><span data-stu-id="5875d-142">Stream</span></span>

<span data-ttu-id="5875d-143">上傳至資料流程的影片會儲存在上載人員的 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="5875d-143">Videos uploaded to Stream are stored in the OneDrive of the person uploading.</span></span> <span data-ttu-id="5875d-144">會議錄製會儲存在每個記錄會議的出席者的 OneDrive 中。</span><span class="sxs-lookup"><span data-stu-id="5875d-144">Meeting recordings are stored in the OneDrive of each attendee who records the meeting.</span></span>

## <a name="taxonomy"></a><span data-ttu-id="5875d-145">分類</span><span class="sxs-lookup"><span data-stu-id="5875d-145">Taxonomy</span></span>

<span data-ttu-id="5875d-146">我們使用您公司中央位置主控的主機，針對不同地理位置的企業管理中繼資料，支援統一的[分類法](/sharepoint/managed-metadata)。</span><span class="sxs-lookup"><span data-stu-id="5875d-146">We support a unified [taxonomy](/sharepoint/managed-metadata) for enterprise managed metadata across geo locations, with the master being hosted in the central location for your company.</span></span> <span data-ttu-id="5875d-147">我們建議您從中央位置管理全域分類法，並只將特定位置的詞彙增到衛星位置的分類法。</span><span class="sxs-lookup"><span data-stu-id="5875d-147">We recommend that you manage your global taxonomy from the central location and only add location-specific terms to the satellite location's Taxonomy.</span></span> <span data-ttu-id="5875d-148">全域分類法詞彙將同步到衛星位置。</span><span class="sxs-lookup"><span data-stu-id="5875d-148">Global taxonomy terms will synchronize to the satellite locations.</span></span>

<span data-ttu-id="5875d-149">如需詳細資訊與開發人員指導方針，請參閱[管理多地理位置租用戶中的中繼資料](/sharepoint/dev/solution-guidance/multigeo-managedmetadata)。</span><span class="sxs-lookup"><span data-stu-id="5875d-149">See [Manage metadata in a multi-geo tenant](/sharepoint/dev/solution-guidance/multigeo-managedmetadata) for additional details and for developer guidance.</span></span>

## <a name="user-profile-application"></a><span data-ttu-id="5875d-150">使用者設定檔應用程式</span><span class="sxs-lookup"><span data-stu-id="5875d-150">User Profile Application</span></span>

<span data-ttu-id="5875d-151">每個地理位置都有一個[使用者設定檔應用程式](/sharepoint/manage-user-profiles)。</span><span class="sxs-lookup"><span data-stu-id="5875d-151">There is a [user profile application](/sharepoint/manage-user-profiles) in each geo location.</span></span> <span data-ttu-id="5875d-152">系統會在每位使用者的地理位置主控其設定檔資訊，且該設定檔資料可供該地理位置的系統管理員使用。</span><span class="sxs-lookup"><span data-stu-id="5875d-152">Each user's profile information is hosted in their geo location and available to the administrator for that geo location.</span></span>

<span data-ttu-id="5875d-153">如果您有自訂的設定檔屬性，則建議您使用跨地理位置的相同設定檔結構描述，然後在所有的地理位置或所需的位置填入自訂設定檔屬性。</span><span class="sxs-lookup"><span data-stu-id="5875d-153">If you have custom profile properties, then we recommend that you use the same profile schema across geographies and populate your custom profile properties either in all geo locations or where needed.</span></span> <span data-ttu-id="5875d-154">如需如何以程式設計方式填入使用者設定檔資料的指導方針，請參閱[大量使用者設定檔更新 API](/sharepoint/dev/solution-guidance/bulk-user-profile-update-api-for-sharepoint-online)。</span><span class="sxs-lookup"><span data-stu-id="5875d-154">For guidance regarding how to populate user profile data programmatically, please refer to the [Bulk User Profile Update API](/sharepoint/dev/solution-guidance/bulk-user-profile-update-api-for-sharepoint-online).</span></span>

<span data-ttu-id="5875d-155">如需詳細資訊與開發人員指導方針，請參閱[在多地理位置租用戶中使用使用者設定檔](/sharepoint/dev/solution-guidance/multigeo-userprofileexperience)。</span><span class="sxs-lookup"><span data-stu-id="5875d-155">See [Work with user profiles in a multi-geo tenant](/sharepoint/dev/solution-guidance/multigeo-userprofileexperience) for additional details and for developer guidance.</span></span>

## <a name="yammer"></a><span data-ttu-id="5875d-156">Yammer</span><span class="sxs-lookup"><span data-stu-id="5875d-156">Yammer</span></span>

<span data-ttu-id="5875d-157">Yammer 不是多地理位置工作負載。</span><span class="sxs-lookup"><span data-stu-id="5875d-157">Yammer is not a Multi-Geo workload.</span></span> <span data-ttu-id="5875d-158">儲存在 Yammer 中的 Yammer 執行緒都會放置在租使用者的中央位置。</span><span class="sxs-lookup"><span data-stu-id="5875d-158">Yammer threads stored in Yammer will be placed in the tenant’s central location.</span></span> <span data-ttu-id="5875d-159">Yammer 正在推出會將 Yammer 檔案儲存在 SharePoint 中的檔案儲存變更。</span><span class="sxs-lookup"><span data-stu-id="5875d-159">Yammer is rolling out a file storage change which will store Yammer files within SharePoint.</span></span> <span data-ttu-id="5875d-160">儲存在 SharePoint 中的 Yammer 檔案將會放入與 Yammer 群組相關聯的 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="5875d-160">Yammer files stored in SharePoint will be placed the SharePoint site associated with the Yammer group.</span></span> <span data-ttu-id="5875d-161">SharePoint 群組網站是以 PDL 邏輯為基礎，如[SharePoint 網站和群組](multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md#sharepoint-sites-and-groups)中所述。</span><span class="sxs-lookup"><span data-stu-id="5875d-161">SharePoint group sites are based on PDL logic as outlined in [SharePoint Sites and Groups](multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md#sharepoint-sites-and-groups).</span></span>