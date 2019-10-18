---
title: 使用現有基礎結構部署 Microsoft 365 企業版
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/24/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 逐一討論在您有現有基礎結構時，部署 Microsoft 365 企業版的允出準則。
ms.openlocfilehash: 1b464398b981133e2851760d7bfe16869f1d1429
ms.sourcegitcommit: 328b31f69663669b3c656b2e4db529f70d1c753e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/25/2019
ms.locfileid: "37148507"
---
# <a name="deployment-of-microsoft-365-enterprise-with-existing-infrastructure"></a><span data-ttu-id="5bc12-103">使用現有基礎結構部署 Microsoft 365 企業版</span><span class="sxs-lookup"><span data-stu-id="5bc12-103">Deployment of Microsoft 365 Enterprise with existing infrastructure</span></span>

<span data-ttu-id="5bc12-p101">許多組織都有現有的網路、身分識別及其他元件，或 Microsoft 內部部署產品和以雲端為基礎的服務。本文將逐一討論部署 Microsoft 365 企業版的每個階段，以便您快速判斷如何調整或變更現有的基礎結構。</span><span class="sxs-lookup"><span data-stu-id="5bc12-p101">Many organizations have exisiting networking, identity, and other components or Microsoft on-premises products and cloud-based services. This article steps through each phase of the deployment of Microsoft 365 Enterprise so you can quickly determine how to adapt or change your existing infrastructure.</span></span>

<span data-ttu-id="5bc12-p102">在結束每個階段前，您必須檢查允出準則，其為一組您必須符合的必要條件以及要考慮的選用條件。每個階段的允出準則可確保您的內部部署和雲端基礎結構與產生的端對端設定符合 Microsoft 365 企業版部署需求。</span><span class="sxs-lookup"><span data-stu-id="5bc12-p102">Before you can exit each phase, you must examine its exit criteria, which is a set of required conditions that you must meet and optional conditions to consider. Exit criteria for each phase ensures that your on-premises and cloud infrastructure and resulting end-to-end configuration meets the requirements for a Microsoft 365 Enterprise deployment.</span></span>

> [!Note] 
> <span data-ttu-id="5bc12-p103">FastTrack 是由 Microsoft 工程師提供的持續且可重複的權益，作為訂閱的一部分免費供您使用，可協助您以自己的步調移轉到雲端。FastTrack 也可在您有需要時，讓您存取合格合作夥伴的其他服務。至今隨著超過 40,000 位啟用此服務的客戶，FastTrack 可協助最大化 ROI、加速部署，以及提高整個組織中的採用率。請參閱[適用於 Microsoft 365 的 FastTrack](https://fasttrack.microsoft.com/microsoft365)。</span><span class="sxs-lookup"><span data-stu-id="5bc12-p103">FastTrack is an ongoing and repeatable benefit—available as part of your subscription—that is delivered by Microsoft engineers to help you move to the cloud at your own pace. FastTrack also gives you access to qualified partners for additional services, as needed. With over 40,000 customers enabled to date, FastTrack helps maximize ROI, accelerate deployment, and increase adoption across your organization. See [FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365).</span></span>

## <a name="exit-criteria-for-networking-phase-1"></a><span data-ttu-id="5bc12-112">網路的允出準則 (階段 1)</span><span class="sxs-lookup"><span data-stu-id="5bc12-112">Exit criteria for networking (phase 1)</span></span>

<span data-ttu-id="5bc12-113">逐一討論網路基礎結構的下列必要和選用條件。</span><span class="sxs-lookup"><span data-stu-id="5bc12-113">Step through the following required and optional conditions for the networking infrastructure.</span></span>

[!INCLUDE [Deployment exit criteria for networking](./includes/deployment-exit-criteria-networking.md)]

## <a name="exit-criteria-for-identity-phase-2"></a><span data-ttu-id="5bc12-114">身分識別的允出準則 (階段 2)</span><span class="sxs-lookup"><span data-stu-id="5bc12-114">Exit criteria for identity (phase 2)</span></span>

<span data-ttu-id="5bc12-115">逐一討論身分識別基礎結構的下列必要和選用條件。</span><span class="sxs-lookup"><span data-stu-id="5bc12-115">Step through the following required and optional conditions for the identity infrastructure.</span></span>

[!INCLUDE [Deployment exit criteria for identity](./includes/deployment-exit-criteria-identity.md)]

## <a name="exit-criteria-for-windows-10-enterprise-phase-3"></a><span data-ttu-id="5bc12-116">Windows 10 企業版的允出準則 (階段 3)</span><span class="sxs-lookup"><span data-stu-id="5bc12-116">Exit criteria for Windows 10 Enterprise (phase 3)</span></span>

<span data-ttu-id="5bc12-117">逐一討論 Windows 10 企業版基礎結構的下列必要和選用條件。</span><span class="sxs-lookup"><span data-stu-id="5bc12-117">Step through the following required and optional conditions for the Windows 10 Enterprise infrastructure.</span></span>

[!INCLUDE [Deployment exit criteria for identity](./includes/deployment-exit-criteria-windows10.md)]

## <a name="exit-criteria-for-office-365-proplus-phase-4"></a><span data-ttu-id="5bc12-118">Office 365 專業增強版的允出準則 (階段 4)</span><span class="sxs-lookup"><span data-stu-id="5bc12-118">Exit criteria for Office 365 ProPlus (phase 4)</span></span>

<span data-ttu-id="5bc12-119">符合 Office 365 專業增強版的評估、部署規劃和部署需求。</span><span class="sxs-lookup"><span data-stu-id="5bc12-119">Meet the requirements for assessment, deployment planning, and deployment of the Office 365 ProPlus infrastructure for Microsoft 365 Enterprise.</span></span>

[!INCLUDE [Deployment exit criteria for Office 365 ProPlus](./includes/deployment-exit-criteria-office365proplus.md)]

## <a name="exit-criteria-for-mobile-device-management-phase-5"></a><span data-ttu-id="5bc12-120">行動裝置管理的允出準則 (階段 5)</span><span class="sxs-lookup"><span data-stu-id="5bc12-120">Exit criteria for mobile device management (phase 5)</span></span>

<span data-ttu-id="5bc12-121">符合行動裝置管理基礎結構的下列需求。</span><span class="sxs-lookup"><span data-stu-id="5bc12-121">Meet the following requirements for the mobile device management infrastructure.</span></span>

[!INCLUDE [Deployment exit criteria for mobile device management](./includes/deployment-exit-criteria-mobility.md)]

## <a name="exit-criteria-for-information-protection-phase-6"></a><span data-ttu-id="5bc12-122">資訊保護的允出準則 (階段 6)</span><span class="sxs-lookup"><span data-stu-id="5bc12-122">Exit criteria for information protection (phase 6)</span></span>

<span data-ttu-id="5bc12-123">逐一討論資訊保護基礎結構的下列必要和選用條件。</span><span class="sxs-lookup"><span data-stu-id="5bc12-123">Step through the following required and optional conditions for the information protection infrastructure.</span></span>

[!INCLUDE [Deployment exit criteria for information protection](./includes/deployment-exit-criteria-infoprotect.md)]

