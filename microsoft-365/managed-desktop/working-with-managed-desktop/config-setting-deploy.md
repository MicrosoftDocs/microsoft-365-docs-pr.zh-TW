---
title: 在 Microsoft 受管理的電腦中部署可設定的設定
description: 在 Microsoft 受管理的電腦中部署及追蹤可設定的設定變更。
keywords: Microsoft 受管理的電腦，Microsoft 365，服務，檔，部署，分段部署，可設定的設定
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: a24d0dc64e2262a8b208119c45a4a6bade701c10
ms.sourcegitcommit: adaedd1418a3bd6e4875b77fd9e008b47e0b2a51
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/18/2020
ms.locfileid: "48104531"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a><span data-ttu-id="8c80f-104">部署及追蹤可設定的設定-Microsoft 受管理的電腦</span><span class="sxs-lookup"><span data-stu-id="8c80f-104">Deploy and track configurable settings - Microsoft Managed Desktop</span></span>

<span data-ttu-id="8c80f-105">變更您的設定類別及階段部署之後，部署狀態頁面可讓您開始將設定部署至群組。</span><span class="sxs-lookup"><span data-stu-id="8c80f-105">After you make changes to your setting categories and stage a deployment, the Deployment status page allows you to begin deploying your settings to groups.</span></span> <span data-ttu-id="8c80f-106">此頁面會顯示每個可設定設定的摘要。</span><span class="sxs-lookup"><span data-stu-id="8c80f-106">This page shows a summary of each configurable setting.</span></span> <span data-ttu-id="8c80f-107">開啟設定類別後，您就可以將設定部署至群組，並追蹤這些部署的進度。</span><span class="sxs-lookup"><span data-stu-id="8c80f-107">By opening a setting category you can deploy settings to groups and track the progress of these deployments.</span></span>

## <a name="deployment-statuses"></a><span data-ttu-id="8c80f-108">部署狀態</span><span class="sxs-lookup"><span data-stu-id="8c80f-108">Deployment statuses</span></span> 

<span data-ttu-id="8c80f-109">您會看到每個部署的狀態。</span><span class="sxs-lookup"><span data-stu-id="8c80f-109">These are the statuses you’ll see for each deployment.</span></span>

<span data-ttu-id="8c80f-110">狀態</span><span class="sxs-lookup"><span data-stu-id="8c80f-110">Status</span></span>  | <span data-ttu-id="8c80f-111">說明</span><span class="sxs-lookup"><span data-stu-id="8c80f-111">Explanation</span></span> 
--- | --- 
<span data-ttu-id="8c80f-112">部署</span><span class="sxs-lookup"><span data-stu-id="8c80f-112">Deploy</span></span> | <span data-ttu-id="8c80f-113">您的變更等候部署至此群組。</span><span class="sxs-lookup"><span data-stu-id="8c80f-113">Your change is waiting to be deployed to this group.</span></span>
<span data-ttu-id="8c80f-114">進行中。</span><span class="sxs-lookup"><span data-stu-id="8c80f-114">In progress</span></span> | <span data-ttu-id="8c80f-115">變更會套用到此群組中的使用中裝置。</span><span class="sxs-lookup"><span data-stu-id="8c80f-115">The change is being applied to active devices in this group.</span></span> 
<span data-ttu-id="8c80f-116">已完成</span><span class="sxs-lookup"><span data-stu-id="8c80f-116">Complete</span></span> | <span data-ttu-id="8c80f-117">在此群組中所有作用中裝置上的變更已完成。</span><span class="sxs-lookup"><span data-stu-id="8c80f-117">The change completed on all active devices in this group.</span></span> 
<span data-ttu-id="8c80f-118">失敗</span><span class="sxs-lookup"><span data-stu-id="8c80f-118">Failed</span></span> | <span data-ttu-id="8c80f-119">變更群組中的10% 作用中裝置時失敗，所以部署已停止。</span><span class="sxs-lookup"><span data-stu-id="8c80f-119">The change failed on a 10 percent of active devices in the group, so the deployment was stopped.</span></span><br><br> <span data-ttu-id="8c80f-120">系統會自動開啟支援要求，以進行部署的疑難排解 Microsoft 受管理的電腦作業。</span><span class="sxs-lookup"><span data-stu-id="8c80f-120">A support request will be automatically opened with Microsoft Managed Desktop operations to troubleshoot the deployment.</span></span> 
<span data-ttu-id="8c80f-121">恢復</span><span class="sxs-lookup"><span data-stu-id="8c80f-121">Reverted</span></span> | <span data-ttu-id="8c80f-122">變更已還原為已成功部署至所有部署群組的最後變更。</span><span class="sxs-lookup"><span data-stu-id="8c80f-122">The change was reverted to the last change that was successfully deployed to all deployment groups.</span></span>

## <a name="deploy-changes"></a><span data-ttu-id="8c80f-123">部署變更</span><span class="sxs-lookup"><span data-stu-id="8c80f-123">Deploy changes</span></span>

<span data-ttu-id="8c80f-124">在這些指示中，我們會顯示桌面背景圖片。</span><span class="sxs-lookup"><span data-stu-id="8c80f-124">We’ll show Desktop background picture in these instructions.</span></span> <span data-ttu-id="8c80f-125">在分段部署之後，您可以從 [部署狀態] 頁面部署變更。</span><span class="sxs-lookup"><span data-stu-id="8c80f-125">After you’ve staged a deployment, you deploy changes from the Deployment status page.</span></span> 

<span data-ttu-id="8c80f-126">**若要部署變更**</span><span class="sxs-lookup"><span data-stu-id="8c80f-126">**To deploy changes**</span></span>

1. <span data-ttu-id="8c80f-127">登入 [Microsoft 端點管理員](https://endpoint.microsoft.com/)，並流覽至 [**裝置**] 功能表</span><span class="sxs-lookup"><span data-stu-id="8c80f-127">Sign in to [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) and navigate to the **Devices** menu</span></span>
2. <span data-ttu-id="8c80f-128">尋找 [Microsoft 受管理的電腦] 區段中，選取 [**設定**]。</span><span class="sxs-lookup"><span data-stu-id="8c80f-128">Look for the Microsoft Managed Desktop section, select **Settings**.</span></span>
3. <span data-ttu-id="8c80f-129">在 [ **部署狀態** ] 工作區中，選取您要部署的設定，然後選取要部署的分段部署。</span><span class="sxs-lookup"><span data-stu-id="8c80f-129">In **Deployment status** workspace, select the setting you want to deploy, and then select the staged deployment to deploy.</span></span>
4. <span data-ttu-id="8c80f-130">選取 [ **部署** ]，將變更部署至其中一個部署群組。</span><span class="sxs-lookup"><span data-stu-id="8c80f-130">Select **Deploy** to deploy the change to one of the deployment groups.</span></span>

> [!NOTE] 
> <span data-ttu-id="8c80f-131">橙色的警告圖示會指出有一個舊的群組可供部署，因此建議您在順序中執行。</span><span class="sxs-lookup"><span data-stu-id="8c80f-131">The orange caution icon indicates there is a previous group available for deployment as it’s recommended to roll out in order.</span></span> 

<!-- Needs picture updated to show MEM ![Deployment status workspace. Trusted sites pane on the right. In the Deployment groups section are three columns: deployment groups, devices, and status. In the status column, "deploy" is highlighted.](../../media/1deployedit.png) -->

<span data-ttu-id="8c80f-132">建議依照此順序部署至部署群組： Test、First、Fast 及寬泛。</span><span class="sxs-lookup"><span data-stu-id="8c80f-132">We recommend deploying to deployment groups in this order: Test, First, Fast, and then Broad.</span></span> 

<span data-ttu-id="8c80f-133">每個群組中的變更完成時，狀態變更為 [ **完成**]。</span><span class="sxs-lookup"><span data-stu-id="8c80f-133">When changes complete in each group, the status changes to **Complete**.</span></span>

<!-- Needs picture updated to show MEM ![Deployment status workspace with columns for date updated, version, test, first, fast, and broad. The Proxy row is expanded, showing a dated setting flagged as "complete" in each of the four deployment groups.](../../media/2completeedit.png) -->

## <a name="revert-deployment"></a><span data-ttu-id="8c80f-134">還原部署</span><span class="sxs-lookup"><span data-stu-id="8c80f-134">Revert deployment</span></span>

<span data-ttu-id="8c80f-135">在您部署變更之後，您可以從 **部署狀態** 還原。</span><span class="sxs-lookup"><span data-stu-id="8c80f-135">After you’ve deployed a change, you can revert from **Deployment status**.</span></span> <span data-ttu-id="8c80f-136">當您還原 **進行中** 或 **完成** 的變更時，目前的部署會停止。</span><span class="sxs-lookup"><span data-stu-id="8c80f-136">When you revert a change that is **In progress** or **Complete**, the current deployment stops.</span></span> <span data-ttu-id="8c80f-137">設定會還原為所有群組部署的最後一個版本。</span><span class="sxs-lookup"><span data-stu-id="8c80f-137">The setting will revert to the last version that was deployed to all groups.</span></span> 

<span data-ttu-id="8c80f-138">我們將使用桌面背景圖片做為範例，顯示還原變更的步驟。</span><span class="sxs-lookup"><span data-stu-id="8c80f-138">We’ll show the steps to revert a change using the Desktop background picture as an example.</span></span> 

<span data-ttu-id="8c80f-139">**還原變更**</span><span class="sxs-lookup"><span data-stu-id="8c80f-139">**To revert a change**</span></span>
1. <span data-ttu-id="8c80f-140">登入 [Microsoft 端點管理員](https://endpoint.microsoft.com/)，並流覽至 [**裝置**] 功能表</span><span class="sxs-lookup"><span data-stu-id="8c80f-140">Sign in to [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) and navigate to the **Devices** menu</span></span>
2. <span data-ttu-id="8c80f-141">尋找 [Microsoft 受管理的電腦] 區段中，選取 [**設定**]。</span><span class="sxs-lookup"><span data-stu-id="8c80f-141">Look for the Microsoft Managed Desktop section, select **Settings**.</span></span>
3. <span data-ttu-id="8c80f-142">在 [ **部署狀態** ] 工作區中，選取您要還原的設定，然後選取要還原的分段部署。</span><span class="sxs-lookup"><span data-stu-id="8c80f-142">In **Deployment status** workspace, select the setting you want to revert, and then select the staged deployment to revert.</span></span>
4. <span data-ttu-id="8c80f-143">在 [ **需要回復此變更嗎？**] 下，選取 [ **還原部署**]。</span><span class="sxs-lookup"><span data-stu-id="8c80f-143">Under **Need to revert this change?**, select **Revert deployment**.</span></span>

<!-- Needs picture updated to show MEM ![Deployment status workspace. Browser start pages is selected, opening a pane on the right side with data about the submitted change and its status. At the bottom is the "need to revert this change" area where you can select "Revert deployment."](../../media/3revert.png) -->

## <a name="additional-resources"></a><span data-ttu-id="8c80f-144">其他資源</span><span class="sxs-lookup"><span data-stu-id="8c80f-144">Additional resources</span></span>
- [<span data-ttu-id="8c80f-145">可設定的設定概述</span><span class="sxs-lookup"><span data-stu-id="8c80f-145">Configurable settings overview</span></span>](config-setting-overview.md)
- [<span data-ttu-id="8c80f-146">可設定的設定參考</span><span class="sxs-lookup"><span data-stu-id="8c80f-146">Configurable settings reference</span></span>](config-setting-ref.md) 
