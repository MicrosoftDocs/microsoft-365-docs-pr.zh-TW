---
title: 移轉至 Microsoft 365 企業版
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/12/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: 在整個組織中逐步執行將 Microsoft Office、Office 伺服器及 Windows 的各版本移轉為 Microsoft 365 企業版的程序。
ms.openlocfilehash: f82e65cdff674884466fe70a299250c92f356186
ms.sourcegitcommit: 86dba00cd786ac8ea761cdfcd85dfbd33e64d088
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/12/2019
ms.locfileid: "36297875"
---
# <a name="migration-to-microsoft-365-enterprise"></a><span data-ttu-id="51b1d-103">移轉至 Microsoft 365 企業版</span><span class="sxs-lookup"><span data-stu-id="51b1d-103">Migration to Microsoft 365 Enterprise</span></span>

<span data-ttu-id="51b1d-p101">大多數的企業組織擁有異質環境，其中具有多種版本的作業系統、用戶端軟體及伺服器軟體。Microsoft 365 企業版包含 IT 基礎結構中這些主要元件最安全的版本，且具有專為充分利用雲端技術所設計的生產力功能。</span><span class="sxs-lookup"><span data-stu-id="51b1d-p101">Most enterprise organizations have a heterogeneous environment with multiple releases of operating systems, client software, and server software. Microsoft 365 Enterprise includes the most secure versions of these key components of your IT infrastructure with productivity features that are designed to take advantage of cloud technologies.</span></span>

<span data-ttu-id="51b1d-106">若要充分發揮 Microsoft 365 企業版產品整合套件的商務價值，請開始規劃並實作策略以移轉以下版本：</span><span class="sxs-lookup"><span data-stu-id="51b1d-106">To maximize the business value of the Microsoft 365 Enterprise integrated suite of products, begin planning and implementing a strategy to migrate releases of:</span></span>

- <span data-ttu-id="51b1d-107">將安裝在您電腦上的 Office 用戶端移轉為 Office 365 專業增強版</span><span class="sxs-lookup"><span data-stu-id="51b1d-107">The Office client installed on your computers to Office 365 ProPlus</span></span>
- <span data-ttu-id="51b1d-108">將安裝在您伺服器上的 Office 伺服器移轉為 Office 365 中的對等服務</span><span class="sxs-lookup"><span data-stu-id="51b1d-108">Office servers installed on your servers to their equivalent services in Office 365</span></span>
- <span data-ttu-id="51b1d-109">將裝置上的 Windows 7 和 Windows 8.1 移轉為 Windows 10 企業版</span><span class="sxs-lookup"><span data-stu-id="51b1d-109">Windows 7 and Windows 8.1 on your devices to Windows 10 Enterprise</span></span>

>[!Note]
><span data-ttu-id="51b1d-110">Windows 7 將於 2020 年 1 月 14 日進入終止支援。</span><span class="sxs-lookup"><span data-stu-id="51b1d-110">Windows 7 reaches end of support on January 14, 2020.</span></span> <span data-ttu-id="51b1d-111">如需詳細資訊，請按一下[這裡](https://support.microsoft.com/help/4057281/windows-7-support-will-end-on-january-14-2020)。</span><span class="sxs-lookup"><span data-stu-id="51b1d-111">For more information, click [?](https://support.microsoft.com/help/4057281/windows-7-support-will-end-on-january-14-2020).</span></span>
>

<span data-ttu-id="51b1d-112">在一段時間內完成所有這些移轉，讓您的組織更接近[現代職場](https://www.microsoft.com/microsoft-365/blog/2018/04/27/making-it-simpler-with-a-modern-workplace/)，也就是安全的整合式環境，讓組織可發揮團隊合作和創意，而以上這些都是藉由 Microsoft 365 企業版來提供及達成。</span><span class="sxs-lookup"><span data-stu-id="51b1d-112">Accomplishing all of these migrations over time gets your organization closer to the [modern workplace](https://www.microsoft.com/microsoft-365/blog/2018/04/27/making-it-simpler-with-a-modern-workplace/), a secure and integrated environment that unlocks teamwork and creativity in your organization, all of which is enabled and empowered by Microsoft 365 Enterprise.</span></span> 

<span data-ttu-id="51b1d-113">如需關於為特定 Office 365 工作負載遷移使用者和資料的資訊：</span><span class="sxs-lookup"><span data-stu-id="51b1d-113">For information about migrating users and data for specific Office 365 workloads:</span></span>

- <span data-ttu-id="51b1d-114">使用者信箱從 Exchange Server 到 Exchange Online，請參閱 [Exchange Online 工作負載](exchangeonline-workload.md)。</span><span class="sxs-lookup"><span data-stu-id="51b1d-114">User mailboxes from Exchange Server to Exchange Online, see the [Exchange Online workload](exchangeonline-workload.md).</span></span>
- <span data-ttu-id="51b1d-115">SharePoint 資料從 SharePoint Server 到 SharePoint Online，請參閱 [SharePoint Online 工作負載](sharepoint-online-onedrive-workload.md)。</span><span class="sxs-lookup"><span data-stu-id="51b1d-115">SharePoint data from SharePoint Server to SharePoint Online, see the [SharePoint Online workload](sharepoint-online-onedrive-workload.md).</span></span>
- <span data-ttu-id="51b1d-116">商務用 Skype Online 到 Microsoft Teams，請參閱 [Microsoft Teams 工作負載](teams-workload.md)。</span><span class="sxs-lookup"><span data-stu-id="51b1d-116">Skype for Business Online to Microsoft Teams, see the [Microsoft Teams workload](teams-workload.md).</span></span>

## <a name="migration-for-microsoft-office-client-products"></a><span data-ttu-id="51b1d-117">Microsoft Office 用戶端產品的移轉</span><span class="sxs-lookup"><span data-stu-id="51b1d-117">Migration for Microsoft Office client products</span></span>

<span data-ttu-id="51b1d-p103">在許多大型和小型組織中，您可能會使用較舊版本的 Office 用戶端產品組合，例如 Word、Excel 和 PowerPoint。這些較舊的版本：</span><span class="sxs-lookup"><span data-stu-id="51b1d-p103">In many organizations both large and small, you might be using a combination of older versions of the Office client products, such as Word, Excel, and PowerPoint. These older versions:</span></span>

- <span data-ttu-id="51b1d-120">可使用最新的安全性更新和支援修正進行[更新](https://support.office.com/article/install-office-updates-2ab296f3-7f03-43a2-8e50-46de917611c5)，但此程序有時需手動進行，且可能無法擴及整個組織。</span><span class="sxs-lookup"><span data-stu-id="51b1d-120">Can be [updated](https://support.office.com/article/install-office-updates-2ab296f3-7f03-43a2-8e50-46de917611c5) with the latest security updates and support fixes, but the process is sometimes manual and might not scale across your organization.</span></span>
- <span data-ttu-id="51b1d-121">未以最佳化方式啟用以便運用 Microsoft 雲端技術，及協助您的企業進行數位轉型。</span><span class="sxs-lookup"><span data-stu-id="51b1d-121">Are not optimally enabled to leverage Microsoft’s cloud technologies and help you digitally transform your business.</span></span>
 
<span data-ttu-id="51b1d-p104">Microsoft 365 企業版包含 Office 365 專業增強版，此 Office 用戶端產品版本可使用 Microsoft 365 企業版授權，且會從 Microsoft 雲端進行安裝與更新。請參閱[關於企業中的 Office 365 專業增強版](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise)以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="51b1d-p104">Microsoft 365 Enterprise includes Office 365 ProPlus, a version of the Office client products that is available with a Microsoft 365 Enterprise license and is installed and updated from the Microsoft cloud. See [About Office 365 ProPlus in the enterprise](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise) for more information.</span></span>

### <a name="office-2007"></a><span data-ttu-id="51b1d-124">Office 2007</span><span class="sxs-lookup"><span data-stu-id="51b1d-124">Office 2007</span></span>

<span data-ttu-id="51b1d-p105">針對 Office 2007 版的 Office 版本，已終止支援。如需詳細資訊，請參閱 [Office 2007 終止支援藍圖](https://docs.microsoft.com/deployoffice/office-2007-end-support-roadmap)。</span><span class="sxs-lookup"><span data-stu-id="51b1d-p105">For versions of Office in the Office 2007 release, the end of support has already passed. See [Office 2007 End of Support Roadmap](https://docs.microsoft.com/deployoffice/office-2007-end-support-roadmap) for more information.</span></span>

<span data-ttu-id="51b1d-127">若不使用 Office 2010、Office 2013 或 Office 2016 來升級您執行 Office 2007 的電腦，請考慮：</span><span class="sxs-lookup"><span data-stu-id="51b1d-127">Rather than upgrading your computers running Office 2007 with Office 2010, Office 2013, or Office 2016, consider:</span></span>

1. <span data-ttu-id="51b1d-128">為使用者取得並指派 Microsoft 365 授權。</span><span class="sxs-lookup"><span data-stu-id="51b1d-128">Obtaining and assigning a Microsoft 365 license for your users.</span></span>
2. <span data-ttu-id="51b1d-129">在使用者電腦中解除安裝 Office 2007。</span><span class="sxs-lookup"><span data-stu-id="51b1d-129">Uninstalling Office 2007 on their computers.</span></span>
3. <span data-ttu-id="51b1d-p106">安裝 Office 365 專業增強版 (個別或搭配 IT 推出)。如需詳細資訊，請參閱[階段 4：Office 365 專業增強版](office365proplus-infrastructure.md)。</span><span class="sxs-lookup"><span data-stu-id="51b1d-p106">Installing Office 365 ProPlus, either individually or in conjunction with an IT rollout. For more information, see [Phase 4: Office 365 ProPlus](office365proplus-infrastructure.md).</span></span>

<span data-ttu-id="51b1d-132">Office 365 專業增強版會自動安裝更新，可以充分利用 Office 365 中以雲端為基礎的服務，以取得增強的安全性和生產力。</span><span class="sxs-lookup"><span data-stu-id="51b1d-132">Office 365 ProPlus installs updates automatically and can take advantage of cloud-based services in Office 365 for enhanced security and productivity.</span></span>

### <a name="office-2010"></a><span data-ttu-id="51b1d-133">Office 2010</span><span class="sxs-lookup"><span data-stu-id="51b1d-133">Office 2010</span></span>

<span data-ttu-id="51b1d-p107">針對 Office 2010 版的 Office 版本，將在 2020 年 10 月 13 日終止支援。如需詳細資訊，請參閱 [Office 2010 終止支援藍圖](https://docs.microsoft.com/deployoffice/office-2010-end-support-roadmap)。</span><span class="sxs-lookup"><span data-stu-id="51b1d-p107">For versions of Office in the Office 2010 release, the end of support is October 13, 2020. For more information, see [Office 2010 end of support roadmap](https://docs.microsoft.com/deployoffice/office-2010-end-support-roadmap).</span></span>

<span data-ttu-id="51b1d-136">若不使用 Office 2013 或 Office 2016 (這兩者都必須手動更新) 來升級您執行 Office 2010 的電腦，請考慮：</span><span class="sxs-lookup"><span data-stu-id="51b1d-136">Rather than upgrading your computers running Office 2010 with Office 2013 or Office 2016, both of which must be manually updated, consider:</span></span> 

1. <span data-ttu-id="51b1d-137">為使用者取得並指派 Microsoft 365 授權。</span><span class="sxs-lookup"><span data-stu-id="51b1d-137">Obtaining and assigning a Microsoft 365 license for your users.</span></span>
2. <span data-ttu-id="51b1d-138">在使用者電腦中解除安裝 Office 2010。</span><span class="sxs-lookup"><span data-stu-id="51b1d-138">Uninstalling Office 2010 on their computers.</span></span>
3. <span data-ttu-id="51b1d-p108">安裝 Office 365 專業增強版 (個別或搭配 IT 推出)。如需詳細資訊，請參閱[階段 4：Office 365 專業增強版](office365proplus-infrastructure.md)。</span><span class="sxs-lookup"><span data-stu-id="51b1d-p108">Installing Office 365 ProPlus, either individually or in conjunction with an IT rollout. For more information, see [Phase 4: Office 365 ProPlus](office365proplus-infrastructure.md).</span></span>

<span data-ttu-id="51b1d-141">Office 365 專業增強版會自動安裝更新，可以充分利用 Office 365 中以雲端為基礎的服務，以取得增強的安全性和生產力。</span><span class="sxs-lookup"><span data-stu-id="51b1d-141">Office 365 ProPlus installs updates automatically and can take advantage of cloud-based services in Office 365 for enhanced security and productivity.</span></span>

### <a name="office-2013-and-office-2016"></a><span data-ttu-id="51b1d-142">Office 2013 和 Office 2016</span><span class="sxs-lookup"><span data-stu-id="51b1d-142">Office 2013 and Office 2016</span></span>

<span data-ttu-id="51b1d-p109">尚未決定 Office 2013 和 Office 2016 版的 Office 終止支援藍圖。不過，以 Office 2010 為例，您仍然必須[安裝更新](https://support.office.com/article/install-office-updates-2ab296f3-7f03-43a2-8e50-46de917611c5)，其根據組織規模可能無法順利調整大小。若不使用 Office 2013 或 Office 2016 最新更新來持續更新您的電腦，或將電腦從 Office 2013 更新到 Office 2016，請考慮：</span><span class="sxs-lookup"><span data-stu-id="51b1d-p109">The end of support roadmap for the Office 2013 and Office 2016 versions of Office has not yet been determined. However, like Office 2010, you must still [install updates](https://support.office.com/article/install-office-updates-2ab296f3-7f03-43a2-8e50-46de917611c5), which might not scale well depending on the size of your organization. Rather than keep updating your computers with the latest updates for Office 2013 or Office 2016 or update your computers from Office 2013 to Office 2016, consider:</span></span>

1. <span data-ttu-id="51b1d-146">為使用者取得並指派 Microsoft 365 授權。</span><span class="sxs-lookup"><span data-stu-id="51b1d-146">Obtaining and assigning a Microsoft 365 license for your users.</span></span>
2. <span data-ttu-id="51b1d-147">在使用者電腦中解除安裝 Office 2013 或 Office 2016。</span><span class="sxs-lookup"><span data-stu-id="51b1d-147">Uninstalling Office 2013 or Office 2016 on their computers.</span></span>
3. <span data-ttu-id="51b1d-p110">安裝 Office 365 專業增強版 (個別或搭配 IT 推出)。如需詳細資訊，請參閱[階段 4：Office 365 專業增強版](office365proplus-infrastructure.md)。</span><span class="sxs-lookup"><span data-stu-id="51b1d-p110">Installing Office 365 ProPlus, either individually or in conjunction with an IT rollout. For more information, see [Phase 4: Office 365 ProPlus](office365proplus-infrastructure.md).</span></span>

<span data-ttu-id="51b1d-150">Office 365 專業增強版會自動安裝更新，可以充分利用 Office 365 中以雲端為基礎的服務，以取得增強的安全性和生產力。</span><span class="sxs-lookup"><span data-stu-id="51b1d-150">Office 365 ProPlus installs updates automatically and can take advantage of cloud-based services in Office 365 for enhanced security and productivity.</span></span>

## <a name="migration-for-microsoft-office-server-products"></a><span data-ttu-id="51b1d-151">Microsoft Office 伺服器產品的移轉</span><span class="sxs-lookup"><span data-stu-id="51b1d-151">Migration for Microsoft Office server products</span></span>

<span data-ttu-id="51b1d-p111">在許多大型和小型組織中，您可能會使用較舊版本的 Office 伺服器產品組合，例如 Exchange Server 與 SharePoint Server。這些較舊的版本：</span><span class="sxs-lookup"><span data-stu-id="51b1d-p111">In many organizations both large and small, you might be using a combination of older versions of the Office Server products, such as Exchange Server and SharePoint Server. These older versions:</span></span>

- <span data-ttu-id="51b1d-p112">應使用最新的安全性更新和支援修正進行更新。在某些情況下，這些更新會每月發行。</span><span class="sxs-lookup"><span data-stu-id="51b1d-p112">Should be updated with the latest security updates and support fixes. In some cases, these updates are released monthly.</span></span>
- <span data-ttu-id="51b1d-156">未以最佳化方式啟用以便運用 Microsoft 雲端技術，及協助您的企業進行數位轉型。</span><span class="sxs-lookup"><span data-stu-id="51b1d-156">Are not optimally enabled to leverage Microsoft’s cloud technologies and help you digitally transform your business.</span></span>
- <span data-ttu-id="51b1d-157">不包含新的生產力應用程式，例如 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="51b1d-157">Do not include new productivity applications, such as Microsoft Teams.</span></span>
- <span data-ttu-id="51b1d-158">不包含最新的安全性功能，例如 Exchange 進階威脅防護。</span><span class="sxs-lookup"><span data-stu-id="51b1d-158">Do not include the latest security features, such as Exchange Advanced Threat Protection.</span></span>

<span data-ttu-id="51b1d-p113">Microsoft 365 企業版包含 Office 365，其中包含雲端型版本的 Office 伺服器服務，其與內部部署版本的 Office 伺服器軟體使用部分相同工具，例如網頁瀏覽器和 Outlook 用戶端。這些服務會持續更新，而不需要 IT 人員，為您節省維護及更新內部部署伺服器所耗費的時間。這些服務也含有未在 Office 伺服器軟體中提供的增強功能。</span><span class="sxs-lookup"><span data-stu-id="51b1d-p113">Microsoft 365 Enterprise includes Office 365, which includes cloud-based versions of Office server services that use some of the same tools as on-premises versions of Office server software, such as web browsers and the Outlook client. These services are continually updated without involving IT, saving you the time it takes to maintain and update on-premises servers. These services also have enhancements not present in Office server software.</span></span> 

### <a name="office-server-2007"></a><span data-ttu-id="51b1d-162">Office Server 2007</span><span class="sxs-lookup"><span data-stu-id="51b1d-162">Office Server 2007</span></span>

<span data-ttu-id="51b1d-p114">對於 Office 2007 版的伺服器產品，已終止支援。請參閱下列文章取得詳細資料：</span><span class="sxs-lookup"><span data-stu-id="51b1d-p114">For server products in the Office 2007 release, the end of support has already passed. See these articles for the details:</span></span>

- [<span data-ttu-id="51b1d-165">Exchange 2007 終止支援藍圖</span><span class="sxs-lookup"><span data-stu-id="51b1d-165">Exchange 2007 end of support roadmap</span></span>](https://docs.microsoft.com/office365/enterprise/exchange-2007-end-of-support)
- [<span data-ttu-id="51b1d-166">SharePoint Server 2007 終止支援藍圖</span><span class="sxs-lookup"><span data-stu-id="51b1d-166">SharePoint Server 2007 end of support roadmap</span></span>](https://docs.microsoft.com/office365/enterprise/sharepoint-2007-end-of-support)
- [<span data-ttu-id="51b1d-167">Project Server 2007 終止支援藍圖</span><span class="sxs-lookup"><span data-stu-id="51b1d-167">Project Server 2007 end of support roadmap</span></span>](https://docs.microsoft.com/office365/enterprise/project-server-2007-end-of-support)
- [<span data-ttu-id="51b1d-168">Office Communications Server 終止支援藍圖</span><span class="sxs-lookup"><span data-stu-id="51b1d-168">Office Communications Server end of support roadmap</span></span>](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/upgrade)
- [<span data-ttu-id="51b1d-169">PerformancePoint Server 2007 終止支援藍圖</span><span class="sxs-lookup"><span data-stu-id="51b1d-169">PerformancePoint Server 2007 end of support roadmap</span></span>](https://docs.microsoft.com/office365/enterprise/pps-2007-end-of-support)

<span data-ttu-id="51b1d-170">若不使用 Office 2010、Office 2013 或 Office 2016 版的伺服器產品升級 Office 2007 版的伺服器產品，請考慮：</span><span class="sxs-lookup"><span data-stu-id="51b1d-170">Rather than upgrading your server products in the Office 2007 release with server products in the Office 2010, Office 2013, or Office 2016 releases, consider:</span></span>

1. <span data-ttu-id="51b1d-p115">將 Office 2007 伺服器上的資料移轉到 Office 365。如需協助，請雇用 Microsoft 合作夥伴。</span><span class="sxs-lookup"><span data-stu-id="51b1d-p115">Migrating the data on your Office 2007 servers to Office 365. To help with this, hire a Microsoft partner.</span></span>
2. <span data-ttu-id="51b1d-173">向使用者推出新功能和作業程序。</span><span class="sxs-lookup"><span data-stu-id="51b1d-173">Rolling out the new functionality and work processes to your users.</span></span>
3. <span data-ttu-id="51b1d-174">不再需要執行 Office 2007 伺服器產品的內部部署伺服器時，請予以解除。</span><span class="sxs-lookup"><span data-stu-id="51b1d-174">When there is no longer a need for the on-premises servers running Office 2007 server products, decommissioning them.</span></span>

### <a name="office-server-2010"></a><span data-ttu-id="51b1d-175">Office Server 2010</span><span class="sxs-lookup"><span data-stu-id="51b1d-175">Office Server 2010</span></span>

<span data-ttu-id="51b1d-176">對於 Office 2010 版的伺服器產品，已決定終止支援下列項目：</span><span class="sxs-lookup"><span data-stu-id="51b1d-176">For server products in the Office 2010 release, the end of support has been determined for the following:</span></span>

- [<span data-ttu-id="51b1d-177">Exchange Server 2010</span><span class="sxs-lookup"><span data-stu-id="51b1d-177">Exchange Server 2010</span></span>](https://docs.microsoft.com/office365/enterprise/exchange-2010-end-of-support)
- [<span data-ttu-id="51b1d-178">SharePoint Server 2010</span><span class="sxs-lookup"><span data-stu-id="51b1d-178">SharePoint Server 2010</span></span>](https://docs.microsoft.com/office365/enterprise/upgrade-from-sharepoint-2010)

<span data-ttu-id="51b1d-179">若不使用 Office 2013 或 Office 2016 版的伺服器產品升級 Office 2010 版的這些伺服器產品，請考慮：</span><span class="sxs-lookup"><span data-stu-id="51b1d-179">Rather than upgrading these server products in the Office 2010 release with server products in the Office 2013 or Office 2016 release, consider:</span></span>

1. <span data-ttu-id="51b1d-p116">將 Office 2010 伺服器上的資料移轉到 Office 365。如需協助，請參閱 [Microsoft 365 的 FastTrack](https://fasttrack.microsoft.com/microsoft365) 或雇用 Microsoft 合作夥伴。</span><span class="sxs-lookup"><span data-stu-id="51b1d-p116">Migrating the data on your Office 2010 servers to Office 365. To help with this, see [FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365) or hire a Microsoft partner.</span></span>
2. <span data-ttu-id="51b1d-182">向使用者推出新功能和作業程序。</span><span class="sxs-lookup"><span data-stu-id="51b1d-182">Rolling out the new functionality and work processes to your users.</span></span>
3. <span data-ttu-id="51b1d-183">不再需要執行 Office 2010 伺服器產品的內部部署伺服器時，請予以解除。</span><span class="sxs-lookup"><span data-stu-id="51b1d-183">When there is no longer a need for the on-premises servers running Office 2010 server products, decommissioning them.</span></span>

### <a name="office-server-2013"></a><span data-ttu-id="51b1d-184">Office Server 2013</span><span class="sxs-lookup"><span data-stu-id="51b1d-184">Office Server 2013</span></span>

<span data-ttu-id="51b1d-p117">對於 Office 2013 版的伺服器產品，尚未決定終止支援。若不使用 Office 2016 版的伺服器產品升級 Office 2013 版的伺服器產品，請考慮：</span><span class="sxs-lookup"><span data-stu-id="51b1d-p117">For server products in the Office 2013 release, the end of support has not been determined. Rather than upgrading your server products in the Office 2013 release with server products in the Office 2016 release, consider:</span></span>

1. <span data-ttu-id="51b1d-p118">將 Office 2013 伺服器上的資料移轉到 Office 365。如需協助，請參閱 [Microsoft 365 的 FastTrack](https://fasttrack.microsoft.com/microsoft365) 或雇用 Microsoft 合作夥伴。</span><span class="sxs-lookup"><span data-stu-id="51b1d-p118">Migrating the data on your Office 2013 servers to Office 365. To help with this, see [FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365) or hire a Microsoft partner.</span></span>
2. <span data-ttu-id="51b1d-189">向使用者推出新功能和作業程序。</span><span class="sxs-lookup"><span data-stu-id="51b1d-189">Rolling out the new functionality and work processes to your users.</span></span>
3. <span data-ttu-id="51b1d-190">不再需要執行 Office 2013 伺服器產品的內部部署伺服器時，請予以解除。</span><span class="sxs-lookup"><span data-stu-id="51b1d-190">When there is no longer a need for the on-premises servers running Office 2013 server products, decommissioning them.</span></span>

### <a name="office-server-2016"></a><span data-ttu-id="51b1d-191">Office Server 2016</span><span class="sxs-lookup"><span data-stu-id="51b1d-191">Office Server 2016</span></span>

<span data-ttu-id="51b1d-p119">對於 Office 2016 版的伺服器產品，尚未決定終止支援。若要充分利用以雲端為基礎的服務和增強功能，以便貴公司進行數位轉型，請考慮：</span><span class="sxs-lookup"><span data-stu-id="51b1d-p119">For server products in the Office 2016 release, the end of support has not been determined. To take advantage of the cloud-based service and enhancements to digitally transform your business, consider:</span></span>

1. <span data-ttu-id="51b1d-p120">將 Office 2016 伺服器上的資料移轉到 Office 365。如需協助，請參閱 [Microsoft 365 的 FastTrack](https://fasttrack.microsoft.com/microsoft365) 或雇用 Microsoft 合作夥伴。</span><span class="sxs-lookup"><span data-stu-id="51b1d-p120">Migrating the data on your Office 2016 servers to Office 365. To help with this, see [FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365) or hire a Microsoft partner.</span></span>
2. <span data-ttu-id="51b1d-196">向使用者推出新功能和作業程序。</span><span class="sxs-lookup"><span data-stu-id="51b1d-196">Rolling out the new functionality and work processes to your users.</span></span>
3. <span data-ttu-id="51b1d-197">不再需要執行 Office 2016 伺服器產品的內部部署伺服器時，請予以解除。</span><span class="sxs-lookup"><span data-stu-id="51b1d-197">When there is no longer a need for the on-premises servers running Office 2016 server products, decommissioning them.</span></span>

## <a name="migration-for-microsoft-windows"></a><span data-ttu-id="51b1d-198">Microsoft Windows 的移轉</span><span class="sxs-lookup"><span data-stu-id="51b1d-198">Migration for Microsoft Windows</span></span>

<span data-ttu-id="51b1d-199">若要移轉執行 Windows 7 或 Windows 8.1 的裝置，您可以執行[就地升級](https://docs.microsoft.com/microsoft-365/enterprise/windows10-deploy-inplaceupgrade)。</span><span class="sxs-lookup"><span data-stu-id="51b1d-199">To migrate your devices running Windows 7 or Windows 8.1, you can perform an [in-place upgrade](https://docs.microsoft.com/microsoft-365/enterprise/windows10-deploy-inplaceupgrade).</span></span> 

<span data-ttu-id="51b1d-p121">如需其他方法，請參閱 [Windows 10 部署案例](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios)。您也可以自行[規劃 Windows 10 部署](https://aka.ms/planforwin10deployment)。</span><span class="sxs-lookup"><span data-stu-id="51b1d-p121">For additional methods, see [Windows 10 deployment scenarios](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios). You can also [plan for Windows 10 deployment](https://aka.ms/planforwin10deployment) on your own.</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="51b1d-202">Microsoft 如何執行 Microsoft 365 企業版</span><span class="sxs-lookup"><span data-stu-id="51b1d-202">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="51b1d-203">請查看 Microsoft 的 IT 專業人員如何使用以下資源將公司移轉到 Microsoft 365 企業版：</span><span class="sxs-lookup"><span data-stu-id="51b1d-203">See how IT experts at Microsoft migrated the company to Microsoft 365 Enterprise with these resources:</span></span> 

- [<span data-ttu-id="51b1d-204">部署及更新 Microsoft Office 365 專業增強版</span><span class="sxs-lookup"><span data-stu-id="51b1d-204">Deploying and updating Microsoft Office 365 ProPlus</span></span>](https://www.microsoft.com/itshowcase/Article/Content/757/Deploying-and-updating-Microsoft-Office-365-ProPlus)
- [<span data-ttu-id="51b1d-205">Microsoft 會將 150000 個信箱移轉到 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="51b1d-205">Microsoft migrates 150,000 mailboxes to Exchange Online</span></span>](https://www.microsoft.com/itshowcase/Article/Content/577/Microsoft-migrates-150000-mailboxes-to-Exchange-Online)
- [<span data-ttu-id="51b1d-206">SharePoint 至雲端：深入了解 Microsoft 如何執行自己的移轉</span><span class="sxs-lookup"><span data-stu-id="51b1d-206">SharePoint to the cloud: Learn how Microsoft ran its own migration</span></span>](https://www.microsoft.com/itshowcase/Article/Content/691/SharePoint-to-the-cloud-Learn-how-Microsoft-ran-its-own-migration)
- [<span data-ttu-id="51b1d-207">在 Microsoft 以就地升級方式部署 Windows 10</span><span class="sxs-lookup"><span data-stu-id="51b1d-207">Deploying Windows 10 at Microsoft as an in-place upgrade</span></span>](https://www.microsoft.com/itshowcase/Article/Content/668/Deploying-Windows-10-at-Microsoft-as-an-inplace-upgrade)
- <span data-ttu-id="51b1d-208">[Windows 10 部署：Microsoft IT 的秘訣與技巧](https://www.microsoft.com/itshowcase/Article/Content/951/Windows-10-deployment-tips-and-tricks-from-Microsoft-IT) (影片)</span><span class="sxs-lookup"><span data-stu-id="51b1d-208">[Windows 10 deployment: tips and tricks from Microsoft IT](https://www.microsoft.com/itshowcase/Article/Content/951/Windows-10-deployment-tips-and-tricks-from-Microsoft-IT) (video)</span></span>

## <a name="transition-your-entire-organization"></a><span data-ttu-id="51b1d-209">轉換您的整個組織</span><span class="sxs-lookup"><span data-stu-id="51b1d-209">Transition your entire organization</span></span>

<span data-ttu-id="51b1d-210">若要更全面地掌握如何將整個組織移至 Microsoft 365 企業版，請下載[轉換海報](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/deploy-microsoft-365-enterprise/transitionorgtom365.pdf)。</span><span class="sxs-lookup"><span data-stu-id="51b1d-210">To get a better picture of how to move your entire organization to Microsoft 365 Enterprise, download the [transition poster](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/deploy-microsoft-365-enterprise/transitionorgtom365.pdf).</span></span>

![](./media/deploy-microsoft-365-enterprise/TransitionOrgToM365.png)

<span data-ttu-id="51b1d-211">這份雙頁海報可讓您快速清查您現有的基礎結構，並取得移至 Microsoft 365 企業版中對應產品或服務的指導方針。</span><span class="sxs-lookup"><span data-stu-id="51b1d-211">This two-page poster is a quick way to inventory your existing infrastructure and get to the guidance for moving to the corresponding product or service in Microsoft 365 Enterprise.</span></span> <span data-ttu-id="51b1d-212">本文中包含產品和其他基礎結構與安全性元素，例如裝置管理、身分識別以及資訊和威脅防護。</span><span class="sxs-lookup"><span data-stu-id="51b1d-212">It includes the products in this article and other infrastructure and security elements such as device management, identity, and information and threat protection.</span></span>

<span data-ttu-id="51b1d-213">您可以以 Letter、Legal 或 Tabloid (11 x 17) 格式列印此海報。</span><span class="sxs-lookup"><span data-stu-id="51b1d-213">You can print this poster in letter, legal, or tabloid (11 x 17) formats.</span></span>

## <a name="result"></a><span data-ttu-id="51b1d-214">結果</span><span class="sxs-lookup"><span data-stu-id="51b1d-214">Result</span></span>

<span data-ttu-id="51b1d-215">貴組織已將舊版 Microsoft Office、Office 伺服器及 Windows 移轉為 Microsoft 365 企業版。</span><span class="sxs-lookup"><span data-stu-id="51b1d-215">Your organization has migrated older versions of Microsoft Office, Office servers, and Windows to Microsoft 365 Enterprise.</span></span>
