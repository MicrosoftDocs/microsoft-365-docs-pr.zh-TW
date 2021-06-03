---
title: Microsoft 365 Defender APIs 概述
description: 深入瞭解 Microsoft 365 Defender 中可用的 APIs
keywords: api，api，綜述，事件，事件，威脅搜尋，microsoft 365 defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: b19a6072be5f97b90c117f053ccae4593587c43d
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730891"
---
# <a name="overview-of--microsoft-365-defender-apis"></a><span data-ttu-id="337dd-104">Microsoft 365 Defender APIs 概述</span><span class="sxs-lookup"><span data-stu-id="337dd-104">Overview of  Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="337dd-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="337dd-105">**Applies to:**</span></span>

- <span data-ttu-id="337dd-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="337dd-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="337dd-107">部分資訊與發行前版本產品有關，在正式發行之前可能會實質上進行修改。</span><span class="sxs-lookup"><span data-stu-id="337dd-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="337dd-108">Microsoft 對此處提供的資訊，不提供任何明確或隱含的瑕疵擔保。</span><span class="sxs-lookup"><span data-stu-id="337dd-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="337dd-109">Microsoft 365Defender 是以整合就緒平臺為基礎。</span><span class="sxs-lookup"><span data-stu-id="337dd-109">Microsoft 365 Defender is built on top of an integration-ready platform.</span></span>

<span data-ttu-id="337dd-110">使用 Microsoft 365 Defender APIs，以自動化以共用事件及高級搜尋表格為基礎的工作流程。</span><span class="sxs-lookup"><span data-stu-id="337dd-110">Use the Microsoft 365 Defender APIs to automate workflows based on the shared incident and advanced hunting tables.</span></span>

- <span data-ttu-id="337dd-111">**[結合的事件佇列](api-incident.md)** -著重于將完整的攻擊範圍和所有受影響的資產分組在事件 API 底下的重要事項。</span><span class="sxs-lookup"><span data-stu-id="337dd-111">**[Combined incidents queue](api-incident.md)** - Focus on what's critical by grouping the full attack scope and all impacted assets together under the incident API.</span></span>

- <span data-ttu-id="337dd-112">**[跨產品威脅搜尋](api-advanced-hunting.md)** -利用您的安全小組的組織知識，透過建立您自己的自訂查詢，以透過跨多個保護產品所收集的原始資料來進行保護，以尋找損害的跡象。</span><span class="sxs-lookup"><span data-stu-id="337dd-112">**[Cross-product threat hunting](api-advanced-hunting.md)** - Leverage your security team's organizational knowledge to hunt for signs of compromise, by creating your own custom queries to sift over raw data collected across multiple protection products.</span></span>

<span data-ttu-id="337dd-113">使用 [流式 API](../defender-endpoint/raw-data-export.md) ，在單一資料流程中發生即時事件及來自實例的警示。</span><span class="sxs-lookup"><span data-stu-id="337dd-113">Use the [Streaming API](../defender-endpoint/raw-data-export.md) to ship real-time events and alerts from instances as they occur within a single data stream.</span></span>


<span data-ttu-id="337dd-114">除了這些 Microsoft 365 Defender 特有 APIs 之外，其他所有的安全性產品都會公開[其他 APIs](api-articles.md) ，以協助您利用其獨特的功能。</span><span class="sxs-lookup"><span data-stu-id="337dd-114">Along with these Microsoft 365 Defender-specific APIs, each of our other security products expose [additional APIs](api-articles.md) to help you take advantage of their unique capabilities.</span></span>


> [!NOTE]
> <span data-ttu-id="337dd-115">轉換至統一入口網站不應該影響以 Microsoft Defender for Endpoint APIs 為基礎的 PowerBi 儀表板。</span><span class="sxs-lookup"><span data-stu-id="337dd-115">The transition to the unified portal should not affect the PowerBi dashboards based on Microsoft Defender for Endpoint APIs.</span></span> <span data-ttu-id="337dd-116">不論互動式入口網站轉換的情況為何，您都可以繼續使用現有的 APIs。</span><span class="sxs-lookup"><span data-stu-id="337dd-116">You can continue to work with the existing APIs regardless of the interactive portal transition.</span></span>


## <a name="learn-more"></a><span data-ttu-id="337dd-117">深入了解</span><span class="sxs-lookup"><span data-stu-id="337dd-117">Learn more</span></span>

| <span data-ttu-id="337dd-118">**瞭解如何存取 APIs**</span><span class="sxs-lookup"><span data-stu-id="337dd-118">**Understand how to access the APIs**</span></span> |
|-|
| [<span data-ttu-id="337dd-119">深入瞭解 API 配額和授權</span><span class="sxs-lookup"><span data-stu-id="337dd-119">Learn about API quotas and licensing</span></span>](api-terms.md) |
| [<span data-ttu-id="337dd-120">存取 Microsoft 365 Defender APIs</span><span class="sxs-lookup"><span data-stu-id="337dd-120">Access the Microsoft 365 Defender APIs</span></span>](api-access.md) |
| <span data-ttu-id="337dd-121">**Build apps**</span><span class="sxs-lookup"><span data-stu-id="337dd-121">**Build apps**</span></span> |
| [<span data-ttu-id="337dd-122">建立 "Hello world" 應用程式</span><span class="sxs-lookup"><span data-stu-id="337dd-122">Create a 'Hello world' app</span></span>](api-hello-world.md) |
| [<span data-ttu-id="337dd-123">建立應用程式，以代表使用者存取 Microsoft 365 Defender APIs</span><span class="sxs-lookup"><span data-stu-id="337dd-123">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>](api-create-app-user-context.md) |
| [<span data-ttu-id="337dd-124">建立應用程式以存取沒有使用者的 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="337dd-124">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md) |
| [<span data-ttu-id="337dd-125">建立具有 Microsoft 365 Defender APIs 的多承租人合作夥伴存取權的應用程式</span><span class="sxs-lookup"><span data-stu-id="337dd-125">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md) |
| <span data-ttu-id="337dd-126">**疑難排解及維護您的應用程式**</span><span class="sxs-lookup"><span data-stu-id="337dd-126">**Troubleshoot and maintain your apps**</span></span> |
| [<span data-ttu-id="337dd-127">瞭解 API 錯誤代碼</span><span class="sxs-lookup"><span data-stu-id="337dd-127">Understand API error codes</span></span>](api-error-codes.md) |
| [<span data-ttu-id="337dd-128">使用 Azure Key Vault 管理應用程式中的機密</span><span class="sxs-lookup"><span data-stu-id="337dd-128">Manage secrets in your apps with Azure Key Vault</span></span>](/learn/modules/manage-secrets-with-azure-key-vault/) |
| [<span data-ttu-id="337dd-129">針對使用者登入執行 OAuth 2.0 授權</span><span class="sxs-lookup"><span data-stu-id="337dd-129">Implement OAuth 2.0 authorization for user sign in</span></span>](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code) |