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
ms.openlocfilehash: 239b3d93cfa6a1184ea21225fa97732712b8eb14
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519699"
---
# <a name="project-server-2010-end-of-support-roadmap"></a><span data-ttu-id="b6b2e-104">Project Server 2010 終止支援藍圖</span><span class="sxs-lookup"><span data-stu-id="b6b2e-104">Project Server 2010 end of support roadmap</span></span>

<span data-ttu-id="b6b2e-105">*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="b6b2e-105">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="b6b2e-106">Project Server 2010 將于 **年4月 13 2021 日** 到達支援終止。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-106">Project Server 2010 will reach end of support on **April 13, 2021**.</span></span> <span data-ttu-id="b6b2e-107">此日期是從上一年10月13日的支援終止日（2020）延伸。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-107">This date was extended from the previous end-of-support date of October 13, 2020.</span></span> <span data-ttu-id="b6b2e-108">如果您目前使用的是 Project Server 2010，請注意，這些相關產品的支援終止日期如下：</span><span class="sxs-lookup"><span data-stu-id="b6b2e-108">If you're currently using Project Server 2010, note that these related products have the following end-of-support dates:</span></span>

|<span data-ttu-id="b6b2e-109">產品</span><span class="sxs-lookup"><span data-stu-id="b6b2e-109">Product</span></span> |<span data-ttu-id="b6b2e-110">支援日期結束</span><span class="sxs-lookup"><span data-stu-id="b6b2e-110">End of support date</span></span>|
|---|---|
|<span data-ttu-id="b6b2e-111">Project 2010 Standard</span><span class="sxs-lookup"><span data-stu-id="b6b2e-111">Project 2010 Standard</span></span>|<span data-ttu-id="b6b2e-112">2020 年 10 月 13 日</span><span class="sxs-lookup"><span data-stu-id="b6b2e-112">October 13, 2020</span></span>|
|<span data-ttu-id="b6b2e-113">Project 2010 專業版</span><span class="sxs-lookup"><span data-stu-id="b6b2e-113">Project 2010 Professional</span></span>|<span data-ttu-id="b6b2e-114">2020 年 10 月 13 日</span><span class="sxs-lookup"><span data-stu-id="b6b2e-114">October 13, 2020</span></span>|

<span data-ttu-id="b6b2e-115">如需有關到達支援終止的詳細資訊，請參閱 [從 Office 2010 伺服器與用戶端產品升級](plan-upgrade-previous-versions-office.md)。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-115">For more information about reaching end of support, see [Upgrade from Office 2010 servers and client products](plan-upgrade-previous-versions-office.md).</span></span>

## <a name="what-does-end-of-support-mean"></a><span data-ttu-id="b6b2e-116">*支援終止的* 意義為何？</span><span class="sxs-lookup"><span data-stu-id="b6b2e-116">What does *end of support* mean?</span></span>

<span data-ttu-id="b6b2e-117">幾乎所有的 Microsoft 產品都有支援週期，在這種情況下，其可取得新功能、錯誤修正及安全性更新。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-117">Almost all Microsoft products have a support lifecycle, during which they get new features, bug fixes, and security updates.</span></span> <span data-ttu-id="b6b2e-118">此生命週期一般會從產品的初始發行版本持續10年。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-118">This lifecycle typically lasts for 10 years from the product's initial release.</span></span> <span data-ttu-id="b6b2e-119">此週期的結尾稱為產品的支援終止。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-119">The end of this lifecycle is known as the product's end of support.</span></span> <span data-ttu-id="b6b2e-120">在 Project Server 2010 在年4月 13 2021 日到達其支援終止後，Microsoft 將不再提供：</span><span class="sxs-lookup"><span data-stu-id="b6b2e-120">After Project Server 2010 reaches its end of support on April 13, 2021, Microsoft will no longer provide:</span></span>

- <span data-ttu-id="b6b2e-121">可能發生問題的技術支援。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-121">Technical support for problems that may occur.</span></span>

- <span data-ttu-id="b6b2e-122">針對所探索之問題的錯誤修正，而且可能會影響伺服器的穩定性和可用性。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-122">Bug fixes for issues that are discovered and that may impact the stability and usability of the server.</span></span>

- <span data-ttu-id="b6b2e-123">已發現之弱點的安全性修正程式，可能會導致伺服器遭受安全性破壞。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-123">Security fixes for vulnerabilities that are discovered and that may make the server vulnerable to security breaches.</span></span>

- <span data-ttu-id="b6b2e-124">時區更新。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-124">Time zone updates.</span></span>

<span data-ttu-id="b6b2e-125">在此日期之後，Project Server 2010 的安裝會繼續執行。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-125">Your installation of Project Server 2010 will continue to run after this date.</span></span> <span data-ttu-id="b6b2e-126">不過，由於先前所列的變更，強烈建議您儘早從 Project Server 2010 進行遷移。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-126">But, because of the changes listed previously, we strongly recommend that you migrate from Project Server 2010 as soon as possible.</span></span>

## <a name="what-are-my-options"></a><span data-ttu-id="b6b2e-127">我有哪些選擇？</span><span class="sxs-lookup"><span data-stu-id="b6b2e-127">What are my options?</span></span>

<span data-ttu-id="b6b2e-128">您的遷移選項包括：</span><span class="sxs-lookup"><span data-stu-id="b6b2e-128">Your migration options are:</span></span>

- <span data-ttu-id="b6b2e-129">遷移至 Project Online</span><span class="sxs-lookup"><span data-stu-id="b6b2e-129">Migrate to Project Online</span></span>

- <span data-ttu-id="b6b2e-130">遷移至較新的內部部署版本的 Project Server (最好的 Project Server 2019) </span><span class="sxs-lookup"><span data-stu-id="b6b2e-130">Migrate to a newer on-premises version of Project Server (preferably Project Server 2019)</span></span>

<span data-ttu-id="b6b2e-131">以下是您可以採取的兩種途徑，以避免 Project Server 2010 的支援結束。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-131">Here are the two paths you can take to avoid the end of support for Project Server 2010.</span></span>

![Project Server 2010 升級路徑](../media/project-server-2010-end-of-support/project-server-2010-end-of-support-timeline.png)

|<span data-ttu-id="b6b2e-133">為什麼我想要遷移至 Project Server 2019？</span><span class="sxs-lookup"><span data-stu-id="b6b2e-133">Why would I prefer to migrate to Project Server 2019?</span></span>|<span data-ttu-id="b6b2e-134">為什麼我想要遷移至 Project Online？</span><span class="sxs-lookup"><span data-stu-id="b6b2e-134">Why would I prefer to migrate to Project Online?</span></span>|
|---|---|
|<span data-ttu-id="b6b2e-135">商務規則限制我在雲端中運作我的公司。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-135">Business rules restrict me from operating my business in the cloud.</span></span>  <br/><br/>  <span data-ttu-id="b6b2e-136">我需要控制環境的更新。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-136">I need control of updates to my environment.</span></span>|<span data-ttu-id="b6b2e-137">我有行動電話或遠端使用者。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-137">I have mobile or remote users.</span></span><br/><br/>  <span data-ttu-id="b6b2e-138">遷移內部部署伺服器所需的成本是 (硬體、軟體、時間和工作執行的重要考慮，如此等等。 ) 。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-138">Costs to migrate on-premises servers are a significant concern (hardware, software, time and effort to implement, and so on.).</span></span> <br/><br/>  <span data-ttu-id="b6b2e-139">遷移後，維護環境所需的成本為 (的考慮，例如，自動更新、保證的執行時間等等) 。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-139">After migration, costs to maintain my environment are a concern (for example, automatic updates, guaranteed uptime, and so on).</span></span>|

> [!NOTE]
> <span data-ttu-id="b6b2e-140">如需有關遷移選項的詳細資訊，請參閱 [協助您從 Office 2010 伺服器及用戶端升級的資源](upgrade-from-office-2010-servers-and-products.md)。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-140">For more information about your migration options, see [Resources to help you upgrade from Office 2010 servers and clients](upgrade-from-office-2010-servers-and-products.md).</span></span> <span data-ttu-id="b6b2e-141">請注意，Project Server 不支援混合式設定，因為 Project Server 和 Project Online 無法共用相同的資源集區。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-141">Note that Project Server doesn't support hybrid configuration because Project Server and Project Online can't share the same resource pool.</span></span>

### <a name="what-are-my-options-for-project-client"></a><span data-ttu-id="b6b2e-142">我的 Project 用戶端選項為何？</span><span class="sxs-lookup"><span data-stu-id="b6b2e-142">What are my options for Project client?</span></span>

<span data-ttu-id="b6b2e-143">如果您使用的是 Project Professional 2010 或 Project Standard 2010，您的選項如下：</span><span class="sxs-lookup"><span data-stu-id="b6b2e-143">If you're using Project Professional 2010 or Project Standard 2010, your options are:</span></span>

- <span data-ttu-id="b6b2e-144">移至較新版本的 Project Professional 或 Project Standard</span><span class="sxs-lookup"><span data-stu-id="b6b2e-144">Move to a newer version of Project Professional or Project Standard</span></span>
- <span data-ttu-id="b6b2e-145">移至線上方案，例如 Project Online 或 Web 專案</span><span class="sxs-lookup"><span data-stu-id="b6b2e-145">Move to an online solution, such as Project Online or Project for the web</span></span>

#### <a name="move-to-a-newer-version-of-project-client"></a><span data-ttu-id="b6b2e-146">移至較新版本的 Project 用戶端</span><span class="sxs-lookup"><span data-stu-id="b6b2e-146">Move to a newer version of Project client</span></span>

<span data-ttu-id="b6b2e-147">如果您是從 Project Standard 2010 遷移，您可以移至較新版本的專案 Standard (Project Standard 2016 或 Project Standard 2019) 。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-147">If you're migrating from Project Standard 2010, you can move to a newer version of Project Standard (Project Standard 2016 or Project Standard 2019).</span></span> <span data-ttu-id="b6b2e-148">建議您移至最新的版本，以充分利用最新的功能。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-148">We recommend you move to the newest version to take advantage of the latest features.</span></span> <span data-ttu-id="b6b2e-149">遷移至最新版本 (專案標準 2016) 也表示您將需要更快地遷移。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-149">Migrating to a less-current version (Project Standard 2016) also means you'll need to migrate again sooner.</span></span>

<span data-ttu-id="b6b2e-150">同樣地，如果您是從 Project Professional 2010 進行遷移，您可以移至較新的版本 (Project Professional 2019 或 Project Professional 2016) 。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-150">Similarly, if you're migrating from Project Professional 2010, you can move to a newer version (Project Professional 2019 or Project Professional 2016).</span></span> <span data-ttu-id="b6b2e-151">另外，請盡可能移至最新版本。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-151">Again, move to the newest version if possible.</span></span> <span data-ttu-id="b6b2e-152">如果您使用 Project Professional 連線至 Project Server，請確定您要遷移至 Project Professional 的版本，以與您使用的 Project Server 版本連線。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-152">If you use Project Professional to connect to Project Server, make sure you migrate to a version of Project Professional that connects with the version of Project Server that you use.</span></span>

<span data-ttu-id="b6b2e-153">Project Professional 2010 使用者也可以遷移至 Project Online 桌面用戶端，這是訂閱型版本的 Project Professional 2019。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-153">Project Professional 2010 users can also migrate to the Project Online Desktop client, which is a subscription-based version of Project Professional 2019.</span></span> <span data-ttu-id="b6b2e-154">它包含在 Project 方案3和專案方案5訂閱中。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-154">It's included in Project Plan 3 and Project Plan 5 subscriptions.</span></span>

#### <a name="move-to-an-online-solution"></a><span data-ttu-id="b6b2e-155">移至線上方案</span><span class="sxs-lookup"><span data-stu-id="b6b2e-155">Move to an online solution</span></span>

<span data-ttu-id="b6b2e-156">您也可以從 Project Professional 2010 或 Project Standard 2010 遷移至以 Project 訂閱為基礎的線上方案。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-156">You can also migrate from Project Professional 2010 or Project Standard 2010 to a Project subscription-based online solution.</span></span> <span data-ttu-id="b6b2e-157">這兩個專案方案3和方案5都包括 Project Online 及最新的雲端方案（ [適用于 web](https://support.office.com/article/what-can-you-do-with-project-for-the-web-b30f5442-be5f-43d2-9072-c95bff778ea1)）。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-157">Both Project Plan 3 and Plan 5 include Project Online and the latest cloud offering, [Project for the web](https://support.office.com/article/what-can-you-do-with-project-for-the-web-b30f5442-be5f-43d2-9072-c95bff778ea1).</span></span> <span data-ttu-id="b6b2e-158">兩者都提供值得探索的新功能和優點。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-158">Both offer new features and benefits that are worth exploring.</span></span>

<span data-ttu-id="b6b2e-159">如需功能和授權的詳細資訊，請參閱 [Microsoft Project service 描述](https://docs.microsoft.com/office365/servicedescriptions/project-online-service-description/project-online-service-description)。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-159">For more information about features and licenses, see [Microsoft Project service description](https://docs.microsoft.com/office365/servicedescriptions/project-online-service-description/project-online-service-description).</span></span>

## <a name="important-considerations-for-migrating-from-project-server-2010"></a><span data-ttu-id="b6b2e-160">從 Project Server 2010 進行遷移時的重要考慮</span><span class="sxs-lookup"><span data-stu-id="b6b2e-160">Important considerations for migrating from Project Server 2010</span></span>

<span data-ttu-id="b6b2e-161">當您規劃從 Project Server 2010 遷移時，請考慮下列事項：</span><span class="sxs-lookup"><span data-stu-id="b6b2e-161">Consider the following when you plan to migrate from Project Server 2010:</span></span>

- <span data-ttu-id="b6b2e-162">**從 Microsoft 解決方案供應商取得協助** -從 Project Server 2010 升級可能是一項挑戰。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-162">**Get help from a Microsoft solution provider** - An upgrade from Project Server 2010 can be a challenge.</span></span> <span data-ttu-id="b6b2e-163">它需要大量的準備工作和規劃。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-163">It requires much preparation and planning.</span></span> <span data-ttu-id="b6b2e-164">如果您不是原始設定 Project Server 2010 的人員，可能特別有挑戰性。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-164">It can be especially challenging if you weren't the person who originally set up Project Server 2010.</span></span> <span data-ttu-id="b6b2e-165">您可以使用 Microsoft 解決方案提供者來協助您，是否要遷移至 Project Server 2019 或 Project Online。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-165">Microsoft solution providers are available to help, whether you plan to migrate to Project Server 2019 or to Project Online.</span></span> <span data-ttu-id="b6b2e-166">在 [Microsoft 解決方案供應商中心](https://go.microsoft.com/fwlink/p/?linkid=841249)搜尋解決方案提供者。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-166">Search for a solution provider in the [Microsoft solution provider center](https://go.microsoft.com/fwlink/p/?linkid=841249).</span></span>

- <span data-ttu-id="b6b2e-167">**規劃自訂** -當您遷移至 project server 2019 或 project Online 時，project server 2010 環境中的自訂功能可能無法運作。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-167">**Plan for your customizations** - Customizations  in your Project Server 2010 environment might not work when you migrate to Project Server 2019 or Project Online.</span></span> <span data-ttu-id="b6b2e-168">在不同的版本之間，Project Server 架構的差異很大。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-168">There are significant differences in Project Server architecture between versions.</span></span> <span data-ttu-id="b6b2e-169">此外，使用版本的必要作業系統、資料庫伺服器及網頁瀏覽器也不同。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-169">Also, the required operating systems, database servers, and web browsers that work with the versions differ.</span></span> <span data-ttu-id="b6b2e-170">規劃如何在新環境中測試或重建自訂專案。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-170">Have a plan on how to test or rebuild your customizations in the new environment.</span></span> <span data-ttu-id="b6b2e-171">採取此機會判斷是否仍需要特定的自訂專案。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-171">Take this opportunity to determine if specific customizations are still needed.</span></span> <span data-ttu-id="b6b2e-172">如需詳細資訊，請參閱＜[Create a plan for current customizations during upgrade to SharePoint 2013](https://docs.microsoft.com/SharePoint/upgrade-and-update/create-a-plan-for-current-customizations-during-upgrade-to-sharepoint-2013)＞。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-172">For more information, see [Create a plan for current customizations during upgrade to SharePoint 2013](https://docs.microsoft.com/SharePoint/upgrade-and-update/create-a-plan-for-current-customizations-during-upgrade-to-sharepoint-2013).</span></span>

- <span data-ttu-id="b6b2e-173">**時間和耐心** 升級的規劃、執行及測試需要相當長的時間和精力，尤其是升級至 Project Server 2019。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-173">**Time and patience** - Upgrade planning, execution, and testing will take considerable time and effort, especially for an upgrade to Project Server 2019.</span></span> <span data-ttu-id="b6b2e-174">如果您要從 Project Server 2010 遷移至 Project Server 2019，您必須先遷移至 Project Server 2013，檢查您的資料，然後再遷移至 Project Server 2016，然後再到 Project Server 2019。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-174">If you're migrating from Project Server 2010 to Project Server 2019, you must first migrate to Project Server 2013, check your data, then migrate to Project Server 2016, and then to Project Server 2019.</span></span> <span data-ttu-id="b6b2e-175">您可能想要與 Microsoft 解決方案提供者聯繫以取得協助的時間範圍和預估成本。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-175">You might want to check with a Microsoft solution provider for a time frame and estimated cost for them to assist.</span></span>

## <a name="migrate-to-project-online"></a><span data-ttu-id="b6b2e-176">遷移至 Project Online</span><span class="sxs-lookup"><span data-stu-id="b6b2e-176">Migrate to Project Online</span></span>

<span data-ttu-id="b6b2e-177">如果您選擇從 Project Server 2010 遷移至 Project Online，您可以遵循下列步驟手動遷移專案計劃資料：</span><span class="sxs-lookup"><span data-stu-id="b6b2e-177">If you choose to migrate from Project Server 2010 to Project Online, you can follow these steps to manually migrate your project plan data:</span></span>

1. <span data-ttu-id="b6b2e-178">將專案方案從 Project Server 2010 儲存為 mpp 格式。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-178">Save your project plans from Project Server 2010 to .mpp format.</span></span>

2. <span data-ttu-id="b6b2e-179">使用 Project Professional 2016、Project Professional 2019 或 Project Online 桌面用戶端，開啟每個副檔名檔案，然後將其儲存併發布到 Project Online。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-179">Using Project Professional 2016, Project Professional 2019, or the Project Online Desktop Client, open each .mpp file, and then save and publish it to Project Online.</span></span>

<span data-ttu-id="b6b2e-180">您可以在 Project Online 中以手動方式建立 PWA 設定 (例如，重新建立任何必要的自訂欄位或企業行事曆) 。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-180">You can manually create your PWA configuration in Project Online (for example, recreate any needed custom fields or enterprise calendars).</span></span> <span data-ttu-id="b6b2e-181">Microsoft 解決方案供應商也可協助您進行此程式。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-181">Microsoft solution providers can also help with this process.</span></span>

<span data-ttu-id="b6b2e-182">主要資源：</span><span class="sxs-lookup"><span data-stu-id="b6b2e-182">Key resources:</span></span>

|<span data-ttu-id="b6b2e-183">資源</span><span class="sxs-lookup"><span data-stu-id="b6b2e-183">Resource</span></span>|<span data-ttu-id="b6b2e-184">描述</span><span class="sxs-lookup"><span data-stu-id="b6b2e-184">Description</span></span>|
|---|---|
|[<span data-ttu-id="b6b2e-185">Project Online 快速入門</span><span class="sxs-lookup"><span data-stu-id="b6b2e-185">Get started with Project Online</span></span>](https://support.office.com/article/e3e5f64f-ada5-4f9d-a578-130b2d4e5f11)|<span data-ttu-id="b6b2e-186">如何設定和使用 Project Online</span><span class="sxs-lookup"><span data-stu-id="b6b2e-186">How to set up and use Project Online</span></span>|
|[<span data-ttu-id="b6b2e-187">Project Online 服務說明</span><span class="sxs-lookup"><span data-stu-id="b6b2e-187">Project Online Service Description</span></span>](https://go.microsoft.com/fwlink/p/?linkid=829088)|<span data-ttu-id="b6b2e-188">可供使用之不同 Project Online 方案的相關資訊</span><span class="sxs-lookup"><span data-stu-id="b6b2e-188">Information about the different Project Online plans available</span></span>|

## <a name="migrate-to-a-newer-on-premises-version-of-project-server"></a><span data-ttu-id="b6b2e-189">遷移至較新的內部部署版本的 Project Server</span><span class="sxs-lookup"><span data-stu-id="b6b2e-189">Migrate to a newer on-premises version of Project Server</span></span>

<span data-ttu-id="b6b2e-190">我們強烈相信您可以透過遷移至 Project Online，獲得最佳的價值和使用者經驗。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-190">We strongly believe that you get the best value and user experience by migrating to Project Online.</span></span> <span data-ttu-id="b6b2e-191">不過，我們也瞭解部分組織必須將專案資料保留在內部部署中。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-191">But we also understand some organizations need to keep project data on-premises.</span></span> <span data-ttu-id="b6b2e-192">如果您選擇將專案資料保留在內部部署中，您可以將 Project Server 2010 環境遷移至 Project Server 2013、Project Server 2016 或 Project Server 2019。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-192">If you choose to keep your project data on-premises, you can migrate your Project Server 2010 environment to Project Server 2013, Project Server 2016, or Project Server 2019.</span></span>

<span data-ttu-id="b6b2e-193">如果您無法遷移至 Project Online，建議您將遷移至 Project Server 2019。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-193">If you can't migrate to Project Online, we recommend that you migrate to Project Server 2019.</span></span> <span data-ttu-id="b6b2e-194">Project Server 2019 包含舊版 Project Server 中的大部分重要功能。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-194">Project Server 2019 includes most of the key features in previous releases of Project Server.</span></span> <span data-ttu-id="b6b2e-195">而且它最符合 Project Online 可用的體驗，不過某些功能僅適用于 Project Online。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-195">And it most closely matches the experience available with Project Online, although some features are available only in Project Online.</span></span>

<span data-ttu-id="b6b2e-196">完成每項遷移後，請確定您的資料已順利遷移。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-196">After you complete each migration, make sure that your data migrated successfully.</span></span>

> [!NOTE]
> <span data-ttu-id="b6b2e-197">如果您局限于內部部署解決方案，而且只考慮遷移至 Project Server 2013，請注意，此版本只會有幾年以上的支援。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-197">If you're limited to an on-premises solution and considering only migrating to Project Server 2013, beware that this version only has a few more years of support left.</span></span> <span data-ttu-id="b6b2e-198">Project Server 2013 的支援日期結束時間為10月13日 Service Pack 2，2023。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-198">The end of support date for Project Server 2013 with Service Pack 2 October 13, 2023.</span></span> <span data-ttu-id="b6b2e-199">如需終止支援日期的詳細資訊，請參閱 [Microsoft 產品生命週期原則](https://go.microsoft.com/fwlink/p/?linkid=842066)。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-199">For more information about end-of-support dates, see [Microsoft Product Lifecycle Policy](https://go.microsoft.com/fwlink/p/?linkid=842066).</span></span>

### <a name="how-do-i-migrate-to-project-server-2019"></a><span data-ttu-id="b6b2e-200">如何遷移至 Project Server 2019？</span><span class="sxs-lookup"><span data-stu-id="b6b2e-200">How do I migrate to Project Server 2019?</span></span>

<span data-ttu-id="b6b2e-201">Project Server 2010 與 Project Server 2019 之間的架構差異會防止直接遷移路徑。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-201">The architectural differences between Project Server 2010 and Project Server 2019 prevent a direct migration path.</span></span> <span data-ttu-id="b6b2e-202">因此，您必須將 Project Server 2010 資料移轉至 Project Server 的每個後續版本，直到達到 Project Server 2019 為止。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-202">So you'll need to migrate your Project Server 2010 data to each successive version of Project Server until you reach Project Server 2019.</span></span> <span data-ttu-id="b6b2e-203">將 Project Server 2010 升級至 Project Server 2019 的步驟：</span><span class="sxs-lookup"><span data-stu-id="b6b2e-203">Steps to upgrade Project Server 2010 to Project Server 2019:</span></span>

1. <span data-ttu-id="b6b2e-204">遷移至 Project Server 2013。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-204">Migrate to Project Server 2013.</span></span>

2. <span data-ttu-id="b6b2e-205">從 Project 將2013遷移至 Project Server 2016。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-205">Migrate from Project Serve 2013 to Project Server 2016.</span></span>

3. <span data-ttu-id="b6b2e-206">從 Project Server 2016 遷移至 Project Server 2019。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-206">Migrate from Project Server 2016 to Project Server 2019.</span></span>

<span data-ttu-id="b6b2e-207">完成每項遷移後，請確定您的資料已順利遷移。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-207">After you complete each migration, make sure that your data migrated successfully.</span></span>

### <a name="step-1-migrate-to-project-server-2013"></a><span data-ttu-id="b6b2e-208">步驟1：遷移至 Project Server 2013</span><span class="sxs-lookup"><span data-stu-id="b6b2e-208">Step 1: Migrate to Project Server 2013</span></span>

<span data-ttu-id="b6b2e-209">如需從 Project Server 2010 升級至 Project Server 2013 的完整資訊，請參閱 [Upgrade To Project server 2013](https://go.microsoft.com/fwlink/p/?linkid=841822)。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-209">For a comprehensive information about upgrading from Project Server 2010 to Project Server 2013, see [Upgrade to Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841822).</span></span>

<span data-ttu-id="b6b2e-210">主要資源：</span><span class="sxs-lookup"><span data-stu-id="b6b2e-210">Key resources:</span></span>

- [<span data-ttu-id="b6b2e-211">Project Server 2013 升級程式概述</span><span class="sxs-lookup"><span data-stu-id="b6b2e-211">Overview of the Project Server 2013 upgrade process</span></span>](https://go.microsoft.com/fwlink/p/?linkid=841822)

  <span data-ttu-id="b6b2e-212">取得如何從 Project Server 2010 升級至 Project Server 2013 的高層次概述。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-212">Get a high-level overview of how to upgrade from Project Server 2010 to Project Server 2013.</span></span>
- [<span data-ttu-id="b6b2e-213">規劃升級到 Project Server 2013</span><span class="sxs-lookup"><span data-stu-id="b6b2e-213">Plan to upgrade to Project Server 2013</span></span>](https://go.microsoft.com/fwlink/p/?linkid=841823)

  <span data-ttu-id="b6b2e-214">請參閱從 Project Server 2010 升級至 Project Server 2013 （包括系統需求）時的規劃考慮。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-214">Look at planning considerations when upgrading from Project Server 2010 to Project Server 2013, including system requirements.</span></span>

- <span data-ttu-id="b6b2e-215">[Project Server 2013 的新功能更新](https://go.microsoft.com/fwlink/p/?linkid=841824) 涵蓋此版本的重要變更，包括：</span><span class="sxs-lookup"><span data-stu-id="b6b2e-215">[What's new in Project Server 2013 upgrade](https://go.microsoft.com/fwlink/p/?linkid=841824) covers important changes for this version, including:</span></span>

   - <span data-ttu-id="b6b2e-216">沒有就地升級至 Project Server 2013。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-216">There's no in-place upgrade to Project Server 2013.</span></span> <span data-ttu-id="b6b2e-217">資料庫附加方法是從 Project Server 2010 升級至 Project Server 2013 的唯一支援方式。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-217">The database-attach method is the only supported way to upgrade from Project Server 2010 to Project Server 2013.</span></span>

   - <span data-ttu-id="b6b2e-218">升級程式不僅會將您的 Project Server 2010 資料轉換成 Project Server 2013 格式，還會將這四個 Project Server 2010 資料庫合併成單一 Project Web App 資料庫。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-218">The upgrade process will not only convert your Project Server 2010 data to Project Server 2013 format but will also consolidate the four Project Server 2010 databases into a single Project Web App database.</span></span>

   - <span data-ttu-id="b6b2e-219">SharePoint Server 2013 和 Project Server 2013 都變更為先前版本的宣告式驗證。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-219">Both SharePoint Server 2013 and Project Server 2013 changed to claims-based authentication from the previous version.</span></span> <span data-ttu-id="b6b2e-220">如果您使用的是傳統驗證，當您升級時，必須考慮這一點。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-220">If you're using classic authentication, you'll need to consider this when you upgrade.</span></span> <span data-ttu-id="b6b2e-221">如需詳細資訊，請參閱＜[在 SharePoint 2013 中從傳統模式移轉至宣告式驗證]( https://docs.microsoft.com/sharepoint/upgrade-and-update/migrate-from-classic-mode-to-claims-based-authentication-in-sharepoint-2013)＞。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-221">For more information, see [Migrate from classic-mode to claims-based authentication in SharePoint 2013]( https://docs.microsoft.com/sharepoint/upgrade-and-update/migrate-from-classic-mode-to-claims-based-authentication-in-sharepoint-2013).</span></span>

<span data-ttu-id="b6b2e-222">主要資源：</span><span class="sxs-lookup"><span data-stu-id="b6b2e-222">Key resources:</span></span>

- [<span data-ttu-id="b6b2e-223">升級到 Project Server 2013 的升級程序概觀</span><span class="sxs-lookup"><span data-stu-id="b6b2e-223">Overview of the upgrade process to Project Server 2013</span></span>](https://go.microsoft.com/fwlink/p/?linkid=841274)

- [<span data-ttu-id="b6b2e-224">升級您的資料庫與 Project Web App 網站集合 (Project Server 2013)</span><span class="sxs-lookup"><span data-stu-id="b6b2e-224">Upgrade your databases and Project Web App site collections (Project Server 2013)</span></span>](https://go.microsoft.com/fwlink/p/?linkid=841272)

- [<span data-ttu-id="b6b2e-225">Microsoft Project Server 升級過程圖表</span><span class="sxs-lookup"><span data-stu-id="b6b2e-225">Microsoft Project Server upgrade process diagram</span></span>](https://go.microsoft.com/fwlink/p/?linkid=841270)

- [<span data-ttu-id="b6b2e-226">極佳的資料庫整合，Project Server 2010 至2013遷移，8個簡單的步驟</span><span class="sxs-lookup"><span data-stu-id="b6b2e-226">The Great Database Consolidation, Project Server 2010 to 2013 Migration in 8 Easy Steps</span></span>](https://go.microsoft.com/fwlink/p/?linkid=841271)

### <a name="step-2-migrate-to-project-server-2016"></a><span data-ttu-id="b6b2e-227">步驟2：遷移至 Project Server 2016</span><span class="sxs-lookup"><span data-stu-id="b6b2e-227">Step 2: Migrate to Project Server 2016</span></span>

<span data-ttu-id="b6b2e-228">移至 Project Server 2013，並確認您的資料已成功遷移後，下一步是遷移至 Project Server 2016。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-228">After you move to Project Server 2013 and verify that your data has migrated successfully, the next step is to migrate to Project Server 2016.</span></span>

<span data-ttu-id="b6b2e-229">如需詳細資訊，請參閱 [升級至 Project Server 2016](https://docs.microsoft.com/Project/upgrade-to-project-server-2016)。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-229">For more information, see [Upgrade to Project Server 2016](https://docs.microsoft.com/Project/upgrade-to-project-server-2016).</span></span>

<span data-ttu-id="b6b2e-230">主要資源：</span><span class="sxs-lookup"><span data-stu-id="b6b2e-230">Key resources:</span></span>

- [<span data-ttu-id="b6b2e-231">Project Server 2016 升級程序概觀</span><span class="sxs-lookup"><span data-stu-id="b6b2e-231">Overview of the Project Server 2016 upgrade process</span></span>](https://docs.microsoft.com/Project/overview-of-the-project-server-2016-upgrade-process)

  <span data-ttu-id="b6b2e-232">瞭解從 Project Server 2013 升級至 Project Server 2016 所需執行的動作。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-232">Understand what you need to do to upgrade from Project Server 2013 to Project Server 2016.</span></span>

- [<span data-ttu-id="b6b2e-233">規劃升級到 Project Server 2016</span><span class="sxs-lookup"><span data-stu-id="b6b2e-233">Plan for upgrade to Project Server 2016</span></span>](https://docs.microsoft.com/Project/plan-for-upgrade-to-project-server-2016)

  <span data-ttu-id="b6b2e-234">請參閱從 Project Server 2013 升級至 Project Server 2016 時所應進行的規劃考慮。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-234">Look at  the planning considerations to make when upgrading from Project Server 2013 to Project Server 2016.</span></span>

<span data-ttu-id="b6b2e-235">若要[瞭解 Project Server 2016 升級的相關事項](https://docs.microsoft.com/project/plan-for-upgrade-to-project-server-2016#thingknow)，請涵蓋升級至此版本的重要變更，包括：</span><span class="sxs-lookup"><span data-stu-id="b6b2e-235">[Things you need to know about Project Server 2016 upgrade](https://docs.microsoft.com/project/plan-for-upgrade-to-project-server-2016#thingknow) covers important changes for upgrading to this version, which include:</span></span>

- <span data-ttu-id="b6b2e-236">當您建立 Project Server 2016 環境時，請注意，Project Server 2016 安裝檔會包含在 SharePoint Server 2016 中。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-236">When you create your Project Server 2016 environment, note that the Project Server 2016 installation files are included in SharePoint Server 2016.</span></span> <span data-ttu-id="b6b2e-237">如需詳細資訊，請參閱 [部署 Project Server 2016](https://go.microsoft.com/fwlink/p/?linkid=841829)。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-237">For more information, see [Deploy Project Server 2016](https://go.microsoft.com/fwlink/p/?linkid=841829).</span></span>

- <span data-ttu-id="b6b2e-238">資源計劃在 Project Server 2016 中已被取代。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-238">Resource plans are deprecated in Project Server 2016.</span></span> <span data-ttu-id="b6b2e-239">您的 Project Server 2013 資源計劃將遷移至 Project Server 2016 和 Project Online 中的資源預訂。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-239">Your Project Server 2013 resource plans will be migrated to Resource Engagements in Project Server 2016 and in Project Online.</span></span> <span data-ttu-id="b6b2e-240">如需詳細資訊，請參閱 [綜述： Resource 預訂](https://support.office.com/article/73eefb5a-81fe-42bf-980e-9532b1bdc870) 。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-240">See [Overview: Resource engagements](https://support.office.com/article/73eefb5a-81fe-42bf-980e-9532b1bdc870) for more information.</span></span>

### <a name="step-3-migrate-to-project-server-2019"></a><span data-ttu-id="b6b2e-241">步驟3：遷移至 Project Server 2019</span><span class="sxs-lookup"><span data-stu-id="b6b2e-241">Step 3: Migrate to Project Server 2019</span></span>

<span data-ttu-id="b6b2e-242">在您遷移至 Project Server 2016 並確認您的資料順利遷移後，下一步是將您的資料移轉至 Project Server 2019。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-242">After you migrate to Project Server 2016 and verify that your data migrated successfully, the next step is to migrate your data to Project Server 2019.</span></span>

<span data-ttu-id="b6b2e-243">若要瞭解從 Project Server 2016 升級至 Project Server 2019 所需執行的動作，請參閱 [升級至 Project server 2019](https://docs.microsoft.com/Project/upgrade-to-project-server-2016)。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-243">To learn what you need to do to upgrade from Project Server 2016 to Project Server 2019, see [Upgrade to Project Server 2019](https://docs.microsoft.com/Project/upgrade-to-project-server-2016).</span></span>

<span data-ttu-id="b6b2e-244">主要資源：</span><span class="sxs-lookup"><span data-stu-id="b6b2e-244">Key resources:</span></span>

- [<span data-ttu-id="b6b2e-245">Project Server 2019 升級程式概述</span><span class="sxs-lookup"><span data-stu-id="b6b2e-245">Overview of the Project Server 2019 upgrade process</span></span>](https://docs.microsoft.com/project/overview-of-the-project-server-2019-upgrade-process)

  <span data-ttu-id="b6b2e-246">深入瞭解從 Project Server 2013 升級至 Project Server 2016 所需執行的動作。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-246">Get a high-level understanding of what you need to do to upgrade from Project Server 2013 to Project Server 2016.</span></span>

- [<span data-ttu-id="b6b2e-247">規劃升級至 Project Server 2019</span><span class="sxs-lookup"><span data-stu-id="b6b2e-247">Plan for upgrade to Project Server 2019</span></span>](https://docs.microsoft.com/project/plan-for-upgrade-to-project-server-2019)

  <span data-ttu-id="b6b2e-248">請查看從 Project Server 2016 升級至 Project Server 2019 的規劃考慮。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-248">Look at planning considerations for upgrading from Project Server 2016 to Project Server 2019.</span></span>

- [<span data-ttu-id="b6b2e-249">您需要瞭解的有關 Project Server 2019 升級的事項</span><span class="sxs-lookup"><span data-stu-id="b6b2e-249">Things you need to know about Project Server 2019 upgrade</span></span>](https://go.microsoft.com/fwlink/p/?linkid=841827)<br/><br/><span data-ttu-id="b6b2e-250">深入瞭解升級至此版本的重要變更，包括：</span><span class="sxs-lookup"><span data-stu-id="b6b2e-250">Learn about important changes for upgrading to this version, which include:</span></span>

   - <span data-ttu-id="b6b2e-251">升級程式會將您的資料從 Project Server 2016 資料庫移轉至 SharePoint 伺服器2019內容資料庫。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-251">The upgrade process will migrate your data from your Project Server 2016 database to the SharePoint Server 2019 Content database.</span></span>  <span data-ttu-id="b6b2e-252">Project Server 2019 將不再在 SharePoint 伺服器陣列中建立自己的 Project Server 資料庫。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-252">Project Server 2019 will no longer create its own Project Server database in the SharePoint Server farm.</span></span>

   - <span data-ttu-id="b6b2e-253">升級之後，請留意 Project Web App 中的數項變更。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-253">After the upgrade, be aware of several changes in Project Web App.</span></span>  <span data-ttu-id="b6b2e-254">如需詳細資訊，請參閱 [Project Server 2019 的新功能](https://docs.microsoft.com/project/what-s-new-for-it-pros-in-project-server-2019#PWAChanges)。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-254">For details, see [What's new in Project Server 2019](https://docs.microsoft.com/project/what-s-new-for-it-pros-in-project-server-2019#PWAChanges).</span></span>

<span data-ttu-id="b6b2e-255">**其他資源**：</span><span class="sxs-lookup"><span data-stu-id="b6b2e-255">**Other resources**:</span></span>

- <span data-ttu-id="b6b2e-256">[Project Online 服務說明](https://go.microsoft.com/fwlink/p/?linkid=841280)：請參閱 project Server 2016 隨附的產品群組管理功能和 Project Online Premium。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-256">[Project Online Service Descriptions](https://go.microsoft.com/fwlink/p/?linkid=841280): See the portfolio management features included with Project Server 2016 and Project Online Premium.</span></span>

- [<span data-ttu-id="b6b2e-257">Microsoft Office 專案公事包伺服器2010遷移指南</span><span class="sxs-lookup"><span data-stu-id="b6b2e-257">Microsoft Office Project Portfolio Server 2010 migration guide</span></span>](https://go.microsoft.com/fwlink/p/?linkid=841279)

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a><span data-ttu-id="b6b2e-258">適用於 Office 2010 用戶端與伺服器和 Windows 7 的選項摘要</span><span class="sxs-lookup"><span data-stu-id="b6b2e-258">Summary of options for Office 2010 client and servers and Windows 7</span></span>

<span data-ttu-id="b6b2e-259">如需適用於 Office 2010 用戶端與伺服器和 Windows 7 的升級、移轉和移至雲端選項的視覺摘要，請參閱[終止支援海報](../downloads/Office2010Windows7EndOfSupport.pdf)。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-259">For a visual summary of the upgrade, migrate, and move-to-the-cloud options for Office 2010 clients and servers and Windows 7, see the [end of support poster](../downloads/Office2010Windows7EndOfSupport.pdf).</span></span>

<span data-ttu-id="b6b2e-260">[![Office 2010 用戶端和伺服器及 Windows 7 海報的支援終止](../media/upgrade-from-office-2010-servers-and-products/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)</span><span class="sxs-lookup"><span data-stu-id="b6b2e-260">[![End of support for Office 2010 clients and servers and Windows 7 poster](../media/upgrade-from-office-2010-servers-and-products/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)</span></span>

<span data-ttu-id="b6b2e-261">此海報說明您可以採取的各種途徑，以避免 Office 2010 用戶端和伺服器產品及 Windows 7 的支援終止，並反白顯示 Microsoft 365 企業版中的偏好路徑和選項支援。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-261">This poster illustrates the various paths you can take to avoid end of support for Office 2010 client and server products and Windows 7, with preferred paths and option support in Microsoft 365 Enterprise highlighted.</span></span>

<span data-ttu-id="b6b2e-262">您也可以 [下載](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) 此標牌，並以 letter、法律或卡片 (11 x 17) 格式來列印。</span><span class="sxs-lookup"><span data-stu-id="b6b2e-262">You can also [download](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) this poster and print it in letter, legal, or tabloid (11 x 17) format.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b6b2e-263">相關主題</span><span class="sxs-lookup"><span data-stu-id="b6b2e-263">Related topics</span></span>

[<span data-ttu-id="b6b2e-264">從 SharePoint 2010 升級</span><span class="sxs-lookup"><span data-stu-id="b6b2e-264">Upgrading from SharePoint 2010</span></span>](upgrade-from-sharepoint-2010.md)

[<span data-ttu-id="b6b2e-265">從 Office 2010 伺服器與用戶端升級</span><span class="sxs-lookup"><span data-stu-id="b6b2e-265">Upgrade from Office 2010 servers and clients</span></span>](upgrade-from-office-2010-servers-and-products.md)
