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
description: 瞭解如何使用會話超時，以在 Microsoft 365 用戶端應用程式中平衡安全性和輕鬆存取。
ms.openlocfilehash: 8fbbb526fe4b0ac136f79acd564b268489841e0b
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688315"
---
# <a name="session-timeouts-for-microsoft-365"></a><span data-ttu-id="ab462-103">Microsoft 365 的會話超時</span><span class="sxs-lookup"><span data-stu-id="ab462-103">Session timeouts for Microsoft 365</span></span>

<span data-ttu-id="ab462-104">「會話週期」是 Microsoft 365 驗證的重要部分，也是平衡安全性的重要元件，以及使用者提示他們輸入認證的次數。</span><span class="sxs-lookup"><span data-stu-id="ab462-104">Session lifetimes are an important part of authentication for Microsoft 365 and are an important component in balancing security and the number of times users are prompted for their credentials.</span></span>
  
## <a name="session-times-for-microsoft-365-services"></a><span data-ttu-id="ab462-105">Microsoft 365 服務的會話時間</span><span class="sxs-lookup"><span data-stu-id="ab462-105">Session times for Microsoft 365 services</span></span>

<span data-ttu-id="ab462-106">當使用者在任何 Microsoft 365 web apps 或行動應用程式中進行驗證時，即會建立會話。</span><span class="sxs-lookup"><span data-stu-id="ab462-106">When users authenticate in any of the Microsoft 365 web apps or mobile apps, a session is established.</span></span> <span data-ttu-id="ab462-107">在會話期間內，使用者不需要重新驗證。</span><span class="sxs-lookup"><span data-stu-id="ab462-107">For the duration of the session, users won't need to re-authenticate.</span></span> <span data-ttu-id="ab462-108">當使用者處於非使用中狀態、當使用者關閉瀏覽器或索引標籤，或其驗證權杖到期時（例如，當其密碼已重設時），會話便會到期。</span><span class="sxs-lookup"><span data-stu-id="ab462-108">Sessions can expire when users are inactive, when they close the browser or tab, or when their authentication token expires for other reasons such as when their password has been reset.</span></span> <span data-ttu-id="ab462-109">Microsoft 365 服務具有不同的會話超時，以與每個服務的一般用途相對應。</span><span class="sxs-lookup"><span data-stu-id="ab462-109">The Microsoft 365 services have different session timeouts to correspond with the typical use of each service.</span></span>
  
<span data-ttu-id="ab462-110">下表列出 Microsoft 365 服務的會話存留時間：</span><span class="sxs-lookup"><span data-stu-id="ab462-110">The following table lists the session lifetimes for Microsoft 365 services:</span></span>
  
|<span data-ttu-id="ab462-111">**Microsoft 365 服務**</span><span class="sxs-lookup"><span data-stu-id="ab462-111">**Microsoft 365 service**</span></span>|<span data-ttu-id="ab462-112">**會話超時**</span><span class="sxs-lookup"><span data-stu-id="ab462-112">**Session timeout**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ab462-113">Microsoft 365 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="ab462-113">Microsoft 365 admin center</span></span>  <br/> |<span data-ttu-id="ab462-114">系統會要求您每8小時為系統管理員提供認證。</span><span class="sxs-lookup"><span data-stu-id="ab462-114">You are asked to provide credentials for the admin center every 8 hours.</span></span>  <br/> |
|<span data-ttu-id="ab462-115">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="ab462-115">SharePoint Online</span></span>  <br/> |<span data-ttu-id="ab462-116">只要使用者選擇 [ **讓我登入**]，就會有5天的非活動狀態。</span><span class="sxs-lookup"><span data-stu-id="ab462-116">5 days of inactivity as long as the users chooses **Keep me signed in**.</span></span> <span data-ttu-id="ab462-117">如果使用者在24小時後又從先前登入的小時內重新存取 SharePoint，該超時值會重設為5天。</span><span class="sxs-lookup"><span data-stu-id="ab462-117">If the user accesses SharePoint Online again after 24 or more hours have passed from the previous sign-in, the timeout value is reset to 5 days.</span></span>  <br/> |
|<span data-ttu-id="ab462-118">Outlook Web App</span><span class="sxs-lookup"><span data-stu-id="ab462-118">Outlook Web App</span></span>  <br/> |<span data-ttu-id="ab462-119">6小時。</span><span class="sxs-lookup"><span data-stu-id="ab462-119">6 hours.</span></span>  <br/> <span data-ttu-id="ab462-120">您可以使用[Set-OrganizationConfig](https://go.microsoft.com/fwlink/p/?LinkId=615378) Cmdlet 中的_ActivityBasedAuthenticationTimeoutInterval_參數變更此值。</span><span class="sxs-lookup"><span data-stu-id="ab462-120">You can change this value by using the  _ActivityBasedAuthenticationTimeoutInterval_ parameter in the [Set-OrganizationConfig](https://go.microsoft.com/fwlink/p/?LinkId=615378) cmdlet.</span></span>  <br/> |
|<span data-ttu-id="ab462-121">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="ab462-121">Azure Active Directory</span></span>  <br/> <span data-ttu-id="ab462-122">由已啟用新式驗證的 Office 2013 Windows 用戶端所使用 () </span><span class="sxs-lookup"><span data-stu-id="ab462-122">(Used by Office 2013 Windows clients with modern authentication enabled)</span></span>  <br/> | <span data-ttu-id="ab462-123">新式驗證使用存取權杖和重新整理權杖，以使用 Azure Active Directory 授與使用者對 Microsoft 365 資源的存取權。</span><span class="sxs-lookup"><span data-stu-id="ab462-123">Modern authentication uses access tokens and refresh tokens to grant user access to Microsoft 365 resources using Azure Active Directory.</span></span> <span data-ttu-id="ab462-124">存取權杖是一種 JSON Web Token，可在驗證成功之後和有效1小時之後提供。</span><span class="sxs-lookup"><span data-stu-id="ab462-124">An access token is a JSON Web Token provided after a successful authentication and is valid for 1 hour.</span></span> <span data-ttu-id="ab462-125">此外，也會提供較長壽命的刷新權杖。</span><span class="sxs-lookup"><span data-stu-id="ab462-125">A refresh token with a longer lifetime is also provided.</span></span> <span data-ttu-id="ab462-126">當存取權杖到期時，Office 用戶端會使用有效的重新整理權杖來取得新的訪問權杖。</span><span class="sxs-lookup"><span data-stu-id="ab462-126">When access tokens expire, Office clients use a valid refresh token to obtain a new access token.</span></span> <span data-ttu-id="ab462-127">如果使用者的初始驗證仍然有效，則此 exchange 會成功。</span><span class="sxs-lookup"><span data-stu-id="ab462-127">This exchange succeeds if the user's initial authentication is still valid.</span></span>  <br/>  <span data-ttu-id="ab462-128">重新整理權杖的有效期為90天，而且連續使用，在廢除之前，其可能會有效。</span><span class="sxs-lookup"><span data-stu-id="ab462-128">Refresh tokens are valid for 90 days, and with continuous use, they can be valid until revoked.</span></span>  <br/>  <span data-ttu-id="ab462-129">重新整理權杖可能會因下列的幾個事件而失效：</span><span class="sxs-lookup"><span data-stu-id="ab462-129">Refresh tokens can be invalidated by several events such as :</span></span>  <br/>  <span data-ttu-id="ab462-130">自重新整理權杖後，使用者的密碼已變更。</span><span class="sxs-lookup"><span data-stu-id="ab462-130">User's password has changed since the refresh token was issued.</span></span>  <br/>  <span data-ttu-id="ab462-131">管理員可以套用條件式存取原則，以限制使用者嘗試存取之資源的存取權。</span><span class="sxs-lookup"><span data-stu-id="ab462-131">An administrator can apply conditional access policies which restrict access to the resource the user is trying to access.</span></span>  <br/> |
|<span data-ttu-id="ab462-132">針對 Android、iOS 和 Windows 10 SharePoint 和 OneDrive 行動應用程式</span><span class="sxs-lookup"><span data-stu-id="ab462-132">SharePoint and OneDrive mobile apps for Android, iOS, and Windows 10</span></span>  <br/> |<span data-ttu-id="ab462-133">存取權杖的預設週期為1小時。</span><span class="sxs-lookup"><span data-stu-id="ab462-133">The default lifetime for the access token is 1 hour.</span></span> <span data-ttu-id="ab462-134">更新權杖的預設最大非使用時間為90天。</span><span class="sxs-lookup"><span data-stu-id="ab462-134">The default max inactive time of the refresh token is 90 days.</span></span>  <br/> [<span data-ttu-id="ab462-135">深入瞭解標記及如何設定權杖存留期</span><span class="sxs-lookup"><span data-stu-id="ab462-135">Learn more about tokens and how to configure token lifetimes</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-configurable-token-lifetimes) <br/> <span data-ttu-id="ab462-136">若要撤銷重新整理權杖，您可以重設使用者的 Microsoft 365 密碼</span><span class="sxs-lookup"><span data-stu-id="ab462-136">To revoke the refresh token, you can reset the user's Microsoft 365 password</span></span>  <br/> |
|<span data-ttu-id="ab462-137">使用 Microsoft 365 Sign-In 的 Yammer</span><span class="sxs-lookup"><span data-stu-id="ab462-137">Yammer with Microsoft 365 Sign-In</span></span>  <br/> |<span data-ttu-id="ab462-138">瀏覽器的存留期。</span><span class="sxs-lookup"><span data-stu-id="ab462-138">Lifetime of the browser.</span></span> <span data-ttu-id="ab462-139">若使用者關閉瀏覽器，並在新的瀏覽器中存取 Yammer，Yammer 將使用 Microsoft 365 重新驗證。</span><span class="sxs-lookup"><span data-stu-id="ab462-139">If users close the browser and access Yammer in a new browser, Yammer will re-authenticate them with Microsoft 365.</span></span> <span data-ttu-id="ab462-140">如果使用者使用可快取 cookie 的協力廠商瀏覽器，在重新開啟瀏覽器時，可能不需要重新驗證。</span><span class="sxs-lookup"><span data-stu-id="ab462-140">If users use third-party browsers that cache cookies, they may not need to re-authenticate when they reopen the browser.</span></span>  <br/> <span data-ttu-id="ab462-141">> [!NOTE]> 這只對使用 Microsoft 365 Sign-In for Yammer 的網路有效。</span><span class="sxs-lookup"><span data-stu-id="ab462-141">> [!NOTE]> This is valid only for networks using Microsoft 365 Sign-In for Yammer.</span></span>           |
   
