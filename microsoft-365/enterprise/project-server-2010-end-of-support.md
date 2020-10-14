---
title: Project Server 2010 終止支援藍圖
ms.author: efrene
author: efrene
manager: pamg
ms.date: 04/14/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: IT_ProjectAdmin
search.appverid:
- MET150
- ZPJ120
- PJU120
- PJW120
description: Project Server 2010 的支援結束于4月13日（2021）。 使用本文做為升級至 Project Online 或更新版本 Project Server 內部部署的指南。
ms.openlocfilehash: 2cf18c5e91c095c92230a33f1b8a19fa26840777
ms.sourcegitcommit: bcb88a6171f9e7bdb5b2d8c03cd628d11c5e7bbf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/14/2020
ms.locfileid: "48464321"
---
# <a name="project-server-2010-end-of-support-roadmap"></a><span data-ttu-id="014f9-104">Project Server 2010 終止支援藍圖</span><span class="sxs-lookup"><span data-stu-id="014f9-104">Project Server 2010 end of support roadmap</span></span>

<span data-ttu-id="014f9-105">*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="014f9-105">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="014f9-106">Project Server 2010 將于 **年4月 13 2021 日**到達支援終止。</span><span class="sxs-lookup"><span data-stu-id="014f9-106">Project Server 2010 will reach end of support on **April 13, 2021**.</span></span> <span data-ttu-id="014f9-107">此日期已從去年10月 13 2020 日的支援日期延伸。</span><span class="sxs-lookup"><span data-stu-id="014f9-107">This date has been extended from the previous end of support date of October 13, 2020.</span></span> <span data-ttu-id="014f9-108">如果您目前使用的是 Project Server 2010，請注意，這些其他相關產品的支援日期會有下列各項：</span><span class="sxs-lookup"><span data-stu-id="014f9-108">If you are currently using Project Server 2010, note that these other related products have the following end of support dates:</span></span>

|<span data-ttu-id="014f9-109">產品</span><span class="sxs-lookup"><span data-stu-id="014f9-109">Product</span></span> |<span data-ttu-id="014f9-110">支援日期結束</span><span class="sxs-lookup"><span data-stu-id="014f9-110">End of support date</span></span>|
|---|---|
|<span data-ttu-id="014f9-111">Project 2010 Standard</span><span class="sxs-lookup"><span data-stu-id="014f9-111">Project 2010 Standard</span></span>|<span data-ttu-id="014f9-112">2020 年 10 月 13 日</span><span class="sxs-lookup"><span data-stu-id="014f9-112">October 13, 2020</span></span>|
|<span data-ttu-id="014f9-113">Project 2010 專業版</span><span class="sxs-lookup"><span data-stu-id="014f9-113">Project 2010 Professional</span></span>|<span data-ttu-id="014f9-114">2020 年 10 月 13 日</span><span class="sxs-lookup"><span data-stu-id="014f9-114">October 13, 2020</span></span>|

<span data-ttu-id="014f9-115">如需適用于 Office 2010 伺服器的詳細資訊，請參閱 [升級至 office 2010 伺服器和用戶端產品](plan-upgrade-previous-versions-office.md)。</span><span class="sxs-lookup"><span data-stu-id="014f9-115">For more information about Office 2010 servers reaching end of support, see [Upgrade from Office 2010 servers and client products](plan-upgrade-previous-versions-office.md).</span></span>

## <a name="what-does-end-of-support-mean"></a><span data-ttu-id="014f9-116">終止支援是什麼意思？</span><span class="sxs-lookup"><span data-stu-id="014f9-116">What does end of support mean?</span></span>

<span data-ttu-id="014f9-117">Project Server 與幾乎所有的 Microsoft 產品一樣，都有一個支援週期，我們提供了新功能、錯誤修正及安全性更新。</span><span class="sxs-lookup"><span data-stu-id="014f9-117">Project Server, like almost all Microsoft products, has a support lifecycle during which we provide new features, bug fixes, and security updates.</span></span> <span data-ttu-id="014f9-118">產品的生命週期從首次發行日期算起，通常會持續 10 年，而這個生命週期的結束就稱為產品支援結束。</span><span class="sxs-lookup"><span data-stu-id="014f9-118">This lifecycle typically lasts for 10 years from the date of the product's initial release, and the end of this lifecycle is known as the product's end of support.</span></span> <span data-ttu-id="014f9-119">當 Project Server 2010 達到其在2021年4月13日的支援時，Microsoft 將無法再提供：</span><span class="sxs-lookup"><span data-stu-id="014f9-119">When Project Server 2010 reaches its end of support on April 13, 2021, Microsoft will no longer provide:</span></span>

- <span data-ttu-id="014f9-120">可能發生問題的技術支援。</span><span class="sxs-lookup"><span data-stu-id="014f9-120">Technical support for problems that may occur.</span></span>

- <span data-ttu-id="014f9-121">針對所探索之問題的錯誤修正，而且可能會影響伺服器的穩定性和可用性。</span><span class="sxs-lookup"><span data-stu-id="014f9-121">Bug fixes for issues that are discovered and that may impact the stability and usability of the server.</span></span>

- <span data-ttu-id="014f9-122">已發現之弱點的安全性修正程式，可能會導致伺服器遭受安全性破壞。</span><span class="sxs-lookup"><span data-stu-id="014f9-122">Security fixes for vulnerabilities that are discovered and that may make the server vulnerable to security breaches.</span></span>

- <span data-ttu-id="014f9-123">時區更新。</span><span class="sxs-lookup"><span data-stu-id="014f9-123">Time zone updates.</span></span>

<span data-ttu-id="014f9-124">在此日期之後，Project Server 2010 的安裝會繼續執行。</span><span class="sxs-lookup"><span data-stu-id="014f9-124">Your installation of Project Server 2010 will continue to run after this date.</span></span> <span data-ttu-id="014f9-125">不過，由於以上所列的變更，強烈建議您儘早從 Project Server 2010 進行遷移。</span><span class="sxs-lookup"><span data-stu-id="014f9-125">However, because of the changes listed above, we strongly recommend that you migrate from Project Server 2010 as soon as possible.</span></span>

## <a name="what-are-my-options"></a><span data-ttu-id="014f9-126">我有哪些選擇？</span><span class="sxs-lookup"><span data-stu-id="014f9-126">What are my options?</span></span>

<span data-ttu-id="014f9-127">如果您使用的是 Project Server 2010，您必須探索遷移選項，其中包括：</span><span class="sxs-lookup"><span data-stu-id="014f9-127">If you are using Project Server 2010, you need to explore your migration options, which are:</span></span>

- <span data-ttu-id="014f9-128">遷移至 Project Online</span><span class="sxs-lookup"><span data-stu-id="014f9-128">Migrate to Project Online</span></span>

- <span data-ttu-id="014f9-129">遷移至較新的內部部署版本的 Project Server (最好的 Project Server 2019) 。</span><span class="sxs-lookup"><span data-stu-id="014f9-129">Migrate to a newer on-premises version of Project Server (preferably Project Server 2019).</span></span>

<span data-ttu-id="014f9-130">以下是您可以採取的兩種途徑，以避免 Project Server 2010 的支援結束。</span><span class="sxs-lookup"><span data-stu-id="014f9-130">Here are the two paths you can take to avoid the end of support for Project Server 2010.</span></span>

![Project Server 2010 升級路徑](../media/project-server-2010-end-of-support/project-server-2010-end-of-support-timeline.png)

|<span data-ttu-id="014f9-132">為什麼我想要遷移至 Project Server 2019？</span><span class="sxs-lookup"><span data-stu-id="014f9-132">Why would I prefer to migrate to Project Server 2019?</span></span>|<span data-ttu-id="014f9-133">為什麼我想要遷移至 Project Online？</span><span class="sxs-lookup"><span data-stu-id="014f9-133">Why would I prefer to migrate to Project Online?</span></span>|
|---|---|
|<span data-ttu-id="014f9-134">商務規則限制我在雲端中運作我的公司。</span><span class="sxs-lookup"><span data-stu-id="014f9-134">Business rules restrict me from operating my business in the cloud.</span></span>  <br/>  <span data-ttu-id="014f9-135">我需要控制環境的更新。</span><span class="sxs-lookup"><span data-stu-id="014f9-135">I need control of updates to my environment.</span></span>|<span data-ttu-id="014f9-136">我有行動電話或遠端使用者。</span><span class="sxs-lookup"><span data-stu-id="014f9-136">I have mobile or remote users.</span></span>  <br/>  <span data-ttu-id="014f9-137">遷移內部部署伺服器所需的成本是一個很重要的問題 (硬體、軟體、時間與工作的實施，等等 ) 。</span><span class="sxs-lookup"><span data-stu-id="014f9-137">Costs to migrate on-premises servers are a big concern (hardware, software, hours and effort to implement, etc.).</span></span>  <br/>  <span data-ttu-id="014f9-138">遷移後，維護環境所需的成本是一個很重要的問題 (例如，自動更新、保證的時間，等等 ) 。</span><span class="sxs-lookup"><span data-stu-id="014f9-138">After migration, costs to maintain my environment are a big concern (for example, automatic updates, guaranteed uptime, etc.).</span></span>|

> [!NOTE]
> <span data-ttu-id="014f9-139">如需從您的 Office 2010 伺服器移動選項的詳細資訊，請參閱 [協助您從 office 2010 伺服器及用戶端升級的資源](upgrade-from-office-2010-servers-and-products.md)。</span><span class="sxs-lookup"><span data-stu-id="014f9-139">For more information about options for moving from your Office 2010 servers, see [Resources to help you upgrade from Office 2010 servers and clients](upgrade-from-office-2010-servers-and-products.md).</span></span> <span data-ttu-id="014f9-140">請注意，Project Server 不支援混合式設定，因為 Project Server 和 Project Online 無法共用相同的資源集區。</span><span class="sxs-lookup"><span data-stu-id="014f9-140">Note that Project Server does not support a hybrid configuration since Project Server and Project Online cannot share the same resource pool.</span></span>

### <a name="what-are-my-options-for-project-client"></a><span data-ttu-id="014f9-141">我的 Project 用戶端選項為何？</span><span class="sxs-lookup"><span data-stu-id="014f9-141">What are my options for Project client?</span></span>

<span data-ttu-id="014f9-142">如果您使用的是 Project Professional 2010 或 Project Standard 2010，且想要探索您的遷移選項，您可以選擇下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="014f9-142">If you are using Project Professional 2010 or Project Standard 2010 and want to explore your migration options, you have the choice of:</span></span>

- <span data-ttu-id="014f9-143">移至較新版本的 Project Professional 或 Project Standard。</span><span class="sxs-lookup"><span data-stu-id="014f9-143">Moving to a newer version of Project Professional or Project Standard.</span></span>
- <span data-ttu-id="014f9-144">移至線上方案，例如 Project Online 或 Web 專案。</span><span class="sxs-lookup"><span data-stu-id="014f9-144">Moving to an online solution such as Project Online or Project for the web.</span></span>

#### <a name="moving-to-a-newer-version-of-project-client"></a><span data-ttu-id="014f9-145">移至較新版本的 Project 用戶端</span><span class="sxs-lookup"><span data-stu-id="014f9-145">Moving to a newer version of Project client</span></span>

<span data-ttu-id="014f9-146">如果您是從 Project Standard 2010 遷移，您可以將專案 standard 2016 或 Project standard 2019) 的更新版本遷移至新的版本 (。</span><span class="sxs-lookup"><span data-stu-id="014f9-146">If you are migrating from Project Standard 2010, you can migrate to a newer version of Project Standard (Project Standard 2016 or Project Standard 2019).</span></span>  <span data-ttu-id="014f9-147">建議您移至最新的版本，以充分利用最新的功能。</span><span class="sxs-lookup"><span data-stu-id="014f9-147">We recommend moving to the newest version to take advantage of the latest features and functionality.</span></span> <span data-ttu-id="014f9-148">此外，遷移至最新的版本 (Project Standard 2016) 表示您必須儘早從這個版本開始遷移，因為它的支援日期會隨之結束。</span><span class="sxs-lookup"><span data-stu-id="014f9-148">Also, migrating to a less current version (Project Standard 2016) means that you will need to migrate from this version sooner as its end of support date comes up.</span></span>

<span data-ttu-id="014f9-149">同樣地，如果您要從 Project Professional 2010 進行遷移，您可以選擇將版本遷移至較新的版本 (Project Professional 2019 或 Project Professional 2016) 。</span><span class="sxs-lookup"><span data-stu-id="014f9-149">Similarly, if you are migrating from Project Professional 2010, you can choose to migrate to a newer version (Project Professional 2019 or Project Professional 2016).</span></span> <span data-ttu-id="014f9-150">建議您盡可能移至最新版本。</span><span class="sxs-lookup"><span data-stu-id="014f9-150">We recommend moving to the newest version if possible.</span></span>  <span data-ttu-id="014f9-151">如果您使用 Project Professional 來連線至 Project Server，請確定您已遷移至 Project Professional 的版本，該版本支援與您所用之 Project Server 版本連線。</span><span class="sxs-lookup"><span data-stu-id="014f9-151">If you are using Project Professional to connect to Project Server, make sure that you migrate to a version of Project Professional that is supported to connect with the version of Project Server that you are using.</span></span>

<span data-ttu-id="014f9-152">Project Professional 2010 使用者也可以選擇將遷移至 Project Online 桌面用戶端。</span><span class="sxs-lookup"><span data-stu-id="014f9-152">Project Professional 2010 users can also choose to migrate to the Project Online Desktop client.</span></span> <span data-ttu-id="014f9-153">它是訂閱型版本的 Project Professional 2019，並包含在專案方案3和專案方案5訂閱中。</span><span class="sxs-lookup"><span data-stu-id="014f9-153">It is a subscription-based version of Project Professional 2019, and is included in Project Plan 3 and Project Plan 5 subscriptions.</span></span>

#### <a name="moving-to-an-online-solution"></a><span data-ttu-id="014f9-154">移至線上方案</span><span class="sxs-lookup"><span data-stu-id="014f9-154">Moving to an online solution</span></span>

<span data-ttu-id="014f9-155">您也可以選擇從 Project Professional 2010 或 Project Standard 2010 遷移至專案的訂閱型線上解決方案。</span><span class="sxs-lookup"><span data-stu-id="014f9-155">You can also choose to migrate from Project Professional 2010 or Project Standard 2010 to Project's subscription-based online solutions.</span></span> <span data-ttu-id="014f9-156">這兩個專案方案3和方案5都包括 Project Online 及最新的雲端方案（ [適用于 web](https://support.office.com/article/what-can-you-do-with-project-for-the-web-b30f5442-be5f-43d2-9072-c95bff778ea1)）。</span><span class="sxs-lookup"><span data-stu-id="014f9-156">Both Project Plan 3 and Plan 5 include Project Online and the latest cloud offering, [Project for the web](https://support.office.com/article/what-can-you-do-with-project-for-the-web-b30f5442-be5f-43d2-9072-c95bff778ea1).</span></span> <span data-ttu-id="014f9-157">這兩者都提供許多新的功能和優點。</span><span class="sxs-lookup"><span data-stu-id="014f9-157">Both offer a number of new features and benefits that are worth exploring.</span></span>

<span data-ttu-id="014f9-158">如需兩者中所包含之功能的詳細資訊，以及其所包含的專案計劃授權，請參閱 [Microsoft Project service 描述](https://docs.microsoft.com/office365/servicedescriptions/project-online-service-description/project-online-service-description)。</span><span class="sxs-lookup"><span data-stu-id="014f9-158">For more information about features included in both, as well as Project Plan licenses they are included in, see the [Microsoft Project service description](https://docs.microsoft.com/office365/servicedescriptions/project-online-service-description/project-online-service-description).</span></span>

## <a name="important-considerations-you-need-to-make-when-planning-to-migrate-from-project-server-2010"></a><span data-ttu-id="014f9-159">規劃從 Project Server 2010 進行遷移時，所需注意的事項</span><span class="sxs-lookup"><span data-stu-id="014f9-159">Important considerations you need to make when planning to migrate from Project Server 2010</span></span>

<span data-ttu-id="014f9-160">當您規劃從 Project Server 2010 遷移時，您必須考慮下列事項：</span><span class="sxs-lookup"><span data-stu-id="014f9-160">You need to consider the following when planning to migrate from Project Server 2010:</span></span>

- <span data-ttu-id="014f9-161">**從 Microsoft 解決方案供應商取得協助** -從 Project Server 2010 升級可能是一項挑戰，需要進行大量的準備與規劃。</span><span class="sxs-lookup"><span data-stu-id="014f9-161">**Get help from a Microsoft solution provider** - Upgrading from Project Server 2010 can be a challenge and requires much preparation and planning.</span></span> <span data-ttu-id="014f9-162">如果您不是最初安裝及設定 Project Server 2010 的方式，可能特別有挑戰性。</span><span class="sxs-lookup"><span data-stu-id="014f9-162">It can be especially challenging if you were not the one to setup and configure Project Server 2010 originally.</span></span> <span data-ttu-id="014f9-163">值得慶倖的是，您可以將 Microsoft 解決方案供應商變成誰在生活中執行這項作業，不論您計畫要遷移至 Project Server 2019 或 Project Online。</span><span class="sxs-lookup"><span data-stu-id="014f9-163">Luckily, there are Microsoft solution providers you can turn to who do this for a living, whether you plan on migrating to Project Server 2019 or to Project Online.</span></span> <span data-ttu-id="014f9-164">您可以搜尋 Microsoft 解決方案供應商，協助您在 [microsoft 解決方案供應商中心](https://go.microsoft.com/fwlink/p/?linkid=841249)進行遷移。</span><span class="sxs-lookup"><span data-stu-id="014f9-164">You can search for a Microsoft solution provider to help with your migration on the [Microsoft solution provider center](https://go.microsoft.com/fwlink/p/?linkid=841249).</span></span>

- <span data-ttu-id="014f9-165">**規劃自訂** -請注意，遷移至 project server 2019 或 project Online 時，許多您在 Project server 2010 環境中所使用的自訂功能可能無法運作。</span><span class="sxs-lookup"><span data-stu-id="014f9-165">**Plan for your customizations** - Be aware that many of the customizations you have working in your Project Server 2010 environment might not work when migrating to Project Server 2019 or to Project Online.</span></span> <span data-ttu-id="014f9-166">在不同版本之間的 Project Server 架構，以及支援的作業系統、資料庫伺服器及用戶端網頁瀏覽器之間，都有很大的差異，可與更新的版本搭配使用。</span><span class="sxs-lookup"><span data-stu-id="014f9-166">There are big differences in Project Server architecture between versions, as well as the required operating systems, database servers, and client web browsers that are supported to work with the newer version.</span></span> <span data-ttu-id="014f9-167">針對您在新環境中所需的自訂進行測試或重建的計畫。</span><span class="sxs-lookup"><span data-stu-id="014f9-167">Have a plan in place on how to test or rebuild your customizations as needed in your new environment.</span></span> <span data-ttu-id="014f9-168">規劃升級也是一種很好的機會，可在您向前推進時，確認是否真的需要特定的自訂專案。</span><span class="sxs-lookup"><span data-stu-id="014f9-168">Planning for your upgrade will also be a good opportunity to verify if a specific customization is really needed as you move forward.</span></span> <span data-ttu-id="014f9-169">[在升級期間建立目前自訂專案的計畫 SharePoint 2013]( https://docs.microsoft.com/SharePoint/upgrade-and-update/create-a-plan-for-current-customizations-during-upgrade-to-sharepoint-2013) 在升級時，有一些有關評估及規劃目前自訂專案的極佳一般資訊。</span><span class="sxs-lookup"><span data-stu-id="014f9-169">[Create a plan for current customizations during upgrade to SharePoint 2013]( https://docs.microsoft.com/SharePoint/upgrade-and-update/create-a-plan-for-current-customizations-during-upgrade-to-sharepoint-2013) has some great general information about evaluating and planning for your current customizations when upgrading.</span></span>

- <span data-ttu-id="014f9-170">**時間和耐心** 升級的規劃、執行及測試需要很長的時間和精力，尤其是當您要升級至 Project Server 2019 時。</span><span class="sxs-lookup"><span data-stu-id="014f9-170">**Time and patience** - Upgrade planning, execution, and testing will take much time and effort, especially if you are upgrading to Project Server 2019.</span></span> <span data-ttu-id="014f9-171">例如，如果您要從 Project Server 2010 遷移至 Project Server 2019，您必須先從 Project Server 2010 遷移至 Project Server 2013，然後檢查您的資料，當您將每個後續版本 (遷移至 Project Server 2016，然後再進行) 的 Project Server 2019 時，請執行相同的動作。</span><span class="sxs-lookup"><span data-stu-id="014f9-171">For example, if you are migrating from Project Server 2010 to Project Server 2019, you will first need to migrate from Project Server 2010 to Project Server 2013, and then check your data, and then do the same thing when you migrate to each successive version (to Project Server 2016 and then to Project Server 2019).</span></span> <span data-ttu-id="014f9-172">您可能會想要與 Microsoft 解決方案提供者核對評估成本，使其達到估計成本的時間，以及其成本。</span><span class="sxs-lookup"><span data-stu-id="014f9-172">You might want to check with a Microsoft solution provider to compare your estimated costs with their estimates of how long it will take for them to do it, and at what cost.</span></span>

## <a name="migrate-to-project-online"></a><span data-ttu-id="014f9-173">遷移至 Project Online</span><span class="sxs-lookup"><span data-stu-id="014f9-173">Migrate to Project Online</span></span>

<span data-ttu-id="014f9-174">如果您選擇從 Project Server 2010 遷移至 Project Online，您可以執行下列動作以手動遷移專案計劃資料：</span><span class="sxs-lookup"><span data-stu-id="014f9-174">If you choose to migrate from Project Server 2010 to Project Online, you can do the following to manually migrate your project plan data:</span></span>

1. <span data-ttu-id="014f9-175">將專案方案從 Project Server 2010 儲存至。MPP 格式。</span><span class="sxs-lookup"><span data-stu-id="014f9-175">Save your project plans from Project Server 2010 to .MPP format.</span></span>

2. <span data-ttu-id="014f9-176">使用 Project Professional 2016、Project Professional 2019 或 Project Online 桌面用戶端，開啟每個副檔名檔案，然後將其儲存併發布到 Project Online。</span><span class="sxs-lookup"><span data-stu-id="014f9-176">Using Project Professional 2016, Project Professional 2019, or the Project Online Desktop Client, open each .mpp file, and then save and publish it to Project Online.</span></span>

<span data-ttu-id="014f9-177">您可以在 Project Online 中以手動方式建立 PWA 設定 (例如，重新建立任何必要的自訂欄位或企業行事曆) 。</span><span class="sxs-lookup"><span data-stu-id="014f9-177">You can manually create your PWA configuration in Project Online (for example, recreate any needed custom fields or enterprise calendars).</span></span> <span data-ttu-id="014f9-178">Microsoft 解決方案供應商也可協助您進行這種情況。</span><span class="sxs-lookup"><span data-stu-id="014f9-178">Microsoft solution providers can also help you with this.</span></span>

<span data-ttu-id="014f9-179">主要資源：</span><span class="sxs-lookup"><span data-stu-id="014f9-179">Key resources:</span></span>

|<span data-ttu-id="014f9-180">資源</span><span class="sxs-lookup"><span data-stu-id="014f9-180">Resource</span></span>|<span data-ttu-id="014f9-181">描述</span><span class="sxs-lookup"><span data-stu-id="014f9-181">Description</span></span>|
|---|---|
|[<span data-ttu-id="014f9-182">Project Online 快速入門</span><span class="sxs-lookup"><span data-stu-id="014f9-182">Get started with Project Online</span></span>](https://support.office.com/article/e3e5f64f-ada5-4f9d-a578-130b2d4e5f11)|<span data-ttu-id="014f9-183">如何設定和使用 Project Online。</span><span class="sxs-lookup"><span data-stu-id="014f9-183">How to setup and use Project Online.</span></span>|
|[<span data-ttu-id="014f9-184">Project Online 服務說明</span><span class="sxs-lookup"><span data-stu-id="014f9-184">Project Online Service Description</span></span>](https://go.microsoft.com/fwlink/p/?linkid=829088)|<span data-ttu-id="014f9-185">可供您使用之不同 Project Online 方案的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="014f9-185">Information about the different Project Online plans that are available to you.</span></span>|

## <a name="migrate-to-a-newer-on-premises-version-of-project-server"></a><span data-ttu-id="014f9-186">遷移至較新的內部部署版本的 Project Server</span><span class="sxs-lookup"><span data-stu-id="014f9-186">Migrate to a newer on-premises version of Project Server</span></span>

<span data-ttu-id="014f9-187">雖然我們極力相信您可以透過遷移至 Project Online，獲得最佳價值和使用者經驗，我們也會瞭解某些組織必須將專案資料保留在內部部署環境中。</span><span class="sxs-lookup"><span data-stu-id="014f9-187">While we strongly believe that you can achieve the best value and user experience by migrating to Project Online, we also understand that some organizations need to keep project data in an on-premises environment.</span></span> <span data-ttu-id="014f9-188">如果您選擇將專案資料保留在內部部署中，您可以將 Project Server 2010 環境遷移至 Project Server 2013、Project Server 2016 或 Project Server 2019。</span><span class="sxs-lookup"><span data-stu-id="014f9-188">If you choose to keep your project data on-premises, you can migrate your Project Server 2010 environment to Project Server 2013, Project Server 2016, or Project Server 2019.</span></span>

<span data-ttu-id="014f9-189">如果您無法遷移至 Project Online，建議您將遷移至 Project Server 2019。</span><span class="sxs-lookup"><span data-stu-id="014f9-189">We recommend that you migrate to Project Server 2019 if you can't migrate to Project Online.</span></span> <span data-ttu-id="014f9-190">Project Server 2019 包含舊版 Project Server 隨附的功能和增強功能，以及與 Project Online 搭配使用的經驗最為接近的功能 (不過某些功能只有在 Project Online) 中才能使用。</span><span class="sxs-lookup"><span data-stu-id="014f9-190">Project Server 2019 includes most of the key the features and advancements included with previous releases of Project Server, and it most closely matches the experience available with Project Online (although some features are available only in Project Online).</span></span>

<span data-ttu-id="014f9-191">完成每個遷移後，您應該檢查資料，以確定其已成功遷移。</span><span class="sxs-lookup"><span data-stu-id="014f9-191">After completing each migration, you should check your data to make sure that it has migrated successfully.</span></span>

> [!NOTE]
> <span data-ttu-id="014f9-192">如果您僅考慮遷移至 Project Server 2013 （如果您僅限內部部署解決方案），請務必注意，左側只會有幾年的支援。</span><span class="sxs-lookup"><span data-stu-id="014f9-192">If you are considering only migrating to Project Server 2013 if you are limited to an on-premises solution, it is important to note that it only has a few more years of support left.</span></span> <span data-ttu-id="014f9-193">Project Server 2013 Service Pack 2 結束支援日期為10/13/2023。</span><span class="sxs-lookup"><span data-stu-id="014f9-193">Project Server 2013 with Service Pack 2 end of support date is 10/13/2023.</span></span> <span data-ttu-id="014f9-194">如需有關支援日期結束的詳細資訊，請參閱 [Microsoft 產品生命週期原則](https://go.microsoft.com/fwlink/p/?linkid=842066)。</span><span class="sxs-lookup"><span data-stu-id="014f9-194">For more information about end of support dates, see [Microsoft Product Lifecycle Policy](https://go.microsoft.com/fwlink/p/?linkid=842066).</span></span>

### <a name="how-do-i-migrate-to-project-server-2019"></a><span data-ttu-id="014f9-195">如何遷移至 Project Server 2019？</span><span class="sxs-lookup"><span data-stu-id="014f9-195">How do I migrate to Project Server 2019?</span></span>

<span data-ttu-id="014f9-196">Project Server 2010 與 Project Server 2019 之間的架構差異，可防止直接遷移路徑。</span><span class="sxs-lookup"><span data-stu-id="014f9-196">The architectural differences between Project Server 2010 and Project Server 2019 prevents a direct migration path.</span></span> <span data-ttu-id="014f9-197">這表示，您必須將 Project Server 2010 資料移轉至下一個後續的 Project Server 版本，直到您升級至 Project Server 2019 為止。</span><span class="sxs-lookup"><span data-stu-id="014f9-197">This means that you will need to migrate your Project Server 2010 data to the next successive version of Project Server until you upgrade to Project Server 2019.</span></span>

<span data-ttu-id="014f9-198">您必須執行下列步驟，將 Project Server 2010 升級為 Project Server 2019：</span><span class="sxs-lookup"><span data-stu-id="014f9-198">You will need to do the following steps to upgrade Project Server 2010 to Project Server 2019:</span></span>

1. <span data-ttu-id="014f9-199">遷移至 Project Server 2013。</span><span class="sxs-lookup"><span data-stu-id="014f9-199">Migrate to Project Server 2013.</span></span>

2. <span data-ttu-id="014f9-200">從 Project 將2013遷移至 Project Server 2016。</span><span class="sxs-lookup"><span data-stu-id="014f9-200">Migrate from Project Serve 2013 to Project Server 2016.</span></span>

3. <span data-ttu-id="014f9-201">從 Project Server 2016 遷移至 Project Server 2019。</span><span class="sxs-lookup"><span data-stu-id="014f9-201">Migrate from Project Server 2016 to Project Server 2019.</span></span>

<span data-ttu-id="014f9-202">完成每個遷移後，您應該檢查資料，以確定其已成功遷移。</span><span class="sxs-lookup"><span data-stu-id="014f9-202">After completing each migration, you should check your data to make sure that it has migrated successfully.</span></span>


### <a name="step-1-migrate-to-project-server-2013"></a><span data-ttu-id="014f9-203">步驟1：遷移至 Project Server 2013</span><span class="sxs-lookup"><span data-stu-id="014f9-203">Step 1: Migrate to Project Server 2013</span></span>

<span data-ttu-id="014f9-204">將 Project Server 2010 資料移轉至 Project server 2019 的第一步，是先遷移至 Project Server 2013。</span><span class="sxs-lookup"><span data-stu-id="014f9-204">Your first step in migrating your Project Server 2010 data to Project Server 2019 is to first migrate to Project Server 2013.</span></span>

<span data-ttu-id="014f9-205">若要全面瞭解從 Project Server 2010 升級至 Project Server 2013 所需執行的工作，請參閱 [升級至 Project server 2013](https://go.microsoft.com/fwlink/p/?linkid=841822)。</span><span class="sxs-lookup"><span data-stu-id="014f9-205">For a comprehensive understanding of what you need to do to upgrade from Project Server 2010 to Project Server 2013, see [Upgrade to Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841822).</span></span>

<span data-ttu-id="014f9-206">主要資源：</span><span class="sxs-lookup"><span data-stu-id="014f9-206">Key resources:</span></span>

- [<span data-ttu-id="014f9-207">Project Server 2013 升級程式概述</span><span class="sxs-lookup"><span data-stu-id="014f9-207">Overview of the Project Server 2013 upgrade process</span></span>](https://go.microsoft.com/fwlink/p/?linkid=841822)

  <span data-ttu-id="014f9-208">深入瞭解從 Project Server 2010 升級至 Project Server 2013 所需執行的動作。</span><span class="sxs-lookup"><span data-stu-id="014f9-208">Get a high-level understanding of what you need to do to upgrade from Project Server 2010 to Project Server 2013.</span></span>
- [<span data-ttu-id="014f9-209">規劃升級到 Project Server 2013</span><span class="sxs-lookup"><span data-stu-id="014f9-209">Plan to upgrade to Project Server 2013</span></span>](https://go.microsoft.com/fwlink/p/?linkid=841823)

  <span data-ttu-id="014f9-210">請查看從 Project Server 2010 升級至 Project Server 2013 時所需進行的規劃考慮，包括系統需求。</span><span class="sxs-lookup"><span data-stu-id="014f9-210">Look at planning considerations you need to make when upgrading from Project Server 2010 to Project Server 2013, including System Requirements.</span></span>

<span data-ttu-id="014f9-211">[Project Server 2013 升級的新功能](https://go.microsoft.com/fwlink/p/?linkid=841824) 會告訴您，在此版本中升級的一些重要變更，最為明顯的：</span><span class="sxs-lookup"><span data-stu-id="014f9-211">[What's new in Project Server 2013 upgrade](https://go.microsoft.com/fwlink/p/?linkid=841824) tells you some important changes for upgrade for this version, the most notable being:</span></span>

- <span data-ttu-id="014f9-212">沒有就地升級至 Project Server 2013。</span><span class="sxs-lookup"><span data-stu-id="014f9-212">There is no in-place upgrade to Project Server 2013.</span></span> <span data-ttu-id="014f9-213">資料庫附加方法是唯一支援的方法，可從 Project Server 2010 升級至 Project Server 2013。</span><span class="sxs-lookup"><span data-stu-id="014f9-213">The database-attach method is the only supported method for upgrading from Project Server 2010 to Project Server 2013.</span></span>

- <span data-ttu-id="014f9-214">升級程式不僅會將您的 Project Server 2010 資料轉換成 Project Server 2013 格式，還會將這四個 Project Server 2010 資料庫合併成單一 Project Web App 資料庫。</span><span class="sxs-lookup"><span data-stu-id="014f9-214">The upgrade process will not only convert your Project Server 2010 data to Project Server 2013 format, but will also consolidate the four Project Server 2010 databases to a single Project Web App database.</span></span>

- <span data-ttu-id="014f9-215">SharePoint Server 2013 和 Project Server 2013 都變更為先前版本的宣告式驗證。</span><span class="sxs-lookup"><span data-stu-id="014f9-215">Both SharePoint Server 2013 and Project Server 2013 changed to claims-based authentication from the previous version.</span></span> <span data-ttu-id="014f9-216">如果您使用的是傳統驗證，則必須考慮進行升級。</span><span class="sxs-lookup"><span data-stu-id="014f9-216">You will need to make considerations when upgrading if you are using classic authentication.</span></span> <span data-ttu-id="014f9-217">如需詳細資訊，請參閱＜[在 SharePoint 2013 中從傳統模式移轉至宣告式驗證]( https://docs.microsoft.com/sharepoint/upgrade-and-update/migrate-from-classic-mode-to-claims-based-authentication-in-sharepoint-2013)＞。</span><span class="sxs-lookup"><span data-stu-id="014f9-217">For more information, see [Migrate from classic-mode to claims-based authentication in SharePoint 2013]( https://docs.microsoft.com/sharepoint/upgrade-and-update/migrate-from-classic-mode-to-claims-based-authentication-in-sharepoint-2013).</span></span>

<span data-ttu-id="014f9-218">主要資源：</span><span class="sxs-lookup"><span data-stu-id="014f9-218">Key resources:</span></span>

- [<span data-ttu-id="014f9-219">升級到 Project Server 2013 的升級程序概觀</span><span class="sxs-lookup"><span data-stu-id="014f9-219">Overview of the upgrade process to Project Server 2013</span></span>](https://go.microsoft.com/fwlink/p/?linkid=841274)

- [<span data-ttu-id="014f9-220">升級您的資料庫與 Project Web App 網站集合 (Project Server 2013)</span><span class="sxs-lookup"><span data-stu-id="014f9-220">Upgrade your databases and Project Web App site collections (Project Server 2013)</span></span>](https://go.microsoft.com/fwlink/p/?linkid=841272)

- [<span data-ttu-id="014f9-221">Microsoft Project Server 升級過程圖表</span><span class="sxs-lookup"><span data-stu-id="014f9-221">Microsoft Project Server upgrade process diagram</span></span>](https://go.microsoft.com/fwlink/p/?linkid=841270)

- [<span data-ttu-id="014f9-222">極佳的資料庫整合，Project Server 2010 至2013遷移，8個簡單的步驟</span><span class="sxs-lookup"><span data-stu-id="014f9-222">The Great Database Consolidation, Project Server 2010 to 2013 Migration in 8 Easy Steps</span></span>](https://go.microsoft.com/fwlink/p/?linkid=841271)

### <a name="step-2-migrate-to-project-server-2016"></a><span data-ttu-id="014f9-223">步驟2：遷移至 Project Server 2016</span><span class="sxs-lookup"><span data-stu-id="014f9-223">Step 2: Migrate to Project Server 2016</span></span>

<span data-ttu-id="014f9-224">在遷移至 Project Server 2013 並確認您的資料已成功遷移後，下一步是將您的資料移轉至 Project Server 2016。</span><span class="sxs-lookup"><span data-stu-id="014f9-224">After migrating to Project Server 2013 and verifying that your data has migrated successfully, the next step is to migrate your data to Project Server 2016.</span></span>

<span data-ttu-id="014f9-225">若要全面瞭解從 Project Server 2013 升級至 Project Server 2016 所需執行的工作，請參閱 [升級至 Project server 2016](https://docs.microsoft.com/Project/upgrade-to-project-server-2016)。</span><span class="sxs-lookup"><span data-stu-id="014f9-225">For a comprehensive understanding of what you need to do to upgrade from Project Server 2013 to Project Server 2016, see [Upgrade to Project Server 2016](https://docs.microsoft.com/Project/upgrade-to-project-server-2016).</span></span>

<span data-ttu-id="014f9-226">主要資源：</span><span class="sxs-lookup"><span data-stu-id="014f9-226">Key resources:</span></span>

- [<span data-ttu-id="014f9-227">Project Server 2016 升級程序概觀</span><span class="sxs-lookup"><span data-stu-id="014f9-227">Overview of the Project Server 2016 upgrade process</span></span>](https://docs.microsoft.com/Project/overview-of-the-project-server-2016-upgrade-process)

  <span data-ttu-id="014f9-228">深入瞭解從 Project Server 2013 升級至 Project Server 2016 所需執行的動作。</span><span class="sxs-lookup"><span data-stu-id="014f9-228">Get a high-level understanding of what you need to do to upgrade from Project Server 2013 to Project Server 2016.</span></span>

- [<span data-ttu-id="014f9-229">規劃升級到 Project Server 2016</span><span class="sxs-lookup"><span data-stu-id="014f9-229">Plan for upgrade to Project Server 2016</span></span>](https://docs.microsoft.com/Project/plan-for-upgrade-to-project-server-2016)

  <span data-ttu-id="014f9-230">請參閱從 Project Server 2013 升級至 Project Server 2016 時，所需的規劃考慮。</span><span class="sxs-lookup"><span data-stu-id="014f9-230">Look at planning considerations you need to make when upgrading from Project Server 2013 to Project Server 2016.</span></span>

<span data-ttu-id="014f9-231">[您需要瞭解的 Project Server 2016 升級相關事項](https://docs.microsoft.com/project/plan-for-upgrade-to-project-server-2016#thingknow) ，可告訴您一些重要的變更可升級至此版本，其中包括：</span><span class="sxs-lookup"><span data-stu-id="014f9-231">[Things you need to know about Project Server 2016 upgrade](https://docs.microsoft.com/project/plan-for-upgrade-to-project-server-2016#thingknow) tells you some important changes for upgrading to this version, which include:</span></span>

- <span data-ttu-id="014f9-232">當您建立要遷移 Project Server 2013 資料的 Project Server 2016 環境時，請注意，Project Server 2016 安裝檔會包含在 SharePoint Server 2016 中。</span><span class="sxs-lookup"><span data-stu-id="014f9-232">When you create your Project Server 2016 environment to which you will migrate your Project Server 2013 data, note that the Project Server 2016 installation files are included in SharePoint Server 2016.</span></span> <span data-ttu-id="014f9-233">如需詳細資訊，請參閱 [部署 Project Server 2016](https://go.microsoft.com/fwlink/p/?linkid=841829)。</span><span class="sxs-lookup"><span data-stu-id="014f9-233">For more information, see [Deploy Project Server 2016](https://go.microsoft.com/fwlink/p/?linkid=841829).</span></span>

- <span data-ttu-id="014f9-234">資源計劃在 Project Server 2016 中已被取代。</span><span class="sxs-lookup"><span data-stu-id="014f9-234">Resource plans are deprecated in Project Server 2016.</span></span> <span data-ttu-id="014f9-235">您的 Project Server 2013 資源計劃將遷移至 Project Server 2016 和 Project Online 中的資源預訂。</span><span class="sxs-lookup"><span data-stu-id="014f9-235">Your Project Server 2013 resource plans will be migrated to Resource Engagements in Project Server 2016 and in Project Online.</span></span> <span data-ttu-id="014f9-236">如需詳細資訊，請參閱 [綜述： Resource 預訂](https://support.office.com/article/73eefb5a-81fe-42bf-980e-9532b1bdc870) 。</span><span class="sxs-lookup"><span data-stu-id="014f9-236">See [Overview: Resource engagements](https://support.office.com/article/73eefb5a-81fe-42bf-980e-9532b1bdc870) for more information.</span></span>

### <a name="step-3-migrate-to-project-server-2019"></a><span data-ttu-id="014f9-237">步驟3：遷移至 Project Server 2019</span><span class="sxs-lookup"><span data-stu-id="014f9-237">Step 3: Migrate to Project Server 2019</span></span>

<span data-ttu-id="014f9-238">在遷移至 Project Server 2016 並確認您的資料已成功遷移後，下一步是將您的資料移轉至 Project Server 2019。</span><span class="sxs-lookup"><span data-stu-id="014f9-238">After migrating to Project Server 2016 and verifying that your data has migrated successfully, the next step is to migrate your data to Project Server 2019.</span></span>

<span data-ttu-id="014f9-239">若要全面瞭解從 Project Server 2016 升級至 Project Server 2019 所需執行的工作，請參閱 [升級至 Project server 2019](https://docs.microsoft.com/Project/upgrade-to-project-server-2016)。</span><span class="sxs-lookup"><span data-stu-id="014f9-239">For a comprehensive understanding of what you need to do to upgrade from Project Server 2016 to Project Server 2019, see [Upgrade to Project Server 2019](https://docs.microsoft.com/Project/upgrade-to-project-server-2016).</span></span>

<span data-ttu-id="014f9-240">主要資源：</span><span class="sxs-lookup"><span data-stu-id="014f9-240">Key resources:</span></span>

- [<span data-ttu-id="014f9-241">Project Server 2019 升級程式概述</span><span class="sxs-lookup"><span data-stu-id="014f9-241">Overview of the Project Server 2019 upgrade process</span></span>](https://docs.microsoft.com/project/overview-of-the-project-server-2019-upgrade-process)

  <span data-ttu-id="014f9-242">深入瞭解從 Project Server 2013 升級至 Project Server 2016 所需執行的動作。</span><span class="sxs-lookup"><span data-stu-id="014f9-242">Get a high-level understanding of what you need to do to upgrade from Project Server 2013 to Project Server 2016.</span></span>

- [<span data-ttu-id="014f9-243">規劃升級至 Project Server 2019</span><span class="sxs-lookup"><span data-stu-id="014f9-243">Plan for upgrade to Project Server 2019</span></span>](https://docs.microsoft.com/project/plan-for-upgrade-to-project-server-2019)

  <span data-ttu-id="014f9-244">請參閱從 Project Server 2016 升級至 Project Server 2019 時，所需的規劃考慮。</span><span class="sxs-lookup"><span data-stu-id="014f9-244">Look at planning considerations you need to make when upgrading from Project Server 2016 to Project Server 2019.</span></span>

<span data-ttu-id="014f9-245">[您需要瞭解的 Project Server 2019 升級相關事項](https://go.microsoft.com/fwlink/p/?linkid=841827) ，可告訴您一些重要的變更可升級至此版本，其中包括：</span><span class="sxs-lookup"><span data-stu-id="014f9-245">[Things you need to know about Project Server 2019 upgrade](https://go.microsoft.com/fwlink/p/?linkid=841827) tells you some important changes for upgrading to this version, which include:</span></span>

- <span data-ttu-id="014f9-246">升級程式會將您的資料從 Project Server 2016 資料庫移轉至 SharePoint 伺服器2019內容資料庫。</span><span class="sxs-lookup"><span data-stu-id="014f9-246">The upgrade process will migrate your data from your Project Server 2016 database to the SharePoint Server 2019 Content database.</span></span>  <span data-ttu-id="014f9-247">Project Server 2019 將不再在 SharePoint 伺服器陣列中建立自己的 Project Server 資料庫。</span><span class="sxs-lookup"><span data-stu-id="014f9-247">Project Server 2019 will no longer create its own Project Server database in the SharePoint Server farm.</span></span>

- <span data-ttu-id="014f9-248">升級之後，請留意 Project Web App 中的數項變更。</span><span class="sxs-lookup"><span data-stu-id="014f9-248">After upgrade, be aware of several changes in Project Web App.</span></span>  <span data-ttu-id="014f9-249">如需這些功能的說明，請參閱 [Project Server 2019 的新功能](https://docs.microsoft.com/project/what-s-new-for-it-pros-in-project-server-2019#PWAChanges)。</span><span class="sxs-lookup"><span data-stu-id="014f9-249">For a description of these, see [What's new in Project Server 2019](https://docs.microsoft.com/project/what-s-new-for-it-pros-in-project-server-2019#PWAChanges).</span></span>

<span data-ttu-id="014f9-250">**其他資源**：</span><span class="sxs-lookup"><span data-stu-id="014f9-250">**Other resources**:</span></span>

- <span data-ttu-id="014f9-251">[Project Online 服務說明](https://go.microsoft.com/fwlink/p/?linkid=841280)：請參閱 project Server 2016 和 Project Online Premium 隨附的公事包管理功能。</span><span class="sxs-lookup"><span data-stu-id="014f9-251">[Project Online Service Descriptions](https://go.microsoft.com/fwlink/p/?linkid=841280): See the portfolio management features that are included with Project Server 2016 and Project Online Premium.</span></span>

- [<span data-ttu-id="014f9-252">Microsoft Office 專案公事包伺服器2010遷移指南</span><span class="sxs-lookup"><span data-stu-id="014f9-252">Microsoft Office Project Portfolio Server 2010 migration guide</span></span>](https://go.microsoft.com/fwlink/p/?linkid=841279)

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a><span data-ttu-id="014f9-253">適用於 Office 2010 用戶端與伺服器和 Windows 7 的選項摘要</span><span class="sxs-lookup"><span data-stu-id="014f9-253">Summary of options for Office 2010 client and servers and Windows 7</span></span>

<span data-ttu-id="014f9-254">如需適用於 Office 2010 用戶端與伺服器和 Windows 7 的升級、移轉和移至雲端選項的視覺摘要，請參閱[終止支援海報](../downloads/Office2010Windows7EndOfSupport.pdf)。</span><span class="sxs-lookup"><span data-stu-id="014f9-254">For a visual summary of the upgrade, migrate, and move-to-the-cloud options for Office 2010 clients and servers and Windows 7, see the [end of support poster](../downloads/Office2010Windows7EndOfSupport.pdf).</span></span>

<span data-ttu-id="014f9-255">[![Office 2010 用戶端與伺服器和 Windows 7 終止支援海報的影像](../media/upgrade-from-office-2010-servers-and-products/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)</span><span class="sxs-lookup"><span data-stu-id="014f9-255">[![Image for the end of support for Office 2010 clients and servers and Windows 7 poster](../media/upgrade-from-office-2010-servers-and-products/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)</span></span>

<span data-ttu-id="014f9-256">這張單頁海報可讓您快速了解可以採取的各種方法，以防止Office 2010 用戶端與伺服器產品以及 Windows 7 進入終止支援，而海報上也會強調顯示 Microsoft 365 企業版中慣用的方式和選項支援。</span><span class="sxs-lookup"><span data-stu-id="014f9-256">This one-page poster is a quick way to understand the various paths you can take to prevent Office 2010 client and server products and Windows 7 from reaching end of support, with preferred paths and option support in Microsoft 365 Enterprise highlighted.</span></span>

<span data-ttu-id="014f9-257">您可以[下載](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf)此海報，並以 Letter、Legal 或 Tabloid (11 x 17) 格式列印此海報。</span><span class="sxs-lookup"><span data-stu-id="014f9-257">You can also [download](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) this poster and print it in letter, legal, or tabloid (11 x 17) formats.</span></span>

## <a name="related-topics"></a><span data-ttu-id="014f9-258">相關主題</span><span class="sxs-lookup"><span data-stu-id="014f9-258">Related topics</span></span>

[<span data-ttu-id="014f9-259">從 SharePoint 2010 升級</span><span class="sxs-lookup"><span data-stu-id="014f9-259">Upgrading from SharePoint 2010</span></span>](upgrade-from-sharepoint-2010.md)

[<span data-ttu-id="014f9-260">從 Office 2010 伺服器與用戶端升級</span><span class="sxs-lookup"><span data-stu-id="014f9-260">Upgrade from Office 2010 servers and clients</span></span>](upgrade-from-office-2010-servers-and-products.md)
