---
title: 在 Microsoft 受管理的電腦中部署可設定的設定
description: 在 Microsoft 受管理的電腦中部署及追蹤可設定的設定變更。
keywords: Microsoft 受管理的桌面、Microsoft 365、服務、檔、部署、分段部署、可設定的設定
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 2/17/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: bfa769cab9f8d812fa2533232f66b0d4f8a4edb7
ms.sourcegitcommit: 427c6459614d58f6ef7c74354ae1816423e22323
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/28/2019
ms.locfileid: "35390510"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a><span data-ttu-id="11eeb-104">部署及追蹤可設定的設定-Microsoft 受管理的電腦</span><span class="sxs-lookup"><span data-stu-id="11eeb-104">Deploy and track configurable settings - Microsoft Managed Desktop</span></span>

<span data-ttu-id="11eeb-105">在您變更設定類別和階段部署之後, 部署狀態頁面可讓您開始將設定部署至群組。</span><span class="sxs-lookup"><span data-stu-id="11eeb-105">After you make changes to your setting categories and stage a deployment, the Deployment status page allows you to begin deploying your settings to groups.</span></span> <span data-ttu-id="11eeb-106">此頁面會顯示每個可設定設定的摘要。</span><span class="sxs-lookup"><span data-stu-id="11eeb-106">This page shows a summary of each configurable setting.</span></span> <span data-ttu-id="11eeb-107">開啟設定類別後, 您就可以將設定部署至群組, 並追蹤這些部署的進度。</span><span class="sxs-lookup"><span data-stu-id="11eeb-107">By opening a setting category you can deploy settings to groups and track the progress of these deployments.</span></span>

## <a name="deployment-statuses"></a><span data-ttu-id="11eeb-108">部署狀態</span><span class="sxs-lookup"><span data-stu-id="11eeb-108">Deployment statuses</span></span> 

<span data-ttu-id="11eeb-109">這些是您將會看到的每個部署的 statues。</span><span class="sxs-lookup"><span data-stu-id="11eeb-109">These are the statues you’ll see for each deployment.</span></span>

<span data-ttu-id="11eeb-110">狀態</span><span class="sxs-lookup"><span data-stu-id="11eeb-110">Status</span></span>  | <span data-ttu-id="11eeb-111">說明</span><span class="sxs-lookup"><span data-stu-id="11eeb-111">Explanation</span></span> 
--- | --- 
<span data-ttu-id="11eeb-112">部署</span><span class="sxs-lookup"><span data-stu-id="11eeb-112">Deploy</span></span> | <span data-ttu-id="11eeb-113">您的變更正等待部署至此群組。</span><span class="sxs-lookup"><span data-stu-id="11eeb-113">Your change is waiting to be deployed to this group.</span></span>
<span data-ttu-id="11eeb-114">進行中。</span><span class="sxs-lookup"><span data-stu-id="11eeb-114">In progress</span></span> | <span data-ttu-id="11eeb-115">此群組中的作用中裝置會套用變更。</span><span class="sxs-lookup"><span data-stu-id="11eeb-115">The change is being applied to active devices in this group.</span></span> 
<span data-ttu-id="11eeb-116">已完成</span><span class="sxs-lookup"><span data-stu-id="11eeb-116">Complete</span></span> | <span data-ttu-id="11eeb-117">此群組中所有使用中裝置的變更都已完成。</span><span class="sxs-lookup"><span data-stu-id="11eeb-117">The change completed on all active devices in this group.</span></span> 
<span data-ttu-id="11eeb-118">失敗</span><span class="sxs-lookup"><span data-stu-id="11eeb-118">Failed</span></span> | <span data-ttu-id="11eeb-119">在群組中的 10% 裝置上, 變更失敗, 因此部署已停止。</span><span class="sxs-lookup"><span data-stu-id="11eeb-119">The change failed on a 10 percent of active devices in the group, so the deployment was stopped.</span></span><br><br> <span data-ttu-id="11eeb-120">系統會自動使用 Microsoft 受管理的桌面作業開啟支援, 以疑難排解部署。</span><span class="sxs-lookup"><span data-stu-id="11eeb-120">A support request will be automatically opened with Microsoft Managed Desktop operations to troubleshoot the deployment.</span></span> 
<span data-ttu-id="11eeb-121">回</span><span class="sxs-lookup"><span data-stu-id="11eeb-121">Reverted</span></span> | <span data-ttu-id="11eeb-122">變更已還原至已成功部署至所有部署群組的最後變更。</span><span class="sxs-lookup"><span data-stu-id="11eeb-122">The change was reverted to the last change that was successfully deployed to all deployment groups.</span></span>

## <a name="deploy-changes"></a><span data-ttu-id="11eeb-123">部署變更</span><span class="sxs-lookup"><span data-stu-id="11eeb-123">Deploy changes</span></span>

<span data-ttu-id="11eeb-124">我們會在這些指示中顯示桌面背景圖片。</span><span class="sxs-lookup"><span data-stu-id="11eeb-124">We’ll show Desktop background picture in these instructions.</span></span> <span data-ttu-id="11eeb-125">分段部署後, 您就可以從 [部署狀態] 頁面部署變更。</span><span class="sxs-lookup"><span data-stu-id="11eeb-125">After you’ve staged a deployment, you deploy changes from the Deployment status page.</span></span> 

<span data-ttu-id="11eeb-126">**部署變更**</span><span class="sxs-lookup"><span data-stu-id="11eeb-126">**To deploy changes**</span></span>

1. <span data-ttu-id="11eeb-127">登入[Microsoft 受管理的桌面管理入口網站](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="11eeb-127">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="11eeb-128">在 [設定] 下, 選取 [**可\*\*\*\*設定**]。</span><span class="sxs-lookup"><span data-stu-id="11eeb-128">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="11eeb-129">在 [**部署狀態**工作區] 中, 選取您要部署的設定, 然後選取要部署的分段部署。</span><span class="sxs-lookup"><span data-stu-id="11eeb-129">In **Deployment status** workspace, select the setting you want to deploy, and then select the staged deployment to deploy.</span></span>
4. <span data-ttu-id="11eeb-130">選取 [**部署**], 將變更部署至其中一個部署群組。</span><span class="sxs-lookup"><span data-stu-id="11eeb-130">Select **Deploy** to deploy the change to one of the deployment groups.</span></span>

![可設定的設定部署狀態概述](images/deploy-cs-overview.png)

<span data-ttu-id="11eeb-132">Microsoft 受管理的桌面建議依此順序部署至部署群組: Test、First、Fast、後的範圍。</span><span class="sxs-lookup"><span data-stu-id="11eeb-132">Microsoft Managed Desktop recommends deploying to deployment groups in this order: Test, First, Fast, and then Broad.</span></span> 

<span data-ttu-id="11eeb-133">當每個群組中的變更完成時, 狀態會變更為 [已**完成**]。</span><span class="sxs-lookup"><span data-stu-id="11eeb-133">When changes complete in each group, the status changes to **Complete**.</span></span>

![可設定的設定部署完成](images/config-setting-complete.png)

## <a name="revert-deployment"></a><span data-ttu-id="11eeb-135">還原部署</span><span class="sxs-lookup"><span data-stu-id="11eeb-135">Revert deployment</span></span>

<span data-ttu-id="11eeb-136">在您部署變更之後, 您可以從**部署狀態**回復。</span><span class="sxs-lookup"><span data-stu-id="11eeb-136">After you’ve deployed a change, you can revert from **Deployment status**.</span></span> <span data-ttu-id="11eeb-137">當您回復正在**進行**或已**完成**的變更時, 目前的部署會停止。</span><span class="sxs-lookup"><span data-stu-id="11eeb-137">When you revert a change that is **In progress** or **Complete**, the current deployment stops.</span></span> <span data-ttu-id="11eeb-138">此設定會回復至已部署至所有群組的最後一個版本。</span><span class="sxs-lookup"><span data-stu-id="11eeb-138">The setting will revert to the last version that was deployed to all groups.</span></span> 

<span data-ttu-id="11eeb-139">我們將使用桌面背景圖片做為範例, 示範回復變更的步驟。</span><span class="sxs-lookup"><span data-stu-id="11eeb-139">We’ll show the steps to revert a change using the Desktop background picture as an example.</span></span> 

<span data-ttu-id="11eeb-140">**回復變更**</span><span class="sxs-lookup"><span data-stu-id="11eeb-140">**To revert a change**</span></span>
1. <span data-ttu-id="11eeb-141">登入[Microsoft 受管理的桌面管理入口網站](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="11eeb-141">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="11eeb-142">在 [設定] 下, 選取 [**可\*\*\*\*設定**]。</span><span class="sxs-lookup"><span data-stu-id="11eeb-142">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="11eeb-143">在 [**部署狀態**工作區] 中, 選取您要還原的設定, 然後選取要還原的分段部署。</span><span class="sxs-lookup"><span data-stu-id="11eeb-143">In **Deployment status** workspace, select the setting you want to revert, and then select the staged deployment to revert.</span></span>
4. <span data-ttu-id="11eeb-144">在 [**需要回復此變更**] 下, 選取 [**還原部署**]。</span><span class="sxs-lookup"><span data-stu-id="11eeb-144">Under **Need to revert this change**, select **Revert deployment**.</span></span>

![可設定的設定部署還原](images/config-setting-revert.png) 

## <a name="additional-resources"></a><span data-ttu-id="11eeb-146">其他資源</span><span class="sxs-lookup"><span data-stu-id="11eeb-146">Additional resources</span></span>
- [<span data-ttu-id="11eeb-147">可設定的設定概述</span><span class="sxs-lookup"><span data-stu-id="11eeb-147">Configurable settings overview</span></span>](config-setting-overview.md)
- [<span data-ttu-id="11eeb-148">可設定的設定參考</span><span class="sxs-lookup"><span data-stu-id="11eeb-148">Configurable settings reference</span></span>](config-setting-ref.md) 
