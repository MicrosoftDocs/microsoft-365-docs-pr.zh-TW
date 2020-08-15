---
title: 最新版本的廣泛部署範例
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
ms.custom: ''
description: 部署最新版本的組織如何使用適用於 Windows 10 和 Microsoft 365 Apps 的通道。
ms.openlocfilehash: fd1d8ddd342b2781470378c879ef70d2ba304316
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686163"
---
# <a name="example-of-broad-deployment-for-the-latest-releases"></a><span data-ttu-id="4077f-103">最新版本的廣泛部署範例</span><span class="sxs-lookup"><span data-stu-id="4077f-103">Example of broad deployment for the latest releases</span></span>

<span data-ttu-id="4077f-104">此通道組態範例適用於使用最新版本的快速部署，以符合這些商業優先順序的組織：</span><span class="sxs-lookup"><span data-stu-id="4077f-104">This channel configuration example is for an organization that uses rapid deployment of the latest releases to fit these business priorities:</span></span>

- <span data-ttu-id="4077f-105">使用 Microsoft 應用程式和服務確保業務持續性。</span><span class="sxs-lookup"><span data-stu-id="4077f-105">Ensure business continuity with Microsoft apps and services.</span></span>
- <span data-ttu-id="4077f-106">利用 Microsoft 提供的最新功能和修正功能，將裝置、服務及資料安全性最大化。</span><span class="sxs-lookup"><span data-stu-id="4077f-106">Maximize device, service, and data security with the latest features and fixes from Microsoft.</span></span>
- <span data-ttu-id="4077f-107">利用 Microsoft 提供的最新功能，將使用者生產力最大化。</span><span class="sxs-lookup"><span data-stu-id="4077f-107">Maximize user productivity with the latest features from Microsoft.</span></span>

<span data-ttu-id="4077f-108">這些目標會轉換為 IT 工作，以利用使用者和裝置的一個具代表性子集在廣泛部署之前驗證功能，找出快速生產部署與早期審查之間的平衡。</span><span class="sxs-lookup"><span data-stu-id="4077f-108">These goals translate to the IT task of finding the balance between rapid production deployment and early vetting with a representative subset of users and devices to validate functionally before broad deployment.</span></span>

<span data-ttu-id="4077f-109">我們的範例組織在全球於歐洲、非洲、亞太地區和美洲各地有 5,000 名員工。</span><span class="sxs-lookup"><span data-stu-id="4077f-109">Our example organization has 5,000 employees in buildings across the world in Europe, Africa, Asia, and the Americas.</span></span> <span data-ttu-id="4077f-110">70% 的員工使用 Microsoft 365 E3，而其餘組織使用 Microsoft 365 E5。</span><span class="sxs-lookup"><span data-stu-id="4077f-110">70% of the employees use Microsoft 365 E3 and the rest of the organization uses Microsoft 365 E5.</span></span>

>[!Note]
><span data-ttu-id="4077f-111">此範例的設計可向您說明如何使用部署階段和群組，其適用於許多類型和規模的組織。</span><span class="sxs-lookup"><span data-stu-id="4077f-111">This example is designed to show you how you can use deployment stages and groups, which can work for organizations of many types and sizes.</span></span>
>

<span data-ttu-id="4077f-112">此組織的 IT 基礎結構：</span><span class="sxs-lookup"><span data-stu-id="4077f-112">This organization's IT infrastructure:</span></span> 

- <span data-ttu-id="4077f-113">多數具同質性，使用 Windows、Microsoft 365 Apps 和 Microsoft 雲端服務，涵蓋已安裝基座的 60%。</span><span class="sxs-lookup"><span data-stu-id="4077f-113">Is largely homogeneous, with Windows, Microsoft 365 Apps, and Microsoft cloud services comprising 60% of the installed base.</span></span> <span data-ttu-id="4077f-114">在多年密集作業以簡化並改善 IT 基礎結構之後，仍存在一些舊版系統。</span><span class="sxs-lookup"><span data-stu-id="4077f-114">A few legacy systems remain after an intensive, multi-year effort to simplify and streamline the IT infrastructure.</span></span>
- <span data-ttu-id="4077f-115">由經驗豐富的人員維護，且任務目標是要透過遵循 Microsoft 在其版本的引領之下，讓使用者和其裝置具生產力且受保護。</span><span class="sxs-lookup"><span data-stu-id="4077f-115">Is maintained by highly experienced staff and tasked with keeping users and their devices productive and secure by following Microsoft’s lead in their releases.</span></span>

## <a name="deployment-and-update-stages"></a><span data-ttu-id="4077f-116">部署和更新階段</span><span class="sxs-lookup"><span data-stu-id="4077f-116">Deployment and update stages</span></span>

<span data-ttu-id="4077f-117">根據最新版本的快速部署目標，此範例組織使用雙步驟部署程序。</span><span class="sxs-lookup"><span data-stu-id="4077f-117">Based on rapid deployment goals of the latest release, this example organization uses a two-step deployment process.</span></span>

1. <span data-ttu-id="4077f-118">**使用預覽或試驗部署：** 運用早期採用者、IT 人員、具代表性組態的使用者和訓練人員進行驗證並反覆執行。</span><span class="sxs-lookup"><span data-stu-id="4077f-118">**Use a preview or pilot deployment:** Validate and iterate with early adopters, IT staff, users with representative configurations, and training staff.</span></span> 

   <span data-ttu-id="4077f-119">早期採用者、IT 人員、具代表性組態的使用者可先使用其他應用程式和裝置來驗證功能，之後再將新功能推出至組織的其餘應用程式和裝置。</span><span class="sxs-lookup"><span data-stu-id="4077f-119">The early adopters, IT staff, users with representative configurations can validate functionality with other apps and on devices before the new features roll out to the rest of the organization.</span></span>

   <span data-ttu-id="4077f-120">變更管理員可在廣泛推出之前快速瀏覽新功能，且可以規劃通知訊息和推出。</span><span class="sxs-lookup"><span data-stu-id="4077f-120">Change managers have an early peek at the new features before widespread rollout and can plan messaging and rollout.</span></span>

   <span data-ttu-id="4077f-121">訓練人員可以在廣泛推出之前，針對新功能規劃新的內部課程，或更新現有課程。</span><span class="sxs-lookup"><span data-stu-id="4077f-121">Training staff can plan new internal courses or update existing courses for the new features before widespread rollout.</span></span>

2. <span data-ttu-id="4077f-122">**生產部署：** 依地區、部門或其他部署方法向所有其餘使用者推出。</span><span class="sxs-lookup"><span data-stu-id="4077f-122">**Production deployment:** Roll out to all remaining users by region, department, or other deployment method.</span></span>

## <a name="deployment-configuration-for-windows-10"></a><span data-ttu-id="4077f-123">Windows 10 的部署組態</span><span class="sxs-lookup"><span data-stu-id="4077f-123">Deployment configuration for Windows 10</span></span>

<span data-ttu-id="4077f-124">整體目標是在驗證「發行預覽通道」變更之後，透過一組具代表性使用者及其裝置來執行最新「半年通道」發行的廣泛部署。</span><span class="sxs-lookup"><span data-stu-id="4077f-124">The overall goal is to perform a broad deployment of the latest Semi-Annual Channel release after validation of Release Preview Channel changes by a group of representative users and their devices.</span></span>

<span data-ttu-id="4077f-125">如需有關 Windows 10 部署方法和策略的詳細資訊，請參閱 [Windows 10 部署](https://docs.microsoft.com/windows/deployment/)。</span><span class="sxs-lookup"><span data-stu-id="4077f-125">See [Windows 10 deployment](https://docs.microsoft.com/windows/deployment/) for more information on Windows 10 deployment methods and strategies.</span></span>

| <span data-ttu-id="4077f-126">階段</span><span class="sxs-lookup"><span data-stu-id="4077f-126">Stage</span></span> | <span data-ttu-id="4077f-127">通道</span><span class="sxs-lookup"><span data-stu-id="4077f-127">Channel</span></span> | <span data-ttu-id="4077f-128">部署群組</span><span class="sxs-lookup"><span data-stu-id="4077f-128">Deployment group</span></span> |
|:-------|:-------|:-----|
| <span data-ttu-id="4077f-129">試驗</span><span class="sxs-lookup"><span data-stu-id="4077f-129">Pilot</span></span> |  <span data-ttu-id="4077f-130">**發行預覽通道**</span><span class="sxs-lookup"><span data-stu-id="4077f-130">**Release Preview Channel**</span></span>  <ul><li><span data-ttu-id="4077f-131">目的：部署功能更新給 IT 人員和早期採用者，以驗證具代表性的裝置和組態 (語言、協力廠商應用程式)。</span><span class="sxs-lookup"><span data-stu-id="4077f-131">Purpose: Deployment of feature updates to IT staff and early adopters for validation on representative devices and configurations (languages, 3rd party apps).</span></span> </li><li> <span data-ttu-id="4077f-132">說明：商業客戶完全符合規範並受支援，且不會計入您的支援合約。</span><span class="sxs-lookup"><span data-stu-id="4077f-132">State: Fully compliant and supported for commercial customers and it does not count against your support agreements.</span></span> </li></ul> | <span data-ttu-id="4077f-133">**Win10ReleasePreviewChannel** (範例名稱)</span><span class="sxs-lookup"><span data-stu-id="4077f-133">**Win10ReleasePreviewChannel** (example name)</span></span> <br><br> <span data-ttu-id="4077f-134">成員是包含下列項目的群組：</span><span class="sxs-lookup"><span data-stu-id="4077f-134">Members are groups containing:</span></span> <ul><li> <span data-ttu-id="4077f-135">跨部門和位置的 Windows 愛好者</span><span class="sxs-lookup"><span data-stu-id="4077f-135">Windows enthusiasts across departments and locations</span></span> </li><li> <span data-ttu-id="4077f-136">具有需要驗證組態的人員</span><span class="sxs-lookup"><span data-stu-id="4077f-136">Staff with configurations that need validation</span></span> </li><li> <span data-ttu-id="4077f-137">IT 系統管理員和 IT 部署人員</span><span class="sxs-lookup"><span data-stu-id="4077f-137">IT admins and IT deployment staff</span></span> </li><li> <span data-ttu-id="4077f-138">變更管理員</span><span class="sxs-lookup"><span data-stu-id="4077f-138">Change managers</span></span> </li><li> <span data-ttu-id="4077f-139">內部訓練人員</span><span class="sxs-lookup"><span data-stu-id="4077f-139">Internal training staff</span></span> </li></ul> |
| <span data-ttu-id="4077f-140">生產環境</span><span class="sxs-lookup"><span data-stu-id="4077f-140">Production</span></span> |  <span data-ttu-id="4077f-141">**半年通道**</span><span class="sxs-lookup"><span data-stu-id="4077f-141">**Semi-Annual Channel**</span></span>  <ul><li><span data-ttu-id="4077f-142">目的：將最新功能更新廣泛部署至組織的其餘部分。</span><span class="sxs-lookup"><span data-stu-id="4077f-142">Purpose: Broad deployment of the latest feature updates to the rest of the organization.</span></span> </li><li> <span data-ttu-id="4077f-143">說明：完全符合規範並受支援。</span><span class="sxs-lookup"><span data-stu-id="4077f-143">State: Fully compliant and supported.</span></span> </li></ul> | <span data-ttu-id="4077f-144">**Win10SemiAnnualChannel** (範例名稱)</span><span class="sxs-lookup"><span data-stu-id="4077f-144">**Win10SemiAnnualChannel** (example name)</span></span> <br><br> <span data-ttu-id="4077f-145">成員為不在 Win10ReleasePreviewChannel 群組中的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="4077f-145">Members are all users that are not in the Win10ReleasePreviewChannel group.</span></span> |
||||

<span data-ttu-id="4077f-146">此組織使用與部署半年通道發行 (例如 Windows Update 或 Windows Server Update Services) 的相同方式來部署發行預覽通道承載的最佳做法，並對這兩個通道更新套用相同原則。</span><span class="sxs-lookup"><span data-stu-id="4077f-146">This organization uses the best practice of deploying the Release Preview Channel payload in the same way as they deploy Semi-Annual Channel releases, such as Windows Update or Windows Server Update Services, and that they apply the same policies for both channel updates.</span></span>

<span data-ttu-id="4077f-147">持續更新程序：</span><span class="sxs-lookup"><span data-stu-id="4077f-147">Ongoing updates process:</span></span>

1. <span data-ttu-id="4077f-148">將發行預覽通道變更部署至 Win10ReleasePreviewChannel (範例名稱) 部署群組。</span><span class="sxs-lookup"><span data-stu-id="4077f-148">Release Preview Channel changes are deployed to the Win10ReleasePreviewChannel (example name) deployment group.</span></span>
2. <span data-ttu-id="4077f-149">Win10ReleasePreviewChannel 群組成員向 IT 部署人員確認「發行預覽通道」變更可運作，而 IT 部署人員可以向 Microsoft 提供意見反應，並等候下一個「發行預覽通道」變更，以進行其他驗證。</span><span class="sxs-lookup"><span data-stu-id="4077f-149">Win10ReleasePreviewChannel group members confirm that Release Preview Channel changes are working to IT deployment staff, who can provide feedback to Microsoft and wait for the next Release Preview Channel changes for additional validation.</span></span>
3. <span data-ttu-id="4077f-150">半年通道功能變更會部署到 Win10SemiAnnualChannel 部署群組。</span><span class="sxs-lookup"><span data-stu-id="4077f-150">Semi-Annual Channel feature changes are deployed to the Win10SemiAnnualChannel deployment group.</span></span> 

>[!Note]
><span data-ttu-id="4077f-151">雖然半年通道為建議的通道，您的 IT 部門應利用其管理工具，並決定何時在組織內部署最新的半年通道發行，然後分批推出。</span><span class="sxs-lookup"><span data-stu-id="4077f-151">While the Semi-Annual Channel is the recommended channel, your IT department should utilize their management tools and determine when to deploy the latest Semi-Annual Channel release within their organization and then roll it out in waves.</span></span>
>

## <a name="deployment-configuration-for-microsoft-365-apps"></a><span data-ttu-id="4077f-152">Microsoft 365 Apps 的部署組態</span><span class="sxs-lookup"><span data-stu-id="4077f-152">Deployment configuration for Microsoft 365 Apps</span></span>

<span data-ttu-id="4077f-153">整體目標是在驗證「目前通道 (預覽)」變更之後，透過一組具代表性使用者來執行最新「目前通道」發行的廣泛部署。</span><span class="sxs-lookup"><span data-stu-id="4077f-153">The overall goal is to perform a broad deployment of the latest Current Channel release after validation of Current Channel (Preview) changes by a group of representative users.</span></span>

<span data-ttu-id="4077f-154">如需有關 Microsoft 365 Apps 部署方法和策略的詳細資訊，請參閱 [Microsoft 365 Apps 部署](https://docs.microsoft.com/deployoffice/plan-office-365-proplus)。</span><span class="sxs-lookup"><span data-stu-id="4077f-154">See [Microsoft 365 Apps deployment](https://docs.microsoft.com/deployoffice/plan-office-365-proplus) for more information on Microsoft 365 Apps deployment methods and strategies.</span></span>

| <span data-ttu-id="4077f-155">階段</span><span class="sxs-lookup"><span data-stu-id="4077f-155">Stage</span></span> | <span data-ttu-id="4077f-156">通道</span><span class="sxs-lookup"><span data-stu-id="4077f-156">Channel</span></span> | <span data-ttu-id="4077f-157">部署群組</span><span class="sxs-lookup"><span data-stu-id="4077f-157">Deployment group</span></span> |
|:-------|:-------|:-----|
| <span data-ttu-id="4077f-158">試驗</span><span class="sxs-lookup"><span data-stu-id="4077f-158">Pilot</span></span> |  <span data-ttu-id="4077f-159">**目前通道 (預覽)**</span><span class="sxs-lookup"><span data-stu-id="4077f-159">**Current Channel (Preview)**</span></span> <ul><li> <span data-ttu-id="4077f-160">目的：{讓具代表性的一組使用者可以一瞥新 Microsoft 365 Apps 的功能} 只要功能的部署經過「目前通道 (預覽)」 使用者的測試並針對生產準備就緒，功能的部署會隨即更新。</span><span class="sxs-lookup"><span data-stu-id="4077f-160">Purpose: {give a group of representative users a sneak peek of new Microsoft 365 Apps features} Deployment of feature updates as soon as they are tested with Current Channel (Preview) users and are production-ready.</span></span> </li><li> <span data-ttu-id="4077f-161">說明：完全符合規範並受支援。</span><span class="sxs-lookup"><span data-stu-id="4077f-161">State: Fully compliant and supported.</span></span></li><li> <span data-ttu-id="4077f-162">頻率：每個月更新 2 到 3 次。</span><span class="sxs-lookup"><span data-stu-id="4077f-162">How often: Updates 2-3 times each month.</span></span> </li></ul> | <span data-ttu-id="4077f-163">**AppsCurrentChannelPreview** (範例名稱)</span><span class="sxs-lookup"><span data-stu-id="4077f-163">**AppsCurrentChannelPreview** (example name)</span></span> <br><br> <span data-ttu-id="4077f-164">成員是包含下列項目的群組：</span><span class="sxs-lookup"><span data-stu-id="4077f-164">Members are groups containing:</span></span> <ul><li> <span data-ttu-id="4077f-165">跨部門和位置的 Office 應用程式愛好者</span><span class="sxs-lookup"><span data-stu-id="4077f-165">Office apps enthusiasts across departments and locations</span></span> </li><li> <span data-ttu-id="4077f-166">具有需要驗證組態的人員</span><span class="sxs-lookup"><span data-stu-id="4077f-166">Staff with configurations that need validation</span></span> </li><li> <span data-ttu-id="4077f-167">IT 系統管理員和 IT 部署人員</span><span class="sxs-lookup"><span data-stu-id="4077f-167">IT admins and IT deployment staff</span></span> </li><li> <span data-ttu-id="4077f-168">變更管理員</span><span class="sxs-lookup"><span data-stu-id="4077f-168">Change managers</span></span> </li><li> <span data-ttu-id="4077f-169">內部訓練人員</span><span class="sxs-lookup"><span data-stu-id="4077f-169">Internal training staff</span></span> </li></ul>|
| <span data-ttu-id="4077f-170">生產環境</span><span class="sxs-lookup"><span data-stu-id="4077f-170">Production</span></span> | <span data-ttu-id="4077f-171">**目前通道**</span><span class="sxs-lookup"><span data-stu-id="4077f-171">**Current Channel**</span></span> <ul><li> <span data-ttu-id="4077f-172">目的：將最新功能更新廣泛部署至組織的其餘部分。</span><span class="sxs-lookup"><span data-stu-id="4077f-172">Purpose: Broad deployment of the latest feature updates to the rest of the organization.</span></span> </li><li> <span data-ttu-id="4077f-173">說明：完全符合規範並受支援。</span><span class="sxs-lookup"><span data-stu-id="4077f-173">State: Fully compliant and supported.</span></span> </li></ul> |  <span data-ttu-id="4077f-174">**AppsCurrentChannel** (範例名稱)</span><span class="sxs-lookup"><span data-stu-id="4077f-174">**AppsCurrentChannel** (example name)</span></span> <br><br> <span data-ttu-id="4077f-175">成員為不在 AppsCurrentChannelPreview 群組中的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="4077f-175">Members are all users that are not in the AppsCurrentChannelPreview group.</span></span> |
|||

<span data-ttu-id="4077f-176">持續更新程序：</span><span class="sxs-lookup"><span data-stu-id="4077f-176">Ongoing updates process:</span></span>

1. <span data-ttu-id="4077f-177">目前通道 (預覽) 的變更會部署至 AppsCurrentChannelPreview 部署群組。</span><span class="sxs-lookup"><span data-stu-id="4077f-177">Current Channel (Preview) changes are deployed to the AppsCurrentChannelPreview deployment group.</span></span>
2. <span data-ttu-id="4077f-178">AppsCurrentChannelPreview 群組成員向 IT 部署人員確認目前通道 (預覽) 變更可運作，而 IT 部署人員可以向 Microsoft 提供意見反應，並等候下一個「目前通道 (預覽)」發行，以進行其他驗證。</span><span class="sxs-lookup"><span data-stu-id="4077f-178">AppsCurrentChannelPreview group members confirm that Current Channel (Preview) changes are working to IT deployment staff, who can provide feedback to Microsoft and wait for the next Current Channel (Preview) release for additional validation.</span></span>
3. <span data-ttu-id="4077f-179">目前通道變更會部署至 AppsCurrentChannel 部署群組。</span><span class="sxs-lookup"><span data-stu-id="4077f-179">Current Channel changes are deployed to the AppsCurrentChannel deployment group.</span></span> 

## <a name="visual-summary"></a><span data-ttu-id="4077f-180">視覺摘要</span><span class="sxs-lookup"><span data-stu-id="4077f-180">Visual summary</span></span>

<span data-ttu-id="4077f-181">以下是此範例組織所使用的產品、通道和部署群組。</span><span class="sxs-lookup"><span data-stu-id="4077f-181">Here are the products, their channels, and the deployment groups used by this example organization.</span></span> 

![用於廣泛部署最新版本的部署群組](../media/deploy-update-channels-examples-rapid-deploy/group-summary.png)

## <a name="see-also"></a><span data-ttu-id="4077f-183">另請參閱</span><span class="sxs-lookup"><span data-stu-id="4077f-183">See also</span></span>

[<span data-ttu-id="4077f-184">部署和更新通道範例組態</span><span class="sxs-lookup"><span data-stu-id="4077f-184">Deployment and update channel example configurations</span></span>](deploy-update-channels-examples.md)

[<span data-ttu-id="4077f-185">Microsoft 365 企業版概觀</span><span class="sxs-lookup"><span data-stu-id="4077f-185">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="4077f-186">測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="4077f-186">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
