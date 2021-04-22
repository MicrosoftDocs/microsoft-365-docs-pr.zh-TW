---
title: Microsoft Defender for Endpoint 中的 API Explorer
ms.reviewer: ''
description: 使用 API Explorer 來構造和執行任何可用 API 的 API 查詢、測試及傳送要求
keywords: api、explorer、send、request、get、post、
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
ms.openlocfilehash: b8d0d991e46464bae3b4d21d6218b9b3b2d2b4cb
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51930110"
---
# <a name="api-explorer"></a><span data-ttu-id="0b3f1-104">API Explorer</span><span class="sxs-lookup"><span data-stu-id="0b3f1-104">API Explorer</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0b3f1-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="0b3f1-105">**Applies to:**</span></span>
- [<span data-ttu-id="0b3f1-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="0b3f1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)


<span data-ttu-id="0b3f1-107">Microsoft Defender for Endpoint API Explorer 是一種工具，可協助您深入探索不同的 Defender for Endpoint APIs。</span><span class="sxs-lookup"><span data-stu-id="0b3f1-107">The Microsoft Defender for Endpoint API Explorer is a tool that helps you explore various Defender for Endpoint APIs interactively.</span></span> 

<span data-ttu-id="0b3f1-108">API Explorer 可讓您輕鬆地構造和執行任何可用之 Defender API 端點的 API 查詢、測試及傳送要求。</span><span class="sxs-lookup"><span data-stu-id="0b3f1-108">The API Explorer makes it easy to construct and do API queries, test, and send requests for any available Defender for Endpoint API endpoint.</span></span> <span data-ttu-id="0b3f1-109">使用 API Explorer 來採取動作或尋找可能尚未透過使用者介面提供的資料。</span><span class="sxs-lookup"><span data-stu-id="0b3f1-109">Use the API Explorer to take actions or find data that might not yet be available through the user interface.</span></span>

<span data-ttu-id="0b3f1-110">工具在應用程式開發期間很有用。</span><span class="sxs-lookup"><span data-stu-id="0b3f1-110">The tool is useful during app development.</span></span> <span data-ttu-id="0b3f1-111">它可讓您執行遵循使用者存取設定的 API 查詢，以減少產生存取權杖的需求。</span><span class="sxs-lookup"><span data-stu-id="0b3f1-111">It allows you to perform API queries that respect your user access settings, reducing the need to generate access tokens.</span></span>

<span data-ttu-id="0b3f1-112">您也可以使用工具來流覽範例查詢、複製結果代碼範例，以及產生調試資訊的畫廊。</span><span class="sxs-lookup"><span data-stu-id="0b3f1-112">You can also use the tool to explore the gallery of sample queries, copy result code samples, and generate debug information.</span></span>

<span data-ttu-id="0b3f1-113">透過 API Explorer，您可以：</span><span class="sxs-lookup"><span data-stu-id="0b3f1-113">With the API Explorer, you can:</span></span>

- <span data-ttu-id="0b3f1-114">對任何方法執行要求，並且即時查看回應</span><span class="sxs-lookup"><span data-stu-id="0b3f1-114">Run requests for any method and see responses in real-time</span></span>
- <span data-ttu-id="0b3f1-115">快速流覽 API 範例，並瞭解其所支援的參數</span><span class="sxs-lookup"><span data-stu-id="0b3f1-115">Quickly browse through the API samples and learn what parameters they support</span></span>
- <span data-ttu-id="0b3f1-116">輕鬆進行 API 呼叫;在管理入口網站登入之外，不需要驗證</span><span class="sxs-lookup"><span data-stu-id="0b3f1-116">Make API calls with ease; no need to authenticate beyond the management portal sign in</span></span>

## <a name="access-api-explorer"></a><span data-ttu-id="0b3f1-117">Access API Explorer</span><span class="sxs-lookup"><span data-stu-id="0b3f1-117">Access API Explorer</span></span>

<span data-ttu-id="0b3f1-118">從左導覽功能表中，選取 [**夥伴] & APIs**  >  **API Explorer**。</span><span class="sxs-lookup"><span data-stu-id="0b3f1-118">From the left navigation menu, select **Partners & APIs** > **API Explorer**.</span></span>

## <a name="supported-apis"></a><span data-ttu-id="0b3f1-119">支援的 APIs</span><span class="sxs-lookup"><span data-stu-id="0b3f1-119">Supported APIs</span></span>

<span data-ttu-id="0b3f1-120">API Explorer 支援所有由 Defender for Endpoint 所提供的 APIs。</span><span class="sxs-lookup"><span data-stu-id="0b3f1-120">API Explorer supports all the APIs offered by Defender for Endpoint.</span></span>
  
<span data-ttu-id="0b3f1-121">[APIs 檔](apis-intro.md)中提供支援的 APIs 清單。</span><span class="sxs-lookup"><span data-stu-id="0b3f1-121">The list of supported APIs is available in the [APIs documentation](apis-intro.md).</span></span> 

## <a name="get-started-with-the-api-explorer"></a><span data-ttu-id="0b3f1-122">開始使用 API Explorer</span><span class="sxs-lookup"><span data-stu-id="0b3f1-122">Get started with the API Explorer</span></span>

1. <span data-ttu-id="0b3f1-123">在左窗格中，有您可以使用的範例要求清單。</span><span class="sxs-lookup"><span data-stu-id="0b3f1-123">In the left pane, there is a list of sample requests that you can use.</span></span> 
2. <span data-ttu-id="0b3f1-124">遵循連結，然後按一下 [ **執行查詢**]。</span><span class="sxs-lookup"><span data-stu-id="0b3f1-124">Follow the links and click **Run query**.</span></span> 

<span data-ttu-id="0b3f1-125">某些範例可能需要在 URL 中指定參數，例如 {machine ID}。</span><span class="sxs-lookup"><span data-stu-id="0b3f1-125">Some of the samples may require specifying a parameter in the URL, for example, {machine- ID}.</span></span>

## <a name="faq"></a><span data-ttu-id="0b3f1-126">常見問題集</span><span class="sxs-lookup"><span data-stu-id="0b3f1-126">FAQ</span></span>

<span data-ttu-id="0b3f1-127">**我需要有 API 權杖才能使用 API Explorer 嗎？**</span><span class="sxs-lookup"><span data-stu-id="0b3f1-127">**Do I need to have an API token to use the API Explorer?**</span></span> <br>
<span data-ttu-id="0b3f1-128">不需要存取 API 的認證。</span><span class="sxs-lookup"><span data-stu-id="0b3f1-128">Credentials to access an API aren't needed.</span></span> <span data-ttu-id="0b3f1-129">API Explorer 會在要求時使用 Defender 進行端點管理入口網站標記。</span><span class="sxs-lookup"><span data-stu-id="0b3f1-129">The API Explorer uses the Defender for Endpoint management portal token whenever it makes a request.</span></span>

<span data-ttu-id="0b3f1-130">登入的使用者驗證認證是用來確認 API Explorer 有權代表您存取資料。</span><span class="sxs-lookup"><span data-stu-id="0b3f1-130">The logged-in user authentication credential is used to verify that the API Explorer is authorized to access data on your behalf.</span></span>

<span data-ttu-id="0b3f1-131">根據您的 RBAC 許可權，特定 API 要求會受到限制。</span><span class="sxs-lookup"><span data-stu-id="0b3f1-131">Specific API requests are limited based on your RBAC privileges.</span></span> <span data-ttu-id="0b3f1-132">例如，對「送出指示器」的要求限制為安全性系統管理員角色。</span><span class="sxs-lookup"><span data-stu-id="0b3f1-132">For example, a request to "Submit indicator" is limited to the security admin role.</span></span> 
