---
title: 部署 Microsoft 受管理電腦中的組態設定
description: 部署及追蹤 Microsoft 受管理電腦中的可設定的設定變更。
keywords: Microsoft 受管理的電腦、 Microsoft 365、 服務、 文件、 部署、 分段的部署中，組態設定
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 2/17/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 62a17c95f5dc6b11f446a27684c507d7aaa95b7b
ms.sourcegitcommit: 8d2e6bcc257a665f53ee914c7f0e1dfb9d31a9e0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/06/2019
ms.locfileid: "30414164"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a><span data-ttu-id="c301c-104">部署及追蹤可設定-Microsoft 受管理的電腦</span><span class="sxs-lookup"><span data-stu-id="c301c-104">Deploy and track configurable settings - Microsoft Managed Desktop</span></span>

<span data-ttu-id="c301c-105">您變更您的設定類別和階段部署之後，您可以部署，並在部署狀態追蹤部署進度。</span><span class="sxs-lookup"><span data-stu-id="c301c-105">After you make changes to your setting categories and stage a deployment, you can deploy and track progress for the deployment on Deployment status.</span></span> <span data-ttu-id="c301c-106">此頁面會顯示每個可設定] 設定的摘要。</span><span class="sxs-lookup"><span data-stu-id="c301c-106">This page shows a summary of each configurable setting.</span></span> <span data-ttu-id="c301c-107">開啟 [若要查看每個部署和其詳細資料，若要將變更部署設定類別]。</span><span class="sxs-lookup"><span data-stu-id="c301c-107">Open a setting category to see each deployment and their details, to deploy the changes.</span></span> 

## <a name="deployment-statuses"></a><span data-ttu-id="c301c-108">部署狀態</span><span class="sxs-lookup"><span data-stu-id="c301c-108">Deployment statuses</span></span> 

<span data-ttu-id="c301c-109">這些是您會看到每個部署雕像。</span><span class="sxs-lookup"><span data-stu-id="c301c-109">These are the statues you’ll see for each deployment.</span></span>

<span data-ttu-id="c301c-110">狀態</span><span class="sxs-lookup"><span data-stu-id="c301c-110">Status</span></span>  | <span data-ttu-id="c301c-111">說明</span><span class="sxs-lookup"><span data-stu-id="c301c-111">Explanation</span></span> 
--- | --- 
<span data-ttu-id="c301c-112">部署</span><span class="sxs-lookup"><span data-stu-id="c301c-112">Deploy</span></span> | <span data-ttu-id="c301c-113">您的變更正在等候部署至這個週期。</span><span class="sxs-lookup"><span data-stu-id="c301c-113">Your change is waiting to be deployed to this ring.</span></span>
<span data-ttu-id="c301c-114">進行中。</span><span class="sxs-lookup"><span data-stu-id="c301c-114">In progress</span></span> | <span data-ttu-id="c301c-115">將變更套用至在此週期中的作用中裝置。</span><span class="sxs-lookup"><span data-stu-id="c301c-115">The change is being applied to active devices in this ring.</span></span> 
<span data-ttu-id="c301c-116">已完成</span><span class="sxs-lookup"><span data-stu-id="c301c-116">Complete</span></span> | <span data-ttu-id="c301c-117">在此週期中的所有作用中裝置上完成變更。</span><span class="sxs-lookup"><span data-stu-id="c301c-117">The change completed on all active devices in this ring.</span></span> 
<span data-ttu-id="c301c-118">失敗</span><span class="sxs-lookup"><span data-stu-id="c301c-118">Failed</span></span> | <span data-ttu-id="c301c-119">在 [作用中的裝置通道，10%的變更失敗，導致部署已停止。</span><span class="sxs-lookup"><span data-stu-id="c301c-119">The change failed on a 10 percent of active devices in the ring, so the deployment was stopped.</span></span><br><br> <span data-ttu-id="c301c-120">與 Microsoft 受管理電腦作業來疑難排解部署會自動開啟支援要求。</span><span class="sxs-lookup"><span data-stu-id="c301c-120">A support request will be automatically opened with Microsoft Managed Desktop operations to troubleshoot the deployment.</span></span> 
<span data-ttu-id="c301c-121">還原</span><span class="sxs-lookup"><span data-stu-id="c301c-121">Reverted</span></span> | <span data-ttu-id="c301c-122">變更已還原至已成功部署至所有部署週期的最後變更。</span><span class="sxs-lookup"><span data-stu-id="c301c-122">The change was reverted to the last change that was successfully deployed to all deployment rings.</span></span>

## <a name="deploy-changes"></a><span data-ttu-id="c301c-123">將變更部署</span><span class="sxs-lookup"><span data-stu-id="c301c-123">Deploy changes</span></span>

<span data-ttu-id="c301c-124">我們會在這些指示中顯示桌面背景圖片。</span><span class="sxs-lookup"><span data-stu-id="c301c-124">We’ll show Desktop background picture in these instructions.</span></span> <span data-ttu-id="c301c-125">已分段部署之後，您將部署來自部署狀態變更。</span><span class="sxs-lookup"><span data-stu-id="c301c-125">After you’ve staged a deployment, you deploy changes from Deployment status.</span></span> 

<span data-ttu-id="c301c-126">**若要部署的變更**</span><span class="sxs-lookup"><span data-stu-id="c301c-126">**To deploy changes**</span></span>

1. <span data-ttu-id="c301c-127">登入[Microsoft 受管理電腦系統管理員入口網站](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="c301c-127">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="c301c-128">在 [**設定**] 下選取 [**可設定**]。</span><span class="sxs-lookup"><span data-stu-id="c301c-128">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="c301c-129">在**部署狀態**工作區中，選取您想要部署的設定，然後選取分段的部署，以部署。</span><span class="sxs-lookup"><span data-stu-id="c301c-129">In **Deployment status** workspace, select the setting you want to deploy, and then select the staged deployment to deploy.</span></span>
4. <span data-ttu-id="c301c-130">選取要將變更部署至下列其中一個部署週期的**部署**。</span><span class="sxs-lookup"><span data-stu-id="c301c-130">Select **Deploy** to deploy the change to one of the deployment rings.</span></span>

![可設定的設定部署狀態概觀](images/deploy-cs-overview.png)

<span data-ttu-id="c301c-132">Microsoft 受管理電腦建議部署至部署週期依此順序： 測試、 第一個、 快速，然後廣泛。</span><span class="sxs-lookup"><span data-stu-id="c301c-132">Microsoft Managed Desktop recommends deploying to deployment rings in this order: Test, First, Fast, and then Broad.</span></span> 

<span data-ttu-id="c301c-133">在每個通道中變更完成，狀態會變更為**完成**。</span><span class="sxs-lookup"><span data-stu-id="c301c-133">When changes complete in each ring, the status changes to **Complete**.</span></span>

![完成部署可設定的設定](images/config-setting-complete.png)

## <a name="revert-deployment"></a><span data-ttu-id="c301c-135">回復部署</span><span class="sxs-lookup"><span data-stu-id="c301c-135">Revert deployment</span></span>

<span data-ttu-id="c301c-136">我們會在這些指示中顯示桌面背景圖片。</span><span class="sxs-lookup"><span data-stu-id="c301c-136">We’ll show Desktop background picture in these instructions.</span></span> 

<span data-ttu-id="c301c-137">您已部署變更之後，您可以還原從**部署狀態**。</span><span class="sxs-lookup"><span data-stu-id="c301c-137">After you’ve deployed a change, you can revert from **Deployment status**.</span></span> <span data-ttu-id="c301c-138">當您還原為**進行中**或**完成**的變更時，會停止目前的部署。</span><span class="sxs-lookup"><span data-stu-id="c301c-138">When you revert a change that is **In progress** or **Complete**, the current deployment stops.</span></span> <span data-ttu-id="c301c-139">設定將會還原至最後一個已部署至所有通道的版本。</span><span class="sxs-lookup"><span data-stu-id="c301c-139">The setting will revert to the last version that was deployed to all rings.</span></span> 

<span data-ttu-id="c301c-140">**若要還原的變更**</span><span class="sxs-lookup"><span data-stu-id="c301c-140">**To revert a change**</span></span>
1. <span data-ttu-id="c301c-141">登入[Microsoft 受管理電腦系統管理員入口網站](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="c301c-141">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="c301c-142">在 [**設定**] 下選取 [**可設定**]。</span><span class="sxs-lookup"><span data-stu-id="c301c-142">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="c301c-143">在**部署狀態**工作區中，選取您想要回復，的設定，然後選取要還原分段的部署。</span><span class="sxs-lookup"><span data-stu-id="c301c-143">In **Deployment status** workspace, select the setting you want to revert, and then select the staged deployment to revert.</span></span>
4. <span data-ttu-id="c301c-144">**需要回復此變更**，請選取 [**還原部署**。</span><span class="sxs-lookup"><span data-stu-id="c301c-144">Under **Need to revert this change**, select **Revert deployment**.</span></span>

![部署可設定的設定還原](images/config-setting-revert.png) 

## <a name="additional-resources"></a><span data-ttu-id="c301c-146">其他資源</span><span class="sxs-lookup"><span data-stu-id="c301c-146">Additional resources</span></span>
- [<span data-ttu-id="c301c-147">組態設定概觀</span><span class="sxs-lookup"><span data-stu-id="c301c-147">Configurable settings overview</span></span>](config-setting-overview.md)
- [<span data-ttu-id="c301c-148">可設定的設定參考</span><span class="sxs-lookup"><span data-stu-id="c301c-148">Configurable settings reference</span></span>](config-setting-ref.md) 