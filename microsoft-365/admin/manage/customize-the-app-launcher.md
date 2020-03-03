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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 1136115a-75af-4497-b693-640c4ce70bc6
description: '建立您的電子郵件、 文件、 應用程式、 SharePoint 網站、 外部網站及其他資源的快速連結應用程式啟動器中新增自訂磚。 '
ms.openlocfilehash: 65c8da7aa0cdb68f4bf32a52b21140413a38a69a
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/02/2020
ms.locfileid: "42361978"
---
# <a name="add-custom-tiles-to-the-app-launcher"></a><span data-ttu-id="e60b5-103">新增自訂磚至 App 啟動器</span><span class="sxs-lookup"><span data-stu-id="e60b5-103">Add custom tiles to the app launcher</span></span>

<span data-ttu-id="e60b5-p101">在 Office 365 中使用 Office 365 App 啟動器，可讓您輕鬆快速地存取電子郵件、行事曆、文件和 App ([深入了解](https://support.office.com/article/79f12104-6fed-442f-96a0-eb089a3f476a.aspx))。這些是 Office 365 中提供給您的 App，以及您從 [SharePoint 市集](https://support.office.com/article/dd98e50e-d3db-4ecb-9bb7-82b189822d43.aspx)或 [Azure AD](https://msdn.microsoft.com/office/office365/howto/connect-your-app-to-o365-app-launcher) 新增的自訂 App。</span><span class="sxs-lookup"><span data-stu-id="e60b5-p101">In Office 365, you can quickly and easily get to your email, calendars, documents, and apps using the Office 365 app launcher ([learn more](https://support.office.com/article/79f12104-6fed-442f-96a0-eb089a3f476a.aspx)). These are apps you get with Office 365 as well as custom apps that you add from the [SharePoint Store](https://support.office.com/article/dd98e50e-d3db-4ecb-9bb7-82b189822d43.aspx) or [Azure AD](https://msdn.microsoft.com/office/office365/howto/connect-your-app-to-o365-app-launcher).</span></span>
  
<span data-ttu-id="e60b5-106">您還可以在 App 啟動器上，加入自己的自訂磚，讓它們指向 SharePoint 網站、外部網站、舊版 App 等。</span><span class="sxs-lookup"><span data-stu-id="e60b5-106">You can add your own custom tiles to the app launcher that point to SharePoint sites, external sites, legacy apps, and more.</span></span> <span data-ttu-id="e60b5-107">自訂磚會出現在應用程式啟動器的**所有**應用程式] 下，但您可以釘選到**首頁**應用程式，並指示使用者執行同樣的動作。</span><span class="sxs-lookup"><span data-stu-id="e60b5-107">The custom tile appears under the app launcher's **All** apps, but you can pin it to the **Home** apps and instruct your users to do the same.</span></span> <span data-ttu-id="e60b5-108">這麼一來，您就可以輕鬆尋找相關的網站、App 和資源來完成您的工作。</span><span class="sxs-lookup"><span data-stu-id="e60b5-108">This makes it easy to find the relevant sites, apps, and resources to do your job.</span></span> <span data-ttu-id="e60b5-109">在下面這個範例中，名為「Contoso 入口網站」的磚，就是用來存取組織 SharePoint 內部網路網站的自訂磚。</span><span class="sxs-lookup"><span data-stu-id="e60b5-109">In the below example, a custom tile called "Contoso Portal" is used to access an organization's SharePoint intranet site.</span></span> 
  
![Office 365 應用程式啟動器](../../media/7acc06cc-ac7a-4c6e-8ea7-81570a5bdbab.png)
  
## <a name="add-a-custom-tile-to-the-app-launcher"></a><span data-ttu-id="e60b5-111">在 App 啟動器上新增自訂磚</span><span class="sxs-lookup"><span data-stu-id="e60b5-111">Add a custom tile to the app launcher</span></span>

1. <span data-ttu-id="e60b5-112">在系統管理中心，移至 [**設定** > **設定**，然後選擇 **[組織設定檔**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="e60b5-112">In the admin center, go to the **Settings** > **Settings** and choose **Organization profile** tab.</span></span>
    
2. <span data-ttu-id="e60b5-113">在 **[組織設定檔**] 索引標籤上，選擇 [**自訂應用程式啟動器磚**。</span><span class="sxs-lookup"><span data-stu-id="e60b5-113">On the **Organization profile** tab, choose **Custom app launcher tiles**.</span></span>
  
3. <span data-ttu-id="e60b5-114">選取 [**新增自訂磚**。</span><span class="sxs-lookup"><span data-stu-id="e60b5-114">Select **Add a custom tile**.</span></span> 
  
4. <span data-ttu-id="e60b5-115">輸入**磚名稱**的新磚。</span><span class="sxs-lookup"><span data-stu-id="e60b5-115">Enter a **Tile name** for the new tile.</span></span> <span data-ttu-id="e60b5-116">磚中就會出現該名稱。</span><span class="sxs-lookup"><span data-stu-id="e60b5-116">The name will appear in the tile.</span></span> 
    
5. <span data-ttu-id="e60b5-117">輸入磚**的網站 URL** 。</span><span class="sxs-lookup"><span data-stu-id="e60b5-117">Enter a **URL of website** for the tile.</span></span> <span data-ttu-id="e60b5-118">這是您希望使用者前往選取 app 啟動器上的磚時的位置。</span><span class="sxs-lookup"><span data-stu-id="e60b5-118">This is the location where you want your users to go when they select the tile on the app launcher.</span></span> <span data-ttu-id="e60b5-119">在 URL 中使用 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="e60b5-119">Use HTTPS in the URL.</span></span><br/><span data-ttu-id="e60b5-120">提示： 如果您正在建立的 SharePoint 網站] 磚，瀏覽至該網站、 複製 URL，並將它貼到這裡。</span><span class="sxs-lookup"><span data-stu-id="e60b5-120">TIP: If you're creating a tile for a SharePoint site, navigate to that site, copy the URL, and paste it here.</span></span> <span data-ttu-id="e60b5-121">預設小組網站的 URL 看起來像這樣：`https://<company_name>.sharepoint.com`</span><span class="sxs-lookup"><span data-stu-id="e60b5-121">The URL of your default team site looks like this: `https://<company_name>.sharepoint.com`</span></span> 
  
6. <span data-ttu-id="e60b5-122">輸入磚**的影像 URL** 。</span><span class="sxs-lookup"><span data-stu-id="e60b5-122">Enter an **URL of the image** for the tile.</span></span> <span data-ttu-id="e60b5-123">隨後影像就會出現在 [我的 App] 頁面和 App 啟動器上。</span><span class="sxs-lookup"><span data-stu-id="e60b5-123">The image appears on the My apps page and app launcher.</span></span><br/><span data-ttu-id="e60b5-124">提示： 圖像應為 60x60 像素，並可供您組織中所有人不需要驗證。</span><span class="sxs-lookup"><span data-stu-id="e60b5-124">TIP: The image should be 60x60 pixels and be available to everyone in your organization without requiring authentication.</span></span>

7. <span data-ttu-id="e60b5-125">輸入磚**描述**。</span><span class="sxs-lookup"><span data-stu-id="e60b5-125">Enter a **Description** for the tile.</span></span> <span data-ttu-id="e60b5-126">您會看到這當您選取磚上的 [我的應用程式] 頁面上，然後選取 [**應用程式詳細資料**。</span><span class="sxs-lookup"><span data-stu-id="e60b5-126">You see this when you select the tile on the My apps page and select **App details**.</span></span> 
  
8. <span data-ttu-id="e60b5-127">選取 [**儲存變更**] 以建立自訂磚。</span><span class="sxs-lookup"><span data-stu-id="e60b5-127">Select **Save changes** to create the custom tile.</span></span> 
    
<span data-ttu-id="e60b5-128">您的自訂磚現在會顯示在 [**所有**] 索引標籤上的 app 啟動器中對您和您的使用者。</span><span class="sxs-lookup"><span data-stu-id="e60b5-128">Your custom tile now appears in the app launcher on the **All** tab for you and your users.</span></span> 
  
## <a name="promote-the-tile-to-app-launcher"></a><span data-ttu-id="e60b5-129">升階到 App 啟動器磚</span><span class="sxs-lookup"><span data-stu-id="e60b5-129">Promote the tile to App Launcher</span></span>

1. <span data-ttu-id="e60b5-130">選取應用程式啟動器圖示，然後選取 [**所有應用程式]**。</span><span class="sxs-lookup"><span data-stu-id="e60b5-130">Select the app launcher icon and select the **All apps**.</span></span> 
    
2. <span data-ttu-id="e60b5-131">找出您的應用程式的新磚，選取省略符號，然後選擇 [**釘選到啟動器**。</span><span class="sxs-lookup"><span data-stu-id="e60b5-131">Locate the new tile for your app, select the ellipsis, and choose **Pin to launcher**.</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="e60b5-p108">如果您在之前的步驟看不到已建立的 [自訂磚]，請確認 Exchange Online 信箱已指派給您，且至少登入您的信箱一次。這些是在 Office 365 中自訂磚時的必要步驟。</span><span class="sxs-lookup"><span data-stu-id="e60b5-p108">If you don't see the custom tile created in the previous steps, make sure you have an Exchange Online mailbox assigned to you and you've signed into your mailbox at least once. These steps are required for custom tiles in Office 365.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="e60b5-134">您和您的使用者都必須執行這些步驟，才能將自訂磚從 [我的 App] 頁面升階到 App 啟動器。</span><span class="sxs-lookup"><span data-stu-id="e60b5-134">Both you and your users need to perform these steps to promote custom tiles from the My apps page to the app launcher.</span></span> 
  
## <a name="edit-or-delete-a-custom-tile"></a><span data-ttu-id="e60b5-135">Edit or delete a custom tile</span><span class="sxs-lookup"><span data-stu-id="e60b5-135">Edit or delete a custom tile</span></span>

1. <span data-ttu-id="e60b5-136">在系統管理中心，移至 [**設定** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2067339" target="_blank">組織設定檔</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="e60b5-136">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2067339" target="_blank">Organization profile</a> page.</span></span>
    
2. <span data-ttu-id="e60b5-137">在 **[組織設定檔**頁面上，**為您的組織新增自訂磚**旁, 選取 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="e60b5-137">On the **Organization profile** page, next to   **Add custom tiles for your organization**, select **Edit**.</span></span>

3. <span data-ttu-id="e60b5-138">更新自訂磚**並排顯示名稱**、 **URL**、**描述**、 或**影像 URL** （請參閱[新增自訂磚至 app 啟動器](#add-a-custom-tile-to-the-app-launcher)）。</span><span class="sxs-lookup"><span data-stu-id="e60b5-138">Update the **Tile name**, **URL**, **Description**, or **Image URL** for the custom tile (see [Add a custom tile to the app launcher](#add-a-custom-tile-to-the-app-launcher)).</span></span>
    
4. <span data-ttu-id="e60b5-139">選取 [**更新** \> **關閉**。</span><span class="sxs-lookup"><span data-stu-id="e60b5-139">Select **Update** \> **Close**.</span></span> 
    
<span data-ttu-id="e60b5-140">若要刪除自訂磚，從 [**自訂磚**] 視窗中，選取磚，請選取 [**移除磚** > **刪除**。</span><span class="sxs-lookup"><span data-stu-id="e60b5-140">To delete a custom tile, from the **Custom tiles** window, select the tile, select **Remove tile** > **Delete**.</span></span> 
  
## <a name="whats-next"></a><span data-ttu-id="e60b5-141">下一步是什麼？</span><span class="sxs-lookup"><span data-stu-id="e60b5-141">What's next?</span></span>

<span data-ttu-id="e60b5-p109">除了在 App 啟動器中新增磚之外，您還可以在 Office 365 導覽列中，新增 App 啟動器磚 ([深入了解](https://support.office.com/article/d536512c-b0f7-49fd-b8db-a8a967e23f23.aspx))。若要配合貴組織的品牌，自訂 Office 365 的外觀與風格，請參閱[自訂 Office 365 佈景主題](../setup/customize-your-organization-theme.md)。</span><span class="sxs-lookup"><span data-stu-id="e60b5-p109">In addition to adding tiles to the app launcher, you can add app launcher tiles to the Office 365 navigation bar ([learn more](https://support.office.com/article/d536512c-b0f7-49fd-b8db-a8a967e23f23.aspx)). To customize the look and feel of Office 365 to match your organization's brand, see [Customize the Office 365 theme](../setup/customize-your-organization-theme.md).</span></span>
  

