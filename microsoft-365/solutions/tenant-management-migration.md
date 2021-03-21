---
title: 步驟 4： Microsoft 365 for enterprise 承租人的遷移
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
- tenant-management
- m365solution-scenario
ms.custom:
- Ent_Solutions
description: 針對您的 Microsoft 365 承租人遷移您的 Windows 裝置、Office 用戶端應用程式及 Office server。
ms.openlocfilehash: 336dee2e62c6d0917c437252ba1d741c304998fa
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929141"
---
# <a name="step-4-migration-for-your-microsoft-365-for-enterprise-tenants"></a><span data-ttu-id="3049b-104">步驟 4.</span><span class="sxs-lookup"><span data-stu-id="3049b-104">Step 4.</span></span> <span data-ttu-id="3049b-105">Microsoft 365 for enterprise 承租人的遷移</span><span class="sxs-lookup"><span data-stu-id="3049b-105">Migration for your Microsoft 365 for enterprise tenants</span></span>

<span data-ttu-id="3049b-106">大多數的企業組織都有異構環境，包括多個版本的作業系統、用戶端軟體和伺服器軟體。</span><span class="sxs-lookup"><span data-stu-id="3049b-106">Most enterprise organizations have a heterogeneous environment that includes multiple releases of operating systems, client software, and server software.</span></span> <span data-ttu-id="3049b-107">適用于企業的 Microsoft 365 包括 IT 基礎結構主要元件的最安全版本。</span><span class="sxs-lookup"><span data-stu-id="3049b-107">Microsoft 365 for enterprise includes the most secure versions of the key components of your IT infrastructure.</span></span> <span data-ttu-id="3049b-108">此外，它也包含可讓您利用雲端技術的生產力功能。</span><span class="sxs-lookup"><span data-stu-id="3049b-108">It also includes productivity features that are designed to take advantage of cloud technologies.</span></span>

<span data-ttu-id="3049b-109">若要最大化 Microsoft 365 的企業整合套件的商業價值，請開始規劃及執行策略，以遷移這些版本：</span><span class="sxs-lookup"><span data-stu-id="3049b-109">To maximize the business value of the Microsoft 365 for enterprise integrated suite of products, begin planning and implementing a strategy to migrate these releases:</span></span>

| <span data-ttu-id="3049b-110">寄件者</span><span class="sxs-lookup"><span data-stu-id="3049b-110">From</span></span> | <span data-ttu-id="3049b-111">收件者</span><span class="sxs-lookup"><span data-stu-id="3049b-111">To</span></span> |
|:-------|:-----|
| <span data-ttu-id="3049b-112">Windows 7 和 Windows 8。1</span><span class="sxs-lookup"><span data-stu-id="3049b-112">Windows 7 and Windows 8.1</span></span> | <span data-ttu-id="3049b-113">Windows 10 企業版</span><span class="sxs-lookup"><span data-stu-id="3049b-113">Windows 10 Enterprise</span></span> |
| <span data-ttu-id="3049b-114">在您的工作人員裝置上安裝的 Office 用戶端產品</span><span class="sxs-lookup"><span data-stu-id="3049b-114">Office client products installed on your worker's devices</span></span> | <span data-ttu-id="3049b-115">Microsoft 365 Apps 企業版</span><span class="sxs-lookup"><span data-stu-id="3049b-115">Microsoft 365 Apps for enterprise</span></span> |
| <span data-ttu-id="3049b-116">在內部部署伺服器上安裝的 Office server 產品</span><span class="sxs-lookup"><span data-stu-id="3049b-116">Office server products installed on on-premises servers</span></span> | <span data-ttu-id="3049b-117">Microsoft 365 中其對等雲端型服務</span><span class="sxs-lookup"><span data-stu-id="3049b-117">Their equivalent cloud-based services in Microsoft 365</span></span> |
|  |  |

## <a name="migrating-to-windows-10"></a><span data-ttu-id="3049b-118">遷移至 Windows 10</span><span class="sxs-lookup"><span data-stu-id="3049b-118">Migrating to Windows 10</span></span>

<span data-ttu-id="3049b-119">每個 Microsoft 365 for enterprise license 都包含 Windows 10 企業版的授權。</span><span class="sxs-lookup"><span data-stu-id="3049b-119">Each Microsoft 365 for enterprise license includes a license for Windows 10 Enterprise.</span></span> <span data-ttu-id="3049b-120">若要遷移執行 Windows 7 或 Windows 8.1 的裝置，您可以執行就地升級。</span><span class="sxs-lookup"><span data-stu-id="3049b-120">To migrate your devices that run Windows 7 or Windows 8.1, you can do an in-place upgrade.</span></span> <span data-ttu-id="3049b-121">Windows 7 在 *2020 年1月14日* 已結束支援。</span><span class="sxs-lookup"><span data-stu-id="3049b-121">Support ended for Windows 7 on *January 14, 2020*.</span></span> 

<span data-ttu-id="3049b-122">如需在就地升級之外安裝 Windows 10 企業版的其他方法，請參閱 [Windows 10 部署案例](/windows/deployment/windows-10-deployment-scenarios)。</span><span class="sxs-lookup"><span data-stu-id="3049b-122">For additional methods of installing Windows 10 Enterprise beyond an in-place upgrade, see [Windows 10 deployment scenarios](/windows/deployment/windows-10-deployment-scenarios).</span></span> <span data-ttu-id="3049b-123">您也可以自行[規劃 Windows 10 部署](/windows/deployment/planning/)。</span><span class="sxs-lookup"><span data-stu-id="3049b-123">You can also [plan for Windows 10 deployment](/windows/deployment/planning/) on your own.</span></span>

## <a name="migrating-to-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="3049b-124">遷移至適用于企業的 Microsoft 365 應用程式</span><span class="sxs-lookup"><span data-stu-id="3049b-124">Migrating to Microsoft 365 Apps for enterprise</span></span>

<span data-ttu-id="3049b-125">適用于企業的 microsoft 365 包括 Microsoft 365 應用程式的企業版、Office 用戶端產品的版本 (Word、PowerPoint、Excel 和 Outlook) 已從 Microsoft 雲端安裝及更新。</span><span class="sxs-lookup"><span data-stu-id="3049b-125">Microsoft 365 for enterprise includes Microsoft 365 Apps for enterprise, a version of the Office client products (Word, PowerPoint, Excel, and Outlook) that is installed and updated from the Microsoft cloud.</span></span> <span data-ttu-id="3049b-126">如需詳細資訊，請參閱 [關於適用于企業的 Microsoft 365 應用程式](/deployoffice/about-microsoft-365-apps)。</span><span class="sxs-lookup"><span data-stu-id="3049b-126">For more information, see [About Microsoft 365 Apps for enterprise](/deployoffice/about-microsoft-365-apps).</span></span>

<span data-ttu-id="3049b-127">請執行下列步驟，而不是讓您的電腦成為 Office 2019 或舊版的最新版本：</span><span class="sxs-lookup"><span data-stu-id="3049b-127">Rather than keeping your computers current for Office 2019 or older versions, take the following steps:</span></span>

1. <span data-ttu-id="3049b-128">為您的使用者取得並指派 Microsoft 365 授權。</span><span class="sxs-lookup"><span data-stu-id="3049b-128">Get and assign a Microsoft 365 license for your users.</span></span>
2. <span data-ttu-id="3049b-129">卸載其電腦上的 Office 2013 或 Office 2016。</span><span class="sxs-lookup"><span data-stu-id="3049b-129">Uninstall Office 2013 or Office 2016 on their computers.</span></span>
3. <span data-ttu-id="3049b-130">安裝 Microsoft 365 應用程式 for enterprise （不論是個別安裝或進行 IT 推廣）。</span><span class="sxs-lookup"><span data-stu-id="3049b-130">Install Microsoft 365 Apps for enterprise, either individually or during an IT rollout.</span></span> <span data-ttu-id="3049b-131">如需詳細資訊，請參閱 [Microsoft 365 應用程式的部署指南](/deployoffice/deployment-guide-microsoft-365-apps)。</span><span class="sxs-lookup"><span data-stu-id="3049b-131">For more information, see [Deployment guide for Microsoft 365 Apps](/deployoffice/deployment-guide-microsoft-365-apps).</span></span>

<span data-ttu-id="3049b-132">Microsoft 365 應用程式的企業應用程式會自動安裝安全性更新和新功能，並可利用 Microsoft 365 中的雲端式服務，以獲得增強的安全性和生產力。</span><span class="sxs-lookup"><span data-stu-id="3049b-132">Microsoft 365 Apps for enterprise installs both security updates and new feature updates automatically and can take advantage of cloud-based services in Microsoft 365 for enhanced security and productivity.</span></span>

## <a name="migrating-on-premises-servers-and-data-to-microsoft-365"></a><span data-ttu-id="3049b-133">將內部部署伺服器和資料移轉至 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3049b-133">Migrating on-premises servers and data to Microsoft 365</span></span>

<span data-ttu-id="3049b-134">Microsoft 365 for enterprise 包含雲端架構版本的 Office server 服務，其使用一些與 Office server 軟體內部部署版本（如網頁瀏覽器和 Outlook 用戶端）相同的工具。</span><span class="sxs-lookup"><span data-stu-id="3049b-134">Microsoft 365 for enterprise includes cloud-based versions of Office server services that use some of the same tools as on-premises versions of Office server software, such as web browsers and the Outlook client.</span></span> <span data-ttu-id="3049b-135">這些雲端式服務會自動更新，以取得安全性和新功能。</span><span class="sxs-lookup"><span data-stu-id="3049b-135">These cloud-based services are automatically updated for security and new features.</span></span> <span data-ttu-id="3049b-136">遷移後，您的 IT 部門可以節省維護和更新內部部署伺服器所需的時間。</span><span class="sxs-lookup"><span data-stu-id="3049b-136">After migration, your IT department can save the time it takes to maintain and update on-premises servers.</span></span>

<span data-ttu-id="3049b-137">請使用下列資源，以取得針對特定 Microsoft 365 工作負載的使用者和資料進行遷移的相關資訊：</span><span class="sxs-lookup"><span data-stu-id="3049b-137">Use the following resources for information about migrating users and data for specific Microsoft 365 workloads:</span></span>

- [<span data-ttu-id="3049b-138">將信箱從內部部署 Exchange Server 移至 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="3049b-138">Move mailboxes from on-premises Exchange Server to Exchange Online</span></span>](/exchange/hybrid-deployment/move-mailboxes)
- [<span data-ttu-id="3049b-139">將 SharePoint 資料從 SharePoint 伺服器遷移至 SharePoint 線上</span><span class="sxs-lookup"><span data-stu-id="3049b-139">Migrate SharePoint data from SharePoint Server to SharePoint Online</span></span>](/sharepointmigration/migrate-to-sharepoint-online)
- [<span data-ttu-id="3049b-140">將商務用 Skype Online 遷移至 Microsoft 團隊</span><span class="sxs-lookup"><span data-stu-id="3049b-140">Migrate Skype for Business Online to Microsoft Teams</span></span>](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

## <a name="transition-your-entire-organization"></a><span data-ttu-id="3049b-141">轉換整個組織</span><span class="sxs-lookup"><span data-stu-id="3049b-141">Transition your entire organization</span></span>

<span data-ttu-id="3049b-142">若要深入瞭解如何將整個組織移至 Microsoft 365 for enterprise 中的產品和服務，請下載此轉換海報：</span><span class="sxs-lookup"><span data-stu-id="3049b-142">To get a better picture of how to move your entire organization to the products and services in Microsoft 365 for enterprise, download this transition poster:</span></span>

<span data-ttu-id="3049b-143">[![顯示轉換至 Microsoft 365 海報的圖像。](../media/microsoft-365-overview/transition-org-to-m365.png)](https://download.microsoft.com/download/2/c/7/2c7bcc04-aae3-4604-9707-1ffff66b9851/transition-org-to-m365.pdf)</span><span class="sxs-lookup"><span data-stu-id="3049b-143">[![Image showing the Transition to Microsoft 365 poster.](../media/microsoft-365-overview/transition-org-to-m365.png)](https://download.microsoft.com/download/2/c/7/2c7bcc04-aae3-4604-9707-1ffff66b9851/transition-org-to-m365.pdf)</span></span>

<span data-ttu-id="3049b-144">這份雙頁海報是清查現有基礎結構的快速方式。</span><span class="sxs-lookup"><span data-stu-id="3049b-144">This two-page poster is a quick way to inventory your existing infrastructure.</span></span> <span data-ttu-id="3049b-145">使用此功能，取得在 Microsoft 365 for enterprise 中移至產品或服務的指導方針。</span><span class="sxs-lookup"><span data-stu-id="3049b-145">Use it to get guidance for moving to a product or service in Microsoft 365 for enterprise.</span></span> <span data-ttu-id="3049b-146">它會顯示 Windows 和 Office 產品及其他基礎結構及安全性元素，例如裝置管理、身分識別和威脅防護，以及資訊保護和符合性。</span><span class="sxs-lookup"><span data-stu-id="3049b-146">It shows Windows and Office products and other infrastructure and security elements such as device management, identity and threat protection, and information protection and compliance.</span></span>

## <a name="results-of-step-4"></a><span data-ttu-id="3049b-147">步驟 4 的結果</span><span class="sxs-lookup"><span data-stu-id="3049b-147">Results of Step 4</span></span>

<span data-ttu-id="3049b-148">針對您的 Microsoft 365 承租人進行遷移，您已決定：</span><span class="sxs-lookup"><span data-stu-id="3049b-148">For migration for your Microsoft 365 tenant, you have determined:</span></span>

- <span data-ttu-id="3049b-149">哪些裝置執行 Windows 7 或 Windows 8.1，以及將其更新至 Windows 10 企業版的計畫。</span><span class="sxs-lookup"><span data-stu-id="3049b-149">Which devices are running Windows 7 or Windows 8.1 and the plan to update them to Windows 10 Enterprise.</span></span>
- <span data-ttu-id="3049b-150">哪些裝置執行 Office 用戶端應用程式，以及將其更新至 Microsoft 365 應用程式以進行企業版的計畫。</span><span class="sxs-lookup"><span data-stu-id="3049b-150">Which devices are running the Office client apps and the plan to update them to Microsoft 365 apps for enterprise.</span></span>
- <span data-ttu-id="3049b-151">哪些內部部署 Office server 服務應遷移至其 Microsoft 365 對等專案，以及遷移其資料的計畫。</span><span class="sxs-lookup"><span data-stu-id="3049b-151">Which on-premises Office server services should be migrated to their Microsoft 365 equivalent and the plan to migrate them and their data.</span></span>

<span data-ttu-id="3049b-152">以下是承租人的範例，其中包含已完成的內部部署伺服器遷移。</span><span class="sxs-lookup"><span data-stu-id="3049b-152">Here is an example of a tenant with a completed migration of on-premises servers.</span></span>

![已完成內部部署伺服器遷移的承租人範例](../media/tenant-management-overview/tenant-management-tenant-build-step4.png)

<span data-ttu-id="3049b-154">在此圖中，組織的：</span><span class="sxs-lookup"><span data-stu-id="3049b-154">In this illustration, the organization has:</span></span>

- <span data-ttu-id="3049b-155">已將其內部部署 Exchange 伺服器信箱遷移至 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="3049b-155">Migrated its on-premises Exchange Server mailboxes to Exchange Online.</span></span>
- <span data-ttu-id="3049b-156">將其內部部署 SharePoint 伺服器網站和資料移轉至 Microsoft 365 中 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="3049b-156">Migrated its on-premises SharePoint Server sites and data to SharePoint in Microsoft 365.</span></span>

## <a name="ongoing-maintenance-for-migration"></a><span data-ttu-id="3049b-157">進行遷移的持續維護</span><span class="sxs-lookup"><span data-stu-id="3049b-157">Ongoing maintenance for migration</span></span>

<span data-ttu-id="3049b-158">您可能需要進行下列作業：</span><span class="sxs-lookup"><span data-stu-id="3049b-158">On an ongoing basis, you might need to:</span></span>

- <span data-ttu-id="3049b-159">請根據您的 Exchange 信箱遷移狀態，繼續在您的組織中滾動轉換至 Exchange。</span><span class="sxs-lookup"><span data-stu-id="3049b-159">Depending on the state of your Exchange mailbox migration, continue rolling the transition to Exchange Online out to your organization.</span></span>
- <span data-ttu-id="3049b-160">請根據您的內部部署 SharePoint 網站遷移狀態，繼續將 Microsoft 365 中 SharePoint 轉換為您的組織。</span><span class="sxs-lookup"><span data-stu-id="3049b-160">Depending on the state of your on-premises SharePoint site migration, continue rolling the transition to SharePoint in Microsoft 365 out to your organization.</span></span>

## <a name="next-step"></a><span data-ttu-id="3049b-161">後續步驟</span><span class="sxs-lookup"><span data-stu-id="3049b-161">Next step</span></span>

<span data-ttu-id="3049b-162">[![步驟5。部署裝置和應用程式管理](../media/tenant-management-overview/tenant-management-step-grid-device-mgmt.png)](tenant-management-device-management.md)</span><span class="sxs-lookup"><span data-stu-id="3049b-162">[![Step 5. Deploy device and app management](../media/tenant-management-overview/tenant-management-step-grid-device-mgmt.png)](tenant-management-device-management.md)</span></span>

<span data-ttu-id="3049b-163">繼續進行 [裝置和應用程式管理](tenant-management-device-management.md) ，以部署裝置和應用程式管理。</span><span class="sxs-lookup"><span data-stu-id="3049b-163">Continue with [device and app management](tenant-management-device-management.md) to deploy device and app management.</span></span>