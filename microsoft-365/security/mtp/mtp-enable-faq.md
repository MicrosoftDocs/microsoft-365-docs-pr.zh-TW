---
title: 開啟 Microsoft 365 Defender 時的常見提問
description: 取得關於啟用 Microsoft 365 Defender 的授權、許可權、初始設定及其他產品及服務的最常見問題的答案。
keywords: 常見問題解答、FAQ、GCC、入門、啟用 MTP、Microsoft 威脅防護、M365、安全性、資料位置、必要許可權、授權資格、設定頁面
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 3dae9f208f5bb08d694322eb9f7cff35986930da
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920487"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-365-defender"></a><span data-ttu-id="e467c-104">開啟 Microsoft 365 Defender 時的常見提問</span><span class="sxs-lookup"><span data-stu-id="e467c-104">Frequently asked questions when turning on Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="e467c-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="e467c-105">**Applies to:**</span></span>
- <span data-ttu-id="e467c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e467c-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="e467c-107">閱讀有關開啟 [Microsoft 365 Defender](microsoft-threat-protection.md)的常見問題解答，包含必要的授權和許可權、部署支援服務，以及初始設定。</span><span class="sxs-lookup"><span data-stu-id="e467c-107">Read responses to the most commonly asked questions about turning on [Microsoft 365 Defender](microsoft-threat-protection.md), including required licenses and permissions, deploying support services, and initial settings.</span></span>

<span data-ttu-id="e467c-108">如需如何開啟服務的指示，請 [參閱開啟 Microsoft 365 Defender](mtp-enable.md)。</span><span class="sxs-lookup"><span data-stu-id="e467c-108">For instructions on how to turn on the service, [read Turn on Microsoft 365 Defender](mtp-enable.md).</span></span>

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-365-defender"></a><span data-ttu-id="e467c-109">我沒有 Microsoft 365 E5 授權。</span><span class="sxs-lookup"><span data-stu-id="e467c-109">I don’t have a Microsoft 365 E5 license.</span></span> <span data-ttu-id="e467c-110">我仍然可以使用 Microsoft 365 Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="e467c-110">Can I still use Microsoft 365 Defender?</span></span>

<span data-ttu-id="e467c-111">具有下列非 E5 授權的客戶可以使用 Microsoft 365 Defender：</span><span class="sxs-lookup"><span data-stu-id="e467c-111">Customers with the following non-E5 licenses can use Microsoft 365 Defender:</span></span>

- <span data-ttu-id="e467c-112">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="e467c-112">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="e467c-113">適用於身分識別的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="e467c-113">Microsoft Defender for Identity</span></span>
- <span data-ttu-id="e467c-114">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="e467c-114">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="e467c-115">適用于 Office 的 Defender 365 (方案 2) </span><span class="sxs-lookup"><span data-stu-id="e467c-115">Defender for Office 365 (Plan 2)</span></span>
 
<span data-ttu-id="e467c-116">如需支援之授權的完整清單，請 [閱讀授權要求](prerequisites.md#licensing-requirements)。</span><span class="sxs-lookup"><span data-stu-id="e467c-116">For a full list of supported licenses, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-365-defender"></a><span data-ttu-id="e467c-117">我需要安裝或部署任何專案，才能開始使用 Microsoft 365 Defender？</span><span class="sxs-lookup"><span data-stu-id="e467c-117">Do I need to install or deploy anything to start using Microsoft 365 Defender?</span></span>

<span data-ttu-id="e467c-118">否，Microsoft 365 Defender 會合並您已部署之 Microsoft 365 安全性服務中的資料。</span><span class="sxs-lookup"><span data-stu-id="e467c-118">No, Microsoft 365 Defender consolidates data from Microsoft 365 security services that you have already deployed.</span></span> <span data-ttu-id="e467c-119">一旦將其開啟，事件、自動化和搜尋體驗便會開始在已部署產品的範圍內運作。</span><span class="sxs-lookup"><span data-stu-id="e467c-119">Once you turn it on, incident, automation, and hunting experiences will start working within the scope of the deployed products.</span></span> <span data-ttu-id="e467c-120">如果這些產品皆未適當部署，Microsoft 365 Defender 將不會顯示任何資料，而且也無法採取任何動作。</span><span class="sxs-lookup"><span data-stu-id="e467c-120">If none of these products are properly deployed, Microsoft 365 Defender will not display any data and is unable to take any action.</span></span>

<span data-ttu-id="e467c-121">若要優化 Microsoft 365 Defender 體驗，建議您部署 *所有* 支援的 [microsoft 365 安全性產品和服務](deploy-supported-services.md)。</span><span class="sxs-lookup"><span data-stu-id="e467c-121">To optimize your Microsoft 365 Defender experiences, we recommend deploying *all* supported [Microsoft 365 security products and services](deploy-supported-services.md).</span></span>

## <a name="where-does-microsoft-365-defender-process-and-store-my-data"></a><span data-ttu-id="e467c-122">Microsoft 365 Defender 處理及儲存資料的位置為何？</span><span class="sxs-lookup"><span data-stu-id="e467c-122">Where does Microsoft 365 Defender process and store my data?</span></span>
<span data-ttu-id="e467c-123">Microsoft 365 Defender 會自動選取資料中心的最佳位置，以進行合併資料的處理和儲存。</span><span class="sxs-lookup"><span data-stu-id="e467c-123">Microsoft 365 Defender automatically selects an optimal location for the data center where consolidated data is processed and stored.</span></span> <span data-ttu-id="e467c-124">如果您有 Microsoft Defender for Endpoint，它會選取用來進行終結點的 Defender 所用的相同位置。</span><span class="sxs-lookup"><span data-stu-id="e467c-124">If you have Microsoft Defender for Endpoint, it selects the same location used by Defender for Endpoint.</span></span>

>[!NOTE]
><span data-ttu-id="e467c-125">Microsoft Defender for Endpoint 會在歐盟 (歐盟透過 Azure Defender 開啟時) 資料中心。</span><span class="sxs-lookup"><span data-stu-id="e467c-125">Microsoft Defender for Endpoint automatically provisions in European Union (EU) data centers when turned on through Azure Defender.</span></span> <span data-ttu-id="e467c-126">Microsoft 365 Defender 會在相同的歐盟資料中心，針對以這種方式布建 Microsoft Defender for Endpoint 的客戶自動布建。</span><span class="sxs-lookup"><span data-stu-id="e467c-126">Microsoft 365 Defender will automatically provision in the same EU data center for customers who have provisioned Microsoft Defender for Endpoint in this manner.</span></span> 

<span data-ttu-id="e467c-127">在 microsoft **365 defender) >** 的 Microsoft 365 Defender (設定] 的 [設定] 頁面中布建服務之前和之後，就會顯示資料中心位置。</span><span class="sxs-lookup"><span data-stu-id="e467c-127">The data center location is shown before and after the service is provisioned in the settings page for Microsoft 365 Defender ( **Settings > Microsoft 365 Defender** ).</span></span> <span data-ttu-id="e467c-128">如果您想要使用另一個資料中心位置，請在 Microsoft 365 的安全性中心選取 [ **需要協助** ]，以與 Microsoft 支援人員聯繫。</span><span class="sxs-lookup"><span data-stu-id="e467c-128">If you prefer to use another data center location, select **Need help?** in the Microsoft 365 security center to contact Microsoft support.</span></span>

## <a name="where-can-i-access-microsoft-365-defender"></a><span data-ttu-id="e467c-129">我可以在哪裡存取 Microsoft 365 Defender？</span><span class="sxs-lookup"><span data-stu-id="e467c-129">Where can I access Microsoft 365 Defender?</span></span>

<span data-ttu-id="e467c-130">Microsoft 365 Defender 可在 Microsoft 365 的 [安全性中心] 中取得。</span><span class="sxs-lookup"><span data-stu-id="e467c-130">Microsoft 365 Defender is available in Microsoft 365 security center.</span></span> <span data-ttu-id="e467c-131">若要移至 [安全性中心]，請流覽至 URL [https://security.microsoft.com](https://security.microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="e467c-131">To go to the security center, browse to the URL [https://security.microsoft.com](https://security.microsoft.com).</span></span>

##  <a name="what-permissions-do-i-need-to-access-microsoft-365-defender-in-microsoft-365-security-center"></a><span data-ttu-id="e467c-132">我需要哪些許可權才能存取 Microsoft 365 security center 中的 Microsoft 365 Defender？</span><span class="sxs-lookup"><span data-stu-id="e467c-132">What permissions do I need to access Microsoft 365 Defender in Microsoft 365 security center?</span></span>

<span data-ttu-id="e467c-133">指派給下列 Azure Active Directory (AD) 角色的帳戶可存取 Microsoft 365 Defender 功能和資料：</span><span class="sxs-lookup"><span data-stu-id="e467c-133">Accounts assigned the following Azure Active Directory (AD) roles can access Microsoft 365 Defender functionality and data:</span></span>

- <span data-ttu-id="e467c-134">全域管理員</span><span class="sxs-lookup"><span data-stu-id="e467c-134">Global administrator</span></span>
- <span data-ttu-id="e467c-135">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="e467c-135">Security administrator</span></span>
- <span data-ttu-id="e467c-136">安全性操作員</span><span class="sxs-lookup"><span data-stu-id="e467c-136">Security Operator</span></span>
- <span data-ttu-id="e467c-137">全域讀取者</span><span class="sxs-lookup"><span data-stu-id="e467c-137">Global Reader</span></span>
- <span data-ttu-id="e467c-138">安全性讀取者</span><span class="sxs-lookup"><span data-stu-id="e467c-138">Security Reader</span></span>

>[!NOTE]
><span data-ttu-id="e467c-139">Microsoft Defender for Endpoint 中以角色為基礎的存取控制設定會影響資料的存取。</span><span class="sxs-lookup"><span data-stu-id="e467c-139">Role-based access control settings in Microsoft Defender for Endpoint influence access to data.</span></span> <span data-ttu-id="e467c-140">如需詳細資訊，請參閱 [管理 Microsoft 365 Defender 的存取](mtp-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="e467c-140">For more information, read about [managing access to Microsoft 365 Defender](mtp-permissions.md).</span></span>

## <a name="what-time-zone-does-microsoft-365-defender-default-to"></a><span data-ttu-id="e467c-141">Microsoft 365 Defender 預設為什麼時區？</span><span class="sxs-lookup"><span data-stu-id="e467c-141">What time zone does Microsoft 365 Defender default to?</span></span>
<span data-ttu-id="e467c-142">Microsoft 365 Defender 預設會在 UTC 時區內顯示時間資訊。</span><span class="sxs-lookup"><span data-stu-id="e467c-142">By default, Microsoft 365 Defender displays time information in the UTC time zone.</span></span> <span data-ttu-id="e467c-143">您可以變更此設定以使用您的本機時區。</span><span class="sxs-lookup"><span data-stu-id="e467c-143">You can change this setting to use your local time zone.</span></span> [<span data-ttu-id="e467c-144">瞭解如何設定時區</span><span class="sxs-lookup"><span data-stu-id="e467c-144">Learn about setting the time zone</span></span>](mtp-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-365-defender-feature-and-ui-updates"></a><span data-ttu-id="e467c-145">如何才能瞭解新的 Microsoft 365 Defender 功能和 UI 更新？</span><span class="sxs-lookup"><span data-stu-id="e467c-145">How can I learn about new Microsoft 365 Defender feature and UI updates?</span></span>

<span data-ttu-id="e467c-146">Microsoft 定期透過各種管道提供資訊，包括：</span><span class="sxs-lookup"><span data-stu-id="e467c-146">Microsoft regularly provides information through the various channels, including:</span></span>

- <span data-ttu-id="e467c-147">Microsoft 365 系統管理中心中的[郵件中心](../../admin/manage/message-center.md)</span><span class="sxs-lookup"><span data-stu-id="e467c-147">The [message center](../../admin/manage/message-center.md) in Microsoft 365 admin center</span></span>
- <span data-ttu-id="e467c-148">[Microsoft 365 security & 合規性技術社區](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)中的 Blogposts</span><span class="sxs-lookup"><span data-stu-id="e467c-148">Blogposts in the [Microsoft 365 security & compliance tech community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span></span>

<span data-ttu-id="e467c-149">開啟 [預覽功能](preview.md)可取得最新的公開體驗。</span><span class="sxs-lookup"><span data-stu-id="e467c-149">Get the latest publicly available experiences by turning on [preview features](preview.md).</span></span>

## <a name="is-microsoft-365-defender-available-for-us-government-community-cloud-gcc-or-gcc-high"></a><span data-ttu-id="e467c-150">Microsoft 365 Defender 可供美國政府社區雲端 (GCC) 或 GCC 高版本？</span><span class="sxs-lookup"><span data-stu-id="e467c-150">Is Microsoft 365 Defender available for US Government Community Cloud (GCC) or GCC High?</span></span>
<span data-ttu-id="e467c-151">目前無法使用。</span><span class="sxs-lookup"><span data-stu-id="e467c-151">At the moment, it is not available.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e467c-152">相關主題</span><span class="sxs-lookup"><span data-stu-id="e467c-152">Related topics</span></span>

- [<span data-ttu-id="e467c-153">Microsoft 365 Defender 概述</span><span class="sxs-lookup"><span data-stu-id="e467c-153">Microsoft 365 Defender overview</span></span>](microsoft-threat-protection.md)
- <span data-ttu-id="e467c-154">[開啟 Microsoft 365 Defender](mtp-enable.md)。</span><span class="sxs-lookup"><span data-stu-id="e467c-154">[Turn on Microsoft 365 Defender](mtp-enable.md).</span></span>
- [<span data-ttu-id="e467c-155">授權需求和其他必要條件</span><span class="sxs-lookup"><span data-stu-id="e467c-155">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="e467c-156">部署支援服務</span><span class="sxs-lookup"><span data-stu-id="e467c-156">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="e467c-157">開啟預覽功能</span><span class="sxs-lookup"><span data-stu-id="e467c-157">Turn on preview features</span></span>](preview.md)
