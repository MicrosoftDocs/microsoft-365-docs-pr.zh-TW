---
title: 管理 Microsoft 受管理電腦中的應用程式
description: 如何更新部署至 Microsoft 受管理的電腦裝置的線條營運應用程式的相關資訊
keywords: Microsoft 受管理的電腦，Microsoft 365 服務，文件
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.date: 01/18/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 7aca4713aae189e39133e08a1fbcad6fd75e6a70
ms.sourcegitcommit: 8fda7852b2a5baa92b8a365865b014ea6d100bbc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/03/2019
ms.locfileid: "39813853"
---
# <a name="manage-line-of-business-apps-in-microsoft-managed-desktop"></a><span data-ttu-id="dea3d-104">管理 Microsoft 受管理電腦中的行營運應用程式</span><span class="sxs-lookup"><span data-stu-id="dea3d-104">Manage line-of-business apps in Microsoft Managed Desktop</span></span>

<!--Application management -->

<span data-ttu-id="dea3d-105">有幾種方式來管理應用程式在您上架到 Microsoft 受管理的電腦，並部署至您的 Microsoft 受管理的電腦裝置的應用程式更新。</span><span class="sxs-lookup"><span data-stu-id="dea3d-105">There are a couple of ways to manage app updates for apps that you've onboarded to Microsoft Managed Desktop and deployed to your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="dea3d-106">您可以在 Microsoft 受管理電腦入口網站或 Intune 進行應用程式更新。</span><span class="sxs-lookup"><span data-stu-id="dea3d-106">You can make app updates in Microsoft Managed Desktop portal, or Intune.</span></span> 

<span id="update-app-mmd" />

## <a name="update-line-of-business-apps-in-microsoft-managed-desktop"></a><span data-ttu-id="dea3d-107">更新 Microsoft 受管理電腦中的行營運應用程式</span><span class="sxs-lookup"><span data-stu-id="dea3d-107">Update line-of-business apps in Microsoft Managed Desktop</span></span>

<span data-ttu-id="dea3d-108">**若要更新在 Microsoft 受管理電腦入口網站-營運應用程式**</span><span class="sxs-lookup"><span data-stu-id="dea3d-108">**To update your line-of-business apps in Microsoft Managed Desktop portal**</span></span>
1. <span data-ttu-id="dea3d-109">登入[Microsoft 受管理的桌上型電腦系統管理入口網站](https://aka.ms/mmdportal)。</span><span class="sxs-lookup"><span data-stu-id="dea3d-109">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="dea3d-110">在 [**詳細目錄**] 下選取 [**應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="dea3d-110">Under **Inventory**, select **Apps**.</span></span>  
3. <span data-ttu-id="dea3d-111">選取您要更新的應用程式，然後選取 [**編輯**。</span><span class="sxs-lookup"><span data-stu-id="dea3d-111">Select the app you want to updates, and then select **Edit**.</span></span>
4. <span data-ttu-id="dea3d-112">在 [**管理**] 下選取 [**屬性**]。</span><span class="sxs-lookup"><span data-stu-id="dea3d-112">Under **Manage**, select **Properties**.</span></span> 
5. <span data-ttu-id="dea3d-113">按一下 [**應用程式套件檔案**，然後瀏覽至新的應用程式套件檔案上傳。</span><span class="sxs-lookup"><span data-stu-id="dea3d-113">Click **App package file**, and then browse to upload a new app package file.</span></span>
6. <span data-ttu-id="dea3d-114">選取 [**應用程式套件檔案**。</span><span class="sxs-lookup"><span data-stu-id="dea3d-114">Select **App package file**.</span></span>
7. <span data-ttu-id="dea3d-115">選取 [資料夾] 圖示，然後瀏覽至您已更新的應用程式檔案的位置。</span><span class="sxs-lookup"><span data-stu-id="dea3d-115">Select the folder icon and browse to the location of your updated app file.</span></span> <span data-ttu-id="dea3d-116">選取 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="dea3d-116">Select **Open**.</span></span> <span data-ttu-id="dea3d-117">應用程式資訊會更新套件的資訊。</span><span class="sxs-lookup"><span data-stu-id="dea3d-117">The app information is updated with the package information.</span></span>
8. <span data-ttu-id="dea3d-118">確認**應用程式版本**會反映更新應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="dea3d-118">Verify that **App version** reflects the updated app package.</span></span> 

<span data-ttu-id="dea3d-119">更新應用程式會部署至使用者的裝置。</span><span class="sxs-lookup"><span data-stu-id="dea3d-119">The updated app will be deployed to your user's devices.</span></span>

<span id="update-app-intune" />

## <a name="update-line-of-business-apps-in-intune"></a><span data-ttu-id="dea3d-120">更新在 Intune 中的行營運應用程式</span><span class="sxs-lookup"><span data-stu-id="dea3d-120">Update line-of-business apps in Intune</span></span>

<span data-ttu-id="dea3d-121">**若要更新您在 Intune 中的行營運應用程式**</span><span class="sxs-lookup"><span data-stu-id="dea3d-121">**To update your line-of-business apps in Intune**</span></span>
1. <span data-ttu-id="dea3d-122">登入[Azure 入口網站](https://portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="dea3d-122">Sign in to [Azure portal](https://portal.azure.com).</span></span>
2. <span data-ttu-id="dea3d-123">選取 [**所有服務** > **Intune**。</span><span class="sxs-lookup"><span data-stu-id="dea3d-123">Select **All Services** > **Intune**.</span></span> <span data-ttu-id="dea3d-124">Intune 會在**監視 + 管理**] 區段中。</span><span class="sxs-lookup"><span data-stu-id="dea3d-124">Intune is in the **Monitoring + Management** section.</span></span>
3. <span data-ttu-id="dea3d-125">選取 [**用戶端應用程式 > 應用程式**。</span><span class="sxs-lookup"><span data-stu-id="dea3d-125">Select **Client Apps > Apps**.</span></span>
4. <span data-ttu-id="dea3d-126">尋找並選取您的應用程式的應用程式] 清單中。</span><span class="sxs-lookup"><span data-stu-id="dea3d-126">Find and select your app in the list of apps.</span></span>
5. <span data-ttu-id="dea3d-127">在 [**概觀**] 刀鋒視窗中，選取**屬性**。</span><span class="sxs-lookup"><span data-stu-id="dea3d-127">In the **Overview** blade, select **Properties**.</span></span>
6. <span data-ttu-id="dea3d-128">選取 [**應用程式套件檔案**。</span><span class="sxs-lookup"><span data-stu-id="dea3d-128">Select **App package file**.</span></span>
7. <span data-ttu-id="dea3d-129">選取 [資料夾] 圖示，然後瀏覽至您已更新的應用程式檔案的位置。</span><span class="sxs-lookup"><span data-stu-id="dea3d-129">Select the folder icon and browse to the location of your updated app file.</span></span> <span data-ttu-id="dea3d-130">選取 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="dea3d-130">Select **Open**.</span></span> <span data-ttu-id="dea3d-131">應用程式資訊會更新套件的資訊。</span><span class="sxs-lookup"><span data-stu-id="dea3d-131">The app information is updated with the package information.</span></span>
8. <span data-ttu-id="dea3d-132">確認**應用程式版本**會反映更新應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="dea3d-132">Verify that **App version** reflects the updated app package.</span></span>

<span id="roll-back-app-mmd" />

## <a name="roll-back-an-app-to-a-previous-version"></a><span data-ttu-id="dea3d-133">回復到舊版應用程式</span><span class="sxs-lookup"><span data-stu-id="dea3d-133">Roll back an app to a previous version</span></span>

<span data-ttu-id="dea3d-134">如果沒有找到部署應用程式的新版本時的錯誤，您可以回復至先前的版本。</span><span class="sxs-lookup"><span data-stu-id="dea3d-134">If there's an error found when a new version of an app is deployed, you can roll back to a previous version.</span></span> <span data-ttu-id="dea3d-135">此處所述的程序是應用程式已列出類型為**Windows MSI-營運應用程式**或**Windows 應用程式 (Win 32)-預覽**</span><span class="sxs-lookup"><span data-stu-id="dea3d-135">The process outlined here is for apps where type is listed as **Windows MSI line-of-business app** or **Windows app (Win 32) - preview**</span></span>

<span data-ttu-id="dea3d-136">**若要回復為舊版-營運應用程式**</span><span class="sxs-lookup"><span data-stu-id="dea3d-136">**To roll back a line-of-business app to a previous version**</span></span>

1. <span data-ttu-id="dea3d-137">登入[Microsoft 受管理的桌上型電腦系統管理入口網站](https://aka.ms/mmdportal)。</span><span class="sxs-lookup"><span data-stu-id="dea3d-137">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="dea3d-138">在 [**詳細目錄**] 下選取 [**應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="dea3d-138">Under **Inventory**, select **Apps**.</span></span>  
3. <span data-ttu-id="dea3d-139">選取您要將回復，該應用程式，然後選取 [**編輯**。</span><span class="sxs-lookup"><span data-stu-id="dea3d-139">Select the app you need to roll back, and then select **Edit**.</span></span>
4. <span data-ttu-id="dea3d-140">在 [**管理**] 下選取 [**屬性**]。</span><span class="sxs-lookup"><span data-stu-id="dea3d-140">Under **Manage**, select **Properties**.</span></span> 
    - <span data-ttu-id="dea3d-141">**Windows MSI-營運應用程式**的應用程式，選取 [**應用程式資訊**]，然後在 [**略過 app 版本**] 中，選取 [**是]**。</span><span class="sxs-lookup"><span data-stu-id="dea3d-141">For **Windows MSI line-of-business app** apps, select **App information**, and then under **Ignore app version**, select **Yes**.</span></span>
    - <span data-ttu-id="dea3d-142">**Windows 應用程式 (Win 32)-預覽**應用程式]，選取**應用程式資訊**，選取 [**偵測規則**]，然後選取 [**新增]**。</span><span class="sxs-lookup"><span data-stu-id="dea3d-142">For **Windows app (Win 32) - preview** apps, select **App information**, select **Detection rules**, and then select **Add**.</span></span> 
    <span data-ttu-id="dea3d-143">如果沒有 MSI 規則，確認**MSI 產品版本檢查**已設定為 [**否]**。</span><span class="sxs-lookup"><span data-stu-id="dea3d-143">If there is an MSI rule, verify that **MSI product version check** is set to **No**.</span></span>
5. <span data-ttu-id="dea3d-144">[將舊版的應用程式來源檔案上傳](../get-started/deploy-apps.md)至 Microsoft 受管理的桌上型電腦系統管理入口網站。</span><span class="sxs-lookup"><span data-stu-id="dea3d-144">[Upload a previous version of the app source file](../get-started/deploy-apps.md) to Microsoft Managed Desktop Admin portal.</span></span>  

