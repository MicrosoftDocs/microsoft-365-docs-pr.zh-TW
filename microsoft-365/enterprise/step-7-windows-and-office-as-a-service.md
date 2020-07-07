---
title: 步驟 7 - Windows 和 Office 服務
f1.keywords:
- NOCSH
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 05/20/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 了解如何在您的環境中準備 Windows 和 Office 服務。
ms.openlocfilehash: e9de339c6bc66e5cd3c02af5f6a53c32b7573b1f
ms.sourcegitcommit: 584e2e9db8c541fe32624acdca5e12ee327fdb63
ms.contentlocale: zh-TW
ms.lasthandoff: 06/10/2020
ms.locfileid: "44678999"
---
# <a name="step-7-windows-and-office-servicing"></a><span data-ttu-id="1c437-103">步驟 7：Windows 和 Office 服務</span><span class="sxs-lookup"><span data-stu-id="1c437-103">Step 7: Windows and Office Servicing</span></span>

![](../media/step-7-windows-and-office-as-a-service-media/step-7-windows-and-office-as-a-service-media-1.png)

<table>
<thead>
<td><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-10.png" alt="Step 7" height="144" width="144" /></td>
<td><p><span data-ttu-id="1c437-104"><strong>步驟 7：Windows 和 Office 服務</strong></span><span class="sxs-lookup"><span data-stu-id="1c437-104"><strong>Step 7: Windows and Office Servicing</strong></span></span></p>
<p><span data-ttu-id="1c437-105">Both Windows 10 and Microsoft 365 Apps for enterprise continually add new capabilities to keep bringing user experiences and security forward with the latest innovations.</span><span class="sxs-lookup"><span data-stu-id="1c437-105">Both Windows 10 and Microsoft 365 Apps for enterprise continually add new capabilities to keep bringing user experiences and security forward with the latest innovations.</span></span> <span data-ttu-id="1c437-106">Learn how to stay current with semi-annual and monthly updates, how the new servicing model works and the tools and options you have.</span><span class="sxs-lookup"><span data-stu-id="1c437-106">Learn how to stay current with semi-annual and monthly updates, how the new servicing model works and the tools and options you have.</span></span></p></td>
<td><a href="https://aka.ms/ddev7" target="_blank"><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-20.png" alt="Step 7" height="130" width="231" /></a></td>
</thead>
</table>

>[!NOTE]
><span data-ttu-id="1c437-107">Windows 和 Office 服務是我們建議的部署程序轉輪中第七個步驟，說明對功能的半年更新進行準備的規劃層面。</span><span class="sxs-lookup"><span data-stu-id="1c437-107">Windows and Office Servicing is the seventh step in our recommended deployment process wheel covering the planning aspects of preparing for semi-annual updates to features.</span></span> <span data-ttu-id="1c437-108">若要查看完整的桌面部署程序，請瀏覽[桌面部署中心](https://aka.ms/HowToShift)。</span><span class="sxs-lookup"><span data-stu-id="1c437-108">To see the full desktop deployment process, visit the [Desktop Deployment Center](https://aka.ms/HowToShift).</span></span>
>

<span data-ttu-id="1c437-109">Windows 10 與 Microsoft 365 Apps 企業版都推出了新的服務選項、支援模型和更新時間表。</span><span class="sxs-lookup"><span data-stu-id="1c437-109">Both Windows 10 and Microsoft 365 Apps for enterprise introduce new servicing options, support models, and update timelines.</span></span> <span data-ttu-id="1c437-110">這些變更可簡化隨時保有最新功能的程序。</span><span class="sxs-lookup"><span data-stu-id="1c437-110">These changes simplify the process for staying current on the latest features.</span></span> <span data-ttu-id="1c437-111">連同這些更新一起推出的是新的設定選項，其可實現符合您需求的服務方案。</span><span class="sxs-lookup"><span data-stu-id="1c437-111">Along with these updates are new configuration options to enable servicing plans that meet your needs.</span></span> <span data-ttu-id="1c437-112">讓我們了解如何準備迎接可在 Windows 10 和 Microsoft 365 Apps 企業版中提供新功能的半年通道更新，同時利用 Microsoft Endpoint Center Configuration Manager (最新分支) 內的新功能。</span><span class="sxs-lookup"><span data-stu-id="1c437-112">Let's learn how to prepare for semi-annual channel updates offering new features and capabilities in Windows 10 and Microsoft 365 Apps for enterprise while leveraging new features within Microsoft Endpoint Configuration Manager (Current Branch).</span></span>

[<span data-ttu-id="1c437-113">協助客戶改用 Windows 10 和 Microsoft 365 Apps 企業版</span><span class="sxs-lookup"><span data-stu-id="1c437-113">Helping customers shift to Windows 10 and Microsoft 365 Apps for enterprise</span></span>](https://www.microsoft.com/microsoft-365/blog/2018/09/06/helping-customers-shift-to-a-modern-desktop/)

## <a name="update-types"></a><span data-ttu-id="1c437-114">更新類型</span><span class="sxs-lookup"><span data-stu-id="1c437-114">Update Types</span></span>

<span data-ttu-id="1c437-115">更新主要可分為兩種類別，分別是功能更新以及品質和安全性更新 (包含累積安全性、可靠性和錯誤修正)。</span><span class="sxs-lookup"><span data-stu-id="1c437-115">Updates fall into two main categories, feature updates and then quality and security updates which contain cumulative security, reliability and bug fixes.</span></span> <span data-ttu-id="1c437-116">就頻率來說，Windows 和 Office 皆提供半年通道，會在每年的 3 月和 9 月分別提供新的功能，並且每個月會推出品質和安全性更新。</span><span class="sxs-lookup"><span data-stu-id="1c437-116">In terms of cadence both Windows and Office deliver a semi-annual channel which delivers new features twice per year around March and September while quality and security Updates occur Monthly.</span></span> <span data-ttu-id="1c437-117">此外，針對 Office 365 應用程式，我們還會提供完整支援的目前通道選項，其中的更新會同時包含新功能和品質更新。</span><span class="sxs-lookup"><span data-stu-id="1c437-117">Additionally, unique to Office 365 applications, we offer a fully-supported Current Channel option where updates contain both new features and quality updates.</span></span>

<span data-ttu-id="1c437-118">如果您已經習慣電腦作業系統與應用程式更新之間較長的週期，您可能會想了解：</span><span class="sxs-lookup"><span data-stu-id="1c437-118">If you’re used to a longer cycle between desktop OS and app updates, you might be wondering;</span></span>

  - <span data-ttu-id="1c437-119">更新是否相容？</span><span class="sxs-lookup"><span data-stu-id="1c437-119">Will the updates be compatible?</span></span>

  - <span data-ttu-id="1c437-120">我需要重新訓練使用者嗎？</span><span class="sxs-lookup"><span data-stu-id="1c437-120">Will I need to keep retraining my users?</span></span>

  - <span data-ttu-id="1c437-121">有哪些風險？</span><span class="sxs-lookup"><span data-stu-id="1c437-121">And what are the risks?</span></span>

<span data-ttu-id="1c437-122">若要回答這些問題以及為何更頻繁地提供新功能，我們提供這種方法的一些優點</span><span class="sxs-lookup"><span data-stu-id="1c437-122">To answer those questions and the rationale for delivering new capabilities more frequently, we’ll some of the advantages of this approach</span></span>

### <a name="feature-update-benefits"></a><span data-ttu-id="1c437-123">功能更新的優點</span><span class="sxs-lookup"><span data-stu-id="1c437-123">Feature Update Benefits</span></span>

<span data-ttu-id="1c437-124">First, we’ve moved away from the model of the past that would introduce huge waves of change around every three years to now incremental smaller changes with feature updates twice per year.</span><span class="sxs-lookup"><span data-stu-id="1c437-124">First, we’ve moved away from the model of the past that would introduce huge waves of change around every three years to now incremental smaller changes with feature updates twice per year.</span></span> <span data-ttu-id="1c437-125">Why?</span><span class="sxs-lookup"><span data-stu-id="1c437-125">Why?</span></span> <span data-ttu-id="1c437-126">With technology trends moving so fast in addition to rapidly evolving security threats, this keeps experiences and protections current.</span><span class="sxs-lookup"><span data-stu-id="1c437-126">With technology trends moving so fast in addition to rapidly evolving security threats, this keeps experiences and protections current.</span></span> <span data-ttu-id="1c437-127">Some of the security related updates for example can’t just be delivered by monthly security updates or antivirus signature files; they may be low-level changes platform, like virtualization-based security.</span><span class="sxs-lookup"><span data-stu-id="1c437-127">Some of the security related updates for example can’t just be delivered by monthly security updates or antivirus signature files; they may be low-level changes platform, like virtualization-based security.</span></span>

[<span data-ttu-id="1c437-128">Windows 即服務快速指南</span><span class="sxs-lookup"><span data-stu-id="1c437-128">Quick guide to Windows as a service</span></span>](https://docs.microsoft.com/windows/deployment/update/waas-quick-start)

[<span data-ttu-id="1c437-129">使用 Windows 10 安全性功能來降低威脅</span><span class="sxs-lookup"><span data-stu-id="1c437-129">Mitigate threats by using Windows 10 security features</span></span>](https://docs.microsoft.com/windows/security/threat-protection/overview-of-threat-mitigations-in-windows-10%20%20)

### <a name="cumulative-update-model-benefits"></a><span data-ttu-id="1c437-130">累計更新模型的優點</span><span class="sxs-lookup"><span data-stu-id="1c437-130">Cumulative Update Model Benefits</span></span>

<span data-ttu-id="1c437-131">Second delivering quality and security updates as a cumulative update package corrects many of the issues of the past.</span><span class="sxs-lookup"><span data-stu-id="1c437-131">Second delivering quality and security updates as a cumulative update package corrects many of the issues of the past.</span></span> <span data-ttu-id="1c437-132">It used to be that you might pick and choose sometimes from a dozen updates or more each month for both Windows and Office.</span><span class="sxs-lookup"><span data-stu-id="1c437-132">It used to be that you might pick and choose sometimes from a dozen updates or more each month for both Windows and Office.</span></span> <span data-ttu-id="1c437-133">As you can imagine, this creates a nearly impossible set of test matrices for support.</span><span class="sxs-lookup"><span data-stu-id="1c437-133">As you can imagine, this creates a nearly impossible set of test matrices for support.</span></span> <span data-ttu-id="1c437-134">Also, if you install a version of Windows or Office that is a year or more old, it might take hours or sometimes days to apply all updates delivered since that version was released.</span><span class="sxs-lookup"><span data-stu-id="1c437-134">Also, if you install a version of Windows or Office that is a year or more old, it might take hours or sometimes days to apply all updates delivered since that version was released.</span></span>

<span data-ttu-id="1c437-135">With the cumulative model, you’re always one update away from being current and in doing so the number of monthly updates that you need to deploy is reduced.</span><span class="sxs-lookup"><span data-stu-id="1c437-135">With the cumulative model, you’re always one update away from being current and in doing so the number of monthly updates that you need to deploy is reduced.</span></span> <span data-ttu-id="1c437-136">Each update builds upon updates from previous months and contains all of the fixes that you need to get current.</span><span class="sxs-lookup"><span data-stu-id="1c437-136">Each update builds upon updates from previous months and contains all of the fixes that you need to get current.</span></span> <span data-ttu-id="1c437-137">Cumulative updates are especially helpful when PCs has been turned off for several months because they are in storage waiting to be reassigned to a different user.</span><span class="sxs-lookup"><span data-stu-id="1c437-137">Cumulative updates are especially helpful when PCs has been turned off for several months because they are in storage waiting to be reassigned to a different user.</span></span>

### <a name="expanded-validation-of-updates"></a><span data-ttu-id="1c437-138">擴充更新驗證</span><span class="sxs-lookup"><span data-stu-id="1c437-138">Expanded Validation of Updates</span></span>

<span data-ttu-id="1c437-139">另一個優點是，在針對廣泛部署推出更新之前，我們會先透過 [Office](https://products.office.com/office-insider?tab=Windows-Desktop) 和 [Windows](https://insider.windows.com/) 的測試人員計畫發行組建，這可讓我們收集診斷資料和意見反應之後，再廣泛發行更新。</span><span class="sxs-lookup"><span data-stu-id="1c437-139">Another advantage is that, before we roll out updates for broad deployment, we first release builds via the Insider programs for [Office](https://products.office.com/office-insider?tab=Windows-Desktop) and [Windows](https://insider.windows.com/), and this allows us to gather diagnostic data and feedback ahead of us releasing updates broadly.</span></span> <span data-ttu-id="1c437-140">測試人員計畫現已對測試人員開放，因此您可事先了解更新。</span><span class="sxs-lookup"><span data-stu-id="1c437-140">Now the Insider programs are open to everyone so that you can get ahead of understanding the updates.</span></span> <span data-ttu-id="1c437-141">在更新發行時，我們會從數百萬個設定之中收到診斷資料，因此當我們實際推出更新時，品質自然會更好</span><span class="sxs-lookup"><span data-stu-id="1c437-141">By the time we release updates we will have received diagnostic data from millions of configurations, so when we do roll out updates, quality is now inherently more predictable</span></span>

<span data-ttu-id="1c437-142">還有一件事，由於 Microsoft 365 Apps 企業版測試人員組建會反映每月通道更新，如果您使用 Office 的半年通道來提供 Windows 每年兩次的功能更新，您也可以使用半年企業通道 (預覽) 版本提早驗證這些組建。</span><span class="sxs-lookup"><span data-stu-id="1c437-142">AND one more thing, because Microsoft 365 Apps for enterprise Insider builds reflect monthly channel updates, if you are using semi-annual channel for Office to deliver feature updates twice per year aligned to Windows, you can validate those builds early as well using the Semi-Annual Enterprise Channel (Preview) releases.</span></span>

### <a name="supporting-management-tools"></a><span data-ttu-id="1c437-143">支援的管理工具</span><span class="sxs-lookup"><span data-stu-id="1c437-143">Supporting Management Tools</span></span>

<span data-ttu-id="1c437-144">We've also thought through how to make the deployment of updates seamless to you.</span><span class="sxs-lookup"><span data-stu-id="1c437-144">We've also thought through how to make the deployment of updates seamless to you.</span></span> <span data-ttu-id="1c437-145">Configuration Manager (Current Branch) is updated frequently to support the roll-out of these updates to Windows and Office and any new capabilities.</span><span class="sxs-lookup"><span data-stu-id="1c437-145">Configuration Manager (Current Branch) is updated frequently to support the roll-out of these updates to Windows and Office and any new capabilities.</span></span>

[<span data-ttu-id="1c437-146">使用 Configuration Manager 來部署 Windows 10 更新</span><span class="sxs-lookup"><span data-stu-id="1c437-146">Deploy Windows 10 updates using Configuration Manager</span></span>](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager)

[<span data-ttu-id="1c437-147">使用 Configuration Manager 管理 Microsoft 365 Apps 企業版</span><span class="sxs-lookup"><span data-stu-id="1c437-147">Manage Microsoft 365 Apps for enterprise with Configuration Manager</span></span>](https://docs.microsoft.com/mem/configmgr/sum/deploy-use/manage-office-365-proplus-updates)

## <a name="overview-of-windows-and-office-channels"></a><span data-ttu-id="1c437-148">Windows 和 Office 通道的概觀</span><span class="sxs-lookup"><span data-stu-id="1c437-148">Overview of Windows and Office Channels</span></span>

<span data-ttu-id="1c437-149">Windows 10 提供三個服務通道：</span><span class="sxs-lookup"><span data-stu-id="1c437-149">Windows 10 offers three servicing channels:</span></span>

- <span data-ttu-id="1c437-150">[**Windows 測試人員計畫**](https://docs.microsoft.com/windows/deployment/update/waas-overview#windows-insider)，可供組織對下一次的功能更新所推出的功能進行測試並提供意見反應</span><span class="sxs-lookup"><span data-stu-id="1c437-150">[**Windows Insider Program**](https://docs.microsoft.com/windows/deployment/update/waas-overview#windows-insider) for organizations to test and provide feedback on features shipped in the next feature update</span></span>
- <span data-ttu-id="1c437-151">**半年通道**，每年兩次提供新的功能與功能更新版本</span><span class="sxs-lookup"><span data-stu-id="1c437-151">**Semi-Annual Channel** provides new functionality with Feature Update releases twice per year</span></span>
- <span data-ttu-id="1c437-152">**長期服務通道**，其設計僅供需要較長期服務選項的專門裝置使用</span><span class="sxs-lookup"><span data-stu-id="1c437-152">**Long Term Servicing Channel** is designed only for specialized devices needing a longer servicing option</span></span>

<span data-ttu-id="1c437-153">Microsoft 365 提供四個服務通道：</span><span class="sxs-lookup"><span data-stu-id="1c437-153">Microsoft 365 offers four servicing channels:</span></span>

- <span data-ttu-id="1c437-154">[**Office 測試人員計畫**](https://products.office.com/office-insider)，可供組織對仍在開發的最新 Office 功能進行測試並提供意見反應</span><span class="sxs-lookup"><span data-stu-id="1c437-154">[**Office Insider Program**](https://products.office.com/office-insider) for organizations to test and provide feedback on the newest Office features and functionalities still in development</span></span>
- <span data-ttu-id="1c437-155">**目前通道**，可在最新的 Office 功能可供使用時，立即提供給使用者。</span><span class="sxs-lookup"><span data-stu-id="1c437-155">**Current Channel** to provide users with the newest Office features as soon as they're available</span></span>
- <span data-ttu-id="1c437-156">**半年企業通道**，每年只會提供兩次新功能</span><span class="sxs-lookup"><span data-stu-id="1c437-156">**Semi-Annual Enterprise Channel** provides new functionality with new features only twice per year</span></span>
- <span data-ttu-id="1c437-157">**半年企業通道 (預覽)**，這是完整支援的 Office 組建，可讓試驗使用者和應用程式相容性測試者測試及驗證下一個半年企業通道</span><span class="sxs-lookup"><span data-stu-id="1c437-157">**Semi-Annual Enterprise Channel (Preview)** is a fully supported build of Office that enables pilot users and application compatibility testers to test and validate the next Semi-Annual Enterprise Channel</span></span>

<span data-ttu-id="1c437-158">如需 Windows 和 Office 服務通道的詳細資訊，請檢閱下列文件：</span><span class="sxs-lookup"><span data-stu-id="1c437-158">For detailed information about Windows and Office servicing channels please review the below documentation:</span></span>

- [<span data-ttu-id="1c437-159">Windows 即服務概觀</span><span class="sxs-lookup"><span data-stu-id="1c437-159">Overview of Windows as a Service</span></span>](https://docs.microsoft.com/windows/deployment/update/waas-overview#servicing-channels)
- [<span data-ttu-id="1c437-160">Microsoft 365 應用程式更新通道概觀</span><span class="sxs-lookup"><span data-stu-id="1c437-160">Overview of update channels for Microsoft 365 Apps</span></span>](https://docs.microsoft.com/DeployOffice/overview-update-channels#BKMK_SAC)

## <a name="phased-deployment-of-updates"></a><span data-ttu-id="1c437-161">階段式更新部署</span><span class="sxs-lookup"><span data-stu-id="1c437-161">Phased Deployment of Updates</span></span>

<span data-ttu-id="1c437-162">Now let’s shift gears to how you will roll out these updates.</span><span class="sxs-lookup"><span data-stu-id="1c437-162">Now let’s shift gears to how you will roll out these updates.</span></span> <span data-ttu-id="1c437-163">For any release, we recommend at least three deployment phases for IT – validation, piloting and broad production deployment.</span><span class="sxs-lookup"><span data-stu-id="1c437-163">For any release, we recommend at least three deployment phases for IT – validation, piloting and broad production deployment.</span></span> <span data-ttu-id="1c437-164">Once you’re up and running on Windows 10 and Microsoft 365 Apps for enterprise, you'll use monthly servicing to stay current with critical security and quality updates, then you’ll move to semi-annual servicing for new features.</span><span class="sxs-lookup"><span data-stu-id="1c437-164">Once you’re up and running on Windows 10 and Microsoft 365 Apps for enterprise, you'll use monthly servicing to stay current with critical security and quality updates, then you’ll move to semi-annual servicing for new features.</span></span>

### <a name="monthly-updating"></a><span data-ttu-id="1c437-165">每月更新</span><span class="sxs-lookup"><span data-stu-id="1c437-165">Monthly Updating</span></span>

<span data-ttu-id="1c437-166">The service model is designed so you can choose to limit the roll-out of new features to twice per year, and if needed you can even skip a semi-annual update and continue receiving quality and security updates.</span><span class="sxs-lookup"><span data-stu-id="1c437-166">The service model is designed so you can choose to limit the roll-out of new features to twice per year, and if needed you can even skip a semi-annual update and continue receiving quality and security updates.</span></span> <span data-ttu-id="1c437-167">As mentioned, the cumulative nature of monthly updates means each will increase in size per month.</span><span class="sxs-lookup"><span data-stu-id="1c437-167">As mentioned, the cumulative nature of monthly updates means each will increase in size per month.</span></span>

#### <a name="express-updates"></a><span data-ttu-id="1c437-168">快速更新</span><span class="sxs-lookup"><span data-stu-id="1c437-168">Express Updates</span></span>

<span data-ttu-id="1c437-169">Using a technology called "Express Updates" in Windows and Binary Delta Compression in Office, we can reduce the download size significantly.</span><span class="sxs-lookup"><span data-stu-id="1c437-169">Using a technology called "Express Updates" in Windows and Binary Delta Compression in Office, we can reduce the download size significantly.</span></span> <span data-ttu-id="1c437-170">In both approaches, the update engines compare what’s on the PC and finds only the differentials needed to update what’s there.</span><span class="sxs-lookup"><span data-stu-id="1c437-170">In both approaches, the update engines compare what’s on the PC and finds only the differentials needed to update what’s there.</span></span>

[<span data-ttu-id="1c437-171">說明 Windows 10 品質更新和差異結尾更新</span><span class="sxs-lookup"><span data-stu-id="1c437-171">Windows 10 quality updates explained & the end of delta updates</span></span>](https://techcommunity.microsoft.com/t5/Windows-IT-Pro-Blog/Windows-10-quality-updates-explained-amp-the-end-of-delta/ba-p/214426)

<span data-ttu-id="1c437-172">商務用 Windows Update 及 Windows Server Update Services 已長期支援快速更新，但我們目前已將該支援擴展至 Microsoft Endpoint Configuration Manager (最新分支)，因此它也可以使用快速更新。</span><span class="sxs-lookup"><span data-stu-id="1c437-172">Windows Update for Business and Windows Server Update Services have supported express updates for a long time, but we've now extended that support to Microsoft Endpoint Configuration Manager (Current Branch) so that it can also use Express Updates.</span></span>

![](../media/step-7-windows-and-office-as-a-service-media/step-7-windows-and-office-as-a-service-media-3.png)

#### <a name="binary-delta-compression"></a><span data-ttu-id="1c437-173">二進位差異壓縮</span><span class="sxs-lookup"><span data-stu-id="1c437-173">Binary Delta Compression</span></span>

<span data-ttu-id="1c437-174">只有在您從最新版本的 Microsoft 365 Apps 企業版更新時，才會使用 Office 的二進位差異壓縮，因此要使用這個方法，您需要從先前的組建更新，且無法略過更新。</span><span class="sxs-lookup"><span data-stu-id="1c437-174">Binary Delta Compression in Office is only used if you're updating from the most recent version of Microsoft 365 Apps for enterprise-- so to use this approach you need to be updating from the previous build and can’t skip updates.</span></span>

<span data-ttu-id="1c437-175">Windows and Office update channels can be managed via Configuration Manager using the standard approval and targeting process.</span><span class="sxs-lookup"><span data-stu-id="1c437-175">Windows and Office update channels can be managed via Configuration Manager using the standard approval and targeting process.</span></span> <span data-ttu-id="1c437-176">Additionally, you can use policy settings in Office and Windows to enforce update channels used, as well as related settings.</span><span class="sxs-lookup"><span data-stu-id="1c437-176">Additionally, you can use policy settings in Office and Windows to enforce update channels used, as well as related settings.</span></span>

### <a name="semi-annual-updates"></a><span data-ttu-id="1c437-177">半年更新</span><span class="sxs-lookup"><span data-stu-id="1c437-177">Semi-Annual Updates</span></span>

<span data-ttu-id="1c437-178">以上為每月更新的考量事項，現在讓我們移至較大的半年更新。</span><span class="sxs-lookup"><span data-stu-id="1c437-178">So those are your considerations for monthly updates, now let’s move to the larger, semi-annual updates.</span></span>

<span data-ttu-id="1c437-179">如同「裝置和應用程式整備」中所說明，您可以使用部署程序轉輪步驟 1 中所設定的相同整備工具，開始進行這些較大更新的準備。</span><span class="sxs-lookup"><span data-stu-id="1c437-179">As we covered in Device and App Readiness, you’ll want to begin your preparation for these larger updates using the same readiness tools we set up in Step 1 of the deployment process wheel.</span></span>

<span data-ttu-id="1c437-180">As for tooling, you can use policy settings with Windows Update for Business, software update management via Microsoft Endpoint Configuration Manager (Current Branch), Windows Server Update Services (WSUS), or update policies set by Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="1c437-180">As for tooling, you can use policy settings with Windows Update for Business, software update management via Microsoft Endpoint Configuration Manager (Current Branch), Windows Server Update Services (WSUS), or update policies set by Microsoft Intune.</span></span> <span data-ttu-id="1c437-181">If you are concerned about network bandwidth, see Step 2: Directory and Network Readiness, to learn about your options to reduce network traffic via Delivery Optimization and other peer to peer caching technologies.</span><span class="sxs-lookup"><span data-stu-id="1c437-181">If you are concerned about network bandwidth, see Step 2: Directory and Network Readiness, to learn about your options to reduce network traffic via Delivery Optimization and other peer to peer caching technologies.</span></span>

![](../media/step-7-windows-and-office-as-a-service-media/step-7-windows-and-office-as-a-service-media-4.png)

[<span data-ttu-id="1c437-182">Windows 半年通道</span><span class="sxs-lookup"><span data-stu-id="1c437-182">Windows Semi-Annual Channel</span></span>](https://docs.microsoft.com/windows/deployment/update/waas-overview#semi-annual-channel)

[<span data-ttu-id="1c437-183">Microsoft 365 Apps 企業版的半年企業通道</span><span class="sxs-lookup"><span data-stu-id="1c437-183">Semi-Annual Enterprise Channel for Microsoft 365 Apps</span></span>](https://docs.microsoft.com/DeployOffice/overview-update-channels#BKMK_SAC)

#### <a name="upgrade-task-sequences"></a><span data-ttu-id="1c437-184">升級工作順序</span><span class="sxs-lookup"><span data-stu-id="1c437-184">Upgrade Task Sequences</span></span>

<span data-ttu-id="1c437-185">透過標準軟體更新管理常式安裝較大的功能更新是受支援的選項，但許多組織會選擇使用「升級工作順序」搭配 Microsoft Endpoint Configuration Manager (最新分支) 或 Microsoft Deployment Toolkit。</span><span class="sxs-lookup"><span data-stu-id="1c437-185">Installing the larger feature updates via standard software update management routines is a supported option, but many organizations will opt to use an Upgrade Task Sequence with Microsoft Endpoint Configuration Manager (Current Branch) or the Microsoft Deployment Toolkit.</span></span>

<span data-ttu-id="1c437-186">「工作順序」可讓您在安裝功能更新之前建立自訂檢查或工作，並可讓您在更新安裝自行完成後執行自訂工作，更新後的工作可能包括在更新期間視需要暫時暫停服務、驅動程式安裝和取代、應用程式升級或工作列與 Windows 10 [開始] 個人化設定。</span><span class="sxs-lookup"><span data-stu-id="1c437-186">A Task Sequence allows you to create custom checks or tasks BEFORE to the installing the Feature Update and allows you to perform custom tasks AFTER the update installation itself has completed – post-update tasks might include temporarily suspending services if needed during the update, driver installation and replacement, application upgrades or taskbar and Windows 10 Start personalization settings.</span></span>

![](../media/step-7-windows-and-office-as-a-service-media/step-7-windows-and-office-as-a-service-media-5.png)

<span data-ttu-id="1c437-187">If you’re already using task sequences to migrate your Windows 7 machines to Windows 10 and are well-versed with those tools, this is a great place to start and provides ultimate control.</span><span class="sxs-lookup"><span data-stu-id="1c437-187">If you’re already using task sequences to migrate your Windows 7 machines to Windows 10 and are well-versed with those tools, this is a great place to start and provides ultimate control.</span></span> <span data-ttu-id="1c437-188">While you can use a single task sequence for the entire upgrade, it is quite common that organizations use two task sequences.</span><span class="sxs-lookup"><span data-stu-id="1c437-188">While you can use a single task sequence for the entire upgrade, it is quite common that organizations use two task sequences.</span></span> <span data-ttu-id="1c437-189">One task sequence for making sure the machines are ready for the upgrade, that silently pre-stages all the required setup files on target computers, and one to do the actual upgrade.</span><span class="sxs-lookup"><span data-stu-id="1c437-189">One task sequence for making sure the machines are ready for the upgrade, that silently pre-stages all the required setup files on target computers, and one to do the actual upgrade.</span></span> <span data-ttu-id="1c437-190">This approach ensures that your user productivity is less impacted.</span><span class="sxs-lookup"><span data-stu-id="1c437-190">This approach ensures that your user productivity is less impacted.</span></span>

[<span data-ttu-id="1c437-191">建立工作順序以在 Configuration Manager 中升級作業系統</span><span class="sxs-lookup"><span data-stu-id="1c437-191">Create a task sequence to upgrade an OS in Configuration Manager</span></span>](https://docs.microsoft.com/mem/configmgr/osd/deploy-use/create-a-task-sequence-to-upgrade-an-operating-system)

#### <a name="semi-annual-channel-support-for-feature-updates"></a><span data-ttu-id="1c437-192">功能更新的半年通道支援</span><span class="sxs-lookup"><span data-stu-id="1c437-192">Semi-annual channel support for feature updates</span></span>

<span data-ttu-id="1c437-193">[如 2018 年 9 月所宣布](https://www.microsoft.com/microsoft-365/blog/2018/09/06/helping-customers-shift-to-a-modern-desktop/)，半年通道更新的支援時間表將會使用下列模型。</span><span class="sxs-lookup"><span data-stu-id="1c437-193">[As announced in September 2018](https://www.microsoft.com/microsoft-365/blog/2018/09/06/helping-customers-shift-to-a-modern-desktop/), support timeline for semi-annual channel updates will use the following model.</span></span>

  - <span data-ttu-id="1c437-194">所有目前支援的 Windows 10 企業版和教育版功能更新，從版本 1607 開始，將會從原始發行日期起受到 30 個月的支援。</span><span class="sxs-lookup"><span data-stu-id="1c437-194">All currently supported feature updates of Windows 10 Enterprise and Education, starting with version 1607, will be supported for 30 months from their original release date.</span></span>

  - <span data-ttu-id="1c437-195">指定目標為 9 月的所有未來功能更新，從版本 1809 開始，將會從發行日期起受到 30 個月的支援。</span><span class="sxs-lookup"><span data-stu-id="1c437-195">All future feature updates, starting with 1809, with a targeting September will be supported for 30 months from their release date.</span></span>

  - <span data-ttu-id="1c437-196">指定目標為 3 月的未來功能更新，從版本 1903 開始，將會從發行日期起繼續受支援 18 個月。</span><span class="sxs-lookup"><span data-stu-id="1c437-196">Future feature updates targeting March and starting with 1903 will continue to be supported for 18 months from their release date.</span></span>

  - <span data-ttu-id="1c437-197">Microsoft 365 Apps 企業版的半年更新會繼續受支援 18 個月</span><span class="sxs-lookup"><span data-stu-id="1c437-197">Microsoft 365 Apps for enterprise semi-annual updates continue to be supported for 18 months</span></span>

#### <a name="additional-setup-automation-options-outside-of-task-sequences"></a><span data-ttu-id="1c437-198">工作順序以外的其他設定自動化選項</span><span class="sxs-lookup"><span data-stu-id="1c437-198">Additional setup automation options outside of task sequences</span></span>

<span data-ttu-id="1c437-199">如果您未使用「升級工作順序」，您現在可以執行自訂動作，或在套用升級之前，在預先安裝階段 (在設定執行相容性檢查之前，或在預先認可階段) 的功能更新期間套用驅動程式檔案。</span><span class="sxs-lookup"><span data-stu-id="1c437-199">If you don’t use Upgrade Task Sequences, you can now run custom actions or apply driver files during feature updates in the Pre-install phase – before setup runs its compatibility checks – or in the pre-commit phase – before the upgrade is applied.</span></span>

[<span data-ttu-id="1c437-200">Windows 10 設定 (版本 1803) 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="1c437-200">What's new in Windows 10 setup, version 1803</span></span>](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803%23windows-setup)

## <a name="next-step"></a><span data-ttu-id="1c437-201">下一步</span><span class="sxs-lookup"><span data-stu-id="1c437-201">Next Step</span></span> 

## <a name="step-8-user-communications-and-training"></a>[<span data-ttu-id="1c437-202">步驟 8：使用者的通訊和訓練</span><span class="sxs-lookup"><span data-stu-id="1c437-202">Step 8: User Communications and Training</span></span>](https://aka.ms/mdd8)

## <a name="previous-step"></a><span data-ttu-id="1c437-203">上一步</span><span class="sxs-lookup"><span data-stu-id="1c437-203">Previous Step</span></span> 

## <a name="step-6-os-deployment-and-feature-updates"></a>[<span data-ttu-id="1c437-204">步驟 6：作業系統部署與功能更新</span><span class="sxs-lookup"><span data-stu-id="1c437-204">Step 6 OS Deployment and Feature Updates</span></span>](https://aka.ms/mdd6)
