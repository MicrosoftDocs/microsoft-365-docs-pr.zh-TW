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
description: 使用此藍圖設定 Microsoft 365 的用戶端和伺服器軟體。
ms.openlocfilehash: 2fb63f73ad49c68cbeb6c92497835c36f9faf737
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920439"
---
# <a name="client-and-server-software-roadmap-for-microsoft-365"></a><span data-ttu-id="3ab21-103">Microsoft 365 的用戶端與伺服器軟體藍圖</span><span class="sxs-lookup"><span data-stu-id="3ab21-103">Client and server software roadmap for Microsoft 365</span></span>

<span data-ttu-id="3ab21-104">大多數的企業組織都有異構環境，包括多個版本的作業系統、用戶端軟體和伺服器軟體。</span><span class="sxs-lookup"><span data-stu-id="3ab21-104">Most enterprise organizations have a heterogeneous environment that includes multiple releases of operating systems, client software, and server software.</span></span> <span data-ttu-id="3ab21-105">Microsoft 365 企業版包含您 IT 基礎結構最安全的主要元件版本。</span><span class="sxs-lookup"><span data-stu-id="3ab21-105">Microsoft 365 Enterprise includes the most secure versions of the key components of your IT infrastructure.</span></span> <span data-ttu-id="3ab21-106">此外，它也包含可讓您利用雲端技術的生產力功能。</span><span class="sxs-lookup"><span data-stu-id="3ab21-106">It also includes productivity features that are designed to take advantage of cloud technologies.</span></span>

<span data-ttu-id="3ab21-107">若要充分發揮 Microsoft 365 企業版產品整合套件的商務價值，請開始規劃並實作策略以移轉以下版本：</span><span class="sxs-lookup"><span data-stu-id="3ab21-107">To maximize the business value of the Microsoft 365 Enterprise integrated suite of products, begin planning and implementing a strategy to migrate releases of:</span></span>

- <span data-ttu-id="3ab21-108">您的電腦上安裝的 Office 用戶端至 Microsoft 365 應用程式 enterprise。</span><span class="sxs-lookup"><span data-stu-id="3ab21-108">The Office client installed on your computers to Microsoft 365 Apps for enterprise.</span></span>
- <span data-ttu-id="3ab21-109">在您的伺服器上安裝到其對等服務的 Office 伺服器至 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="3ab21-109">The Office servers installed on your servers to their equivalent services in Microsoft 365.</span></span>
- <span data-ttu-id="3ab21-110">裝置上的 windows 7 和 Windows 8.1 至 Windows 10 企業版。</span><span class="sxs-lookup"><span data-stu-id="3ab21-110">Windows 7 and Windows 8.1 on your devices to Windows 10 Enterprise.</span></span>

>[!Note]
><span data-ttu-id="3ab21-111">Windows 7 的支援已于 *2020 年1月14日* 結束。</span><span class="sxs-lookup"><span data-stu-id="3ab21-111">Support for Windows 7 ended on *January 14, 2020*.</span></span> <span data-ttu-id="3ab21-112">如需詳細資訊，請參閱 [支援終止的詳細資料](https://support.microsoft.com/help/4057281/windows-7-support-will-end-on-january-14-2020)。</span><span class="sxs-lookup"><span data-stu-id="3ab21-112">For more information, see the [end-of-support details](https://support.microsoft.com/help/4057281/windows-7-support-will-end-on-january-14-2020).</span></span>
>

<span data-ttu-id="3ab21-113">當您隨時間完成這些遷移時，您的組織會更接近 [現代辦公環境](https://www.microsoft.com/microsoft-365/blog/2018/04/27/making-it-simpler-with-a-modern-workplace/)的願景。</span><span class="sxs-lookup"><span data-stu-id="3ab21-113">As you accomplish these migrations over time, your organization comes closer to the vision of the [modern workplace](https://www.microsoft.com/microsoft-365/blog/2018/04/27/making-it-simpler-with-a-modern-workplace/).</span></span> <span data-ttu-id="3ab21-114">這種安全且整合的環境可協助您解除組織中的團隊合作和創造力。</span><span class="sxs-lookup"><span data-stu-id="3ab21-114">This secure and integrated environment can help you unlock teamwork and creativity in your organization.</span></span> <span data-ttu-id="3ab21-115">Microsoft 365 企業版可讓您在所有的方式中，同時提供您。</span><span class="sxs-lookup"><span data-stu-id="3ab21-115">Microsoft 365 Enterprise enables and empowers you all along the way.</span></span>

## <a name="migration-for-office-client-products"></a><span data-ttu-id="3ab21-116">Office 用戶端產品的遷移</span><span class="sxs-lookup"><span data-stu-id="3ab21-116">Migration for Office client products</span></span>

<span data-ttu-id="3ab21-117">大型和小型組織通常會使用舊版 Office 用戶端產品的組合，例如 Word、Excel 及 PowerPoint。</span><span class="sxs-lookup"><span data-stu-id="3ab21-117">Organizations both large and small often use a combination of older versions of Office client products, such as Word, Excel, and PowerPoint.</span></span> <span data-ttu-id="3ab21-118">這些舊版本：</span><span class="sxs-lookup"><span data-stu-id="3ab21-118">These older versions:</span></span>

- <span data-ttu-id="3ab21-119">可使用最新的安全性更新和支援修復程式進行 [更新](https://support.office.com/article/install-office-updates-2ab296f3-7f03-43a2-8e50-46de917611c5) 。</span><span class="sxs-lookup"><span data-stu-id="3ab21-119">Can be [updated](https://support.office.com/article/install-office-updates-2ab296f3-7f03-43a2-8e50-46de917611c5) with the latest security updates and support fixes.</span></span> <span data-ttu-id="3ab21-120">不過，此程式有時是手動進行，而且可能無法在您的整個組織中擴充。</span><span class="sxs-lookup"><span data-stu-id="3ab21-120">But the process is sometimes manual and might not scale across your organization.</span></span>
- <span data-ttu-id="3ab21-121">不會優化使用 Microsoft 雲端技術，協助您以數位方式轉換您的業務。</span><span class="sxs-lookup"><span data-stu-id="3ab21-121">Aren't optimized to use the Microsoft cloud technologies that help you digitally transform your business.</span></span>
- <span data-ttu-id="3ab21-122">不提供最新功能。</span><span class="sxs-lookup"><span data-stu-id="3ab21-122">Don't provide the latest features.</span></span>

<span data-ttu-id="3ab21-123">Microsoft 365 企業版包含適用于企業的 Microsoft 365 應用程式。</span><span class="sxs-lookup"><span data-stu-id="3ab21-123">Microsoft 365 Enterprise includes Microsoft 365 Apps for enterprise.</span></span> <span data-ttu-id="3ab21-124">此版本的 Office 用戶端產品可搭配 Microsoft 365 企業版授權使用。</span><span class="sxs-lookup"><span data-stu-id="3ab21-124">This version of the Office client products is available with a Microsoft 365 Enterprise license.</span></span> <span data-ttu-id="3ab21-125">它已從 Microsoft 雲端安裝並更新。</span><span class="sxs-lookup"><span data-stu-id="3ab21-125">It's installed and updated from the Microsoft cloud.</span></span> <span data-ttu-id="3ab21-126">Microsoft 365 Apps 企業版授權包括安全性更新和最新功能。</span><span class="sxs-lookup"><span data-stu-id="3ab21-126">Microsoft 365 Apps for enterprise includes security updates and the latest features.</span></span> <span data-ttu-id="3ab21-127">如需詳細資訊，請參閱 [關於適用于企業的 Microsoft 365 應用程式](https://docs.microsoft.com/deployoffice/about-microsoft-365-apps)。</span><span class="sxs-lookup"><span data-stu-id="3ab21-127">For more information, see [About Microsoft 365 Apps for enterprise](https://docs.microsoft.com/deployoffice/about-microsoft-365-apps).</span></span>

### <a name="office-2007"></a><span data-ttu-id="3ab21-128">Office 2007</span><span class="sxs-lookup"><span data-stu-id="3ab21-128">Office 2007</span></span>

<span data-ttu-id="3ab21-129">若為 office 2007 版本中的 Office 版本，支援的終止已過去。</span><span class="sxs-lookup"><span data-stu-id="3ab21-129">For versions of Office in the Office 2007 release, the end of support has already passed.</span></span> <span data-ttu-id="3ab21-130">如需詳細資訊，請參閱 [Office 2007 終止支援藍圖](https://docs.microsoft.com/deployoffice/office-2007-end-support-roadmap)。</span><span class="sxs-lookup"><span data-stu-id="3ab21-130">For more information, see [Office 2007 end-of-support roadmap](https://docs.microsoft.com/deployoffice/office-2007-end-support-roadmap).</span></span>

<span data-ttu-id="3ab21-131">請考慮採取下列步驟，而不是將執行 Office 2007 的電腦升級至 Office 2010、Office 2013 或 Office 2016：</span><span class="sxs-lookup"><span data-stu-id="3ab21-131">Rather than upgrading your computers that run Office 2007 to Office 2010, Office 2013, or Office 2016, consider taking the following steps:</span></span>

1. <span data-ttu-id="3ab21-132">為您的使用者取得並指派 Microsoft 365 授權。</span><span class="sxs-lookup"><span data-stu-id="3ab21-132">Get and assign a Microsoft 365 license for your users.</span></span>
2. <span data-ttu-id="3ab21-133">在其電腦上卸載 Office 2007。</span><span class="sxs-lookup"><span data-stu-id="3ab21-133">Uninstall Office 2007 on their computers.</span></span>
3. <span data-ttu-id="3ab21-134">安裝 Microsoft 365 應用程式 for enterprise （不論是個別安裝或進行 IT 推廣）。</span><span class="sxs-lookup"><span data-stu-id="3ab21-134">Install Microsoft 365 Apps for enterprise, either individually or during an IT rollout.</span></span> <span data-ttu-id="3ab21-135">如需詳細資訊，請參閱 [Microsoft 365 應用程式的部署指南](https://docs.microsoft.com/deployoffice/deployment-guide-microsoft-365-apps)。</span><span class="sxs-lookup"><span data-stu-id="3ab21-135">For more information, see [Deployment guide for Microsoft 365 Apps](https://docs.microsoft.com/deployoffice/deployment-guide-microsoft-365-apps).</span></span>

<span data-ttu-id="3ab21-136">適用于企業的 Microsoft 365 應用程式會自動安裝更新。</span><span class="sxs-lookup"><span data-stu-id="3ab21-136">Microsoft 365 Apps for enterprise installs updates automatically.</span></span> <span data-ttu-id="3ab21-137">它可利用雲端架構服務，以增強安全性和生產力。</span><span class="sxs-lookup"><span data-stu-id="3ab21-137">It can take advantage of cloud-based services for enhanced security and productivity.</span></span>

### <a name="office-2010"></a><span data-ttu-id="3ab21-138">Office 2010</span><span class="sxs-lookup"><span data-stu-id="3ab21-138">Office 2010</span></span>

<span data-ttu-id="3ab21-139">若為 Office 2010 版本中的 Office 版本，支援已于 *2020 年10月13日* 結束。</span><span class="sxs-lookup"><span data-stu-id="3ab21-139">For versions of Office in the Office 2010 release, support ended on *October 13, 2020*.</span></span> <span data-ttu-id="3ab21-140">如需詳細資訊，請參閱 [Office 2010 終止支援藍圖](https://docs.microsoft.com/deployoffice/office-2010-end-support-roadmap)。</span><span class="sxs-lookup"><span data-stu-id="3ab21-140">For more information, see [Office 2010 end-of-support roadmap](https://docs.microsoft.com/deployoffice/office-2010-end-support-roadmap).</span></span>

<span data-ttu-id="3ab21-141">您可以考慮將執行 Office 2010 的電腦升級至 Office 2013 或 Office 2016。</span><span class="sxs-lookup"><span data-stu-id="3ab21-141">You might consider upgrading your computers that run Office 2010 to Office 2013 or Office 2016.</span></span> <span data-ttu-id="3ab21-142">不過，這兩個版本都必須手動更新。</span><span class="sxs-lookup"><span data-stu-id="3ab21-142">However, both of those versions must be manually updated.</span></span> <span data-ttu-id="3ab21-143">所以請改為採取下列步驟：</span><span class="sxs-lookup"><span data-stu-id="3ab21-143">So consider taking the following steps instead:</span></span>

1. <span data-ttu-id="3ab21-144">為您的使用者取得並指派 Microsoft 365 授權。</span><span class="sxs-lookup"><span data-stu-id="3ab21-144">Get and assign a Microsoft 365 license for your users.</span></span>
2. <span data-ttu-id="3ab21-145">在其電腦上卸載 Office 2010。</span><span class="sxs-lookup"><span data-stu-id="3ab21-145">Uninstall Office 2010 on their computers.</span></span>
3. <span data-ttu-id="3ab21-146">安裝 Microsoft 365 應用程式 for enterprise （不論是個別安裝或進行 IT 推廣）。</span><span class="sxs-lookup"><span data-stu-id="3ab21-146">Install Microsoft 365 Apps for enterprise, either individually or during an IT rollout.</span></span> <span data-ttu-id="3ab21-147">如需詳細資訊，請參閱 [Microsoft 365 應用程式的部署指南](https://docs.microsoft.com/deployoffice/deployment-guide-microsoft-365-apps)。</span><span class="sxs-lookup"><span data-stu-id="3ab21-147">For more information, see [Deployment guide for Microsoft 365 Apps](https://docs.microsoft.com/deployoffice/deployment-guide-microsoft-365-apps).</span></span>

<span data-ttu-id="3ab21-148">適用于企業的 Microsoft 365 應用程式會自動同時安裝安全性更新和新功能更新。</span><span class="sxs-lookup"><span data-stu-id="3ab21-148">Microsoft 365 Apps for enterprise automatically installs both security updates and new feature updates.</span></span> <span data-ttu-id="3ab21-149">它可以利用 Microsoft 365 中的雲端式服務，以獲得增強的安全性和生產力。</span><span class="sxs-lookup"><span data-stu-id="3ab21-149">It can take advantage of cloud-based services in Microsoft 365 for enhanced security and productivity.</span></span>

### <a name="office-2013-and-office-2016"></a><span data-ttu-id="3ab21-150">Office 2013 和 Office 2016</span><span class="sxs-lookup"><span data-stu-id="3ab21-150">Office 2013 and Office 2016</span></span>

<span data-ttu-id="3ab21-151">Office 2013 和 Office 2016 的支援終止藍圖尚未決定。</span><span class="sxs-lookup"><span data-stu-id="3ab21-151">The end-of-support roadmap for Office 2013 and Office 2016 hasn't yet been determined.</span></span> <span data-ttu-id="3ab21-152">在這些版本（如 Office 2010）中，您仍然必須 [安裝安全性更新](https://support.office.com/article/install-office-updates-2ab296f3-7f03-43a2-8e50-46de917611c5)。</span><span class="sxs-lookup"><span data-stu-id="3ab21-152">In these versions, like Office 2010, you must still [install security updates](https://support.office.com/article/install-office-updates-2ab296f3-7f03-43a2-8e50-46de917611c5).</span></span> <span data-ttu-id="3ab21-153">這項工作可能無法正常縮放，視組織的規模而定。</span><span class="sxs-lookup"><span data-stu-id="3ab21-153">This task might not scale well, depending on the size of your organization.</span></span>

<span data-ttu-id="3ab21-154">請不要使用 Office 2013 或 Office 2016 的最新安全性更新，或是將電腦從 Office 2013 更新為 Office 2016，而讓電腦保持最新的狀態，請考慮採取下列步驟：</span><span class="sxs-lookup"><span data-stu-id="3ab21-154">Rather than keeping your computers current with the latest security updates for Office 2013 or Office 2016, or updating your computers from Office 2013 to Office 2016, consider taking the following steps:</span></span>

1. <span data-ttu-id="3ab21-155">為您的使用者取得並指派 Microsoft 365 授權。</span><span class="sxs-lookup"><span data-stu-id="3ab21-155">Get and assign a Microsoft 365 license for your users.</span></span>
2. <span data-ttu-id="3ab21-156">卸載其電腦上的 Office 2013 或 Office 2016。</span><span class="sxs-lookup"><span data-stu-id="3ab21-156">Uninstall Office 2013 or Office 2016 on their computers.</span></span>
3. <span data-ttu-id="3ab21-157">安裝 Microsoft 365 應用程式 for enterprise （不論是個別安裝或進行 IT 推廣）。</span><span class="sxs-lookup"><span data-stu-id="3ab21-157">Install Microsoft 365 Apps for enterprise, either individually or during an IT rollout.</span></span> <span data-ttu-id="3ab21-158">如需詳細資訊，請參閱 [Microsoft 365 應用程式的部署指南](https://docs.microsoft.com/deployoffice/deployment-guide-microsoft-365-apps)。</span><span class="sxs-lookup"><span data-stu-id="3ab21-158">For more information, see [Deployment guide for Microsoft 365 Apps](https://docs.microsoft.com/deployoffice/deployment-guide-microsoft-365-apps).</span></span>

<span data-ttu-id="3ab21-159">Microsoft 365 應用程式 enterprise 會自動安裝安全性更新和新功能更新。</span><span class="sxs-lookup"><span data-stu-id="3ab21-159">Microsoft 365 Apps for enterprise installs both security updates and new feature updates automatically.</span></span> <span data-ttu-id="3ab21-160">它可以利用 Microsoft 365 中的雲端式服務，以獲得增強的安全性和生產力。</span><span class="sxs-lookup"><span data-stu-id="3ab21-160">It can take advantage of cloud-based services in Microsoft 365 for enhanced security and productivity.</span></span>

## <a name="migration-for-office-server-products"></a><span data-ttu-id="3ab21-161">Office server 產品遷移</span><span class="sxs-lookup"><span data-stu-id="3ab21-161">Migration for Office server products</span></span>

<span data-ttu-id="3ab21-162">大型及小型組織通常會使用舊版 Office server 產品的組合，例如 Exchange Server 和 SharePoint Server。</span><span class="sxs-lookup"><span data-stu-id="3ab21-162">Both large and small organizations often use a combination of older versions of the Office server products, such as Exchange Server and SharePoint Server.</span></span> <span data-ttu-id="3ab21-163">這些舊版本：</span><span class="sxs-lookup"><span data-stu-id="3ab21-163">These older versions:</span></span>

- <span data-ttu-id="3ab21-164">應該更新，以獲得最新的安全性更新和支援修正程式。</span><span class="sxs-lookup"><span data-stu-id="3ab21-164">Should be updated with the latest security updates and support fixes.</span></span> <span data-ttu-id="3ab21-165">在某些情況下，這些更新會每月發行。</span><span class="sxs-lookup"><span data-stu-id="3ab21-165">In some cases, these updates are released monthly.</span></span>
- <span data-ttu-id="3ab21-166">不會優化使用 Microsoft 雲端技術，協助您以數位方式轉換您的業務。</span><span class="sxs-lookup"><span data-stu-id="3ab21-166">Aren't optimized to use the Microsoft cloud technologies that help you digitally transform your business.</span></span>
- <span data-ttu-id="3ab21-167">不要包含新的生產力應用程式，例如 Microsoft 團隊。</span><span class="sxs-lookup"><span data-stu-id="3ab21-167">Don't include new productivity applications, such as Microsoft Teams.</span></span>
- <span data-ttu-id="3ab21-168">不要包含最新的安全性功能，例如 Exchange 和 Defender for Office 365。</span><span class="sxs-lookup"><span data-stu-id="3ab21-168">Don't include the latest security features, such as Exchange and Defender for Office 365.</span></span>

<span data-ttu-id="3ab21-169">Microsoft 365 Enterprise 包含雲端架構版本的 Office server 服務，其使用一些與 Office server 軟體內部部署版本（如網頁瀏覽器和 Outlook 用戶端）相同的工具。</span><span class="sxs-lookup"><span data-stu-id="3ab21-169">Microsoft 365 Enterprise includes cloud-based versions of Office server services that use some of the same tools as on-premises versions of Office server software, such as web browsers and the Outlook client.</span></span> <span data-ttu-id="3ab21-170">這些服務會自動更新以取得安全性。</span><span class="sxs-lookup"><span data-stu-id="3ab21-170">These services are automatically updated for security.</span></span> <span data-ttu-id="3ab21-171">所以，您的 IT 人員可節省維護和更新內部部署伺服器所需的時間。</span><span class="sxs-lookup"><span data-stu-id="3ab21-171">So your IT personnel save the time it takes to maintain and update on-premises servers.</span></span> <span data-ttu-id="3ab21-172">這些服務也提供 Office server 軟體中不存在的新功能增強功能。</span><span class="sxs-lookup"><span data-stu-id="3ab21-172">These services also offer new feature enhancements that aren't present in Office server software.</span></span>

<span data-ttu-id="3ab21-173">請使用下列資源，以取得針對特定 Microsoft 365 工作負載的使用者和資料進行遷移的相關資訊：</span><span class="sxs-lookup"><span data-stu-id="3ab21-173">Use the following resources for information about migrating users and data for specific Microsoft 365 workloads:</span></span>

- [<span data-ttu-id="3ab21-174">將信箱從內部部署 Exchange Server 移至 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="3ab21-174">Move mailboxes from on-premises Exchange Server to Exchange Online</span></span>](https://docs.microsoft.com/exchange/hybrid-deployment/move-mailboxes)
- [<span data-ttu-id="3ab21-175">將 SharePoint 資料從 SharePoint 伺服器遷移至 SharePoint 線上</span><span class="sxs-lookup"><span data-stu-id="3ab21-175">Migrate SharePoint data from SharePoint Server to SharePoint Online</span></span>](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online)
- [<span data-ttu-id="3ab21-176">將商務用 Skype Online 遷移至 Microsoft 團隊</span><span class="sxs-lookup"><span data-stu-id="3ab21-176">Migrate Skype for Business Online to Microsoft Teams</span></span>](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)

### <a name="office-2007-server-products"></a><span data-ttu-id="3ab21-177">Office 2007 伺服器產品</span><span class="sxs-lookup"><span data-stu-id="3ab21-177">Office 2007 server products</span></span>

<span data-ttu-id="3ab21-178">針對 Office 2007 版本中的伺服器產品，支援終止已過。</span><span class="sxs-lookup"><span data-stu-id="3ab21-178">For server products in the Office 2007 release, the end of support has already passed.</span></span> <span data-ttu-id="3ab21-179">如需詳細資訊，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="3ab21-179">See these articles for details:</span></span>

- [<span data-ttu-id="3ab21-180">Exchange 2007 終止支援藍圖</span><span class="sxs-lookup"><span data-stu-id="3ab21-180">Exchange 2007 end-of-support roadmap</span></span>](exchange-2007-end-of-support.md)
- [<span data-ttu-id="3ab21-181">SharePoint Server 2007 終止支援藍圖</span><span class="sxs-lookup"><span data-stu-id="3ab21-181">SharePoint Server 2007 end-of-support roadmap</span></span>](sharepoint-2007-end-of-support.md)
- [<span data-ttu-id="3ab21-182">Project Server 2007 終止支援藍圖</span><span class="sxs-lookup"><span data-stu-id="3ab21-182">Project Server 2007 end-of-support roadmap</span></span>](project-server-2007-end-of-support.md)
- [<span data-ttu-id="3ab21-183">Office 通訊伺服器支援終止藍圖</span><span class="sxs-lookup"><span data-stu-id="3ab21-183">Office Communications Server end-of-support roadmap</span></span>](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/upgrade)
- [<span data-ttu-id="3ab21-184">PerformancePoint Server 2007 終止支援藍圖</span><span class="sxs-lookup"><span data-stu-id="3ab21-184">PerformancePoint Server 2007 end-of-support roadmap</span></span>](pps-2007-end-of-support.md)

<span data-ttu-id="3ab21-185">請考慮採取下列步驟，而不是使用 office 2010、Office 2013 或 2016 Office 的版本中的伺服器產品來升級 Office 2007 版本中的伺服器產品：</span><span class="sxs-lookup"><span data-stu-id="3ab21-185">Rather than upgrading your server products in the Office 2007 release with server products in the releases for Office 2010, Office 2013, or Office 2016, consider taking the following steps:</span></span>

1. <span data-ttu-id="3ab21-186">將您的 Office 2007 伺服器上的資料移轉至 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="3ab21-186">Migrate the data on your Office 2007 servers to Microsoft 365.</span></span> <span data-ttu-id="3ab21-187">如需詳細資訊或協助，請雇用 Microsoft 合作夥伴。</span><span class="sxs-lookup"><span data-stu-id="3ab21-187">For more information or help, hire a Microsoft partner.</span></span>
2. <span data-ttu-id="3ab21-188">將新的功能和工作流程推廣給您的使用者。</span><span class="sxs-lookup"><span data-stu-id="3ab21-188">Roll out the new functionality and work processes to your users.</span></span>
3. <span data-ttu-id="3ab21-189">當您不再需要執行 Office 2007 伺服器產品的內部部署伺服器時，請解除其授權。</span><span class="sxs-lookup"><span data-stu-id="3ab21-189">When you no longer need the on-premises servers running Office 2007 server products, decommission them.</span></span>

### <a name="office-2010-server-products"></a><span data-ttu-id="3ab21-190">Office 2010 伺服器產品</span><span class="sxs-lookup"><span data-stu-id="3ab21-190">Office 2010 server products</span></span>

<span data-ttu-id="3ab21-191">[Exchange Server 2010](exchange-2010-end-of-support.md)的支援已于 *2020 年10月13日* 結束。</span><span class="sxs-lookup"><span data-stu-id="3ab21-191">Support for [Exchange Server 2010](exchange-2010-end-of-support.md) ended on *October 13, 2020*.</span></span>

<span data-ttu-id="3ab21-192">[SharePoint Server 2010](upgrade-from-sharepoint-2010.md) 的支援終止日期為 *2021 年 4 月 13 日* 。</span><span class="sxs-lookup"><span data-stu-id="3ab21-192">The end of support for [SharePoint Server 2010](upgrade-from-sharepoint-2010.md) is *April 13, 2021*.</span></span>

<span data-ttu-id="3ab21-193">請考慮採取下列步驟，而不是使用 office 2013 或 Office 2016 的發行版本中的伺服器產品升級這些伺服器2010產品：</span><span class="sxs-lookup"><span data-stu-id="3ab21-193">Rather than upgrading these server products in the Office 2010 release with server products in the releases for Office 2013 or Office 2016, consider taking the following steps:</span></span>

1. <span data-ttu-id="3ab21-194">將您的 Office 2010 伺服器上的資料移轉至 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="3ab21-194">Migrate the data on your Office 2010 servers to Microsoft 365.</span></span> <span data-ttu-id="3ab21-195">如需詳細資訊，請參閱 [FastTrack For microsoft 365](https://fasttrack.microsoft.com/microsoft365) 或雇用 microsoft partner。</span><span class="sxs-lookup"><span data-stu-id="3ab21-195">For more information, see [FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365) or hire a Microsoft partner.</span></span>
2. <span data-ttu-id="3ab21-196">將新的功能和工作流程推廣給您的使用者。</span><span class="sxs-lookup"><span data-stu-id="3ab21-196">Roll out the new functionality and work processes to your users.</span></span>
3. <span data-ttu-id="3ab21-197">當您不再需要執行 Office 2010 伺服器產品的內部部署伺服器時，請解除其授權。</span><span class="sxs-lookup"><span data-stu-id="3ab21-197">When you no longer need the on-premises servers running Office 2010 server products, decommission them.</span></span>

### <a name="office-2013-server-products"></a><span data-ttu-id="3ab21-198">Office 2013 伺服器產品</span><span class="sxs-lookup"><span data-stu-id="3ab21-198">Office 2013 server products</span></span>

<span data-ttu-id="3ab21-199">針對 Office 2013 版本中的伺服器產品，尚未決定支援的終止。</span><span class="sxs-lookup"><span data-stu-id="3ab21-199">For server products in the Office 2013 release, the end of support hasn't been determined.</span></span> <span data-ttu-id="3ab21-200">請考慮採取下列步驟，而不是使用 Office 2016 版本中的伺服器產品升級 Office 2013 版本中的伺服器產品：</span><span class="sxs-lookup"><span data-stu-id="3ab21-200">Rather than upgrading your server products in the Office 2013 release with server products in the Office 2016 release, consider taking the following steps:</span></span>

1. <span data-ttu-id="3ab21-201">將您的 Office 2013 伺服器上的資料移轉至 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="3ab21-201">Migrate the data on your Office 2013 servers to Microsoft 365.</span></span> <span data-ttu-id="3ab21-202">如需詳細資訊，請參閱 [FastTrack For microsoft 365](https://fasttrack.microsoft.com/microsoft365) 或雇用 microsoft partner。</span><span class="sxs-lookup"><span data-stu-id="3ab21-202">For more information, see [FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365) or hire a Microsoft partner.</span></span>
2. <span data-ttu-id="3ab21-203">將新的功能和工作流程推廣給您的使用者。</span><span class="sxs-lookup"><span data-stu-id="3ab21-203">Roll out the new functionality and work processes to your users.</span></span>
3. <span data-ttu-id="3ab21-204">當您不再需要執行 Office 2013 伺服器產品的內部部署伺服器時，請解除其授權。</span><span class="sxs-lookup"><span data-stu-id="3ab21-204">When you no longer need the on-premises servers running Office 2013 server products, decommission them.</span></span>

### <a name="office-2016-server-products"></a><span data-ttu-id="3ab21-205">Office 2016 伺服器產品</span><span class="sxs-lookup"><span data-stu-id="3ab21-205">Office 2016 server products</span></span>

<span data-ttu-id="3ab21-206">針對 Office 2016 版本中的伺服器產品，尚未決定支援的終止。</span><span class="sxs-lookup"><span data-stu-id="3ab21-206">For server products in the Office 2016 release, the end of support hasn't been determined.</span></span> <span data-ttu-id="3ab21-207">若要利用雲端架構服務和增強功能以數位方式轉換您的企業，請考慮採取下列步驟：</span><span class="sxs-lookup"><span data-stu-id="3ab21-207">To take advantage of cloud-based service and enhancements to digitally transform your business, consider taking the following steps:</span></span>

1. <span data-ttu-id="3ab21-208">將您的 Office 2016 伺服器上的資料移轉至 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="3ab21-208">Migrate the data on your Office 2016 servers to Microsoft 365.</span></span> <span data-ttu-id="3ab21-209">如需詳細資訊，請參閱 [FastTrack For microsoft 365](https://fasttrack.microsoft.com/microsoft365) 或雇用 microsoft partner。</span><span class="sxs-lookup"><span data-stu-id="3ab21-209">For more information, see [FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365) or hire a Microsoft partner.</span></span>
2. <span data-ttu-id="3ab21-210">將新的功能和工作流程推廣給您的使用者。</span><span class="sxs-lookup"><span data-stu-id="3ab21-210">Roll out the new functionality and work processes to your users.</span></span>
3. <span data-ttu-id="3ab21-211">當您不再需要執行 Office 2016 伺服器產品的內部部署伺服器時，請解除其授權。</span><span class="sxs-lookup"><span data-stu-id="3ab21-211">When you no longer need the on-premises servers running Office 2016 server products, decommission them.</span></span>

## <a name="migration-for-windows-7-and-81"></a><span data-ttu-id="3ab21-212">Windows 7 和8.1 的遷移</span><span class="sxs-lookup"><span data-stu-id="3ab21-212">Migration for Windows 7 and 8.1</span></span>

<span data-ttu-id="3ab21-213">Windows 7 在 *2020 年1月14日* 已結束支援。</span><span class="sxs-lookup"><span data-stu-id="3ab21-213">Support ended for Windows 7 on *January 14, 2020*.</span></span> <span data-ttu-id="3ab21-214">若要遷移執行 Windows 7 或 Windows 8.1 的裝置，您可以執行就地升級。</span><span class="sxs-lookup"><span data-stu-id="3ab21-214">To migrate your devices that run Windows 7 or Windows 8.1, you can do an in-place upgrade.</span></span>

<span data-ttu-id="3ab21-215">如需其他方法，請參閱 [Windows 10 部署案例](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios)。</span><span class="sxs-lookup"><span data-stu-id="3ab21-215">For additional methods, see [Windows 10 deployment scenarios](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios).</span></span> <span data-ttu-id="3ab21-216">您也可以自行[規劃 Windows 10 部署](https://aka.ms/planforwin10deployment)。</span><span class="sxs-lookup"><span data-stu-id="3ab21-216">You can also [plan for Windows 10 deployment](https://aka.ms/planforwin10deployment) on your own.</span></span>

## <a name="office-2010-clients-and-servers-and-windows-7"></a><span data-ttu-id="3ab21-217">Office 2010 用戶端和伺服器及 Windows 7</span><span class="sxs-lookup"><span data-stu-id="3ab21-217">Office 2010 clients and servers and Windows 7</span></span>

<span data-ttu-id="3ab21-218">以下是 Office 2010 用戶端和伺服器及 Windows 7 的升級、遷移和移至雲端選項的視覺摘要：</span><span class="sxs-lookup"><span data-stu-id="3ab21-218">Here's a visual summary of the upgrade, migration, and move-to-cloud options for Office 2010 clients and servers and Windows 7:</span></span>

<span data-ttu-id="3ab21-219">[![顯示 Office 2010 用戶端和伺服器及 Windows 7 支援終止選項的影像。](../media/microsoft-365-overview/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)</span><span class="sxs-lookup"><span data-stu-id="3ab21-219">[![Image showing the options for the end of support for Office 2010 clients and servers and Windows 7.](../media/microsoft-365-overview/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)</span></span>

<span data-ttu-id="3ab21-220">這個單頁標牌是一種快速瞭解可用於管理 Office 2010 用戶端和伺服器產品及 Windows 7 支援的路徑。</span><span class="sxs-lookup"><span data-stu-id="3ab21-220">This one-page poster is a quick way to understand the paths you can take to manage the end of support for Office 2010 client and server products and Windows 7.</span></span> <span data-ttu-id="3ab21-221">Microsoft 365 企業版支援偏好的路徑。</span><span class="sxs-lookup"><span data-stu-id="3ab21-221">The preferred paths are supported in Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="3ab21-222">您可以 [下載此標牌](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) ，並以 letter 大小、合法大小或 tabloid 列印它，) 大小 (11 x 17。</span><span class="sxs-lookup"><span data-stu-id="3ab21-222">You can [download this poster](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) and print it in letter size, legal size, or tabloid (11 x 17) size.</span></span>

## <a name="transition-your-entire-organization"></a><span data-ttu-id="3ab21-223">轉換整個組織</span><span class="sxs-lookup"><span data-stu-id="3ab21-223">Transition your entire organization</span></span>

<span data-ttu-id="3ab21-224">若要深入瞭解如何將整個組織移至 Microsoft 365 企業版中的產品和服務，請下載此轉換海報：</span><span class="sxs-lookup"><span data-stu-id="3ab21-224">To get a better picture of how to move your entire organization to the products and services in Microsoft 365 Enterprise, download this transition poster:</span></span>

<span data-ttu-id="3ab21-225">[![顯示轉換至 Microsoft 365 海報的圖像。](../media/microsoft-365-overview/transition-org-to-m365.png)](https://download.microsoft.com/download/2/c/7/2c7bcc04-aae3-4604-9707-1ffff66b9851/transition-org-to-m365.pdf)</span><span class="sxs-lookup"><span data-stu-id="3ab21-225">[![Image showing the Transition to Microsoft 365 poster.](../media/microsoft-365-overview/transition-org-to-m365.png)](https://download.microsoft.com/download/2/c/7/2c7bcc04-aae3-4604-9707-1ffff66b9851/transition-org-to-m365.pdf)</span></span>

<span data-ttu-id="3ab21-226">這份雙頁海報是清查現有基礎結構的快速方式。</span><span class="sxs-lookup"><span data-stu-id="3ab21-226">This two-page poster is a quick way to inventory your existing infrastructure.</span></span> <span data-ttu-id="3ab21-227">使用它來取得移至 Microsoft 365 企業版產品或服務的指導方針。</span><span class="sxs-lookup"><span data-stu-id="3ab21-227">Use it to get guidance for moving to a product or service in Microsoft 365 Enterprise.</span></span> <span data-ttu-id="3ab21-228">它會顯示 Windows 和 Office 產品及其他基礎結構及安全性元素，例如裝置管理、身分識別和威脅防護，以及資訊和合規性防護。</span><span class="sxs-lookup"><span data-stu-id="3ab21-228">It shows Windows and Office products and other infrastructure and security elements such as device management, identity and threat protection, and information and compliance protection.</span></span>

## <a name="how-microsoft-migrated-to-microsoft-365-enterprise"></a><span data-ttu-id="3ab21-229">Microsoft 如何遷移至 Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="3ab21-229">How Microsoft migrated to Microsoft 365 Enterprise</span></span>

<span data-ttu-id="3ab21-230">請參閱 Microsoft IT 專家如何將公司遷移至 Microsoft 365 企業版：</span><span class="sxs-lookup"><span data-stu-id="3ab21-230">See how IT experts at Microsoft migrated the company to Microsoft 365 Enterprise:</span></span>

- [<span data-ttu-id="3ab21-231">部署和更新適用于企業的 Microsoft 365 應用程式</span><span class="sxs-lookup"><span data-stu-id="3ab21-231">Deploying and updating Microsoft 365 Apps for enterprise</span></span>](https://www.microsoft.com/itshowcase/Article/Content/757/Deploying-and-updating-Microsoft-Office-365-ProPlus)
- [<span data-ttu-id="3ab21-232">Microsoft 會將 150000 個信箱移轉到 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="3ab21-232">Microsoft migrates 150,000 mailboxes to Exchange Online</span></span>](https://www.microsoft.com/itshowcase/Article/Content/577/Microsoft-migrates-150000-mailboxes-to-Exchange-Online)
- [<span data-ttu-id="3ab21-233">SharePoint 至雲端：深入了解 Microsoft 如何執行自己的移轉</span><span class="sxs-lookup"><span data-stu-id="3ab21-233">SharePoint to the cloud: Learn how Microsoft ran its own migration</span></span>](https://www.microsoft.com/itshowcase/Article/Content/691/SharePoint-to-the-cloud-Learn-how-Microsoft-ran-its-own-migration)
- [<span data-ttu-id="3ab21-234">在 Microsoft 以就地升級方式部署 Windows 10</span><span class="sxs-lookup"><span data-stu-id="3ab21-234">Deploying Windows 10 at Microsoft as an in-place upgrade</span></span>](https://www.microsoft.com/itshowcase/Article/Content/668/Deploying-Windows-10-at-Microsoft-as-an-inplace-upgrade)
- <span data-ttu-id="3ab21-235">[Windows 10 部署： MICROSOFT IT (影片) 的秘訣和技巧](https://www.microsoft.com/itshowcase/Article/Content/951/Windows-10-deployment-tips-and-tricks-from-Microsoft-IT)</span><span class="sxs-lookup"><span data-stu-id="3ab21-235">[Windows 10 deployment: Tips and tricks from Microsoft IT](https://www.microsoft.com/itshowcase/Article/Content/951/Windows-10-deployment-tips-and-tricks-from-Microsoft-IT) (video)</span></span>
