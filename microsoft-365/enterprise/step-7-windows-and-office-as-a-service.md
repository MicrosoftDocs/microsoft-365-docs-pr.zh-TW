---
title: 步驟 7 - Windows 和 Office 即服務
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 09/14/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 了解如何在您的環境中準備 Windows 和 Office 即服務。
ms.openlocfilehash: 5c3eb54e07b1cc5492a6d938e97286283fc47ca7
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866513"
---
# <a name="step-7-windows-and-office-as-a-service"></a><span data-ttu-id="938bf-103">步驟 7：Windows 和 Office 即服務</span><span class="sxs-lookup"><span data-stu-id="938bf-103">Step 7: Windows and Office as a Service</span></span>

<span data-ttu-id="938bf-104">準備迎接半年通道更新與 Windows 10 和 Office 365 專業增強版的新功能，以及 System Center Configuration Manager 最新分支管理工具的對應更新。</span><span class="sxs-lookup"><span data-stu-id="938bf-104">Prepare for semi-annual channel updates with new features and capabilities in Windows 10 and Office 365 ProPlus along with corresponding updates to management tools with System Center Configuration Manager Current Branch.</span></span>

![](media/step-7-windows-and-office-as-a-service-media/step-7-windows-and-office-as-a-service-media-1.png)

<table>
<thead>
<td><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-10.png" alt="Step 7" height="144" width="144" /></td>
<td><p><span data-ttu-id="938bf-105"><strong>步驟 7：準備 Windows 和 Office 即服務</strong></span><span class="sxs-lookup"><span data-stu-id="938bf-105"><strong>Step 7: Preparing for Windows and Office as a Service</strong></span></span></p>
<p><span data-ttu-id="938bf-p101">Windows 10 和 Office 365 專業增強版都會持續新增功能，以最新的發明帶領使用者體驗和安全性前進。深入了解如何保持在最新的半年和每月更新、新服務模型如何運作，以及您所擁有的工具和選項。</span><span class="sxs-lookup"><span data-stu-id="938bf-p101">Both Windows 10 and Office 365 ProPlus continually add new capabilities to keep bringing user experiences and security forward with the latest innovations. Learn how to stay current with semi-annual and monthly updates, how the new servicing model works and the tools and options you have.</span></span></p></td>
<td><a href="https://aka.ms/ddev7" target="_blank"><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-20.png" alt="Step 7" height="130" width="231" /></a></td>
</thead>
</table>

>[!NOTE]
><span data-ttu-id="938bf-p102">Windows 與 Office 即服務是我們建議的部署程序轉輪中第七個步驟，說明對功能的半年更新進行準備的規劃層面。若要查看完整的桌面部署程序，請瀏覽[現代化電腦的部署中心](https://aka.ms/HowToShift) (英文)。</span><span class="sxs-lookup"><span data-stu-id="938bf-p102">Windows and Office as a Service is the seventh step in our recommended deployment process wheel covering the planning aspects of preparing for semi-annual updates to features. To see the full desktop deployment process, visit the [Modern Desktop Deployment Center](https://aka.ms/HowToShift).</span></span>
>

<span data-ttu-id="938bf-p103">Windows 10 和 Office 365 專業增強版引入新的服務選項、支援模型及更新時間表。這些變更簡化程序來維持目前的最新功能。除了這些更新以外還有新的設定選項，以提供符合您需求的服務方案。</span><span class="sxs-lookup"><span data-stu-id="938bf-p103">Both Windows 10 and Office 365 ProPlus introduce new servicing options, support models and update timelines. These changes simplify the process for staying current on the latest features. Along with these updates are new configuration options to enable servicing plans that meet your needs.</span></span>

<span data-ttu-id="938bf-113">[協助客戶移至現代化桌面](https://www.microsoft.com/zh-TW/microsoft-365/blog/2018/09/06/helping-customers-shift-to-a-modern-desktop/) (英文)</span><span class="sxs-lookup"><span data-stu-id="938bf-113">[Helping customers shift to a modern desktop](https://www.microsoft.com/zh-TW/microsoft-365/blog/2018/09/06/helping-customers-shift-to-a-modern-desktop/)</span></span>

## <a name="update-types"></a><span data-ttu-id="938bf-114">更新類型</span><span class="sxs-lookup"><span data-stu-id="938bf-114">Update Types</span></span>

<span data-ttu-id="938bf-p104">更新可分為兩種主要類別：功能更新以及包含累計安全性、可靠性和錯誤修正的品質和安全性更新。以頻率而言，Windows 和 Office 提供半年通道，每年在 3 月和 9 月時會提供新功能兩次，而品質和安全性更新則是每月提供。此外，Office 365 應用程式特別的是，我們提供每月通道更新，受到完整支援並包含新功能和品質更新。</span><span class="sxs-lookup"><span data-stu-id="938bf-p104">Updates fall into two main categories, feature updates and then quality and security updates which contain cumulative security, reliability and bug fixes. In terms of cadence both Windows and Office deliver a semi-annual channel which delivers new features twice per year around March and September while Quality and Security Updates occur Monthly. Additionally, unique to Office 365 Apps, we deliver Monthly Channel updates that are fully-supported and contain both new features and quality updates.</span></span>

<span data-ttu-id="938bf-118">如果您已經習慣電腦作業系統與應用程式更新之間較長的週期，您可能會想了解：</span><span class="sxs-lookup"><span data-stu-id="938bf-118">If you’re used to a longer cycle between desktop OS and app updates, you might be wondering;</span></span>

  - <span data-ttu-id="938bf-119">更新是否相容？</span><span class="sxs-lookup"><span data-stu-id="938bf-119">Will the updates be compatible?</span></span>

  - <span data-ttu-id="938bf-120">我需要重新訓練使用者嗎？</span><span class="sxs-lookup"><span data-stu-id="938bf-120">Will I need to keep retraining my users?</span></span>

  - <span data-ttu-id="938bf-121">有哪些風險？</span><span class="sxs-lookup"><span data-stu-id="938bf-121">And what are the risks?</span></span>

<span data-ttu-id="938bf-122">若要回答這些問題以及為何更頻繁地提供新功能，我們提供這種方法的一些優點</span><span class="sxs-lookup"><span data-stu-id="938bf-122">To answer those questions and the rationale for delivering new capabilities more frequently, we’ll some of the advantages of this approach</span></span>

### <a name="feature-update-benefits"></a><span data-ttu-id="938bf-123">功能更新的優點</span><span class="sxs-lookup"><span data-stu-id="938bf-123">Feature Update Benefits</span></span>

<span data-ttu-id="938bf-p105">首先，我們已經捨棄過去的模型，過去約每隔三年會引入大型變更，現在則是增量的小型變更，以及每年兩次的功能更新。為什麼？由於技術趨勢變動快速，加上快速發展的安全性威脅，這麼做可讓體驗和保護維持在最新狀態。舉例來說，部分安全性相關的更新，無法只藉由每月的安全性更新或防毒簽章檔案來提供；它們可能是低階變更平台，如虛擬化型安全性。</span><span class="sxs-lookup"><span data-stu-id="938bf-p105">First, we’ve moved away from the model of the past that would introduce huge waves of change around every three years to now incremental smaller changes with feature updates twice per year. Why? With technology trends moving so fast in addition to rapidly evolving security threats, this keeps experiences and protections current. Some of the security related updates for example can’t just be delivered by monthly security updates or antivirus signature files; they may be low-level changes platform, like virtualization-based security.</span></span>

<span data-ttu-id="938bf-128">[Windows 即服務快速指南](https://docs.microsoft.com/zh-TW/windows/deployment/update/waas-quick-start) (機器翻譯)</span><span class="sxs-lookup"><span data-stu-id="938bf-128">[Quick guide to Windows as a service](https://docs.microsoft.com/zh-TW/windows/deployment/update/waas-quick-start)</span></span>

[<span data-ttu-id="938bf-129">使用 Windows 10 安全性功能來降低威脅</span><span class="sxs-lookup"><span data-stu-id="938bf-129">Mitigate threats by using Windows 10 security features</span></span>](https://docs.microsoft.com/zh-TW/windows/security/threat-protection/overview-of-threat-mitigations-in-windows-10%20%20)

### <a name="cumulative-update-model-benefits"></a><span data-ttu-id="938bf-130">累計更新模型的優點</span><span class="sxs-lookup"><span data-stu-id="938bf-130">Cumulative Update Model Benefits</span></span>

<span data-ttu-id="938bf-p106">第二，以累計更新套件的方式提供品質和安全性更新可修正許多過去的問題。過去，有時您可能每個月要為 Windows 和 Office 從十幾個或更多的更新中進行挑選。可以想像，這會是一組幾乎無法支援的測試矩陣。此外，如果您安裝的 Windows 或 Office 版本已經過一年或者更舊，可能需要數小時或甚至數日來套用自該版本發行後提供的所有更新。</span><span class="sxs-lookup"><span data-stu-id="938bf-p106">Second delivering quality and security updates as a cumulative update package corrects many of the issues of the past. It used to be that you might pick and choose sometimes from a dozen updates or more each month for both Windows and Office. As you can imagine, this creates a nearly impossible set of test matrices for support. Also, if you install a version of Windows or Office that is a year or more old, it might take hours or sometimes days to apply all updates delivered since that version was released.</span></span>

<span data-ttu-id="938bf-p107">使用累計模型，您只需要一次更新就能保持在目前最新狀態，如此可減少您需要部署的每月更新數。每個更新都建立在前幾個月的更新之上，且包含保持在最新狀態所需的所有修正程式。當電腦已關閉數個月，在儲存狀態中等待重新指派給其他使用者時，累計更新特別有幫助。</span><span class="sxs-lookup"><span data-stu-id="938bf-p107">With the cumulative model, you’re always one update away from being current and in doing so the number of monthly updates that you need to deploy is reduced. Each update builds upon updates from previous months and contains all of the fixes that you need to get current. Cumulative updates are especially helpful when PCs has been turned off for several months because they are in storage waiting to be reassigned to a different user.</span></span>

<span data-ttu-id="938bf-138">[Windows 即服務概觀](https://docs.microsoft.com/zh-TW/windows/deployment/update/waas-overview) (機器翻譯)</span><span class="sxs-lookup"><span data-stu-id="938bf-138">[Overivew of Windows as a service](https://docs.microsoft.com/zh-TW/windows/deployment/update/waas-overview)</span></span>

### <a name="expanded-validation-of-updates"></a><span data-ttu-id="938bf-139">擴充更新驗證</span><span class="sxs-lookup"><span data-stu-id="938bf-139">Expanded Validation of Updates</span></span>

<span data-ttu-id="938bf-p108">另一個優點是，在推出用於廣泛部署的更新之前，我們會先透過「[Office](https://products.office.com/en-us/office-insider?tab=Windows-Desktop) 與 [Windows](https://insider.windows.com/zh-TW/) 測試人員計畫」發行組建，這可讓我們在廣泛發行更新之前收集遙測和意見反應。現在測試人員計畫已開放給所有人，讓您可以提早了解更新。等到發行更新時，我們將已從數百萬個設定收到遙測，因此在實際推出更新時，就較能夠掌握品質。</span><span class="sxs-lookup"><span data-stu-id="938bf-p108">Another advantage is that, before we roll out updates for broad deployment, we first release builds via the Insider programs for [Office](https://products.office.com/en-us/office-insider?tab=Windows-Desktop) and [Windows](https://insider.windows.com/zh-TW/), and this allows us to gather telemetry and feedback ahead of us releasing updates broadly. Now the Insider programs are open to everyone so that you can get ahead of understanding the updates. By the time we release updates we will have received telemetry from millions of configurations, so when we do roll out updates, quality is now inherently more predictable</span></span>

<span data-ttu-id="938bf-143">還有一件事，由於 Office 365 專業增強版測試人員組建會反映每月通道更新，如果您使用 Office 的半年通道來提供 Windows 每年兩次的功能更新，您也可以使用半年通道目標版本提早驗證這些組建。</span><span class="sxs-lookup"><span data-stu-id="938bf-143">AND one more thing, because Office 365 ProPlus Insider builds reflect monthly channel updates, if you are using semi-annual channel for Office to deliver feature updates twice per year aligned to Windows, you can validate those builds early as well using the semi-annual channel targeted releases.</span></span>

### <a name="supporting-management-tools"></a><span data-ttu-id="938bf-144">支援的管理工具</span><span class="sxs-lookup"><span data-stu-id="938bf-144">Supporting Management Tools</span></span>

<span data-ttu-id="938bf-p109">我們也思考如何讓您的更新部署更順利。System Center Configuration Manager 最新分支會經常更新，以支援推出這些 Windows 和 Office 更新以及任何新功能。</span><span class="sxs-lookup"><span data-stu-id="938bf-p109">We've also thought through how to make the deployment of updates seamless to you. System Center Configuration Manager Current Branch is updated frequently to support the roll-out of these updates to Windows and Office and any new capabilities.</span></span>

<span data-ttu-id="938bf-147">[使用 System Center Configuration Manager 來部署 Windows 10 更新](https://docs.microsoft.com/zh-TW/windows/deployment/update/waas-manage-updates-configuration-manager) (機器翻譯)</span><span class="sxs-lookup"><span data-stu-id="938bf-147">[Deploy Windows 10 updates using System Center Configuration Manager](https://docs.microsoft.com/zh-TW/windows/deployment/update/waas-manage-updates-configuration-manager)</span></span>

[<span data-ttu-id="938bf-148">使用 Configuration Manager 管理 Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="938bf-148">Manage Office 365 ProPlus with Configuration Manager</span></span>](https://docs.microsoft.com/zh-TW/sccm/sum/deploy-use/manage-office-365-proplus-updates)

## <a name="phased-deployment-of-updates"></a><span data-ttu-id="938bf-149">階段式更新部署</span><span class="sxs-lookup"><span data-stu-id="938bf-149">Phased Deployment of Updates</span></span>

<span data-ttu-id="938bf-p110">現在讓我們來看如何推出這些更新。在任何版本中，我們建議您至少要有三個 IT 部署階段 - 驗證、試驗和廣泛生產部署。當您開始執行 Windows 10 與 Office 365 專業增強版，您將會使用每月服務透過重要安全性和品質更新維持在最新狀態，然後移至半年服務以取得新功能。</span><span class="sxs-lookup"><span data-stu-id="938bf-p110">Now let’s shift gears to how you will roll out these updates. For any release, we recommend at least three deployment phases for IT – validation, piloting and broad production deployment. Once you’re up and running on Windows 10 and Office 365 ProPlus, you'll use monthly servicing to stay current with critical security and quality updates, then you’ll move to semi-annual servicing for new features.</span></span>

### <a name="monthly-updating"></a><span data-ttu-id="938bf-153">每月更新</span><span class="sxs-lookup"><span data-stu-id="938bf-153">Monthly Updating</span></span>

<span data-ttu-id="938bf-p111">服務模型的設計讓您可以選擇將新功能的推出限制為每年兩次，且視需要您可以略過半年更新，並繼續接收品質和安全性更新。如上所述，每月更新的累計性表示每次更新在每個月大小會增加。</span><span class="sxs-lookup"><span data-stu-id="938bf-p111">The service model is designed so you can choose to limit the roll-out of new features to twice per year, and if needed you can even skip a semi-annual update and continue receiving quality and security updates. As mentioned, the cumulative nature of monthly updates means each will increase in size per month.</span></span>

#### <a name="express-updates"></a><span data-ttu-id="938bf-156">快速更新</span><span class="sxs-lookup"><span data-stu-id="938bf-156">Express Updates</span></span>

<span data-ttu-id="938bf-p112">使用 Windows 中稱為「快速更新」的技術和 Office 中的「二進位差異壓縮」，我們可以大幅縮減下載大小。在這兩種方法中，更新引擎會比較電腦上的內容，並僅尋找需要更新的差異。</span><span class="sxs-lookup"><span data-stu-id="938bf-p112">Using a technology called "Express Updates" in Windows and Binary Delta Compression in Office, we can reduce the download size significantly. In both approaches, the update engines compare what’s on the PC and finds only the differentials needed to update what’s there.</span></span>

[<span data-ttu-id="938bf-159">說明 Windows 10 品質更新和差異結尾更新</span><span class="sxs-lookup"><span data-stu-id="938bf-159">Windows 10 quality updates explained & the end of delta updates</span></span>](https://techcommunity.microsoft.com/t5/Windows-IT-Pro-Blog/Windows-10-quality-updates-explained-amp-the-end-of-delta/ba-p/214426)

<span data-ttu-id="938bf-160">商務用 Windows Update 及 Windows Server Update Services 已長期支援快速更新，但我們目前已將該支援擴展至 System Center Configuration Manager，因此它也可以使用快速更新。</span><span class="sxs-lookup"><span data-stu-id="938bf-160">Windows Update for Business and Windows Server Update Services have supported express updates for a long time, but we've now extended that support to System Center Configuration Manager so that it can also use Express Updates.</span></span>

![](media/step-7-windows-and-office-as-a-service-media/step-7-windows-and-office-as-a-service-media-3.png)

#### <a name="binary-delta-compression"></a><span data-ttu-id="938bf-161">二進位差異壓縮</span><span class="sxs-lookup"><span data-stu-id="938bf-161">Binary Delta Compression</span></span>

<span data-ttu-id="938bf-162">如果您要從最新版本的 Office 365 專業增強版進行更新，才會使用 Office 的二進位差異壓縮，因此要使用這個方法您需要從先前的組建更新，且無法略過更新。</span><span class="sxs-lookup"><span data-stu-id="938bf-162">Binary Delta Compression in Office is only used if you're updating from the most recent version of Office 365 ProPlus-- so to use this approach you need to be updating from the previous build and can’t skip updates.</span></span>

<span data-ttu-id="938bf-p113">Windows 和 Office 更新通道可使用標準的核准和目標設定程序，透過 Configuration Manager 進行管理。此外，您可以使用 Office 和 Windows 中的原則設定，以強制使用更新通道以及相關設定。</span><span class="sxs-lookup"><span data-stu-id="938bf-p113">Windows and Office update channels can be managed via Configuration Manager using the standard approval and targeting process. Additionally, you can use policy settings in Office and Windows to enforce update channels used, as well as related settings.</span></span>

### <a name="semi-annual-updates"></a><span data-ttu-id="938bf-165">半年更新</span><span class="sxs-lookup"><span data-stu-id="938bf-165">Semi-Annual Updates</span></span>

<span data-ttu-id="938bf-166">以上為每月更新的考量事項，現在讓我們移至較大的半年更新。</span><span class="sxs-lookup"><span data-stu-id="938bf-166">So those are your considerations for monthly updates, now let’s move to the larger, semi-annual updates.</span></span>

<span data-ttu-id="938bf-167">如同「裝置和應用程式整備」中所說明，您可以使用部署程序轉輪步驟 1 中所設定的相同整備工具，開始進行這些較大更新的準備。</span><span class="sxs-lookup"><span data-stu-id="938bf-167">As we covered in Device and App Readiness, you’ll want to begin your preparation for these larger updates using the same readiness tools we set up in Step 1 of the deployment process wheel.</span></span>

<span data-ttu-id="938bf-p114">對於工具，您可以使用原則設定與商務用 Windows Update、透過 System Center Configuration Manager 的軟體更新管理、Windows Server Update Services (WSUS)，或 Microsoft Intune 所設定的更新原則。如果您擔心網路頻寬，請參閱步驟 2：目錄和網路整備，以了解透過傳遞最佳化和其他對等快取技術降低網路流量的選項。</span><span class="sxs-lookup"><span data-stu-id="938bf-p114">As for tooling, you can use policy settings with Windows Update for Business, software update management via System Center Configuration Manager, Windows Server Update Services (WSUS), or update policies set by Microsoft Intune. If you are concerned about network bandwidth, see Step 2: Directory and Network Readiness, to learn about your options to reduce network traffic via Delivery Optimization and other peer to peer caching technologies.</span></span>

![](media/step-7-windows-and-office-as-a-service-media/step-7-windows-and-office-as-a-service-media-4.png)

[<span data-ttu-id="938bf-170">Windows 半年通道</span><span class="sxs-lookup"><span data-stu-id="938bf-170">Windows Semi-Annual Channel</span></span>](https://docs.microsoft.com/zh-TW/windows/deployment/update/waas-overview#semi-annual-channel)

[<span data-ttu-id="938bf-171">Office 365 專業增強版的半年通道</span><span class="sxs-lookup"><span data-stu-id="938bf-171">Semi-Annual Channel for Office 365 ProPlus</span></span>](https://docs.microsoft.com/zh-TW/DeployOffice/overview-of-update-channels-for-office-365-proplus#BKMK_SAC)

#### <a name="upgrade-task-sequences"></a><span data-ttu-id="938bf-172">升級工作順序</span><span class="sxs-lookup"><span data-stu-id="938bf-172">Upgrade Task Sequences</span></span>

<span data-ttu-id="938bf-173">透過標準軟體更新管理常式安裝較大的功能更新是受支援的選項，但許多組織會選擇使用「升級工作順序」搭配 System Center Configuration Manager 或 Microsoft Deployment Toolkit。</span><span class="sxs-lookup"><span data-stu-id="938bf-173">Installing the larger feature updates via standard software update management routines is a supported option, but many organizations will opt to use an Upgrade Task Sequence with System Center Configuration Manager or the Microsoft Deployment Toolkit.</span></span>

<span data-ttu-id="938bf-174">「工作順序」可讓您在安裝功能更新之前建立自訂檢查或工作，並可讓您在更新安裝自行完成後執行自訂工作，更新後的工作可能包括在更新期間視需要暫時暫停服務、驅動程式安裝和取代、應用程式升級或工作列與 Windows 10 [開始] 個人化設定。</span><span class="sxs-lookup"><span data-stu-id="938bf-174">A Task Sequence allows you to create custom checks or tasks BEFORE to the installing the Feature Update and allows you to perform custom tasks AFTER the update installation itself has completed – post-update tasks might include temporarily suspending services if needed during the update, driver installation and replacement, application upgrades or taskbar and Windows 10 Start personalization settings.</span></span>

![](media/step-7-windows-and-office-as-a-service-media/step-7-windows-and-office-as-a-service-media-5.png)

<span data-ttu-id="938bf-p115">如果您已使用工作順序將 Windows 7 電腦移轉到 Windows 10，且您很熟悉這些工具，則這是很好的起點，並可提供最終的控制。雖然您可以針對整個升級使用單一工作順序，組織使用兩個工作順序是很常見的。其中一個工作順序用來確定電腦已準備好升級，可自動在目標電腦上將所有必要的安裝檔案預先區分階段，另一個則執行實際的升級。這個方法可確保使用者生產力較不會受到影響。</span><span class="sxs-lookup"><span data-stu-id="938bf-p115">If you’re already using task sequences to migrate your Windows 7 machines to Windows 10 and are well-versed with those tools, this is a great place to start and provides ultimate control. While you can use a single task sequence for the entire upgrade, it is quite common that organizations use two task sequences. One task sequence for making sure the machines are ready for the upgrade, that silently pre-stages all the required setup files on target computers, and one to do the actual upgrade. This approach ensures that your user productivity is less impacted.</span></span>

<span data-ttu-id="938bf-179">[建立工作順序以在 Configuration Manager 中升級作業系統](https://docs.microsoft.com/zh-TW/sccm/osd/deploy-use/create-a-task-sequence-to-upgrade-an-operating-system) (英文)</span><span class="sxs-lookup"><span data-stu-id="938bf-179">[Create a task sequence to upgrade an OS in Configuration Manager](https://docs.microsoft.com/zh-TW/sccm/osd/deploy-use/create-a-task-sequence-to-upgrade-an-operating-system)</span></span>

#### <a name="semi-annual-channel-support-for-feature-updates"></a><span data-ttu-id="938bf-180">功能更新的半年通道支援</span><span class="sxs-lookup"><span data-stu-id="938bf-180">Semi-annual channel support for feature updates</span></span>

<span data-ttu-id="938bf-181">[如 2018 年 9 月所宣布](https://www.microsoft.com/zh-TW/microsoft-365/blog/2018/09/06/helping-customers-shift-to-a-modern-desktop/)，半年通道更新的支援時間表將會使用下列模型。</span><span class="sxs-lookup"><span data-stu-id="938bf-181">[As announced in September 2018](https://www.microsoft.com/zh-TW/microsoft-365/blog/2018/09/06/helping-customers-shift-to-a-modern-desktop/), support timeline for semi-annual channel updates will use the following model.</span></span>

  - <span data-ttu-id="938bf-182">所有目前支援的 Windows 10 企業版和教育版功能更新，從版本 1607 開始，將會從原始發行日期起受到 30 個月的支援。</span><span class="sxs-lookup"><span data-stu-id="938bf-182">All currently supported feature updates of Windows 10 Enterprise and Education, starting with version 1607, will be supported for 30 months from their original release date.</span></span>

  - <span data-ttu-id="938bf-183">指定目標為 9 月的所有未來功能更新，從版本 1809 開始，將會從發行日期起受到 30 個月的支援。</span><span class="sxs-lookup"><span data-stu-id="938bf-183">All future feature updates, starting with 1809, with a targeting September will be supported for 30 months from their release date.</span></span>

  - <span data-ttu-id="938bf-184">指定目標為 3 月的未來功能更新，從版本 1903 開始，將會從發行日期起繼續受支援 18 個月。</span><span class="sxs-lookup"><span data-stu-id="938bf-184">Future feature updates targeting March and starting with 1903 will continue to be supported for 18 months from their release date.</span></span>

  - <span data-ttu-id="938bf-185">Office 365 專業增強版的半年更新會繼續受支援 18 個月</span><span class="sxs-lookup"><span data-stu-id="938bf-185">Office 365 ProPlus semi-annual updates continue to be supported for 18 months</span></span>

#### <a name="additional-setup-automation-options-outside-of-task-sequences"></a><span data-ttu-id="938bf-186">工作順序以外的其他設定自動化選項</span><span class="sxs-lookup"><span data-stu-id="938bf-186">Additional setup automation options outside of task sequences</span></span>

<span data-ttu-id="938bf-187">如果您未使用「升級工作順序」，您現在可以執行自訂動作，或在套用升級之前，在預先安裝階段 (在設定執行相容性檢查之前，或在預先認可階段) 的功能更新期間套用驅動程式檔案。</span><span class="sxs-lookup"><span data-stu-id="938bf-187">If you don’t use Upgrade Task Sequences, you can now run custom actions or apply driver files during feature updates in the Pre-install phase – before setup runs its compatibility checks – or in the pre-commit phase – before the upgrade is applied.</span></span>

[<span data-ttu-id="938bf-188">Windows 10 設定 (版本 1803) 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="938bf-188">What's new in Windows 10 setup, version 1803</span></span>](https://docs.microsoft.com/zh-TW/windows/whats-new/whats-new-windows-10-version-1803%23windows-setup)

## <a name="next-step"></a><span data-ttu-id="938bf-189">下一步</span><span class="sxs-lookup"><span data-stu-id="938bf-189">Next Step</span></span> 

## <a name="step-8-user-communications-and-traininghttpsakamsmdd8"></a><span data-ttu-id="938bf-190">[步驟 8：使用者的通訊和訓練](https://aka.ms/mdd8) (英文)</span><span class="sxs-lookup"><span data-stu-id="938bf-190">[Step 8: User Communications and Training](https://aka.ms/mdd8)</span></span>

## <a name="previous-step"></a><span data-ttu-id="938bf-191">上一步</span><span class="sxs-lookup"><span data-stu-id="938bf-191">Previous Step</span></span> 

## <a name="step-6-os-deployment-and-feature-updateshttpsakamsmdd6"></a><span data-ttu-id="938bf-192">[步驟 6：作業系統部署與功能更新](https://aka.ms/mdd6) (英文)</span><span class="sxs-lookup"><span data-stu-id="938bf-192">[Step 6 OS Deployment and Feature Updates](https://aka.ms/mdd6)</span></span>