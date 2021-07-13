---
title: Microsoft 365 Lighthouse裝置合規性頁面概述
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: 針對受管理的服務提供者 (MSPs) 使用 Microsoft 365 Lighthouse，請深入瞭解裝置符合性頁面。
ms.openlocfilehash: 3568f5b362df86955a1ea6ce15928658c854a584
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "53395034"
---
# <a name="microsoft-365-lighthouse-device-compliance-page-overview"></a><span data-ttu-id="29800-103">Microsoft 365 Lighthouse裝置合規性頁面概述</span><span class="sxs-lookup"><span data-stu-id="29800-103">Microsoft 365 Lighthouse Device compliance page overview</span></span>

> [!NOTE]
> <span data-ttu-id="29800-104">本文所述的功能都是在預覽中進行變更，而且只有符合 [需求](m365-lighthouse-requirements.md)的合作夥伴才能使用。</span><span class="sxs-lookup"><span data-stu-id="29800-104">The features described in this article are in Preview, are subject to change, and are only available to partners who meet the [requirements](m365-lighthouse-requirements.md).</span></span> <span data-ttu-id="29800-105">如果您的組織沒有 Microsoft 365 Lighthouse，請參閱[註冊 Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md)。</span><span class="sxs-lookup"><span data-stu-id="29800-105">If your organization does not have Microsoft 365 Lighthouse, see [Sign up for Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md).</span></span>

<span data-ttu-id="29800-106">Microsoft 365 Lighthouse 可讓您透過選取左導覽窗格中的 [**裝置**]，以開啟 [裝置符合性] 頁面，以查看所有租使用者的相關資訊與 Intune 裝置相容性。</span><span class="sxs-lookup"><span data-stu-id="29800-106">Microsoft 365 Lighthouse lets you view insights and information related to Intune device compliance for all your tenants by selecting **Devices** in the left navigation pane to open the Device compliance page.</span></span> <span data-ttu-id="29800-107">在此頁面中，您可以瞭解承租人的相容性狀態、查看每個租使用者的裝置清單，以及取得相容性原則及設定的狀態報表。</span><span class="sxs-lookup"><span data-stu-id="29800-107">From this page, you can get an overview of compliance status across tenants, view a list of devices for each tenant, and get status reports on compliance policies and settings.</span></span>

## <a name="overview-tab"></a><span data-ttu-id="29800-108">概覽] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="29800-108">Overview tab</span></span>  
  
<span data-ttu-id="29800-109">在 [一覽] 索引標籤上，您可以在租使用者中查看裝置符合性狀態、查看每月裝置的相容性趨勢，以及追蹤裝置是否有指派符合性原則。</span><span class="sxs-lookup"><span data-stu-id="29800-109">On the Overview tab, you can view device compliance status across your tenants, see monthly device compliance trends, and track whether devices have compliance policies assigned to them.</span></span> <span data-ttu-id="29800-110">您也可以根據條件式存取原則，查看有關租使用者裝置合規性動作和需求的資訊。</span><span class="sxs-lookup"><span data-stu-id="29800-110">You can also view information on tenant device compliance actions and requirements based on Conditional Access policies.</span></span>

:::image type="content" source="../media/m365-lighthouse-device-compliance-page-overview/device-overview-tab.png" alt-text="[一覽] 索引標籤的螢幕擷取畫面。":::

## <a name="devices-tab"></a><span data-ttu-id="29800-112">裝置] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="29800-112">Devices tab</span></span>

<span data-ttu-id="29800-113">在 [裝置] 索引標籤上，您可以查看所有承租人裝置的清單，並根據下列符合性狀態篩選清單：相容性、不相容性、寬限期和未評估。</span><span class="sxs-lookup"><span data-stu-id="29800-113">On the Devices tab, you can view a list of all tenant devices and filter the list based on the following compliance statuses: Compliant, Non-compliant, In Grace period, and Not evaluated.</span></span> <span data-ttu-id="29800-114">如需不同規範狀態的詳細資訊，請參閱 [監視 Intune 裝置合規性原則](/mem/intune/protect/compliance-policy-monitor)。</span><span class="sxs-lookup"><span data-stu-id="29800-114">For more information about the different compliance statuses, see [Monitor Intune Device compliance policies](/mem/intune/protect/compliance-policy-monitor).</span></span>

<span data-ttu-id="29800-115">選取 [任何裝置]，以查看有關裝置為何處於其目前符合性狀態的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="29800-115">Select any device to view more information on why the device is in its current compliance state.</span></span> <span data-ttu-id="29800-116">如果您需要在裝置上採取動作，有一個可在 Microsoft 端點管理員中查看裝置的選項。</span><span class="sxs-lookup"><span data-stu-id="29800-116">If you need to take action on the device, there's an option to view the device in Microsoft Endpoint Manager.</span></span>

:::image type="content" source="../media/m365-lighthouse-device-compliance-page-overview/devices-device-tab.png" alt-text="[裝置] 索引標籤的螢幕擷取畫面。":::

## <a name="policies-tab"></a><span data-ttu-id="29800-118">原則] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="29800-118">Policies tab</span></span>

<span data-ttu-id="29800-119">在 [原則] 索引標籤上，您可以透過您的承租人查看規範原則，並使用工具列上的 [比較] 功能，比較相同平臺類型的兩個或三個原則。</span><span class="sxs-lookup"><span data-stu-id="29800-119">On the Policies tab, you can view compliance policies across your tenants and compare two or three policies of the same platform type by using the Compare feature on the toolbar.</span></span> <span data-ttu-id="29800-120">您也可以選取任何原則，以查看詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="29800-120">You can also select any policy to view more information.</span></span>

:::image type="content" source="../media/m365-lighthouse-device-compliance-page-overview/devices-policies-tab.png" alt-text="[原則] 索引標籤的螢幕擷取畫面。":::

## <a name="settings-tab"></a><span data-ttu-id="29800-122">設定] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="29800-122">Settings tab</span></span>

<span data-ttu-id="29800-123">[設定] 索引標籤提供不同承租人裝置中不相容設定的匯總報告。</span><span class="sxs-lookup"><span data-stu-id="29800-123">The settings tab provides an aggregated report of non-compliant settings across tenant devices.</span></span> <span data-ttu-id="29800-124">選取任何報告列以查看詳細資訊，包括不相容裝置所屬的承租人。</span><span class="sxs-lookup"><span data-stu-id="29800-124">Select any of the report rows to view more information, including which tenants the non-compliant devices belong to.</span></span>

:::image type="content" source="../media/m365-lighthouse-device-compliance-page-overview/device-settings-tab.png" alt-text="設定] 索引標籤的螢幕擷取畫面。":::

## <a name="related-content"></a><span data-ttu-id="29800-126">相關內容</span><span class="sxs-lookup"><span data-stu-id="29800-126">Related content</span></span>

<span data-ttu-id="29800-127">[Microsoft 365 Lighthouse 使用者] 頁面概述](m365-lighthouse-users-page-overview.md) (文章) </span><span class="sxs-lookup"><span data-stu-id="29800-127">[Microsoft 365 Lighthouse Users page overview](m365-lighthouse-users-page-overview.md) (article)</span></span>\
<span data-ttu-id="29800-128">[Microsoft 365 Lighthouse 常見問題](m365-lighthouse-faq.yml) (文章) </span><span class="sxs-lookup"><span data-stu-id="29800-128">[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (article)</span></span>
