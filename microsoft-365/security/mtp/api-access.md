---
title: 存取 Microsoft 威脅防護 APIs
description: 瞭解如何存取 Microsoft 威脅防護 APIs
keywords: access、api、application coNtext、user coNtext、aad 應用程式、存取權杖
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
ms.openlocfilehash: 653c359c324852719688a374a6e863df0a1909ba
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650218"
---
# <a name="access-the-microsoft-threat-protection-apis"></a><span data-ttu-id="7af5e-104">存取 Microsoft 威脅防護 APIs</span><span class="sxs-lookup"><span data-stu-id="7af5e-104">Access the Microsoft Threat Protection APIs</span></span>

<span data-ttu-id="7af5e-105">適用於：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="7af5e-105">**Applies to:**</span></span>
- <span data-ttu-id="7af5e-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="7af5e-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="7af5e-107">一些與 prereleased 產品相關的資訊，在正式發行之前，可能會受到大量修改。</span><span class="sxs-lookup"><span data-stu-id="7af5e-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="7af5e-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="7af5e-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


 <span data-ttu-id="7af5e-109">Microsoft 威脅防護會透過一組程式設計 APIs 來公開其資料和動作。</span><span class="sxs-lookup"><span data-stu-id="7af5e-109">Microsoft Threat Protection exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="7af5e-110">這些 APIs 可讓您根據 Microsoft 威脅防護功能來自動化工作流程及創新。</span><span class="sxs-lookup"><span data-stu-id="7af5e-110">Those APIs will enable you to automate workflows and innovate based on  Microsoft Threat Protection capabilities.</span></span> <span data-ttu-id="7af5e-111">API 存取需要 OAuth 2.0 驗證。</span><span class="sxs-lookup"><span data-stu-id="7af5e-111">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="7af5e-112">如需詳細資訊，請參閱 [OAuth 2.0 授權碼流程](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)。</span><span class="sxs-lookup"><span data-stu-id="7af5e-112">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>


<span data-ttu-id="7af5e-113">一般來講，您必須採取下列步驟，才能使用 APIs：</span><span class="sxs-lookup"><span data-stu-id="7af5e-113">In general, you'll need to take the following steps to use the APIs:</span></span>
- <span data-ttu-id="7af5e-114">建立 AAD 應用程式</span><span class="sxs-lookup"><span data-stu-id="7af5e-114">Create an AAD application</span></span>
- <span data-ttu-id="7af5e-115">使用此應用程式取得存取 token</span><span class="sxs-lookup"><span data-stu-id="7af5e-115">Get an access token using this application</span></span>
- <span data-ttu-id="7af5e-116">使用權杖存取 Microsoft 威脅防護 API</span><span class="sxs-lookup"><span data-stu-id="7af5e-116">Use the token to access  Microsoft Threat Protection API</span></span>


<span data-ttu-id="7af5e-117">您可以使用 **應用程式內容** 或 **使用者內容**，存取 Microsoft 威脅防護 API。</span><span class="sxs-lookup"><span data-stu-id="7af5e-117">You can access  Microsoft Threat Protection API with **Application Context** or **User Context**.</span></span>

- <span data-ttu-id="7af5e-118">\*\*應用程式內容：建議 () \*\*</span><span class="sxs-lookup"><span data-stu-id="7af5e-118">**Application Context: (Recommended)**</span></span> <br>
    <span data-ttu-id="7af5e-119">由未登入使用者的執行中執行的應用程式所使用。</span><span class="sxs-lookup"><span data-stu-id="7af5e-119">Used by apps that run without a signed-in user present.</span></span> <span data-ttu-id="7af5e-120">例如，以背景服務或守護程式形式執行的應用程式。</span><span class="sxs-lookup"><span data-stu-id="7af5e-120">for example, apps that run as background services or daemons.</span></span>

    <span data-ttu-id="7af5e-121">需要採取的步驟來存取 Microsoft 威脅防護 API 與應用程式內容：</span><span class="sxs-lookup"><span data-stu-id="7af5e-121">Steps that need to be taken to access  Microsoft Threat Protection API with application context:</span></span>

  1. <span data-ttu-id="7af5e-122">建立 AAD Web 應用程式。</span><span class="sxs-lookup"><span data-stu-id="7af5e-122">Create an AAD Web-Application.</span></span>
  2. <span data-ttu-id="7af5e-123">將所需的許可權指派給 applicationFor 範例（ **Incident）。全部**、 **AdvancedHunting、read**。</span><span class="sxs-lookup"><span data-stu-id="7af5e-123">Assign the desired permission to the applicationFor example, **Incident.Read.All**, **AdvancedHunting.Read.All**.</span></span> 
  3. <span data-ttu-id="7af5e-124">建立此應用程式的索引鍵。</span><span class="sxs-lookup"><span data-stu-id="7af5e-124">Create a key for this Application.</span></span>
  4. <span data-ttu-id="7af5e-125">使用應用程式及其金鑰取得標記。</span><span class="sxs-lookup"><span data-stu-id="7af5e-125">Get token using the application with its key.</span></span>
  5. <span data-ttu-id="7af5e-126">使用權杖存取 Microsoft 威脅防護 API</span><span class="sxs-lookup"><span data-stu-id="7af5e-126">Use the token to access  Microsoft Threat Protection API</span></span>

     <span data-ttu-id="7af5e-127">如需詳細資訊，請參閱 [Get access with application coNtext](api-create-app-web.md)。</span><span class="sxs-lookup"><span data-stu-id="7af5e-127">For more information, see [Get access with application context](api-create-app-web.md).</span></span>


- <span data-ttu-id="7af5e-128">**使用者內容：**</span><span class="sxs-lookup"><span data-stu-id="7af5e-128">**User Context:**</span></span> <br>
    <span data-ttu-id="7af5e-129">用來代表使用者在 API 中執行動作。</span><span class="sxs-lookup"><span data-stu-id="7af5e-129">Used to perform actions in the API on behalf of a user.</span></span>

    <span data-ttu-id="7af5e-130">需要採取的步驟來存取 Microsoft 威脅防護 API 與應用程式內容：</span><span class="sxs-lookup"><span data-stu-id="7af5e-130">Steps that needs to be taken to access  Microsoft Threat Protection API with application context:</span></span>
  1. <span data-ttu-id="7af5e-131">建立 AAD 原生應用程式。</span><span class="sxs-lookup"><span data-stu-id="7af5e-131">Create AAD Native-Application.</span></span>
  2. <span data-ttu-id="7af5e-132">將所需的許可權指派給應用程式。</span><span class="sxs-lookup"><span data-stu-id="7af5e-132">Assign the desired permission to the application.</span></span> <span data-ttu-id="7af5e-133">例如，AdvancedHunting**讀取、讀取**。 **AdvancedHunting.Read**</span><span class="sxs-lookup"><span data-stu-id="7af5e-133">For example, **Incident.Read**, **AdvancedHunting.Read**.</span></span>
  3. <span data-ttu-id="7af5e-134">使用具有使用者認證的應用程式取得權杖。</span><span class="sxs-lookup"><span data-stu-id="7af5e-134">Get token using the application with user credentials.</span></span>
  4. <span data-ttu-id="7af5e-135">使用權杖存取 Microsoft 威脅防護 API</span><span class="sxs-lookup"><span data-stu-id="7af5e-135">Use the token to access  Microsoft Threat Protection API</span></span>

     <span data-ttu-id="7af5e-136">如需詳細資訊，請參閱 [Get access with user coNtext](api-create-app-user-context.md)。</span><span class="sxs-lookup"><span data-stu-id="7af5e-136">For more information, see [Get access with user context](api-create-app-user-context.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="7af5e-137">相關主題</span><span class="sxs-lookup"><span data-stu-id="7af5e-137">Related topics</span></span>
- [<span data-ttu-id="7af5e-138">Microsoft 威脅防護 APIs</span><span class="sxs-lookup"><span data-stu-id="7af5e-138">Microsoft Threat Protection APIs</span></span>](api-supported.md)
- [<span data-ttu-id="7af5e-139">使用應用程式內容存取 Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="7af5e-139">Access  Microsoft Threat Protection with application context</span></span>](api-create-app-web.md)
- [<span data-ttu-id="7af5e-140">使用使用者內容存取 Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="7af5e-140">Access  Microsoft Threat Protection with user context</span></span>](api-create-app-user-context.md)
