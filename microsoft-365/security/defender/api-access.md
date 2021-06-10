---
title: 存取 Microsoft 365 Defender APIs
description: 瞭解如何存取 Microsoft 365 Defender APIs
keywords: access、api、application coNtext、user coNtext、aad 應用程式、存取權杖
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
ms.openlocfilehash: 1fbba132e664f4773496eac7123a0a408db5b3bd
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51058623"
---
# <a name="access-the-microsoft-365-defender-apis"></a><span data-ttu-id="9db82-104">存取 Microsoft 365 Defender APIs</span><span class="sxs-lookup"><span data-stu-id="9db82-104">Access the Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="9db82-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="9db82-105">**Applies to:**</span></span>

- <span data-ttu-id="9db82-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9db82-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9db82-107">部分資訊與發行前版本產品有關，在正式發行之前可能會實質上進行修改。</span><span class="sxs-lookup"><span data-stu-id="9db82-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="9db82-108">Microsoft 對此處提供的資訊，不提供任何明確或隱含的瑕疵擔保。</span><span class="sxs-lookup"><span data-stu-id="9db82-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="9db82-109">Microsoft 365Defender 會透過一組程式設計 APIs 來公開其大部分資料和動作。</span><span class="sxs-lookup"><span data-stu-id="9db82-109">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="9db82-110">這些 APIs 可協助您自動化工作流程，並充分利用 Microsoft 365 Defender 的功能。</span><span class="sxs-lookup"><span data-stu-id="9db82-110">These APIs help you automate workflows and make full use of Microsoft 365 Defender's capabilities.</span></span>

<span data-ttu-id="9db82-111">一般來講，您必須採取下列步驟，才能使用 APIs：</span><span class="sxs-lookup"><span data-stu-id="9db82-111">In general, you'll need to take the following steps to use the APIs:</span></span>

- <span data-ttu-id="9db82-112">建立 Azure Active Directory 應用程式</span><span class="sxs-lookup"><span data-stu-id="9db82-112">Create an Azure Active Directory application</span></span>
- <span data-ttu-id="9db82-113">使用此應用程式取得存取 token</span><span class="sxs-lookup"><span data-stu-id="9db82-113">Get an access token using this application</span></span>
- <span data-ttu-id="9db82-114">使用權杖存取 Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="9db82-114">Use the token to access the Microsoft 365 Defender API</span></span>

> [!NOTE]
> <span data-ttu-id="9db82-115">API access 需要 OAuth 2.0 驗證。</span><span class="sxs-lookup"><span data-stu-id="9db82-115">API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="9db82-116">如需詳細資訊，請參閱[OAuth 2.0 授權碼 Flow](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)。</span><span class="sxs-lookup"><span data-stu-id="9db82-116">For more information, see [OAuth 2.0 Authorization Code Flow](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="9db82-117">完成這些步驟之後，即可使用特定內容來存取 Microsoft 365 Defender API。</span><span class="sxs-lookup"><span data-stu-id="9db82-117">Once you've accomplished these steps, you're ready to access the Microsoft 365 Defender API using a particular context.</span></span>

## <a name="application-context-recommended"></a><span data-ttu-id="9db82-118">建議的應用程式內容 () </span><span class="sxs-lookup"><span data-stu-id="9db82-118">Application context (Recommended)</span></span>

<span data-ttu-id="9db82-119">在未登入使用者顯示的情況下，使用此內容來執行應用程式，例如背景服務或幕後程式。</span><span class="sxs-lookup"><span data-stu-id="9db82-119">Use this context for apps that run without a signed-in user present, such as background services or daemons.</span></span>

1. <span data-ttu-id="9db82-120">建立 Azure Active Directory 的 web 應用程式。</span><span class="sxs-lookup"><span data-stu-id="9db82-120">Create an Azure Active Directory web application.</span></span>
2. <span data-ttu-id="9db82-121">將所需的許可權指派給應用程式。</span><span class="sxs-lookup"><span data-stu-id="9db82-121">Assign the desired permissions to the application.</span></span>
3. <span data-ttu-id="9db82-122">建立應用程式的索引鍵。</span><span class="sxs-lookup"><span data-stu-id="9db82-122">Create a key for the application.</span></span>
4. <span data-ttu-id="9db82-123">使用 application 及其 key 取得安全性權杖。</span><span class="sxs-lookup"><span data-stu-id="9db82-123">Get a security token using the application and its key.</span></span>
5. <span data-ttu-id="9db82-124">使用權杖存取 Microsoft 365 Defender API。</span><span class="sxs-lookup"><span data-stu-id="9db82-124">Use the token to access  Microsoft 365 Defender API.</span></span>

<span data-ttu-id="9db82-125">如需詳細資訊，請參閱 **[Create a app to access Microsoft 365 Defender （沒有使用者](api-create-app-web.md)**）。</span><span class="sxs-lookup"><span data-stu-id="9db82-125">For more information, see **[Create an app to access Microsoft 365 Defender without a user](api-create-app-web.md)**.</span></span>

## <a name="user-context"></a><span data-ttu-id="9db82-126">使用者內容</span><span class="sxs-lookup"><span data-stu-id="9db82-126">User context</span></span>

<span data-ttu-id="9db82-127">使用此內容代表單一使用者執行動作。</span><span class="sxs-lookup"><span data-stu-id="9db82-127">Use this context to perform actions on behalf of a single user.</span></span>

1. <span data-ttu-id="9db82-128">建立 Azure Active Directory 原生應用程式。</span><span class="sxs-lookup"><span data-stu-id="9db82-128">Create an Azure Active Directory native application.</span></span>
2. <span data-ttu-id="9db82-129">將所需的許可權指派給應用程式。</span><span class="sxs-lookup"><span data-stu-id="9db82-129">Assign the desired permission to the application.</span></span>
3. <span data-ttu-id="9db82-130">使用應用程式的使用者認證取得安全性權杖。</span><span class="sxs-lookup"><span data-stu-id="9db82-130">Get a security token using the user credentials for the application.</span></span>
4. <span data-ttu-id="9db82-131">使用權杖存取 Microsoft 365 Defender API。</span><span class="sxs-lookup"><span data-stu-id="9db82-131">Use the token to access  Microsoft 365 Defender API.</span></span>

<span data-ttu-id="9db82-132">如需詳細資訊，請參閱 **[建立應用程式，以代表使用者存取 Microsoft 365 Defender APIs](api-create-app-user-context.md)**。</span><span class="sxs-lookup"><span data-stu-id="9db82-132">For more information, see **[Create an app to access Microsoft 365 Defender APIs on behalf of a user](api-create-app-user-context.md)**.</span></span>

## <a name="partner-context"></a><span data-ttu-id="9db82-133">夥伴內容</span><span class="sxs-lookup"><span data-stu-id="9db82-133">Partner context</span></span>

<span data-ttu-id="9db82-134">當您需要跨 [多個承租人](/azure/active-directory/develop/single-and-multi-tenant-apps)向許多使用者提供應用程式時，請使用此內容。</span><span class="sxs-lookup"><span data-stu-id="9db82-134">Use this context when you need to provide an app to many users across [multiple tenants](/azure/active-directory/develop/single-and-multi-tenant-apps).</span></span>

1. <span data-ttu-id="9db82-135">建立 Azure Active Directory 多租使用者應用程式。</span><span class="sxs-lookup"><span data-stu-id="9db82-135">Create an Azure Active Directory multi-tenant application.</span></span>
2. <span data-ttu-id="9db82-136">將所需的許可權指派給應用程式。</span><span class="sxs-lookup"><span data-stu-id="9db82-136">Assign the desired permission to the application.</span></span>
3. <span data-ttu-id="9db82-137">從每個承租人取得應用程式的系統 [管理員同意](/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) 。</span><span class="sxs-lookup"><span data-stu-id="9db82-137">Get [admin consent](/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) for the app from each tenant.</span></span>
4. <span data-ttu-id="9db82-138">根據客戶的租使用者識別碼，使用使用者認證取得安全性權杖。</span><span class="sxs-lookup"><span data-stu-id="9db82-138">Get a security token using user credentials based on a customer's tenant ID.</span></span>
5. <span data-ttu-id="9db82-139">使用權杖存取 Microsoft 365 Defender API。</span><span class="sxs-lookup"><span data-stu-id="9db82-139">Use the token to access  Microsoft 365 Defender API.</span></span>

<span data-ttu-id="9db82-140">如需詳細資訊，請參閱 **[Create a app with partner access to Microsoft 365 Defender APIs](api-partner-access.md)**。</span><span class="sxs-lookup"><span data-stu-id="9db82-140">For more information, see **[Create an app with partner access to Microsoft 365 Defender APIs](api-partner-access.md)**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="9db82-141">相關文章</span><span class="sxs-lookup"><span data-stu-id="9db82-141">Related articles</span></span>

- [<span data-ttu-id="9db82-142">Microsoft 365Defender APIs 概述</span><span class="sxs-lookup"><span data-stu-id="9db82-142">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="9db82-143">OAuth 2.0 使用者登入和 API 存取的授權</span><span class="sxs-lookup"><span data-stu-id="9db82-143">OAuth 2.0 authorization for user sign in and API access</span></span>](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
- [<span data-ttu-id="9db82-144">使用 Azure Key Vault 管理伺服器應用程式中的機密</span><span class="sxs-lookup"><span data-stu-id="9db82-144">Manage secrets in your server apps with Azure Key Vault</span></span>](/learn/modules/manage-secrets-with-azure-key-vault/)
- [<span data-ttu-id="9db82-145">建立存取 Microsoft 365 的 "Hello world" 應用程式 APIs</span><span class="sxs-lookup"><span data-stu-id="9db82-145">Create a 'Hello world' application that accesses the Microsoft 365 APIs</span></span>](api-hello-world.md)