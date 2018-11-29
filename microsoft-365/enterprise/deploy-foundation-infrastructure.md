---
title: Microsoft 365 企業版底層基礎結構
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 06/27/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 了解貴組織中部署 Microsoft 365 企業版底層基礎結構的主要階段。
ms.openlocfilehash: abc38dc0eb3d33f7af9e2c91f020a735cf0c8d96
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866118"
---
# <a name="microsoft-365-enterprise-foundation-infrastructure"></a><span data-ttu-id="d5409-103">Microsoft 365 企業版底層基礎結構</span><span class="sxs-lookup"><span data-stu-id="d5409-103">Microsoft 365 Enterprise foundation infrastructure</span></span>

<span data-ttu-id="d5409-104">若要完全發揮 Microsoft 365 企業版的優點，您需要從底層基礎結構開始部署。</span><span class="sxs-lookup"><span data-stu-id="d5409-104">To fully realize the benefits of Microsoft 365 Enterprise, you’ll begin your deployment with its foundation infrastructure.</span></span> 

## <a name="foundation-infrastructure-for-deploying-microsoft-365-enterprise"></a><span data-ttu-id="d5409-105">部署 Microsoft 365 企業版的底層基礎結構</span><span class="sxs-lookup"><span data-stu-id="d5409-105">Foundation infrastructure for deploying Microsoft 365 Enterprise</span></span>

<span data-ttu-id="d5409-p101">底層基礎結構是您可以在其上部署生產力工作負載 (如 Office 365 中的 Microsoft Teams 和 Exchange Online) 和案例 (例如移轉至 Microsoft 365 及自動化用戶端更新) 的基礎。它提供智慧安全性與整合，可簡化持續的管理，確保您的用戶端軟體會以最新的生產力與安全性增強功能進行更新。</span><span class="sxs-lookup"><span data-stu-id="d5409-p101">The foundation infrastructure is the groundwork upon which you can deploy productivity workloads (such as Microsoft Teams and Exchange Online in Office 365) and scenarios (such as migrating to Microsoft 365 and automating client updates). It provides intelligent security and integration that simplifies ongoing management, which ensures that your client software is updated with the latest productivity and security enhancements.</span></span>

<span data-ttu-id="d5409-108">您將使用下列階段在組織中規劃和部署 Microsoft 365 企業版的底層基礎結構：</span><span class="sxs-lookup"><span data-stu-id="d5409-108">You'll use the following phases to plan for and deploy the foundation infrastructure of Microsoft 365 Enterprise in your organization:</span></span>

|||
|:-------|:-----|
|![](./media/deploy-foundation-infrastructure/networking_icon-small.png)|[<span data-ttu-id="d5409-109">階段 1：網路</span><span class="sxs-lookup"><span data-stu-id="d5409-109">Phase 1: Networking</span></span>](networking-infrastructure.md)|
|![](./media/deploy-foundation-infrastructure/identity_icon-small.png)|[<span data-ttu-id="d5409-110">階段 2：身分識別</span><span class="sxs-lookup"><span data-stu-id="d5409-110">Phase 2: Identity</span></span>](identity-infrastructure.md)|
|![](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)|[<span data-ttu-id="d5409-111">階段 3：Windows 10 企業版</span><span class="sxs-lookup"><span data-stu-id="d5409-111">Phase 3: Windows 10 Enterprise</span></span>](windows10-infrastructure.md)|
|![](./media/deploy-foundation-infrastructure/O365proplus_icon-small.png)|[<span data-ttu-id="d5409-112">階段 4：Office 365 專業增強版</span><span class="sxs-lookup"><span data-stu-id="d5409-112">Phase 4: Office 365 ProPlus</span></span>](office365proplus-infrastructure.md)|
|![](./media/deploy-foundation-infrastructure/mobiledevicemgmt_icon-small.png)|[<span data-ttu-id="d5409-113">階段 5：行動裝置管理</span><span class="sxs-lookup"><span data-stu-id="d5409-113">Phase 5: Mobile device management</span></span>](mobility-infrastructure.md)|
|![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)|[<span data-ttu-id="d5409-114">階段 6：資訊保護</span><span class="sxs-lookup"><span data-stu-id="d5409-114">Phase 6: Information protection</span></span>](infoprotect-infrastructure.md)|


<span data-ttu-id="d5409-p102">在結束每個階段前，您必須檢查允出準則，其為一組您必須符合的必要條件以及要考慮的選用條件。每個階段的允出準則可確保您的內部部署和雲端基礎結構與產生的端對端設定符合 Microsoft 365 企業版部署需求。</span><span class="sxs-lookup"><span data-stu-id="d5409-p102">Before you can exit each phase, you must examine its exit criteria, which is a set of required conditions that you must meet and optional conditions to consider. Exit criteria for each phase ensures that your on-premises and cloud infrastructure and resulting end-to-end configuration meet the requirements for a Microsoft 365 Enterprise deployment.</span></span>

<span data-ttu-id="d5409-117">請觀看這段關於基礎結構內容運作方式的短片。</span><span class="sxs-lookup"><span data-stu-id="d5409-117">Watch this short video on how the foundation infrastructure content works.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE23VRG]

<span data-ttu-id="d5409-118">下圖顯示在整體 Microsoft 365 企業版部署內容中的底層基礎結構及您的部署路徑。</span><span class="sxs-lookup"><span data-stu-id="d5409-118">The following figure shows the foundation infrastructure in the overall Microsoft 365 Enterprise deployment content and your path through it.</span></span>

![](./media/deploy-foundation-infrastructure/m365-deploy-content-arch-foundation.png)

## <a name="fasttrack"></a><span data-ttu-id="d5409-119">FastTrack</span><span class="sxs-lookup"><span data-stu-id="d5409-119">FastTrack</span></span>

<span data-ttu-id="d5409-p103">FastTrack 是由 Microsoft 工程師提供的持續且可重複的好處，作為訂閱的一部分供您使用，可協助您以自己的步調移轉到雲端。FastTrack 也可在您有需要時，讓您存取合格合作夥伴的其他服務。至今隨著超過 40000 位啟用此服務的客戶，FastTrack 可協助最大化 ROI、加速部署，以及提高整個組織中的採用率。請參閱[適用於 Microsoft 365 的 FastTrack](https://fasttrack.microsoft.com/microsoft365)。</span><span class="sxs-lookup"><span data-stu-id="d5409-p103">FastTrack is an ongoing and repeatable benefit—available as part of your subscription—that is delivered by Microsoft engineers to help you move to the cloud at your own pace. FastTrack also gives you access to qualified partners for additional services, as needed. With over 40,000 customers enabled to date, FastTrack helps maximize ROI, accelerate deployment, and increase adoption across your organization. See [FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365).</span></span> 

<span data-ttu-id="d5409-p104">如果您想要利用 FastTrack 來部署 Microsoft 365 企業版，您可以使用 FastTrack [Microsoft 365 部署建議程式](https://aka.ms/microsoft365setupguide)，以了解有關部署及設定基礎結構的指導方針。您必須以全域管理員身分登入 Office 365 或 Microsoft 365 租用戶，以便存取此頁面。</span><span class="sxs-lookup"><span data-stu-id="d5409-p104">If you want to take advantage of FastTrack to deploy Microsoft 365 Enterprise, you can use the FastTrack [Microsoft 365 deployment advisor](https://aka.ms/microsoft365setupguide) for guidance on how to deploy and set up your foundation infrastructure. You must be signed on as a global administrator in an Office 365 or Microsoft 365 tenant in order to access this page.</span></span>

## <a name="next-step"></a><span data-ttu-id="d5409-126">下一步</span><span class="sxs-lookup"><span data-stu-id="d5409-126">Next step</span></span>

<span data-ttu-id="d5409-p105">如果您有 Office 365、Enterprise Mobility + Security 或 Windows 10 企業版現有的基礎結構，請參閱[使用現有基礎結構部署 Microsoft 365 企業版](deploy-with-existing-infrastructure.md)。此文章會逐步引導您了解每個階段的允出準則。使用此資訊，您可以更快判斷要讓 IT 基礎結構與 Microsoft 365 企業版相容所需的變更。</span><span class="sxs-lookup"><span data-stu-id="d5409-p105">If you have existing infrastructure for Office 365, Enterprise Mobility + Security, or Windows 10 Enterprise, see [Deployment of Microsoft 365 Enterprise with existing infrastructure](deploy-with-existing-infrastructure.md). This article steps you through the exit criteria for each phase. With this information, you can more quickly determine what you need to change to make your IT infrastructure Microsoft 365 Enterprise-compliant.</span></span>

<span data-ttu-id="d5409-130">如果沒有，則可以使用[階段 1：網路](networking-infrastructure.md)開始您的 Microsoft 365 企業版端對端部署。</span><span class="sxs-lookup"><span data-stu-id="d5409-130">Otherwise, you can begin your Microsoft 365 Enterprise end-to-end deployment journey with [Phase 1: Networking](networking-infrastructure.md).</span></span>