---
title: 移轉至 Microsoft 365 企業版
author: JoeDavies-MSFT
manager: laurawi
ms.date: 02/13/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: 在整個組織中逐步執行將 Microsoft Office、Office 伺服器及 Windows 的各版本移轉為 Microsoft 365 企業版的程序。
ms.openlocfilehash: f165e09b58b5208fa4d9aae24f7d5cdda385c639
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291261"
---
# <a name="migration-to-microsoft-365-enterprise"></a><span data-ttu-id="6bc37-103">移轉至 Microsoft 365 企業版</span><span class="sxs-lookup"><span data-stu-id="6bc37-103">Migration to Microsoft 365 Enterprise</span></span>

<span data-ttu-id="6bc37-p101">大多數的企業組織擁有異質環境，其中具有多種版本的作業系統、用戶端軟體及伺服器軟體。Microsoft 365 企業版包含 IT 基礎結構中這些主要元件最安全的版本，且具有專為充分利用雲端技術所設計的生產力功能。</span><span class="sxs-lookup"><span data-stu-id="6bc37-p101">Most enterprise organizations have a heterogeneous environment with multiple releases of operating systems, client software, and server software. Microsoft 365 Enterprise includes the most secure versions of these key components of your IT infrastructure with productivity features that are designed to take advantage of cloud technologies.</span></span>

<span data-ttu-id="6bc37-106">若要充分發揮 Microsoft 365 企業版產品整合套件的商務價值，請開始規劃並實作策略以移轉以下版本：</span><span class="sxs-lookup"><span data-stu-id="6bc37-106">To maximize the business value of the Microsoft 365 Enterprise integrated suite of products, begin planning and implementing a strategy to migrate releases of:</span></span>

- <span data-ttu-id="6bc37-107">將安裝在您電腦上的 Office 用戶端移轉為 Office 365 專業增強版</span><span class="sxs-lookup"><span data-stu-id="6bc37-107">The Office client installed on your computers to Office 365 ProPlus</span></span>
- <span data-ttu-id="6bc37-108">將安裝在您伺服器上的 Office 伺服器移轉為 Office 365 中的對等服務</span><span class="sxs-lookup"><span data-stu-id="6bc37-108">Office servers installed on your servers to their equivalent services in Office 365</span></span>
- <span data-ttu-id="6bc37-109">將裝置上的 Windows 7 和 Windows 8.1 移轉為 Windows 10 企業版</span><span class="sxs-lookup"><span data-stu-id="6bc37-109">Windows 7 and Windows 8.1 on your devices to Windows 10 Enterprise</span></span>

<span data-ttu-id="6bc37-110">在一段時間內完成所有這些移轉，讓您的組織更接近[現代職場](https://www.microsoft.com/microsoft-365/blog/2018/04/27/making-it-simpler-with-a-modern-workplace/)，也就是安全的整合式環境，讓組織可發揮團隊合作和創意，而以上這些都是藉由 Microsoft 365 企業版來提供及達成。</span><span class="sxs-lookup"><span data-stu-id="6bc37-110">Accomplishing all of these migrations over time gets your organization closer to the [modern workplace](https://www.microsoft.com/microsoft-365/blog/2018/04/27/making-it-simpler-with-a-modern-workplace/), a secure and integrated environment that unlocks teamwork and creativity in your organization, all of which is enabled and empowered by Microsoft 365 Enterprise.</span></span> 

<span data-ttu-id="6bc37-111">如需關於為特定 Office 365 工作負載遷移使用者和資料的資訊：</span><span class="sxs-lookup"><span data-stu-id="6bc37-111">For information about migrating users and data for specific Office 365 workloads:</span></span>

- <span data-ttu-id="6bc37-112">使用者信箱從 Exchange Server 到 Exchange Online，請參閱 [Exchange Online 工作負載](exchangeonline-workload.md)。</span><span class="sxs-lookup"><span data-stu-id="6bc37-112">User mailboxes from Exchange Server to Exchange Online, see the [Exchange Online workload](exchangeonline-workload.md).</span></span>
- <span data-ttu-id="6bc37-113">SharePoint 資料從 SharePoint Server 到 SharePoint Online，請參閱 [SharePoint Online 工作負載](sharepoint-online-onedrive-workload.md)。</span><span class="sxs-lookup"><span data-stu-id="6bc37-113">SharePoint data from SharePoint Server to SharePoint Online, see the [SharePoint Online workload](sharepoint-online-onedrive-workload.md).</span></span>
- <span data-ttu-id="6bc37-114">商務用 Skype Online 到 Microsoft Teams，請參閱 [Microsoft Teams 工作負載](teams-workload.md)。</span><span class="sxs-lookup"><span data-stu-id="6bc37-114">Skype for Business Online to Microsoft Teams, see the [Microsoft Teams workload](teams-workload.md).</span></span>

## <a name="migration-for-microsoft-office-client-products"></a><span data-ttu-id="6bc37-115">Microsoft Office 用戶端產品的移轉</span><span class="sxs-lookup"><span data-stu-id="6bc37-115">Migration for Microsoft Office client products</span></span>

<span data-ttu-id="6bc37-p102">在許多大型和小型組織中，您可能會使用較舊版本的 Office 用戶端產品組合，例如 Word、Excel 和 PowerPoint。這些較舊的版本：</span><span class="sxs-lookup"><span data-stu-id="6bc37-p102">In many organizations both large and small, you might be using a combination of older versions of the Office client products, such as Word, Excel, and PowerPoint. These older versions:</span></span>

- <span data-ttu-id="6bc37-118">可使用最新的安全性更新和支援修正進行[更新](https://support.office.com/article/install-office-updates-2ab296f3-7f03-43a2-8e50-46de917611c5)，但此程序有時需手動進行，且可能無法擴及整個組織。</span><span class="sxs-lookup"><span data-stu-id="6bc37-118">Can be [updated](https://support.office.com/article/install-office-updates-2ab296f3-7f03-43a2-8e50-46de917611c5) with the latest security updates and support fixes, but the process is sometimes manual and might not scale across your organization.</span></span>
- <span data-ttu-id="6bc37-119">未以最佳化方式啟用以便運用 Microsoft 雲端技術，及協助您的企業進行數位轉型。</span><span class="sxs-lookup"><span data-stu-id="6bc37-119">Are not optimally enabled to leverage Microsoft’s cloud technologies and help you digitally transform your business.</span></span>
 
<span data-ttu-id="6bc37-p103">Microsoft 365 企業版包含 Office 365 專業增強版，此 Office 用戶端產品版本可使用 Microsoft 365 企業版授權，且會從 Microsoft 雲端進行安裝與更新。請參閱[關於企業中的 Office 365 專業增強版](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise)以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="6bc37-p103">Microsoft 365 Enterprise includes Office 365 ProPlus, a version of the Office client products that is available with a Microsoft 365 Enterprise license and is installed and updated from the Microsoft cloud. See [About Office 365 ProPlus in the enterprise](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise) for more information.</span></span>

### <a name="office-2007"></a><span data-ttu-id="6bc37-122">Office 2007</span><span class="sxs-lookup"><span data-stu-id="6bc37-122">Office 2007</span></span>

<span data-ttu-id="6bc37-p104">針對 Office 2007 版的 Office 版本，已終止支援。如需詳細資訊，請參閱 [Office 2007 終止支援藍圖](https://docs.microsoft.com/deployoffice/office-2007-end-support-roadmap)。</span><span class="sxs-lookup"><span data-stu-id="6bc37-p104">For versions of Office in the Office 2007 release, the end of support has already passed. See [Office 2007 End of Support Roadmap](https://docs.microsoft.com/deployoffice/office-2007-end-support-roadmap) for more information.</span></span>

<span data-ttu-id="6bc37-125">若不使用 Office 2010、Office 2013 或 Office 2016 來升級您執行 Office 2007 的電腦，請考慮：</span><span class="sxs-lookup"><span data-stu-id="6bc37-125">Rather than upgrading your computers running Office 2007 with Office 2010, Office 2013, or Office 2016, consider:</span></span>

1. <span data-ttu-id="6bc37-126">為使用者取得並指派 Microsoft 365 授權。</span><span class="sxs-lookup"><span data-stu-id="6bc37-126">Obtaining and assigning a Microsoft 365 license for your users.</span></span>
2. <span data-ttu-id="6bc37-127">在使用者電腦中解除安裝 Office 2007。</span><span class="sxs-lookup"><span data-stu-id="6bc37-127">Uninstalling Office 2007 on their computers.</span></span>
3. <span data-ttu-id="6bc37-p105">安裝 Office 365 專業增強版 (個別或搭配 IT 推出)。如需詳細資訊，請參閱[階段 4：Office 365 專業增強版](office365proplus-infrastructure.md)。</span><span class="sxs-lookup"><span data-stu-id="6bc37-p105">Installing Office 365 ProPlus, either individually or in conjunction with an IT rollout. For more information, see [Phase 4: Office 365 ProPlus](office365proplus-infrastructure.md).</span></span>

<span data-ttu-id="6bc37-130">Office 365 專業增強版會自動安裝更新，可以充分利用 Office 365 中以雲端為基礎的服務，以取得增強的安全性和生產力。</span><span class="sxs-lookup"><span data-stu-id="6bc37-130">Office 365 ProPlus installs updates automatically and can take advantage of cloud-based services in Office 365 for enhanced security and productivity.</span></span>

### <a name="office-2010"></a><span data-ttu-id="6bc37-131">Office 2010</span><span class="sxs-lookup"><span data-stu-id="6bc37-131">Office 2010</span></span>

<span data-ttu-id="6bc37-p106">針對 Office 2010 版的 Office 版本，將在 2020 年 10 月 13 日終止支援。如需詳細資訊，請參閱 [Office 2010 終止支援藍圖](https://docs.microsoft.com/deployoffice/office-2010-end-support-roadmap)。</span><span class="sxs-lookup"><span data-stu-id="6bc37-p106">For versions of Office in the Office 2010 release, the end of support is October 13, 2020. For more information, see [Office 2010 end of support roadmap](https://docs.microsoft.com/deployoffice/office-2010-end-support-roadmap).</span></span>

<span data-ttu-id="6bc37-134">若不使用 Office 2013 或 Office 2016 (這兩者都必須手動更新) 來升級您執行 Office 2010 的電腦，請考慮：</span><span class="sxs-lookup"><span data-stu-id="6bc37-134">Rather than upgrading your computers running Office 2010 with Office 2013 or Office 2016, both of which must be manually updated, consider:</span></span> 

1. <span data-ttu-id="6bc37-135">為使用者取得並指派 Microsoft 365 授權。</span><span class="sxs-lookup"><span data-stu-id="6bc37-135">Obtaining and assigning a Microsoft 365 license for your users.</span></span>
2. <span data-ttu-id="6bc37-136">在使用者電腦中解除安裝 Office 2010。</span><span class="sxs-lookup"><span data-stu-id="6bc37-136">Uninstalling Office 2010 on their computers.</span></span>
3. <span data-ttu-id="6bc37-p107">安裝 Office 365 專業增強版 (個別或搭配 IT 推出)。如需詳細資訊，請參閱[階段 4：Office 365 專業增強版](office365proplus-infrastructure.md)。</span><span class="sxs-lookup"><span data-stu-id="6bc37-p107">Installing Office 365 ProPlus, either individually or in conjunction with an IT rollout. For more information, see [Phase 4: Office 365 ProPlus](office365proplus-infrastructure.md).</span></span>

<span data-ttu-id="6bc37-139">Office 365 專業增強版會自動安裝更新，可以充分利用 Office 365 中以雲端為基礎的服務，以取得增強的安全性和生產力。</span><span class="sxs-lookup"><span data-stu-id="6bc37-139">Office 365 ProPlus installs updates automatically and can take advantage of cloud-based services in Office 365 for enhanced security and productivity.</span></span>

### <a name="office-2013-and-office-2016"></a><span data-ttu-id="6bc37-140">Office 2013 和 Office 2016</span><span class="sxs-lookup"><span data-stu-id="6bc37-140">Office 2013 and Office 2016</span></span>

<span data-ttu-id="6bc37-p108">尚未決定 Office 2013 和 Office 2016 版的 Office 終止支援藍圖。不過，以 Office 2010 為例，您仍然必須[安裝更新](https://support.office.com/article/install-office-updates-2ab296f3-7f03-43a2-8e50-46de917611c5)，其根據組織規模可能無法順利調整大小。若不使用 Office 2013 或 Office 2016 最新更新來持續更新您的電腦，或將電腦從 Office 2013 更新到 Office 2016，請考慮：</span><span class="sxs-lookup"><span data-stu-id="6bc37-p108">The end of support roadmap for the Office 2013 and Office 2016 versions of Office has not yet been determined. However, like Office 2010, you must still [install updates](https://support.office.com/article/install-office-updates-2ab296f3-7f03-43a2-8e50-46de917611c5), which might not scale well depending on the size of your organization. Rather than keep updating your computers with the latest updates for Office 2013 or Office 2016 or update your computers from Office 2013 to Office 2016, consider:</span></span>

1. <span data-ttu-id="6bc37-144">為使用者取得並指派 Microsoft 365 授權。</span><span class="sxs-lookup"><span data-stu-id="6bc37-144">Obtaining and assigning a Microsoft 365 license for your users.</span></span>
2. <span data-ttu-id="6bc37-145">在使用者電腦中解除安裝 Office 2013 或 Office 2016。</span><span class="sxs-lookup"><span data-stu-id="6bc37-145">Uninstalling Office 2013 or Office 2016 on their computers.</span></span>
3. <span data-ttu-id="6bc37-p109">安裝 Office 365 專業增強版 (個別或搭配 IT 推出)。如需詳細資訊，請參閱[階段 4：Office 365 專業增強版](office365proplus-infrastructure.md)。</span><span class="sxs-lookup"><span data-stu-id="6bc37-p109">Installing Office 365 ProPlus, either individually or in conjunction with an IT rollout. For more information, see [Phase 4: Office 365 ProPlus](office365proplus-infrastructure.md).</span></span>

<span data-ttu-id="6bc37-148">Office 365 專業增強版會自動安裝更新，可以充分利用 Office 365 中以雲端為基礎的服務，以取得增強的安全性和生產力。</span><span class="sxs-lookup"><span data-stu-id="6bc37-148">Office 365 ProPlus installs updates automatically and can take advantage of cloud-based services in Office 365 for enhanced security and productivity.</span></span>

## <a name="migration-for-microsoft-office-server-products"></a><span data-ttu-id="6bc37-149">Microsoft Office 伺服器產品的移轉</span><span class="sxs-lookup"><span data-stu-id="6bc37-149">Migration for Microsoft Office server products</span></span>

<span data-ttu-id="6bc37-p110">在許多大型和小型組織中，您可能會使用較舊版本的 Office 伺服器產品組合，例如 Exchange Server 與 SharePoint Server。這些較舊的版本：</span><span class="sxs-lookup"><span data-stu-id="6bc37-p110">In many organizations both large and small, you might be using a combination of older versions of the Office Server products, such as Exchange Server and SharePoint Server. These older versions:</span></span>

- <span data-ttu-id="6bc37-p111">應使用最新的安全性更新和支援修正進行更新。在某些情況下，這些更新會每月發行。</span><span class="sxs-lookup"><span data-stu-id="6bc37-p111">Should be updated with the latest security updates and support fixes. In some cases, these updates are released monthly.</span></span>
- <span data-ttu-id="6bc37-154">未以最佳化方式啟用以便運用 Microsoft 雲端技術，及協助您的企業進行數位轉型。</span><span class="sxs-lookup"><span data-stu-id="6bc37-154">Are not optimally enabled to leverage Microsoft’s cloud technologies and help you digitally transform your business.</span></span>
- <span data-ttu-id="6bc37-155">不包含新的生產力應用程式，例如 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="6bc37-155">Do not include new productivity applications, such as Microsoft Teams.</span></span>
- <span data-ttu-id="6bc37-156">不包含最新的安全性功能，例如 Exchange 進階威脅防護。</span><span class="sxs-lookup"><span data-stu-id="6bc37-156">Do not include the latest security features, such as Exchange Advanced Threat Protection.</span></span>

<span data-ttu-id="6bc37-p112">Microsoft 365 企業版包含 Office 365，其中包含雲端型版本的 Office 伺服器服務，其與內部部署版本的 Office 伺服器軟體使用部分相同工具，例如網頁瀏覽器和 Outlook 用戶端。這些服務會持續更新，而不需要 IT 人員，為您節省維護及更新內部部署伺服器所耗費的時間。這些服務也含有未在 Office 伺服器軟體中提供的增強功能。</span><span class="sxs-lookup"><span data-stu-id="6bc37-p112">Microsoft 365 Enterprise includes Office 365, which includes cloud-based versions of Office server services that use some of the same tools as on-premises versions of Office server software, such as web browsers and the Outlook client. These services are continually updated without involving IT, saving you the time it takes to maintain and update on-premises servers. These services also have enhancements not present in Office server software.</span></span> 

### <a name="office-server-2007"></a><span data-ttu-id="6bc37-160">Office Server 2007</span><span class="sxs-lookup"><span data-stu-id="6bc37-160">Office Server 2007</span></span>

<span data-ttu-id="6bc37-p113">對於 Office 2007 版的伺服器產品，已終止支援。請參閱下列文章取得詳細資料：</span><span class="sxs-lookup"><span data-stu-id="6bc37-p113">For server products in the Office 2007 release, the end of support has already passed. See these articles for the details:</span></span>

- [<span data-ttu-id="6bc37-163">Exchange 2007 終止支援藍圖</span><span class="sxs-lookup"><span data-stu-id="6bc37-163">Exchange 2007 end of support roadmap</span></span>](https://docs.microsoft.com/office365/enterprise/exchange-2007-end-of-support)
- [<span data-ttu-id="6bc37-164">SharePoint Server 2007 終止支援藍圖</span><span class="sxs-lookup"><span data-stu-id="6bc37-164">SharePoint Server 2007 end of support roadmap</span></span>](https://docs.microsoft.com/office365/enterprise/sharepoint-2007-end-of-support)
- [<span data-ttu-id="6bc37-165">Project Server 2007 終止支援藍圖</span><span class="sxs-lookup"><span data-stu-id="6bc37-165">Project Server 2007 end of support roadmap</span></span>](https://docs.microsoft.com/office365/enterprise/project-server-2007-end-of-support)
- [<span data-ttu-id="6bc37-166">Office Communications Server 終止支援藍圖</span><span class="sxs-lookup"><span data-stu-id="6bc37-166">Office Communications Server end of support roadmap</span></span>](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/upgrade)
- [<span data-ttu-id="6bc37-167">PerformancePoint Server 2007 終止支援藍圖</span><span class="sxs-lookup"><span data-stu-id="6bc37-167">PerformancePoint Server 2007 end of support roadmap</span></span>](https://docs.microsoft.com/office365/enterprise/pps-2007-end-of-support)

<span data-ttu-id="6bc37-168">若不使用 Office 2010、Office 2013 或 Office 2016 版的伺服器產品升級 Office 2007 版的伺服器產品，請考慮：</span><span class="sxs-lookup"><span data-stu-id="6bc37-168">Rather than upgrading your server products in the Office 2007 release with server products in the Office 2010, Office 2013, or Office 2016 releases, consider:</span></span>

1. <span data-ttu-id="6bc37-p114">將 Office 2007 伺服器上的資料移轉到 Office 365。如需協助，請雇用 Microsoft 合作夥伴。</span><span class="sxs-lookup"><span data-stu-id="6bc37-p114">Migrating the data on your Office 2007 servers to Office 365. To help with this, hire a Microsoft partner.</span></span>
2. <span data-ttu-id="6bc37-171">向使用者推出新功能和作業程序。</span><span class="sxs-lookup"><span data-stu-id="6bc37-171">Rolling out the new functionality and work processes to your users.</span></span>
3. <span data-ttu-id="6bc37-172">不再需要執行 Office 2007 伺服器產品的內部部署伺服器時，請予以解除。</span><span class="sxs-lookup"><span data-stu-id="6bc37-172">When there is no longer a need for the on-premises servers running Office 2007 server products, decommissioning them.</span></span>

### <a name="office-server-2010"></a><span data-ttu-id="6bc37-173">Office Server 2010</span><span class="sxs-lookup"><span data-stu-id="6bc37-173">Office Server 2010</span></span>

<span data-ttu-id="6bc37-174">對於 Office 2010 版的伺服器產品，已決定終止支援下列項目：</span><span class="sxs-lookup"><span data-stu-id="6bc37-174">For server products in the Office 2010 release, the end of support has been determined for the following:</span></span>

- [<span data-ttu-id="6bc37-175">Exchange Server 2010</span><span class="sxs-lookup"><span data-stu-id="6bc37-175">Exchange Server 2010</span></span>](https://docs.microsoft.com/office365/enterprise/exchange-2010-end-of-support)
- [<span data-ttu-id="6bc37-176">SharePoint Server 2010</span><span class="sxs-lookup"><span data-stu-id="6bc37-176">SharePoint Server 2010</span></span>](https://docs.microsoft.com/office365/enterprise/upgrade-from-sharepoint-2010)

<span data-ttu-id="6bc37-177">若不使用 Office 2013 或 Office 2016 版的伺服器產品升級 Office 2010 版的這些伺服器產品，請考慮：</span><span class="sxs-lookup"><span data-stu-id="6bc37-177">Rather than upgrading these server products in the Office 2010 release with server products in the Office 2013 or Office 2016 release, consider:</span></span>

1. <span data-ttu-id="6bc37-p115">將 Office 2010 伺服器上的資料移轉到 Office 365。如需協助，請參閱 [Microsoft 365 的 FastTrack](https://fasttrack.microsoft.com/microsoft365) 或雇用 Microsoft 合作夥伴。</span><span class="sxs-lookup"><span data-stu-id="6bc37-p115">Migrating the data on your Office 2010 servers to Office 365. To help with this, see [FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365) or hire a Microsoft partner.</span></span>
2. <span data-ttu-id="6bc37-180">向使用者推出新功能和作業程序。</span><span class="sxs-lookup"><span data-stu-id="6bc37-180">Rolling out the new functionality and work processes to your users.</span></span>
3. <span data-ttu-id="6bc37-181">不再需要執行 Office 2010 伺服器產品的內部部署伺服器時，請予以解除。</span><span class="sxs-lookup"><span data-stu-id="6bc37-181">When there is no longer a need for the on-premises servers running Office 2010 server products, decommissioning them.</span></span>

### <a name="office-server-2013"></a><span data-ttu-id="6bc37-182">Office Server 2013</span><span class="sxs-lookup"><span data-stu-id="6bc37-182">Office Server 2013</span></span>

<span data-ttu-id="6bc37-p116">對於 Office 2013 版的伺服器產品，尚未決定終止支援。若不使用 Office 2016 版的伺服器產品升級 Office 2013 版的伺服器產品，請考慮：</span><span class="sxs-lookup"><span data-stu-id="6bc37-p116">For server products in the Office 2013 release, the end of support has not been determined. Rather than upgrading your server products in the Office 2013 release with server products in the Office 2016 release, consider:</span></span>

1. <span data-ttu-id="6bc37-p117">將 Office 2013 伺服器上的資料移轉到 Office 365。如需協助，請參閱 [Microsoft 365 的 FastTrack](https://fasttrack.microsoft.com/microsoft365) 或雇用 Microsoft 合作夥伴。</span><span class="sxs-lookup"><span data-stu-id="6bc37-p117">Migrating the data on your Office 2013 servers to Office 365. To help with this, see [FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365) or hire a Microsoft partner.</span></span>
2. <span data-ttu-id="6bc37-187">向使用者推出新功能和作業程序。</span><span class="sxs-lookup"><span data-stu-id="6bc37-187">Rolling out the new functionality and work processes to your users.</span></span>
3. <span data-ttu-id="6bc37-188">不再需要執行 Office 2013 伺服器產品的內部部署伺服器時，請予以解除。</span><span class="sxs-lookup"><span data-stu-id="6bc37-188">When there is no longer a need for the on-premises servers running Office 2013 server products, decommissioning them.</span></span>

### <a name="office-server-2016"></a><span data-ttu-id="6bc37-189">Office Server 2016</span><span class="sxs-lookup"><span data-stu-id="6bc37-189">Office Server 2016</span></span>

<span data-ttu-id="6bc37-p118">對於 Office 2016 版的伺服器產品，尚未決定終止支援。若要充分利用以雲端為基礎的服務和增強功能，以便貴公司進行數位轉型，請考慮：</span><span class="sxs-lookup"><span data-stu-id="6bc37-p118">For server products in the Office 2016 release, the end of support has not been determined. To take advantage of the cloud-based service and enhancements to digitally transform your business, consider:</span></span>

1. <span data-ttu-id="6bc37-p119">將 Office 2016 伺服器上的資料移轉到 Office 365。如需協助，請參閱 [Microsoft 365 的 FastTrack](https://fasttrack.microsoft.com/microsoft365) 或雇用 Microsoft 合作夥伴。</span><span class="sxs-lookup"><span data-stu-id="6bc37-p119">Migrating the data on your Office 2016 servers to Office 365. To help with this, see [FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365) or hire a Microsoft partner.</span></span>
2. <span data-ttu-id="6bc37-194">向使用者推出新功能和作業程序。</span><span class="sxs-lookup"><span data-stu-id="6bc37-194">Rolling out the new functionality and work processes to your users.</span></span>
3. <span data-ttu-id="6bc37-195">不再需要執行 Office 2016 伺服器產品的內部部署伺服器時，請予以解除。</span><span class="sxs-lookup"><span data-stu-id="6bc37-195">When there is no longer a need for the on-premises servers running Office 2016 server products, decommissioning them.</span></span>

## <a name="migration-for-microsoft-windows"></a><span data-ttu-id="6bc37-196">Microsoft Windows 的移轉</span><span class="sxs-lookup"><span data-stu-id="6bc37-196">Migration for Microsoft Windows</span></span>

<span data-ttu-id="6bc37-197">若要移轉執行 Windows 7 或 Windows 8.1 的裝置，您可以執行[就地升級](https://docs.microsoft.com/microsoft-365/enterprise/windows10-deploy-inplaceupgrade)。</span><span class="sxs-lookup"><span data-stu-id="6bc37-197">To migrate your devices running Windows 7 or Windows 8.1, you can perform an [in-place upgrade](https://docs.microsoft.com/microsoft-365/enterprise/windows10-deploy-inplaceupgrade).</span></span> 

<span data-ttu-id="6bc37-p120">如需其他方法，請參閱 [Windows 10 部署案例](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios)。您也可以自行[規劃 Windows 10 部署](https://aka.ms/planforwin10deployment)。</span><span class="sxs-lookup"><span data-stu-id="6bc37-p120">For additional methods, see [Windows 10 deployment scenarios](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios). You can also [plan for Windows 10 deployment](https://aka.ms/planforwin10deployment) on your own.</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="6bc37-200">Microsoft 如何執行 Microsoft 365 企業版</span><span class="sxs-lookup"><span data-stu-id="6bc37-200">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="6bc37-201">請查看 Microsoft 的 IT 專業人員如何使用以下資源將公司移轉到 Microsoft 365 企業版：</span><span class="sxs-lookup"><span data-stu-id="6bc37-201">See how IT experts at Microsoft migrated the company to Microsoft 365 Enterprise with these resources:</span></span> 

- [<span data-ttu-id="6bc37-202">部署及更新 Microsoft Office 365 專業增強版</span><span class="sxs-lookup"><span data-stu-id="6bc37-202">Deploying and updating Microsoft Office 365 ProPlus</span></span>](https://www.microsoft.com/itshowcase/Article/Content/757/Deploying-and-updating-Microsoft-Office-365-ProPlus)
- [<span data-ttu-id="6bc37-203">Microsoft 會將 150000 個信箱移轉到 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="6bc37-203">Microsoft migrates 150,000 mailboxes to Exchange Online</span></span>](https://www.microsoft.com/itshowcase/Article/Content/577/Microsoft-migrates-150000-mailboxes-to-Exchange-Online)
- [<span data-ttu-id="6bc37-204">SharePoint 至雲端：深入了解 Microsoft 如何執行自己的移轉</span><span class="sxs-lookup"><span data-stu-id="6bc37-204">SharePoint to the cloud: Learn how Microsoft ran its own migration</span></span>](https://www.microsoft.com/itshowcase/Article/Content/691/SharePoint-to-the-cloud-Learn-how-Microsoft-ran-its-own-migration)
- [<span data-ttu-id="6bc37-205">在 Microsoft 以就地升級方式部署 Windows 10</span><span class="sxs-lookup"><span data-stu-id="6bc37-205">Deploying Windows 10 at Microsoft as an in-place upgrade</span></span>](https://www.microsoft.com/itshowcase/Article/Content/668/Deploying-Windows-10-at-Microsoft-as-an-inplace-upgrade)
- <span data-ttu-id="6bc37-206">[Windows 10 部署：Microsoft IT 的秘訣與技巧](https://www.microsoft.com/itshowcase/Article/Content/951/Windows-10-deployment-tips-and-tricks-from-Microsoft-IT) (影片)</span><span class="sxs-lookup"><span data-stu-id="6bc37-206">[Windows 10 deployment: tips and tricks from Microsoft IT](https://www.microsoft.com/itshowcase/Article/Content/951/Windows-10-deployment-tips-and-tricks-from-Microsoft-IT) (video)</span></span>

## <a name="result"></a><span data-ttu-id="6bc37-207">結果</span><span class="sxs-lookup"><span data-stu-id="6bc37-207">Result</span></span>

<span data-ttu-id="6bc37-208">貴組織已將舊版 Microsoft Office、Office 伺服器及 Windows 移轉為 Microsoft 365 企業版。</span><span class="sxs-lookup"><span data-stu-id="6bc37-208">Your organization has migrated older versions of Microsoft Office, Office servers, and Windows to Microsoft 365 Enterprise.</span></span>
