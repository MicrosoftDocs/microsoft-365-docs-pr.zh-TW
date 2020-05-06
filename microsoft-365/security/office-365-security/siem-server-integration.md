---
title: SIEM server 與 Microsoft 365 服務與應用程式的整合
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
- seo-marvel-apr2020
description: 深入瞭解安全性資訊和事件管理（SIEM）伺服器與您的 Microsoft 365 雲端服務和應用程式的整合
ms.openlocfilehash: c52f24c6260c890b1f6d8612efacb78f9b08be86
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035257"
---
# <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a><span data-ttu-id="b6094-103">安全性資訊和事件管理（SIEM）伺服器與 Microsoft 365 服務和應用程式整合</span><span class="sxs-lookup"><span data-stu-id="b6094-103">Security Information and Event Management (SIEM) server integration with Microsoft 365 services and applications</span></span>

## <a name="summary"></a><span data-ttu-id="b6094-104">摘要</span><span class="sxs-lookup"><span data-stu-id="b6094-104">Summary</span></span>

<span data-ttu-id="b6094-105">您的組織是使用或規劃要取得安全性資訊和事件管理（SIEM）伺服器嗎？</span><span class="sxs-lookup"><span data-stu-id="b6094-105">Is your organization using or planning to get a Security Information and Event Management (SIEM) server?</span></span> <span data-ttu-id="b6094-106">您可能會想知道它如何與 Microsoft 365 或 Office 365 整合。</span><span class="sxs-lookup"><span data-stu-id="b6094-106">You might be wondering how it integrates with Microsoft 365 or Office 365.</span></span> <span data-ttu-id="b6094-107">本文提供您可以用來將 SIEM 伺服器與 Microsoft 365 服務和應用程式整合的資源清單。</span><span class="sxs-lookup"><span data-stu-id="b6094-107">This article provides a list of resources you can use to integrate your SIEM server with Microsoft 365 services and applications.</span></span>

> [!TIP]
> <span data-ttu-id="b6094-108">如果您還沒有 SIEM 伺服器，且正在探索您的選項，請考慮使用**[Microsoft Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)**。</span><span class="sxs-lookup"><span data-stu-id="b6094-108">If you don't have a SIEM server yet and are exploring your options, consider **[Microsoft Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)**.</span></span>

## <a name="do-i-need-a-siem-server"></a><span data-ttu-id="b6094-109">我需要 SIEM 伺服器嗎？</span><span class="sxs-lookup"><span data-stu-id="b6094-109">Do I need a SIEM server?</span></span>

<span data-ttu-id="b6094-110">您是否需要 SIEM server 取決於許多因素，例如組織的安全性需求和您的資料所在的位置。</span><span class="sxs-lookup"><span data-stu-id="b6094-110">Whether you need a SIEM server depends on many factors, such as your organization's security requirements and where your data resides.</span></span> <span data-ttu-id="b6094-111">Microsoft 365 包含各種各樣的安全性功能，可滿足許多組織的安全性需求，不需要其他伺服器，例如 SIEM server。</span><span class="sxs-lookup"><span data-stu-id="b6094-111">Microsoft 365 includes a wide variety of security features that meet many organizations' security needs without additional servers, such as a SIEM server.</span></span> <span data-ttu-id="b6094-112">有些組織需要使用 SIEM server 的特殊情況。</span><span class="sxs-lookup"><span data-stu-id="b6094-112">Some organizations have special circumstances that require the use of a SIEM server.</span></span> <span data-ttu-id="b6094-113">以下為一些範例：</span><span class="sxs-lookup"><span data-stu-id="b6094-113">Here are some examples:</span></span>

- <span data-ttu-id="b6094-114">*Fabrikam*的內部部署有一些內容和應用程式，有些則是雲端（他們有混合式雲端部署）。</span><span class="sxs-lookup"><span data-stu-id="b6094-114">*Fabrikam* has some content and applications on premises, and some in the cloud (they have a hybrid cloud deployment).</span></span> <span data-ttu-id="b6094-115">若要在其所有內容和應用程式中取得安全性報告，Fabrikam 已執行 SIEM 伺服器。</span><span class="sxs-lookup"><span data-stu-id="b6094-115">To get security reports across all their content and applications, Fabrikam has implemented a SIEM server.</span></span>

- <span data-ttu-id="b6094-116">*Contoso*是一種金融服務組織，具有特別嚴格的安全性需求。</span><span class="sxs-lookup"><span data-stu-id="b6094-116">*Contoso* is a financial services organization that has particularly stringent security requirements.</span></span> <span data-ttu-id="b6094-117">他們已將 SIEM 伺服器新增至其環境，以充分利用所需的額外安全性保護。</span><span class="sxs-lookup"><span data-stu-id="b6094-117">They have added a SIEM server to their environment to take advantage of the extra security protection they require.</span></span>

## <a name="siem-server-integration-with-microsoft-365"></a><span data-ttu-id="b6094-118">SIEM server 與 Microsoft 365 的整合</span><span class="sxs-lookup"><span data-stu-id="b6094-118">SIEM server integration with Microsoft 365</span></span>

<span data-ttu-id="b6094-119">SIEM server 可以從各種各樣的 Microsoft 365 服務和應用程式接收資料。</span><span class="sxs-lookup"><span data-stu-id="b6094-119">A SIEM server can receive data from a wide variety of Microsoft 365 services and applications.</span></span> <span data-ttu-id="b6094-120">下表列出數個 Microsoft 365 服務和應用程式，以及 SIEM server 輸入和資源以深入瞭解。</span><span class="sxs-lookup"><span data-stu-id="b6094-120">The following table lists several Microsoft 365 services and applications, along with SIEM server inputs and resources to learn more.</span></span>

||||
|---|---|---|
|<span data-ttu-id="b6094-121">**Microsoft 365 服務或應用程式**</span><span class="sxs-lookup"><span data-stu-id="b6094-121">**Microsoft 365 Service or Application**</span></span>|<span data-ttu-id="b6094-122">**SIEM 伺服器的輸入/方法**</span><span class="sxs-lookup"><span data-stu-id="b6094-122">**SIEM server inputs/methods**</span></span>|<span data-ttu-id="b6094-123">**可深入了解的資源**</span><span class="sxs-lookup"><span data-stu-id="b6094-123">**Resources to learn more**</span></span>|
|[<span data-ttu-id="b6094-124">Office 365 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="b6094-124">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)|<span data-ttu-id="b6094-125">稽核記錄</span><span class="sxs-lookup"><span data-stu-id="b6094-125">Audit logs</span></span>|[<span data-ttu-id="b6094-126">SIEM 與 Office 365 高級威脅防護的整合</span><span class="sxs-lookup"><span data-stu-id="b6094-126">SIEM integration with Office 365 Advanced Threat Protection</span></span>](siem-integration-with-office-365-ti.md)|
|[<span data-ttu-id="b6094-127">Windows Defender 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="b6094-127">Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)|<span data-ttu-id="b6094-128">Azure 中主控的 HTTPS 端點</span><span class="sxs-lookup"><span data-stu-id="b6094-128">HTTPS endpoint hosted in Azure</span></span> <br/><span data-ttu-id="b6094-129">REST API</span><span class="sxs-lookup"><span data-stu-id="b6094-129">REST API</span></span>|[<span data-ttu-id="b6094-130">將提醒納入您的 SIEM 工具</span><span class="sxs-lookup"><span data-stu-id="b6094-130">Pull alerts to your SIEM tools</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem)|
|[<span data-ttu-id="b6094-131">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="b6094-131">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)|<span data-ttu-id="b6094-132">記錄整合</span><span class="sxs-lookup"><span data-stu-id="b6094-132">Log integration</span></span>|[<span data-ttu-id="b6094-133">SIEM 與 Microsoft Cloud App Security 的整合</span><span class="sxs-lookup"><span data-stu-id="b6094-133">SIEM integration with Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/siem)|
|

> [!TIP]
> <span data-ttu-id="b6094-134">請看一下[Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)。</span><span class="sxs-lookup"><span data-stu-id="b6094-134">Take a look at [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview).</span></span> <span data-ttu-id="b6094-135">Azure Sentinel 隨附 Microsoft 解決方案的連接器。</span><span class="sxs-lookup"><span data-stu-id="b6094-135">Azure Sentinel comes with connectors for Microsoft solutions.</span></span> <span data-ttu-id="b6094-136">這些連接器可用於「現成」，並提供即時整合。</span><span class="sxs-lookup"><span data-stu-id="b6094-136">These connectors are available "out of the box" and provide for real-time integration.</span></span> <span data-ttu-id="b6094-137">您可以搭配 Microsoft 威脅防護解決方案和 Microsoft 365 服務（包括 Office 365、Azure AD、Azure ATP、Microsoft Cloud App Security 等等）搭配使用 Azure Sentinel。</span><span class="sxs-lookup"><span data-stu-id="b6094-137">You can use Azure Sentinel with your Microsoft Threat Protection solutions and Microsoft 365 services, including Office 365, Azure AD, Azure ATP, Microsoft Cloud App Security, and more.</span></span>

### <a name="audit-logging-must-be-turned-on"></a><span data-ttu-id="b6094-138">必須開啟審核記錄</span><span class="sxs-lookup"><span data-stu-id="b6094-138">Audit logging must be turned on</span></span>

<span data-ttu-id="b6094-139">設定 SIEM server 整合之前，請確定已開啟審核記錄。</span><span class="sxs-lookup"><span data-stu-id="b6094-139">Make sure that audit logging is turned on before you configure SIEM server integration.</span></span>

- <span data-ttu-id="b6094-140">針對 SharePoint 線上、商務 OneDrive 和 Azure Active Directory，[在安全性 & 規範中心開啟審核記錄](../../compliance/turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="b6094-140">For SharePoint Online, OneDrive for Business, and Azure Active Directory, [audit logging is turned on in the Security & Compliance Center](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="b6094-141">針對 Exchange Online，請參閱[管理信箱審核](../../compliance/enable-mailbox-auditing.md)。</span><span class="sxs-lookup"><span data-stu-id="b6094-141">For Exchange Online, see [Manage mailbox auditing](../../compliance/enable-mailbox-auditing.md).</span></span>

## <a name="more-resources"></a><span data-ttu-id="b6094-142">其他資源</span><span class="sxs-lookup"><span data-stu-id="b6094-142">More resources</span></span>

[<span data-ttu-id="b6094-143">整合 Azure Security Center 中的安全性解決方案</span><span class="sxs-lookup"><span data-stu-id="b6094-143">Integrate security solutions in Azure Security Center</span></span>](https://docs.microsoft.com/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[<span data-ttu-id="b6094-144">整合 Microsoft Graph 安全性 API 警示與 SIEM</span><span class="sxs-lookup"><span data-stu-id="b6094-144">Integrate Microsoft Graph Security API alerts with a SIEM</span></span>](https://docs.microsoft.com/graph/security-integration)
