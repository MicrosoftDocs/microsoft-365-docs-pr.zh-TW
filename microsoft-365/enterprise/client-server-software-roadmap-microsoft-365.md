---
title: Microsoft 365 的用戶端與伺服器軟體藍圖
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/10/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-subscription-management
ms.custom: it-pro
description: 設定 Microsoft 365 用戶端和伺服器軟體的藍圖。
ms.openlocfilehash: d51aead9a50df3acace94526824cfa08fc083a01
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847151"
---
# <a name="client-and-server-software-roadmap-for-microsoft-365"></a><span data-ttu-id="23dcf-103">Microsoft 365 的用戶端與伺服器軟體藍圖</span><span class="sxs-lookup"><span data-stu-id="23dcf-103">Client and server software roadmap for Microsoft 365</span></span>

<span data-ttu-id="23dcf-104">大多數的企業組織都有異類環境，具有多種版本的作業系統、用戶端軟體和伺服器軟體。</span><span class="sxs-lookup"><span data-stu-id="23dcf-104">Most enterprise organizations have a heterogeneous environment with multiple releases of operating systems, client software, and server software.</span></span> <span data-ttu-id="23dcf-105">適用于企業的 Microsoft 365 為您的 IT 基礎結構提供這些重要元件的最安全版本，其生產力功能是用來充分利用雲端技術。</span><span class="sxs-lookup"><span data-stu-id="23dcf-105">Microsoft 365 for enterprise includes the most secure versions of these key components of your IT infrastructure with productivity features that are designed to take advantage of cloud technologies.</span></span>

<span data-ttu-id="23dcf-106">若要最大化 Microsoft 365 的企業整合套件的商業價值，請開始規劃及執行遷移版本的策略：</span><span class="sxs-lookup"><span data-stu-id="23dcf-106">To maximize the business value of the Microsoft 365 for enterprise integrated suite of products, begin planning and implementing a strategy to migrate releases of:</span></span>

- <span data-ttu-id="23dcf-107">將安裝在您電腦上的 Office 用戶端移轉為 Microsoft 365 Apps 企業版</span><span class="sxs-lookup"><span data-stu-id="23dcf-107">The Office client installed on your computers to Microsoft 365 Apps for enterprise</span></span>
- <span data-ttu-id="23dcf-108">在您的伺服器上安裝到其對等服務的 Office 伺服器（Microsoft 365）</span><span class="sxs-lookup"><span data-stu-id="23dcf-108">Office servers installed on your servers to their equivalent services in Microsoft 365</span></span>
- <span data-ttu-id="23dcf-109">將裝置上的 Windows 7 和 Windows 8.1 移轉為 Windows 10 企業版</span><span class="sxs-lookup"><span data-stu-id="23dcf-109">Windows 7 and Windows 8.1 on your devices to Windows 10 Enterprise</span></span>

>[!Note]
><span data-ttu-id="23dcf-110">Windows 7 已於 **2020 年 1 月 14 日** 終止支援。</span><span class="sxs-lookup"><span data-stu-id="23dcf-110">Windows 7 reached end of support on **January 14, 2020**.</span></span> <span data-ttu-id="23dcf-111">如需詳細資訊，請按一下[這裡](https://support.microsoft.com/help/4057281/windows-7-support-will-end-on-january-14-2020)。</span><span class="sxs-lookup"><span data-stu-id="23dcf-111">For more information, click [here](https://support.microsoft.com/help/4057281/windows-7-support-will-end-on-january-14-2020).</span></span>
>

<span data-ttu-id="23dcf-112">完成所有這些遷移一段時間之後，您的組織越接近 [現代的工作場所](https://www.microsoft.com/microsoft-365/blog/2018/04/27/making-it-simpler-with-a-modern-workplace/)，這是一種安全且整合的環境，可解除組織中的團隊合作和創造力，而且所有這些都是由 Microsoft 365 for enterprise 所支援及加強。</span><span class="sxs-lookup"><span data-stu-id="23dcf-112">Accomplishing all of these migrations over time gets your organization closer to the [modern workplace](https://www.microsoft.com/microsoft-365/blog/2018/04/27/making-it-simpler-with-a-modern-workplace/), a secure and integrated environment that unlocks teamwork and creativity in your organization, all of which is enabled and empowered by Microsoft 365 for enterprise.</span></span>

## <a name="migration-for-microsoft-office-client-products"></a><span data-ttu-id="23dcf-113">Microsoft Office 用戶端產品的移轉</span><span class="sxs-lookup"><span data-stu-id="23dcf-113">Migration for Microsoft Office client products</span></span>

<span data-ttu-id="23dcf-p103">在許多大型和小型組織中，您可能會使用較舊版本的 Office 用戶端產品組合，例如 Word、Excel 和 PowerPoint。這些較舊的版本：</span><span class="sxs-lookup"><span data-stu-id="23dcf-p103">In many organizations both large and small, you might be using a combination of older versions of the Office client products, such as Word, Excel, and PowerPoint. These older versions:</span></span>

- <span data-ttu-id="23dcf-116">可使用最新的安全性更新和支援修正進行[更新](https://support.office.com/article/install-office-updates-2ab296f3-7f03-43a2-8e50-46de917611c5)，但此程序有時需手動進行，且可能無法擴及整個組織。</span><span class="sxs-lookup"><span data-stu-id="23dcf-116">Can be [updated](https://support.office.com/article/install-office-updates-2ab296f3-7f03-43a2-8e50-46de917611c5) with the latest security updates and support fixes, but the process is sometimes manual and might not scale across your organization.</span></span>
- <span data-ttu-id="23dcf-117">未以最佳化方式啟用以便運用 Microsoft 雲端技術，及協助您的企業進行數位轉型。</span><span class="sxs-lookup"><span data-stu-id="23dcf-117">Are not optimally enabled to leverage Microsoft’s cloud technologies and help you digitally transform your business.</span></span>
- <span data-ttu-id="23dcf-118">不包含新功能。</span><span class="sxs-lookup"><span data-stu-id="23dcf-118">Do not contain new features.</span></span>

<span data-ttu-id="23dcf-119">適用于企業的 microsoft 365 包括適用于企業的 Microsoft 365 應用程式、Office 用戶端產品的版本，以及 microsoft 365 for enterprise license，已從 Microsoft 雲端安裝並更新。</span><span class="sxs-lookup"><span data-stu-id="23dcf-119">Microsoft 365 for enterprise includes Microsoft 365 Apps for enterprise, a version of the Office client products that is available with a Microsoft 365 for enterprise license and is installed and updated from the Microsoft cloud.</span></span> <span data-ttu-id="23dcf-120">Microsoft 365 Apps 企業版授權包括安全性更新和最新功能。</span><span class="sxs-lookup"><span data-stu-id="23dcf-120">Microsoft 365 Apps for enterprise includes security updates and the latest features.</span></span> <span data-ttu-id="23dcf-121">如需詳細資訊，請參閱[關於 Microsoft 365 應用程式企業版](https://docs.microsoft.com/deployoffice/about-microsoft-365-apps)。</span><span class="sxs-lookup"><span data-stu-id="23dcf-121">See [About Microsoft 365 Apps for enterprise](https://docs.microsoft.com/deployoffice/about-microsoft-365-apps) for more information.</span></span>

### <a name="office-2007"></a><span data-ttu-id="23dcf-122">Office 2007</span><span class="sxs-lookup"><span data-stu-id="23dcf-122">Office 2007</span></span>

<span data-ttu-id="23dcf-p105">針對 Office 2007 版的 Office 版本，已終止支援。如需詳細資訊，請參閱 [Office 2007 終止支援藍圖](https://docs.microsoft.com/deployoffice/office-2007-end-support-roadmap)。</span><span class="sxs-lookup"><span data-stu-id="23dcf-p105">For versions of Office in the Office 2007 release, the end of support has already passed. See [Office 2007 End of Support Roadmap](https://docs.microsoft.com/deployoffice/office-2007-end-support-roadmap) for more information.</span></span>

<span data-ttu-id="23dcf-125">若不使用 Office 2010、Office 2013 或 Office 2016 來升級您執行 Office 2007 的電腦，請考慮：</span><span class="sxs-lookup"><span data-stu-id="23dcf-125">Rather than upgrading your computers running Office 2007 with Office 2010, Office 2013, or Office 2016, consider:</span></span>

1. <span data-ttu-id="23dcf-126">為使用者取得並指派 Microsoft 365 授權。</span><span class="sxs-lookup"><span data-stu-id="23dcf-126">Obtaining and assigning a Microsoft 365 license for your users.</span></span>
2. <span data-ttu-id="23dcf-127">在使用者電腦中解除安裝 Office 2007。</span><span class="sxs-lookup"><span data-stu-id="23dcf-127">Uninstalling Office 2007 on their computers.</span></span>
3. <span data-ttu-id="23dcf-128">安裝 Microsoft 365 App 企業版 (個別安裝或搭配 IT 推出)。</span><span class="sxs-lookup"><span data-stu-id="23dcf-128">Installing Microsoft 365 Apps for enterprise, either individually or in conjunction with an IT rollout.</span></span> <span data-ttu-id="23dcf-129">如需詳細資訊，請參閱 [Microsoft 365 應用程式的部署指南](https://docs.microsoft.com/deployoffice/deployment-guide-microsoft-365-apps)。</span><span class="sxs-lookup"><span data-stu-id="23dcf-129">For more information, see [Deployment guide for Microsoft 365 Apps](https://docs.microsoft.com/deployoffice/deployment-guide-microsoft-365-apps).</span></span>

<span data-ttu-id="23dcf-130">Microsoft 365 App 企業版會自動安裝更新，可以充分利用以雲端為基礎的服務，以取得增強的安全性和生產力。</span><span class="sxs-lookup"><span data-stu-id="23dcf-130">Microsoft 365 Apps for enterprise installs updates automatically and can take advantage of cloud-based services for enhanced security and productivity.</span></span>

### <a name="office-2010"></a><span data-ttu-id="23dcf-131">Office 2010</span><span class="sxs-lookup"><span data-stu-id="23dcf-131">Office 2010</span></span>

<span data-ttu-id="23dcf-132">若為 Office 2010 版本中的 Office 版本，支援已于 **2020 年10月13日** 結束。</span><span class="sxs-lookup"><span data-stu-id="23dcf-132">For versions of Office in the Office 2010 release, support ended on **October 13, 2020**.</span></span> <span data-ttu-id="23dcf-133">如需詳細資訊，請參閱 [Office 2010 終止支援藍圖](https://docs.microsoft.com/deployoffice/office-2010-end-support-roadmap)。</span><span class="sxs-lookup"><span data-stu-id="23dcf-133">For more information, see [Office 2010 end of support roadmap](https://docs.microsoft.com/deployoffice/office-2010-end-support-roadmap).</span></span>

<span data-ttu-id="23dcf-134">若不使用 Office 2013 或 Office 2016 (這兩者都必須手動更新) 來升級您執行 Office 2010 的電腦，請考慮：</span><span class="sxs-lookup"><span data-stu-id="23dcf-134">Rather than upgrading your computers running Office 2010 with Office 2013 or Office 2016, both of which must be manually updated, consider:</span></span>

1. <span data-ttu-id="23dcf-135">為使用者取得並指派 Microsoft 365 授權。</span><span class="sxs-lookup"><span data-stu-id="23dcf-135">Obtaining and assigning a Microsoft 365 license for your users.</span></span>
2. <span data-ttu-id="23dcf-136">在使用者電腦中解除安裝 Office 2010。</span><span class="sxs-lookup"><span data-stu-id="23dcf-136">Uninstalling Office 2010 on their computers.</span></span>
3. <span data-ttu-id="23dcf-137">安裝 Microsoft 365 App 企業版 (個別安裝或搭配 IT 推出)。</span><span class="sxs-lookup"><span data-stu-id="23dcf-137">Installing Microsoft 365 Apps for enterprise, either individually or in conjunction with an IT rollout.</span></span> <span data-ttu-id="23dcf-138">如需詳細資訊，請參閱 [Microsoft 365 應用程式的部署指南](https://docs.microsoft.com/deployoffice/deployment-guide-microsoft-365-apps)。</span><span class="sxs-lookup"><span data-stu-id="23dcf-138">For more information, see [Deployment guide for Microsoft 365 Apps](https://docs.microsoft.com/deployoffice/deployment-guide-microsoft-365-apps).</span></span>

<span data-ttu-id="23dcf-139">Microsoft 365 App 企業版會自動安裝安全性和新功能更新，並可以充分利用 Microsoft 365 中以雲端為基礎的服務，以取得增強的安全性和生產力。</span><span class="sxs-lookup"><span data-stu-id="23dcf-139">Microsoft 365 Apps for enterprise installs both security and new feature updates automatically and can take advantage of cloud-based services in Microsoft 365 for enhanced security and productivity.</span></span>

### <a name="office-2013-and-office-2016"></a><span data-ttu-id="23dcf-140">Office 2013 和 Office 2016</span><span class="sxs-lookup"><span data-stu-id="23dcf-140">Office 2013 and Office 2016</span></span>

<span data-ttu-id="23dcf-141">Office 2013 和 Office 2016 版的終止支援藍圖尚未確定。</span><span class="sxs-lookup"><span data-stu-id="23dcf-141">The end of support roadmap for the Office 2013 and Office 2016 versions of Office has not yet been determined.</span></span> <span data-ttu-id="23dcf-142">不過，與 Office 2010 相同，您仍必須[安全性更新](https://support.office.com/article/install-office-updates-2ab296f3-7f03-43a2-8e50-46de917611c5)，而具體取決於組織的規模，可能無法妥善地擴充。</span><span class="sxs-lookup"><span data-stu-id="23dcf-142">However, like Office 2010, you must still [install security updates](https://support.office.com/article/install-office-updates-2ab296f3-7f03-43a2-8e50-46de917611c5), which might not scale well depending on the size of your organization.</span></span>

<span data-ttu-id="23dcf-143">若不想使用 Office 2013 或 Office 2016 的最新安全性更新持續更新您的電腦，或將您電腦從 Office 2013 更新至 Office 2016，請考慮：</span><span class="sxs-lookup"><span data-stu-id="23dcf-143">Rather than keep updating your computers with the latest security updates for Office 2013 or Office 2016 or update your computers from Office 2013 to Office 2016, consider:</span></span>

1. <span data-ttu-id="23dcf-144">為使用者取得並指派 Microsoft 365 授權。</span><span class="sxs-lookup"><span data-stu-id="23dcf-144">Obtaining and assigning a Microsoft 365 license for your users.</span></span>
2. <span data-ttu-id="23dcf-145">在使用者電腦中解除安裝 Office 2013 或 Office 2016。</span><span class="sxs-lookup"><span data-stu-id="23dcf-145">Uninstalling Office 2013 or Office 2016 on their computers.</span></span>
3. <span data-ttu-id="23dcf-146">安裝 Microsoft 365 App 企業版 (個別安裝或搭配 IT 推出)。</span><span class="sxs-lookup"><span data-stu-id="23dcf-146">Installing Microsoft 365 Apps for enterprise, either individually or in conjunction with an IT rollout.</span></span> <span data-ttu-id="23dcf-147">如需詳細資訊，請參閱 [Microsoft 365 應用程式的部署指南](https://docs.microsoft.com/deployoffice/deployment-guide-microsoft-365-apps)。</span><span class="sxs-lookup"><span data-stu-id="23dcf-147">For more information, see [Deployment guide for Microsoft 365 Apps](https://docs.microsoft.com/deployoffice/deployment-guide-microsoft-365-apps).</span></span>

<span data-ttu-id="23dcf-148">Microsoft 365 App 企業版會自動安裝安全性和新功能更新，並可以充分利用 Microsoft 365 中以雲端為基礎的服務，以取得增強的安全性和生產力。</span><span class="sxs-lookup"><span data-stu-id="23dcf-148">Microsoft 365 Apps for enterprise installs both security and new feature updates automatically and can take advantage of cloud-based services in Microsoft 365 for enhanced security and productivity.</span></span>

## <a name="migration-for-microsoft-office-server-products"></a><span data-ttu-id="23dcf-149">Microsoft Office 伺服器產品的移轉</span><span class="sxs-lookup"><span data-stu-id="23dcf-149">Migration for Microsoft Office server products</span></span>

<span data-ttu-id="23dcf-p111">在許多大型和小型組織中，您可能會使用較舊版本的 Office 伺服器產品組合，例如 Exchange Server 與 SharePoint Server。這些較舊的版本：</span><span class="sxs-lookup"><span data-stu-id="23dcf-p111">In many organizations both large and small, you might be using a combination of older versions of the Office Server products, such as Exchange Server and SharePoint Server. These older versions:</span></span>

- <span data-ttu-id="23dcf-p112">應使用最新的安全性更新和支援修正進行更新。在某些情況下，這些更新會每月發行。</span><span class="sxs-lookup"><span data-stu-id="23dcf-p112">Should be updated with the latest security updates and support fixes. In some cases, these updates are released monthly.</span></span>
- <span data-ttu-id="23dcf-154">未以最佳化方式啟用以便運用 Microsoft 雲端技術，及協助您的企業進行數位轉型。</span><span class="sxs-lookup"><span data-stu-id="23dcf-154">Are not optimally enabled to leverage Microsoft’s cloud technologies and help you digitally transform your business.</span></span>
- <span data-ttu-id="23dcf-155">不包含新的生產力應用程式，例如 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="23dcf-155">Do not include new productivity applications, such as Microsoft Teams.</span></span>
- <span data-ttu-id="23dcf-156">請勿包含最新的安全性功能，例如 Exchange 和 Defender for Office 365。</span><span class="sxs-lookup"><span data-stu-id="23dcf-156">Do not include the latest security features, such as Exchange and Defender for Office 365.</span></span>

<span data-ttu-id="23dcf-157">Microsoft 365 for enterprise 包含雲端架構版本的 Office server 服務，其使用一些與 Office server 軟體內部部署版本（如網頁瀏覽器和 Outlook 用戶端）相同的工具。</span><span class="sxs-lookup"><span data-stu-id="23dcf-157">Microsoft 365 for enterprise includes cloud-based versions of Office server services that use some of the same tools as on-premises versions of Office server software, such as web browsers and the Outlook client.</span></span> <span data-ttu-id="23dcf-158">這些服務會不斷進行安全性更新，而不需 IT 進行，進而為您節省了維護和更新內部部署伺服器所需的時間。</span><span class="sxs-lookup"><span data-stu-id="23dcf-158">These services are continually updated for security without involving IT, saving you the time it takes to maintain and update on-premises servers.</span></span> <span data-ttu-id="23dcf-159">這些服務也含有 Office 伺服器軟體中沒有的新功能增強功能。</span><span class="sxs-lookup"><span data-stu-id="23dcf-159">These services also have new features enhancements that are not present in Office server software.</span></span>

<span data-ttu-id="23dcf-160">如需針對特定 Microsoft 365 工作負載遷移使用者和資料的詳細資訊：</span><span class="sxs-lookup"><span data-stu-id="23dcf-160">For information about migrating users and data for specific Microsoft 365 workloads:</span></span>

- <span data-ttu-id="23dcf-161">使用者信箱從 Exchange Server 移至 Exchange Online，請參閱 [在內部部署和 Exchange Online 組織之間移動信箱](https://docs.microsoft.com/exchange/hybrid-deployment/move-mailboxes)。</span><span class="sxs-lookup"><span data-stu-id="23dcf-161">User mailboxes from Exchange Server to Exchange Online, see [Move mailboxes between on-premises and Exchange Online organizations](https://docs.microsoft.com/exchange/hybrid-deployment/move-mailboxes).</span></span>
- <span data-ttu-id="23dcf-162">SharePoint SharePoint 伺服器的資料，以 SharePoint 線上，請參閱將 [您的內容遷移至 Microsoft 365](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online)。</span><span class="sxs-lookup"><span data-stu-id="23dcf-162">SharePoint data from SharePoint Server to SharePoint Online, see [Migrate your content to Microsoft 365](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online).</span></span>
- <span data-ttu-id="23dcf-163">商務用 Skype Online 至 Microsoft 小組，請參閱 [遷移和互通性指南](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)。</span><span class="sxs-lookup"><span data-stu-id="23dcf-163">Skype for Business Online to Microsoft Teams, see [Migration and interoperability guidance](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span></span>

### <a name="office-server-2007"></a><span data-ttu-id="23dcf-164">Office Server 2007</span><span class="sxs-lookup"><span data-stu-id="23dcf-164">Office Server 2007</span></span>

<span data-ttu-id="23dcf-p114">對於 Office 2007 版的伺服器產品，已終止支援。請參閱下列文章取得詳細資料：</span><span class="sxs-lookup"><span data-stu-id="23dcf-p114">For server products in the Office 2007 release, the end of support has already passed. See these articles for the details:</span></span>

- [<span data-ttu-id="23dcf-167">Exchange 2007 終止支援藍圖</span><span class="sxs-lookup"><span data-stu-id="23dcf-167">Exchange 2007 end of support roadmap</span></span>](exchange-2007-end-of-support.md)
- [<span data-ttu-id="23dcf-168">SharePoint Server 2007 終止支援藍圖</span><span class="sxs-lookup"><span data-stu-id="23dcf-168">SharePoint Server 2007 end of support roadmap</span></span>](sharepoint-2007-end-of-support.md)
- [<span data-ttu-id="23dcf-169">Project Server 2007 終止支援藍圖</span><span class="sxs-lookup"><span data-stu-id="23dcf-169">Project Server 2007 end of support roadmap</span></span>](project-server-2007-end-of-support.md)
- [<span data-ttu-id="23dcf-170">Office Communications Server 終止支援藍圖</span><span class="sxs-lookup"><span data-stu-id="23dcf-170">Office Communications Server end of support roadmap</span></span>](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/upgrade)
- [<span data-ttu-id="23dcf-171">PerformancePoint Server 2007 終止支援藍圖</span><span class="sxs-lookup"><span data-stu-id="23dcf-171">PerformancePoint Server 2007 end of support roadmap</span></span>](pps-2007-end-of-support.md)

<span data-ttu-id="23dcf-172">若不使用 Office 2010、Office 2013 或 Office 2016 版的伺服器產品升級 Office 2007 版的伺服器產品，請考慮：</span><span class="sxs-lookup"><span data-stu-id="23dcf-172">Rather than upgrading your server products in the Office 2007 release with server products in the Office 2010, Office 2013, or Office 2016 releases, consider:</span></span>

1. <span data-ttu-id="23dcf-173">將您的 Office 2007 伺服器上的資料移轉至 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="23dcf-173">Migrating the data on your Office 2007 servers to Microsoft 365.</span></span> <span data-ttu-id="23dcf-174">若要協助此，請雇用 Microsoft 合作夥伴。</span><span class="sxs-lookup"><span data-stu-id="23dcf-174">To help with this, hire a Microsoft partner.</span></span>
2. <span data-ttu-id="23dcf-175">向使用者推出新功能和作業程序。</span><span class="sxs-lookup"><span data-stu-id="23dcf-175">Rolling out the new functionality and work processes to your users.</span></span>
3. <span data-ttu-id="23dcf-176">不再需要執行 Office 2007 伺服器產品的內部部署伺服器時，請予以解除。</span><span class="sxs-lookup"><span data-stu-id="23dcf-176">When there is no longer a need for the on-premises servers running Office 2007 server products, decommissioning them.</span></span>

### <a name="office-server-2010"></a><span data-ttu-id="23dcf-177">Office Server 2010</span><span class="sxs-lookup"><span data-stu-id="23dcf-177">Office Server 2010</span></span>

<span data-ttu-id="23dcf-178">[Exchange Server 2010](exchange-2010-end-of-support.md)的支援已于 **2020 年10月13日** 結束。</span><span class="sxs-lookup"><span data-stu-id="23dcf-178">Support for [Exchange Server 2010](exchange-2010-end-of-support.md) ended on **October 13, 2020**.</span></span>

<span data-ttu-id="23dcf-179">[SharePoint Server 2010](upgrade-from-sharepoint-2010.md) 的支援終止日期為 **2021 年 4 月 13 日** 。</span><span class="sxs-lookup"><span data-stu-id="23dcf-179">The end of support for [SharePoint Server 2010](upgrade-from-sharepoint-2010.md) is **April 13, 2021**.</span></span>

<span data-ttu-id="23dcf-180">若不使用 Office 2013 或 Office 2016 版的伺服器產品升級 Office 2010 版的這些伺服器產品，請考慮：</span><span class="sxs-lookup"><span data-stu-id="23dcf-180">Rather than upgrading these server products in the Office 2010 release with server products in the Office 2013 or Office 2016 release, consider:</span></span>

1. <span data-ttu-id="23dcf-181">將 Office 2010 伺服器上的資料移轉至 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="23dcf-181">Migrating the data on your Office 2010 servers to Microsoft 365.</span></span> <span data-ttu-id="23dcf-182">若需要協助，請參閱[適用於 Microsoft 365 的 FastTrack](https://fasttrack.microsoft.com/microsoft365) 或雇用 Microsoft 合作夥伴。</span><span class="sxs-lookup"><span data-stu-id="23dcf-182">To help with this, see [FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365) or hire a Microsoft partner.</span></span>
2. <span data-ttu-id="23dcf-183">向使用者推出新功能和作業程序。</span><span class="sxs-lookup"><span data-stu-id="23dcf-183">Rolling out the new functionality and work processes to your users.</span></span>
3. <span data-ttu-id="23dcf-184">不再需要執行 Office 2010 伺服器產品的內部部署伺服器時，請予以解除。</span><span class="sxs-lookup"><span data-stu-id="23dcf-184">When there is no longer a need for the on-premises servers running Office 2010 server products, decommissioning them.</span></span>

### <a name="office-server-2013"></a><span data-ttu-id="23dcf-185">Office Server 2013</span><span class="sxs-lookup"><span data-stu-id="23dcf-185">Office Server 2013</span></span>

<span data-ttu-id="23dcf-p117">對於 Office 2013 版的伺服器產品，尚未決定終止支援。若不使用 Office 2016 版的伺服器產品升級 Office 2013 版的伺服器產品，請考慮：</span><span class="sxs-lookup"><span data-stu-id="23dcf-p117">For server products in the Office 2013 release, the end of support has not been determined. Rather than upgrading your server products in the Office 2013 release with server products in the Office 2016 release, consider:</span></span>

1. <span data-ttu-id="23dcf-188">將您的 Office 2013 伺服器上的資料移轉至 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="23dcf-188">Migrating the data on your Office 2013 servers to Microsoft 365.</span></span> <span data-ttu-id="23dcf-189">若需要協助，請參閱[適用於 Microsoft 365 的 FastTrack](https://fasttrack.microsoft.com/microsoft365) 或雇用 Microsoft 合作夥伴。</span><span class="sxs-lookup"><span data-stu-id="23dcf-189">To help with this, see [FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365) or hire a Microsoft partner.</span></span>
2. <span data-ttu-id="23dcf-190">向使用者推出新功能和作業程序。</span><span class="sxs-lookup"><span data-stu-id="23dcf-190">Rolling out the new functionality and work processes to your users.</span></span>
3. <span data-ttu-id="23dcf-191">不再需要執行 Office 2013 伺服器產品的內部部署伺服器時，請予以解除。</span><span class="sxs-lookup"><span data-stu-id="23dcf-191">When there is no longer a need for the on-premises servers running Office 2013 server products, decommissioning them.</span></span>

### <a name="office-server-2016"></a><span data-ttu-id="23dcf-192">Office Server 2016</span><span class="sxs-lookup"><span data-stu-id="23dcf-192">Office Server 2016</span></span>

<span data-ttu-id="23dcf-p119">對於 Office 2016 版的伺服器產品，尚未決定終止支援。若要充分利用以雲端為基礎的服務和增強功能，以便貴公司進行數位轉型，請考慮：</span><span class="sxs-lookup"><span data-stu-id="23dcf-p119">For server products in the Office 2016 release, the end of support has not been determined. To take advantage of the cloud-based service and enhancements to digitally transform your business, consider:</span></span>

1. <span data-ttu-id="23dcf-195">將您的 Office 2016 伺服器上的資料移轉至 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="23dcf-195">Migrating the data on your Office 2016 servers to Microsoft 365.</span></span> <span data-ttu-id="23dcf-196">若需要協助，請參閱[適用於 Microsoft 365 的 FastTrack](https://fasttrack.microsoft.com/microsoft365) 或雇用 Microsoft 合作夥伴。</span><span class="sxs-lookup"><span data-stu-id="23dcf-196">To help with this, see [FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365) or hire a Microsoft partner.</span></span>
2. <span data-ttu-id="23dcf-197">向使用者推出新功能和作業程序。</span><span class="sxs-lookup"><span data-stu-id="23dcf-197">Rolling out the new functionality and work processes to your users.</span></span>
3. <span data-ttu-id="23dcf-198">不再需要執行 Office 2016 伺服器產品的內部部署伺服器時，請予以解除。</span><span class="sxs-lookup"><span data-stu-id="23dcf-198">When there is no longer a need for the on-premises servers running Office 2016 server products, decommissioning them.</span></span>

## <a name="migration-for-microsoft-windows-7-and-81"></a><span data-ttu-id="23dcf-199">Microsoft Windows 7 和 8.1 的移轉</span><span class="sxs-lookup"><span data-stu-id="23dcf-199">Migration for Microsoft Windows 7 and 8.1</span></span>

<span data-ttu-id="23dcf-200">Windows 7 已於 **2020 年 1 月 14 日** 終止支援。</span><span class="sxs-lookup"><span data-stu-id="23dcf-200">Windows 7 reached end of support on **January 14, 2020**.</span></span> <span data-ttu-id="23dcf-201">若要移轉執行 Windows 7 或 Windows 8.1 的裝置，您可以執行就地升級。</span><span class="sxs-lookup"><span data-stu-id="23dcf-201">To migrate your devices running Windows 7 or Windows 8.1, you can perform an in-place upgrade.</span></span>

<span data-ttu-id="23dcf-202">如需其他方法，請參閱 [Windows 10 部署案例](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios)。</span><span class="sxs-lookup"><span data-stu-id="23dcf-202">For additional methods, see [Windows 10 deployment scenarios](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios).</span></span> <span data-ttu-id="23dcf-203">您也可以自行[規劃 Windows 10 部署](https://aka.ms/planforwin10deployment)。</span><span class="sxs-lookup"><span data-stu-id="23dcf-203">You can also [plan for Windows 10 deployment](https://aka.ms/planforwin10deployment) on your own.</span></span>

## <a name="summary-of-options-for-office-2010-clients-and-servers-and-windows-7"></a><span data-ttu-id="23dcf-204">適用於 Office 2010 用戶端與伺服器和 Windows 7 的選項摘要</span><span class="sxs-lookup"><span data-stu-id="23dcf-204">Summary of options for Office 2010 clients and servers and Windows 7</span></span>

<span data-ttu-id="23dcf-205">如需適用於這些產品的升級、移轉和移至雲端選項的視覺摘要，請參閱[終止支援海報](../downloads/Office2010Windows7EndOfSupport.pdf)。</span><span class="sxs-lookup"><span data-stu-id="23dcf-205">For a visual summary of the upgrade, migrate, and move-to-the-cloud options for these products, see the [end of support poster](../downloads/Office2010Windows7EndOfSupport.pdf).</span></span>

<span data-ttu-id="23dcf-206">[![Office 2010 用戶端與伺服器和 Windows 7 終止支援海報的影像](../media/microsoft-365-overview/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)</span><span class="sxs-lookup"><span data-stu-id="23dcf-206">[![Image for the end of support for Office 2010 clients and servers and Windows 7 poster](../media/microsoft-365-overview/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)</span></span>

<span data-ttu-id="23dcf-207">這個單頁標牌是一種快速瞭解可讓 Office 2010 用戶端和伺服器產品和 Windows 7 達到支援的各種途徑，其優先的路徑和 Microsoft 365 for enterprise 中所產生的目的地支援會反白顯示。</span><span class="sxs-lookup"><span data-stu-id="23dcf-207">This one-page poster is a quick way to understand the various paths you can take to prevent Office 2010 client and server products and Windows 7 from reaching end of support, with preferred paths and resulting destination support in Microsoft 365 for enterprise highlighted.</span></span>

<span data-ttu-id="23dcf-208">您可以[下載此海報](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf)，並以 Letter、Legal 或 Tabloid (11 x 17) 格式列印此海報。</span><span class="sxs-lookup"><span data-stu-id="23dcf-208">You can [download this poster](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) and print it in letter, legal, or tabloid (11 x 17) formats.</span></span>

## <a name="transition-your-entire-organization"></a><span data-ttu-id="23dcf-209">轉換整個組織</span><span class="sxs-lookup"><span data-stu-id="23dcf-209">Transition your entire organization</span></span>

<span data-ttu-id="23dcf-210">若要深入瞭解如何將整個組織移至 Microsoft 365 for enterprise 中的產品和服務，請下載並查看 [轉換海報](https://download.microsoft.com/download/2/c/7/2c7bcc04-aae3-4604-9707-1ffff66b9851/transition-org-to-m365.pdf)。</span><span class="sxs-lookup"><span data-stu-id="23dcf-210">To get a better picture of how to move your entire organization to the products and services in Microsoft 365 for enterprise, download and view the [transition poster](https://download.microsoft.com/download/2/c/7/2c7bcc04-aae3-4604-9707-1ffff66b9851/transition-org-to-m365.pdf).</span></span>

<span data-ttu-id="23dcf-211">[![轉換至 Microsoft 365 海報的影像](../media/microsoft-365-overview/transition-org-to-m365.png)](https://download.microsoft.com/download/2/c/7/2c7bcc04-aae3-4604-9707-1ffff66b9851/transition-org-to-m365.pdf)</span><span class="sxs-lookup"><span data-stu-id="23dcf-211">[![Image for the Transition to Microsoft 365 poster](../media/microsoft-365-overview/transition-org-to-m365.png)](https://download.microsoft.com/download/2/c/7/2c7bcc04-aae3-4604-9707-1ffff66b9851/transition-org-to-m365.pdf)</span></span>

<span data-ttu-id="23dcf-212">這份雙頁海報可讓您快速清查您現有的基礎結構，並取得移至 Microsoft 365 企業版中對應產品或服務的指導方針。</span><span class="sxs-lookup"><span data-stu-id="23dcf-212">This two-page poster is a quick way to inventory your existing infrastructure and get to the guidance for moving to the corresponding product or service in Microsoft 365 for enterprise.</span></span> <span data-ttu-id="23dcf-213">包含 Windows 和 Office 產品和其他基礎結構與安全性元素，例如裝置管理、身分識別以及資訊和威脅防護。</span><span class="sxs-lookup"><span data-stu-id="23dcf-213">It includes Windows and Office products and other infrastructure and security elements such as device management, identity, and information and threat protection.</span></span>

## <a name="how-microsoft-does-microsoft-365-for-enterprise"></a><span data-ttu-id="23dcf-214">Microsoft 如何進行企業的 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="23dcf-214">How Microsoft does Microsoft 365 for enterprise</span></span>

<span data-ttu-id="23dcf-215">請參閱 Microsoft IT 專家如何使用下列資源將公司遷移至 Microsoft 365 for enterprise：</span><span class="sxs-lookup"><span data-stu-id="23dcf-215">See how IT experts at Microsoft migrated the company to Microsoft 365 for enterprise with these resources:</span></span>

- [<span data-ttu-id="23dcf-216">部署和更新適用于企業的 Microsoft 365 應用程式</span><span class="sxs-lookup"><span data-stu-id="23dcf-216">Deploying and updating Microsoft 365 Apps for enterprise</span></span>](https://www.microsoft.com/itshowcase/Article/Content/757/Deploying-and-updating-Microsoft-Office-365-ProPlus)
- [<span data-ttu-id="23dcf-217">Microsoft 會將 150000 個信箱移轉到 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="23dcf-217">Microsoft migrates 150,000 mailboxes to Exchange Online</span></span>](https://www.microsoft.com/itshowcase/Article/Content/577/Microsoft-migrates-150000-mailboxes-to-Exchange-Online)
- [<span data-ttu-id="23dcf-218">SharePoint 至雲端：深入了解 Microsoft 如何執行自己的移轉</span><span class="sxs-lookup"><span data-stu-id="23dcf-218">SharePoint to the cloud: Learn how Microsoft ran its own migration</span></span>](https://www.microsoft.com/itshowcase/Article/Content/691/SharePoint-to-the-cloud-Learn-how-Microsoft-ran-its-own-migration)
- [<span data-ttu-id="23dcf-219">在 Microsoft 以就地升級方式部署 Windows 10</span><span class="sxs-lookup"><span data-stu-id="23dcf-219">Deploying Windows 10 at Microsoft as an in-place upgrade</span></span>](https://www.microsoft.com/itshowcase/Article/Content/668/Deploying-Windows-10-at-Microsoft-as-an-inplace-upgrade)
- <span data-ttu-id="23dcf-220">[Windows 10 部署：Microsoft IT 的秘訣與技巧](https://www.microsoft.com/itshowcase/Article/Content/951/Windows-10-deployment-tips-and-tricks-from-Microsoft-IT) (影片)</span><span class="sxs-lookup"><span data-stu-id="23dcf-220">[Windows 10 deployment: tips and tricks from Microsoft IT](https://www.microsoft.com/itshowcase/Article/Content/951/Windows-10-deployment-tips-and-tricks-from-Microsoft-IT) (video)</span></span>
