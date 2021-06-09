---
title: 在 Microsoft 受管理的電腦中管理應用程式
description: 如何更新部署至 Microsoft 受管理的電腦裝置的企業營運應用程式的相關資訊
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.date: 01/18/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 1a6b91ab5b4523f4b980dab0c25af41a9d614189
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600680"
---
# <a name="manage-line-of-business-apps-in-microsoft-managed-desktop"></a><span data-ttu-id="198cd-104">Microsoft 受管理的電腦中管理企業營運應用程式</span><span class="sxs-lookup"><span data-stu-id="198cd-104">Manage line-of-business apps in Microsoft Managed Desktop</span></span>

<!--Application management -->

<span data-ttu-id="198cd-105">有幾種方式可管理您已架 Microsoft 受管理的電腦並部署至 Microsoft 受管理的電腦裝置之應用程式的應用程式更新。</span><span class="sxs-lookup"><span data-stu-id="198cd-105">There are a couple of ways to manage app updates for apps that you've onboarded to Microsoft Managed Desktop and deployed to your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="198cd-106">您可以在 Microsoft 受管理的電腦入口網站或 Intune 中進行應用程式更新。</span><span class="sxs-lookup"><span data-stu-id="198cd-106">You can make app updates in Microsoft Managed Desktop portal, or Intune.</span></span> 

<span id="update-app-mmd" />

## <a name="update-line-of-business-apps-in-microsoft-managed-desktop"></a><span data-ttu-id="198cd-107">更新 Microsoft 受管理的電腦中的企業營運應用程式</span><span class="sxs-lookup"><span data-stu-id="198cd-107">Update line-of-business apps in Microsoft Managed Desktop</span></span>

<span data-ttu-id="198cd-108">**若要更新 Microsoft 受管理的電腦入口網站中的企業營運應用程式**</span><span class="sxs-lookup"><span data-stu-id="198cd-108">**To update your line-of-business apps in Microsoft Managed Desktop portal**</span></span>
1. <span data-ttu-id="198cd-109">登入[Microsoft 受管理的電腦管理入口網站](https://aka.ms/mmdportal)。</span><span class="sxs-lookup"><span data-stu-id="198cd-109">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="198cd-110">在 [ **庫存**] 下，選取 [ **應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="198cd-110">Under **Inventory**, select **Apps**.</span></span>  
3. <span data-ttu-id="198cd-111">選取您要更新的應用程式，然後選取 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="198cd-111">Select the app you want to updates, and then select **Edit**.</span></span>
4. <span data-ttu-id="198cd-112">在 [ **管理**] 下，選取 [ **屬性**]。</span><span class="sxs-lookup"><span data-stu-id="198cd-112">Under **Manage**, select **Properties**.</span></span> 
5. <span data-ttu-id="198cd-113">按一下 [ **應用程式套件** 檔案]，然後流覽以上傳新的應用程式套件檔案。</span><span class="sxs-lookup"><span data-stu-id="198cd-113">Click **App package file**, and then browse to upload a new app package file.</span></span>
6. <span data-ttu-id="198cd-114">選取 **應用程式套件** 檔案。</span><span class="sxs-lookup"><span data-stu-id="198cd-114">Select **App package file**.</span></span>
7. <span data-ttu-id="198cd-115">選取 [資料夾] 圖示，並流覽至更新應用程式檔案的位置。</span><span class="sxs-lookup"><span data-stu-id="198cd-115">Select the folder icon and browse to the location of your updated app file.</span></span> <span data-ttu-id="198cd-116">選取 [開啟]。</span><span class="sxs-lookup"><span data-stu-id="198cd-116">Select **Open**.</span></span> <span data-ttu-id="198cd-117">使用套件資訊更新應用程式資訊。</span><span class="sxs-lookup"><span data-stu-id="198cd-117">The app information is updated with the package information.</span></span>
8. <span data-ttu-id="198cd-118">請確認 **應用程式版本** 反映的是更新的應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="198cd-118">Verify that **App version** reflects the updated app package.</span></span> 

<span data-ttu-id="198cd-119">更新的應用程式會部署至使用者的裝置。</span><span class="sxs-lookup"><span data-stu-id="198cd-119">The updated app will be deployed to your user's devices.</span></span>

<span id="update-app-intune" />

## <a name="update-line-of-business-apps-in-intune"></a><span data-ttu-id="198cd-120">更新 Intune 中的企業營運應用程式</span><span class="sxs-lookup"><span data-stu-id="198cd-120">Update line-of-business apps in Intune</span></span>

<span data-ttu-id="198cd-121">**若要更新 Intune 中的企業營運應用程式**</span><span class="sxs-lookup"><span data-stu-id="198cd-121">**To update your line-of-business apps in Intune**</span></span>
1. <span data-ttu-id="198cd-122">登入 [Azure 入口網站](https://portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="198cd-122">Sign in to [Azure portal](https://portal.azure.com).</span></span>
2. <span data-ttu-id="198cd-123">選取 [**所有服務**]  >  **Intune**。</span><span class="sxs-lookup"><span data-stu-id="198cd-123">Select **All Services** > **Intune**.</span></span> <span data-ttu-id="198cd-124">Intune 位於 **監控 + 管理** 區段中。</span><span class="sxs-lookup"><span data-stu-id="198cd-124">Intune is in the **Monitoring + Management** section.</span></span>
3. <span data-ttu-id="198cd-125">選取 [ **用戶端應用程式] > 應用程式**。</span><span class="sxs-lookup"><span data-stu-id="198cd-125">Select **Client Apps > Apps**.</span></span>
4. <span data-ttu-id="198cd-126">在應用程式清單中尋找並選取您的應用程式。</span><span class="sxs-lookup"><span data-stu-id="198cd-126">Find and select your app in the list of apps.</span></span>
5. <span data-ttu-id="198cd-127">在 [ **一覽** ] 邊欄中，選取 [ **屬性**]。</span><span class="sxs-lookup"><span data-stu-id="198cd-127">In the **Overview** blade, select **Properties**.</span></span>
6. <span data-ttu-id="198cd-128">選取 **應用程式套件** 檔案。</span><span class="sxs-lookup"><span data-stu-id="198cd-128">Select **App package file**.</span></span>
7. <span data-ttu-id="198cd-129">選取 [資料夾] 圖示，並流覽至更新應用程式檔案的位置。</span><span class="sxs-lookup"><span data-stu-id="198cd-129">Select the folder icon and browse to the location of your updated app file.</span></span> <span data-ttu-id="198cd-130">選取 [開啟]。</span><span class="sxs-lookup"><span data-stu-id="198cd-130">Select **Open**.</span></span> <span data-ttu-id="198cd-131">使用套件資訊更新應用程式資訊。</span><span class="sxs-lookup"><span data-stu-id="198cd-131">The app information is updated with the package information.</span></span>
8. <span data-ttu-id="198cd-132">請確認 **應用程式版本** 反映的是更新的應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="198cd-132">Verify that **App version** reflects the updated app package.</span></span>

<span id="roll-back-app-mmd" />

## <a name="roll-back-an-app-to-a-previous-version"></a><span data-ttu-id="198cd-133">將應用程式還原為先前版本</span><span class="sxs-lookup"><span data-stu-id="198cd-133">Roll back an app to a previous version</span></span>

<span data-ttu-id="198cd-134">如果部署新版本的應用程式時發現錯誤，您可以復原至先前的版本。</span><span class="sxs-lookup"><span data-stu-id="198cd-134">If there's an error found when a new version of an app is deployed, you can roll back to a previous version.</span></span> <span data-ttu-id="198cd-135">此處所述的程式是針對其類型列為 **Windows MSI 營運應用程式** 或 Windows 應用程式的應用程式， **(Win 32) 預覽**</span><span class="sxs-lookup"><span data-stu-id="198cd-135">The process outlined here is for apps where type is listed as **Windows MSI line-of-business app** or **Windows app (Win 32) - preview**</span></span>

<span data-ttu-id="198cd-136">**將企業營運應用程式還原為繼承應用程式**</span><span class="sxs-lookup"><span data-stu-id="198cd-136">**To roll back a line-of-business app to a previous version**</span></span>

1. <span data-ttu-id="198cd-137">登入[Microsoft 受管理的電腦管理入口網站](https://aka.ms/mmdportal)。</span><span class="sxs-lookup"><span data-stu-id="198cd-137">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="198cd-138">在 [ **庫存**] 下，選取 [ **應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="198cd-138">Under **Inventory**, select **Apps**.</span></span>  
3. <span data-ttu-id="198cd-139">選取您需要回復的應用程式，然後選取 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="198cd-139">Select the app you need to roll back, and then select **Edit**.</span></span>
4. <span data-ttu-id="198cd-140">在 [ **管理**] 下，選取 [ **屬性**]。</span><span class="sxs-lookup"><span data-stu-id="198cd-140">Under **Manage**, select **Properties**.</span></span> 
    - <span data-ttu-id="198cd-141">若為 **Windows MSI 的企業應用程式 app** ，請選取 [**應用程式資訊**]，然後在 [**忽略應用程式版本**] 底下，選取 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="198cd-141">For **Windows MSI line-of-business app** apps, select **App information**, and then under **Ignore app version**, select **Yes**.</span></span>
    - <span data-ttu-id="198cd-142">**Windows 應用程式 (Win 32) 預覽** 應用程式，選取 **[應用程式資訊**]，選取 [**偵測規則**]，然後選取 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="198cd-142">For **Windows app (Win 32) - preview** apps, select **App information**, select **Detection rules**, and then select **Add**.</span></span> 
    <span data-ttu-id="198cd-143">如果有 MSI 規則，請確認 **msi 產品版本檢查** 是否設為 [ **否**]。</span><span class="sxs-lookup"><span data-stu-id="198cd-143">If there is an MSI rule, verify that **MSI product version check** is set to **No**.</span></span>
5. <span data-ttu-id="198cd-144">[Upload 舊版本的應用程式原始檔案](../get-started/deploy-apps.md)Microsoft 受管理的電腦管理入口網站。</span><span class="sxs-lookup"><span data-stu-id="198cd-144">[Upload a previous version of the app source file](../get-started/deploy-apps.md) to Microsoft Managed Desktop Admin portal.</span></span>  

