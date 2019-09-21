---
title: 應用程式監視和報告在 Microsoft 365 安全中心
description: 說明如何取得更深入的雲端應用程式使用，以及在組織中
keywords: 安全性、 惡意程式碼、 Microsoft 365、 M365、 資訊安全中心、 監視、 報表、 應用程式
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.openlocfilehash: 29dd1f4ebb8d65bb6079cdc4467f1aa5e33ae906
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37078353"
---
# <a name="app-monitoring-and-reporting-in-microsoft-365-security-center"></a><span data-ttu-id="ba91d-104">應用程式監視和報告在 Microsoft 365 安全中心</span><span class="sxs-lookup"><span data-stu-id="ba91d-104">App monitoring and reporting in Microsoft 365 security center</span></span>

<span data-ttu-id="ba91d-105">這些報告可提供更深入的雲端應用程式在您的組織，包括何種應用程式、 其層級的風險和提醒的使用方式。</span><span class="sxs-lookup"><span data-stu-id="ba91d-105">These reports provide more insight into how cloud apps are being used in your organization, including what kinds of apps, their level of risk, and alerts.</span></span>

## <a name="monitor-email-accounts-at-risk"></a><span data-ttu-id="ba91d-106">監視風險的電子郵件帳戶</span><span class="sxs-lookup"><span data-stu-id="ba91d-106">Monitor email accounts at risk</span></span>

<span data-ttu-id="ba91d-107">**電子郵件保護**顯示電子郵件帳戶的風險。</span><span class="sxs-lookup"><span data-stu-id="ba91d-107">**Email protection** shows email accounts at risk.</span></span> <span data-ttu-id="ba91d-108">您可以按一下 [帳戶以調查進一步 Microsoft defender 資訊安全中心。</span><span class="sxs-lookup"><span data-stu-id="ba91d-108">You can click an account to investigate further in Microsoft Defender Security Center.</span></span>

![電子郵件保護卡片](../media/security-docs/email-protection.png)

## <a name="monitor-app-permissions-granted-by-users"></a><span data-ttu-id="ba91d-110">監視應用程式權限授與使用者</span><span class="sxs-lookup"><span data-stu-id="ba91d-110">Monitor app permissions granted by users</span></span>

<span data-ttu-id="ba91d-111">**Cloud App Security OAuth 應用程式**列出探索到的 Cloud App Security 應用程式已授與權限的使用者。</span><span class="sxs-lookup"><span data-stu-id="ba91d-111">**Cloud App Security - OAuth apps** lists apps discovered by Cloud App Security that have been granted permissions by users.</span></span> <span data-ttu-id="ba91d-112">雲端 App 安全性的風險目錄包含超過 16000 會評估使用超過 70 風險因素的應用程式。</span><span class="sxs-lookup"><span data-stu-id="ba91d-112">Cloud App Security's risk catalog includes over 16,000 apps that are assessed using over 70 risk factors.</span></span>

<span data-ttu-id="ba91d-113">風險因素開始一般資訊，例如應用程式發行者，從安全性措施和控制項，例如應用程式是否支援靜態加密，或提供使用者活動的稽核記錄檔。</span><span class="sxs-lookup"><span data-stu-id="ba91d-113">The risk factors start from general information, such as the app publisher, to security measures and controls, such as whether the app supports for encryption at rest or provides an audit log of user activity.</span></span>

![雲端 App 安全性 OAuth 應用程式卡](../media/security-docs/cloud-app-security-oauth-apps.png)

## <a name="monitor-cloud-app-user-accounts"></a><span data-ttu-id="ba91d-115">監視雲端應用程式使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="ba91d-115">Monitor cloud app user accounts</span></span>

<span data-ttu-id="ba91d-116">**雲端應用程式帳戶檢閱**列出可能需要加以留意的帳戶。</span><span class="sxs-lookup"><span data-stu-id="ba91d-116">**Cloud app accounts for review** lists accounts that may require attention.</span></span>

![檢閱卡片的雲端應用程式帳戶](../media/security-docs/cloud-app-accounts-for-review.png)

## <a name="understand-which-cloud-apps-are-used"></a><span data-ttu-id="ba91d-118">了解使用哪一個雲端應用程式</span><span class="sxs-lookup"><span data-stu-id="ba91d-118">Understand which cloud apps are used</span></span>

<span data-ttu-id="ba91d-119">**Discovered 雲端應用程式 （類別）** 顯示您的組織和連結至雲端 App 安全性中的雲端探索儀表板中正在使用何種應用程式。</span><span class="sxs-lookup"><span data-stu-id="ba91d-119">**Discovered cloud apps (categories)** show what kinds of apps are being used in your organization and links to the Cloud Discovery dashboard in Cloud App Security.</span></span> <span data-ttu-id="ba91d-120">如需詳細資訊，請參閱[快速入門： 使用探索到的應用程式](https://docs.microsoft.com/cloud-app-security/discovered-apps)。</span><span class="sxs-lookup"><span data-stu-id="ba91d-120">For more information, see [Quickstart: Work with discovered apps](https://docs.microsoft.com/cloud-app-security/discovered-apps).</span></span>  

![探索到的雲端應用程式] 類別卡片](../media/security-docs/discovered-cloud-apps-categories.png)

## <a name="monitor-where-users-access-cloud-apps"></a><span data-ttu-id="ba91d-122">監視使用者在存取雲端應用程式</span><span class="sxs-lookup"><span data-stu-id="ba91d-122">Monitor where users access cloud apps</span></span>

<span data-ttu-id="ba91d-123">**雲端應用程式活動位置**顯示使用者在存取雲端應用程式。</span><span class="sxs-lookup"><span data-stu-id="ba91d-123">**Cloud app activity locations** show where users are accessing cloud apps.</span></span>

![雲端應用程式活動位置卡](../media/security-docs/cloud-app-activity-locations.png)

## <a name="monitor-health-for-infrastructure-workloads"></a><span data-ttu-id="ba91d-125">基礎結構的工作負載的監視器健康情況</span><span class="sxs-lookup"><span data-stu-id="ba91d-125">Monitor health for infrastructure workloads</span></span>

<span data-ttu-id="ba91d-126">**基礎結構狀況**會顯示在 [Azure 資訊安全中心基礎結構的工作負載的狀態通知健康情況。</span><span class="sxs-lookup"><span data-stu-id="ba91d-126">**Infrastructure health** shows health status alerts for infrastructure workloads in Azure Security Center.</span></span>

<span data-ttu-id="ba91d-127">Azure 資訊安全中心提供整合安全性管理和進階威脅防護跨內部部署和雲端工作負載。</span><span class="sxs-lookup"><span data-stu-id="ba91d-127">Azure Security Center provides unified security management and advanced threat protection across on-premises and cloud workloads.</span></span> <span data-ttu-id="ba91d-128">您可以收集、 搜尋及分析安全性資料從各種來源，包括防火牆和其他協力廠商解決方案。</span><span class="sxs-lookup"><span data-stu-id="ba91d-128">You can collect, search, and analyze security data from a variety of sources, including firewalls and other partner solutions.</span></span>

<span data-ttu-id="ba91d-129">如需詳細資訊，請參閱[Azure 安全性中心文件](https://docs.microsoft.com/azure/security-center/)。</span><span class="sxs-lookup"><span data-stu-id="ba91d-129">For more information, see [Azure Security Center Documentation](https://docs.microsoft.com/azure/security-center/).</span></span>

![基礎結構健康情況] 卡片](../media/security-docs/infrastructure-health.png)
