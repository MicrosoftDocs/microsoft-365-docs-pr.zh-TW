---
title: 部署 Microsoft 365 Lighthouse 基線
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
description: 針對受管理的服務提供者 (MSPs) 使用 Microsoft 365 Lighthouse，瞭解如何部署 Microsoft 365 Lighthouse 的比較基準。
ms.openlocfilehash: 0bda7edec2a200e51e734db64e2b703a027e57bb
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "53395077"
---
# <a name="deploy-microsoft-365-lighthouse-baselines"></a><span data-ttu-id="4455f-103">部署 Microsoft 365 Lighthouse 基線</span><span class="sxs-lookup"><span data-stu-id="4455f-103">Deploy Microsoft 365 Lighthouse baselines</span></span> 

> [!NOTE]
> <span data-ttu-id="4455f-104">本文所述的功能都是在預覽中進行變更，而且只有符合 [需求](m365-lighthouse-requirements.md)的合作夥伴才能使用。</span><span class="sxs-lookup"><span data-stu-id="4455f-104">The features described in this article are in Preview, are subject to change, and are only available to partners who meet the [requirements](m365-lighthouse-requirements.md).</span></span> <span data-ttu-id="4455f-105">如果您的組織沒有 Microsoft 365 Lighthouse，請參閱[註冊 Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md)。</span><span class="sxs-lookup"><span data-stu-id="4455f-105">If your organization does not have Microsoft 365 Lighthouse, see [Sign up for Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md).</span></span>

<span data-ttu-id="4455f-106">Microsoft 365 Lighthouse 基準可讓您部署標準的受管理租使用者設定，以保護租使用者使用者、裝置和資料。</span><span class="sxs-lookup"><span data-stu-id="4455f-106">Microsoft 365 Lighthouse baselines let you deploy standard managed tenant configurations to secure tenant users, devices, and data.</span></span> <span data-ttu-id="4455f-107">Microsoft 365 Lighthouse 標配六個預設基準設定：</span><span class="sxs-lookup"><span data-stu-id="4455f-107">There are six default baseline configurations that come standard with Microsoft 365 Lighthouse:</span></span>

- <span data-ttu-id="4455f-108">需要對系統管理員進行 MFA</span><span class="sxs-lookup"><span data-stu-id="4455f-108">Require MFA for admins</span></span>
- <span data-ttu-id="4455f-109">需要對使用者進行 MFA</span><span class="sxs-lookup"><span data-stu-id="4455f-109">Require MFA for end users</span></span>
- <span data-ttu-id="4455f-110">封鎖舊版驗證</span><span class="sxs-lookup"><span data-stu-id="4455f-110">Block Legacy Authentication</span></span>
- <span data-ttu-id="4455f-111">在 Microsoft 端點管理員中設定裝置註冊– Azure AD Join</span><span class="sxs-lookup"><span data-stu-id="4455f-111">Set up Device Enrollment in Microsoft Endpoint Manager – Azure AD Join</span></span>
- <span data-ttu-id="4455f-112">設定 Windows 裝置的 Defender 防病毒原則</span><span class="sxs-lookup"><span data-stu-id="4455f-112">Configure Defender Anti-virus policy for Windows devices</span></span>
- <span data-ttu-id="4455f-113">設定 Windows 裝置的相容性原則</span><span class="sxs-lookup"><span data-stu-id="4455f-113">Configure Compliance Policy for Windows devices</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="4455f-114">在您開始之前</span><span class="sxs-lookup"><span data-stu-id="4455f-114">Before you begin</span></span>

<span data-ttu-id="4455f-115">請確認您和您的客戶租使用者符合[Microsoft 365 Lighthouse 需求](m365-lighthouse-requirements.md)中所列的需求。</span><span class="sxs-lookup"><span data-stu-id="4455f-115">Make sure you and your customer tenants meet the requirements listed in [Requirements for Microsoft 365 Lighthouse](m365-lighthouse-requirements.md).</span></span>

## <a name="learn-more-about-the-default-baseline"></a><span data-ttu-id="4455f-116">深入瞭解預設基線</span><span class="sxs-lookup"><span data-stu-id="4455f-116">Learn more about the default baseline</span></span>

<span data-ttu-id="4455f-117">從左導覽窗格選取 [ **基線** ]，以開啟 [比較基準] 頁面。</span><span class="sxs-lookup"><span data-stu-id="4455f-117">Select **Baselines** from the left navigation pane to open the Baselines page.</span></span> <span data-ttu-id="4455f-118">您會看到預設的基準已經新增至預設租使用者群組 (所有承租人) 。</span><span class="sxs-lookup"><span data-stu-id="4455f-118">You'll see that the default baseline has already been added to the Default tenant group (all tenants).</span></span> <span data-ttu-id="4455f-119">若要查看預設的基準設定，請選取 [ **view 基線** ] 以開啟 [預設基線] 頁面。</span><span class="sxs-lookup"><span data-stu-id="4455f-119">To view the default baseline configurations, select **View baseline** to open the Default baseline page.</span></span> <span data-ttu-id="4455f-120">設定會列為部署步驟。</span><span class="sxs-lookup"><span data-stu-id="4455f-120">The configurations are listed as deployment steps.</span></span> <span data-ttu-id="4455f-121">選取任何部署步驟，以查看部署詳細資料和使用者影響。</span><span class="sxs-lookup"><span data-stu-id="4455f-121">Select any of the deployment steps to view deployment details and user impact.</span></span>

:::image type="content" source="../media/m365-lighthouse-deploy-baselines/default-baseline-page.png" alt-text="預設基線頁面的螢幕擷取畫面。 >。":::

## <a name="deploy-a-baseline-configuration"></a><span data-ttu-id="4455f-123">部署基準設定</span><span class="sxs-lookup"><span data-stu-id="4455f-123">Deploy a baseline configuration</span></span>  

1. <span data-ttu-id="4455f-124">在左導覽頁面中，選取 [ **承租人** ] 以查看您的架承租人清單。</span><span class="sxs-lookup"><span data-stu-id="4455f-124">In the left navigation page, select **Tenants** to view a list of your onboarded tenants.</span></span>

2. <span data-ttu-id="4455f-125">選取您要部署基準設定的承租人。</span><span class="sxs-lookup"><span data-stu-id="4455f-125">Select the tenant you want to deploy the baseline configuration to.</span></span>

3. <span data-ttu-id="4455f-126">選取 [ **部署計畫** ] 索引標籤，以查看已新增至租使用者之部署計畫之基準的所有部署步驟。</span><span class="sxs-lookup"><span data-stu-id="4455f-126">Select the **Deployment plan** tab to see all the deployment steps from the baseline that have been added to the tenant's deployment plan.</span></span>

4. <span data-ttu-id="4455f-127">選取部署步驟以開啟 [部署步驟] 頁面。</span><span class="sxs-lookup"><span data-stu-id="4455f-127">Select a deployment step to open the deployment step page.</span></span>

5. <span data-ttu-id="4455f-128">選取 **[套用] 將選取** 的部署步驟套用至租使用者。</span><span class="sxs-lookup"><span data-stu-id="4455f-128">Select **Apply** to apply the selected deployment step to the tenant.</span></span> <span data-ttu-id="4455f-129">如果部署步驟指出「此動作需要手動步驟」，請務必完成手動步驟，以便正確套用部署步驟。</span><span class="sxs-lookup"><span data-stu-id="4455f-129">If the deployment step indicates "This action requires a manual step", make sure to complete the manual step so the deployment step is applied correctly.</span></span>

## <a name="related-content"></a><span data-ttu-id="4455f-130">相關內容</span><span class="sxs-lookup"><span data-stu-id="4455f-130">Related content</span></span>

<span data-ttu-id="4455f-131">[使用基線部署標準租](m365-lighthouse-deploying-standard-tenant-configurations-overview.md) 使用者設定 (篇文章) </span><span class="sxs-lookup"><span data-stu-id="4455f-131">[Overview of using baselines to deploy standard tenant configurations](m365-lighthouse-deploying-standard-tenant-configurations-overview.md) (article)</span></span>\
<span data-ttu-id="4455f-132">[Microsoft 365 Lighthouse 常見問題](m365-lighthouse-faq.yml) (文章) </span><span class="sxs-lookup"><span data-stu-id="4455f-132">[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (article)</span></span>