---
title: 為 Microsoft Cloud App Security 啟用評估環境
description: 瞭解 Microsoft Defender 內 MCAS 的架構，以 Office 365 和瞭解 Microsoft 365 Defender 產品之間的互動。
keywords: Microsoft 365 Defender 試用版，請嘗試 Microsoft 365 Defender，評估 Microsoft 365 Defender，Microsoft 365 Defender 評估實驗室，Microsoft 365 Defender 試驗，網路安全性，高級持續性威脅，企業安全性，裝置，裝置，身分識別，使用者，資料，應用程式，事件，自動化調查和修正，高級搜尋
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 6ada9613f852e085158b7002cbbb9a9928d36d58
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/15/2021
ms.locfileid: "53457762"
---
# <a name="enable-the-evaluation-environment-for-microsoft-cloud-app-security"></a><span data-ttu-id="256f6-104">為 Microsoft Cloud App Security 啟用評估環境</span><span class="sxs-lookup"><span data-stu-id="256f6-104">Enable the evaluation environment for Microsoft Cloud App Security</span></span>


<span data-ttu-id="256f6-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="256f6-105">**Applies to:**</span></span>

- <span data-ttu-id="256f6-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="256f6-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="256f6-107">本文是設定 Microsoft Cloud App Security 評估環境之程式中的[步驟2之 2](eval-defender-mcas-overview.md) 。</span><span class="sxs-lookup"><span data-stu-id="256f6-107">This article is [Step 2 of 2](eval-defender-mcas-overview.md) in the process of setting up the evaluation environment for Microsoft Cloud App Security.</span></span> <span data-ttu-id="256f6-108">如需此程式的詳細資訊，請參閱 [概述文章](eval-defender-mcas-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="256f6-108">For more information about this process, see the [overview article](eval-defender-mcas-overview.md).</span></span>

<span data-ttu-id="256f6-109">本文將引導您逐步瞭解存取雲端 App 安全性入口網站及設定必要的整合，以收集雲端應用程式流量資料。</span><span class="sxs-lookup"><span data-stu-id="256f6-109">This article walks you through the process of accessing the Cloud App Security portal and configuring the necessary integration to collect cloud app traffic data.</span></span>

<span data-ttu-id="256f6-110">若要探索您環境中使用的雲端應用程式，您可以執行下列其中一項或兩項操作：</span><span class="sxs-lookup"><span data-stu-id="256f6-110">To discover cloud apps used in your environment, you can do one or both of the following:</span></span>

- <span data-ttu-id="256f6-111">與 Microsoft Defender for Endpoint 整合，透過雲端探索快速取得並執行。</span><span class="sxs-lookup"><span data-stu-id="256f6-111">Get up and running quickly with Cloud Discovery by integrating with Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="256f6-112">這種原生整合可讓您立即開始在網路上的 Windows 10 裝置之間收集雲端流量的資料。</span><span class="sxs-lookup"><span data-stu-id="256f6-112">This native integration enables you to immediately start collecting data on cloud traffic across your Windows 10 devices, on and off your network.</span></span>
- <span data-ttu-id="256f6-113">若要探索所有連接至網路之裝置存取的所有雲端應用程式，請在防火牆和其他 proxy 上部署雲端 App 安全性的記錄收集器。</span><span class="sxs-lookup"><span data-stu-id="256f6-113">To discover all cloud apps accessed by all devices connected to your network, deploy the Cloud App Security log collector on your firewalls and other proxies.</span></span> <span data-ttu-id="256f6-114">這樣會從您的端點收集資料，並將其傳送至雲端 App 安全性以進行分析。</span><span class="sxs-lookup"><span data-stu-id="256f6-114">This collects data from your endpoints and sends it to Cloud App Security for analysis.</span></span> <span data-ttu-id="256f6-115">雲端 App 安全性原本會與某些協力廠商 proxy 整合，以取得更多功能。</span><span class="sxs-lookup"><span data-stu-id="256f6-115">Cloud App Security natively integrates with some third-party proxies for even more capabilities.</span></span>

<span data-ttu-id="256f6-116">本文包含這兩種方法的指導方針。</span><span class="sxs-lookup"><span data-stu-id="256f6-116">This article includes guidance for both methods.</span></span>

<span data-ttu-id="256f6-117">使用下列步驟來設定 Microsoft Cloud App Security。</span><span class="sxs-lookup"><span data-stu-id="256f6-117">Use the following steps to set up Microsoft Cloud App Security.</span></span>

![在 microsoft Defender 評估環境中啟用 microsoft Microsoft Cloud App Security 的步驟](../../media/defender/m365-defender-mcas-eval-enable-steps.png)

- [<span data-ttu-id="256f6-119">步驟1。連線至雲端 App 安全性入口網站</span><span class="sxs-lookup"><span data-stu-id="256f6-119">Step 1. Connect to the Cloud App Security portal</span></span>](#step-1-connect-to-the-cloud-app-security-portal)
- [<span data-ttu-id="256f6-120">步驟2。與 Microsoft Defender for Endpoint 整合</span><span class="sxs-lookup"><span data-stu-id="256f6-120">Step 2. Integrate with Microsoft Defender for Endpoint</span></span>](#step-2-integrate-with-microsoft-defender-for-endpoint)
- [<span data-ttu-id="256f6-121">步驟3。在防火牆和其他 proxy 上部署雲端 App 安全性記錄收集器</span><span class="sxs-lookup"><span data-stu-id="256f6-121">Step 3. Deploy the Cloud App Security log collector on your firewalls and other proxies</span></span>](#step-3-deploy-the-cloud-app-security-log-collector-on-your-firewalls-and-other-proxies)
- [<span data-ttu-id="256f6-122">步驟4。查看雲端探索儀表板，以查看您的組織正在使用哪些應用程式</span><span class="sxs-lookup"><span data-stu-id="256f6-122">Step 4. View the Cloud Discovery dashboard to see what apps are being used in your organization</span></span>](#step-4-view-the-cloud-discovery-dashboard-to-see-what-apps-are-being-used-in-your-organization)

## <a name="step-1-connect-to-the-cloud-app-security-portal"></a><span data-ttu-id="256f6-123">步驟 1.</span><span class="sxs-lookup"><span data-stu-id="256f6-123">Step 1.</span></span> <span data-ttu-id="256f6-124">連線至雲端 App 安全性入口網站</span><span class="sxs-lookup"><span data-stu-id="256f6-124">Connect to the Cloud App Security portal</span></span>

<span data-ttu-id="256f6-125">若要驗證授權並聯機至雲端 App 安全性入口網站，請參閱[快速入門：開始使用 Microsoft Cloud App Security](/cloud-app-security/getting-started-with-cloud-app-security)。</span><span class="sxs-lookup"><span data-stu-id="256f6-125">To verify licensing and to connect to the Cloud App Security portal, see [Quickstart: Get started with Microsoft Cloud App Security](/cloud-app-security/getting-started-with-cloud-app-security).</span></span> 

<span data-ttu-id="256f6-126">如果您不能立即連線至入口網站，您可能需要將 IP 位址新增至防火牆的允許清單。</span><span class="sxs-lookup"><span data-stu-id="256f6-126">If you're not immediately able to connect to the portal, you might need to add the IP address to the allow list of your firewall.</span></span> <span data-ttu-id="256f6-127">請參閱[基本設定雲端 App 安全性](/cloud-app-security/general-setup)。</span><span class="sxs-lookup"><span data-stu-id="256f6-127">See [Basic setup for Cloud App Security](/cloud-app-security/general-setup).</span></span>

<span data-ttu-id="256f6-128">如果仍有問題，請複查 [網路需求](/cloud-app-security/network-requirements)。</span><span class="sxs-lookup"><span data-stu-id="256f6-128">If you're still having trouble, review [Network requirements](/cloud-app-security/network-requirements).</span></span>

## <a name="step-2-integrate-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="256f6-129">步驟 2.</span><span class="sxs-lookup"><span data-stu-id="256f6-129">Step 2.</span></span> <span data-ttu-id="256f6-130">與 Microsoft Defender for Endpoint 整合</span><span class="sxs-lookup"><span data-stu-id="256f6-130">Integrate with Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="256f6-131">Microsoft Cloud App Security 與 Microsoft Defender for Endpoint 本來進行整合。</span><span class="sxs-lookup"><span data-stu-id="256f6-131">Microsoft Cloud App Security integrates with Microsoft Defender for Endpoint natively.</span></span> <span data-ttu-id="256f6-132">整合可簡化 Cloud Discovery 的推出、將雲端探索功能延伸至公司網路以外，並啟用裝置型調查。</span><span class="sxs-lookup"><span data-stu-id="256f6-132">The integration simplifies roll out of Cloud Discovery, extends Cloud Discovery capabilities beyond your corporate network, and enables device-based investigation.</span></span> <span data-ttu-id="256f6-133">這種整合會顯示從 IT 管理的 Windows 10 裝置存取的雲端應用程式和服務。</span><span class="sxs-lookup"><span data-stu-id="256f6-133">This integration reveals cloud apps and services being accessed from IT-managed Windows 10 devices.</span></span> 

<span data-ttu-id="256f6-134">如果您已設定 Microsoft Defender for Endpoint，設定與雲端 App 安全性的整合是 Microsoft 365 Defender 中的切換。</span><span class="sxs-lookup"><span data-stu-id="256f6-134">If you've already set up Microsoft Defender for Endpoint, configuring integration with Cloud App Security is a toggle in Microsoft 365 Defender.</span></span> <span data-ttu-id="256f6-135">整合開啟之後，您可以回到雲端 App 安全性入口網站，並在雲端探索儀表板中查看豐富的資料。</span><span class="sxs-lookup"><span data-stu-id="256f6-135">After integration is turned on, you can return to the Cloud App Security portal and view rich data in the Cloud Discovery Dashboard.</span></span>

<span data-ttu-id="256f6-136">若要完成這些工作，請參閱[Microsoft Defender For Endpoint integration with Microsoft Cloud App Security](/cloud-app-security/mde-integration)。</span><span class="sxs-lookup"><span data-stu-id="256f6-136">To accomplish these tasks, see [Microsoft Defender for Endpoint integration with Microsoft Cloud App Security](/cloud-app-security/mde-integration).</span></span> 

## <a name="step-3-deploy-the-cloud-app-security-log-collector-on-your-firewalls-and-other-proxies"></a><span data-ttu-id="256f6-137">步驟 3.</span><span class="sxs-lookup"><span data-stu-id="256f6-137">Step 3.</span></span> <span data-ttu-id="256f6-138">在防火牆和其他 proxy 上部署雲端 App 安全性記錄收集器</span><span class="sxs-lookup"><span data-stu-id="256f6-138">Deploy the Cloud App Security log collector on your firewalls and other proxies</span></span>

<span data-ttu-id="256f6-139">若要在連接至網路的所有裝置上進行覆蓋率，請在防火牆和其他 proxy 上部署雲端 App 安全性的記錄收集器，以從端點收集資料，並將資料傳送至雲端 App 安全性進行分析。</span><span class="sxs-lookup"><span data-stu-id="256f6-139">For coverage on all devices connected to your network, deploy the Cloud App Security log collector on your firewalls and other proxies to collect data from your endpoints and send it to Cloud App Security for analysis.</span></span> 

<span data-ttu-id="256f6-140">如果您使用下列其中一個安全網頁閘道 (SWG) ，雲端 App 安全性可提供無縫的部署和整合：</span><span class="sxs-lookup"><span data-stu-id="256f6-140">If you're using one of the following Secure Web Gateways (SWG), Cloud App Security provides seamless deployment and integration:</span></span>
- <span data-ttu-id="256f6-141">Zscaler</span><span class="sxs-lookup"><span data-stu-id="256f6-141">Zscaler</span></span>
- <span data-ttu-id="256f6-142">iboss</span><span class="sxs-lookup"><span data-stu-id="256f6-142">iboss</span></span>
- <span data-ttu-id="256f6-143">Corrata</span><span class="sxs-lookup"><span data-stu-id="256f6-143">Corrata</span></span>
- <span data-ttu-id="256f6-144">Menlo 安全性</span><span class="sxs-lookup"><span data-stu-id="256f6-144">Menlo Security</span></span>

<span data-ttu-id="256f6-145">如需整合這些網路裝置的詳細資訊，請參閱 [設定雲端探索](/cloud-app-security/set-up-cloud-discovery)。</span><span class="sxs-lookup"><span data-stu-id="256f6-145">For more information on integrating with these network devices, see [Set up Cloud Discovery](/cloud-app-security/set-up-cloud-discovery).</span></span> 
## <a name="step-4-view-the-cloud-discovery-dashboard-to-see-what-apps-are-being-used-in-your-organization"></a><span data-ttu-id="256f6-146">步驟 4：</span><span class="sxs-lookup"><span data-stu-id="256f6-146">Step 4.</span></span> <span data-ttu-id="256f6-147">查看雲端探索儀表板，以查看您的組織正在使用哪些應用程式</span><span class="sxs-lookup"><span data-stu-id="256f6-147">View the Cloud Discovery dashboard to see what apps are being used in your organization</span></span>

<span data-ttu-id="256f6-148">雲端探索儀表板的設計可讓您深入瞭解組織中的雲端應用程式的使用方式。</span><span class="sxs-lookup"><span data-stu-id="256f6-148">The Cloud Discovery dashboard is designed to give you more insight into how cloud apps are being used in your organization.</span></span> <span data-ttu-id="256f6-149">它會深入瞭解使用哪些類型的應用程式、開啟的警示，以及組織中應用程式的風險層級。</span><span class="sxs-lookup"><span data-stu-id="256f6-149">It provides an at-a-glance overview of what kinds of apps are being used, your open alerts, and the risk levels of apps in your organization.</span></span> 

<span data-ttu-id="256f6-150">若要開始使用雲端探索儀表板，請參閱使用已 [探索的應用程式](/cloud-app-security/discovered-apps)。</span><span class="sxs-lookup"><span data-stu-id="256f6-150">To get started using the Cloud Discovery dashboard, see [Working with discovered apps](/cloud-app-security/discovered-apps).</span></span>

## <a name="next-steps"></a><span data-ttu-id="256f6-151">後續步驟</span><span class="sxs-lookup"><span data-stu-id="256f6-151">Next steps</span></span>

<span data-ttu-id="256f6-152">步驟3之3：[試驗 Microsoft Cloud App Security](eval-defender-mcas-pilot.md)</span><span class="sxs-lookup"><span data-stu-id="256f6-152">Step 3 of 3: [Pilot Microsoft Cloud App Security](eval-defender-mcas-pilot.md)</span></span>

<span data-ttu-id="256f6-153">回到 [[評估 Microsoft Cloud App Security](eval-defender-mcas-overview.md)的總覽</span><span class="sxs-lookup"><span data-stu-id="256f6-153">Return to the overview for [Evaluate Microsoft Cloud App Security](eval-defender-mcas-overview.md)</span></span>

<span data-ttu-id="256f6-154">回到[評估與試驗 Microsoft 365 Defender](eval-overview.md)概述</span><span class="sxs-lookup"><span data-stu-id="256f6-154">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>