---
title: 對應磁碟機準備 Microsoft 受管理的電腦
description: 若要確定重要步驟
keywords: Microsoft 受管理的電腦，Microsoft 365 服務，文件
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: b3fc4a4ed82c01188f348d2e494a0dbf7effc77a
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/15/2019
ms.locfileid: "34079265"
---
#  <a name="prepare-mapped-drives-for-microsoft-managed-desktop"></a><span data-ttu-id="098d8-104">對應磁碟機準備 Microsoft 受管理的電腦</span><span class="sxs-lookup"><span data-stu-id="098d8-104">Prepare mapped drives for Microsoft Managed Desktop</span></span>

<span data-ttu-id="098d8-105">許多企業環境有舊版的需求，以允許共用及儲存檔案，其使用者或小組的對應磁碟機或內部部署應用程式。</span><span class="sxs-lookup"><span data-stu-id="098d8-105">Many enterprise environments have legacy requirements for mapped drives to allow their users or teams to share and store files, or for on-premises applications.</span></span> <span data-ttu-id="098d8-106">Microsoft 不建議使用對應的磁碟機與 Microsoft 受管理的電腦。</span><span class="sxs-lookup"><span data-stu-id="098d8-106">Microsoft does not recommend the use of mapped drives with the Microsoft Managed Desktop.</span></span> <span data-ttu-id="098d8-107">相反地，我們建議您現代化 yor 檔案存取解決方案，如下所示：</span><span class="sxs-lookup"><span data-stu-id="098d8-107">Instead, we recommend that you modernize yor file access solutions as follows:</span></span>
  
- <span data-ttu-id="098d8-108">移轉商務用 onedrive 的個別使用者所使用的對應磁碟機。</span><span class="sxs-lookup"><span data-stu-id="098d8-108">Migrate mapped drives used by individual users to OneDrive for Business.</span></span> 
- <span data-ttu-id="098d8-109">移轉小組用來共用檔案至 SharePoint Online 的對應磁碟機。</span><span class="sxs-lookup"><span data-stu-id="098d8-109">Migrate mapped drives used by teams to share files to SharePoint Online.</span></span> 
- <span data-ttu-id="098d8-110">現代化或取代任何應用程式，用於內部部署檔案共用移除此需求。</span><span class="sxs-lookup"><span data-stu-id="098d8-110">Modernize or replace any applications that use on-premises file shares to remove that requirement.</span></span>
  
<span data-ttu-id="098d8-111">現代化這些服務會允許與 Microsoft 受管理電腦的最佳使用者經驗。</span><span class="sxs-lookup"><span data-stu-id="098d8-111">Modernizing these services will allow the best end-user experience with Microsoft Managed Desktop.</span></span> <span data-ttu-id="098d8-112">Microsoft FastTrack 服務可以協助您使用 Microsoft 雲端服務現代化您的環境。</span><span class="sxs-lookup"><span data-stu-id="098d8-112">Microsoft FastTrack Services can assist you in modernizing your environment by using Microsoft Cloud Services.</span></span> <span data-ttu-id="098d8-113">您可以檢查您是否是合格的 FastTrack 服務[合格服務與計劃](https://docs.microsoft.com/fasttrack/m365-eligible-services-and-plans)，而且再連絡這些直接向 Microsoft 受管理電腦的準備。</span><span class="sxs-lookup"><span data-stu-id="098d8-113">You can check whether you're eligible for FastTrack services at [Eligible Services and Plans](https://docs.microsoft.com/fasttrack/m365-eligible-services-and-plans) and then contact them directly to prepare for Microsoft Managed Desktop.</span></span> <span data-ttu-id="098d8-114">背景 FastTrack 商務用 OneDrive 或 SharePoint Online 移轉資訊，請參閱[資料移轉](https://docs.microsoft.com/fasttrack/o365-data-migration)。</span><span class="sxs-lookup"><span data-stu-id="098d8-114">For background about FastTrack OneDrive for Business or SharePoint Online Migration, see [Data Migration](https://docs.microsoft.com/fasttrack/o365-data-migration).</span></span>

## <a name="mapped-drives-on-microsoft-managed-desktop"></a><span data-ttu-id="098d8-115">Microsoft 受管理的電腦上的對應磁碟機</span><span class="sxs-lookup"><span data-stu-id="098d8-115">Mapped drives on Microsoft Managed Desktop</span></span>
 
<span data-ttu-id="098d8-116">如果您不能移除或取代對應磁碟機，某些使用情況下，您應該提交 Microsoft 受管理電腦入口網站中的支援要求，已將其部署至 Microsoft 受管理電腦的使用者。</span><span class="sxs-lookup"><span data-stu-id="098d8-116">If you cannot remove or replace mapped drives for some use cases, you should submit a support request in the Microsoft Managed Desktop portal to have them deployed to Microsoft Managed Desktop users.</span></span>
    
<span data-ttu-id="098d8-117">這類要求，您必須提供支援要求中的下列詳細資料：</span><span class="sxs-lookup"><span data-stu-id="098d8-117">For such a request, you'll have to provide the following details in the support request:</span></span> 

- <span data-ttu-id="098d8-118">所有的 UNC 路徑，檔案共用必須要對應的 Microsoft 受管理的電腦裝置的位置</span><span class="sxs-lookup"><span data-stu-id="098d8-118">All UNC paths to file share locations that will need to be mapped for Microsoft Managed Desktop devices</span></span> 
- <span data-ttu-id="098d8-119">需要這些檔案共用位置的存取權的使用者群組</span><span class="sxs-lookup"><span data-stu-id="098d8-119">User groups that require access to these file share locations</span></span> 
- <span data-ttu-id="098d8-120">（如果需要） 分派需要任何特定的磁碟機代號</span><span class="sxs-lookup"><span data-stu-id="098d8-120">Any specific drive letter that needs to be assigned (if necessary)</span></span>

<span data-ttu-id="098d8-121">例如：</span><span class="sxs-lookup"><span data-stu-id="098d8-121">For example:</span></span>

| <span data-ttu-id="098d8-122">磁碟機代號</span><span class="sxs-lookup"><span data-stu-id="098d8-122">Drive letter</span></span> | <span data-ttu-id="098d8-123">UNC 路徑</span><span class="sxs-lookup"><span data-stu-id="098d8-123">UNC path</span></span> | <span data-ttu-id="098d8-124">使用者群組</span><span class="sxs-lookup"><span data-stu-id="098d8-124">User group</span></span> |
|--------------|----------|------------|
| <span data-ttu-id="098d8-125">X:</span><span class="sxs-lookup"><span data-stu-id="098d8-125">X:</span></span>  | <span data-ttu-id="098d8-126">\\\server\share\Marketing</span><span class="sxs-lookup"><span data-stu-id="098d8-126">\\\server\share\Marketing</span></span> | <span data-ttu-id="098d8-127">ContosoMarketing</span><span class="sxs-lookup"><span data-stu-id="098d8-127">ContosoMarketing</span></span> |

<span data-ttu-id="098d8-128">它完全是為了確保使用者和群組具有，並維持適當的權限來存取檔案共用位置與內部部署檔案服務仍然可以存取您的責任。</span><span class="sxs-lookup"><span data-stu-id="098d8-128">It's entirely your responsibility to ensure that users and groups have and maintain the right permissions to access file share locations and that the on-premises file services remain accessible.</span></span> <span data-ttu-id="098d8-129">此外，您應該儘速移除這類檔案共用的需求。</span><span class="sxs-lookup"><span data-stu-id="098d8-129">Also, you should remove your requirements for such file shares as soon as possible.</span></span>

### <a name="to-have-mapped-drives-deployed-in-microsoft-managed-desktop"></a><span data-ttu-id="098d8-130">若要有對應的部署中 Microsoft 受管理電腦的磁碟機</span><span class="sxs-lookup"><span data-stu-id="098d8-130">To have mapped drives deployed in Microsoft Managed Desktop</span></span>
 
<span data-ttu-id="098d8-131">請確定對應磁碟機無法避免使用，而且您提交任何服務要求之前先仔細檢閱需求。</span><span class="sxs-lookup"><span data-stu-id="098d8-131">Make sure that mapped drives cannot be avoided and you have carefully reviewed the requirements before submitting any service request.</span></span> <span data-ttu-id="098d8-132">然後遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="098d8-132">Then follow these steps:</span></span>

1. <span data-ttu-id="098d8-133">瀏覽至[Microsoft 受管理電腦入口網站](https://aka.ms/mmdportal)。</span><span class="sxs-lookup"><span data-stu-id="098d8-133">Navigate to the [Microsoft Managed Desktop portal](https://aka.ms/mmdportal).</span></span>  
2. <span data-ttu-id="098d8-134">透過**支援 > 支援要求**] 區段中提交支援要求標題為 「 對應磁碟機部署 」，並提供所有必要的檔案共用的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="098d8-134">Submit a support request titled “Mapped drives deployment” through the **Support > Support requests** section and provide all the required file share details.</span></span>  
3. <span data-ttu-id="098d8-135">Microsoft 受管理的桌上型電腦作業將會告知，藉由使用時，支援要求的更新，要求已完成。</span><span class="sxs-lookup"><span data-stu-id="098d8-135">Microsoft Managed Desktop Operations will advise, by using support request updates, when the request has been completed.</span></span> <span data-ttu-id="098d8-136">最初將只部署此組態，測試部署群組中的裝置。</span><span class="sxs-lookup"><span data-stu-id="098d8-136">Initially this configuration will only be deployed to devices in the Test deployment group.</span></span>  
4. <span data-ttu-id="098d8-137">您必須測試並確認 Microsoft 受管理的桌上型電腦作業小組所部署的組態是否運作如預期般。</span><span class="sxs-lookup"><span data-stu-id="098d8-137">You must test and confirm whether the configuration deployed by the Microsoft Managed Desktop Operations team works as you expect.</span></span> <span data-ttu-id="098d8-138">當您完成測試更新 Microsoft 受管理電腦作業使用支援要求。</span><span class="sxs-lookup"><span data-stu-id="098d8-138">Use the support request to update Microsoft Managed Desktop Operations once you've completed your testing.</span></span>  
5. <span data-ttu-id="098d8-139">Microsoft 受管理的桌上型電腦作業小組會再將設定部署至其他部署群組。</span><span class="sxs-lookup"><span data-stu-id="098d8-139">Microsoft Managed Desktop Operations team will then deploy the configuration to the other deployment groups.</span></span> 