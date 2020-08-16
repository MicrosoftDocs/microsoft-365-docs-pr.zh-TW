---
title: Microsoft 365 多地理位置
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.custom: seo-marvel-apr2020
ms.collection: Strat_SP_gtc
localization_priority: Normal
f1.keywords:
- NOCSH
description: 在本文中，您將瞭解如何使用 Microsoft 365 多地理位置，將 Microsoft 365 的目前狀態擴充為多個地理區域。
ms.openlocfilehash: a5843b98b5d64dfb3872c3d8a5d48c0e56949c02
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688682"
---
# <a name="microsoft-365-multi-geo"></a><span data-ttu-id="a875d-103">Microsoft 365 多地理位置</span><span class="sxs-lookup"><span data-stu-id="a875d-103">Microsoft 365 Multi-Geo</span></span>

<span data-ttu-id="a875d-104">使用 Microsoft 365 多地理位置，您的組織可以將 Microsoft 365 存在狀態擴展到現有租用戶中的多個地理區域和/或國家/地區。</span><span class="sxs-lookup"><span data-stu-id="a875d-104">With Microsoft 365 Multi-Geo, your organization can expand its Microsoft 365 presence to multiple geographic regions and/or countries within your existing tenant.</span></span> <span data-ttu-id="a875d-105">聯繫您的 Microsoft 客戶小組，以註冊跨國公司的 Microsoft 365 多地理位置。</span><span class="sxs-lookup"><span data-stu-id="a875d-105">Reach out to your Microsoft Account Team to sign up your Multi-National Company for Microsoft 365 Multi-Geo.</span></span>
  
<span data-ttu-id="a875d-106">您可以使用 Microsoft 365 多地理位置，在您所選擇的地理位置佈建和儲存待用資料以符合資料落地要求，同時將現代化生產力體驗逐步拓展至您的員工。</span><span class="sxs-lookup"><span data-stu-id="a875d-106">With Microsoft 365 Multi-Geo, you can provision and store data at rest in the geo locations that you've chosen to meet data residency requirements, and at the same time unlock your global roll out of modern productivity experiences to your workforce.</span></span>

#### <a name="video-introducing-microsoft-365-multi-geo"></a><span data-ttu-id="a875d-107">影片：簡介 Microsoft 365 多地理位置</span><span class="sxs-lookup"><span data-stu-id="a875d-107">Video: Introducing Microsoft 365 Multi-Geo</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1Yk6B?autoplay=false]

<span data-ttu-id="a875d-108">在多地理位置環境中，Microsoft 365 租用戶包含一個中央位置(最初佈建 Microsoft 365 訂閱的位置) 和一個或多個衛星位置。</span><span class="sxs-lookup"><span data-stu-id="a875d-108">In a Multi-Geo environment, your Microsoft 365 tenant consists of a central location (where your Microsoft 365 subscription was originally provisioned) and one or more satellite locations.</span></span> <span data-ttu-id="a875d-109">在多地理位置租用戶中，地理位置、群組和使用者資訊的相關資訊掌握在 Azure Active Directory (Azure AD) 中。</span><span class="sxs-lookup"><span data-stu-id="a875d-109">In a multi-geo tenant, the information about geo locations, groups, and user information, is mastered in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="a875d-110">由於您的租用戶資訊會集中管理並同步到每個地理位置，若要共用及體驗，公司的每一位員工都必須擁有全域概念。</span><span class="sxs-lookup"><span data-stu-id="a875d-110">Because your tenant information is mastered centrally and synchronized into each geo location, sharing and experiences involving anyone from your company contain global awareness.</span></span>

![SharePoint 系統管理中心內多地理位置地圖的螢幕擷取畫面](../media/multi-geo-world-map.png)

<span data-ttu-id="a875d-112">請注意，Microsoft 365 多地理位置不是為效能最佳化優化而設計，其主要設計目的在滿足資料落地要求。</span><span class="sxs-lookup"><span data-stu-id="a875d-112">Note that Microsoft 365 Multi-Geo is not designed for performance optimization, it is designed to meet data residency requirements.</span></span> <span data-ttu-id="a875d-113">如需 Microsoft 365 效能最佳化的詳細資訊，請參閱 [Microsoft 365 的網路規劃與效能調整](https://support.office.com/article/e5f1228c-da3c-4654-bf16-d163daee8848)或連絡客戶支援小組。</span><span class="sxs-lookup"><span data-stu-id="a875d-113">For information about performance optimization for Microsoft 365, see [Network planning and performance tuning for Microsoft 365](https://support.office.com/article/e5f1228c-da3c-4654-bf16-d163daee8848) or contact your support group.</span></span>

## <a name="terminology"></a><span data-ttu-id="a875d-114">術語</span><span class="sxs-lookup"><span data-stu-id="a875d-114">Terminology</span></span>

<span data-ttu-id="a875d-115">以下是用於說明 Microsoft 365 多地理位置的重要詞彙：</span><span class="sxs-lookup"><span data-stu-id="a875d-115">Here are the key terms used in describing Microsoft 365 Multi-Geo:</span></span>

- <span data-ttu-id="a875d-116">**中央位置** - 佈建租用戶的原始地理位置。</span><span class="sxs-lookup"><span data-stu-id="a875d-116">**Central location** - the geo location where your tenant was originally provisioned.</span></span>
- <span data-ttu-id="a875d-117">**地理位置管理員** - 系統管理員，可以管理一或多個指定的衛星位置。</span><span class="sxs-lookup"><span data-stu-id="a875d-117">**Geo administrator** - An administrator who can administer one or more specified satellite locations.</span></span>
- <span data-ttu-id="a875d-118">**地理位置代碼** - 表示特定地理位置的三個字母代碼。</span><span class="sxs-lookup"><span data-stu-id="a875d-118">**Geo code** - a three-letter code for a given geo location.</span></span>
- <span data-ttu-id="a875d-119">**地理位置** – 用於在多地理位置租用戶中主控資料的地理位置，包括 Exchange 信箱以及 OneDrive 和 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="a875d-119">**Geo location** – A geographic location that can be used in a multi-geo tenant to host data, including Exchange mailboxes and OneDrive and SharePoint sites.</span></span>
- <span data-ttu-id="a875d-120">**慣用的資料位置 (PDL)** - 由系統管理員設定的使用者屬性，表示應佈建使用者 Exchange 信箱和 OneDrive 的地理位置。</span><span class="sxs-lookup"><span data-stu-id="a875d-120">**Preferred Data Location (PDL)** – A user property set by the administrator that indicates where the geo location where the users Exchange mailbox and OneDrive should be provisioned.</span></span> <span data-ttu-id="a875d-121">PDL 還可決定要在哪裡佈建使用者建立的 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="a875d-121">The PDL also determines where SharePoint sites that are created by the user are provisioned.</span></span>
- <span data-ttu-id="a875d-122">**衛星位置** – 在多地理位置租用戶中啟用地理感知 Microsoft 365工作量 (SharePoint、OneDrive和 Exchange) 的地理位置。</span><span class="sxs-lookup"><span data-stu-id="a875d-122">**Satellite location** – The geo locations where the geo-aware Microsoft 365 workloads (SharePoint, OneDrive, and Exchange) are enabled in a multi-geo tenant.</span></span>
- <span data-ttu-id="a875d-123">**租用戶** – 組織在 Microsoft 365 中的呈現方式，通常會有與其相關聯的一個或多個網域 (例如 contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="a875d-123">**Tenant** – An organization's representation in Microsoft 365 which typically has one or more domains associated with it (for example, contoso.com).</span></span>

## <a name="licensing"></a><span data-ttu-id="a875d-124">授權</span><span class="sxs-lookup"><span data-stu-id="a875d-124">Licensing</span></span>

<span data-ttu-id="a875d-125">Microsoft 365 多地理位置可作為以下 Microsoft 365 訂閱方案的附加元件，這些 EA 客戶的租用戶中至少有 250 個 Microsoft 365 基座，其中至少有 5% 使用多地理位置。</span><span class="sxs-lookup"><span data-stu-id="a875d-125">Microsoft 365 Multi-Geo is available as an add-on to the following Microsoft 365 subscription plans for EA customers with a minimum of 250 Microsoft 365 seats in their tenant, and a minimum of 5% of those seats using multi-geo.</span></span> <span data-ttu-id="a875d-126">如需詳細資訊，請連絡您的 Microsoft 帳戶小組。</span><span class="sxs-lookup"><span data-stu-id="a875d-126">Please contact your Microsoft account team for details.</span></span>

- <span data-ttu-id="a875d-127">Microsoft 365 F1、E1、E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="a875d-127">Microsoft 365 F1, E1, E3, or E5</span></span>
- <span data-ttu-id="a875d-128">Exchange Online 方案 1 或方案 2</span><span class="sxs-lookup"><span data-stu-id="a875d-128">Exchange Online Plan 1 or Plan 2</span></span>
- <span data-ttu-id="a875d-129">商務用 OneDrive 方案 1 或方案 2</span><span class="sxs-lookup"><span data-stu-id="a875d-129">OneDrive for Business Plan 1 or Plan 2</span></span>
- <span data-ttu-id="a875d-130">SharePoint Online 方案 1 或方案 2</span><span class="sxs-lookup"><span data-stu-id="a875d-130">SharePoint Online Plan 1 or Plan 2</span></span>

## <a name="microsoft-365-multi-geo-availability"></a><span data-ttu-id="a875d-131">Microsoft 365 多地理位置可用性</span><span class="sxs-lookup"><span data-stu-id="a875d-131">Microsoft 365 Multi-Geo availability</span></span>

<span data-ttu-id="a875d-132">目前在這些地區與國家中提供 Microsoft 365 多地理位置：</span><span class="sxs-lookup"><span data-stu-id="a875d-132">Microsoft 365 Multi-Geo is currently offered in these regions and countries:</span></span>

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

## <a name="getting-started"></a><span data-ttu-id="a875d-133">快速入門</span><span class="sxs-lookup"><span data-stu-id="a875d-133">Getting started</span></span>

<span data-ttu-id="a875d-134">按照這些步驟來開始使用多地理位置：</span><span class="sxs-lookup"><span data-stu-id="a875d-134">Follow these steps to get started with multi-geo:</span></span>

1. <span data-ttu-id="a875d-135">與您的帳戶團隊合作來新增「Microsoft 365 多地理位置功能」__ 服務方案。</span><span class="sxs-lookup"><span data-stu-id="a875d-135">Work with your account team to add the _Multi-Geo Capabilities in Microsoft 365_ service plan.</span></span> <span data-ttu-id="a875d-136">他們會引導您新增所需數量的授權。</span><span class="sxs-lookup"><span data-stu-id="a875d-136">They will guide you to add the number of licenses needed.</span></span> <span data-ttu-id="a875d-137">多地理位置功能可供具有至少 250 個 Microsoft 365 訂閱的 EA 客戶使用。</span><span class="sxs-lookup"><span data-stu-id="a875d-137">Multi-Geo feature is available to EA customers with a minimum of 250 Microsoft 365 subscriptions.</span></span>

   <span data-ttu-id="a875d-138">開始使用 Microsoft 365 多地理位置之前，Microsoft 必須先設定您的 Exchange Online 租用戶，以支援多地理位置。</span><span class="sxs-lookup"><span data-stu-id="a875d-138">Before you can start using Microsoft 365 Multi-Geo, Microsoft needs to configure your Exchange Online tenant for multi-geo support.</span></span> <span data-ttu-id="a875d-139">當您訂購「Microsoft 365 中的多地理位置功能」\*\* 服務方案，並於租用戶中顯示授權之後，將觸發此一次性設定程序。</span><span class="sxs-lookup"><span data-stu-id="a875d-139">This one-time configuration process is triggered after you order the *Multi-Geo Capabilities in Microsoft 365* service plan and the licenses show up in your tenant.</span></span> <span data-ttu-id="a875d-140">套用多地理位置授權之後，您會在 [Microsoft 365 訊息中心](https://support.office.com/article/38FB3333-BFCC-4340-A37B-DEDA509C2093)收到通知，然後就可以開始進行設定並使用 Microsoft 365 多地理位置功能。</span><span class="sxs-lookup"><span data-stu-id="a875d-140">You'll receive notifications in the [Microsoft 365 message center](https://support.office.com/article/38FB3333-BFCC-4340-A37B-DEDA509C2093) once your Multi-Geo licenses are applied and you then may begin configuring and using your Microsoft 365 Multi-Geo capabilities.</span></span>

2. <span data-ttu-id="a875d-141">閱讀[規劃多地理位置環境](plan-for-multi-geo.md)。</span><span class="sxs-lookup"><span data-stu-id="a875d-141">Read [Plan your multi-geo environment](plan-for-multi-geo.md).</span></span>

3. <span data-ttu-id="a875d-142">深入了解[管理多地理位置環境](administering-a-multi-geo-environment.md)與[使用者會遇到的環境](multi-geo-user-experience.md)。</span><span class="sxs-lookup"><span data-stu-id="a875d-142">Learn about [administering a multi-geo environment](administering-a-multi-geo-environment.md) and [how your users will experience the environment](multi-geo-user-experience.md).</span></span>

4. <span data-ttu-id="a875d-143">當您準備好設定 Microsoft 365 多地理位置，請[設定租用戶以支援多地理位置](multi-geo-tenant-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="a875d-143">When you are ready to set up Microsoft 365 Multi-Geo, [configure your tenant for multi-geo](multi-geo-tenant-configuration.md).</span></span>

5. <span data-ttu-id="a875d-144">[設定搜尋](configure-search-for-multi-geo.md)。</span><span class="sxs-lookup"><span data-stu-id="a875d-144">[Set up search](configure-search-for-multi-geo.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a875d-145">請參閱</span><span class="sxs-lookup"><span data-stu-id="a875d-145">See also</span></span>

[<span data-ttu-id="a875d-146">Exchange Online 和 OneDrive 中的多地理位置</span><span class="sxs-lookup"><span data-stu-id="a875d-146">Multi-Geo in Exchange Online and OneDrive</span></span>](https://Aka.ms/GoMultiGeo)

[<span data-ttu-id="a875d-147">OneDrive 和 SharePoint Online 中的多地理位置功能</span><span class="sxs-lookup"><span data-stu-id="a875d-147">Multi-Geo Capabilities in OneDrive and SharePoint Online</span></span>](multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md)

[<span data-ttu-id="a875d-148">Exchange Online 中的多地理位置功能</span><span class="sxs-lookup"><span data-stu-id="a875d-148">Multi-Geo Capabilities in Exchange Online</span></span>](multi-geo-capabilities-in-exchange-online.md)

[<span data-ttu-id="a875d-149">多地理位置環境中的 Teams 體驗</span><span class="sxs-lookup"><span data-stu-id="a875d-149">Teams experience in a multi-geo environment</span></span>](https://docs.microsoft.com/microsoftteams/teams-experience-o365odb-spo-multi-geo)