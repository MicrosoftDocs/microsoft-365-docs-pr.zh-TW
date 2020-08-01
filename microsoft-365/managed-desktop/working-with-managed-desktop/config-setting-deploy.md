---
title: 在 Microsoft Managed Desktop 中部署可設定的設定
description: 在 Microsoft 受管理的電腦中部署及追蹤可設定的設定變更。
keywords: Microsoft 受管理的桌面、Microsoft 365、服務、檔、部署、分段部署、可設定的設定
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: b731422e6d981b12ea576ed26b841e7c679266ae
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/30/2020
ms.locfileid: "46530256"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a><span data-ttu-id="a6571-104">部署及追蹤可設定的設定-Microsoft 受管理的電腦</span><span class="sxs-lookup"><span data-stu-id="a6571-104">Deploy and track configurable settings - Microsoft Managed Desktop</span></span>

<span data-ttu-id="a6571-105">變更您的設定類別及階段部署之後，部署狀態頁面可讓您開始將設定部署至群組。</span><span class="sxs-lookup"><span data-stu-id="a6571-105">After you make changes to your setting categories and stage a deployment, the Deployment status page allows you to begin deploying your settings to groups.</span></span> <span data-ttu-id="a6571-106">此頁面會顯示每個可設定設定的摘要。</span><span class="sxs-lookup"><span data-stu-id="a6571-106">This page shows a summary of each configurable setting.</span></span> <span data-ttu-id="a6571-107">開啟設定類別後，您就可以將設定部署至群組，並追蹤這些部署的進度。</span><span class="sxs-lookup"><span data-stu-id="a6571-107">By opening a setting category you can deploy settings to groups and track the progress of these deployments.</span></span>

## <a name="deployment-statuses"></a><span data-ttu-id="a6571-108">部署狀態</span><span class="sxs-lookup"><span data-stu-id="a6571-108">Deployment statuses</span></span> 

<span data-ttu-id="a6571-109">您會看到每個部署的狀態。</span><span class="sxs-lookup"><span data-stu-id="a6571-109">These are the statuses you’ll see for each deployment.</span></span>

<span data-ttu-id="a6571-110">狀態</span><span class="sxs-lookup"><span data-stu-id="a6571-110">Status</span></span>  | <span data-ttu-id="a6571-111">說明</span><span class="sxs-lookup"><span data-stu-id="a6571-111">Explanation</span></span> 
--- | --- 
<span data-ttu-id="a6571-112">部署</span><span class="sxs-lookup"><span data-stu-id="a6571-112">Deploy</span></span> | <span data-ttu-id="a6571-113">您的變更等候部署至此群組。</span><span class="sxs-lookup"><span data-stu-id="a6571-113">Your change is waiting to be deployed to this group.</span></span>
<span data-ttu-id="a6571-114">進行中。</span><span class="sxs-lookup"><span data-stu-id="a6571-114">In progress</span></span> | <span data-ttu-id="a6571-115">變更會套用到此群組中的使用中裝置。</span><span class="sxs-lookup"><span data-stu-id="a6571-115">The change is being applied to active devices in this group.</span></span> 
<span data-ttu-id="a6571-116">已完成</span><span class="sxs-lookup"><span data-stu-id="a6571-116">Complete</span></span> | <span data-ttu-id="a6571-117">在此群組中所有作用中裝置上的變更已完成。</span><span class="sxs-lookup"><span data-stu-id="a6571-117">The change completed on all active devices in this group.</span></span> 
<span data-ttu-id="a6571-118">失敗</span><span class="sxs-lookup"><span data-stu-id="a6571-118">Failed</span></span> | <span data-ttu-id="a6571-119">變更群組中的10% 作用中裝置時失敗，所以部署已停止。</span><span class="sxs-lookup"><span data-stu-id="a6571-119">The change failed on a 10 percent of active devices in the group, so the deployment was stopped.</span></span><br><br> <span data-ttu-id="a6571-120">系統會自動使用 Microsoft Managed Desktop operations 來開啟支援要求，以進行部署疑難排解。</span><span class="sxs-lookup"><span data-stu-id="a6571-120">A support request will be automatically opened with Microsoft Managed Desktop operations to troubleshoot the deployment.</span></span> 
<span data-ttu-id="a6571-121">恢復</span><span class="sxs-lookup"><span data-stu-id="a6571-121">Reverted</span></span> | <span data-ttu-id="a6571-122">變更已還原為已成功部署至所有部署群組的最後變更。</span><span class="sxs-lookup"><span data-stu-id="a6571-122">The change was reverted to the last change that was successfully deployed to all deployment groups.</span></span>

## <a name="deploy-changes"></a><span data-ttu-id="a6571-123">部署變更</span><span class="sxs-lookup"><span data-stu-id="a6571-123">Deploy changes</span></span>

<span data-ttu-id="a6571-124">在這些指示中，我們會顯示桌面背景圖片。</span><span class="sxs-lookup"><span data-stu-id="a6571-124">We’ll show Desktop background picture in these instructions.</span></span> <span data-ttu-id="a6571-125">在分段部署之後，您可以從 [部署狀態] 頁面部署變更。</span><span class="sxs-lookup"><span data-stu-id="a6571-125">After you’ve staged a deployment, you deploy changes from the Deployment status page.</span></span> 

<span data-ttu-id="a6571-126">**若要部署變更**</span><span class="sxs-lookup"><span data-stu-id="a6571-126">**To deploy changes**</span></span>

1. <span data-ttu-id="a6571-127">登入[Microsoft Managed Desktop Admin 入口網站](https://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="a6571-127">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="a6571-128">在 [設定] 底下，選取 [**可\*\*\*\*設定**]。</span><span class="sxs-lookup"><span data-stu-id="a6571-128">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="a6571-129">在 [**部署狀態**] 工作區中，選取您要部署的設定，然後選取要部署的分段部署。</span><span class="sxs-lookup"><span data-stu-id="a6571-129">In **Deployment status** workspace, select the setting you want to deploy, and then select the staged deployment to deploy.</span></span>
4. <span data-ttu-id="a6571-130">選取 [**部署**]，將變更部署至其中一個部署群組。</span><span class="sxs-lookup"><span data-stu-id="a6571-130">Select **Deploy** to deploy the change to one of the deployment groups.</span></span>

> [!NOTE] 
> <span data-ttu-id="a6571-131">橙色的警告圖示會指出有一個舊的群組可供部署，因此建議您在順序中執行。</span><span class="sxs-lookup"><span data-stu-id="a6571-131">The orange caution icon indicates there is a previous group available for deployment as it’s recommended to roll out in order.</span></span> 

<span data-ttu-id="a6571-132">![部署狀態工作區。</span><span class="sxs-lookup"><span data-stu-id="a6571-132">![Deployment status workspace.</span></span> <span data-ttu-id="a6571-133">右側的 [信任的網站] 窗格。</span><span class="sxs-lookup"><span data-stu-id="a6571-133">Trusted sites pane on the right.</span></span> <span data-ttu-id="a6571-134">「部署群組」區段分為三欄：部署群組、裝置和狀態。</span><span class="sxs-lookup"><span data-stu-id="a6571-134">In the Deployment groups section are three columns: deployment groups, devices, and status.</span></span> <span data-ttu-id="a6571-135">在 [狀態] 欄中，會反白顯示「deploy」。](../../media/1deployedit.png)</span><span class="sxs-lookup"><span data-stu-id="a6571-135">In the status column, "deploy" is highlighted.](../../media/1deployedit.png)</span></span>
<span data-ttu-id="a6571-136">建議依照此順序部署至部署群組： Test、First、Fast 及寬泛。</span><span class="sxs-lookup"><span data-stu-id="a6571-136">We recommend deploying to deployment groups in this order: Test, First, Fast, and then Broad.</span></span> 

<span data-ttu-id="a6571-137">每個群組中的變更完成時，狀態變更為 [**完成**]。</span><span class="sxs-lookup"><span data-stu-id="a6571-137">When changes complete in each group, the status changes to **Complete**.</span></span>

![部署狀態工作區，具有更新日期的欄、版本、測試、第一、快速和廣泛。](../../media/2completeedit.png)

## <a name="revert-deployment"></a><span data-ttu-id="a6571-140">還原部署</span><span class="sxs-lookup"><span data-stu-id="a6571-140">Revert deployment</span></span>

<span data-ttu-id="a6571-141">在您部署變更之後，您可以從**部署狀態**還原。</span><span class="sxs-lookup"><span data-stu-id="a6571-141">After you’ve deployed a change, you can revert from **Deployment status**.</span></span> <span data-ttu-id="a6571-142">當您還原**進行中**或**完成**的變更時，目前的部署會停止。</span><span class="sxs-lookup"><span data-stu-id="a6571-142">When you revert a change that is **In progress** or **Complete**, the current deployment stops.</span></span> <span data-ttu-id="a6571-143">設定會還原為所有群組部署的最後一個版本。</span><span class="sxs-lookup"><span data-stu-id="a6571-143">The setting will revert to the last version that was deployed to all groups.</span></span> 

<span data-ttu-id="a6571-144">我們將使用桌面背景圖片做為範例，顯示還原變更的步驟。</span><span class="sxs-lookup"><span data-stu-id="a6571-144">We’ll show the steps to revert a change using the Desktop background picture as an example.</span></span> 

<span data-ttu-id="a6571-145">**還原變更**</span><span class="sxs-lookup"><span data-stu-id="a6571-145">**To revert a change**</span></span>
1. <span data-ttu-id="a6571-146">登入[Microsoft Managed Desktop Admin 入口網站](https://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="a6571-146">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="a6571-147">在 [設定] 底下，選取 [**可\*\*\*\*設定**]。</span><span class="sxs-lookup"><span data-stu-id="a6571-147">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="a6571-148">在 [**部署狀態**] 工作區中，選取您要還原的設定，然後選取要還原的分段部署。</span><span class="sxs-lookup"><span data-stu-id="a6571-148">In **Deployment status** workspace, select the setting you want to revert, and then select the staged deployment to revert.</span></span>
4. <span data-ttu-id="a6571-149">在 [**需要回復此變更嗎？**] 下，選取 [**還原部署**]。</span><span class="sxs-lookup"><span data-stu-id="a6571-149">Under **Need to revert this change?**, select **Revert deployment**.</span></span>

![部署狀態工作區。](../../media/3revert.png) 

## <a name="additional-resources"></a><span data-ttu-id="a6571-153">其他資源</span><span class="sxs-lookup"><span data-stu-id="a6571-153">Additional resources</span></span>
- [<span data-ttu-id="a6571-154">可設定的設定概述</span><span class="sxs-lookup"><span data-stu-id="a6571-154">Configurable settings overview</span></span>](config-setting-overview.md)
- [<span data-ttu-id="a6571-155">可設定的設定參考</span><span class="sxs-lookup"><span data-stu-id="a6571-155">Configurable settings reference</span></span>](config-setting-ref.md) 
