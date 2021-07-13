---
title: 使用基線部署標準租使用者設定的概覽
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
description: 針對受管理的服務提供者 (MSPs) 使用 Microsoft 365 Lighthouse，瞭解如何使用比較基準部署標準租使用者設定。
ms.openlocfilehash: ff3fb21e71195f9614870b8e3c65c92ee11fdf69
ms.sourcegitcommit: 8c698d1a0c41baf5f35d07b0d765b4a5ead593d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/13/2021
ms.locfileid: "53409174"
---
# <a name="overview-of-using-baselines-to-deploy-standard-tenant-configurations"></a><span data-ttu-id="6b87d-103">使用基線部署標準租使用者設定的概覽</span><span class="sxs-lookup"><span data-stu-id="6b87d-103">Overview of using baselines to deploy standard tenant configurations</span></span> 

> [!NOTE]
> <span data-ttu-id="6b87d-104">本文所述的功能都是在預覽中進行變更，而且只有符合 [需求](m365-lighthouse-requirements.md)的合作夥伴才能使用。</span><span class="sxs-lookup"><span data-stu-id="6b87d-104">The features described in this article are in Preview, are subject to change, and are only available to partners who meet the [requirements](m365-lighthouse-requirements.md).</span></span> <span data-ttu-id="6b87d-105">如果您的組織沒有 Microsoft 365 Lighthouse，請參閱[註冊 Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md)。</span><span class="sxs-lookup"><span data-stu-id="6b87d-105">If your organization does not have Microsoft 365 Lighthouse, see [Sign up for Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md).</span></span>

<span data-ttu-id="6b87d-106">Microsoft 365 Lighthouse 基線為您提供可重複且可伸縮的方式，可讓您評估和管理跨多個承租人的 Microsoft 365 安全性設定。</span><span class="sxs-lookup"><span data-stu-id="6b87d-106">Microsoft 365 Lighthouse baselines provide a repeatable and scalable way for you to assess and manage Microsoft 365 security settings across multiple tenants.</span></span> <span data-ttu-id="6b87d-107">基準也會協助監控核心安全性原則和租使用者規範標準，以及保護使用者、裝置及資料的設定。</span><span class="sxs-lookup"><span data-stu-id="6b87d-107">Baselines also help monitor core security policies and tenant compliance standards with configurations that secure users, devices, and data.</span></span>

<span data-ttu-id="6b87d-108">其設計目的是協助合作夥伴以其自己的節奏來啟用安全性採用，Microsoft 365 Lighthouse 為 Microsoft 365 服務提供一組標準的基準參數和預先定義的設定。</span><span class="sxs-lookup"><span data-stu-id="6b87d-108">Designed to help partners enable customer adoption of security at their own pace, Microsoft 365 Lighthouse provides a standard set of baseline parameters and pre-defined configurations for Microsoft 365 services.</span></span> <span data-ttu-id="6b87d-109">這些安全性設定有助於衡量承租人的 Microsoft 365 安全性和合規性進度。</span><span class="sxs-lookup"><span data-stu-id="6b87d-109">These security configurations help measure your tenants' Microsoft 365 security and compliance progress.</span></span>

<span data-ttu-id="6b87d-110">您可以從 Microsoft 365 Lighthouse 中查看預設的基準及其部署步驟。</span><span class="sxs-lookup"><span data-stu-id="6b87d-110">You can view the default baseline and its deployment steps from within Microsoft 365 Lighthouse.</span></span> <span data-ttu-id="6b87d-111">若要將基準套用至租使用者，請在左功能窗格中選取 [ **承租人** ]，然後選取租使用者。</span><span class="sxs-lookup"><span data-stu-id="6b87d-111">To apply baselines to a tenant, select **Tenants** in the left navigation pane, and then select a tenant.</span></span> <span data-ttu-id="6b87d-112">接下來，移至 [ **部署計畫** ] 索引標籤，並執行所需的基準。</span><span class="sxs-lookup"><span data-stu-id="6b87d-112">Next, go to the **Deployment plans** tab and implement the desired baseline.</span></span>

## <a name="standard-baseline-security-templates"></a><span data-ttu-id="6b87d-113">標準基準安全性範本</span><span class="sxs-lookup"><span data-stu-id="6b87d-113">Standard baseline security templates</span></span>

<span data-ttu-id="6b87d-114">Microsoft 365 Lighthouse 安全性工作負載的標準基準設定，是為了協助所有受管理的承租人達到安全性範圍和合規性的可接受狀態。</span><span class="sxs-lookup"><span data-stu-id="6b87d-114">Microsoft 365 Lighthouse standard baseline configurations for security workloads are designed to help all managed tenants reach an acceptable state of security coverage and compliance.</span></span>

<span data-ttu-id="6b87d-115">下表中的基準設定標配 Microsoft 365 Lighthouse 預設的基準。</span><span class="sxs-lookup"><span data-stu-id="6b87d-115">The baseline configurations in the following table come standard with the Microsoft 365 Lighthouse default baseline.</span></span><br><br>

| <span data-ttu-id="6b87d-116">基準設定</span><span class="sxs-lookup"><span data-stu-id="6b87d-116">Baseline configuration</span></span> | <span data-ttu-id="6b87d-117">描述</span><span class="sxs-lookup"><span data-stu-id="6b87d-117">Description</span></span> |
|--|--|
| <span data-ttu-id="6b87d-118">需要對系統管理員進行 MFA</span><span class="sxs-lookup"><span data-stu-id="6b87d-118">Require MFA for admins</span></span> | <span data-ttu-id="6b87d-119">僅限報告的條件式存取原則，需要系統管理員的多重驗證。</span><span class="sxs-lookup"><span data-stu-id="6b87d-119">A report-only Conditional Access policy requiring multifactor authentication for admins.</span></span> <span data-ttu-id="6b87d-120">所有的雲端應用程式都需要這種方式。</span><span class="sxs-lookup"><span data-stu-id="6b87d-120">It's required for all cloud applications.</span></span> |
| <span data-ttu-id="6b87d-121">需要對使用者進行 MFA</span><span class="sxs-lookup"><span data-stu-id="6b87d-121">Require MFA for end users</span></span> | <span data-ttu-id="6b87d-122">僅限報告的條件式存取原則，需要使用者的多重要素驗證。</span><span class="sxs-lookup"><span data-stu-id="6b87d-122">A report-only Conditional Access policy that requires multifactor authentication for users.</span></span> <span data-ttu-id="6b87d-123">所有的雲端應用程式都需要這種方式。</span><span class="sxs-lookup"><span data-stu-id="6b87d-123">It's required for all cloud applications.</span></span> |
| <span data-ttu-id="6b87d-124">封鎖舊版驗證</span><span class="sxs-lookup"><span data-stu-id="6b87d-124">Block legacy authentication</span></span> | <span data-ttu-id="6b87d-125">僅限報告的條件式存取原則，以封鎖舊版用戶端驗證。</span><span class="sxs-lookup"><span data-stu-id="6b87d-125">A report-only Conditional Access policy to block legacy client authentication.</span></span> |
| <span data-ttu-id="6b87d-126">在 Microsoft 端點管理員中註冊裝置– Azure AD Join</span><span class="sxs-lookup"><span data-stu-id="6b87d-126">Enroll devices in Microsoft Endpoint Manager – Azure AD Join</span></span> | <span data-ttu-id="6b87d-127">裝置註冊，以允許租使用者裝置 Microsoft 端點管理員註冊。</span><span class="sxs-lookup"><span data-stu-id="6b87d-127">Device enrollment to allow your tenant devices to enroll in Microsoft Endpoint Manager.</span></span> <span data-ttu-id="6b87d-128">這是透過設定 Azure Active Directory 和 Microsoft 端點管理員之間的自動註冊來完成。</span><span class="sxs-lookup"><span data-stu-id="6b87d-128">This is done by setting up Auto Enrollment between Azure Active Directory and Microsoft Endpoint Manager.</span></span> |
| <span data-ttu-id="6b87d-129">防病毒 (AV) 原則設定</span><span class="sxs-lookup"><span data-stu-id="6b87d-129">Antivirus (AV) policy configuration</span></span> | <span data-ttu-id="6b87d-130">具有預先設定 Microsoft Defender 防毒軟體設定之 Windows 裝置的裝置設定檔。</span><span class="sxs-lookup"><span data-stu-id="6b87d-130">A Device Configuration profile for Windows devices with pre-configured Microsoft Defender Antivirus settings.</span></span> |
| <span data-ttu-id="6b87d-131">視窗10符合性原則設定</span><span class="sxs-lookup"><span data-stu-id="6b87d-131">Window 10 Compliance policy set up</span></span> | <span data-ttu-id="6b87d-132">具備預先設定的 Windows 裝置原則，以符合基本規範的需求。</span><span class="sxs-lookup"><span data-stu-id="6b87d-132">A Windows device policy with pre-configured settings to meet basic compliance requirements.</span></span> |

## <a name="related-content"></a><span data-ttu-id="6b87d-133">相關內容</span><span class="sxs-lookup"><span data-stu-id="6b87d-133">Related content</span></span>

<span data-ttu-id="6b87d-134"> (文章[部署 Microsoft 365 Lighthouse 基線](m365-lighthouse-deploy-baselines.md)) </span><span class="sxs-lookup"><span data-stu-id="6b87d-134">[Deploy Microsoft 365 Lighthouse baselines](m365-lighthouse-deploy-baselines.md) (article)\</span></span>
<span data-ttu-id="6b87d-135">[Microsoft 365 Lighthouse 常見問題](m365-lighthouse-faq.yml) (文章) </span><span class="sxs-lookup"><span data-stu-id="6b87d-135">[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (article)</span></span>
