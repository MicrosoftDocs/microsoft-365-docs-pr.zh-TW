---
title: 在 Microsoft 365 Defender 時開啟常見問題
description: 取得對啟用 Microsoft 365 Defender 相關授權、許可權、初始設定及其他產品及服務的最常見問題的答案。
keywords: 常見問題解答、常見問題、GCC、入門、啟用 Microsoft 365 Defender、Microsoft 365 defender、M365、security、data location、必要許可權、授權資格、設定頁面
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 008e3cc6ee65597a032aa932b74a64ac591927f2
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572762"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-365-defender"></a><span data-ttu-id="e3e37-104">在 Microsoft 365 Defender 時開啟常見問題</span><span class="sxs-lookup"><span data-stu-id="e3e37-104">Frequently asked questions when turning on Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="e3e37-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="e3e37-105">**Applies to:**</span></span>
- <span data-ttu-id="e3e37-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e3e37-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="e3e37-107">閱讀有關開啟[Microsoft 365 Defender](microsoft-365-defender.md)的常見問題解答，包含必要的授權和許可權、部署支援服務，以及初始設定。</span><span class="sxs-lookup"><span data-stu-id="e3e37-107">Read responses to the most commonly asked questions about turning on [Microsoft 365 Defender](microsoft-365-defender.md), including required licenses and permissions, deploying support services, and initial settings.</span></span>

<span data-ttu-id="e3e37-108">如需如何開啟服務的指示，請[參閱開啟 Microsoft 365 Defender](m365d-enable.md)。</span><span class="sxs-lookup"><span data-stu-id="e3e37-108">For instructions on how to turn on the service, [read Turn on Microsoft 365 Defender](m365d-enable.md).</span></span>

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-365-defender"></a><span data-ttu-id="e3e37-109">我沒有 Microsoft 365 E5 授權。</span><span class="sxs-lookup"><span data-stu-id="e3e37-109">I don’t have a Microsoft 365 E5 license.</span></span> <span data-ttu-id="e3e37-110">我仍然可以使用 Microsoft 365 Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="e3e37-110">Can I still use Microsoft 365 Defender?</span></span>

<span data-ttu-id="e3e37-111">具有下列非 E5 授權的客戶可以使用 Microsoft 365 Defender：</span><span class="sxs-lookup"><span data-stu-id="e3e37-111">Customers with the following non-E5 licenses can use Microsoft 365 Defender:</span></span>

- <span data-ttu-id="e3e37-112">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="e3e37-112">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="e3e37-113">適用於身分識別的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="e3e37-113">Microsoft Defender for Identity</span></span>
- <span data-ttu-id="e3e37-114">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="e3e37-114">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="e3e37-115">適用於 Office 365 的 Defender (方案 2)</span><span class="sxs-lookup"><span data-stu-id="e3e37-115">Defender for Office 365 (Plan 2)</span></span>
 
<span data-ttu-id="e3e37-116">如需支援之授權的完整清單，請 [閱讀授權要求](prerequisites.md#licensing-requirements)。</span><span class="sxs-lookup"><span data-stu-id="e3e37-116">For a full list of supported licenses, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-365-defender"></a><span data-ttu-id="e3e37-117">我需要使用 Microsoft 365 Defender 安裝或部署任何專案？</span><span class="sxs-lookup"><span data-stu-id="e3e37-117">Do I need to install or deploy anything to start using Microsoft 365 Defender?</span></span>

<span data-ttu-id="e3e37-118">否，Microsoft 365 Defender 會合並您已部署 Microsoft 365 安全服務中的資料。</span><span class="sxs-lookup"><span data-stu-id="e3e37-118">No, Microsoft 365 Defender consolidates data from Microsoft 365 security services that you have already deployed.</span></span> <span data-ttu-id="e3e37-119">一旦將其開啟，事件、自動化和搜尋體驗便會開始在已部署產品的範圍內運作。</span><span class="sxs-lookup"><span data-stu-id="e3e37-119">Once you turn it on, incident, automation, and hunting experiences will start working within the scope of the deployed products.</span></span> <span data-ttu-id="e3e37-120">如果這些產品皆未適當部署，Microsoft 365 Defender 將不會顯示任何資料，而且也無法採取任何動作。</span><span class="sxs-lookup"><span data-stu-id="e3e37-120">If none of these products are properly deployed, Microsoft 365 Defender will not display any data and is unable to take any action.</span></span>

<span data-ttu-id="e3e37-121">為了優化 Microsoft 365 的 Defender 體驗，我們建議您部署 *所有* 支援的 [Microsoft 365 安全產品和服務](deploy-supported-services.md)。</span><span class="sxs-lookup"><span data-stu-id="e3e37-121">To optimize your Microsoft 365 Defender experiences, we recommend deploying *all* supported [Microsoft 365 security products and services](deploy-supported-services.md).</span></span>

## <a name="where-does-microsoft-365-defender-process-and-store-my-data"></a><span data-ttu-id="e3e37-122">Microsoft 365 Defender 處理及儲存資料的位置為何？</span><span class="sxs-lookup"><span data-stu-id="e3e37-122">Where does Microsoft 365 Defender process and store my data?</span></span>
<span data-ttu-id="e3e37-123">Microsoft 365Defender 會自動選取資料中心的最佳位置，以進行合併資料的處理和儲存。</span><span class="sxs-lookup"><span data-stu-id="e3e37-123">Microsoft 365 Defender automatically selects an optimal location for the data center where consolidated data is processed and stored.</span></span> <span data-ttu-id="e3e37-124">如果您有 Microsoft Defender for Endpoint，它會選取用來進行終結點的 Defender 所用的相同位置。</span><span class="sxs-lookup"><span data-stu-id="e3e37-124">If you have Microsoft Defender for Endpoint, it selects the same location used by Defender for Endpoint.</span></span>

>[!NOTE]
><span data-ttu-id="e3e37-125">Microsoft Defender for Endpoint 會在歐盟 (歐盟透過 Azure Defender 開啟時) 資料中心。</span><span class="sxs-lookup"><span data-stu-id="e3e37-125">Microsoft Defender for Endpoint automatically provisions in European Union (EU) data centers when turned on through Azure Defender.</span></span> <span data-ttu-id="e3e37-126">Microsoft 365您可以在相同的歐盟資料中心，針對以這種方式布建 Microsoft Defender for Endpoint 的客戶自動布建。</span><span class="sxs-lookup"><span data-stu-id="e3e37-126">Microsoft 365 Defender will automatically provision in the same EU data center for customers who have provisioned Microsoft Defender for Endpoint in this manner.</span></span> 

<span data-ttu-id="e3e37-127">在 [Microsoft 365 defender (**設定 > Microsoft 365 Defender**) ] 的 [設定] 頁面中布建服務之前及之後都會顯示資料中心位置。</span><span class="sxs-lookup"><span data-stu-id="e3e37-127">The data center location is shown before and after the service is provisioned in the settings page for Microsoft 365 Defender (**Settings > Microsoft 365 Defender**).</span></span> <span data-ttu-id="e3e37-128">如果您想要使用另一個資料中心位置，請在 Microsoft 365 的安全性中心選取 [**需要協助**]，以聯繫 Microsoft 支援部門。</span><span class="sxs-lookup"><span data-stu-id="e3e37-128">If you prefer to use another data center location, select **Need help?** in the Microsoft 365 security center to contact Microsoft support.</span></span>

## <a name="where-can-i-access-microsoft-365-defender"></a><span data-ttu-id="e3e37-129">我可以在哪裡存取 Microsoft 365 Defender？</span><span class="sxs-lookup"><span data-stu-id="e3e37-129">Where can I access Microsoft 365 Defender?</span></span>

<span data-ttu-id="e3e37-130">Microsoft 365您可以在 Microsoft 365 的安全性中心使用 Defender。</span><span class="sxs-lookup"><span data-stu-id="e3e37-130">Microsoft 365 Defender is available in Microsoft 365 security center.</span></span> <span data-ttu-id="e3e37-131">若要移至 [安全性中心]，請流覽至 URL [https://security.microsoft.com](https://security.microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="e3e37-131">To go to the security center, browse to the URL [https://security.microsoft.com](https://security.microsoft.com).</span></span>

##  <a name="what-permissions-do-i-need-to-access-microsoft-365-defender-in-microsoft-365-security-center"></a><span data-ttu-id="e3e37-132">在 Microsoft 365 安全中心存取 Microsoft 365 Defender 時，需要哪些許可權？</span><span class="sxs-lookup"><span data-stu-id="e3e37-132">What permissions do I need to access Microsoft 365 Defender in Microsoft 365 security center?</span></span>

<span data-ttu-id="e3e37-133">已指派下列 Azure Active Directory 的帳戶 (Azure AD) 角色可以存取 Microsoft 365 的 Defender 功能和資料：</span><span class="sxs-lookup"><span data-stu-id="e3e37-133">Accounts assigned the following Azure Active Directory (Azure AD) roles can access Microsoft 365 Defender functionality and data:</span></span>

- <span data-ttu-id="e3e37-134">全域管理員</span><span class="sxs-lookup"><span data-stu-id="e3e37-134">Global administrator</span></span>
- <span data-ttu-id="e3e37-135">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="e3e37-135">Security administrator</span></span>
- <span data-ttu-id="e3e37-136">安全性操作員</span><span class="sxs-lookup"><span data-stu-id="e3e37-136">Security Operator</span></span>
- <span data-ttu-id="e3e37-137">全域讀取者</span><span class="sxs-lookup"><span data-stu-id="e3e37-137">Global Reader</span></span>
- <span data-ttu-id="e3e37-138">安全性讀取者</span><span class="sxs-lookup"><span data-stu-id="e3e37-138">Security Reader</span></span>

>[!NOTE]
><span data-ttu-id="e3e37-139">Microsoft Defender for Endpoint 中以角色為基礎的存取控制設定會影響資料的存取。</span><span class="sxs-lookup"><span data-stu-id="e3e37-139">Role-based access control settings in Microsoft Defender for Endpoint influence access to data.</span></span> <span data-ttu-id="e3e37-140">如需詳細資訊，請參閱[管理 Microsoft 365 Defender 的存取](m365d-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="e3e37-140">For more information, read about [managing access to Microsoft 365 Defender](m365d-permissions.md).</span></span>

## <a name="what-time-zone-does-microsoft-365-defender-default-to"></a><span data-ttu-id="e3e37-141">Microsoft 365 Defender 預設值是哪一個時區？</span><span class="sxs-lookup"><span data-stu-id="e3e37-141">What time zone does Microsoft 365 Defender default to?</span></span>
<span data-ttu-id="e3e37-142">根據預設，Microsoft 365 Defender 會在 UTC 時區內顯示時間資訊。</span><span class="sxs-lookup"><span data-stu-id="e3e37-142">By default, Microsoft 365 Defender displays time information in the UTC time zone.</span></span> <span data-ttu-id="e3e37-143">您可以變更此設定以使用您的本機時區。</span><span class="sxs-lookup"><span data-stu-id="e3e37-143">You can change this setting to use your local time zone.</span></span> [<span data-ttu-id="e3e37-144">瞭解如何設定時區</span><span class="sxs-lookup"><span data-stu-id="e3e37-144">Learn about setting the time zone</span></span>](m365d-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-365-defender-feature-and-ui-updates"></a><span data-ttu-id="e3e37-145">如何瞭解如何進行新 Microsoft 365 Defender 功能和 UI 更新？</span><span class="sxs-lookup"><span data-stu-id="e3e37-145">How can I learn about new Microsoft 365 Defender feature and UI updates?</span></span>

<span data-ttu-id="e3e37-146">Microsoft 定期透過各種管道提供資訊，包括：</span><span class="sxs-lookup"><span data-stu-id="e3e37-146">Microsoft regularly provides information through the various channels, including:</span></span>

- <span data-ttu-id="e3e37-147">Microsoft 365 系統管理中心的[郵件中心](../../admin/manage/message-center.md)</span><span class="sxs-lookup"><span data-stu-id="e3e37-147">The [message center](../../admin/manage/message-center.md) in Microsoft 365 admin center</span></span>
- <span data-ttu-id="e3e37-148">[Microsoft 365 security & 規範技術社區](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)中的 Blogposts</span><span class="sxs-lookup"><span data-stu-id="e3e37-148">Blogposts in the [Microsoft 365 security & compliance tech community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span></span>

<span data-ttu-id="e3e37-149">開啟 [預覽功能](preview.md)可取得最新的公開體驗。</span><span class="sxs-lookup"><span data-stu-id="e3e37-149">Get the latest publicly available experiences by turning on [preview features](preview.md).</span></span>

## <a name="is-microsoft-365-defender-available-for-us-government-community-cloud-gcc-or-gcc-high"></a><span data-ttu-id="e3e37-150">Microsoft 365 Defender 是否可供我們政府社群雲端 (GCC) 或 GCC 高？</span><span class="sxs-lookup"><span data-stu-id="e3e37-150">Is Microsoft 365 Defender available for US Government Community Cloud (GCC) or GCC High?</span></span>
<span data-ttu-id="e3e37-151">目前無法使用。</span><span class="sxs-lookup"><span data-stu-id="e3e37-151">At the moment, it is not available.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e3e37-152">相關主題</span><span class="sxs-lookup"><span data-stu-id="e3e37-152">Related topics</span></span>

- [<span data-ttu-id="e3e37-153">Microsoft 365Defender 概述</span><span class="sxs-lookup"><span data-stu-id="e3e37-153">Microsoft 365 Defender overview</span></span>](microsoft-365-defender.md)
- <span data-ttu-id="e3e37-154">[開啟 Microsoft 365 Defender](m365d-enable.md)。</span><span class="sxs-lookup"><span data-stu-id="e3e37-154">[Turn on Microsoft 365 Defender](m365d-enable.md).</span></span>
- [<span data-ttu-id="e3e37-155">授權需求和其他必要條件</span><span class="sxs-lookup"><span data-stu-id="e3e37-155">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="e3e37-156">部署支援服務</span><span class="sxs-lookup"><span data-stu-id="e3e37-156">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="e3e37-157">開啟預覽功能</span><span class="sxs-lookup"><span data-stu-id="e3e37-157">Turn on preview features</span></span>](preview.md)
