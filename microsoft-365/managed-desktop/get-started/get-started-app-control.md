---
title: 快速入門應用程式控制
description: ''
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 12df7b074019ea47f2e293b71c6b0b25fe46f66f
ms.sourcegitcommit: 63887d742c59cc660fc85537b335e98a9dc66fbe
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/18/2020
ms.locfileid: "45170686"
---
# <a name="get-started-with-app-control"></a><span data-ttu-id="a1b3b-103">快速入門應用程式控制</span><span class="sxs-lookup"><span data-stu-id="a1b3b-103">Get started with app control</span></span>

<span data-ttu-id="a1b3b-104">在您的環境中啟用應用程式控制之前，請務必複查並瞭解[Microsoft 管理的桌面如何執行它](../service-description/app-control.md)和您的角色與責任。</span><span class="sxs-lookup"><span data-stu-id="a1b3b-104">Before you enable app control in your environment, be sure to review and understand [how Microsoft Managed Desktop implements it](../service-description/app-control.md) and your roles and responsibilities.</span></span>

<span data-ttu-id="a1b3b-105">Microsoft 受管理的桌面在取得安全基礎原則方面的難度更具挑戰性，以簡化應用程式控制。</span><span class="sxs-lookup"><span data-stu-id="a1b3b-105">Microsoft Managed Desktop simplifies app control by taking care of the more challenging aspects of getting a secure base policy.</span></span> <span data-ttu-id="a1b3b-106">您的 IT 管理員仍必須在測試環中測試您的應用程式，並檢查記錄檔是否有任何警告或錯誤。</span><span class="sxs-lookup"><span data-stu-id="a1b3b-106">Your IT Administrators must still test your apps in the Test ring and review the logs for any warnings or errors.</span></span> <span data-ttu-id="a1b3b-107">若應用程式需要例外，您可以將要求歸檔，或 Microsoft 受管理的桌面作業可能會根據最先偵測的人員而定。</span><span class="sxs-lookup"><span data-stu-id="a1b3b-107">If an app needs an exemption, you can file a request, or Microsoft Managed Desktop Operation might, depending on who detects it first.</span></span>

## <a name="initial-deployment-of-apps"></a><span data-ttu-id="a1b3b-108">應用程式的初始部署</span><span class="sxs-lookup"><span data-stu-id="a1b3b-108">Initial deployment of apps</span></span>

<span data-ttu-id="a1b3b-109">當您第一次部署應用程式時，Microsoft 受管理的桌面必須評估其目前的行為。</span><span class="sxs-lookup"><span data-stu-id="a1b3b-109">When you first deploy apps, Microsoft Managed Desktop needs to assess their current behavior.</span></span> <span data-ttu-id="a1b3b-110">啟用應用程式控制的確切步驟取決於您的環境中是否已部署裝置。</span><span class="sxs-lookup"><span data-stu-id="a1b3b-110">The exact steps for enabling app control depend on whether devices have already been deployed in your environment.</span></span>

### <a name="devices-already-in-use"></a><span data-ttu-id="a1b3b-111">裝置已在使用中</span><span class="sxs-lookup"><span data-stu-id="a1b3b-111">Devices already in use</span></span>

<span data-ttu-id="a1b3b-112">如果已有至少一個 Microsoft 受管理的桌面裝置正在使用中，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="a1b3b-112">If already have at least one Microsoft Managed Desktop device in use, follow these steps:</span></span>

1. <span data-ttu-id="a1b3b-113">使用 Microsoft Managed Desktop Operations 開啟服務票證，以要求我們開啟應用程式控制。</span><span class="sxs-lookup"><span data-stu-id="a1b3b-113">Open a service ticket with Microsoft Managed Desktop Operations requesting that we turn on app control.</span></span> <span data-ttu-id="a1b3b-114">作業會將[審核原則](../service-description/app-control.md#audit-policy)部署至所有裝置。</span><span class="sxs-lookup"><span data-stu-id="a1b3b-114">Operations will deploy an [Audit policy](../service-description/app-control.md#audit-policy) to all devices.</span></span>
2. <span data-ttu-id="a1b3b-115">[測試您的應用程式](../working-with-managed-desktop/work-with-app-control.md#add-a-new-app)，以查看是否有任何封鎖。</span><span class="sxs-lookup"><span data-stu-id="a1b3b-115">[Test your applications](../working-with-managed-desktop/work-with-app-control.md#add-a-new-app) to see if any would be blocked.</span></span> <span data-ttu-id="a1b3b-116">若應用程式遭到封鎖，請開啟 [[簽署者要求](../working-with-managed-desktop/work-with-app-control.md#add-or-remove-a-trusted-signer)]。</span><span class="sxs-lookup"><span data-stu-id="a1b3b-116">If an application would be blocked, open a [signer request](../working-with-managed-desktop/work-with-app-control.md#add-or-remove-a-trusted-signer).</span></span> 
3. <span data-ttu-id="a1b3b-117">當您完成測試（任何結果）時，請通知作業，注意任何擱置的簽署者要求。</span><span class="sxs-lookup"><span data-stu-id="a1b3b-117">Once you have completed your testing (whatever the results), notify Operations, noting any pending signer requests.</span></span> <span data-ttu-id="a1b3b-118">作業會逐步將原則部署到遵循此排程的部署群組：</span><span class="sxs-lookup"><span data-stu-id="a1b3b-118">Operations will progressively deploy policies to deployment groups following this schedule:</span></span>

|<span data-ttu-id="a1b3b-119">部署群組</span><span class="sxs-lookup"><span data-stu-id="a1b3b-119">Deployment group</span></span>  |<span data-ttu-id="a1b3b-120">原則類型</span><span class="sxs-lookup"><span data-stu-id="a1b3b-120">Policy type</span></span>  |<span data-ttu-id="a1b3b-121">時程</span><span class="sxs-lookup"><span data-stu-id="a1b3b-121">Timing</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="a1b3b-122">測試</span><span class="sxs-lookup"><span data-stu-id="a1b3b-122">Test</span></span>     |  <span data-ttu-id="a1b3b-123">審計</span><span class="sxs-lookup"><span data-stu-id="a1b3b-123">Audit</span></span>       |  <span data-ttu-id="a1b3b-124">Day 0</span><span class="sxs-lookup"><span data-stu-id="a1b3b-124">Day 0</span></span>       |
|<span data-ttu-id="a1b3b-125">名字</span><span class="sxs-lookup"><span data-stu-id="a1b3b-125">First</span></span>     | <span data-ttu-id="a1b3b-126">Enforced</span><span class="sxs-lookup"><span data-stu-id="a1b3b-126">Enforced</span></span>        | <span data-ttu-id="a1b3b-127">第 1 天</span><span class="sxs-lookup"><span data-stu-id="a1b3b-127">Day 1</span></span>        |
|<span data-ttu-id="a1b3b-128">快速</span><span class="sxs-lookup"><span data-stu-id="a1b3b-128">Fast</span></span>     | <span data-ttu-id="a1b3b-129">Enforced</span><span class="sxs-lookup"><span data-stu-id="a1b3b-129">Enforced</span></span>        |  <span data-ttu-id="a1b3b-130">第 3 天</span><span class="sxs-lookup"><span data-stu-id="a1b3b-130">Day 3</span></span>       |
|<span data-ttu-id="a1b3b-131">廣泛</span><span class="sxs-lookup"><span data-stu-id="a1b3b-131">Broad</span></span>     | <span data-ttu-id="a1b3b-132">Enforced</span><span class="sxs-lookup"><span data-stu-id="a1b3b-132">Enforced</span></span>        |  <span data-ttu-id="a1b3b-133">第 7 天</span><span class="sxs-lookup"><span data-stu-id="a1b3b-133">Day 7</span></span>       |

<span data-ttu-id="a1b3b-134">您可以隨時開啟另一個服務要求，以在部署期間隨時暫停或回退此部署的一部分。</span><span class="sxs-lookup"><span data-stu-id="a1b3b-134">You can always open another service request to pause or roll back part of this deployment at any time during the rollout.</span></span>

### <a name="devices-not-yet-in-use"></a><span data-ttu-id="a1b3b-135">尚未使用的裝置</span><span class="sxs-lookup"><span data-stu-id="a1b3b-135">Devices not yet in use</span></span>

<span data-ttu-id="a1b3b-136">若尚未使用任何裝置，請使用 Microsoft Managed Desktop Operations 開啟服務票證，以要求我們開啟應用程式控制。</span><span class="sxs-lookup"><span data-stu-id="a1b3b-136">If you don't yet have any devices in use, open a service ticket with Microsoft Managed Desktop Operations requesting that we turn on app control.</span></span> <span data-ttu-id="a1b3b-137">作業會逐步將原則部署到遵循此排程的部署群組：</span><span class="sxs-lookup"><span data-stu-id="a1b3b-137">Operations will progressively deploy policies to deployment groups following this schedule:</span></span>

|<span data-ttu-id="a1b3b-138">部署群組</span><span class="sxs-lookup"><span data-stu-id="a1b3b-138">Deployment group</span></span>  |<span data-ttu-id="a1b3b-139">原則類型</span><span class="sxs-lookup"><span data-stu-id="a1b3b-139">Policy type</span></span>  |<span data-ttu-id="a1b3b-140">時程</span><span class="sxs-lookup"><span data-stu-id="a1b3b-140">Timing</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="a1b3b-141">測試</span><span class="sxs-lookup"><span data-stu-id="a1b3b-141">Test</span></span>     |  <span data-ttu-id="a1b3b-142">審計</span><span class="sxs-lookup"><span data-stu-id="a1b3b-142">Audit</span></span>       |  <span data-ttu-id="a1b3b-143">Day 0</span><span class="sxs-lookup"><span data-stu-id="a1b3b-143">Day 0</span></span>       |
|<span data-ttu-id="a1b3b-144">名字</span><span class="sxs-lookup"><span data-stu-id="a1b3b-144">First</span></span>     | <span data-ttu-id="a1b3b-145">Enforced</span><span class="sxs-lookup"><span data-stu-id="a1b3b-145">Enforced</span></span>        | <span data-ttu-id="a1b3b-146">第 1 天</span><span class="sxs-lookup"><span data-stu-id="a1b3b-146">Day 1</span></span>        |
|<span data-ttu-id="a1b3b-147">快速</span><span class="sxs-lookup"><span data-stu-id="a1b3b-147">Fast</span></span>     | <span data-ttu-id="a1b3b-148">Enforced</span><span class="sxs-lookup"><span data-stu-id="a1b3b-148">Enforced</span></span>        |  <span data-ttu-id="a1b3b-149">第 3 天</span><span class="sxs-lookup"><span data-stu-id="a1b3b-149">Day 3</span></span>       |
|<span data-ttu-id="a1b3b-150">廣泛</span><span class="sxs-lookup"><span data-stu-id="a1b3b-150">Broad</span></span>     | <span data-ttu-id="a1b3b-151">Enforced</span><span class="sxs-lookup"><span data-stu-id="a1b3b-151">Enforced</span></span>        |  <span data-ttu-id="a1b3b-152">第 7 天</span><span class="sxs-lookup"><span data-stu-id="a1b3b-152">Day 7</span></span>       |

<span data-ttu-id="a1b3b-153">您可以隨時開啟另一個服務要求，以在部署期間隨時暫停或回退此部署的一部分。</span><span class="sxs-lookup"><span data-stu-id="a1b3b-153">You can always open another service request to pause or roll back part of this deployment at any time during the rollout.</span></span>

