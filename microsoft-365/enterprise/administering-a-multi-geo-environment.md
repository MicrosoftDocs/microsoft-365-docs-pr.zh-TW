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
ms.openlocfilehash: 213070f2f7a04e15a1e2ac3cd9a3ae697b66a718
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905593"
---
# <a name="administering-a-multi-geo-environment"></a><span data-ttu-id="18d1f-103">管理多地理位置環境</span><span class="sxs-lookup"><span data-stu-id="18d1f-103">Administering a multi-geo environment</span></span>

<span data-ttu-id="18d1f-104">查看 Microsoft 365 服務在多地理位置環境中的運作方式。</span><span class="sxs-lookup"><span data-stu-id="18d1f-104">Here's a look at how Microsoft 365 services work in a multi-geo environment.</span></span>

## <a name="audit-log-search"></a><span data-ttu-id="18d1f-105">稽核記錄檔搜尋</span><span class="sxs-lookup"><span data-stu-id="18d1f-105">Audit log search</span></span>

<span data-ttu-id="18d1f-106">可以從 Microsoft 365 稽核記錄搜索頁面取得所有衛星位置的統一[稽核記錄](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c)。</span><span class="sxs-lookup"><span data-stu-id="18d1f-106">A unified [Audit log](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c) for all your satellite locations is available from the Microsoft 365 audit log search page.</span></span> <span data-ttu-id="18d1f-107">您可以看到跨地理位置的所有稽核記錄項目，例如，北美洲與歐洲使用者的活動會在一個組織視圖中顯示，然後您可以套用現有的篩選器，以查看特定使用者的活動。</span><span class="sxs-lookup"><span data-stu-id="18d1f-107">You can see all the audit log entries from across geo locations, for example, NAM & EUR users' activities will show up in one org view and then you can apply existing filters to see specific user's activities.</span></span>

## <a name="bcs-secure-store-apps"></a><span data-ttu-id="18d1f-108">BCS、Secure Store、應用程式</span><span class="sxs-lookup"><span data-stu-id="18d1f-108">BCS, Secure Store, Apps</span></span>

<span data-ttu-id="18d1f-109">BCS、Secure Store 及應用程式在每個衛星位置中都有個別的執行個體，因此 Sharepoint Online 系統管理員應該從每個衛星位置中個別管理及設定這些服務。</span><span class="sxs-lookup"><span data-stu-id="18d1f-109">BCS, Secure Store, and Apps all have separate instances in each satellite location, therefore the SharePoint Online administrator should manage and configure these services separately from each satellite location.</span></span>

## <a name="ediscovery"></a><span data-ttu-id="18d1f-110">eDiscovery</span><span class="sxs-lookup"><span data-stu-id="18d1f-110">eDiscovery</span></span> 

<span data-ttu-id="18d1f-111">根據預設，多地理位置租用戶的電子文件探索管理員或系統管理員只能在該租用戶的中央位置進行電子文件探索。</span><span class="sxs-lookup"><span data-stu-id="18d1f-111">By default, an eDiscovery Manager or Administrator of a multi-geo tenant will be able to conduct eDiscovery only in the central location of that tenant.</span></span> <span data-ttu-id="18d1f-112">Office 365 全域系統管理員必須指派電子文件探索管理員權限，以允許其他人執行電子文件探索，並在其適用的合規性安全性篩選中指派「地區」參數，以將進行電子文件探索的區域指定為衛星位置，否則將不會為該衛星位置執行任何電子文件探索。</span><span class="sxs-lookup"><span data-stu-id="18d1f-112">The Office 365 global administrator must assign eDiscovery Manager permissions to allow others to perform eDiscovery and assign a "Region" parameter in their applicable Compliance Security Filter to specify the region for conducting eDiscovery as satellite location, otherwise no eDiscovery will be carried out for the satellite location.</span></span> <span data-ttu-id="18d1f-113">若要設定地區的法規遵循安全性篩選器，請參閱[設定 Office 365 多地理位置電子文件探索](multi-geo-ediscovery-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="18d1f-113">To configure the Compliance Security Filter for a Region, see [Configure Office 365 Multi-Geo eDiscovery](multi-geo-ediscovery-configuration.md).</span></span>

## <a name="exchange-mailboxes"></a><span data-ttu-id="18d1f-114">Exchange 信箱</span><span class="sxs-lookup"><span data-stu-id="18d1f-114">Exchange mailboxes</span></span>

<span data-ttu-id="18d1f-115">如果使用者的 PDL 變更，系統會自動移動使用者的 Exchange 信箱。</span><span class="sxs-lookup"><span data-stu-id="18d1f-115">Users' Exchange mailboxes are moved automatically if their PDL is changed.</span></span> <span data-ttu-id="18d1f-116">建立新的信箱時，如果使用者的 PDL 未設定任何值，信箱會佈建到使用者的 PDL 或中央位置。</span><span class="sxs-lookup"><span data-stu-id="18d1f-116">When a new mailbox is created, it is provisioned to the user's PDL or to the central location if no value has been set for the user's PDL.</span></span>

## <a name="information-protection-ip-data-loss-prevention-dlp-policy"></a><span data-ttu-id="18d1f-117">資訊保護 (IP) 的資料外洩防護 (DLP) 原則</span><span class="sxs-lookup"><span data-stu-id="18d1f-117">Information Protection (IP) Data Loss Prevention (DLP) Policy</span></span>

<span data-ttu-id="18d1f-118">您可以視整個租用戶或適用使用者的需求，在安全性和合規性中心為商務用 OneDrive、SharePoint 和 Exchange 設定 IP DLP 原則和範圍原則。</span><span class="sxs-lookup"><span data-stu-id="18d1f-118">You can set your IP DLP policies for OneDrive for Business, SharePoint, and Exchange in the Security and Compliance center, scoping policies as needed to the whole tenant or to applicable users.</span></span> <span data-ttu-id="18d1f-119">例如：如果您想為衛星位置的使用者選取原則，請選取將原則套用到特定 OneDrive 並輸入使用者的 OneDrive URL。</span><span class="sxs-lookup"><span data-stu-id="18d1f-119">For example: If you wish to select a policy for a user in a satellite location, select to apply the policy to a specific OneDrive and enter the user's OneDrive url.</span></span> <span data-ttu-id="18d1f-120">如需建立 DLP 原則的一般指導方針，請參閱[資料外洩防護原則概觀](https://support.office.com/article/1966b2a7-d1e2-4d92-ab61-42efbb137f5e)。</span><span class="sxs-lookup"><span data-stu-id="18d1f-120">See [Overview of data loss prevention policies](https://support.office.com/article/1966b2a7-d1e2-4d92-ab61-42efbb137f5e) for general guidance in creating DLP policies.</span></span>

<span data-ttu-id="18d1f-121">系統會根據 DLP 原則對每個地理位置的適用性來自動同步處理這些原則。</span><span class="sxs-lookup"><span data-stu-id="18d1f-121">The DLP policies are automatically synchronized based on their applicability to each geo location.</span></span>

<span data-ttu-id="18d1f-122">對某個地理位置中的所有使用者執行資訊保護和資料外洩防護原則，不是 UI 中的可用選項，您反而必須選取該原則適用的帳戶，或將該原則全域套用至所有帳戶。</span><span class="sxs-lookup"><span data-stu-id="18d1f-122">Implementing Information Protection and Data Loss prevention policies to all users in a geo location is not an option available in the UI, instead you must select the applicable accounts for the policy or apply the policy globally to all accounts.</span></span>

## <a name="microsoft-flow"></a><span data-ttu-id="18d1f-123">Microsoft Flow</span><span class="sxs-lookup"><span data-stu-id="18d1f-123">Microsoft Flow</span></span>

<span data-ttu-id="18d1f-124">為衛星位置建立的流程將使用位於該租用戶預設地理位置的端點。</span><span class="sxs-lookup"><span data-stu-id="18d1f-124">Flows created for the satellite location will use the end point located in the default geo location for the tenant.</span></span>  <span data-ttu-id="18d1f-125">Microsoft Flow 不是多地理位置服務。</span><span class="sxs-lookup"><span data-stu-id="18d1f-125">Microsoft Flow is not a Multi-Geo service.</span></span> 

## <a name="microsoft-powerapps"></a><span data-ttu-id="18d1f-126">Microsoft PowerApps</span><span class="sxs-lookup"><span data-stu-id="18d1f-126">Microsoft PowerApps</span></span>

<span data-ttu-id="18d1f-127">為衛星位置建立的 PowerApps 將使用位於該租用戶中央位置的端點。</span><span class="sxs-lookup"><span data-stu-id="18d1f-127">PowerApps created for the satellite location will use the end point located in the central location for the tenant.</span></span> <span data-ttu-id="18d1f-128">Microsoft PowerApps 不是多地理位置服務。</span><span class="sxs-lookup"><span data-stu-id="18d1f-128">Microsoft PowerApps is not a Multi-Geo service.</span></span> 

## <a name="onedrive-administrator-experience"></a><span data-ttu-id="18d1f-129">OneDrive 系統管理員體驗</span><span class="sxs-lookup"><span data-stu-id="18d1f-129">OneDrive Administrator Experience</span></span>

<span data-ttu-id="18d1f-p107">[OneDrive 系統管理中心](https://admin.onedrive.com)在左側瀏覽中 (含有地理位置地圖) 具有 [**地理位置**] 索引標籤，您可以在其中檢視及管理您的地理位置。請使用此頁面來新增或刪除您的租用戶地理位置。</span><span class="sxs-lookup"><span data-stu-id="18d1f-p107">The [OneDrive admin center](https://admin.onedrive.com) has a **Geo locations** tab in the left navigation which features a geo locations map where you can view and manage your geo locations. Use this page to add or delete geo locations for your tenant.</span></span>

## <a name="security-and-compliance-admin-center"></a><span data-ttu-id="18d1f-132">安全性與合規性管理中心</span><span class="sxs-lookup"><span data-stu-id="18d1f-132">Security and Compliance Admin Center</span></span>

<span data-ttu-id="18d1f-133">有一個適用於多地理位置租用戶的中央合規性中心：[Microsoft 365 安全性與合規性中心](https://protection.office.com/?rfr=AdminCenter\#/homepage)。</span><span class="sxs-lookup"><span data-stu-id="18d1f-133">There is one central compliance center for a multi-geo tenant: [Microsoft 365 Security & Compliance Center](https://protection.office.com/?rfr=AdminCenter\#/homepage).</span></span>

## <a name="sharepoint-storage-quota"></a><span data-ttu-id="18d1f-134">SharePoint 儲存空間配額</span><span class="sxs-lookup"><span data-stu-id="18d1f-134">SharePoint storage quota</span></span>

<span data-ttu-id="18d1f-135">根據預設，多重地理環境的所有地理位置會共用可用的租用戶儲存空間配額。</span><span class="sxs-lookup"><span data-stu-id="18d1f-135">By default, all geo locations of a multi-geo environment share the available tenant storage quota.</span></span>  <span data-ttu-id="18d1f-136">您也可以為特定的地理位置分配特定配額，以管理儲存空間配額。</span><span class="sxs-lookup"><span data-stu-id="18d1f-136">You can also manage the storage quota by allocating a specific quota for a particular geo location.</span></span> <span data-ttu-id="18d1f-137">如需詳細資訊，請參閱[多地理位置環境中的 SharePoint 儲存空間配額](sharepoint-multi-geo-storage-quota.md)。</span><span class="sxs-lookup"><span data-stu-id="18d1f-137">For more information, see [SharePoint storage quotas in multi-geo environments](sharepoint-multi-geo-storage-quota.md).</span></span>

## <a name="sharing"></a><span data-ttu-id="18d1f-138">共用</span><span class="sxs-lookup"><span data-stu-id="18d1f-138">Sharing</span></span>

<span data-ttu-id="18d1f-139">系統管理員可以設定並管理每個位置的共用原則。</span><span class="sxs-lookup"><span data-stu-id="18d1f-139">Administrators can set and manage sharing policies for each of their locations.</span></span> <span data-ttu-id="18d1f-140">每個地理位置中的 OneDrive 和 SharePoint 網站只會遵守對應的地理位置特定的共用設定。</span><span class="sxs-lookup"><span data-stu-id="18d1f-140">The OneDrive and SharePoint sites in each geo location will honor only the corresponding geo specific sharing settings.</span></span> <span data-ttu-id="18d1f-141">(例如，您可以允許在中央位置[外部共用](https://support.office.com/article/C8A462EB-0723-4B0B-8D0A-70FEAFE4BE85)，但不能在衛星位置外部共用，反之亦然。) 請注意，共用設定不允許在地理位置之間設定共用限制。</span><span class="sxs-lookup"><span data-stu-id="18d1f-141">(For example, you can allow [external sharing](https://support.office.com/article/C8A462EB-0723-4B0B-8D0A-70FEAFE4BE85) for your central location, but not for your satellite location or vice versa.) Note that the sharing settings do not allow configuring sharing limitations between geo locations.</span></span>

## <a name="taxonomy"></a><span data-ttu-id="18d1f-142">分類</span><span class="sxs-lookup"><span data-stu-id="18d1f-142">Taxonomy</span></span>

<span data-ttu-id="18d1f-143">我們使用您公司中央位置主控的主機，針對不同地理位置的企業管理中繼資料，支援統一的[分類法](/sharepoint/managed-metadata)。</span><span class="sxs-lookup"><span data-stu-id="18d1f-143">We support a unified [taxonomy](/sharepoint/managed-metadata) for enterprise managed metadata across geo locations, with the master being hosted in the central location for your company.</span></span> <span data-ttu-id="18d1f-144">我們建議您從中央位置管理全域分類法，並只將特定位置的詞彙增到衛星位置的分類法。</span><span class="sxs-lookup"><span data-stu-id="18d1f-144">We recommend that you manage your global taxonomy from the central location and only add location-specific terms to the satellite location's Taxonomy.</span></span> <span data-ttu-id="18d1f-145">全域分類法詞彙將同步到衛星位置。</span><span class="sxs-lookup"><span data-stu-id="18d1f-145">Global taxonomy terms will synchronize to the satellite locations.</span></span>

<span data-ttu-id="18d1f-146">如需詳細資訊與開發人員指導方針，請參閱[管理多地理位置租用戶中的中繼資料](/sharepoint/dev/solution-guidance/multigeo-managedmetadata)。</span><span class="sxs-lookup"><span data-stu-id="18d1f-146">See [Manage metadata in a multi-geo tenant](/sharepoint/dev/solution-guidance/multigeo-managedmetadata) for additional details and for developer guidance.</span></span>

## <a name="user-profile-application"></a><span data-ttu-id="18d1f-147">使用者設定檔應用程式</span><span class="sxs-lookup"><span data-stu-id="18d1f-147">User Profile Application</span></span>

<span data-ttu-id="18d1f-148">每個地理位置都有一個[使用者設定檔應用程式](/sharepoint/manage-user-profiles)。</span><span class="sxs-lookup"><span data-stu-id="18d1f-148">There is a [user profile application](/sharepoint/manage-user-profiles) in each geo location.</span></span> <span data-ttu-id="18d1f-149">系統會在每位使用者的地理位置主控其設定檔資訊，且該設定檔資料可供該地理位置的系統管理員使用。</span><span class="sxs-lookup"><span data-stu-id="18d1f-149">Each user's profile information is hosted in their geo location and available to the administrator for that geo location.</span></span>

<span data-ttu-id="18d1f-150">如果您有自訂的設定檔屬性，則建議您使用跨地理位置的相同設定檔結構描述，然後在所有的地理位置或所需的位置填入自訂設定檔屬性。</span><span class="sxs-lookup"><span data-stu-id="18d1f-150">If you have custom profile properties, then we recommend that you use the same profile schema across geographies and populate your custom profile properties either in all geo locations or where needed.</span></span> <span data-ttu-id="18d1f-151">如需如何以程式設計方式填入使用者設定檔資料的指導方針，請參閱[大量使用者設定檔更新 API](/sharepoint/dev/solution-guidance/bulk-user-profile-update-api-for-sharepoint-online)。</span><span class="sxs-lookup"><span data-stu-id="18d1f-151">For guidance regarding how to populate user profile data programmatically, please refer to the [Bulk User Profile Update API](/sharepoint/dev/solution-guidance/bulk-user-profile-update-api-for-sharepoint-online).</span></span>

<span data-ttu-id="18d1f-152">如需詳細資訊與開發人員指導方針，請參閱[在多地理位置租用戶中使用使用者設定檔](/sharepoint/dev/solution-guidance/multigeo-userprofileexperience)。</span><span class="sxs-lookup"><span data-stu-id="18d1f-152">See [Work with user profiles in a multi-geo tenant](/sharepoint/dev/solution-guidance/multigeo-userprofileexperience) for additional details and for developer guidance.</span></span>

## <a name="video-portal"></a><span data-ttu-id="18d1f-153">影片入口網站</span><span class="sxs-lookup"><span data-stu-id="18d1f-153">Video Portal</span></span>

<span data-ttu-id="18d1f-154">在多地理位置租用戶中，O365影片入口網站只能從預設地理位置提供，所有使用者將被重新導向至該中央入口網站 URL。</span><span class="sxs-lookup"><span data-stu-id="18d1f-154">In a multi-geo tenant, the O365 Video Portal is served only from default geo and all users will be redirected to that central portal url.</span></span> <span data-ttu-id="18d1f-155">因此，會根據您的中央位置使用該地區的遠端媒體服務 (RMS)，如下所示。</span><span class="sxs-lookup"><span data-stu-id="18d1f-155">Hence, the Remote Media Service (RMS) for that region will be used, as follows based on your central location.</span></span>

<span data-ttu-id="18d1f-156">Stream 目前提供下列語言：</span><span class="sxs-lookup"><span data-stu-id="18d1f-156">Stream is currently available in the following regions:</span></span>

- <span data-ttu-id="18d1f-157">北美地區，主機位於美國</span><span class="sxs-lookup"><span data-stu-id="18d1f-157">North America, hosted in the United States</span></span> 
- <span data-ttu-id="18d1f-158">歐洲</span><span class="sxs-lookup"><span data-stu-id="18d1f-158">Europe</span></span>
- <span data-ttu-id="18d1f-159">亞太地區</span><span class="sxs-lookup"><span data-stu-id="18d1f-159">Asia Pacific</span></span>

<span data-ttu-id="18d1f-160">不過，目前支援 Microsoft 365 影片的下列地區尚無法使用 Stream，因此在這些地區，我們將使用位於最接近支援地區的 RMS。</span><span class="sxs-lookup"><span data-stu-id="18d1f-160">However, Stream is not yet available in the following regions that are currently supported for Microsoft 365 Video, therefore for these local instances, we will use the RMS that is in the closest supported region.</span></span>

- <span data-ttu-id="18d1f-161">澳洲</span><span class="sxs-lookup"><span data-stu-id="18d1f-161">Australia</span></span>
- <span data-ttu-id="18d1f-162">加拿大</span><span class="sxs-lookup"><span data-stu-id="18d1f-162">Canada</span></span>
- <span data-ttu-id="18d1f-163">印度</span><span class="sxs-lookup"><span data-stu-id="18d1f-163">India</span></span>
- <span data-ttu-id="18d1f-164">英國</span><span class="sxs-lookup"><span data-stu-id="18d1f-164">United Kingdom</span></span>

## <a name="yammer"></a><span data-ttu-id="18d1f-165">Yammer</span><span class="sxs-lookup"><span data-stu-id="18d1f-165">Yammer</span></span>

<span data-ttu-id="18d1f-166">Yammer 不是多地理位置工作負載。</span><span class="sxs-lookup"><span data-stu-id="18d1f-166">Yammer is not a Multi-Geo workload.</span></span> <span data-ttu-id="18d1f-167">儲存在 Yammer 中的 yammer 執行緒將會置於租使用者的中央位置。</span><span class="sxs-lookup"><span data-stu-id="18d1f-167">Yammer threads stored in Yammer will be placed in the tenant’s central location.</span></span> <span data-ttu-id="18d1f-168">Yammer 正在推出儲存在 SharePoint 中 Yammer 檔案的檔案儲存變更。</span><span class="sxs-lookup"><span data-stu-id="18d1f-168">Yammer is rolling out a file storage change which will store Yammer files within SharePoint.</span></span> <span data-ttu-id="18d1f-169">儲存在 SharePoint 中的 Yammer 檔案會放入與 Yammer 群組相關聯的 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="18d1f-169">Yammer files stored in SharePoint will be placed the SharePoint site associated with the Yammer group.</span></span> <span data-ttu-id="18d1f-170">SharePoint 群組網站是以 PDL 邏輯為基礎，如 [SharePoint 網站和群組](multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md#sharepoint-sites-and-groups)中所述。</span><span class="sxs-lookup"><span data-stu-id="18d1f-170">SharePoint group sites are based on PDL logic as outlined in [SharePoint Sites and Groups](multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md#sharepoint-sites-and-groups).</span></span>