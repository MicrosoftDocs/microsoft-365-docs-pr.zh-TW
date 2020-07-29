---
title: 開始使用應用程式控制
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
ms.openlocfilehash: 431e6cb3b8d7ab7e1dd317918fab4821889c7d4e
ms.sourcegitcommit: 583fd1ac1f385c58b93bda648907a1bd8e0a1950
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/28/2020
ms.locfileid: "45430456"
---
# <a name="get-started-with-app-control"></a><span data-ttu-id="cf042-103">開始使用應用程式控制</span><span class="sxs-lookup"><span data-stu-id="cf042-103">Get started with app control</span></span>

<span data-ttu-id="cf042-104">在您的環境中啟用應用程式控制之前，請務必複查並瞭解[Microsoft 管理的桌面如何執行它](../service-description/app-control.md)和您的角色與責任。</span><span class="sxs-lookup"><span data-stu-id="cf042-104">Before you enable app control in your environment, be sure to review and understand [how Microsoft Managed Desktop implements it](../service-description/app-control.md) and your roles and responsibilities.</span></span>

<span data-ttu-id="cf042-105">Microsoft 受管理的桌面在取得安全基礎原則方面的難度更具挑戰性，以簡化應用程式控制。</span><span class="sxs-lookup"><span data-stu-id="cf042-105">Microsoft Managed Desktop simplifies app control by taking care of the more challenging aspects of getting a secure base policy.</span></span> <span data-ttu-id="cf042-106">您的 IT 管理員仍必須在測試環中測試您的應用程式，並檢查記錄檔是否有任何警告或錯誤。</span><span class="sxs-lookup"><span data-stu-id="cf042-106">Your IT Administrators must still test your apps in the Test ring and review the logs for any warnings or errors.</span></span> <span data-ttu-id="cf042-107">若應用程式需要例外，您可以將要求歸檔，或 Microsoft 受管理的桌面作業可能會根據最先偵測的人員而定。</span><span class="sxs-lookup"><span data-stu-id="cf042-107">If an app needs an exemption, you can file a request, or Microsoft Managed Desktop Operation might, depending on who detects it first.</span></span>

## <a name="initial-deployment-of-apps"></a><span data-ttu-id="cf042-108">應用程式的初始部署</span><span class="sxs-lookup"><span data-stu-id="cf042-108">Initial deployment of apps</span></span>

<span data-ttu-id="cf042-109">當您第一次部署應用程式時，Microsoft 受管理的桌面必須評估其目前的行為。</span><span class="sxs-lookup"><span data-stu-id="cf042-109">When you first deploy apps, Microsoft Managed Desktop needs to assess their current behavior.</span></span> <span data-ttu-id="cf042-110">啟用應用程式控制的確切步驟取決於您的環境中是否已部署裝置。</span><span class="sxs-lookup"><span data-stu-id="cf042-110">The exact steps for enabling app control depend on whether devices have already been deployed in your environment.</span></span>

### <a name="devices-not-yet-in-use"></a><span data-ttu-id="cf042-111">尚未使用的裝置</span><span class="sxs-lookup"><span data-stu-id="cf042-111">Devices not yet in use</span></span>

<span data-ttu-id="cf042-112">若尚未使用任何裝置，請使用 Microsoft Managed Desktop Operations 開啟服務票證，以要求我們開啟應用程式控制。</span><span class="sxs-lookup"><span data-stu-id="cf042-112">If you don't yet have any devices in use, open a service ticket with Microsoft Managed Desktop Operations requesting that we turn on app control.</span></span> <span data-ttu-id="cf042-113">作業會逐步將原則部署到遵循此排程的部署群組：</span><span class="sxs-lookup"><span data-stu-id="cf042-113">Operations will progressively deploy policies to deployment groups following this schedule:</span></span>

|<span data-ttu-id="cf042-114">部署群組</span><span class="sxs-lookup"><span data-stu-id="cf042-114">Deployment group</span></span>  |<span data-ttu-id="cf042-115">原則類型</span><span class="sxs-lookup"><span data-stu-id="cf042-115">Policy type</span></span>  |<span data-ttu-id="cf042-116">時程</span><span class="sxs-lookup"><span data-stu-id="cf042-116">Timing</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="cf042-117">測試</span><span class="sxs-lookup"><span data-stu-id="cf042-117">Test</span></span>     |  <span data-ttu-id="cf042-118">審計</span><span class="sxs-lookup"><span data-stu-id="cf042-118">Audit</span></span>       |  <span data-ttu-id="cf042-119">Day 0</span><span class="sxs-lookup"><span data-stu-id="cf042-119">Day 0</span></span>       |
|<span data-ttu-id="cf042-120">名字</span><span class="sxs-lookup"><span data-stu-id="cf042-120">First</span></span>     | <span data-ttu-id="cf042-121">Enforced</span><span class="sxs-lookup"><span data-stu-id="cf042-121">Enforced</span></span>        | <span data-ttu-id="cf042-122">第 1 天</span><span class="sxs-lookup"><span data-stu-id="cf042-122">Day 1</span></span>        |
|<span data-ttu-id="cf042-123">快速</span><span class="sxs-lookup"><span data-stu-id="cf042-123">Fast</span></span>     | <span data-ttu-id="cf042-124">Enforced</span><span class="sxs-lookup"><span data-stu-id="cf042-124">Enforced</span></span>        |  <span data-ttu-id="cf042-125">第 2 天</span><span class="sxs-lookup"><span data-stu-id="cf042-125">Day 2</span></span>       |
|<span data-ttu-id="cf042-126">廣泛</span><span class="sxs-lookup"><span data-stu-id="cf042-126">Broad</span></span>     | <span data-ttu-id="cf042-127">Enforced</span><span class="sxs-lookup"><span data-stu-id="cf042-127">Enforced</span></span>        |  <span data-ttu-id="cf042-128">第 3 天</span><span class="sxs-lookup"><span data-stu-id="cf042-128">Day 3</span></span>       |

<span data-ttu-id="cf042-129">您可以隨時開啟另一個服務要求，以在部署期間隨時暫停或回退此部署的一部分。</span><span class="sxs-lookup"><span data-stu-id="cf042-129">You can always open another service request to pause or roll back part of this deployment at any time during the rollout.</span></span>

### <a name="devices-already-in-use"></a><span data-ttu-id="cf042-130">裝置已在使用中</span><span class="sxs-lookup"><span data-stu-id="cf042-130">Devices already in use</span></span>

<span data-ttu-id="cf042-131">如果已有至少一個 Microsoft 受管理的桌面裝置正在使用中，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="cf042-131">If already have at least one Microsoft Managed Desktop device in use, follow these steps:</span></span>

1. <span data-ttu-id="cf042-132">使用 Microsoft Managed Desktop Operations 開啟服務票證，以要求我們開啟應用程式控制。</span><span class="sxs-lookup"><span data-stu-id="cf042-132">Open a service ticket with Microsoft Managed Desktop Operations requesting that we turn on app control.</span></span> <span data-ttu-id="cf042-133">作業會將[審核原則](../service-description/app-control.md#audit-policy)部署至所有裝置。</span><span class="sxs-lookup"><span data-stu-id="cf042-133">Operations will deploy an [Audit policy](../service-description/app-control.md#audit-policy) to all devices.</span></span>
2. <span data-ttu-id="cf042-134">[測試您的應用程式](../working-with-managed-desktop/work-with-app-control.md#add-a-new-app)，以查看是否有任何封鎖。</span><span class="sxs-lookup"><span data-stu-id="cf042-134">[Test your applications](../working-with-managed-desktop/work-with-app-control.md#add-a-new-app) to see if any would be blocked.</span></span> <span data-ttu-id="cf042-135">若應用程式遭到封鎖，請開啟 [[簽署者要求](../working-with-managed-desktop/work-with-app-control.md#add-or-remove-a-trusted-signer)]。</span><span class="sxs-lookup"><span data-stu-id="cf042-135">If an application would be blocked, open a [signer request](../working-with-managed-desktop/work-with-app-control.md#add-or-remove-a-trusted-signer).</span></span> 
3. <span data-ttu-id="cf042-136">當您完成測試（任何結果）時，請通知作業，注意任何擱置的簽署者要求。</span><span class="sxs-lookup"><span data-stu-id="cf042-136">Once you have completed your testing (whatever the results), notify Operations, noting any pending signer requests.</span></span> <span data-ttu-id="cf042-137">作業會逐步將原則部署到遵循此排程的部署群組：</span><span class="sxs-lookup"><span data-stu-id="cf042-137">Operations will progressively deploy policies to deployment groups following this schedule:</span></span>

|<span data-ttu-id="cf042-138">部署群組</span><span class="sxs-lookup"><span data-stu-id="cf042-138">Deployment group</span></span>  |<span data-ttu-id="cf042-139">原則類型</span><span class="sxs-lookup"><span data-stu-id="cf042-139">Policy type</span></span>  |<span data-ttu-id="cf042-140">時程</span><span class="sxs-lookup"><span data-stu-id="cf042-140">Timing</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="cf042-141">測試</span><span class="sxs-lookup"><span data-stu-id="cf042-141">Test</span></span>     |  <span data-ttu-id="cf042-142">審計</span><span class="sxs-lookup"><span data-stu-id="cf042-142">Audit</span></span>       |  <span data-ttu-id="cf042-143">Day 0</span><span class="sxs-lookup"><span data-stu-id="cf042-143">Day 0</span></span>       |
|<span data-ttu-id="cf042-144">名字</span><span class="sxs-lookup"><span data-stu-id="cf042-144">First</span></span>     | <span data-ttu-id="cf042-145">Enforced</span><span class="sxs-lookup"><span data-stu-id="cf042-145">Enforced</span></span>        | <span data-ttu-id="cf042-146">第 1 天</span><span class="sxs-lookup"><span data-stu-id="cf042-146">Day 1</span></span>        |
|<span data-ttu-id="cf042-147">快速</span><span class="sxs-lookup"><span data-stu-id="cf042-147">Fast</span></span>     | <span data-ttu-id="cf042-148">Enforced</span><span class="sxs-lookup"><span data-stu-id="cf042-148">Enforced</span></span>        |  <span data-ttu-id="cf042-149">已暫停，按要求進行推廣</span><span class="sxs-lookup"><span data-stu-id="cf042-149">Paused, rollout on request</span></span>       |
|<span data-ttu-id="cf042-150">廣泛</span><span class="sxs-lookup"><span data-stu-id="cf042-150">Broad</span></span>     | <span data-ttu-id="cf042-151">Enforced</span><span class="sxs-lookup"><span data-stu-id="cf042-151">Enforced</span></span>        |  <span data-ttu-id="cf042-152">已暫停，按要求進行推廣</span><span class="sxs-lookup"><span data-stu-id="cf042-152">Paused, rollout on request</span></span>       |

<span data-ttu-id="cf042-153">您可以隨時開啟另一個服務要求，以在部署期間隨時暫停或回退此部署的一部分。</span><span class="sxs-lookup"><span data-stu-id="cf042-153">You can always open another service request to pause or roll back part of this deployment at any time during the rollout.</span></span>



