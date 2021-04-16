---
title: 管理和 API 概觀
ms.reviewer: ''
description: 深入瞭解 Microsoft Defender for Endpoint 中的管理工具和 API 類別
keywords: 上架，api，siem，rbac，access，portal，integration，調查，回應，實體，實體，使用者內容，應用程式內容，資料流程
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 9e54fb5f2105f0a77c4b63e8d880135005c17168
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2021
ms.locfileid: "51862088"
---
# <a name="overview-of-management-and-apis"></a><span data-ttu-id="f3c50-104">管理和 API 概觀</span><span class="sxs-lookup"><span data-stu-id="f3c50-104">Overview of management and APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f3c50-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="f3c50-105">**Applies to:**</span></span>
- [<span data-ttu-id="f3c50-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="f3c50-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f3c50-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f3c50-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f3c50-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="f3c50-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="f3c50-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="f3c50-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mgt-apis-abovefoldlink)


<span data-ttu-id="f3c50-110">的 Defender for Endpoint 支援各種選項，以確保客戶可以輕鬆採用此平臺。</span><span class="sxs-lookup"><span data-stu-id="f3c50-110">Defender for Endpoint supports a wide variety of options to ensure that customers can easily adopt the platform.</span></span> 

<span data-ttu-id="f3c50-111">確認客戶環境和結構可以改變，但建立的 Defender 是以彈性和細微的方式控制，以滿足不同客戶的需求。</span><span class="sxs-lookup"><span data-stu-id="f3c50-111">Acknowledging that customer environments and structures can vary, Defender for Endpoint was created with flexibility and granular control to fit varying customer requirements.</span></span> 

## <a name="endpoint-onboarding-and-portal-access"></a><span data-ttu-id="f3c50-112">端點上架和入口網站存取</span><span class="sxs-lookup"><span data-stu-id="f3c50-112">Endpoint onboarding and portal access</span></span> 

<span data-ttu-id="f3c50-113">裝置上架已完全整合至 Microsoft 端點管理員和 Microsoft Intune for 用戶端裝置和 Azure Security Center for server 裝置，提供設定、部署和監控的完整端對端體驗。</span><span class="sxs-lookup"><span data-stu-id="f3c50-113">Device onboarding is fully integrated into Microsoft Endpoint Manager and Microsoft Intune for client devices and Azure Security Center for server devices, providing complete end-to-end experience of configuration, deployment, and monitoring.</span></span> <span data-ttu-id="f3c50-114">此外，Microsoft Defender for Endpoint 會支援用於裝置管理的群組原則及其他協力廠商工具。</span><span class="sxs-lookup"><span data-stu-id="f3c50-114">In addition, Microsoft Defender for Endpoint supports Group Policy and other third-party tools used for devices management.</span></span>

<span data-ttu-id="f3c50-115">Defender for Endpoint 提供精細的控制，可讓具有入口網站存取權的使用者透過角色型存取控制 (RBAC) 的彈性來查看並執行。</span><span class="sxs-lookup"><span data-stu-id="f3c50-115">Defender for Endpoint provides fine-grained control over what users with access to the portal can see and do through the flexibility of role-based access control (RBAC).</span></span> <span data-ttu-id="f3c50-116">RBAC 模型支援所有的安全性小組結構類型：</span><span class="sxs-lookup"><span data-stu-id="f3c50-116">The RBAC model supports all flavors of security teams structure:</span></span>
- <span data-ttu-id="f3c50-117">全域分散式組織和安全小組</span><span class="sxs-lookup"><span data-stu-id="f3c50-117">Globally distributed organizations and security teams</span></span>
- <span data-ttu-id="f3c50-118">分級模型安全性運作小組</span><span class="sxs-lookup"><span data-stu-id="f3c50-118">Tiered model security operations teams</span></span>
- <span data-ttu-id="f3c50-119">以單一集中式全域安全性運作小組進行完全隔離的分部</span><span class="sxs-lookup"><span data-stu-id="f3c50-119">Fully segregated divisions with single centralized global security operations teams</span></span> 

## <a name="available-apis"></a><span data-ttu-id="f3c50-120">可用 APIs</span><span class="sxs-lookup"><span data-stu-id="f3c50-120">Available APIs</span></span>
<span data-ttu-id="f3c50-121">Microsoft Defender for Endpoint 方案是以整合就緒平臺為基礎。</span><span class="sxs-lookup"><span data-stu-id="f3c50-121">The Microsoft Defender for Endpoint solution is built on top of an integration-ready platform.</span></span>

<span data-ttu-id="f3c50-122">「！的 Defender」會透過一組程式設計 APIs 公開其資料和動作。</span><span class="sxs-lookup"><span data-stu-id="f3c50-122">Defender for Endpoint exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="f3c50-123">這些 APIs 可讓您以使用 Defender for Endpoint 功能來自動化工作流程及創新。</span><span class="sxs-lookup"><span data-stu-id="f3c50-123">Those APIs will enable you to automate workflows and innovate based on Defender for Endpoint capabilities.</span></span>

![Microsoft Defender for Endpoint 中可用 API 和整合的影像](images/mdatp-apis.png)  

<span data-ttu-id="f3c50-125">Endpoint APIs 的 Defender 可以分為三種：</span><span class="sxs-lookup"><span data-stu-id="f3c50-125">The Defender for Endpoint APIs can be grouped into three:</span></span>
- <span data-ttu-id="f3c50-126">Microsoft Defender for Endpoint APIs</span><span class="sxs-lookup"><span data-stu-id="f3c50-126">Microsoft Defender for Endpoint APIs</span></span> 
- <span data-ttu-id="f3c50-127">原始資料串流 API</span><span class="sxs-lookup"><span data-stu-id="f3c50-127">Raw data streaming API</span></span>
- <span data-ttu-id="f3c50-128">SIEM 整合</span><span class="sxs-lookup"><span data-stu-id="f3c50-128">SIEM integration</span></span>

## <a name="microsoft-defender-for-endpoint-apis"></a><span data-ttu-id="f3c50-129">Microsoft Defender for Endpoint APIs</span><span class="sxs-lookup"><span data-stu-id="f3c50-129">Microsoft Defender for Endpoint APIs</span></span>

<span data-ttu-id="f3c50-130">Defender for Endpoint 提供分層 API 模型，以結構化、清晰且便於使用的模型公開資料和功能，透過標準 Azure AD 型驗證和授權模型公開，允許使用者或 SaaS 應用程式的內容存取。</span><span class="sxs-lookup"><span data-stu-id="f3c50-130">Defender for Endpoint offers a layered API model exposing data and capabilities in a structured, clear, and easy to use model, exposed through a standard Azure  AD-based authentication and authorization model allowing access in context of users or SaaS applications.</span></span> <span data-ttu-id="f3c50-131">API 模型設計為以一致的形式公開實體和功能。</span><span class="sxs-lookup"><span data-stu-id="f3c50-131">The API model was designed to expose entities and capabilities in a consistent form.</span></span> 

<span data-ttu-id="f3c50-132">觀賞這段影片，以快速瞭解如何使用 Defender 的 Endpoint APIs。</span><span class="sxs-lookup"><span data-stu-id="f3c50-132">Watch this video for a quick overview of Defender for Endpoint's APIs.</span></span> 
>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4d73M]

<span data-ttu-id="f3c50-133">**調查 API** 公開大量用於端點公開計算或「已分析」實體的 Defender (例如，裝置、使用者、檔案) 和分散的事件 (例如，程式建立及檔案建立) ，這通常會說明與實體相關的行為，並可透過調查介面存取資料，以允許以查詢為基礎的資料存取。</span><span class="sxs-lookup"><span data-stu-id="f3c50-133">The **Investigation API** exposes the richness of Defender for Endpoint - exposing calculated or 'profiled' entities (for example, device, user, and file) and discrete events (for example, process creation and file creation) which typically describes a behavior related to an entity, enabling access to data via investigation interfaces allowing a query-based access to data.</span></span> <span data-ttu-id="f3c50-134">如需詳細資訊，請參閱 [支援的 APIs](exposed-apis-list.md)。</span><span class="sxs-lookup"><span data-stu-id="f3c50-134">For more information, see [Supported APIs](exposed-apis-list.md).</span></span>

<span data-ttu-id="f3c50-135">**回應 API** 公開在服務和裝置上採取動作的能力，讓客戶能夠攝取指示器、管理設定、警示狀態，以及在裝置上採取回應動作，例如隔離裝置與網路、隔離檔案等等。</span><span class="sxs-lookup"><span data-stu-id="f3c50-135">The **Response API** exposes the ability to take actions in the service and on devices, enabling customers to ingest indicators, manage settings, alert status, as well as take response actions on devices programmatically such as isolate devices from the network, quarantine files, and others.</span></span> 

## <a name="raw-data-streaming-api"></a><span data-ttu-id="f3c50-136">原始資料串流 API</span><span class="sxs-lookup"><span data-stu-id="f3c50-136">Raw data streaming API</span></span> 
<span data-ttu-id="f3c50-137">使用 Defender for Endpoint raw data stream API，可讓客戶在單一資料流程中發生即時事件及警示，以提供低延遲、高輸送量傳遞機制。</span><span class="sxs-lookup"><span data-stu-id="f3c50-137">Defender for Endpoint raw data streaming API provides the ability for customers to ship real-time events and alerts from their instances as they occur within a single data stream, providing a low latency, high throughput delivery mechanism.</span></span>

<span data-ttu-id="f3c50-138">將 Endpoint 事件資訊的 Defender 事件資訊直接推入 Azure 存放區，以進行長期資料保留，或透過視覺化服務或其他資料處理引擎使用 Azure 事件中心以取得消耗。</span><span class="sxs-lookup"><span data-stu-id="f3c50-138">The Defender for Endpoint event information is pushed directly to Azure storage for long-term data retention, or to Azure Event Hubs for consumption by visualization services or additional data processing engines.</span></span> 

<span data-ttu-id="f3c50-139">如需詳細資訊，請參閱 [Raw data 流式 API](raw-data-export.md)。</span><span class="sxs-lookup"><span data-stu-id="f3c50-139">For more information, see [Raw data streaming API](raw-data-export.md).</span></span>


## <a name="siem-api"></a><span data-ttu-id="f3c50-140">SIEM API</span><span class="sxs-lookup"><span data-stu-id="f3c50-140">SIEM API</span></span>
<span data-ttu-id="f3c50-141">當您啟用安全性資訊和事件管理 (SIEM) 整合時，它可讓您使用 SIEM 解決方案或直接連線至偵測到的 REST API，從 Microsoft Defender Security Center 提取偵測。</span><span class="sxs-lookup"><span data-stu-id="f3c50-141">When you enable security information and event management (SIEM) integration, it allows you to pull detections from Microsoft Defender Security Center using your SIEM solution or by connecting directly to the detections REST API.</span></span> <span data-ttu-id="f3c50-142">這會以預先填入的值來啟動 SIEM connector access 詳細資料區段，且會在您的 Azure Active Directory (Azure AD) 租使用者下建立應用程式。</span><span class="sxs-lookup"><span data-stu-id="f3c50-142">This activates the SIEM connector access details section with pre-populated values and an application is created under your Azure Active Directory (Azure AD) tenant.</span></span> <span data-ttu-id="f3c50-143">如需詳細資訊，請參閱 [SIEM integration](enable-siem-integration.md)。</span><span class="sxs-lookup"><span data-stu-id="f3c50-143">For more information, see [SIEM integration](enable-siem-integration.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="f3c50-144">相關主題</span><span class="sxs-lookup"><span data-stu-id="f3c50-144">Related topics</span></span>
- [<span data-ttu-id="f3c50-145">存取 Microsoft Defender for Endpoint APIs </span><span class="sxs-lookup"><span data-stu-id="f3c50-145">Access the Microsoft Defender for Endpoint APIs </span></span>](apis-intro.md)
- [<span data-ttu-id="f3c50-146">支援的 APIs</span><span class="sxs-lookup"><span data-stu-id="f3c50-146">Supported APIs</span></span>](exposed-apis-list.md)
- [<span data-ttu-id="f3c50-147">技術合作夥伴機會</span><span class="sxs-lookup"><span data-stu-id="f3c50-147">Technical partner opportunities</span></span>](partner-integration.md)

