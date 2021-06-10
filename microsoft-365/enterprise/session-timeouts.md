---
title: Microsoft 365 的會話超時
ms.author: tracyp
author: MSFTTracyP
manager: scotv
ms.date: 6/29/2018
audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- BCS160
ms.assetid: 37a5c116-5b07-4f70-8333-5b86fd2c3c40
ms.collection:
- M365-security-compliance
description: 瞭解如何使用會話超時，以平衡 Microsoft 365 用戶端應用程式中的安全性和輕鬆存取。
ms.openlocfilehash: b85ed8a45727e8a8eed2537fa2233125cd05ece7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924913"
---
# <a name="session-timeouts-for-microsoft-365"></a><span data-ttu-id="76862-103">Microsoft 365 的會話超時</span><span class="sxs-lookup"><span data-stu-id="76862-103">Session timeouts for Microsoft 365</span></span>

<span data-ttu-id="76862-104">「會話週期」是 Microsoft 365 驗證的重要部分，也就是平衡安全性的重要元件，以及使用者提示其認證的提示次數。</span><span class="sxs-lookup"><span data-stu-id="76862-104">Session lifetimes are an important part of authentication for Microsoft 365 and are an important component in balancing security and the number of times users are prompted for their credentials.</span></span>

## <a name="session-times-for-microsoft-365-services"></a><span data-ttu-id="76862-105">Microsoft 365 服務的會話時間</span><span class="sxs-lookup"><span data-stu-id="76862-105">Session times for Microsoft 365 services</span></span>

<span data-ttu-id="76862-106">當使用者在任何 Microsoft 365 web 應用程式或行動應用程式中進行驗證時，即會建立會話。</span><span class="sxs-lookup"><span data-stu-id="76862-106">When users authenticate in any of the Microsoft 365 web apps or mobile apps, a session is established.</span></span> <span data-ttu-id="76862-107">在會話期間內，使用者不需要重新驗證。</span><span class="sxs-lookup"><span data-stu-id="76862-107">For the duration of the session, users won't need to re-authenticate.</span></span> <span data-ttu-id="76862-108">當使用者處於非使用中狀態、當使用者關閉瀏覽器或索引標籤，或其驗證權杖到期時（例如，當其密碼已重設時），會話便會到期。</span><span class="sxs-lookup"><span data-stu-id="76862-108">Sessions can expire when users are inactive, when they close the browser or tab, or when their authentication token expires for other reasons such as when their password has been reset.</span></span> <span data-ttu-id="76862-109">Microsoft 365 服務具有不同的會話超時，以與每個服務的一般用途相對應。</span><span class="sxs-lookup"><span data-stu-id="76862-109">The Microsoft 365 services have different session timeouts to correspond with the typical use of each service.</span></span>

<span data-ttu-id="76862-110">下表列出 Microsoft 365 服務的會話壽命：</span><span class="sxs-lookup"><span data-stu-id="76862-110">The following table lists the session lifetimes for Microsoft 365 services:</span></span>

| <span data-ttu-id="76862-111">Microsoft 365 服務</span><span class="sxs-lookup"><span data-stu-id="76862-111">Microsoft 365 service</span></span> | <span data-ttu-id="76862-112">會話超時</span><span class="sxs-lookup"><span data-stu-id="76862-112">Session timeout</span></span> |
|:-----|:-----|
|<span data-ttu-id="76862-113">Microsoft 365 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="76862-113">Microsoft 365 admin center</span></span>  <br/> |<span data-ttu-id="76862-114">系統會要求您每8小時為系統管理員提供認證。</span><span class="sxs-lookup"><span data-stu-id="76862-114">You are asked to provide credentials for the admin center every 8 hours.</span></span>  <br/> |
|<span data-ttu-id="76862-115">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="76862-115">SharePoint Online</span></span>  <br/> |<span data-ttu-id="76862-116">只要使用者選擇 [ **讓我登入**]，就會有5天的非活動狀態。</span><span class="sxs-lookup"><span data-stu-id="76862-116">5 days of inactivity as long as the users chooses **Keep me signed in**.</span></span> <span data-ttu-id="76862-117">如果使用者在24小時後又從先前登入的小時內重新存取 SharePoint，該超時值會重設為5天。</span><span class="sxs-lookup"><span data-stu-id="76862-117">If the user accesses SharePoint Online again after 24 or more hours have passed from the previous sign-in, the timeout value is reset to 5 days.</span></span>  <br/> |
|<span data-ttu-id="76862-118">Outlook Web App</span><span class="sxs-lookup"><span data-stu-id="76862-118">Outlook Web App</span></span>  <br/> |<span data-ttu-id="76862-119">6 小時。</span><span class="sxs-lookup"><span data-stu-id="76862-119">6 hours.</span></span>  <br/> <span data-ttu-id="76862-120">您可以使用 [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) Cmdlet 中的 _ActivityBasedAuthenticationTimeoutInterval_ 參數變更此值。</span><span class="sxs-lookup"><span data-stu-id="76862-120">You can change this value by using the  _ActivityBasedAuthenticationTimeoutInterval_ parameter in the [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) cmdlet.</span></span>  <br/> |
|<span data-ttu-id="76862-121">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="76862-121">Azure Active Directory</span></span>  <br/> <span data-ttu-id="76862-122">在已啟用新式驗證的情況 Windows 用戶端中 Office 和 Microsoft 365 應用程式所使用的 () </span><span class="sxs-lookup"><span data-stu-id="76862-122">(Used by Office and Microsoft 365 applications in Windows clients with modern authentication enabled)</span></span>  <br/> | <span data-ttu-id="76862-123">新式驗證使用存取權杖和重新整理權杖，以使用 Azure Active Directory 授與使用者對 Microsoft 365 資源的存取權。</span><span class="sxs-lookup"><span data-stu-id="76862-123">Modern authentication uses access tokens and refresh tokens to grant user access to Microsoft 365 resources using Azure Active Directory.</span></span> <span data-ttu-id="76862-124">存取權杖是一種 JSON Web Token，可在驗證成功之後和有效1小時之後提供。</span><span class="sxs-lookup"><span data-stu-id="76862-124">An access token is a JSON Web Token provided after a successful authentication and is valid for 1 hour.</span></span> <span data-ttu-id="76862-125">此外，也會提供較長壽命的刷新權杖。</span><span class="sxs-lookup"><span data-stu-id="76862-125">A refresh token with a longer lifetime is also provided.</span></span> <span data-ttu-id="76862-126">當存取權杖到期時，Office 用戶端會使用有效的重新整理權杖來取得新的訪問權杖。</span><span class="sxs-lookup"><span data-stu-id="76862-126">When access tokens expire, Office clients use a valid refresh token to obtain a new access token.</span></span> <span data-ttu-id="76862-127">如果使用者的初始驗證仍然有效，則此 exchange 會成功。</span><span class="sxs-lookup"><span data-stu-id="76862-127">This exchange succeeds if the user's initial authentication is still valid.</span></span>  <br/>  <span data-ttu-id="76862-128">重新整理權杖的有效期為90天，而且連續使用，在廢除之前，其可能會有效。</span><span class="sxs-lookup"><span data-stu-id="76862-128">Refresh tokens are valid for 90 days, and with continuous use, they can be valid until revoked.</span></span>  <br/>  <span data-ttu-id="76862-129">重新整理權杖可能會因下列的幾個事件而失效：</span><span class="sxs-lookup"><span data-stu-id="76862-129">Refresh tokens can be invalidated by several events such as:</span></span>  <br/>  <span data-ttu-id="76862-130">自重新整理權杖後，使用者的密碼已變更。</span><span class="sxs-lookup"><span data-stu-id="76862-130">User's password has changed since the refresh token was issued.</span></span>  <br/>  <span data-ttu-id="76862-131">管理員可以套用條件式存取原則，以限制使用者嘗試存取之資源的存取權。</span><span class="sxs-lookup"><span data-stu-id="76862-131">An administrator can apply conditional access policies that restrict access to the resource the user is trying to access.</span></span>  <br/> |
|<span data-ttu-id="76862-132">SharePoint 和 OneDrive Android、iOS 及 Windows 10 的行動應用程式</span><span class="sxs-lookup"><span data-stu-id="76862-132">SharePoint and OneDrive mobile apps for Android, iOS, and Windows 10</span></span>  <br/> |<span data-ttu-id="76862-133">存取權杖的預設週期為1小時。</span><span class="sxs-lookup"><span data-stu-id="76862-133">The default lifetime for the access token is 1 hour.</span></span> <span data-ttu-id="76862-134">更新權杖的預設最大非使用時間為90天。</span><span class="sxs-lookup"><span data-stu-id="76862-134">The default max inactive time of the refresh token is 90 days.</span></span>  <br/> [<span data-ttu-id="76862-135">深入瞭解標記及如何設定權杖存留期</span><span class="sxs-lookup"><span data-stu-id="76862-135">Learn more about tokens and how to configure token lifetimes</span></span>](/azure/active-directory/active-directory-configurable-token-lifetimes) <br/> <span data-ttu-id="76862-136">若要撤銷重新整理權杖，您可以重設使用者的 Microsoft 365 密碼</span><span class="sxs-lookup"><span data-stu-id="76862-136">To revoke the refresh token, you can reset the user's Microsoft 365 password</span></span>  <br/> |
|<span data-ttu-id="76862-137">使用 Microsoft 365 的 Yammer Sign-In</span><span class="sxs-lookup"><span data-stu-id="76862-137">Yammer with Microsoft 365 Sign-In</span></span>  <br/> |<span data-ttu-id="76862-138">瀏覽器的存留期。</span><span class="sxs-lookup"><span data-stu-id="76862-138">Lifetime of the browser.</span></span> <span data-ttu-id="76862-139">如果使用者關閉瀏覽器，並在新的瀏覽器中存取 Yammer，Yammer 會以 Microsoft 365 重新驗證。</span><span class="sxs-lookup"><span data-stu-id="76862-139">If users close the browser and access Yammer in a new browser, Yammer will re-authenticate them with Microsoft 365.</span></span> <span data-ttu-id="76862-140">如果使用者使用可快取 cookie 的協力廠商瀏覽器，在重新開啟瀏覽器時，可能不需要重新驗證。</span><span class="sxs-lookup"><span data-stu-id="76862-140">If users use third-party browsers that cache cookies, they may not need to re-authenticate when they reopen the browser.</span></span>  <br/> <span data-ttu-id="76862-141">> [!NOTE]> 這只對使用 Microsoft 365 Sign-In 進行 Yammer 的網路有效。</span><span class="sxs-lookup"><span data-stu-id="76862-141">> [!NOTE]> This is valid only for networks using Microsoft 365 Sign-In for Yammer.</span></span>           |