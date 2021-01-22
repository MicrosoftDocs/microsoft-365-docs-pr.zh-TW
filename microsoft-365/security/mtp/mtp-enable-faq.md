---
title: 開啟 Microsoft 365 Defender 時常見問題
description: 取得授權、許可權、初始設定，以及其他與啟用 Microsoft 365 Defender 相關產品和服務的常見問題解答
keywords: 常見問題， 常見問題， GCC， 快速入門， 啟用 MTP， Microsoft Threat Protection， M365， 安全性， 資料位置， 必要的許可權， 授權資格， 設定頁面
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 2cb9aed070959644e3660188835386118d5f4d9b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930183"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-365-defender"></a><span data-ttu-id="64fb4-104">開啟 Microsoft 365 Defender 時常見問題</span><span class="sxs-lookup"><span data-stu-id="64fb4-104">Frequently asked questions when turning on Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="64fb4-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="64fb4-105">**Applies to:**</span></span>
- <span data-ttu-id="64fb4-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="64fb4-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="64fb4-107">閱讀有關開啟 [Microsoft 365 Defender](microsoft-threat-protection.md)的最常見問題的回復，包括必要的授權與許可權、部署支援服務，以及初始設定。</span><span class="sxs-lookup"><span data-stu-id="64fb4-107">Read responses to the most commonly asked questions about turning on [Microsoft 365 Defender](microsoft-threat-protection.md), including required licenses and permissions, deploying support services, and initial settings.</span></span>

<span data-ttu-id="64fb4-108">有關如何開啟服務的指示，請參閱開啟 Microsoft [365 Defender。](mtp-enable.md)</span><span class="sxs-lookup"><span data-stu-id="64fb4-108">For instructions on how to turn on the service, [read Turn on Microsoft 365 Defender](mtp-enable.md).</span></span>

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-365-defender"></a><span data-ttu-id="64fb4-109">我沒有 Microsoft 365 E5 授權。</span><span class="sxs-lookup"><span data-stu-id="64fb4-109">I don’t have a Microsoft 365 E5 license.</span></span> <span data-ttu-id="64fb4-110">我是否仍可以使用 Microsoft 365 Defender？</span><span class="sxs-lookup"><span data-stu-id="64fb4-110">Can I still use Microsoft 365 Defender?</span></span>

<span data-ttu-id="64fb4-111">擁有下列非 E5 授權的客戶可以使用 Microsoft 365 Defender：</span><span class="sxs-lookup"><span data-stu-id="64fb4-111">Customers with the following non-E5 licenses can use Microsoft 365 Defender:</span></span>

- <span data-ttu-id="64fb4-112">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="64fb4-112">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="64fb4-113">適用於身分識別的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="64fb4-113">Microsoft Defender for Identity</span></span>
- <span data-ttu-id="64fb4-114">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="64fb4-114">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="64fb4-115">Office 365 方案 2 (的後) </span><span class="sxs-lookup"><span data-stu-id="64fb4-115">Defender for Office 365 (Plan 2)</span></span>
 
<span data-ttu-id="64fb4-116">有關支援授權的完整清單， [請閱讀授權需求](prerequisites.md#licensing-requirements)。</span><span class="sxs-lookup"><span data-stu-id="64fb4-116">For a full list of supported licenses, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-365-defender"></a><span data-ttu-id="64fb4-117">我是否需要安裝或部署任何專案，以開始使用 Microsoft 365 Defender？</span><span class="sxs-lookup"><span data-stu-id="64fb4-117">Do I need to install or deploy anything to start using Microsoft 365 Defender?</span></span>

<span data-ttu-id="64fb4-118">否，Microsoft 365 Defender 會合並您部署之 Microsoft 365 安全性服務的資料。</span><span class="sxs-lookup"><span data-stu-id="64fb4-118">No, Microsoft 365 Defender consolidates data from Microsoft 365 security services that you have already deployed.</span></span> <span data-ttu-id="64fb4-119">開啟之後，事件、自動化和尋找體驗就會在部署的產品範圍內開始工作。</span><span class="sxs-lookup"><span data-stu-id="64fb4-119">Once you turn it on, incident, automation, and hunting experiences will start working within the scope of the deployed products.</span></span> <span data-ttu-id="64fb4-120">如果這些產品未正確部署，Microsoft 365 Defender 將不會顯示任何資料，且無法執行任何動作。</span><span class="sxs-lookup"><span data-stu-id="64fb4-120">If none of these products are properly deployed, Microsoft 365 Defender will not display any data and is unable to take any action.</span></span>

<span data-ttu-id="64fb4-121">若要優化您的 Microsoft 365 Defender 體驗，建議您部署所有支援的[Microsoft 365 安全性產品和服務](deploy-supported-services.md)。</span><span class="sxs-lookup"><span data-stu-id="64fb4-121">To optimize your Microsoft 365 Defender experiences, we recommend deploying *all* supported [Microsoft 365 security products and services](deploy-supported-services.md).</span></span>

## <a name="where-does-microsoft-365-defender-process-and-store-my-data"></a><span data-ttu-id="64fb4-122">Microsoft 365 Defender 會處理和儲存我的資料在哪裡？</span><span class="sxs-lookup"><span data-stu-id="64fb4-122">Where does Microsoft 365 Defender process and store my data?</span></span>
<span data-ttu-id="64fb4-123">Microsoft 365 Defender 會自動為處理及儲存合併資料的資料中心選取最佳位置。</span><span class="sxs-lookup"><span data-stu-id="64fb4-123">Microsoft 365 Defender automatically selects an optimal location for the data center where consolidated data is processed and stored.</span></span> <span data-ttu-id="64fb4-124">如果您有 Microsoft Defender for Endpoint，它會選取由 Defender for Endpoint 使用的相同位置。</span><span class="sxs-lookup"><span data-stu-id="64fb4-124">If you have Microsoft Defender for Endpoint, it selects the same location used by Defender for Endpoint.</span></span>

>[!NOTE]
><span data-ttu-id="64fb4-125">透過 Azure Defender 開啟時，Microsoft Defender for Endpoint (歐盟) 資料中心自動提供。</span><span class="sxs-lookup"><span data-stu-id="64fb4-125">Microsoft Defender for Endpoint automatically provisions in European Union (EU) data centers when turned on through Azure Defender.</span></span> <span data-ttu-id="64fb4-126">Microsoft 365 Defender 將針對以這種方式提供 Microsoft Defender for Endpoint 的客戶，自動在同一個歐盟資料中心進行提供。</span><span class="sxs-lookup"><span data-stu-id="64fb4-126">Microsoft 365 Defender will automatically provision in the same EU data center for customers who have provisioned Microsoft Defender for Endpoint in this manner.</span></span> 

<span data-ttu-id="64fb4-127">在 Microsoft 365 Defender 的設定頁面提供 Microsoft 365 Defender (設定> **Microsoft 365 Defender**) 之前和之後，會顯示資料中心位置。</span><span class="sxs-lookup"><span data-stu-id="64fb4-127">The data center location is shown before and after the service is provisioned in the settings page for Microsoft 365 Defender (**Settings > Microsoft 365 Defender**).</span></span> <span data-ttu-id="64fb4-128">如果您想要使用另一個資料中心位置，請在 Microsoft  365 安全性中心中選取需要協助嗎？以與 Microsoft 支援服務聯繫。</span><span class="sxs-lookup"><span data-stu-id="64fb4-128">If you prefer to use another data center location, select **Need help?** in the Microsoft 365 security center to contact Microsoft support.</span></span>

## <a name="where-can-i-access-microsoft-365-defender"></a><span data-ttu-id="64fb4-129">我可以在哪裡存取 Microsoft 365 Defender？</span><span class="sxs-lookup"><span data-stu-id="64fb4-129">Where can I access Microsoft 365 Defender?</span></span>

<span data-ttu-id="64fb4-130">Microsoft 365 資訊安全中心提供 Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="64fb4-130">Microsoft 365 Defender is available in Microsoft 365 security center.</span></span> <span data-ttu-id="64fb4-131">若要前往資訊安全中心，請流覽至 [https://security.microsoft.com](https://security.microsoft.com) URL。</span><span class="sxs-lookup"><span data-stu-id="64fb4-131">To go to the security center, browse to the URL [https://security.microsoft.com](https://security.microsoft.com).</span></span>

##  <a name="what-permissions-do-i-need-to-access-microsoft-365-defender-in-microsoft-365-security-center"></a><span data-ttu-id="64fb4-132">我需要哪些許可權才能存取 Microsoft 365 資訊安全中心的 Microsoft 365 Defender？</span><span class="sxs-lookup"><span data-stu-id="64fb4-132">What permissions do I need to access Microsoft 365 Defender in Microsoft 365 security center?</span></span>

<span data-ttu-id="64fb4-133">指派有下列 Azure Active Directory 帳戶 (AD) 角色可以存取 Microsoft 365 Defender 功能和資料：</span><span class="sxs-lookup"><span data-stu-id="64fb4-133">Accounts assigned the following Azure Active Directory (AD) roles can access Microsoft 365 Defender functionality and data:</span></span>

- <span data-ttu-id="64fb4-134">全域管理員</span><span class="sxs-lookup"><span data-stu-id="64fb4-134">Global administrator</span></span>
- <span data-ttu-id="64fb4-135">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="64fb4-135">Security administrator</span></span>
- <span data-ttu-id="64fb4-136">安全性操作員</span><span class="sxs-lookup"><span data-stu-id="64fb4-136">Security Operator</span></span>
- <span data-ttu-id="64fb4-137">全域讀取者</span><span class="sxs-lookup"><span data-stu-id="64fb4-137">Global Reader</span></span>
- <span data-ttu-id="64fb4-138">安全性讀取者</span><span class="sxs-lookup"><span data-stu-id="64fb4-138">Security Reader</span></span>

>[!NOTE]
><span data-ttu-id="64fb4-139">Microsoft Defender for Endpoint 中的角色型存取控制設定會影響資料的存取。</span><span class="sxs-lookup"><span data-stu-id="64fb4-139">Role-based access control settings in Microsoft Defender for Endpoint influence access to data.</span></span> <span data-ttu-id="64fb4-140">詳細資訊請參閱管理 Microsoft [365 Defender](mtp-permissions.md)存取權。</span><span class="sxs-lookup"><span data-stu-id="64fb4-140">For more information, read about [managing access to Microsoft 365 Defender](mtp-permissions.md).</span></span>

## <a name="what-time-zone-does-microsoft-365-defender-default-to"></a><span data-ttu-id="64fb4-141">Microsoft 365 Defender 預設為什麼時區？</span><span class="sxs-lookup"><span data-stu-id="64fb4-141">What time zone does Microsoft 365 Defender default to?</span></span>
<span data-ttu-id="64fb4-142">根據預設，Microsoft 365 Defender 會以 UTC 時區顯示時間資訊。</span><span class="sxs-lookup"><span data-stu-id="64fb4-142">By default, Microsoft 365 Defender displays time information in the UTC time zone.</span></span> <span data-ttu-id="64fb4-143">您可以將此設定變更為使用您的當地時區。</span><span class="sxs-lookup"><span data-stu-id="64fb4-143">You can change this setting to use your local time zone.</span></span> [<span data-ttu-id="64fb4-144">瞭解如何設定時區</span><span class="sxs-lookup"><span data-stu-id="64fb4-144">Learn about setting the time zone</span></span>](mtp-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-365-defender-feature-and-ui-updates"></a><span data-ttu-id="64fb4-145">如何瞭解新的 Microsoft 365 Defender 功能與 UI 更新？</span><span class="sxs-lookup"><span data-stu-id="64fb4-145">How can I learn about new Microsoft 365 Defender feature and UI updates?</span></span>

<span data-ttu-id="64fb4-146">Microsoft 會定期透過各種通道提供資訊，包括：</span><span class="sxs-lookup"><span data-stu-id="64fb4-146">Microsoft regularly provides information through the various channels, including:</span></span>

- <span data-ttu-id="64fb4-147">Microsoft [](../../admin/manage/message-center.md) 365 系統管理中心的訊息中心</span><span class="sxs-lookup"><span data-stu-id="64fb4-147">The [message center](../../admin/manage/message-center.md) in Microsoft 365 admin center</span></span>
- <span data-ttu-id="64fb4-148">[Microsoft 365 安全性與&技術社群中的部落格文章](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span><span class="sxs-lookup"><span data-stu-id="64fb4-148">Blogposts in the [Microsoft 365 security & compliance tech community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span></span>

<span data-ttu-id="64fb4-149">開啟預覽功能，以取得最新的 [公開體驗](preview.md)。</span><span class="sxs-lookup"><span data-stu-id="64fb4-149">Get the latest publicly available experiences by turning on [preview features](preview.md).</span></span>

## <a name="is-microsoft-365-defender-available-for-us-government-community-cloud-gcc-or-gcc-high"></a><span data-ttu-id="64fb4-150">Microsoft 365 Defender 是否適用于美國政府社群雲端服務 (GCC) GCC High？</span><span class="sxs-lookup"><span data-stu-id="64fb4-150">Is Microsoft 365 Defender available for US Government Community Cloud (GCC) or GCC High?</span></span>
<span data-ttu-id="64fb4-151">目前無法使用。</span><span class="sxs-lookup"><span data-stu-id="64fb4-151">At the moment, it is not available.</span></span>

## <a name="related-topics"></a><span data-ttu-id="64fb4-152">相關主題</span><span class="sxs-lookup"><span data-stu-id="64fb4-152">Related topics</span></span>

- [<span data-ttu-id="64fb4-153">Microsoft 365 Defender 概觀</span><span class="sxs-lookup"><span data-stu-id="64fb4-153">Microsoft 365 Defender overview</span></span>](microsoft-threat-protection.md)
- <span data-ttu-id="64fb4-154">[開啟 Microsoft 365 Defender。](mtp-enable.md)</span><span class="sxs-lookup"><span data-stu-id="64fb4-154">[Turn on Microsoft 365 Defender](mtp-enable.md).</span></span>
- [<span data-ttu-id="64fb4-155">授權需求和其他必要條件</span><span class="sxs-lookup"><span data-stu-id="64fb4-155">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="64fb4-156">部署支援服務</span><span class="sxs-lookup"><span data-stu-id="64fb4-156">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="64fb4-157">開啟預覽功能</span><span class="sxs-lookup"><span data-stu-id="64fb4-157">Turn on preview features</span></span>](preview.md)
