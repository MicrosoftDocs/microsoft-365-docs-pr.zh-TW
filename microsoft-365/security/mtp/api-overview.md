---
title: Microsoft 365 Defender APIs 概述
description: 深入瞭解 Microsoft 365 Defender 中可用的 APIs
keywords: api，api，綜述，事件，事件，威脅搜尋，microsoft 365 defender
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 1a75a561e60c05208e8ea302505f9644ac0bc044
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719187"
---
# <a name="overview-of--microsoft-365-defender-apis"></a><span data-ttu-id="a5313-104">Microsoft 365 Defender APIs 概述</span><span class="sxs-lookup"><span data-stu-id="a5313-104">Overview of  Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="a5313-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="a5313-105">**Applies to:**</span></span>

- <span data-ttu-id="a5313-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a5313-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a5313-107">一些與 prereleased 產品相關的資訊，在正式發行之前，可能會受到大量修改。</span><span class="sxs-lookup"><span data-stu-id="a5313-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="a5313-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="a5313-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="a5313-109">Microsoft 365 Defender 是以整合就緒平臺為基礎。</span><span class="sxs-lookup"><span data-stu-id="a5313-109">Microsoft 365 Defender is built on top of an integration-ready platform.</span></span>

<span data-ttu-id="a5313-110">使用 Microsoft 365 Defender APIs，根據共用的事件和高級搜尋表來自動化工作流程。</span><span class="sxs-lookup"><span data-stu-id="a5313-110">Use the Microsoft 365 Defender APIs to automate workflows based on the shared incident and advanced hunting tables.</span></span>

- <span data-ttu-id="a5313-111">**[結合的事件佇列](api-incident.md)** -著重于將完整的攻擊範圍和所有受影響的資產分組在事件 API 底下的重要事項。</span><span class="sxs-lookup"><span data-stu-id="a5313-111">**[Combined incidents queue](api-incident.md)** - Focus on what's critical by grouping the full attack scope and all impacted assets together under the incident API.</span></span>

- <span data-ttu-id="a5313-112">**[跨產品威脅搜尋](api-advanced-hunting.md)** -利用您的安全小組的組織知識，透過建立您自己的自訂查詢，以透過跨多個保護產品所收集的原始資料來進行保護，以尋找損害的跡象。</span><span class="sxs-lookup"><span data-stu-id="a5313-112">**[Cross-product threat hunting](api-advanced-hunting.md)** - Leverage your security team's organizational knowledge to hunt for signs of compromise, by creating your own custom queries to sift over raw data collected across multiple protection products.</span></span>

<span data-ttu-id="a5313-113">除了這些 Microsoft 365 Defender 特有的 APIs 之外，其他所有的安全性產品都會公開 [其他 APIs](api-articles.md) ，以協助您利用其獨特的功能。</span><span class="sxs-lookup"><span data-stu-id="a5313-113">Along with these Microsoft 365 Defender-specific APIs, each of our other security products expose [additional APIs](api-articles.md) to help you take advantage of their unique capabilities.</span></span>

## <a name="learn-more"></a><span data-ttu-id="a5313-114">深入了解</span><span class="sxs-lookup"><span data-stu-id="a5313-114">Learn more</span></span>

| <span data-ttu-id="a5313-115">**瞭解如何存取 APIs**</span><span class="sxs-lookup"><span data-stu-id="a5313-115">**Understand how to access the APIs**</span></span> |
|-|
| [<span data-ttu-id="a5313-116">深入瞭解 API 配額和授權</span><span class="sxs-lookup"><span data-stu-id="a5313-116">Learn about API quotas and licensing</span></span>](api-terms.md) |
| [<span data-ttu-id="a5313-117">存取 Microsoft 365 Defender APIs</span><span class="sxs-lookup"><span data-stu-id="a5313-117">Access the Microsoft 365 Defender APIs</span></span>](api-access.md) |
| <span data-ttu-id="a5313-118">**Build apps**</span><span class="sxs-lookup"><span data-stu-id="a5313-118">**Build apps**</span></span> |
| [<span data-ttu-id="a5313-119">建立 "Hello world" 應用程式</span><span class="sxs-lookup"><span data-stu-id="a5313-119">Create a 'Hello world' app</span></span>](api-hello-world.md) |
| [<span data-ttu-id="a5313-120">建立應用程式以代表使用者存取 Microsoft 365 Defender APIs</span><span class="sxs-lookup"><span data-stu-id="a5313-120">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>](api-create-app-user-context.md) |
| [<span data-ttu-id="a5313-121">建立應用程式以存取沒有使用者的 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a5313-121">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md) |
| [<span data-ttu-id="a5313-122">建立具有對 Microsoft 365 Defender APIs 的多承租人合作夥伴存取權的應用程式</span><span class="sxs-lookup"><span data-stu-id="a5313-122">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md) |
| <span data-ttu-id="a5313-123">**疑難排解及維護您的應用程式**</span><span class="sxs-lookup"><span data-stu-id="a5313-123">**Troubleshoot and maintain your apps**</span></span> |
| [<span data-ttu-id="a5313-124">瞭解 API 錯誤代碼</span><span class="sxs-lookup"><span data-stu-id="a5313-124">Understand API error codes</span></span>](api-error-codes.md) |
| [<span data-ttu-id="a5313-125">使用 Azure Key Vault 管理應用程式中的機密</span><span class="sxs-lookup"><span data-stu-id="a5313-125">Manage secrets in your apps with Azure Key Vault</span></span>](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/) |
| [<span data-ttu-id="a5313-126">針對使用者登入執行 OAuth 2.0 授權</span><span class="sxs-lookup"><span data-stu-id="a5313-126">Implement OAuth 2.0 authorization for user sign in</span></span>](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code) |
