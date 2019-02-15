---
title: 部署 Microsoft 受管理的桌上型電腦中的組態設定
description: 部署及追蹤 Microsoft 受管理的桌上型電腦中的組態設定變更。
keywords: Microsoft 受管理的桌上型電腦、 Microsoft 365、 服務、 文件、 部署、 分段的部署組態設定
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 2/12/2019
ms.openlocfilehash: fd0e0750332fa8f650cfc4756f8eb108be2a71df
ms.sourcegitcommit: 59bc66eaa2575bad8ecb34d45b1172cda23a729b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2019
ms.locfileid: "30051124"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a><span data-ttu-id="a7340-104">部署及追蹤組態設定-Microsoft 受管理的桌上型電腦</span><span class="sxs-lookup"><span data-stu-id="a7340-104">Deploy and track configurable settings - Microsoft Managed Desktop</span></span>

<span data-ttu-id="a7340-p101">您變更設定類別和階段部署之後，您可以部署及部署狀態追蹤部署進度。此頁面會顯示每個可設定的摘要。開啟 [設定類別以查看每個部署及其詳細資料，來部署所做的變更]。</span><span class="sxs-lookup"><span data-stu-id="a7340-p101">After you make changes to your setting categories and stage a deployment, you can deploy and track progress for the deployment on Deployment status. This page shows a summary of each configurable setting. Open a setting category to see each deployment and their details, to deploy the changes.</span></span> 

## <a name="deployment-statuses"></a><span data-ttu-id="a7340-108">部署狀態</span><span class="sxs-lookup"><span data-stu-id="a7340-108">Deployment statuses</span></span> 

<span data-ttu-id="a7340-109">這些是您會看見的每個部署雕像。</span><span class="sxs-lookup"><span data-stu-id="a7340-109">These are the statues you’ll see for each deployment.</span></span>

<span data-ttu-id="a7340-110">狀態</span><span class="sxs-lookup"><span data-stu-id="a7340-110">Status</span></span>  | <span data-ttu-id="a7340-111">說明</span><span class="sxs-lookup"><span data-stu-id="a7340-111">Explanation</span></span> 
--- | --- 
<span data-ttu-id="a7340-112">部署</span><span class="sxs-lookup"><span data-stu-id="a7340-112">Deploy</span></span> | <span data-ttu-id="a7340-113">您的變更正在等待部署至這個響鈴。</span><span class="sxs-lookup"><span data-stu-id="a7340-113">Your change is waiting to be deployed to this ring.</span></span>
<span data-ttu-id="a7340-114">進行中</span><span class="sxs-lookup"><span data-stu-id="a7340-114">In progress</span></span> | <span data-ttu-id="a7340-115">變更會套用到此響鈴的裝置。</span><span class="sxs-lookup"><span data-stu-id="a7340-115">The change is being applied to devices in this ring.</span></span> 
<span data-ttu-id="a7340-116">完整</span><span class="sxs-lookup"><span data-stu-id="a7340-116">Complete</span></span> | <span data-ttu-id="a7340-117">變更會套用到此響鈴的裝置。</span><span class="sxs-lookup"><span data-stu-id="a7340-117">The change is being applied to devices in this ring.</span></span> 
<span data-ttu-id="a7340-118">失敗</span><span class="sxs-lookup"><span data-stu-id="a7340-118">Failed</span></span> | <span data-ttu-id="a7340-119">變更失敗 10%的響鈴的裝置上以便部署已停止。</span><span class="sxs-lookup"><span data-stu-id="a7340-119">The change failed on a 10 percent of devices in the ring, so the deployment was stopped.</span></span><br><br> <span data-ttu-id="a7340-120">支援要求將會自動開啟 Microsoft 受管理的桌上型電腦每日操作來疑難排解部署。</span><span class="sxs-lookup"><span data-stu-id="a7340-120">A support request will be automatically opened with Microsoft Managed Desktop operations to troubleshoot the deployment.</span></span> 
<span data-ttu-id="a7340-121">Csdeviceupdateconfiguration</span><span class="sxs-lookup"><span data-stu-id="a7340-121">Reverted</span></span> | <span data-ttu-id="a7340-122">變更已還原成已成功部署至所有部署鈴響的最後一個修訂。</span><span class="sxs-lookup"><span data-stu-id="a7340-122">The change was reverted to the last change that was successfully deployed to all deployment rings.</span></span>

## <a name="deploy-changes"></a><span data-ttu-id="a7340-123">部署的變更</span><span class="sxs-lookup"><span data-stu-id="a7340-123">Deploy changes</span></span>

<span data-ttu-id="a7340-p102">我們將這些指示中顯示桌面背景圖片。您已分段部署之後，您部署從部署狀態的變更。</span><span class="sxs-lookup"><span data-stu-id="a7340-p102">We’ll show Desktop background picture in these instructions. After you’ve staged a deployment, you deploy changes from Deployment status.</span></span> 

<span data-ttu-id="a7340-126">**若要部署的變更**</span><span class="sxs-lookup"><span data-stu-id="a7340-126">**To deploy changes**</span></span>

1. <span data-ttu-id="a7340-127">登入[Microsoft 受管理的桌上型電腦管理入口網站](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="a7340-127">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="a7340-128">[**設定**] 下選取 [**可設定**]。</span><span class="sxs-lookup"><span data-stu-id="a7340-128">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="a7340-129">在**部署狀態**工作區中，選取您想要部署的設定，然後選取要部署分段的部署。</span><span class="sxs-lookup"><span data-stu-id="a7340-129">In **Deployment status** workspace, select the setting you want to deploy, and then select the staged deployment to deploy.</span></span>
4. <span data-ttu-id="a7340-130">選取其中一個部署鈴響部署變更的**部署**。</span><span class="sxs-lookup"><span data-stu-id="a7340-130">Select **Deploy** to deploy the change to one of the deployment rings.</span></span>

![可設定的設定部署狀態概觀 （英文)](images/deploy-cs-overview.png)

<span data-ttu-id="a7340-132">Microsoft 受管理的桌上型電腦建議部署至部署鈴響順序如下： 測試、 第一個、 快速且然後廣泛。</span><span class="sxs-lookup"><span data-stu-id="a7340-132">Microsoft Managed Desktop recommends deploying to deployment rings in this order: Test, First, Fast, and then Broad.</span></span> 

<span data-ttu-id="a7340-133">當每一個環內完成變更時、 狀態變更為**完成**。</span><span class="sxs-lookup"><span data-stu-id="a7340-133">When changes complete in each ring, the status changes to **Complete**.</span></span>

![完成部署可設定的設定](images/config-setting-complete.png)

## <a name="revert-deployment"></a><span data-ttu-id="a7340-135">回復部署</span><span class="sxs-lookup"><span data-stu-id="a7340-135">Revert deployment</span></span>

<span data-ttu-id="a7340-136">我們將這些指示中顯示桌面背景圖片。</span><span class="sxs-lookup"><span data-stu-id="a7340-136">We’ll show Desktop background picture in these instructions.</span></span> 

<span data-ttu-id="a7340-p103">您已部署變更後，您可以回復從**部署狀態**。當您將回復為**進行中**或**完成**的變更時，會停止目前的部署。設定還原至最後一個已部署至所有鈴響的版本。</span><span class="sxs-lookup"><span data-stu-id="a7340-p103">After you’ve deployed a change, you can revert from **Deployment status**. When you revert a change that is **In progress** or **Complete**, the current deployment stops. The setting will revert to the last version that was deployed to all rings.</span></span> 

<span data-ttu-id="a7340-140">**若要將回復變更**</span><span class="sxs-lookup"><span data-stu-id="a7340-140">**To revert a change**</span></span>
1. <span data-ttu-id="a7340-141">登入[Microsoft 受管理的桌上型電腦管理入口網站](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="a7340-141">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="a7340-142">[**設定**] 下選取 [**可設定**]。</span><span class="sxs-lookup"><span data-stu-id="a7340-142">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="a7340-143">在**部署狀態**工作區中，選取想要還原，的設定，然後選取要還原分段的部署。</span><span class="sxs-lookup"><span data-stu-id="a7340-143">In **Deployment status** workspace, select the setting you want to revert, and then select the staged deployment to revert.</span></span>
4. <span data-ttu-id="a7340-144">**必須回復此變更**，請選取 [**還原部署**。</span><span class="sxs-lookup"><span data-stu-id="a7340-144">Under **Need to revert this change**, select **Revert deployment**.</span></span>

![還原組態設定部署](images/config-setting-revert.png) 

## <a name="additional-resources"></a><span data-ttu-id="a7340-146">其他資源</span><span class="sxs-lookup"><span data-stu-id="a7340-146">Additional resources</span></span>
- [<span data-ttu-id="a7340-147">組態設定概觀 （英文)</span><span class="sxs-lookup"><span data-stu-id="a7340-147">Configurable settings overview</span></span>](config-setting-overview.md)
- [<span data-ttu-id="a7340-148">可設定的設定參考 （英文)</span><span class="sxs-lookup"><span data-stu-id="a7340-148">Configurable settings reference</span></span>](config-setting-ref.md) 