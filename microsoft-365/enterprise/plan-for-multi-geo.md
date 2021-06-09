---
title: 規劃 Microsoft 365 多地理位置
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.collection:
- Strat_SP_gtc
- SPO_Content
localization_priority: Normal
description: 了解什麼是 Microsoft 365 多地理位置、多地理位置的運作方式，以及哪些地理位置可用於儲存資料。
ms.openlocfilehash: 9625d55015cc0f18801d59e82fc8ca7090b3b721
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927529"
---
# <a name="plan-for-microsoft-365-multi-geo"></a><span data-ttu-id="ddfb0-103">規劃 Microsoft 365 多地理位置</span><span class="sxs-lookup"><span data-stu-id="ddfb0-103">Plan for Microsoft 365 Multi-Geo</span></span>

<span data-ttu-id="ddfb0-104">本指南是為多國公司 (MNC) 的系統管理員而設計，這些管理員會根據公司的目前位置將 Microsoft 365 租用戶擴充至其他地理位置，以符合資料落地要求。</span><span class="sxs-lookup"><span data-stu-id="ddfb0-104">This guidance is designed for administrators of multi-national companies (MNCs) who are preparing their Microsoft 365 tenant to be expanded to additional geographies in accordance with the company’s presence to meet data residency requirements.</span></span>

<span data-ttu-id="ddfb0-105">在多地理位置組態中，Microsoft 365 租用戶由一個中央位置和一或多個衛星位置所組成。</span><span class="sxs-lookup"><span data-stu-id="ddfb0-105">In a multi-geo configuration, your Microsoft 365 tenant consists of a central location and one or more satellite locations.</span></span> <span data-ttu-id="ddfb0-106">這個單一租用戶跨越多個地理位置。</span><span class="sxs-lookup"><span data-stu-id="ddfb0-106">This is a single tenant that spans across multiple geo locations.</span></span> <span data-ttu-id="ddfb0-107">您的租用戶資訊，包括由 Azure Active Directory (Azure AD) 管理的地理位置。</span><span class="sxs-lookup"><span data-stu-id="ddfb0-107">Your tenant information, including geo locations, is mastered in Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="ddfb0-108">以下是一些重要的多地理位置詞彙，可協助您了解設定的基本概念：</span><span class="sxs-lookup"><span data-stu-id="ddfb0-108">Here are some key multi-geo terms to help you understand the basic concepts of the configuration:</span></span>

-   <span data-ttu-id="ddfb0-109">**租用戶** – 組織在 Microsoft 365 中的呈現方式，通常會有與其相關聯的一個或多個網域 (例如 https://contoso.sharepoint.com))。</span><span class="sxs-lookup"><span data-stu-id="ddfb0-109">**Tenant** – An organization's representation in Microsoft 365 which typically has one or more domains associated with it (for example, https://contoso.sharepoint.com).</span></span> 

-   <span data-ttu-id="ddfb0-110">**地理位置** – 可用來裝載 Microsoft 365 租用戶中資料的地理位置。</span><span class="sxs-lookup"><span data-stu-id="ddfb0-110">**Geo locations** – The geographic locations available to host data in a Microsoft 365 tenant.</span></span>

-   <span data-ttu-id="ddfb0-111">**衛星位置**：您在 Microsoft 365 租用戶中設定來裝載資料的其他地理位置。</span><span class="sxs-lookup"><span data-stu-id="ddfb0-111">**Satellite locations** – The additional geo locations that you have configured to host data in your Microsoft 365 tenant.</span></span> <span data-ttu-id="ddfb0-112">多地理位置租用戶橫跨多個地理位置，例如，北美洲和歐洲。</span><span class="sxs-lookup"><span data-stu-id="ddfb0-112">Multi-geo tenants span more than one geo location, for example, North America and Europe.</span></span>

-   <span data-ttu-id="ddfb0-113">**慣用的資料位置 (PDL)** -個別使用者儲存 Exchange 和 OneDrive 資料的地理位置。</span><span class="sxs-lookup"><span data-stu-id="ddfb0-113">**Preferred Data Location (PDL)** – The geo location where an individual user's Exchange and OneDrive data is stored.</span></span> <span data-ttu-id="ddfb0-114">系統管理員可將此位置設定為已為租用戶設定的任何地理位置。</span><span class="sxs-lookup"><span data-stu-id="ddfb0-114">This can be set by the administrator to any of the geo locations that have been configured for the tenant.</span></span> <span data-ttu-id="ddfb0-115">請注意，如果您變更已經擁有 OneDrive 網站的使用者的 PDL，他們的 OneDrive 資料將不會自動移動到新的地理位置。</span><span class="sxs-lookup"><span data-stu-id="ddfb0-115">Note that if you change the PDL for a user who already has a OneDrive site, their OneDrive data is not moved to the new geo location automatically.</span></span> <span data-ttu-id="ddfb0-116">如需詳細資訊，請參閱[將 OneDrive 文件庫移至不同的地理位置](move-onedrive-between-geo-locations.md)。</span><span class="sxs-lookup"><span data-stu-id="ddfb0-116">See [Move a OneDrive library to a different geo-location](move-onedrive-between-geo-locations.md) for more information.</span></span> <span data-ttu-id="ddfb0-117">如果他們有 Exchange 信箱，則信箱會自動移至新的慣用資料位置。</span><span class="sxs-lookup"><span data-stu-id="ddfb0-117">If they have an Exchange mailbox, the mailbox is moved to the new preferred data location automatically.</span></span>

<span data-ttu-id="ddfb0-118">啟用多地理位置需要四個關鍵步驟：</span><span class="sxs-lookup"><span data-stu-id="ddfb0-118">Enabling Multi-Geo requires four key steps:</span></span>

1.  <span data-ttu-id="ddfb0-119">與您的帳戶團隊合作來新增「Microsoft 365 多地理位置功能」服務方案。</span><span class="sxs-lookup"><span data-stu-id="ddfb0-119">Work with your account team to add the _Multi-Geo Capabilities in Microsoft 365_ service plan.</span></span>

2.  <span data-ttu-id="ddfb0-120">選擇您想要的衛星位置，並將其新增至您的租用戶。</span><span class="sxs-lookup"><span data-stu-id="ddfb0-120">Choose your desired satellite location(s) and add them to your tenant.</span></span>

3.  <span data-ttu-id="ddfb0-121">將使用者的慣用資料位置設定為想要的衛星位置。</span><span class="sxs-lookup"><span data-stu-id="ddfb0-121">Set your users' preferred data location to the desired satellite location.</span></span> <span data-ttu-id="ddfb0-122">為使用者佈建新 OneDrive 網站或 Exchange 信箱時，該網站或信箱會佈建到使用者的 PDL。</span><span class="sxs-lookup"><span data-stu-id="ddfb0-122">When a new OneDrive site or Exchange mailbox is provisioned for a user, it is provisioned to their PDL.</span></span>

4.  <span data-ttu-id="ddfb0-123">請視需要將使用者現有 OneDrive 網站從中央位置移轉至其慣用的資料位置。</span><span class="sxs-lookup"><span data-stu-id="ddfb0-123">Migrate your users' existing OneDrive sites from the central location to their preferred data location as needed.</span></span> <span data-ttu-id="ddfb0-124">(當您設定使用者的 PDL 時，系統會自動移轉 Exchange 信箱。)</span><span class="sxs-lookup"><span data-stu-id="ddfb0-124">(Exchange mailboxes are migrated automatically when you set a user's PDL.)</span></span>

<span data-ttu-id="ddfb0-125">如需各步驟的詳細資料，請參閱[設定 Microsoft 365 多地理位置](multi-geo-tenant-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="ddfb0-125">See [Configure Microsoft 365 Multi-Geo](multi-geo-tenant-configuration.md) for details on each of these steps.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ddfb0-126">請注意，Microsoft 365 多地理位置不是為效能最佳化優化而設計，其主要設計目的在滿足資料落地要求。</span><span class="sxs-lookup"><span data-stu-id="ddfb0-126">Note that Microsoft 365 Multi-Geo is not designed for performance optimization, it is designed to meet data residency requirements.</span></span> <span data-ttu-id="ddfb0-127">如需 Microsoft 365 效能最佳化的詳細資訊，請參閱 [Microsoft 365 的網路規劃與效能調整](https://support.office.com/article/e5f1228c-da3c-4654-bf16-d163daee8848)或連絡客戶支援小組。</span><span class="sxs-lookup"><span data-stu-id="ddfb0-127">For information about performance optimization for Microsoft 365, see [Network planning and performance tuning for Microsoft 365](https://support.office.com/article/e5f1228c-da3c-4654-bf16-d163daee8848) or contact your support group.</span></span>

<span data-ttu-id="ddfb0-128">您可以將下列位置設定為衛星位置，以便在其上裝載 OneDrive 和 SharePoint 網站，及 Exchange 信箱。</span><span class="sxs-lookup"><span data-stu-id="ddfb0-128">You can configure any of the following locations to be satellite locations where you can host OneDrive and SharePoint sites, and Exchange mailboxes.</span></span> <span data-ttu-id="ddfb0-129">當您規劃多地理位置時，請列出您要新增至 Microsoft 365 租用戶的位置清單。</span><span class="sxs-lookup"><span data-stu-id="ddfb0-129">As you plan for multi-geo, make a list of the locations that you want to add to your Microsoft 365 tenant.</span></span> <span data-ttu-id="ddfb0-130">我們建議從一或兩個衛星位置開始，然後再視需要逐步擴充至更多地理位置。</span><span class="sxs-lookup"><span data-stu-id="ddfb0-130">We recommend starting with one or two satellite locations and then gradually expanding to more geo locations, if needed.</span></span>

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

<span data-ttu-id="ddfb0-p108">設定多地理位置時，請考慮在移轉到 Microsoft 365 時合併內部部署基礎結構的可能性。比方說，如果您在新加坡和馬來西亞有內部部署伺服器陣列，然後您可以將他們合併至 APC 衛星位置中，提供的資料常駐要求可讓您執行此動作。</span><span class="sxs-lookup"><span data-stu-id="ddfb0-p108">When you configure multi-geo, consider taking the opportunity to consolidate your on-premises infrastructure while migrating to Microsoft 365. For example, if you have on-premises farms in Singapore and Malaysia, then you can consolidate them to the APC satellite location, provided data residency requirements allow you to do so.</span></span>

## <a name="best-practices"></a><span data-ttu-id="ddfb0-133">最佳做法</span><span class="sxs-lookup"><span data-stu-id="ddfb0-133">Best practices</span></span>

<span data-ttu-id="ddfb0-134">我們建議您在 Microsoft 365 中建立測試使用者，以進行一些初步測試。</span><span class="sxs-lookup"><span data-stu-id="ddfb0-134">We recommend that you create a test user in Microsoft 365 to do some initial testing.</span></span> <span data-ttu-id="ddfb0-135">在您將生產使用者上架到 Microsoft 365 多地理位置之前，我們將與該使用者一起完成一些測試和驗證步驟。</span><span class="sxs-lookup"><span data-stu-id="ddfb0-135">We’ll walk through some testing and verification steps with this user before you proceed to onboard production users into Microsoft 365 Multi-Geo.</span></span>

<span data-ttu-id="ddfb0-136">與測試使用者一起完成測試後，請選取一個試驗組 (可以是您的 IT 部門的人員)，成為第一批在新地理位置使用 OneDrive 和 Exchange 的人。</span><span class="sxs-lookup"><span data-stu-id="ddfb0-136">Once you’ve completed testing with the test user, select a pilot group – perhaps from your IT department – to be the first to use OneDrive and Exchange in a new geo location.</span></span> <span data-ttu-id="ddfb0-137">在第一批人員當中，選取還沒有 OneDrive 的使用者。</span><span class="sxs-lookup"><span data-stu-id="ddfb0-137">For this first group, select users who do not yet have a OneDrive.</span></span> <span data-ttu-id="ddfb0-138">我們建議這個試驗組不要超過五個人，之後再透過批次推出方法來逐步擴展。</span><span class="sxs-lookup"><span data-stu-id="ddfb0-138">We recommend no more than five people in this initial group and gradually expand following a batched rollout approach.</span></span>

<span data-ttu-id="ddfb0-p111">每個使用者應具備 *慣用的資料位置*(PDL) 設定，以便 Microsoft 365 判斷佈建其 OneDrive 的地理位置。使用者慣用的資料位置必須與您所選的某個衛星位置或您的中心位置相符。當 PDL 不是強制性欄位時，我們建議為所有使用者設定 PDL。沒有 PDL 的使用者工作負載會佈建在中心位置。</span><span class="sxs-lookup"><span data-stu-id="ddfb0-p111">Each user should have a *preferred data location* (PDL) set so that Microsoft 365 can determine in which geo location to provision their OneDrive. The user's preferred data location must match one of your chosen satellite locations or your central location. While the PDL field is not mandatory, we recommend that a PDL be set for all users. Workloads of a user without a PDL will be provisioned in the central location.</span></span>

<span data-ttu-id="ddfb0-p112">建立使用者清單，並包含使用者主體名稱 (UPN) 與適當慣用資料位置的位置代碼。包含測試使用者與您起始的試驗群組來開始進行。您將需要此清單來設定程序。</span><span class="sxs-lookup"><span data-stu-id="ddfb0-p112">Create a list of your users, and include their user principal name (UPN) and the location code for the appropriate preferred data location. Include your test user and your initial pilot group to start with. You'll need this list for the configuration procedures.</span></span>

<span data-ttu-id="ddfb0-146">如果您的使用者是從內部部署 Active Directory 系統同步到 Azure Active Directory，您必須將慣用資料位置設定為 Active Directory 屬性，並使用 Azure Active Directory Connect 進行同步。</span><span class="sxs-lookup"><span data-stu-id="ddfb0-146">If your users are synchronized from an on-premises Active Directory system to Azure Active Directory, you must set the preferred data location as an Active Directory attribute and synchronize it by using Azure Active Directory Connect.</span></span> <span data-ttu-id="ddfb0-147">您無法使用 Azure AD PowerShell為同步使用者直接設定慣用資料位置。</span><span class="sxs-lookup"><span data-stu-id="ddfb0-147">You cannot directly configure the preferred data location for synchronized users using Azure AD PowerShell.</span></span> <span data-ttu-id="ddfb0-148">在 Active Directory 中設定 PDL 並對其進行同步的步驟會於 [Azure Active Directory Connect 同步：為 Microsoft 365 資源設定慣用資料位置](/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation)中說明。</span><span class="sxs-lookup"><span data-stu-id="ddfb0-148">The steps to set up PDL in Active Directory and Synchronize it are covered in [Azure Active Directory Connect sync: Configure preferred data location for Microsoft 365 resources](/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation).</span></span>

<span data-ttu-id="ddfb0-p114">多地理位置租用戶的管理可能與非多地理位置租用戶不同，因為許多 SharePoint 和 OneDrive 設定與服務具有多地理位置意識。我們建議您檢閱[管理多地理位置環境](administering-a-multi-geo-environment.md)，再繼續進行您的組態。</span><span class="sxs-lookup"><span data-stu-id="ddfb0-p114">The administration of a multi-geo tenant can differ from a non-multi-geo tenant, as many of the SharePoint and OneDrive settings and services are multi-geo aware. We recommend that you review [Administering a multi-geo environment](administering-a-multi-geo-environment.md) before you proceed with your configuration.</span></span>

<span data-ttu-id="ddfb0-151">在 [多地理位置環境中讀取使用者的經驗](multi-geo-user-experience.md) ，以取得使用者在多地理位置環境中的體驗的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="ddfb0-151">Read [User experience in a multi-geo environment](multi-geo-user-experience.md) for details about your end users' experience in a multi-geo environment.</span></span>

<span data-ttu-id="ddfb0-152">如需有關 Microsoft 365 多地理位置租用中 Teams 體驗的詳細資訊，請參閱[在 Microsoft 365 OneDrive 和 SharePoint Online 多地理位置租用中的 Teams 體驗](/microsoftteams/teams-experience-o365odb-spo-multi-geo) (部分機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="ddfb0-152">For details about the Teams experience in a Microsoft 365 Multi-Geo tenancy, see [Teams experience in a Microsoft 365 OneDrive and SharePoint Online Multi-Geo-enabled tenancy](/microsoftteams/teams-experience-o365odb-spo-multi-geo).</span></span>

<span data-ttu-id="ddfb0-153">若要開始設定 Microsoft 365 多地理位置，請參閱[設定 Microsoft 365 多地理位置](multi-geo-tenant-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="ddfb0-153">To get started configuring Microsoft 365 Multi-Geo, see [Configure Microsoft 365 Multi-Geo](multi-geo-tenant-configuration.md).</span></span>

<span data-ttu-id="ddfb0-154">當您完成設定時，請記得視需要[移轉使用者的 OneDrive 文件庫](move-onedrive-between-geo-locations.md)，讓使用者在自己慣用的資料位置工作。</span><span class="sxs-lookup"><span data-stu-id="ddfb0-154">Once you've completed the configuration, remember to [migrate your users' OneDrive libraries](move-onedrive-between-geo-locations.md) as needed to get your users working from their preferred data locations.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ddfb0-155">相關主題</span><span class="sxs-lookup"><span data-stu-id="ddfb0-155">Related topics</span></span>

[<span data-ttu-id="ddfb0-156">Microsoft 365 多地理位置電子文件探索設定</span><span class="sxs-lookup"><span data-stu-id="ddfb0-156">Microsoft 365 Multi-Geo eDiscovery configuration</span></span>](./multi-geo-ediscovery-configuration.md)