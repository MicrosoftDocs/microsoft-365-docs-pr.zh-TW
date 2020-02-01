---
title: " Microsoft 365 服務與應用程式的安全性資訊和事件管理 (SIEM) server 整合"
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/18/2019
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
description: 取得與 Microsoft 365 雲端服務和應用程式的安全性資訊和事件管理 (SIEM) 伺服器整合的概觀
ms.openlocfilehash: 0d5f1f6b3137e247778384f3a29390af560394e8
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598290"
---
#  <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a><span data-ttu-id="1e12a-103">Microsoft 365 服務與應用程式的安全性資訊和事件管理 (SIEM) server 整合</span><span class="sxs-lookup"><span data-stu-id="1e12a-103">Security Information and Event Management (SIEM) server integration with Microsoft 365 services and applications</span></span>

## <a name="summary"></a><span data-ttu-id="1e12a-104">摘要</span><span class="sxs-lookup"><span data-stu-id="1e12a-104">Summary</span></span>

<span data-ttu-id="1e12a-105">是您的組織使用或規劃以取得安全性資訊和事件管理 (SIEM) 伺服器？</span><span class="sxs-lookup"><span data-stu-id="1e12a-105">Is your organization using or planning to get a Security Information and Event Management (SIEM) server?</span></span> <span data-ttu-id="1e12a-106">您可能會想知道如何與 Microsoft 365 或 Office 365 整合。</span><span class="sxs-lookup"><span data-stu-id="1e12a-106">You might be wondering how it integrates with Microsoft 365 or Office 365.</span></span> <span data-ttu-id="1e12a-107">本文提供的資源可用來將 SIEM 伺服器整合的 Microsoft 365 服務和應用程式的清單。</span><span class="sxs-lookup"><span data-stu-id="1e12a-107">This article provides a list of resources you can use to integrate your SIEM server with Microsoft 365 services and applications.</span></span>

> [!TIP]
> <span data-ttu-id="1e12a-108">如果您沒有 SIEM 伺服器，並會瀏覽您的選項，請考慮**[Microsoft Azure 護衛巨像](https://docs.microsoft.com/azure/sentinel/overview)**。</span><span class="sxs-lookup"><span data-stu-id="1e12a-108">If you don't have a SIEM server yet and are exploring your options, consider **[Microsoft Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)**.</span></span>

## <a name="do-i-need-a-siem-server"></a><span data-ttu-id="1e12a-109">是否需要 SIEM 伺服器？</span><span class="sxs-lookup"><span data-stu-id="1e12a-109">Do I need a SIEM server?</span></span>

<span data-ttu-id="1e12a-110">您是否需要 SIEM 伺服器取決於許多因素，例如貴組織的安全性需求及您的資料所在的位置。</span><span class="sxs-lookup"><span data-stu-id="1e12a-110">Whether you need a SIEM server depends on many factors, such as your organization's security requirements and where your data resides.</span></span> <span data-ttu-id="1e12a-111">Microsoft 365 也包含各種不同的安全性功能，可以滿足許多組織的安全性需求，沒有其他伺服器，例如 SIEM 伺服器。</span><span class="sxs-lookup"><span data-stu-id="1e12a-111">Microsoft 365 includes a wide variety of security features that meet many organizations' security needs without additional servers, such as a SIEM server.</span></span> <span data-ttu-id="1e12a-112">某些組織基於要求 SIEM 伺服器使用的特殊情況。</span><span class="sxs-lookup"><span data-stu-id="1e12a-112">Some organizations have special circumstances that require the use of a SIEM server.</span></span> <span data-ttu-id="1e12a-113">以下為一些範例：</span><span class="sxs-lookup"><span data-stu-id="1e12a-113">Here are some examples:</span></span>

- <span data-ttu-id="1e12a-114">*Fabrikam*上部署，而部分 （它們有混合式雲端部署） 在雲端中具有某些內容和應用程式。</span><span class="sxs-lookup"><span data-stu-id="1e12a-114">*Fabrikam* has some content and applications on premises, and some in the cloud (they have a hybrid cloud deployment).</span></span> <span data-ttu-id="1e12a-115">若要取得所有其內容及應用程式之間的安全性報告，Fabrikam 已實作 SIEM 伺服器。</span><span class="sxs-lookup"><span data-stu-id="1e12a-115">To get security reports across all their content and applications, Fabrikam has implemented a SIEM server.</span></span> 

- <span data-ttu-id="1e12a-116">*Contoso*為金融服務組織具有特別嚴格的安全性需求。</span><span class="sxs-lookup"><span data-stu-id="1e12a-116">*Contoso* is a financial services organization that has particularly stringent security requirements.</span></span> <span data-ttu-id="1e12a-117">若要利用其所需要的額外的安全性保護其環境已加入 SIEM 伺服器。</span><span class="sxs-lookup"><span data-stu-id="1e12a-117">They have added a SIEM server to their environment to take advantage of the extra security protection they require.</span></span>

## <a name="siem-server-integration-with-microsoft-365"></a><span data-ttu-id="1e12a-118">Microsoft 365 的 SIEM 伺服器整合</span><span class="sxs-lookup"><span data-stu-id="1e12a-118">SIEM server integration with Microsoft 365</span></span>

<span data-ttu-id="1e12a-119">SIEM 伺服器可以接收來自各種不同的 Microsoft 365 服務和應用程式的資料。</span><span class="sxs-lookup"><span data-stu-id="1e12a-119">A SIEM server can receive data from a wide variety of Microsoft 365 services and applications.</span></span> <span data-ttu-id="1e12a-120">下表列出數個 Microsoft 365 服務和應用程式，以及 SIEM 伺服器的輸入和了解更多的資源。</span><span class="sxs-lookup"><span data-stu-id="1e12a-120">The following table lists several Microsoft 365 services and applications, along with SIEM server inputs and resources to learn more.</span></span> 

| <span data-ttu-id="1e12a-121">Microsoft 365 服務或應用程式</span><span class="sxs-lookup"><span data-stu-id="1e12a-121">Microsoft 365 Service or Application</span></span> | <span data-ttu-id="1e12a-122">SIEM 伺服器的輸入/方法</span><span class="sxs-lookup"><span data-stu-id="1e12a-122">SIEM server inputs/methods</span></span> | <span data-ttu-id="1e12a-123">可深入了解的資源</span><span class="sxs-lookup"><span data-stu-id="1e12a-123">Resources to learn more</span></span> |
| --- | --- | --- |
| [<span data-ttu-id="1e12a-124">Office 365 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="1e12a-124">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)  | <span data-ttu-id="1e12a-125">稽核記錄</span><span class="sxs-lookup"><span data-stu-id="1e12a-125">Audit logs</span></span> | [<span data-ttu-id="1e12a-126">Office 365 進階威脅防護的 SIEM 整合</span><span class="sxs-lookup"><span data-stu-id="1e12a-126">SIEM integration with Office 365 Advanced Threat Protection</span></span>](siem-integration-with-office-365-ti.md) |
| [<span data-ttu-id="1e12a-127">Windows Defender 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="1e12a-127">Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/) | <span data-ttu-id="1e12a-128">裝載於 Azure 中的 HTTPS 端點</span><span class="sxs-lookup"><span data-stu-id="1e12a-128">HTTPS endpoint hosted in Azure</span></span> <br/><span data-ttu-id="1e12a-129">REST API</span><span class="sxs-lookup"><span data-stu-id="1e12a-129">REST API</span></span>| [<span data-ttu-id="1e12a-130">提取提醒您 SIEM 工具</span><span class="sxs-lookup"><span data-stu-id="1e12a-130">Pull alerts to your SIEM tools</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem) |
| [<span data-ttu-id="1e12a-131">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="1e12a-131">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) | <span data-ttu-id="1e12a-132">記錄整合</span><span class="sxs-lookup"><span data-stu-id="1e12a-132">Log integration</span></span> | [<span data-ttu-id="1e12a-133">Microsoft Cloud App Security 的 SIEM 整合</span><span class="sxs-lookup"><span data-stu-id="1e12a-133">SIEM integration with Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/siem) |

> [!TIP]
> <span data-ttu-id="1e12a-134">看看[Azure 護衛巨像](https://docs.microsoft.com/azure/sentinel/overview)。</span><span class="sxs-lookup"><span data-stu-id="1e12a-134">Take a look at [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview).</span></span> <span data-ttu-id="1e12a-135">Azure 警示隨附於 Microsoft 解決方案的連接器。</span><span class="sxs-lookup"><span data-stu-id="1e12a-135">Azure Sentinel comes with connectors for Microsoft solutions.</span></span> <span data-ttu-id="1e12a-136">這些連接器可供 「 現成 」，而且提供即時的整合。</span><span class="sxs-lookup"><span data-stu-id="1e12a-136">These connectors are available "out of the box" and provide for real-time integration.</span></span> <span data-ttu-id="1e12a-137">您可以使用 Azure 護衛巨像您的 Microsoft 威脅防護解決方案和 Microsoft 365 服務，包括 Office 365、 Azure AD，Azure ATP、 Microsoft Cloud App Security，等等。</span><span class="sxs-lookup"><span data-stu-id="1e12a-137">You can use Azure Sentinel with your Microsoft Threat Protection solutions and Microsoft 365 services, including Office 365, Azure AD, Azure ATP, Microsoft Cloud App Security, and more.</span></span>

### <a name="audit-logging-must-be-turned-on"></a><span data-ttu-id="1e12a-138">必須先開啟稽核記錄</span><span class="sxs-lookup"><span data-stu-id="1e12a-138">Audit logging must be turned on</span></span>

<span data-ttu-id="1e12a-139">請確定之前設定 SIEM 伺服器整合，開啟稽核記錄。</span><span class="sxs-lookup"><span data-stu-id="1e12a-139">Make sure that audit logging is turned on before you configure SIEM server integration.</span></span> 

- <span data-ttu-id="1e12a-140">OneDrive for Business 和 Azure Active Directory[稽核記錄在安全 & 合規性中心中已開啟](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off)SharePoint online，版本。</span><span class="sxs-lookup"><span data-stu-id="1e12a-140">For SharePoint Online, OneDrive for Business, and Azure Active Directory, [audit logging is turned on in the Security & Compliance Center](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off).</span></span>

- <span data-ttu-id="1e12a-141">針對 Exchange Online、[使用 Windows PowerShell 開啟稽核記錄](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing)。</span><span class="sxs-lookup"><span data-stu-id="1e12a-141">For Exchange Online, [audit logging is turned on with Windows PowerShell](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing).</span></span>
 
## <a name="more-resources"></a><span data-ttu-id="1e12a-142">其他資源</span><span class="sxs-lookup"><span data-stu-id="1e12a-142">More resources</span></span>

[<span data-ttu-id="1e12a-143">整合 Azure 資訊安全中心中的安全性解決方案</span><span class="sxs-lookup"><span data-stu-id="1e12a-143">Integrate security solutions in Azure Security Center</span></span>](https://docs.microsoft.com/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[<span data-ttu-id="1e12a-144">與 SIEM 整合 Microsoft Graph 安全性 API 提醒</span><span class="sxs-lookup"><span data-stu-id="1e12a-144">Integrate Microsoft Graph Security API alerts with a SIEM</span></span>](https://docs.microsoft.com/graph/security-integration)