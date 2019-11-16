---
title: Microsoft 365 服務和應用程式的 SIEM 伺服器整合
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/15/2019
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
description: 閱讀本篇文章以取得 Microsoft 365 的 SIEM 伺服器整合的概觀。
ms.openlocfilehash: bea6141022fef1275a7e291217f698f52613f170
ms.sourcegitcommit: d8d001c03c28c10bea005d1c9b5f4a8f393af706
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/16/2019
ms.locfileid: "38677506"
---
# <a name="siem-server-integration-with-microsoft-365-services-and-applications"></a><span data-ttu-id="409b7-103">Microsoft 365 服務和應用程式的 SIEM 伺服器整合</span><span class="sxs-lookup"><span data-stu-id="409b7-103">SIEM server integration with Microsoft 365 services and applications</span></span>

## <a name="summary"></a><span data-ttu-id="409b7-104">摘要</span><span class="sxs-lookup"><span data-stu-id="409b7-104">Summary</span></span>

<span data-ttu-id="409b7-105">如果您的組織使用的安全性資訊和事件管理 (SIEM) 伺服器，或如果您計劃要推出取得 SIEM 伺服器，您可能想知道如何，將會與 Microsoft 365 或 Office 365 整合。</span><span class="sxs-lookup"><span data-stu-id="409b7-105">If your organization is using a Security Information and Event Management (SIEM) server, or if you are planning to get a SIEM server soon, you might be wondering how that'll integrate with Microsoft 365 or Office 365.</span></span> <span data-ttu-id="409b7-106">本文提供的資源清單可用於設定您的 Microsoft 365 服務和應用程式的 SIEM 伺服器整合。</span><span class="sxs-lookup"><span data-stu-id="409b7-106">This article provides a list of resources you can use to set up SIEM server integration with your Microsoft 365 services and applications.</span></span>

> [!TIP]
> <span data-ttu-id="409b7-107">如果您沒有 SIEM 伺服器，並會瀏覽您的選項，請考慮**[Microsoft Azure 護衛巨像](https://docs.microsoft.com/azure/sentinel/overview)**。</span><span class="sxs-lookup"><span data-stu-id="409b7-107">If you don't have a SIEM server yet and are exploring your options, consider **[Microsoft Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)**.</span></span>

## <a name="do-i-need-a-siem-server"></a><span data-ttu-id="409b7-108">是否需要 SIEM 伺服器？</span><span class="sxs-lookup"><span data-stu-id="409b7-108">Do I need a SIEM server?</span></span>

<span data-ttu-id="409b7-109">您是否需要 SIEM 伺服器取決於許多因素，例如貴組織的安全性需求及您的資料所在的位置。</span><span class="sxs-lookup"><span data-stu-id="409b7-109">Whether you need a SIEM server depends on many factors, such as your organization's security requirements and where your data resides.</span></span> <span data-ttu-id="409b7-110">Microsoft 365 也包含各種不同的安全性功能，可以滿足許多組織的安全性需求，沒有其他伺服器，例如 SIEM 伺服器。</span><span class="sxs-lookup"><span data-stu-id="409b7-110">Microsoft 365 includes a wide variety of security features that meet many organizations' security needs without additional servers, such as a SIEM server.</span></span> <span data-ttu-id="409b7-111">某些組織基於要求 SIEM 伺服器使用的特殊情況。</span><span class="sxs-lookup"><span data-stu-id="409b7-111">Some organizations have special circumstances that require the use of a SIEM server.</span></span> <span data-ttu-id="409b7-112">以下為一些範例：</span><span class="sxs-lookup"><span data-stu-id="409b7-112">Here are some examples:</span></span>

- <span data-ttu-id="409b7-113">*Fabrikam*上部署，而部分 （它們有混合式雲端部署） 在雲端中具有某些內容和應用程式。</span><span class="sxs-lookup"><span data-stu-id="409b7-113">*Fabrikam* has some content and applications on premises, and some in the cloud (they have a hybrid cloud deployment).</span></span> <span data-ttu-id="409b7-114">若要取得所有其內容及應用程式之間的安全性報告，Fabrikam 已實作 SIEM 伺服器。</span><span class="sxs-lookup"><span data-stu-id="409b7-114">To get security reports across all their content and applications, Fabrikam has implemented a SIEM server.</span></span> 

- <span data-ttu-id="409b7-115">*Contoso*為金融服務組織具有特別嚴格的安全性需求。</span><span class="sxs-lookup"><span data-stu-id="409b7-115">*Contoso* is a financial services organization that has particularly stringent security requirements.</span></span> <span data-ttu-id="409b7-116">若要利用其所需要的額外的安全性保護其環境已加入 SIEM 伺服器。</span><span class="sxs-lookup"><span data-stu-id="409b7-116">They have added a SIEM server to their environment to take advantage of the extra security protection they require.</span></span>

## <a name="siem-server-integration-with-microsoft-365"></a><span data-ttu-id="409b7-117">Microsoft 365 的 SIEM 伺服器整合</span><span class="sxs-lookup"><span data-stu-id="409b7-117">SIEM server integration with Microsoft 365</span></span>

<span data-ttu-id="409b7-118">SIEM 伺服器可以接收來自各種不同的 Microsoft 365 服務和應用程式的資料。</span><span class="sxs-lookup"><span data-stu-id="409b7-118">A SIEM server can receive data from a wide variety of Microsoft 365 services and applications.</span></span> <span data-ttu-id="409b7-119">下表列出數個 Microsoft 365 服務與應用程式以及 SIEM 伺服器輸入和資源來深入了解 SIEM 伺服器整合。</span><span class="sxs-lookup"><span data-stu-id="409b7-119">The following table lists several Microsoft 365 services and applications along with SIEM server inputs, and resources to learn more about SIEM server integration.</span></span> 

| <span data-ttu-id="409b7-120">Microsoft 365 服務或應用程式</span><span class="sxs-lookup"><span data-stu-id="409b7-120">Microsoft 365 Service or Application</span></span> | <span data-ttu-id="409b7-121">SIEM 伺服器輸入</span><span class="sxs-lookup"><span data-stu-id="409b7-121">SIEM server inputs</span></span> | <span data-ttu-id="409b7-122">可深入了解的資源</span><span class="sxs-lookup"><span data-stu-id="409b7-122">Resources to learn more</span></span> |
| --- | --- | --- |
| [<span data-ttu-id="409b7-123">Office 365 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="409b7-123">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)  | <span data-ttu-id="409b7-124">稽核記錄</span><span class="sxs-lookup"><span data-stu-id="409b7-124">Audit logs</span></span> | [<span data-ttu-id="409b7-125">Office 365 進階威脅防護的 SIEM 整合</span><span class="sxs-lookup"><span data-stu-id="409b7-125">SIEM integration with Office 365 Advanced Threat Protection</span></span>](siem-integration-with-office-365-ti.md) |
| [<span data-ttu-id="409b7-126">Windows Defender 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="409b7-126">Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/) | <span data-ttu-id="409b7-127">裝載於 Azure 中的 HTTPS 端點</span><span class="sxs-lookup"><span data-stu-id="409b7-127">HTTPS endpoint hosted in Azure</span></span> <br/><span data-ttu-id="409b7-128">REST API</span><span class="sxs-lookup"><span data-stu-id="409b7-128">REST API</span></span>| [<span data-ttu-id="409b7-129">提取提醒您 SIEM 工具</span><span class="sxs-lookup"><span data-stu-id="409b7-129">Pull alerts to your SIEM tools</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem) |
| [<span data-ttu-id="409b7-130">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="409b7-130">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) | <span data-ttu-id="409b7-131">記錄整合</span><span class="sxs-lookup"><span data-stu-id="409b7-131">Log integration</span></span> | [<span data-ttu-id="409b7-132">Microsoft Cloud App Security 的 SIEM 整合</span><span class="sxs-lookup"><span data-stu-id="409b7-132">SIEM integration with Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/siem) |

> [!TIP]
> <span data-ttu-id="409b7-133">請看一下[Azure 護衛巨像](https://docs.microsoft.com/azure/sentinel/overview)，隨附於數目超出] 方塊中，並且提供即時的整合，包括 Microsoft 威脅防護解決方案，以及 Microsoft 365 來源，包括 Office 365、 Azure AD，可使用的 Microsoft 解決方案連接器 Azure ATP，以及 Microsoft Cloud App Security，等等。</span><span class="sxs-lookup"><span data-stu-id="409b7-133">Take a look at [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview), which comes with a number of connectors for Microsoft solutions, available out of the box and providing real-time integration, including Microsoft Threat Protection solutions, and Microsoft 365 sources, including Office 365, Azure AD, Azure ATP, and Microsoft Cloud App Security, and more.</span></span>

### <a name="audit-logging-must-be-turned-on"></a><span data-ttu-id="409b7-134">必須先開啟稽核記錄</span><span class="sxs-lookup"><span data-stu-id="409b7-134">Audit logging must be turned on</span></span>

<span data-ttu-id="409b7-135">請確定您在設定 SIEM 伺服器整合之前，開啟稽核記錄。</span><span class="sxs-lookup"><span data-stu-id="409b7-135">Make sure audit logging is turned on before you configure SIEM server integration.</span></span> 

- <span data-ttu-id="409b7-136">OneDrive for Business 和 Azure Active Directory[稽核記錄在安全 & 合規性中心中已開啟](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off)SharePoint online，版本。</span><span class="sxs-lookup"><span data-stu-id="409b7-136">For SharePoint Online, OneDrive for Business, and Azure Active Directory, [audit logging is turned on in the Security & Compliance Center](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off).</span></span>

- <span data-ttu-id="409b7-137">針對 Exchange Online、[使用 Windows PowerShell 開啟稽核記錄](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing)。</span><span class="sxs-lookup"><span data-stu-id="409b7-137">For Exchange Online, [audit logging is turned on with Windows PowerShell](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing).</span></span>
 
## <a name="additional-resources"></a><span data-ttu-id="409b7-138">其他資源</span><span class="sxs-lookup"><span data-stu-id="409b7-138">Additional resources</span></span>

[<span data-ttu-id="409b7-139">整合 Azure 資訊安全中心中的安全性解決方案</span><span class="sxs-lookup"><span data-stu-id="409b7-139">Integrate security solutions in Azure Security Center</span></span>](https://docs.microsoft.com/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[<span data-ttu-id="409b7-140">與 SIEM 整合 Microsoft Graph 安全性 API 提醒</span><span class="sxs-lookup"><span data-stu-id="409b7-140">Integrate Microsoft Graph Security API alerts with a SIEM</span></span>](https://docs.microsoft.com/graph/security-integration)