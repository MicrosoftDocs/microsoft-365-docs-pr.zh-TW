---
title: Microsoft 365 Defender API 概觀
description: 瞭解 Microsoft 365 Defender 中可用的 API
keywords: api， apis， overview， incident， incidents， threat搜尋， microsoft 365 defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 8e06d4b4f7c895b532091c73e8269411fb38bf21
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930999"
---
# <a name="overview-of--microsoft-365-defender-apis"></a><span data-ttu-id="66e7b-104">Microsoft 365 Defender API 概觀</span><span class="sxs-lookup"><span data-stu-id="66e7b-104">Overview of  Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="66e7b-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="66e7b-105">**Applies to:**</span></span>

- <span data-ttu-id="66e7b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="66e7b-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="66e7b-107">部分與發行前產品有關的資訊，在正式發行之前可能會大幅修改。</span><span class="sxs-lookup"><span data-stu-id="66e7b-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="66e7b-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="66e7b-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="66e7b-109">Microsoft 365 Defender 建在整合就緒的平臺上。</span><span class="sxs-lookup"><span data-stu-id="66e7b-109">Microsoft 365 Defender is built on top of an integration-ready platform.</span></span>

<span data-ttu-id="66e7b-110">使用 Microsoft 365 Defender API，根據共用事件和進一搜尋資料表自動化工作流程。</span><span class="sxs-lookup"><span data-stu-id="66e7b-110">Use the Microsoft 365 Defender APIs to automate workflows based on the shared incident and advanced hunting tables.</span></span>

- <span data-ttu-id="66e7b-111">**[結合事件佇列](api-incident.md)** - 在事件 API 下將完整攻擊範圍及所有受影響資產分組，以著重于關鍵專案。</span><span class="sxs-lookup"><span data-stu-id="66e7b-111">**[Combined incidents queue](api-incident.md)** - Focus on what's critical by grouping the full attack scope and all impacted assets together under the incident API.</span></span>

- <span data-ttu-id="66e7b-112">**[搜尋跨產品](api-advanced-hunting.md)** 威脅 - 利用您安全性小組的組織知識，建立自己的自訂查詢來篩選收集于多個保護產品上的原始資料，以尋找入侵符號。</span><span class="sxs-lookup"><span data-stu-id="66e7b-112">**[Cross-product threat hunting](api-advanced-hunting.md)** - Leverage your security team's organizational knowledge to hunt for signs of compromise, by creating your own custom queries to sift over raw data collected across multiple protection products.</span></span>

<span data-ttu-id="66e7b-113">除了這些 Microsoft 365 Defender 專用 API，我們每一個其他安全性產品都公開了其他 [API，](api-articles.md) 説明您充分利用其獨特功能。</span><span class="sxs-lookup"><span data-stu-id="66e7b-113">Along with these Microsoft 365 Defender-specific APIs, each of our other security products expose [additional APIs](api-articles.md) to help you take advantage of their unique capabilities.</span></span>

## <a name="learn-more"></a><span data-ttu-id="66e7b-114">深入了解</span><span class="sxs-lookup"><span data-stu-id="66e7b-114">Learn more</span></span>

| <span data-ttu-id="66e7b-115">**瞭解如何存取 API**</span><span class="sxs-lookup"><span data-stu-id="66e7b-115">**Understand how to access the APIs**</span></span> |
|-|
| [<span data-ttu-id="66e7b-116">瞭解 API 配額與授權</span><span class="sxs-lookup"><span data-stu-id="66e7b-116">Learn about API quotas and licensing</span></span>](api-terms.md) |
| [<span data-ttu-id="66e7b-117">存取 Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="66e7b-117">Access the Microsoft 365 Defender APIs</span></span>](api-access.md) |
| <span data-ttu-id="66e7b-118">**Build apps**</span><span class="sxs-lookup"><span data-stu-id="66e7b-118">**Build apps**</span></span> |
| [<span data-ttu-id="66e7b-119">建立'Hello world'App</span><span class="sxs-lookup"><span data-stu-id="66e7b-119">Create a 'Hello world' app</span></span>](api-hello-world.md) |
| [<span data-ttu-id="66e7b-120">建立應用程式以代表使用者存取 Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="66e7b-120">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>](api-create-app-user-context.md) |
| [<span data-ttu-id="66e7b-121">建立應用程式以在沒有使用者的情況下存取 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="66e7b-121">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md) |
| [<span data-ttu-id="66e7b-122">建立具有 Microsoft 365 Defender API 多租使用者合作夥伴存取權的應用程式</span><span class="sxs-lookup"><span data-stu-id="66e7b-122">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md) |
| <span data-ttu-id="66e7b-123">**疑難排解及維護您的應用程式**</span><span class="sxs-lookup"><span data-stu-id="66e7b-123">**Troubleshoot and maintain your apps**</span></span> |
| [<span data-ttu-id="66e7b-124">瞭解 API 錯誤碼</span><span class="sxs-lookup"><span data-stu-id="66e7b-124">Understand API error codes</span></span>](api-error-codes.md) |
| [<span data-ttu-id="66e7b-125">使用 Azure 金鑰庫管理應用程式中的秘訣</span><span class="sxs-lookup"><span data-stu-id="66e7b-125">Manage secrets in your apps with Azure Key Vault</span></span>](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/) |
| [<span data-ttu-id="66e7b-126">將 OAuth 2.0 授權用於使用者登錄</span><span class="sxs-lookup"><span data-stu-id="66e7b-126">Implement OAuth 2.0 authorization for user sign in</span></span>](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code) |
