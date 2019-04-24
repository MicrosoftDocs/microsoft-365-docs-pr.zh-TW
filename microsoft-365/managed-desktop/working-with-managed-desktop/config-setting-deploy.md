---
title: 部署 Microsoft 受管理電腦中的組態設定
description: 部署及追蹤 Microsoft 受管理電腦中的可設定的設定變更。
keywords: Microsoft 受管理的電腦、 Microsoft 365、 服務、 文件、 部署、 分段的部署中，組態設定
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 2/17/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 4662373b926d07558ecedd05c9dfcf472ceb6357
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278414"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a><span data-ttu-id="28b97-104">部署及追蹤可設定-Microsoft 受管理的電腦</span><span class="sxs-lookup"><span data-stu-id="28b97-104">Deploy and track configurable settings - Microsoft Managed Desktop</span></span>

<span data-ttu-id="28b97-105">變更您設定的分類和階段部署之後，[部署狀態] 頁面可讓您開始部署您的設定群組。</span><span class="sxs-lookup"><span data-stu-id="28b97-105">After you make changes to your setting categories and stage a deployment, the Deployment status page allows you to begin deploying your settings to groups.</span></span> <span data-ttu-id="28b97-106">此頁面會顯示每個可設定] 設定的摘要。</span><span class="sxs-lookup"><span data-stu-id="28b97-106">This page shows a summary of each configurable setting.</span></span> <span data-ttu-id="28b97-107">藉由開啟設定類別您可以將設定部署至群組，並追蹤這些部署中的進度。</span><span class="sxs-lookup"><span data-stu-id="28b97-107">By opening a setting category you can deploy settings to groups and track the progress of these deployments.</span></span>

## <a name="deployment-statuses"></a><span data-ttu-id="28b97-108">部署狀態</span><span class="sxs-lookup"><span data-stu-id="28b97-108">Deployment statuses</span></span> 

<span data-ttu-id="28b97-109">這些是您會看到每個部署雕像。</span><span class="sxs-lookup"><span data-stu-id="28b97-109">These are the statues you’ll see for each deployment.</span></span>

<span data-ttu-id="28b97-110">狀態</span><span class="sxs-lookup"><span data-stu-id="28b97-110">Status</span></span>  | <span data-ttu-id="28b97-111">說明</span><span class="sxs-lookup"><span data-stu-id="28b97-111">Explanation</span></span> 
--- | --- 
<span data-ttu-id="28b97-112">部署</span><span class="sxs-lookup"><span data-stu-id="28b97-112">Deploy</span></span> | <span data-ttu-id="28b97-113">您的變更正在等候部署至這個群組。</span><span class="sxs-lookup"><span data-stu-id="28b97-113">Your change is waiting to be deployed to this group.</span></span>
<span data-ttu-id="28b97-114">進行中。</span><span class="sxs-lookup"><span data-stu-id="28b97-114">In progress</span></span> | <span data-ttu-id="28b97-115">變更會套用到此群組中的作用中裝置。</span><span class="sxs-lookup"><span data-stu-id="28b97-115">The change is being applied to active devices in this group.</span></span> 
<span data-ttu-id="28b97-116">已完成</span><span class="sxs-lookup"><span data-stu-id="28b97-116">Complete</span></span> | <span data-ttu-id="28b97-117">變更此群組中的所有作用中裝置上已完成。</span><span class="sxs-lookup"><span data-stu-id="28b97-117">The change completed on all active devices in this group.</span></span> 
<span data-ttu-id="28b97-118">失敗</span><span class="sxs-lookup"><span data-stu-id="28b97-118">Failed</span></span> | <span data-ttu-id="28b97-119">在群組中的作用中裝置的 10%的變更失敗，導致部署已停止。</span><span class="sxs-lookup"><span data-stu-id="28b97-119">The change failed on a 10 percent of active devices in the group, so the deployment was stopped.</span></span><br><br> <span data-ttu-id="28b97-120">與 Microsoft 受管理電腦作業來疑難排解部署會自動開啟支援要求。</span><span class="sxs-lookup"><span data-stu-id="28b97-120">A support request will be automatically opened with Microsoft Managed Desktop operations to troubleshoot the deployment.</span></span> 
<span data-ttu-id="28b97-121">還原</span><span class="sxs-lookup"><span data-stu-id="28b97-121">Reverted</span></span> | <span data-ttu-id="28b97-122">變更已還原至已成功部署至所有部署群組的最後變更。</span><span class="sxs-lookup"><span data-stu-id="28b97-122">The change was reverted to the last change that was successfully deployed to all deployment groups.</span></span>

## <a name="deploy-changes"></a><span data-ttu-id="28b97-123">將變更部署</span><span class="sxs-lookup"><span data-stu-id="28b97-123">Deploy changes</span></span>

<span data-ttu-id="28b97-124">我們會在這些指示中顯示桌面背景圖片。</span><span class="sxs-lookup"><span data-stu-id="28b97-124">We’ll show Desktop background picture in these instructions.</span></span> <span data-ttu-id="28b97-125">您已分段部署之後，您部署從 [部署狀態] 頁面上的變更。</span><span class="sxs-lookup"><span data-stu-id="28b97-125">After you’ve staged a deployment, you deploy changes from the Deployment status page.</span></span> 

<span data-ttu-id="28b97-126">**若要部署的變更**</span><span class="sxs-lookup"><span data-stu-id="28b97-126">**To deploy changes**</span></span>

1. <span data-ttu-id="28b97-127">登入[Microsoft 受管理電腦系統管理員入口網站](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="28b97-127">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="28b97-128">在 [**設定**] 下選取 [**可設定**]。</span><span class="sxs-lookup"><span data-stu-id="28b97-128">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="28b97-129">在**部署狀態**工作區中，選取您想要部署的設定，然後選取分段的部署，以部署。</span><span class="sxs-lookup"><span data-stu-id="28b97-129">In **Deployment status** workspace, select the setting you want to deploy, and then select the staged deployment to deploy.</span></span>
4. <span data-ttu-id="28b97-130">選取要將變更部署至其中一個部署群組的**部署**。</span><span class="sxs-lookup"><span data-stu-id="28b97-130">Select **Deploy** to deploy the change to one of the deployment groups.</span></span>

![可設定的設定部署狀態概觀](images/deploy-cs-overview.png)

<span data-ttu-id="28b97-132">Microsoft 受管理電腦建議部署至依此順序部署群組： 測試、 第一個、 快速，然後廣泛。</span><span class="sxs-lookup"><span data-stu-id="28b97-132">Microsoft Managed Desktop recommends deploying to deployment groups in this order: Test, First, Fast, and then Broad.</span></span> 

<span data-ttu-id="28b97-133">當變更完成每個群組中時，狀態會變更為**完成**。</span><span class="sxs-lookup"><span data-stu-id="28b97-133">When changes complete in each group, the status changes to **Complete**.</span></span>

![完成部署可設定的設定](images/config-setting-complete.png)

## <a name="revert-deployment"></a><span data-ttu-id="28b97-135">回復部署</span><span class="sxs-lookup"><span data-stu-id="28b97-135">Revert deployment</span></span>

<span data-ttu-id="28b97-136">您已部署變更之後，您可以還原從**部署狀態**。</span><span class="sxs-lookup"><span data-stu-id="28b97-136">After you’ve deployed a change, you can revert from **Deployment status**.</span></span> <span data-ttu-id="28b97-137">當您還原為**進行中**或**完成**的變更時，會停止目前的部署。</span><span class="sxs-lookup"><span data-stu-id="28b97-137">When you revert a change that is **In progress** or **Complete**, the current deployment stops.</span></span> <span data-ttu-id="28b97-138">設定會回復至最後一個已部署至所有群組的版本。</span><span class="sxs-lookup"><span data-stu-id="28b97-138">The setting will revert to the last version that was deployed to all groups.</span></span> 

<span data-ttu-id="28b97-139">我們將顯示還原使用桌面背景圖片做為範例變更的步驟。</span><span class="sxs-lookup"><span data-stu-id="28b97-139">We’ll show the steps to revert a change using the Desktop background picture as an example.</span></span> 

<span data-ttu-id="28b97-140">**若要還原的變更**</span><span class="sxs-lookup"><span data-stu-id="28b97-140">**To revert a change**</span></span>
1. <span data-ttu-id="28b97-141">登入[Microsoft 受管理電腦系統管理員入口網站](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="28b97-141">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="28b97-142">在 [**設定**] 下選取 [**可設定**]。</span><span class="sxs-lookup"><span data-stu-id="28b97-142">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="28b97-143">在**部署狀態**工作區中，選取您想要回復，的設定，然後選取要還原分段的部署。</span><span class="sxs-lookup"><span data-stu-id="28b97-143">In **Deployment status** workspace, select the setting you want to revert, and then select the staged deployment to revert.</span></span>
4. <span data-ttu-id="28b97-144">**需要回復此變更**，請選取 [**還原部署**。</span><span class="sxs-lookup"><span data-stu-id="28b97-144">Under **Need to revert this change**, select **Revert deployment**.</span></span>

![部署可設定的設定還原](images/config-setting-revert.png) 

## <a name="additional-resources"></a><span data-ttu-id="28b97-146">其他資源</span><span class="sxs-lookup"><span data-stu-id="28b97-146">Additional resources</span></span>
- [<span data-ttu-id="28b97-147">組態設定概觀</span><span class="sxs-lookup"><span data-stu-id="28b97-147">Configurable settings overview</span></span>](config-setting-overview.md)
- [<span data-ttu-id="28b97-148">可設定的設定參考</span><span class="sxs-lookup"><span data-stu-id="28b97-148">Configurable settings reference</span></span>](config-setting-ref.md) 
