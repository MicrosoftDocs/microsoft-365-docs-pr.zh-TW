---
title: 移轉至 Microsoft 365 企業版
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: 在整個組織中逐步執行將 Microsoft Office、Office 伺服器及 Windows 的各版本移轉為 Microsoft 365 企業版的程序。
ms.openlocfilehash: 6830b4627eea799e18d32d3f9150617df339d7d4
ms.sourcegitcommit: bd8d55f82ca008af1b93a9bb4d1545f68e8188ad
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2020
ms.locfileid: "44011792"
---
# <a name="migration-to-microsoft-365-enterprise"></a><span data-ttu-id="b9968-103">移轉至 Microsoft 365 企業版</span><span class="sxs-lookup"><span data-stu-id="b9968-103">Migration to Microsoft 365 Enterprise</span></span>

<span data-ttu-id="b9968-p101">大多數的企業組織擁有異質環境，其中具有多種版本的作業系統、用戶端軟體及伺服器軟體。Microsoft 365 企業版包含 IT 基礎結構中這些主要元件最安全的版本，且具有專為充分利用雲端技術所設計的生產力功能。</span><span class="sxs-lookup"><span data-stu-id="b9968-p101">Most enterprise organizations have a heterogeneous environment with multiple releases of operating systems, client software, and server software. Microsoft 365 Enterprise includes the most secure versions of these key components of your IT infrastructure with productivity features that are designed to take advantage of cloud technologies.</span></span>

<span data-ttu-id="b9968-106">若要充分發揮 Microsoft 365 企業版產品整合套件的商務價值，請開始規劃並實作策略以移轉以下版本：</span><span class="sxs-lookup"><span data-stu-id="b9968-106">To maximize the business value of the Microsoft 365 Enterprise integrated suite of products, begin planning and implementing a strategy to migrate releases of:</span></span>

- <span data-ttu-id="b9968-107">將安裝在您電腦上的 Office 用戶端移轉為 Microsoft 365 Apps 企業版</span><span class="sxs-lookup"><span data-stu-id="b9968-107">The Office client installed on your computers to Microsoft 365 Apps for enterprise</span></span>
- <span data-ttu-id="b9968-108">將安裝在您伺服器上的 Office 伺服器移轉為 Office 365 中的對等服務</span><span class="sxs-lookup"><span data-stu-id="b9968-108">Office servers installed on your servers to their equivalent services in Office 365</span></span>
- <span data-ttu-id="b9968-109">將裝置上的 Windows 7 和 Windows 8.1 移轉為 Windows 10 企業版</span><span class="sxs-lookup"><span data-stu-id="b9968-109">Windows 7 and Windows 8.1 on your devices to Windows 10 Enterprise</span></span>

>[!Note]
><span data-ttu-id="b9968-110">Windows 7 已於 **2020 年 1 月 14 日**終止支援。</span><span class="sxs-lookup"><span data-stu-id="b9968-110">Windows 7 reached end of support on **January 14, 2020**.</span></span> <span data-ttu-id="b9968-111">如需詳細資訊，請按一下[這裡](https://support.microsoft.com/help/4057281/windows-7-support-will-end-on-january-14-2020)。</span><span class="sxs-lookup"><span data-stu-id="b9968-111">For more information, click [here](https://support.microsoft.com/help/4057281/windows-7-support-will-end-on-january-14-2020).</span></span>
>

<span data-ttu-id="b9968-112">在一段時間內完成所有這些移轉，讓您的組織更接近[現代職場](https://www.microsoft.com/microsoft-365/blog/2018/04/27/making-it-simpler-with-a-modern-workplace/)，也就是安全的整合式環境，讓組織可發揮團隊合作和創意，而以上這些都是藉由 Microsoft 365 企業版來提供及達成。</span><span class="sxs-lookup"><span data-stu-id="b9968-112">Accomplishing all of these migrations over time gets your organization closer to the [modern workplace](https://www.microsoft.com/microsoft-365/blog/2018/04/27/making-it-simpler-with-a-modern-workplace/), a secure and integrated environment that unlocks teamwork and creativity in your organization, all of which is enabled and empowered by Microsoft 365 Enterprise.</span></span> 

<span data-ttu-id="b9968-113">如需關於為特定 Office 365 工作負載遷移使用者和資料的資訊：</span><span class="sxs-lookup"><span data-stu-id="b9968-113">For information about migrating users and data for specific Office 365 workloads:</span></span>

- <span data-ttu-id="b9968-114">使用者信箱從 Exchange Server 到 Exchange Online，請參閱 [Exchange Online 工作負載](exchangeonline-workload.md)。</span><span class="sxs-lookup"><span data-stu-id="b9968-114">User mailboxes from Exchange Server to Exchange Online, see the [Exchange Online workload](exchangeonline-workload.md).</span></span>
- <span data-ttu-id="b9968-115">SharePoint 資料從 SharePoint Server 到 SharePoint Online，請參閱 [SharePoint Online 工作負載](sharepoint-online-onedrive-workload.md)。</span><span class="sxs-lookup"><span data-stu-id="b9968-115">SharePoint data from SharePoint Server to SharePoint Online, see the [SharePoint Online workload](sharepoint-online-onedrive-workload.md).</span></span>
- <span data-ttu-id="b9968-116">商務用 Skype Online 到 Microsoft Teams，請參閱 [Microsoft Teams 工作負載](teams-workload.md)。</span><span class="sxs-lookup"><span data-stu-id="b9968-116">Skype for Business Online to Microsoft Teams, see the [Microsoft Teams workload](teams-workload.md).</span></span>

## <a name="migration-for-microsoft-office-client-products"></a><span data-ttu-id="b9968-117">Microsoft Office 用戶端產品的移轉</span><span class="sxs-lookup"><span data-stu-id="b9968-117">Migration for Microsoft Office client products</span></span>

<span data-ttu-id="b9968-p103">在許多大型和小型組織中，您可能會使用較舊版本的 Office 用戶端產品組合，例如 Word、Excel 和 PowerPoint。這些較舊的版本：</span><span class="sxs-lookup"><span data-stu-id="b9968-p103">In many organizations both large and small, you might be using a combination of older versions of the Office client products, such as Word, Excel, and PowerPoint. These older versions:</span></span>

- <span data-ttu-id="b9968-120">可使用最新的安全性更新和支援修正進行[更新](https://support.office.com/article/install-office-updates-2ab296f3-7f03-43a2-8e50-46de917611c5)，但此程序有時需手動進行，且可能無法擴及整個組織。</span><span class="sxs-lookup"><span data-stu-id="b9968-120">Can be [updated](https://support.office.com/article/install-office-updates-2ab296f3-7f03-43a2-8e50-46de917611c5) with the latest security updates and support fixes, but the process is sometimes manual and might not scale across your organization.</span></span>
- <span data-ttu-id="b9968-121">未以最佳化方式啟用以便運用 Microsoft 雲端技術，及協助您的企業進行數位轉型。</span><span class="sxs-lookup"><span data-stu-id="b9968-121">Are not optimally enabled to leverage Microsoft’s cloud technologies and help you digitally transform your business.</span></span>
- <span data-ttu-id="b9968-122">不包含新功能。</span><span class="sxs-lookup"><span data-stu-id="b9968-122">Do not contain new features.</span></span>
 
<span data-ttu-id="b9968-123">Microsoft 365 企業版包含 Microsoft 365 Apps 企業版，此 Office 用戶端產品版本可使用 Microsoft 365 企業版授權，且會從 Microsoft 雲端進行安裝與更新。</span><span class="sxs-lookup"><span data-stu-id="b9968-123">Microsoft 365 Enterprise includes Microsoft 365 Apps for enterprise, a version of the Office client products that is available with a Microsoft 365 Enterprise license and is installed and updated from the Microsoft cloud.</span></span> <span data-ttu-id="b9968-124">Microsoft 365 Apps 企業版授權包括安全性更新和最新功能。</span><span class="sxs-lookup"><span data-stu-id="b9968-124">Microsoft 365 Apps for enterprise includes security updates and the latest features.</span></span> <span data-ttu-id="b9968-125">如需詳細資訊，請參閱[關於 Microsoft 365 應用程式企業版](https://docs.microsoft.com/deployoffice/about-microsoft-365-apps)。</span><span class="sxs-lookup"><span data-stu-id="b9968-125">See [About Microsoft 365 Apps for enterprise](https://docs.microsoft.com/deployoffice/about-microsoft-365-apps) for more information.</span></span>

### <a name="office-2007"></a><span data-ttu-id="b9968-126">Office 2007</span><span class="sxs-lookup"><span data-stu-id="b9968-126">Office 2007</span></span>

<span data-ttu-id="b9968-p105">針對 Office 2007 版的 Office 版本，已終止支援。如需詳細資訊，請參閱 [Office 2007 終止支援藍圖](https://docs.microsoft.com/deployoffice/office-2007-end-support-roadmap)。</span><span class="sxs-lookup"><span data-stu-id="b9968-p105">For versions of Office in the Office 2007 release, the end of support has already passed. See [Office 2007 End of Support Roadmap](https://docs.microsoft.com/deployoffice/office-2007-end-support-roadmap) for more information.</span></span>

<span data-ttu-id="b9968-129">若不使用 Office 2010、Office 2013 或 Office 2016 來升級您執行 Office 2007 的電腦，請考慮：</span><span class="sxs-lookup"><span data-stu-id="b9968-129">Rather than upgrading your computers running Office 2007 with Office 2010, Office 2013, or Office 2016, consider:</span></span>

1. <span data-ttu-id="b9968-130">為使用者取得並指派 Microsoft 365 授權。</span><span class="sxs-lookup"><span data-stu-id="b9968-130">Obtaining and assigning a Microsoft 365 license for your users.</span></span>
2. <span data-ttu-id="b9968-131">在使用者電腦中解除安裝 Office 2007。</span><span class="sxs-lookup"><span data-stu-id="b9968-131">Uninstalling Office 2007 on their computers.</span></span>
3. <span data-ttu-id="b9968-132">安裝 Microsoft 365 App 企業版 (個別安裝或搭配 IT 推出)。</span><span class="sxs-lookup"><span data-stu-id="b9968-132">Installing Microsoft 365 Apps for enterprise, either individually or in conjunction with an IT rollout.</span></span> <span data-ttu-id="b9968-133">如需詳細資訊，請參閱[階段4：Microsoft 365 App 企業版](office365proplus-infrastructure.md)。</span><span class="sxs-lookup"><span data-stu-id="b9968-133">For more information, see [Phase 4: Microsoft 365 Apps for enterprise](office365proplus-infrastructure.md).</span></span>

<span data-ttu-id="b9968-134">Microsoft 365 App 企業版會自動安裝更新，可以充分利用以雲端為基礎的服務，以取得增強的安全性和生產力。</span><span class="sxs-lookup"><span data-stu-id="b9968-134">Microsoft 365 Apps for enterprise installs updates automatically and can take advantage of cloud-based services for enhanced security and productivity.</span></span>

### <a name="office-2010"></a><span data-ttu-id="b9968-135">Office 2010</span><span class="sxs-lookup"><span data-stu-id="b9968-135">Office 2010</span></span>

<span data-ttu-id="b9968-136">針對 Office 2010 發行版本中的 Office 版本，終止支援為 **2020 年 10 月 13 日**。</span><span class="sxs-lookup"><span data-stu-id="b9968-136">For versions of Office in the Office 2010 release, the end of support is **October 13, 2020**.</span></span> <span data-ttu-id="b9968-137">如需詳細資訊，請參閱 [Office 2010 終止支援藍圖](https://docs.microsoft.com/deployoffice/office-2010-end-support-roadmap)。</span><span class="sxs-lookup"><span data-stu-id="b9968-137">For more information, see [Office 2010 end of support roadmap](https://docs.microsoft.com/deployoffice/office-2010-end-support-roadmap).</span></span>

<span data-ttu-id="b9968-138">若不使用 Office 2013 或 Office 2016 (這兩者都必須手動更新) 來升級您執行 Office 2010 的電腦，請考慮：</span><span class="sxs-lookup"><span data-stu-id="b9968-138">Rather than upgrading your computers running Office 2010 with Office 2013 or Office 2016, both of which must be manually updated, consider:</span></span> 

1. <span data-ttu-id="b9968-139">為使用者取得並指派 Microsoft 365 授權。</span><span class="sxs-lookup"><span data-stu-id="b9968-139">Obtaining and assigning a Microsoft 365 license for your users.</span></span>
2. <span data-ttu-id="b9968-140">在使用者電腦中解除安裝 Office 2010。</span><span class="sxs-lookup"><span data-stu-id="b9968-140">Uninstalling Office 2010 on their computers.</span></span>
3. <span data-ttu-id="b9968-141">安裝 Microsoft 365 App 企業版 (個別安裝或搭配 IT 推出)。</span><span class="sxs-lookup"><span data-stu-id="b9968-141">Installing Microsoft 365 Apps for enterprise, either individually or in conjunction with an IT rollout.</span></span> <span data-ttu-id="b9968-142">如需詳細資訊，請參閱[階段4：Microsoft 365 App 企業版](office365proplus-infrastructure.md)。</span><span class="sxs-lookup"><span data-stu-id="b9968-142">For more information, see [Phase 4: Microsoft 365 Apps for enterprise](office365proplus-infrastructure.md).</span></span>

<span data-ttu-id="b9968-143">Microsoft 365 App 企業版會自動安裝安全性和新功能更新，並可以充分利用 Microsoft 365 中以雲端為基礎的服務，以取得增強的安全性和生產力。</span><span class="sxs-lookup"><span data-stu-id="b9968-143">Microsoft 365 Apps for enterprise installs both security and new feature updates automatically and can take advantage of cloud-based services in Microsoft 365 for enhanced security and productivity.</span></span>

### <a name="office-2013-and-office-2016"></a><span data-ttu-id="b9968-144">Office 2013 和 Office 2016</span><span class="sxs-lookup"><span data-stu-id="b9968-144">Office 2013 and Office 2016</span></span>

<span data-ttu-id="b9968-145">Office 2013 和 Office 2016 版的終止支援藍圖尚未確定。</span><span class="sxs-lookup"><span data-stu-id="b9968-145">The end of support roadmap for the Office 2013 and Office 2016 versions of Office has not yet been determined.</span></span> <span data-ttu-id="b9968-146">不過，與 Office 2010 相同，您仍必須[安全性更新](https://support.office.com/article/install-office-updates-2ab296f3-7f03-43a2-8e50-46de917611c5)，而具體取決於組織的規模，可能無法妥善地擴充。</span><span class="sxs-lookup"><span data-stu-id="b9968-146">However, like Office 2010, you must still [install security updates](https://support.office.com/article/install-office-updates-2ab296f3-7f03-43a2-8e50-46de917611c5), which might not scale well depending on the size of your organization.</span></span>

<span data-ttu-id="b9968-147">若不想使用 Office 2013 或 Office 2016 的最新安全性更新持續更新您的電腦，或將您電腦從 Office 2013 更新至 Office 2016，請考慮：</span><span class="sxs-lookup"><span data-stu-id="b9968-147">Rather than keep updating your computers with the latest security updates for Office 2013 or Office 2016 or update your computers from Office 2013 to Office 2016, consider:</span></span>

1. <span data-ttu-id="b9968-148">為使用者取得並指派 Microsoft 365 授權。</span><span class="sxs-lookup"><span data-stu-id="b9968-148">Obtaining and assigning a Microsoft 365 license for your users.</span></span>
2. <span data-ttu-id="b9968-149">在使用者電腦中解除安裝 Office 2013 或 Office 2016。</span><span class="sxs-lookup"><span data-stu-id="b9968-149">Uninstalling Office 2013 or Office 2016 on their computers.</span></span>
3. <span data-ttu-id="b9968-150">安裝 Microsoft 365 App 企業版 (個別安裝或搭配 IT 推出)。</span><span class="sxs-lookup"><span data-stu-id="b9968-150">Installing Microsoft 365 Apps for enterprise, either individually or in conjunction with an IT rollout.</span></span> <span data-ttu-id="b9968-151">如需詳細資訊，請參閱[階段4：Microsoft 365 App 企業版](office365proplus-infrastructure.md)。</span><span class="sxs-lookup"><span data-stu-id="b9968-151">For more information, see [Phase 4: Microsoft 365 Apps for enterprise](office365proplus-infrastructure.md).</span></span>

<span data-ttu-id="b9968-152">Microsoft 365 App 企業版會自動安裝安全性和新功能更新，並可以充分利用 Microsoft 365 中以雲端為基礎的服務，以取得增強的安全性和生產力。</span><span class="sxs-lookup"><span data-stu-id="b9968-152">Microsoft 365 Apps for enterprise installs both security and new feature updates automatically and can take advantage of cloud-based services in Microsoft 365 for enhanced security and productivity.</span></span>

## <a name="migration-for-microsoft-office-server-products"></a><span data-ttu-id="b9968-153">Microsoft Office 伺服器產品的移轉</span><span class="sxs-lookup"><span data-stu-id="b9968-153">Migration for Microsoft Office server products</span></span>

<span data-ttu-id="b9968-p111">在許多大型和小型組織中，您可能會使用較舊版本的 Office 伺服器產品組合，例如 Exchange Server 與 SharePoint Server。這些較舊的版本：</span><span class="sxs-lookup"><span data-stu-id="b9968-p111">In many organizations both large and small, you might be using a combination of older versions of the Office Server products, such as Exchange Server and SharePoint Server. These older versions:</span></span>

- <span data-ttu-id="b9968-p112">應使用最新的安全性更新和支援修正進行更新。在某些情況下，這些更新會每月發行。</span><span class="sxs-lookup"><span data-stu-id="b9968-p112">Should be updated with the latest security updates and support fixes. In some cases, these updates are released monthly.</span></span>
- <span data-ttu-id="b9968-158">未以最佳化方式啟用以便運用 Microsoft 雲端技術，及協助您的企業進行數位轉型。</span><span class="sxs-lookup"><span data-stu-id="b9968-158">Are not optimally enabled to leverage Microsoft’s cloud technologies and help you digitally transform your business.</span></span>
- <span data-ttu-id="b9968-159">不包含新的生產力應用程式，例如 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="b9968-159">Do not include new productivity applications, such as Microsoft Teams.</span></span>
- <span data-ttu-id="b9968-160">不包含最新的安全性功能，例如 Exchange 進階威脅防護。</span><span class="sxs-lookup"><span data-stu-id="b9968-160">Do not include the latest security features, such as Exchange Advanced Threat Protection.</span></span>

<span data-ttu-id="b9968-161">Microsoft 365 企業版包括 Office 365，其中包括雲端型的 Office 伺服器服務，這些服務使用的工具與內部部署版的 Office 伺服器軟體相同，例如 Web 瀏覽器和 Outlook 用戶端。</span><span class="sxs-lookup"><span data-stu-id="b9968-161">Microsoft 365 Enterprise includes Office 365, which includes cloud-based versions of Office server services that use some of the same tools as on-premises versions of Office server software, such as web browsers and the Outlook client.</span></span> <span data-ttu-id="b9968-162">這些服務會不斷進行安全性更新，而不需 IT 進行，進而為您節省了維護和更新內部部署伺服器所需的時間。</span><span class="sxs-lookup"><span data-stu-id="b9968-162">These services are continually updated for security without involving IT, saving you the time it takes to maintain and update on-premises servers.</span></span> <span data-ttu-id="b9968-163">這些服務也含有 Office 伺服器軟體中沒有的新功能增強功能。</span><span class="sxs-lookup"><span data-stu-id="b9968-163">These services also have new features enhancements that are not present in Office server software.</span></span> 

### <a name="office-server-2007"></a><span data-ttu-id="b9968-164">Office Server 2007</span><span class="sxs-lookup"><span data-stu-id="b9968-164">Office Server 2007</span></span>

<span data-ttu-id="b9968-p114">對於 Office 2007 版的伺服器產品，已終止支援。請參閱下列文章取得詳細資料：</span><span class="sxs-lookup"><span data-stu-id="b9968-p114">For server products in the Office 2007 release, the end of support has already passed. See these articles for the details:</span></span>

- [<span data-ttu-id="b9968-167">Exchange 2007 終止支援藍圖</span><span class="sxs-lookup"><span data-stu-id="b9968-167">Exchange 2007 end of support roadmap</span></span>](https://docs.microsoft.com/office365/enterprise/exchange-2007-end-of-support)
- [<span data-ttu-id="b9968-168">SharePoint Server 2007 終止支援藍圖</span><span class="sxs-lookup"><span data-stu-id="b9968-168">SharePoint Server 2007 end of support roadmap</span></span>](https://docs.microsoft.com/office365/enterprise/sharepoint-2007-end-of-support)
- [<span data-ttu-id="b9968-169">Project Server 2007 終止支援藍圖</span><span class="sxs-lookup"><span data-stu-id="b9968-169">Project Server 2007 end of support roadmap</span></span>](https://docs.microsoft.com/office365/enterprise/project-server-2007-end-of-support)
- [<span data-ttu-id="b9968-170">Office Communications Server 終止支援藍圖</span><span class="sxs-lookup"><span data-stu-id="b9968-170">Office Communications Server end of support roadmap</span></span>](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/upgrade)
- [<span data-ttu-id="b9968-171">PerformancePoint Server 2007 終止支援藍圖</span><span class="sxs-lookup"><span data-stu-id="b9968-171">PerformancePoint Server 2007 end of support roadmap</span></span>](https://docs.microsoft.com/office365/enterprise/pps-2007-end-of-support)

<span data-ttu-id="b9968-172">若不使用 Office 2010、Office 2013 或 Office 2016 版的伺服器產品升級 Office 2007 版的伺服器產品，請考慮：</span><span class="sxs-lookup"><span data-stu-id="b9968-172">Rather than upgrading your server products in the Office 2007 release with server products in the Office 2010, Office 2013, or Office 2016 releases, consider:</span></span>

1. <span data-ttu-id="b9968-p115">將 Office 2007 伺服器上的資料移轉到 Office 365。如需協助，請雇用 Microsoft 合作夥伴。</span><span class="sxs-lookup"><span data-stu-id="b9968-p115">Migrating the data on your Office 2007 servers to Office 365. To help with this, hire a Microsoft partner.</span></span>
2. <span data-ttu-id="b9968-175">向使用者推出新功能和作業程序。</span><span class="sxs-lookup"><span data-stu-id="b9968-175">Rolling out the new functionality and work processes to your users.</span></span>
3. <span data-ttu-id="b9968-176">不再需要執行 Office 2007 伺服器產品的內部部署伺服器時，請予以解除。</span><span class="sxs-lookup"><span data-stu-id="b9968-176">When there is no longer a need for the on-premises servers running Office 2007 server products, decommissioning them.</span></span>

### <a name="office-server-2010"></a><span data-ttu-id="b9968-177">Office Server 2010</span><span class="sxs-lookup"><span data-stu-id="b9968-177">Office Server 2010</span></span>

<span data-ttu-id="b9968-178">[Exchange Server 2010](https://docs.microsoft.com/office365/enterprise/exchange-2010-end-of-support) 的支援終止日期為 **2020 年 10 月 13 日**。</span><span class="sxs-lookup"><span data-stu-id="b9968-178">The end of support for [Exchange Server 2010](https://docs.microsoft.com/office365/enterprise/exchange-2010-end-of-support) is **October 13, 2020**.</span></span>

<span data-ttu-id="b9968-179">[SharePoint Server 2010](https://docs.microsoft.com/office365/enterprise/upgrade-from-sharepoint-2010) 的支援終止日期為 **2021 年 4 月 13 日**。</span><span class="sxs-lookup"><span data-stu-id="b9968-179">The end of support for [SharePoint Server 2010](https://docs.microsoft.com/office365/enterprise/upgrade-from-sharepoint-2010) is **April 13, 2021**.</span></span>

<span data-ttu-id="b9968-180">若不使用 Office 2013 或 Office 2016 版的伺服器產品升級 Office 2010 版的這些伺服器產品，請考慮：</span><span class="sxs-lookup"><span data-stu-id="b9968-180">Rather than upgrading these server products in the Office 2010 release with server products in the Office 2013 or Office 2016 release, consider:</span></span>

1. <span data-ttu-id="b9968-181">將 Office 2010 伺服器上的資料移轉至 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="b9968-181">Migrating the data on your Office 2010 servers to Microsoft 365.</span></span> <span data-ttu-id="b9968-182">若需要協助，請參閱[適用於 Microsoft 365 的 FastTrack](https://fasttrack.microsoft.com/microsoft365) 或雇用 Microsoft 合作夥伴。</span><span class="sxs-lookup"><span data-stu-id="b9968-182">To help with this, see [FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365) or hire a Microsoft partner.</span></span>
2. <span data-ttu-id="b9968-183">向使用者推出新功能和作業程序。</span><span class="sxs-lookup"><span data-stu-id="b9968-183">Rolling out the new functionality and work processes to your users.</span></span>
3. <span data-ttu-id="b9968-184">不再需要執行 Office 2010 伺服器產品的內部部署伺服器時，請予以解除。</span><span class="sxs-lookup"><span data-stu-id="b9968-184">When there is no longer a need for the on-premises servers running Office 2010 server products, decommissioning them.</span></span>

### <a name="office-server-2013"></a><span data-ttu-id="b9968-185">Office Server 2013</span><span class="sxs-lookup"><span data-stu-id="b9968-185">Office Server 2013</span></span>

<span data-ttu-id="b9968-p117">對於 Office 2013 版的伺服器產品，尚未決定終止支援。若不使用 Office 2016 版的伺服器產品升級 Office 2013 版的伺服器產品，請考慮：</span><span class="sxs-lookup"><span data-stu-id="b9968-p117">For server products in the Office 2013 release, the end of support has not been determined. Rather than upgrading your server products in the Office 2013 release with server products in the Office 2016 release, consider:</span></span>

1. <span data-ttu-id="b9968-p118">將 Office 2013 伺服器上的資料移轉到 Office 365。如需協助，請參閱 [Microsoft 365 的 FastTrack](https://fasttrack.microsoft.com/microsoft365) 或雇用 Microsoft 合作夥伴。</span><span class="sxs-lookup"><span data-stu-id="b9968-p118">Migrating the data on your Office 2013 servers to Office 365. To help with this, see [FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365) or hire a Microsoft partner.</span></span>
2. <span data-ttu-id="b9968-190">向使用者推出新功能和作業程序。</span><span class="sxs-lookup"><span data-stu-id="b9968-190">Rolling out the new functionality and work processes to your users.</span></span>
3. <span data-ttu-id="b9968-191">不再需要執行 Office 2013 伺服器產品的內部部署伺服器時，請予以解除。</span><span class="sxs-lookup"><span data-stu-id="b9968-191">When there is no longer a need for the on-premises servers running Office 2013 server products, decommissioning them.</span></span>

### <a name="office-server-2016"></a><span data-ttu-id="b9968-192">Office Server 2016</span><span class="sxs-lookup"><span data-stu-id="b9968-192">Office Server 2016</span></span>

<span data-ttu-id="b9968-p119">對於 Office 2016 版的伺服器產品，尚未決定終止支援。若要充分利用以雲端為基礎的服務和增強功能，以便貴公司進行數位轉型，請考慮：</span><span class="sxs-lookup"><span data-stu-id="b9968-p119">For server products in the Office 2016 release, the end of support has not been determined. To take advantage of the cloud-based service and enhancements to digitally transform your business, consider:</span></span>

1. <span data-ttu-id="b9968-p120">將 Office 2016 伺服器上的資料移轉到 Office 365。如需協助，請參閱 [Microsoft 365 的 FastTrack](https://fasttrack.microsoft.com/microsoft365) 或雇用 Microsoft 合作夥伴。</span><span class="sxs-lookup"><span data-stu-id="b9968-p120">Migrating the data on your Office 2016 servers to Office 365. To help with this, see [FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365) or hire a Microsoft partner.</span></span>
2. <span data-ttu-id="b9968-197">向使用者推出新功能和作業程序。</span><span class="sxs-lookup"><span data-stu-id="b9968-197">Rolling out the new functionality and work processes to your users.</span></span>
3. <span data-ttu-id="b9968-198">不再需要執行 Office 2016 伺服器產品的內部部署伺服器時，請予以解除。</span><span class="sxs-lookup"><span data-stu-id="b9968-198">When there is no longer a need for the on-premises servers running Office 2016 server products, decommissioning them.</span></span>

## <a name="migration-for-microsoft-windows-7-and-81"></a><span data-ttu-id="b9968-199">Microsoft Windows 7 和 8.1 的移轉</span><span class="sxs-lookup"><span data-stu-id="b9968-199">Migration for Microsoft Windows 7 and 8.1</span></span>

<span data-ttu-id="b9968-200">Windows 7 已於 **2020 年 1 月 14 日**終止支援。</span><span class="sxs-lookup"><span data-stu-id="b9968-200">Windows 7 reached end of support on **January 14, 2020**.</span></span> <span data-ttu-id="b9968-201">若要移轉執行 Windows 7 或 Windows 8.1 的裝置，您可以執行[就地升級](https://docs.microsoft.com/microsoft-365/enterprise/windows10-deploy-inplaceupgrade)。</span><span class="sxs-lookup"><span data-stu-id="b9968-201">To migrate your devices running Windows 7 or Windows 8.1, you can perform an [in-place upgrade](https://docs.microsoft.com/microsoft-365/enterprise/windows10-deploy-inplaceupgrade).</span></span> 

<span data-ttu-id="b9968-202">如需其他方法，請參閱 [Windows 10 部署案例](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios)。</span><span class="sxs-lookup"><span data-stu-id="b9968-202">For additional methods, see [Windows 10 deployment scenarios](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios).</span></span> <span data-ttu-id="b9968-203">您也可以自行[規劃 Windows 10 部署](https://aka.ms/planforwin10deployment)。</span><span class="sxs-lookup"><span data-stu-id="b9968-203">You can also [plan for Windows 10 deployment](https://aka.ms/planforwin10deployment) on your own.</span></span>

## <a name="summary-of-options-for-office-2010-clients-and-servers-and-windows-7"></a><span data-ttu-id="b9968-204">適用於 Office 2010 用戶端與伺服器和 Windows 7 的選項摘要</span><span class="sxs-lookup"><span data-stu-id="b9968-204">Summary of options for Office 2010 clients and servers and Windows 7</span></span>

<span data-ttu-id="b9968-205">如需適用於這些產品的升級、移轉和移至雲端選項的視覺摘要，請參閱[終止支援海報](../media/migration-microsoft-365-enterprise-workload/Office2010Windows7EndOfSupport.pdf)。</span><span class="sxs-lookup"><span data-stu-id="b9968-205">For a visual summary of the upgrade, migrate, and move-to-the-cloud options for these products, see the [end of support poster](../media/migration-microsoft-365-enterprise-workload/Office2010Windows7EndOfSupport.pdf).</span></span>

<span data-ttu-id="b9968-206">[![Office 2010 用戶端與伺服器和 Windows 7 終止支援海報的影像](../media/migration-microsoft-365-enterprise-workload/office2010-windows7-end-of-support.png)](../media/migration-microsoft-365-enterprise-workload/Office2010Windows7EndOfSupport.pdf)</span><span class="sxs-lookup"><span data-stu-id="b9968-206">[![Image for the end of support for Office 2010 clients and servers and Windows 7 poster](../media/migration-microsoft-365-enterprise-workload/office2010-windows7-end-of-support.png)](../media/migration-microsoft-365-enterprise-workload/Office2010Windows7EndOfSupport.pdf)</span></span>

<span data-ttu-id="b9968-207">這張單頁海報可讓您快速了解可以採取的各種方法，以防止 Office 2010 用戶端與伺服器產品以及 Windows 7 進入終止支援，而海報上也會強調顯示 Microsoft 365 企業版中慣用的方式和結果目的地。</span><span class="sxs-lookup"><span data-stu-id="b9968-207">This one-page poster is a quick way to understand the various paths you can take to prevent Office 2010 client and server products and Windows 7 from reaching end of support, with preferred paths and resulting destination support in Microsoft 365 Enterprise highlighted.</span></span>

<span data-ttu-id="b9968-208">您可以[下載此海報](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/migration-microsoft-365-enterprise-workload/Office2010Windows7EndOfSupport.pdf)，並以 Letter、Legal 或 Tabloid (11 x 17) 格式列印此海報。</span><span class="sxs-lookup"><span data-stu-id="b9968-208">You can [download this poster](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/migration-microsoft-365-enterprise-workload/Office2010Windows7EndOfSupport.pdf) and print it in letter, legal, or tabloid (11 x 17) formats.</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="b9968-209">Microsoft 如何執行 Microsoft 365 企業版</span><span class="sxs-lookup"><span data-stu-id="b9968-209">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="b9968-210">請查看 Microsoft 的 IT 專業人員如何使用以下資源將公司移轉到 Microsoft 365 企業版：</span><span class="sxs-lookup"><span data-stu-id="b9968-210">See how IT experts at Microsoft migrated the company to Microsoft 365 Enterprise with these resources:</span></span> 

- [<span data-ttu-id="b9968-211">部署及更新 Microsoft 365 Apps 企業版</span><span class="sxs-lookup"><span data-stu-id="b9968-211">Deploying and updating Microsoft Microsoft 365 Apps for enterprise</span></span>](https://www.microsoft.com/itshowcase/Article/Content/757/Deploying-and-updating-Microsoft-Office-365-ProPlus)
- [<span data-ttu-id="b9968-212">Microsoft 會將 150000 個信箱移轉到 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="b9968-212">Microsoft migrates 150,000 mailboxes to Exchange Online</span></span>](https://www.microsoft.com/itshowcase/Article/Content/577/Microsoft-migrates-150000-mailboxes-to-Exchange-Online)
- [<span data-ttu-id="b9968-213">SharePoint 至雲端：深入了解 Microsoft 如何執行自己的移轉</span><span class="sxs-lookup"><span data-stu-id="b9968-213">SharePoint to the cloud: Learn how Microsoft ran its own migration</span></span>](https://www.microsoft.com/itshowcase/Article/Content/691/SharePoint-to-the-cloud-Learn-how-Microsoft-ran-its-own-migration)
- [<span data-ttu-id="b9968-214">在 Microsoft 以就地升級方式部署 Windows 10</span><span class="sxs-lookup"><span data-stu-id="b9968-214">Deploying Windows 10 at Microsoft as an in-place upgrade</span></span>](https://www.microsoft.com/itshowcase/Article/Content/668/Deploying-Windows-10-at-Microsoft-as-an-inplace-upgrade)
- <span data-ttu-id="b9968-215">[Windows 10 部署：Microsoft IT 的秘訣與技巧](https://www.microsoft.com/itshowcase/Article/Content/951/Windows-10-deployment-tips-and-tricks-from-Microsoft-IT) (影片)</span><span class="sxs-lookup"><span data-stu-id="b9968-215">[Windows 10 deployment: tips and tricks from Microsoft IT](https://www.microsoft.com/itshowcase/Article/Content/951/Windows-10-deployment-tips-and-tricks-from-Microsoft-IT) (video)</span></span>

## <a name="transition-your-entire-organization"></a><span data-ttu-id="b9968-216">轉換您的整個組織</span><span class="sxs-lookup"><span data-stu-id="b9968-216">Transition your entire organization</span></span>

<span data-ttu-id="b9968-217">若要更全面地掌握如何將整個組織移至 Microsoft 365 企業版中的產品和服務，請參閱[轉換海報](../media/deploy-microsoft-365-enterprise/transition-org-to-m365.pdf)。</span><span class="sxs-lookup"><span data-stu-id="b9968-217">To get a better picture of how to move your entire organization to the products and services in Microsoft 365 Enterprise, see the [transition poster](../media/deploy-microsoft-365-enterprise/transition-org-to-m365.pdf).</span></span>

<span data-ttu-id="b9968-218">[![轉換至 Microsoft 365 海報的影像](../media/deploy-microsoft-365-enterprise/transition-org-to-m365.png)](../media/deploy-microsoft-365-enterprise/transition-org-to-m365.pdf)</span><span class="sxs-lookup"><span data-stu-id="b9968-218">[![Image for the Transition to Microsoft 365 poster](../media/deploy-microsoft-365-enterprise/transition-org-to-m365.png)](../media/deploy-microsoft-365-enterprise/transition-org-to-m365.pdf)</span></span>

<span data-ttu-id="b9968-219">這份雙頁海報可讓您快速清查您現有的基礎結構，並取得移至 Microsoft 365 企業版中對應產品或服務的指導方針。</span><span class="sxs-lookup"><span data-stu-id="b9968-219">This two-page poster is a quick way to inventory your existing infrastructure and get to the guidance for moving to the corresponding product or service in Microsoft 365 Enterprise.</span></span> <span data-ttu-id="b9968-220">包含 Windows 和 Office 產品和其他基礎結構與安全性元素，例如裝置管理、身分識別以及資訊和威脅防護。</span><span class="sxs-lookup"><span data-stu-id="b9968-220">It includes Windows and Office products and other infrastructure and security elements such as device management, identity, and information and threat protection.</span></span>

<span data-ttu-id="b9968-221">您可以[下載此海報](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/deploy-microsoft-365-enterprise/transition-org-to-m365.pdf)，並以 Letter、Legal 或 Tabloid (11 x 17) 格式列印此海報。</span><span class="sxs-lookup"><span data-stu-id="b9968-221">You can [download this poster](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/deploy-microsoft-365-enterprise/transition-org-to-m365.pdf) and print it in letter, legal, or tabloid (11 x 17) formats.</span></span>

## <a name="result"></a><span data-ttu-id="b9968-222">結果</span><span class="sxs-lookup"><span data-stu-id="b9968-222">Result</span></span>

<span data-ttu-id="b9968-223">貴組織已將舊版 Microsoft Office、Office 伺服器及 Windows 移轉為 Microsoft 365 企業版。</span><span class="sxs-lookup"><span data-stu-id="b9968-223">Your organization has migrated older versions of Microsoft Office, Office servers, and Windows to Microsoft 365 Enterprise.</span></span>
