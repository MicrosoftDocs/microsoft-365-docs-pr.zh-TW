---
title: 新增自訂磚至 App 啟動器
f1.keywords:
- CSH
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
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 1136115a-75af-4497-b693-640c4ce70bc6
description: '新增自訂磚至應用程式啟動器，以建立電子郵件、檔、App、SharePoint 網站、外部網站及其他資源的快速連結。 '
ms.openlocfilehash: 2bbcf64b807754aed199c441f6df028d5fe20a97
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926231"
---
# <a name="add-custom-tiles-to-the-app-launcher"></a><span data-ttu-id="6872a-103">新增自訂磚至 App 啟動器</span><span class="sxs-lookup"><span data-stu-id="6872a-103">Add custom tiles to the app launcher</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="6872a-104">系統管理中心正在變更。</span><span class="sxs-lookup"><span data-stu-id="6872a-104">The admin center is changing.</span></span> <span data-ttu-id="6872a-105">如果您的體驗不符合此處所示的詳細資料，請參閱 [關於新版 Microsoft 365 系統管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet) (英文)。</span><span class="sxs-lookup"><span data-stu-id="6872a-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="6872a-106">在 Microsoft 365 中，您可以使用應用程式啟動器快速且輕鬆地取得您的電子郵件、月曆、檔和應用程式， ([深入瞭解) 。](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a)</span><span class="sxs-lookup"><span data-stu-id="6872a-106">In Microsoft 365, you can quickly and easily get to your email, calendars, documents, and apps using the App launcher ([learn more](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a)).</span></span> <span data-ttu-id="6872a-107">這些是您從 Microsoft 365 取得的應用程式，以及您從 [SharePoint Store](https://support.microsoft.com/office/dd98e50e-d3db-4ecb-9bb7-82b189822d43) 或 [Azure AD](https://msdn.microsoft.com/office/office365/howto/connect-your-app-to-o365-app-launcher)新增的自訂應用程式。</span><span class="sxs-lookup"><span data-stu-id="6872a-107">These are apps you get with Microsoft 365 as well as custom apps that you add from the [SharePoint Store](https://support.microsoft.com/office/dd98e50e-d3db-4ecb-9bb7-82b189822d43) or [Azure AD](https://msdn.microsoft.com/office/office365/howto/connect-your-app-to-o365-app-launcher).</span></span>
  
<span data-ttu-id="6872a-108">您可以新增自己的自訂磚至應用程式啟動器，用來指向 SharePoint 網站、外部網站、舊版應用程式及其他項目。</span><span class="sxs-lookup"><span data-stu-id="6872a-108">You can add your own custom tiles to the app launcher that point to SharePoint sites, external sites, legacy apps, and more.</span></span> <span data-ttu-id="6872a-109">自訂磚會出現在應用程式啟動器的所有 App下，但您可以將它釘釘到家用App，並指示使用者執行相同的操作。</span><span class="sxs-lookup"><span data-stu-id="6872a-109">The custom tile appears under the app launcher's **All** apps, but you can pin it to the **Home** apps and instruct your users to do the same.</span></span> <span data-ttu-id="6872a-110">這麼一來，您就可以輕鬆尋找相關的網站、App 和資源來完成您的工作。</span><span class="sxs-lookup"><span data-stu-id="6872a-110">This makes it easy to find the relevant sites, apps, and resources to do your job.</span></span> <span data-ttu-id="6872a-111">在下面這個範例中，名為「Contoso 入口網站」的磚，就是用來存取組織 SharePoint 內部網路網站的自訂磚。</span><span class="sxs-lookup"><span data-stu-id="6872a-111">In the below example, a custom tile called "Contoso Portal" is used to access an organization's SharePoint intranet site.</span></span> 
  
![應用程式啟動器](../../media/7acc06cc-ac7a-4c6e-8ea7-81570a5bdbab.png)
  
## <a name="add-a-custom-tile-to-the-app-launcher"></a><span data-ttu-id="6872a-113">在 App 啟動器上新增自訂磚</span><span class="sxs-lookup"><span data-stu-id="6872a-113">Add a custom tile to the app launcher</span></span>

1. <span data-ttu-id="6872a-114">以全域管理員的名列號到系統管理中心，前往設定  >  **組織設定**，然後選擇組織 **設定檔的 Tab。**</span><span class="sxs-lookup"><span data-stu-id="6872a-114">Sign in to the admin center as a Global Administrator, go to **Settings** > **Org Settings**, and choose the **Organization profile** tab.</span></span>
    
2. <span data-ttu-id="6872a-115">在組織 **設定檔的 Tab** 上，選擇 **自訂應用程式啟動器磚**。</span><span class="sxs-lookup"><span data-stu-id="6872a-115">On the **Organization profile** tab, choose **Custom app launcher tiles**.</span></span>
  
3. <span data-ttu-id="6872a-116">選取 **新增自訂磚**。</span><span class="sxs-lookup"><span data-stu-id="6872a-116">Select **Add a custom tile**.</span></span> 
  
4. <span data-ttu-id="6872a-117">輸入新 **磚** 的磚名稱。</span><span class="sxs-lookup"><span data-stu-id="6872a-117">Enter a **Tile name** for the new tile.</span></span> <span data-ttu-id="6872a-118">磚中就會出現該名稱。</span><span class="sxs-lookup"><span data-stu-id="6872a-118">The name will appear in the tile.</span></span> 
    
5. <span data-ttu-id="6872a-119">輸入 **磚的網站** URL。</span><span class="sxs-lookup"><span data-stu-id="6872a-119">Enter a **URL of website** for the tile.</span></span> <span data-ttu-id="6872a-120">這是當使用者選取 App 啟動器上的磚時，您希望使用者前往的位置。</span><span class="sxs-lookup"><span data-stu-id="6872a-120">This is the location where you want your users to go when they select the tile on the app launcher.</span></span> <span data-ttu-id="6872a-121">在 URL 使用 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="6872a-121">Use HTTPS in the URL.</span></span><br/><span data-ttu-id="6872a-122">提示：如果您要為 SharePoint 網站建立磚，請流覽至該網站、複製 URL，然後貼到這裡。</span><span class="sxs-lookup"><span data-stu-id="6872a-122">TIP: If you're creating a tile for a SharePoint site, navigate to that site, copy the URL, and paste it here.</span></span> <span data-ttu-id="6872a-123">預設小組網站的 URL 看起來像這樣： `https://<company_name>.sharepoint.com`</span><span class="sxs-lookup"><span data-stu-id="6872a-123">The URL of your default team site looks like this: `https://<company_name>.sharepoint.com`</span></span> 
  
6. <span data-ttu-id="6872a-124">輸入 **磚影像** 的 URL。</span><span class="sxs-lookup"><span data-stu-id="6872a-124">Enter an **URL of the image** for the tile.</span></span> <span data-ttu-id="6872a-125">隨後影像就會出現在 [我的 App] 頁面和 App 啟動器上。</span><span class="sxs-lookup"><span data-stu-id="6872a-125">The image appears on the My apps page and app launcher.</span></span><br/><span data-ttu-id="6872a-126">提示：影像大小應為 60x60 圖元，且可供貴組織中所有人使用，而不需要驗證。</span><span class="sxs-lookup"><span data-stu-id="6872a-126">TIP: The image should be 60x60 pixels and be available to everyone in your organization without requiring authentication.</span></span>

7. <span data-ttu-id="6872a-127">輸入 **磚** 的描述。</span><span class="sxs-lookup"><span data-stu-id="6872a-127">Enter a **Description** for the tile.</span></span> <span data-ttu-id="6872a-128">當您選取我的應用程式頁面上的磚，然後選取應用程式詳細資料時，會看到 **這一點**。</span><span class="sxs-lookup"><span data-stu-id="6872a-128">You see this when you select the tile on the My apps page and select **App details**.</span></span> 
  
8. <span data-ttu-id="6872a-129">選取 **儲存變更** 以建立自訂磚。</span><span class="sxs-lookup"><span data-stu-id="6872a-129">Select **Save changes** to create the custom tile.</span></span> 
    
<span data-ttu-id="6872a-130">您的自訂磚現在會顯示在 App 啟動器中的您和使用者。</span><span class="sxs-lookup"><span data-stu-id="6872a-130">Your custom tile now appears in the app launcher on the **All** tab for you and your users.</span></span> 
  
## <a name="promote-the-tile-to-app-launcher"></a><span data-ttu-id="6872a-131">將磚升上應用程式啟動器</span><span class="sxs-lookup"><span data-stu-id="6872a-131">Promote the tile to App Launcher</span></span>

1. <span data-ttu-id="6872a-132">選取應用程式啟動器圖示，然後選取所有 **應用程式**。</span><span class="sxs-lookup"><span data-stu-id="6872a-132">Select the app launcher icon and select the **All apps**.</span></span> 
    
2. <span data-ttu-id="6872a-133">找出應用程式的新磚，選取省略號，然後選擇釘 **選到啟動器**。</span><span class="sxs-lookup"><span data-stu-id="6872a-133">Locate the new tile for your app, select the ellipsis, and choose **Pin to launcher**.</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="6872a-134">如果您在之前的步驟看不到已建立的 [自訂磚]，請確認 Exchange Online 信箱已指派給您，且至少登入您的信箱一次。</span><span class="sxs-lookup"><span data-stu-id="6872a-134">If you don't see the custom tile created in the previous steps, make sure you have an Exchange Online mailbox assigned to you and you've signed into your mailbox at least once.</span></span> <span data-ttu-id="6872a-135">這些步驟是 Microsoft 365 中自訂磚的必填步驟。</span><span class="sxs-lookup"><span data-stu-id="6872a-135">These steps are required for custom tiles in Microsoft 365.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="6872a-136">您和您的使用者都必須執行這些步驟，才能將自訂磚從 [我的 App] 頁面升階到 App 啟動器。</span><span class="sxs-lookup"><span data-stu-id="6872a-136">Both you and your users need to perform these steps to promote custom tiles from the My apps page to the app launcher.</span></span> 
  
## <a name="edit-or-delete-a-custom-tile"></a><span data-ttu-id="6872a-137">Edit or delete a custom tile</span><span class="sxs-lookup"><span data-stu-id="6872a-137">Edit or delete a custom tile</span></span>

1. <span data-ttu-id="6872a-138">在系統管理中心中，前往設定  >  **組織設定**  >  **組織設定檔的 Tab。** </a></span><span class="sxs-lookup"><span data-stu-id="6872a-138">In the admin center, go to the **Settings** > **Org Settings** > **Organization profile**</a> tab.</span></span>
    
2. <span data-ttu-id="6872a-139">在組織 **設定檔頁面面上**，選取貴組織自訂 **磚** 旁 **的編輯。**</span><span class="sxs-lookup"><span data-stu-id="6872a-139">On the **Organization profile** page, next to   **Add custom tiles for your organization**, select **Edit**.</span></span>

3. <span data-ttu-id="6872a-140">更新自訂 **磚** 的磚名稱 **、URL、** 描述或影像 **URL** [ (請參閱在](#add-a-custom-tile-to-the-app-launcher)應用程式啟動器中新增自訂磚) 。 </span><span class="sxs-lookup"><span data-stu-id="6872a-140">Update the **Tile name**, **URL**, **Description**, or **Image URL** for the custom tile (see [Add a custom tile to the app launcher](#add-a-custom-tile-to-the-app-launcher)).</span></span>
    
4. <span data-ttu-id="6872a-141">選取 **更新** \> **關閉**。</span><span class="sxs-lookup"><span data-stu-id="6872a-141">Select **Update** \> **Close**.</span></span> 
    
<span data-ttu-id="6872a-142">若要刪除自訂磚，請從自訂磚視窗中選取該磚，然後選取移除 **磚**  >  **Delete。**</span><span class="sxs-lookup"><span data-stu-id="6872a-142">To delete a custom tile, from the **Custom tiles** window, select the tile, select **Remove tile** > **Delete**.</span></span> 
  
## <a name="whats-next"></a><span data-ttu-id="6872a-143">下一步是什麼？</span><span class="sxs-lookup"><span data-stu-id="6872a-143">What's next?</span></span>

<span data-ttu-id="6872a-144">除了在應用程式啟動器中新增磚，您還可以在流覽工具列中新增應用程式啟動器磚， ([進](https://support.microsoft.com/office/eb34a21b-52fa-4fbf-a8d5-146132242985) 一) 。</span><span class="sxs-lookup"><span data-stu-id="6872a-144">In addition to adding tiles to the app launcher, you can add app launcher tiles to the navigation bar ([learn more](https://support.microsoft.com/office/eb34a21b-52fa-4fbf-a8d5-146132242985)).</span></span> <span data-ttu-id="6872a-145">若要配合貴組織的品牌來自訂 Microsoft 365 的外觀與感覺，請參閱自訂 [Microsoft 365 主題](../setup/customize-your-organization-theme.md)。</span><span class="sxs-lookup"><span data-stu-id="6872a-145">To customize the look and feel of Microsoft 365 to match your organization's brand, see [Customize the Microsoft 365 theme](../setup/customize-your-organization-theme.md).</span></span>
  
