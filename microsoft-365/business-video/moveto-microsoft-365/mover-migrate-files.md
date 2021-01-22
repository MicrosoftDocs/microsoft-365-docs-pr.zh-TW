---
title: '將 Google 檔案遷移到商務用 Microsoft 365 '
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: 瞭解如何使用 Mover 將 Google 檔案遷移到商務用 Microsoft 365。
ms.openlocfilehash: 99040e4846aba084f40536e88f0aed70998f48be
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928195"
---
# <a name="migrate-google-files-to-microsoft-365-for-business"></a><span data-ttu-id="27c20-103">將 Google 檔案遷移到商務用 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="27c20-103">Migrate Google files to Microsoft 365 for business</span></span> 

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4MhaD?autoplay=false]

<span data-ttu-id="27c20-104">當您移轉商務用 Microsoft 365 時，會想要從 Google 雲端硬碟移轉檔案。</span><span class="sxs-lookup"><span data-stu-id="27c20-104">When you move to Microsoft 365 for business, you’ll want to migrate your files from Google Drive.</span></span> <span data-ttu-id="27c20-105">您可以使用 Mover 應用程式，從個人磁片磁碟機和共用磁片磁碟機移動檔案。</span><span class="sxs-lookup"><span data-stu-id="27c20-105">You can use the Mover app to move files from personal and shared Drives.</span></span> <span data-ttu-id="27c20-106">有關詳細資訊，請參閱 [Mover 雲端移移](https://docs.microsoft.com/sharepointmigration/mover-plan-migration)</span><span class="sxs-lookup"><span data-stu-id="27c20-106">For more information, see [Mover Cloud Migration](https://docs.microsoft.com/sharepointmigration/mover-plan-migration)</span></span>

> [!NOTE]
> <span data-ttu-id="27c20-107">Mover 會製作檔案的複本，並移至商務用 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="27c20-107">Mover will make a copy of the files and move the copies to Microsoft 365 for business.</span></span> <span data-ttu-id="27c20-108">原始檔案也會留在 Google 雲端硬碟中。</span><span class="sxs-lookup"><span data-stu-id="27c20-108">The original files will stay in Google Drives also.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="27c20-109">開始之前</span><span class="sxs-lookup"><span data-stu-id="27c20-109">Before you start</span></span>

<span data-ttu-id="27c20-110">所有使用者都應該已簽署商務用 Microsoft 365 並設定其商務用 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="27c20-110">All the users should have signed in to Microsoft 365 for business and set up their OneDrive for Business.</span></span> <span data-ttu-id="27c20-111">若要這麼做，請 [office.com](https://office.com)您的商務用 Microsft 365 認證進行登錄，然後選擇 [OneDrive。</span><span class="sxs-lookup"><span data-stu-id="27c20-111">To do this, go to [office.com](https://office.com), sign in with you Microsft 365 for business credentials, and then choose OneDrive.</span></span>

## <a name="try-it"></a><span data-ttu-id="27c20-112">試試看吧！</span><span class="sxs-lookup"><span data-stu-id="27c20-112">Try it!</span></span>

### <a name="install-mover"></a><span data-ttu-id="27c20-113">安裝 Mover</span><span class="sxs-lookup"><span data-stu-id="27c20-113">Install Mover</span></span>

1. <span data-ttu-id="27c20-114">在 admin.google.com 上，[請admin.google.com。](https://admin.google.com)</span><span class="sxs-lookup"><span data-stu-id="27c20-114">Sign into your Google Workspace admin console at [admin.google.com](https://admin.google.com).</span></span>

1. <span data-ttu-id="27c20-115">選擇 **應用程式** **、Google Workspace Marketplace 應用程式**，然後 **新增應用程式至網域安裝清單**。</span><span class="sxs-lookup"><span data-stu-id="27c20-115">Choose **Apps**, **Google Workspace Marketplace apps**, Then **Add app to Domain Install list**.</span></span>

1. <span data-ttu-id="27c20-116">搜尋並選取 Mover。</span><span class="sxs-lookup"><span data-stu-id="27c20-116">Search for Mover and select it.</span></span>

1. <span data-ttu-id="27c20-117">選擇 **網域安裝，** 然後 **繼續**。</span><span class="sxs-lookup"><span data-stu-id="27c20-117">Choose **Domain Install**, then **Continue**.</span></span>

1. <span data-ttu-id="27c20-118">請審查許可權，選取核取方塊以同意條款，然後選取 **允許，選擇\*\*\*\*下一** 步，然後 **完成**。</span><span class="sxs-lookup"><span data-stu-id="27c20-118">Review the permissions, select the checkbox to agree to the terms,then select **Allow**, choose **Next**, then **Done**.</span></span>

### <a name="create-connectors-and-run-the-migration"></a><span data-ttu-id="27c20-119">建立連接器及執行移移</span><span class="sxs-lookup"><span data-stu-id="27c20-119">Create Connectors and run the migration</span></span>

1. <span data-ttu-id="27c20-120">返回 **Google Workspace Marketplace 應用程式**。</span><span class="sxs-lookup"><span data-stu-id="27c20-120">Return to **Google Workspace Marketplace apps**.</span></span>
1. <span data-ttu-id="27c20-121">重新更新瀏覽器，然後選取 **Mover** App。</span><span class="sxs-lookup"><span data-stu-id="27c20-121">Refresh your browser, and select the **Mover** app.</span></span>
1. <span data-ttu-id="27c20-122">向下卷軸並選擇通用流覽連結。</span><span class="sxs-lookup"><span data-stu-id="27c20-122">Scroll down and choose the universal navigation link.</span></span>
1. <span data-ttu-id="27c20-123">選取 **授權新連接器**，找到 **G Suite (系統管理員) ，\*\*\*\*然後選擇授權。**</span><span class="sxs-lookup"><span data-stu-id="27c20-123">Select **Authorize New Connector**, locate **G Suite (Admin)**, and choose **Authorize**.</span></span>
1. <span data-ttu-id="27c20-124">您可以變更 **顯示名稱**，然後 **選取授權。**</span><span class="sxs-lookup"><span data-stu-id="27c20-124">Change the **Display Name**, if you want, then select **Authorize**.</span></span>
1. <span data-ttu-id="27c20-125">選擇 Google 系統管理帳戶、審查許可權， **然後選取允許**。</span><span class="sxs-lookup"><span data-stu-id="27c20-125">Choose a Google admin account, review the permissions,then select **Allow**.</span></span>

    <span data-ttu-id="27c20-126">Mover 會顯示所找到的團隊磁片磁碟機和使用者磁片磁碟機數量。</span><span class="sxs-lookup"><span data-stu-id="27c20-126">Mover displays the number of team drives and user drives it discovered.</span></span> 

1. <span data-ttu-id="27c20-127">在 **選取目的地下**，選擇 **授權新連接器**，找出 **Office 365，\*\*\*\*然後選取** 授權。</span><span class="sxs-lookup"><span data-stu-id="27c20-127">Under **Select destination**, choose **Authorize New Connector**, locate **Office 365**, and select **Authorize**.</span></span>
1. <span data-ttu-id="27c20-128">若要將許可權授予您 Azure Active Directory 中的 Mover 應用程式，請 [流覽至](https://aka.ms/Office365MoverAuth)aka.ms/Office365MoverAuth。</span><span class="sxs-lookup"><span data-stu-id="27c20-128">To grant permissions to the Mover app in your Azure Active Directory, navigate to [aka.ms/Office365MoverAuth](https://aka.ms/Office365MoverAuth).</span></span>
1. <span data-ttu-id="27c20-129">選取 **Office 365 Mover、\*\*\*\*許可權、\*\*\*\*為貴公司授予系統管理員同意**。</span><span class="sxs-lookup"><span data-stu-id="27c20-129">Select **Office 365 Mover**, **Permissions**, **Grant admin consent for your company**.</span></span>
1. <span data-ttu-id="27c20-130">選擇您的帳戶、審查許可權， **然後選取接受**。</span><span class="sxs-lookup"><span data-stu-id="27c20-130">Choose your account, review the permissions, and select **Accept**.</span></span>
1. <span data-ttu-id="27c20-131">選擇 **屬性** ，並確認需要 **使用者指派？** 已開啟。</span><span class="sxs-lookup"><span data-stu-id="27c20-131">Choose **Properties** and verify that **User assignment required?** is turned on.</span></span>
1. <span data-ttu-id="27c20-132">回到 Mover App，視需要變更顯示名稱，選擇 **授權，然後** 選取 Microsoft 系統管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="27c20-132">Return to the Mover app, change the **Display Name**, if you want, choose **Authorize**,then select a Microsoft admin account.</span></span>

    <span data-ttu-id="27c20-133">Mover 會告知您 SharePoint Online 使用者或 SPO (網站) 使用者數目。</span><span class="sxs-lookup"><span data-stu-id="27c20-133">Mover will inform you about the number of SharePoint Online (or SPO) sites and users it discovered.</span></span>
1. <span data-ttu-id="27c20-134">選擇 **繼續移移設定**，選取 **新增使用者，** 然後 **自動探索和新增使用者。**</span><span class="sxs-lookup"><span data-stu-id="27c20-134">Choose **Continue Migration Setup**, select **Add Users**, then **Automatically Discover and Add Users**.</span></span>

    <span data-ttu-id="27c20-135">Mover App 會嘗試將雲端硬碟從 Google 的 Source Path，到 Microsoft 365 中的目的地路徑。</span><span class="sxs-lookup"><span data-stu-id="27c20-135">The Mover app will attempt to map drives from the Source Path in Google, to the Destination Path in Microsoft 365.</span></span> 

    <span data-ttu-id="27c20-136">如果磁片磁碟機無法自動進行地圖，請將其目的地路徑新增到 CSV 檔案，我們會稍後再使用這個路徑，將共用磁片磁碟機遷移到 SharePoint 文件庫。</span><span class="sxs-lookup"><span data-stu-id="27c20-136">If a drive doesn’t map automatically, add its destination path to a CSV file, which we’ll use later to migrate the shared drive to a SharePoint document library.</span></span> 

1. <span data-ttu-id="27c20-137">在此案例中，我們已新增名為移案的 SharePoint 網站，並記下檔頁面的 URL。</span><span class="sxs-lookup"><span data-stu-id="27c20-137">In this case, we have added a SharePoint site called Migrated files, and taken note of the URL for the documents page.</span></span> 
1. <span data-ttu-id="27c20-138">接著，我們使用來源路徑、目的地路徑和標記的格式來建立 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="27c20-138">We then created a CSV file using the format of Source Path, Destination Path, and Tags.</span></span> 

    <span data-ttu-id="27c20-139">詳情[請參閱aka.ms/movercsv。](https://docs.microsoft.com/sharepointmigration/mover-create-migration-csv)</span><span class="sxs-lookup"><span data-stu-id="27c20-139">For details see [aka.ms/movercsv](https://docs.microsoft.com/sharepointmigration/mover-create-migration-csv).</span></span>

    <span data-ttu-id="27c20-140">新增目的地路徑 URL 時，請移除共用文件之後的所有專案，例如，這個完整的 URL 將無法執行： `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents/Forms/AllItems.aspx`</span><span class="sxs-lookup"><span data-stu-id="27c20-140">When adding the Destination Path URL, remove everything after Shared Documents for example For example, this full URL won't work: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents/Forms/AllItems.aspx`</span></span>

    <span data-ttu-id="27c20-141">將其變更為：`https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents`</span><span class="sxs-lookup"><span data-stu-id="27c20-141">Change it to: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents`</span></span>

1. <span data-ttu-id="27c20-142">CSV 檔案準備就緒後，請選取移移動作 **、新增** 到移案、**選擇要上傳的檔案**。</span><span class="sxs-lookup"><span data-stu-id="27c20-142">Once your CSV file is ready, select **Migration Actions**, **Add to Migration**, **Choose a file to upload**.</span></span>
1. <span data-ttu-id="27c20-143">流覽至您的 CSV 檔案，選取該檔案，**然後選擇開啟。**</span><span class="sxs-lookup"><span data-stu-id="27c20-143">Navigate to your CSV file, select it,then choose **Open**.</span></span>
1. <span data-ttu-id="27c20-144">選取您想要移移其檔案的使用者磁片磁碟機，然後選擇 **開始移移使用者。**</span><span class="sxs-lookup"><span data-stu-id="27c20-144">Select the user drives whose files you want to migrate, then choose **Start Migrating Users**.</span></span>
1. <span data-ttu-id="27c20-145">請審查移移資訊，選擇何時開始移移，同意條款 **及條件**， **然後選取繼續**。</span><span class="sxs-lookup"><span data-stu-id="27c20-145">Review the migration information, choose when to start the migration, agree to the **Terms and Conditions**, then select **Continue**.</span></span>

<span data-ttu-id="27c20-146">移移程式完成時，Mover App 會通知您。</span><span class="sxs-lookup"><span data-stu-id="27c20-146">The Mover app will inform you when the migration process is complete.</span></span>