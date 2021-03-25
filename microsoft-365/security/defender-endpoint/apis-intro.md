---
title: 存取 Microsoft Defender for Endpoint APIs
ms.reviewer: ''
description: 瞭解如何使用 APIs，根據 Microsoft Defender ATP 功能自動化工作流程及創新
keywords: api，api，wdatp，open api，microsoft defender atp api，public api，支援的 api，警示，裝置，使用者，網域，ip，file，advanced 搜尋，查詢
search.product: eADQiWindows 10XVcnh
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
ms.openlocfilehash: 70a8ba9d3ff864ca58c856714b00f0e8feba933a
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164744"
---
# <a name="access-the-microsoft-defender-for-endpoint-apis"></a><span data-ttu-id="aa4e0-104">存取 Microsoft Defender for Endpoint APIs</span><span class="sxs-lookup"><span data-stu-id="aa4e0-104">Access the Microsoft Defender for Endpoint APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="aa4e0-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="aa4e0-105">**Applies to:**</span></span>
- [<span data-ttu-id="aa4e0-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="aa4e0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="aa4e0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="aa4e0-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


<span data-ttu-id="aa4e0-108">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="aa4e0-108">**Applies to:**</span></span> 
- [<span data-ttu-id="aa4e0-109">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="aa4e0-109">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

> <span data-ttu-id="aa4e0-110">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="aa4e0-110">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="aa4e0-111">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="aa4e0-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 



<span data-ttu-id="aa4e0-112">「！的 Defender」會透過一組程式設計 APIs 公開其資料和動作。</span><span class="sxs-lookup"><span data-stu-id="aa4e0-112">Defender for Endpoint exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="aa4e0-113">這些 APIs 可讓您以使用 Defender for Endpoint 功能來自動化工作流程及創新。</span><span class="sxs-lookup"><span data-stu-id="aa4e0-113">Those APIs will enable you to automate workflows and innovate based on Defender for Endpoint capabilities.</span></span> <span data-ttu-id="aa4e0-114">API 存取需要 OAuth 2.0 驗證。</span><span class="sxs-lookup"><span data-stu-id="aa4e0-114">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="aa4e0-115">如需詳細資訊，請參閱 [OAuth 2.0 授權碼流程](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)。</span><span class="sxs-lookup"><span data-stu-id="aa4e0-115">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="aa4e0-116">觀賞這段影片，以快速瞭解如何使用 Defender 的 Endpoint APIs。</span><span class="sxs-lookup"><span data-stu-id="aa4e0-116">Watch this video for a quick overview of Defender for Endpoint's APIs.</span></span> 
>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4d73M]

<span data-ttu-id="aa4e0-117">一般來講，您必須採取下列步驟，才能使用 APIs：</span><span class="sxs-lookup"><span data-stu-id="aa4e0-117">In general, you’ll need to take the following steps to use the APIs:</span></span>
- <span data-ttu-id="aa4e0-118">建立 AAD 應用程式</span><span class="sxs-lookup"><span data-stu-id="aa4e0-118">Create an AAD application</span></span>
- <span data-ttu-id="aa4e0-119">使用此應用程式取得存取 token</span><span class="sxs-lookup"><span data-stu-id="aa4e0-119">Get an access token using this application</span></span>
- <span data-ttu-id="aa4e0-120">使用權杖來存取適用于 Endpoint API 的 Defender</span><span class="sxs-lookup"><span data-stu-id="aa4e0-120">Use the token to access Defender for Endpoint API</span></span>


<span data-ttu-id="aa4e0-121">您可以使用 **應用程式內容** 或 **使用者內容**，存取適用于 Endpoint API 的 Defender。</span><span class="sxs-lookup"><span data-stu-id="aa4e0-121">You can access Defender for Endpoint API with **Application Context** or **User Context**.</span></span>

- <span data-ttu-id="aa4e0-122">**應用程式內容：建議 ()**</span><span class="sxs-lookup"><span data-stu-id="aa4e0-122">**Application Context: (Recommended)**</span></span> <br>
    <span data-ttu-id="aa4e0-123">由未登入使用者的執行中執行的應用程式所使用。</span><span class="sxs-lookup"><span data-stu-id="aa4e0-123">Used by apps that run without a signed-in user present.</span></span> <span data-ttu-id="aa4e0-124">例如，以背景服務或守護程式形式執行的應用程式。</span><span class="sxs-lookup"><span data-stu-id="aa4e0-124">for example, apps that run as background services or daemons.</span></span>

    <span data-ttu-id="aa4e0-125">必須採取的步驟，才能存取應用程式內容之 Endpoint API 的 Defender：</span><span class="sxs-lookup"><span data-stu-id="aa4e0-125">Steps that need to be taken to access Defender for Endpoint API with application context:</span></span>

  1. <span data-ttu-id="aa4e0-126">建立 AAD Web 應用程式。</span><span class="sxs-lookup"><span data-stu-id="aa4e0-126">Create an AAD Web-Application.</span></span>
  2. <span data-ttu-id="aa4e0-127">將所需的許可權指派給應用程式，例如「讀取警示」、「隔離電腦」。</span><span class="sxs-lookup"><span data-stu-id="aa4e0-127">Assign the desired permission to the application, for example, 'Read Alerts', 'Isolate Machines'.</span></span> 
  3. <span data-ttu-id="aa4e0-128">建立此應用程式的索引鍵。</span><span class="sxs-lookup"><span data-stu-id="aa4e0-128">Create a key for this Application.</span></span>
  4. <span data-ttu-id="aa4e0-129">使用應用程式及其金鑰取得標記。</span><span class="sxs-lookup"><span data-stu-id="aa4e0-129">Get token using the application with its key.</span></span>
  5. <span data-ttu-id="aa4e0-130">使用權杖來存取 Microsoft Defender ATP API</span><span class="sxs-lookup"><span data-stu-id="aa4e0-130">Use the token to access Microsoft Defender ATP API</span></span>

     <span data-ttu-id="aa4e0-131">如需詳細資訊，請參閱 [Get access with application coNtext](exposed-apis-create-app-webapp.md)。</span><span class="sxs-lookup"><span data-stu-id="aa4e0-131">For more information, see [Get access with application context](exposed-apis-create-app-webapp.md).</span></span>


- <span data-ttu-id="aa4e0-132">**使用者內容：**</span><span class="sxs-lookup"><span data-stu-id="aa4e0-132">**User Context:**</span></span> <br>
    <span data-ttu-id="aa4e0-133">用來代表使用者在 API 中執行動作。</span><span class="sxs-lookup"><span data-stu-id="aa4e0-133">Used to perform actions in the API on behalf of a user.</span></span>

    <span data-ttu-id="aa4e0-134">使用應用程式內容存取應用程式的 Endpoint API 時，所需採取的步驟：</span><span class="sxs-lookup"><span data-stu-id="aa4e0-134">Steps to take to access Defender for Endpoint API with application context:</span></span>

  1. <span data-ttu-id="aa4e0-135">建立 AAD 原生應用程式。</span><span class="sxs-lookup"><span data-stu-id="aa4e0-135">Create AAD Native-Application.</span></span>
  2. <span data-ttu-id="aa4e0-136">將所需的許可權指派給應用程式，例如「讀取警示」、「隔離電腦」等等。</span><span class="sxs-lookup"><span data-stu-id="aa4e0-136">Assign the desired permission to the application, e.g 'Read Alerts', 'Isolate Machines' etc.</span></span> 
  3. <span data-ttu-id="aa4e0-137">使用具有使用者認證的應用程式取得權杖。</span><span class="sxs-lookup"><span data-stu-id="aa4e0-137">Get token using the application with user credentials.</span></span>
  4. <span data-ttu-id="aa4e0-138">使用權杖來存取 Microsoft Defender ATP API</span><span class="sxs-lookup"><span data-stu-id="aa4e0-138">Use the token to access Microsoft Defender ATP API</span></span>

     <span data-ttu-id="aa4e0-139">如需詳細資訊，請參閱 [Get access with user coNtext](exposed-apis-create-app-nativeapp.md)。</span><span class="sxs-lookup"><span data-stu-id="aa4e0-139">For more information, see [Get access with user context](exposed-apis-create-app-nativeapp.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="aa4e0-140">相關主題</span><span class="sxs-lookup"><span data-stu-id="aa4e0-140">Related topics</span></span>
- [<span data-ttu-id="aa4e0-141">Microsoft Defender for Endpoint APIs</span><span class="sxs-lookup"><span data-stu-id="aa4e0-141">Microsoft Defender for Endpoint APIs</span></span>](exposed-apis-list.md)
- [<span data-ttu-id="aa4e0-142">使用應用程式內容存取 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="aa4e0-142">Access Microsoft Defender for Endpoint with application context</span></span>](exposed-apis-create-app-webapp.md)
- [<span data-ttu-id="aa4e0-143">使用使用者內容存取 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="aa4e0-143">Access Microsoft Defender for Endpoint with user context</span></span>](exposed-apis-create-app-nativeapp.md)
