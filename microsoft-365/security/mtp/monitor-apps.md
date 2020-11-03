---
title: 應用程式監視 & 報告-安全性中心
description: 瞭解如何深入瞭解您的組織中的雲端應用程式使用。 包括不同類型的應用程式、其風險層級及警示。
keywords: 安全性，惡意程式碼，Microsoft 365，M365，security center，monitor，report，應用程式
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: dcb7997c8c248c2b4e7d16902b6ebdd7756ccd0b
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846625"
---
# <a name="app-monitoring-and-reporting-in-the-microsoft-365-security-center"></a><span data-ttu-id="08d4e-105">Microsoft 365 security center 中的應用程式監視與報告</span><span class="sxs-lookup"><span data-stu-id="08d4e-105">App monitoring and reporting in the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="08d4e-106">這些報告可進一步深入瞭解您的組織中使用雲端應用程式的方式。</span><span class="sxs-lookup"><span data-stu-id="08d4e-106">These reports provide more insight into how cloud apps are being used in your organization.</span></span> <span data-ttu-id="08d4e-107">包括不同類型的應用程式、其風險層級及警示。</span><span class="sxs-lookup"><span data-stu-id="08d4e-107">Includes different kinds of apps, their level of risk, and alerts.</span></span>

## <a name="monitor-email-accounts-at-risk"></a><span data-ttu-id="08d4e-108">監視有風險的電子郵件帳戶</span><span class="sxs-lookup"><span data-stu-id="08d4e-108">Monitor email accounts at risk</span></span>

<span data-ttu-id="08d4e-109">**電子郵件保護** 顯示電子郵件帳戶面臨危險。</span><span class="sxs-lookup"><span data-stu-id="08d4e-109">**Email protection** shows email accounts at risk.</span></span> <span data-ttu-id="08d4e-110">您可以選取要在 Microsoft Defender Security Center 中進一步調查的帳戶。</span><span class="sxs-lookup"><span data-stu-id="08d4e-110">You can select an account to investigate further in Microsoft Defender Security Center.</span></span>

![電子郵件保護卡](../../media/email-protection.png)

## <a name="monitor-app-permissions-granted-by-users"></a><span data-ttu-id="08d4e-112">監視使用者所授與的應用程式許可權</span><span class="sxs-lookup"><span data-stu-id="08d4e-112">Monitor app permissions granted by users</span></span>

<span data-ttu-id="08d4e-113">**Cloud App security-OAuth app** 列出已由使用者授與許可權的 Cloud App Security 所探索的應用程式。</span><span class="sxs-lookup"><span data-stu-id="08d4e-113">**Cloud App Security - OAuth apps** lists apps discovered by Cloud App Security that have been granted permissions by users.</span></span> <span data-ttu-id="08d4e-114">Cloud App Security 的風險目錄包含16000個應用程式，使用超過70的風險因素進行評估。</span><span class="sxs-lookup"><span data-stu-id="08d4e-114">Cloud App Security's risk catalog includes over 16,000 apps that are assessed using over 70 risk factors.</span></span>

<span data-ttu-id="08d4e-115">風險因素是從一般資訊開始，例如，應用程式發行者。</span><span class="sxs-lookup"><span data-stu-id="08d4e-115">The risk factors start from general information, such as the app publisher.</span></span> <span data-ttu-id="08d4e-116">然後，它會移至安全性措施和控制項，例如，應用程式是否支援靜態加密或提供使用者活動的審計記錄。</span><span class="sxs-lookup"><span data-stu-id="08d4e-116">It then moves to security measures and controls, such as whether the app supports encryption at rest or provides an audit log of user activity.</span></span>

![Cloud App Security OAuth app 卡片](../../media/cloud-app-security-oauth-apps.png)

## <a name="monitor-cloud-app-user-accounts"></a><span data-ttu-id="08d4e-118">監視 cloud app 使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="08d4e-118">Monitor cloud app user accounts</span></span>

<span data-ttu-id="08d4e-119">**雲端應用程式帳戶以供審查** 清單可能需要注意的帳戶。</span><span class="sxs-lookup"><span data-stu-id="08d4e-119">**Cloud app accounts for review** lists accounts that may require attention.</span></span>

![適用于審閱卡片的雲端應用程式帳戶](../../media/cloud-app-accounts-for-review.png)

## <a name="understand-which-cloud-apps-are-used"></a><span data-ttu-id="08d4e-121">瞭解使用的雲端應用程式</span><span class="sxs-lookup"><span data-stu-id="08d4e-121">Understand which cloud apps are used</span></span>

<span data-ttu-id="08d4e-122">已 **探索 cloud app (類別)** 顯示您的組織中所使用的應用程式類型。</span><span class="sxs-lookup"><span data-stu-id="08d4e-122">**Discovered cloud apps (categories)** show what kinds of apps are being used in your organization.</span></span> <span data-ttu-id="08d4e-123">它會連結至 Cloud App Security 中的雲端探索儀表板。</span><span class="sxs-lookup"><span data-stu-id="08d4e-123">It links to the Cloud Discovery dashboard in Cloud App Security.</span></span> <span data-ttu-id="08d4e-124">如需詳細資訊，請參閱 [快速入門：使用已探索的應用程式](https://docs.microsoft.com/cloud-app-security/discovered-apps)。</span><span class="sxs-lookup"><span data-stu-id="08d4e-124">For more information, see [Quickstart: Work with discovered apps](https://docs.microsoft.com/cloud-app-security/discovered-apps).</span></span>  

![探索的雲端應用程式類別卡片](../../media/discovered-cloud-apps-categories.png)

## <a name="monitor-where-users-access-cloud-apps"></a><span data-ttu-id="08d4e-126">監視使用者存取雲端 app 的位置</span><span class="sxs-lookup"><span data-stu-id="08d4e-126">Monitor where users access cloud apps</span></span>

<span data-ttu-id="08d4e-127">**雲端應用程式活動位置** 顯示使用者存取雲端 app 的位置。</span><span class="sxs-lookup"><span data-stu-id="08d4e-127">**Cloud app activity locations** show where users are accessing cloud apps.</span></span>

![雲端應用程式活動位置卡片](../../media/cloud-app-activity-locations.png)

## <a name="monitor-health-for-infrastructure-workloads"></a><span data-ttu-id="08d4e-129">監視基礎結構工作負載的健康情況</span><span class="sxs-lookup"><span data-stu-id="08d4e-129">Monitor health for infrastructure workloads</span></span>

<span data-ttu-id="08d4e-130">**基礎結構健康** 情況會顯示 Azure Defender 中基礎結構工作負載的健康狀態警示。</span><span class="sxs-lookup"><span data-stu-id="08d4e-130">**Infrastructure health** shows health status alerts for infrastructure workloads in Azure Defender\*.</span></span>

<span data-ttu-id="08d4e-131">Azure Defender \* 跨內部部署和雲端工作負載提供 Office 365 的統一安全性管理和 Defender。</span><span class="sxs-lookup"><span data-stu-id="08d4e-131">Azure Defender\* provides unified security management and Defender for Office 365 across on-premises and cloud workloads.</span></span> <span data-ttu-id="08d4e-132">您可以收集、搜尋及分析不同來源的安全性資料，包括防火牆和其他合作夥伴解決方案。</span><span class="sxs-lookup"><span data-stu-id="08d4e-132">You can collect, search, and analyze security data from different sources, including firewalls and other partner solutions.</span></span>

<span data-ttu-id="08d4e-133">如需詳細資訊，請參閱 [Azure Defender \* 檔](https://docs.microsoft.com/azure/security-center/)。</span><span class="sxs-lookup"><span data-stu-id="08d4e-133">For more information, see [Azure Defender\* Documentation](https://docs.microsoft.com/azure/security-center/).</span></span>

![基礎結構健康卡](../../media/infrastructure-health.png)
