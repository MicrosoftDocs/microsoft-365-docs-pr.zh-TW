---
title: 為 Microsoft 受管理的電腦準備對應磁碟機
description: 確定使用者可以存取對應磁片磁碟機上之資料的重要步驟
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: f770f5083fe9193660b03e7971b09a127f2dae16
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574556"
---
#  <a name="prepare-mapped-drives-for-microsoft-managed-desktop"></a><span data-ttu-id="f0932-104">為 Microsoft 受管理的電腦準備對應磁碟機</span><span class="sxs-lookup"><span data-stu-id="f0932-104">Prepare mapped drives for Microsoft Managed Desktop</span></span>

<span data-ttu-id="f0932-105">許多企業環境對對應的磁片磁碟機具有舊版需求，以允許其使用者或小組共用及儲存檔案，或用於內部部署應用程式。</span><span class="sxs-lookup"><span data-stu-id="f0932-105">Many enterprise environments have legacy requirements for mapped drives to allow their users or teams to share and store files, or for on-premises applications.</span></span> <span data-ttu-id="f0932-106">Microsoft 不建議搭配 Microsoft Managed Desktop 使用對應的磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="f0932-106">Microsoft does not recommend the use of mapped drives with the Microsoft Managed Desktop.</span></span> <span data-ttu-id="f0932-107">相反地，我們建議您現代化檔存取解決方案，如下所示：</span><span class="sxs-lookup"><span data-stu-id="f0932-107">Instead, we recommend that you modernize your file access solutions as follows:</span></span>
  
- <span data-ttu-id="f0932-108">將個別使用者所使用的對應磁片磁碟機遷移至 OneDrive 商務。</span><span class="sxs-lookup"><span data-stu-id="f0932-108">Migrate mapped drives used by individual users to OneDrive for Business.</span></span> 
- <span data-ttu-id="f0932-109">遷移小組所用的對應磁片磁碟機，以共用檔案至 SharePoint 線上。</span><span class="sxs-lookup"><span data-stu-id="f0932-109">Migrate mapped drives used by teams to share files to SharePoint Online.</span></span> 
- <span data-ttu-id="f0932-110">[現代化] 或 [取代] 任何使用內部部署檔案共用的應用程式，以移除該需求。</span><span class="sxs-lookup"><span data-stu-id="f0932-110">Modernize or replace any applications that use on-premises file shares to remove that requirement.</span></span>
  
<span data-ttu-id="f0932-111">現代化這些服務可讓 Microsoft 受管理的電腦取得最佳的使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="f0932-111">Modernizing these services will allow the best user experience with Microsoft Managed Desktop.</span></span> <span data-ttu-id="f0932-112">Microsoft FastTrack 服務可協助您使用 Microsoft 雲端服務現代化您的環境。</span><span class="sxs-lookup"><span data-stu-id="f0932-112">Microsoft FastTrack Services can assist you in modernizing your environment by using Microsoft Cloud Services.</span></span> <span data-ttu-id="f0932-113">您可以檢查您是否符合 [合格服務與計畫](/fasttrack/m365-eligible-services-and-plans) 的 FastTrack 服務，然後直接與他們聯繫以準備 Microsoft 受管理的電腦。</span><span class="sxs-lookup"><span data-stu-id="f0932-113">You can check whether you're eligible for FastTrack services at [Eligible Services and Plans](/fasttrack/m365-eligible-services-and-plans) and then contact them directly to prepare for Microsoft Managed Desktop.</span></span> <span data-ttu-id="f0932-114">如需 FastTrack 商務 OneDrive 或 SharePoint 線上遷移的背景，請參閱 [資料移轉](/fasttrack/o365-data-migration)。</span><span class="sxs-lookup"><span data-stu-id="f0932-114">For background about FastTrack OneDrive for Business or SharePoint Online Migration, see [Data Migration](/fasttrack/o365-data-migration).</span></span>

## <a name="mapped-drives-on-microsoft-managed-desktop"></a><span data-ttu-id="f0932-115">Microsoft 受管理電腦上的對應磁片磁碟機</span><span class="sxs-lookup"><span data-stu-id="f0932-115">Mapped drives on Microsoft Managed Desktop</span></span>
 
<span data-ttu-id="f0932-116">如果您無法移除或取代某些使用案例中的對應磁片磁碟機，您應該提交 Microsoft Managed Desktop admin 入口網站的支援要求，將其部署至 Microsoft 受管理的桌面使用者。</span><span class="sxs-lookup"><span data-stu-id="f0932-116">If you cannot remove or replace mapped drives for some use cases, you should submit a support request in the Microsoft Managed Desktop admin portal to have them deployed to Microsoft Managed Desktop users.</span></span>
    
<span data-ttu-id="f0932-117">針對這類要求，您必須在支援要求中提供下列詳細資料：</span><span class="sxs-lookup"><span data-stu-id="f0932-117">For such a request, you'll have to provide the following details in the support request:</span></span> 

- <span data-ttu-id="f0932-118">必須對應至 Microsoft 受管理的電腦裝置的檔案共用位置的所有 UNC 路徑</span><span class="sxs-lookup"><span data-stu-id="f0932-118">All UNC paths to file share locations that will need to be mapped for Microsoft Managed Desktop devices</span></span> 
- <span data-ttu-id="f0932-119">需要存取這些檔案共用位置的使用者群組</span><span class="sxs-lookup"><span data-stu-id="f0932-119">User groups that require access to these file share locations</span></span> 
- <span data-ttu-id="f0932-120">必要時必須指派 (任何特定的磁碟機號) </span><span class="sxs-lookup"><span data-stu-id="f0932-120">Any specific drive letter that needs to be assigned (if necessary)</span></span>

<span data-ttu-id="f0932-121">例如：</span><span class="sxs-lookup"><span data-stu-id="f0932-121">For example:</span></span>

| <span data-ttu-id="f0932-122">磁碟機號</span><span class="sxs-lookup"><span data-stu-id="f0932-122">Drive letter</span></span> | <span data-ttu-id="f0932-123">UNC 路徑</span><span class="sxs-lookup"><span data-stu-id="f0932-123">UNC path</span></span> | <span data-ttu-id="f0932-124">使用者群組</span><span class="sxs-lookup"><span data-stu-id="f0932-124">User group</span></span> |
|--------------|----------|------------|
| <span data-ttu-id="f0932-125">X：</span><span class="sxs-lookup"><span data-stu-id="f0932-125">X:</span></span>  | <span data-ttu-id="f0932-126">\\\server\share\Marketing</span><span class="sxs-lookup"><span data-stu-id="f0932-126">\\\server\share\Marketing</span></span> | <span data-ttu-id="f0932-127">ContosoMarketing</span><span class="sxs-lookup"><span data-stu-id="f0932-127">ContosoMarketing</span></span> |

<span data-ttu-id="f0932-128">您應完全負責確保使用者和群組具有及維護存取檔案共用位置的適當許可權，且內部部署檔案服務仍然可供存取。</span><span class="sxs-lookup"><span data-stu-id="f0932-128">It's entirely your responsibility to ensure that users and groups have and maintain the right permissions to access file share locations and that the on-premises file services remain accessible.</span></span> <span data-ttu-id="f0932-129">此外，您也應該儘快移除這些檔案共用的需求。</span><span class="sxs-lookup"><span data-stu-id="f0932-129">Also, you should remove your requirements for such file shares as soon as possible.</span></span>

### <a name="to-have-mapped-drives-deployed-in-microsoft-managed-desktop"></a><span data-ttu-id="f0932-130">在 Microsoft 受管理的電腦中部署對應磁片磁碟機</span><span class="sxs-lookup"><span data-stu-id="f0932-130">To have mapped drives deployed in Microsoft Managed Desktop</span></span>
 
<span data-ttu-id="f0932-131">請確定無法避免使用對應的磁片磁碟機，而且在提交任何服務要求之前，您已仔細查看需求。</span><span class="sxs-lookup"><span data-stu-id="f0932-131">Make sure that mapped drives cannot be avoided and you have carefully reviewed the requirements before submitting any service request.</span></span> <span data-ttu-id="f0932-132">請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="f0932-132">Then follow these steps:</span></span>

1. <span data-ttu-id="f0932-133">流覽至 [ [Microsoft 端點管理員](https://endpoint.microsoft.com/) ]，然後選取 [疑難排解 + 支援]，然後在 [Microsoft 受管理的桌面] 區段中尋找「服務要求」。</span><span class="sxs-lookup"><span data-stu-id="f0932-133">Navigate to [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) and select "Troubleshooting + support" then look for "Service requests" under the Microsoft Managed Desktop section.</span></span>  
2. <span data-ttu-id="f0932-134">提交名為 "對應的磁片磁碟機部署" 的支援要求，並提供所有必要的檔案共用詳細資料。</span><span class="sxs-lookup"><span data-stu-id="f0932-134">Submit a support request titled “Mapped drives deployment” and provide all the required file share details.</span></span>  
3. <span data-ttu-id="f0932-135">Microsoft 受管理的桌面 IT 作業會在要求完成時，使用支援要求更新通知。</span><span class="sxs-lookup"><span data-stu-id="f0932-135">Microsoft Managed Desktop IT Operations will advise, by using support request updates, when the request has been completed.</span></span> <span data-ttu-id="f0932-136">起初，此設定只會部署至測試部署群組中的裝置。</span><span class="sxs-lookup"><span data-stu-id="f0932-136">Initially this configuration will only be deployed to devices in the Test deployment group.</span></span>  
4. <span data-ttu-id="f0932-137">您必須測試及確認 Microsoft 受管理的桌面 IT 作業所部署的設定是否如預期的那樣運作。</span><span class="sxs-lookup"><span data-stu-id="f0932-137">You must test and confirm whether the configuration deployed by the Microsoft Managed Desktop IT Operations works as you expect.</span></span> <span data-ttu-id="f0932-138">使用相同支援要求的詳細資料中的 [討論] 索引標籤回復，以在您完成測試時通知 Microsoft 受管理的桌面 IT 作業。</span><span class="sxs-lookup"><span data-stu-id="f0932-138">Reply using the Discussion tab in the details of the same support request to notify Microsoft Managed Desktop IT Operations once you've completed your testing.</span></span>  
5. <span data-ttu-id="f0932-139">Microsoft 受管理的桌面 IT 作業小組接著會將設定部署至其他部署群組。</span><span class="sxs-lookup"><span data-stu-id="f0932-139">Microsoft Managed Desktop IT Operations team will then deploy the configuration to the other deployment groups.</span></span> 

## <a name="steps-to-get-ready"></a><span data-ttu-id="f0932-140">準備就緒的步驟</span><span class="sxs-lookup"><span data-stu-id="f0932-140">Steps to get ready</span></span>

1. <span data-ttu-id="f0932-141">檢查 [Microsoft 受管理的桌面的必要條件](prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="f0932-141">Review [Prerequisites for Microsoft Managed Desktop](prerequisites.md).</span></span>
2. <span data-ttu-id="f0932-142">[使用準備工作評估工具](readiness-assessment-tool.md)。</span><span class="sxs-lookup"><span data-stu-id="f0932-142">[Use Readiness assessment tools](readiness-assessment-tool.md).</span></span>
3. [<span data-ttu-id="f0932-143">來賓帳戶的先決條件</span><span class="sxs-lookup"><span data-stu-id="f0932-143">Prerequisites for guest accounts</span></span>](guest-accounts.md)
4. [<span data-ttu-id="f0932-144">Microsoft 受管理電腦的網路設定</span><span class="sxs-lookup"><span data-stu-id="f0932-144">Network configuration for Microsoft Managed Desktop</span></span>](network.md)
5. [<span data-ttu-id="f0932-145">為 Microsoft 受管理的電腦準備認證和網路設定檔</span><span class="sxs-lookup"><span data-stu-id="f0932-145">Prepare certificates and network profiles for Microsoft Managed Desktop</span></span>](certs-wifi-lan.md)
6. [<span data-ttu-id="f0932-146">為 Microsoft 受管理的電腦準備備內部部署資源存取權</span><span class="sxs-lookup"><span data-stu-id="f0932-146">Prepare on-premises resources access for Microsoft Managed Desktop</span></span>](authentication.md)
7. [<span data-ttu-id="f0932-147">Microsoft 受管理電腦中的應用程式</span><span class="sxs-lookup"><span data-stu-id="f0932-147">Apps in Microsoft Managed Desktop</span></span>](apps.md)
8. <span data-ttu-id="f0932-148">[為 Microsoft Managed Desktop 準備對應的磁片磁碟機](mapped-drives.md) (本文) </span><span class="sxs-lookup"><span data-stu-id="f0932-148">[Prepare mapped drives for Microsoft Managed Desktop](mapped-drives.md) (This article)</span></span>
9. [<span data-ttu-id="f0932-149">為 Microsoft 受管理的電腦準備列印資源</span><span class="sxs-lookup"><span data-stu-id="f0932-149">Prepare printing resources for Microsoft Managed Desktop</span></span>](printing.md)
