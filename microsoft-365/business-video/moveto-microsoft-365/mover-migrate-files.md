---
title: '將 Google 檔案遷移至 Microsoft 365 for business '
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
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: 瞭解如何使用移動器將 Google 檔案遷移至 Microsoft 365 for business。
ms.openlocfilehash: 72ea81ad86a20e01b4650915fef96a713b207c3b
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166156"
---
# <a name="migrate-google-files-to-microsoft-365-for-business"></a><span data-ttu-id="5e20c-103">將 Google 檔案遷移至 Microsoft 365 for business</span><span class="sxs-lookup"><span data-stu-id="5e20c-103">Migrate Google files to Microsoft 365 for business</span></span> 

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4MhaD?autoplay=false]

<span data-ttu-id="5e20c-104">當您移至 Microsoft 365 for business 時，您會想要從 Google Drive 遷移檔案。</span><span class="sxs-lookup"><span data-stu-id="5e20c-104">When you move to Microsoft 365 for business, you'll want to migrate your files from Google Drive.</span></span> <span data-ttu-id="5e20c-105">您可以使用移動器應用程式，從個人和共用磁片磁碟機移動檔案。</span><span class="sxs-lookup"><span data-stu-id="5e20c-105">You can use the Mover app to move files from personal and shared Drives.</span></span> <span data-ttu-id="5e20c-106">如需詳細資訊，請參閱 [移動雲端遷移](https://docs.microsoft.com/sharepointmigration/mover-plan-migration)。</span><span class="sxs-lookup"><span data-stu-id="5e20c-106">For more information, see [Mover Cloud Migration](https://docs.microsoft.com/sharepointmigration/mover-plan-migration).</span></span>

> [!NOTE]
> <span data-ttu-id="5e20c-107">移動器會製作檔案複本，並將複本移至 Microsoft 365 for business。</span><span class="sxs-lookup"><span data-stu-id="5e20c-107">Mover will make a copy of the files and move the copies to Microsoft 365 for business.</span></span> <span data-ttu-id="5e20c-108">原始檔案也會保留在 Google 磁片磁碟機中。</span><span class="sxs-lookup"><span data-stu-id="5e20c-108">The original files will stay in Google Drives also.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="5e20c-109">開始之前</span><span class="sxs-lookup"><span data-stu-id="5e20c-109">Before you start</span></span>

<span data-ttu-id="5e20c-110">所有使用者都應該登入 Microsoft 365 for business，並設定其 OneDrive 的商務用。</span><span class="sxs-lookup"><span data-stu-id="5e20c-110">All the users should have signed in to Microsoft 365 for business and set up their OneDrive for Business.</span></span> <span data-ttu-id="5e20c-111">若要這麼做，請移至 [office.com](https://office.com)，使用您的 Microsoft 365 商務版認證登入，然後選擇 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="5e20c-111">To do this, go to [office.com](https://office.com), sign in with your Microsoft 365 for business credentials, and then choose OneDrive.</span></span>

## <a name="try-it"></a><span data-ttu-id="5e20c-112">試試看吧！</span><span class="sxs-lookup"><span data-stu-id="5e20c-112">Try it!</span></span>

### <a name="install-mover"></a><span data-ttu-id="5e20c-113">安裝移動器</span><span class="sxs-lookup"><span data-stu-id="5e20c-113">Install Mover</span></span>

1. <span data-ttu-id="5e20c-114">在 [admin.google.com](https://admin.google.com)登入 Google Workspace 管理主控台。</span><span class="sxs-lookup"><span data-stu-id="5e20c-114">Sign in to your Google Workspace admin console at [admin.google.com](https://admin.google.com).</span></span>

1. <span data-ttu-id="5e20c-115">選擇 [**應用** 程式  >  **Google Workspace Marketplace 應用** 程式  >  **將應用程式新增至網域安裝] 清單**。</span><span class="sxs-lookup"><span data-stu-id="5e20c-115">Choose **Apps** > **Google Workspace Marketplace apps** > **Add app to Domain Install list**.</span></span>

1. <span data-ttu-id="5e20c-116">搜尋移動器並選取它。</span><span class="sxs-lookup"><span data-stu-id="5e20c-116">Search for Mover and select it.</span></span>

1. <span data-ttu-id="5e20c-117">選擇 [ **網域安裝**]，然後 **繼續**。</span><span class="sxs-lookup"><span data-stu-id="5e20c-117">Choose **Domain Install**, then **Continue**.</span></span>

1. <span data-ttu-id="5e20c-118">檢查許可權，選取 [同意] 核取方塊，然後選取 [ **允許**]，再選擇 **[下一步]**，然後 **執行**。</span><span class="sxs-lookup"><span data-stu-id="5e20c-118">Review the permissions, select the checkbox to agree to the terms,then select **Allow**, choose **Next**, then **Done**.</span></span>

### <a name="create-connectors-and-run-the-migration"></a><span data-ttu-id="5e20c-119">建立連接器並執行遷移</span><span class="sxs-lookup"><span data-stu-id="5e20c-119">Create Connectors and run the migration</span></span>

1. <span data-ttu-id="5e20c-120">回到 **Google Workspace Marketplace 應用程式**。</span><span class="sxs-lookup"><span data-stu-id="5e20c-120">Return to **Google Workspace Marketplace apps**.</span></span>
1. <span data-ttu-id="5e20c-121">重新整理瀏覽器，然後選取 **移動** 器應用程式。</span><span class="sxs-lookup"><span data-stu-id="5e20c-121">Refresh your browser, and select the **Mover** app.</span></span>
1. <span data-ttu-id="5e20c-122">向左下向，然後選擇通用導覽連結。</span><span class="sxs-lookup"><span data-stu-id="5e20c-122">Scroll down and choose the universal navigation link.</span></span>
1. <span data-ttu-id="5e20c-123">選取 [ **授權新的連接器**]，找出 [ **G Suite (管理)**]，然後選擇 [ **授權**]。</span><span class="sxs-lookup"><span data-stu-id="5e20c-123">Select **Authorize New Connector**, locate **G Suite (Admin)**, and choose **Authorize**.</span></span>
1. <span data-ttu-id="5e20c-124">如有需要，請變更 **顯示名稱**，然後選取 [ **授權**]。</span><span class="sxs-lookup"><span data-stu-id="5e20c-124">Change the **Display Name**, if you want, then select **Authorize**.</span></span>
1. <span data-ttu-id="5e20c-125">選擇 Google 系統管理員帳戶，複查許可權，然後選取 [ **允許**]。</span><span class="sxs-lookup"><span data-stu-id="5e20c-125">Choose a Google admin account, review the permissions,then select **Allow**.</span></span>

    <span data-ttu-id="5e20c-126">移動器顯示所探索的團隊磁片磁碟機和使用者磁片數目。</span><span class="sxs-lookup"><span data-stu-id="5e20c-126">Mover displays the number of team drives and user drives it discovered.</span></span> 

1. <span data-ttu-id="5e20c-127">在 [ **選取目的地**] 底下，選擇 [ **授權新的連接器**]，找到 **Office 365**，然後選取 [ **授權**]。</span><span class="sxs-lookup"><span data-stu-id="5e20c-127">Under **Select destination**, choose **Authorize New Connector**, locate **Office 365**, and select **Authorize**.</span></span>
1. <span data-ttu-id="5e20c-128">若要將許可權授與您的 Azure Active Directory 中的移動器應用程式，請流覽至 [aka.ms/Office365MoverAuth](https://aka.ms/Office365MoverAuth)。</span><span class="sxs-lookup"><span data-stu-id="5e20c-128">To grant permissions to the Mover app in your Azure Active Directory, navigate to [aka.ms/Office365MoverAuth](https://aka.ms/Office365MoverAuth).</span></span>
1. <span data-ttu-id="5e20c-129">選取 [ **Office 365 移動器**] **許可權**， **授與您公司的系統管理員同意**。</span><span class="sxs-lookup"><span data-stu-id="5e20c-129">Select **Office 365 Mover**, **Permissions**, **Grant admin consent for your company**.</span></span>
1. <span data-ttu-id="5e20c-130">選擇您的帳戶，查看許可權，然後選取 [ **接受**]。</span><span class="sxs-lookup"><span data-stu-id="5e20c-130">Choose your account, review the permissions, and select **Accept**.</span></span>
1. <span data-ttu-id="5e20c-131">選擇 [ **屬性** ]，然後確認 [ **需要使用者指派]？** 已開啟。</span><span class="sxs-lookup"><span data-stu-id="5e20c-131">Choose **Properties** and verify that **User assignment required?** is turned on.</span></span>
1. <span data-ttu-id="5e20c-132">回到移動器應用程式，變更 **顯示名稱**（如有需要），選擇 [ **授權**]，然後選取 Microsoft 系統管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="5e20c-132">Return to the Mover app, change the **Display Name**, if you want, choose **Authorize**,then select a Microsoft admin account.</span></span>

    <span data-ttu-id="5e20c-133">行動電話會通知您 SharePoint 線上 (或 SPO) 網站與所探索的使用者數目。</span><span class="sxs-lookup"><span data-stu-id="5e20c-133">Mover will inform you about the number of SharePoint Online (or SPO) sites and users it discovered.</span></span>
1. <span data-ttu-id="5e20c-134">選擇 [ **繼續遷移設定**]，選取 [ **新增使用者**]，然後 **自動探索及新增使用者**。</span><span class="sxs-lookup"><span data-stu-id="5e20c-134">Choose **Continue Migration Setup**, select **Add Users**, then **Automatically Discover and Add Users**.</span></span>

    <span data-ttu-id="5e20c-135">移動器應用程式會嘗試將 Google 中來源路徑的磁片磁碟機，對應至 Microsoft 365 中的目的地路徑。</span><span class="sxs-lookup"><span data-stu-id="5e20c-135">The Mover app will attempt to map drives from the Source Path in Google, to the Destination Path in Microsoft 365.</span></span> 

    <span data-ttu-id="5e20c-136">如果磁片磁碟機未自動對應，請將其目的地路徑新增至 CSV 檔案，我們稍後將用來將共用磁片磁碟機遷移至 SharePoint 文件庫。</span><span class="sxs-lookup"><span data-stu-id="5e20c-136">If a drive doesn't map automatically, add its destination path to a CSV file, which we'll use later to migrate the shared drive to a SharePoint document library.</span></span> 

1. <span data-ttu-id="5e20c-137">在此情況下，我們已新增稱為「遷移檔案」的 SharePoint 網站，並記下 [檔] 頁面的 URL。</span><span class="sxs-lookup"><span data-stu-id="5e20c-137">In this case, we have added a SharePoint site called Migrated files, and taken note of the URL for the documents page.</span></span> 
1. <span data-ttu-id="5e20c-138">然後，我們會使用來源路徑、目的地路徑及標記的格式建立 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="5e20c-138">We then created a CSV file using the format of Source Path, Destination Path, and Tags.</span></span> 

    <span data-ttu-id="5e20c-139">如需詳細資訊，請參閱 [aka.ms/movercsv](https://docs.microsoft.com/sharepointmigration/mover-create-migration-csv)。</span><span class="sxs-lookup"><span data-stu-id="5e20c-139">For details see [aka.ms/movercsv](https://docs.microsoft.com/sharepointmigration/mover-create-migration-csv).</span></span>

    <span data-ttu-id="5e20c-140">新增目的地路徑 URL 時，請移除共用檔之後的所有專案。</span><span class="sxs-lookup"><span data-stu-id="5e20c-140">When adding the Destination Path URL, remove everything after Shared Documents.</span></span> <span data-ttu-id="5e20c-141">例如，以下完整的 URL 將無法運作：`https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents/Forms/AllItems.aspx`</span><span class="sxs-lookup"><span data-stu-id="5e20c-141">For example, this full URL won't work: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents/Forms/AllItems.aspx`</span></span>

    <span data-ttu-id="5e20c-142">將其變更為：`https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents`</span><span class="sxs-lookup"><span data-stu-id="5e20c-142">Change it to: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents`</span></span>

1. <span data-ttu-id="5e20c-143">當您的 CSV 檔案準備好後，請選取 [ **遷移動作**] [ **新增至遷移**]，然後 **選擇要上傳的** 檔案。</span><span class="sxs-lookup"><span data-stu-id="5e20c-143">Once your CSV file is ready, select **Migration Actions**, **Add to Migration**, **Choose a file to upload**.</span></span>
1. <span data-ttu-id="5e20c-144">流覽至您的 CSV 檔案，選取它，然後選擇 [ **開啟**]。</span><span class="sxs-lookup"><span data-stu-id="5e20c-144">Navigate to your CSV file, select it,then choose **Open**.</span></span>
1. <span data-ttu-id="5e20c-145">選取您要遷移其檔案的使用者磁片磁碟機，然後選擇 [ **開始遷移使用者**]。</span><span class="sxs-lookup"><span data-stu-id="5e20c-145">Select the user drives whose files you want to migrate, then choose **Start Migrating Users**.</span></span>
1. <span data-ttu-id="5e20c-146">檢查遷移資訊，選擇何時開始遷移，請同意 **條款及條件**，然後選取 [ **繼續**]。</span><span class="sxs-lookup"><span data-stu-id="5e20c-146">Review the migration information, choose when to start the migration, agree to the **Terms and Conditions**, then select **Continue**.</span></span>

<span data-ttu-id="5e20c-147">移動器應用程式會在遷移過程完成時通知您。</span><span class="sxs-lookup"><span data-stu-id="5e20c-147">The Mover app will inform you when the migration process is complete.</span></span>
