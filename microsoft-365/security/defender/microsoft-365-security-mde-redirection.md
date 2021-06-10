---
title: 將帳戶從 Microsoft Defender for Endpoint 重新導向至 Microsoft 365 Defender
description: 如何將帳戶和會話從 Defender to Endpoint 重新導向至 Microsoft 365 defender。
keywords: Microsoft 365Microsoft 365 defender、安全性中心重新導向的 defender （快速入門）
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: c678cb8d9eece9ff3a900a7d2b0c6bf95ad8eda9
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842563"
---
# <a name="redirecting-accounts-from-microsoft-defender-for-endpoint-to-microsoft-365-defender"></a><span data-ttu-id="52485-104">將帳戶從 Microsoft Defender for Endpoint 重新導向至 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="52485-104">Redirecting accounts from Microsoft Defender for Endpoint to Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="52485-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="52485-105">**Applies to:**</span></span>
- <span data-ttu-id="52485-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="52485-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="52485-107">適用於端點的 Defender</span><span class="sxs-lookup"><span data-stu-id="52485-107">Defender for Endpoint</span></span>

<span data-ttu-id="52485-108">在與 microsoft 的跨網域方法進行威脅防護時，SIEM 及擴充偵測和回應 (XDR) ，我們已 rebranded Microsoft Defender 進階威脅防護為 Microsoft Defender for Endpoint，並將其整合到單一整合入口網站-Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="52485-108">In alignment with Microsoft’s cross-domain approach to threat protection with SIEM and Extended detection and response (XDR), we’ve rebranded Microsoft Defender Advanced Threat Protection as Microsoft Defender for Endpoint and unified it into a single integrated portal - Microsoft 365 Defender.</span></span>

<span data-ttu-id="52485-109">本指南說明如何透過從先前的 Microsoft Defender for 端點入口網站自動重新導向 (securitycenter.windows.com 或 securitycenter.microsoft.com) 的方式，將帳戶路由至 Microsoft 365 defender，以 Microsoft 365 Defender 入口網站 (security.microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="52485-109">This guide explains how to route accounts to Microsoft 365 Defender by enabling automatic redirection from the former Microsoft Defender for Endpoint portal (securitycenter.windows.com or securitycenter.microsoft.com), to Microsoft 365 Defender portal (security.microsoft.com).</span></span>

> [!NOTE]
> <span data-ttu-id="52485-110">Microsoft 365 defender 中的 Microsoft defender for Endpoint 支援在[microsoft defender security center 中授](./mssp-access.md)與存取[受管理的安全性服務提供者 (MSSPs) ](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access)的方式。</span><span class="sxs-lookup"><span data-stu-id="52485-110">Microsoft Defender for Endpoint in Microsoft 365 Defender supports [granting access to managed security service providers (MSSPs)](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) in the same that way access is [granted in the Microsoft Defender security center](./mssp-access.md).</span></span>

## <a name="what-to-expect"></a><span data-ttu-id="52485-111">預期的專案</span><span class="sxs-lookup"><span data-stu-id="52485-111">What to expect</span></span>
<span data-ttu-id="52485-112">啟用自動重新導向後，在 securitycenter.windows.com 或 securitycenter.microsoft.com 存取先前的 Microsoft Defender for Endpoint 入口網站的帳戶將會自動路由到 security.microsoft.com 的 Microsoft 365 Defender 入口網站。</span><span class="sxs-lookup"><span data-stu-id="52485-112">Once automatic redirection is enabled, accounts accessing the former Microsoft Defender for Endpoint portal at securitycenter.windows.com or securitycenter.microsoft.com, will be automatically routed to Microsoft 365 Defender portal at security.microsoft.com.</span></span>
 
<span data-ttu-id="52485-113">深入瞭解已變更的專案： [Microsoft 365 defender 中的端點的 Microsoft defender](microsoft-365-security-center-mde.md)。</span><span class="sxs-lookup"><span data-stu-id="52485-113">Learn more about what’s changed: [Microsoft Defender for Endpoint in Microsoft 365 Defender](microsoft-365-security-center-mde.md).</span></span>

<span data-ttu-id="52485-114">這包括透過瀏覽器直接存取先前入口網站的重新導向，包含指向前 securitycenter.windows.com 入口網站的連結，例如電子郵件通知中的連結，以及 SIEM API 通話傳回的連結。</span><span class="sxs-lookup"><span data-stu-id="52485-114">This includes redirection for direct access to the former portal via browser, including links pointing towards the former securitycenter.windows.com portal - such as links in email notifications, and links returned by SIEM API calls.</span></span>  

 <span data-ttu-id="52485-115">電子郵件通知或 SIEM APIs 中的外部連結目前包含這兩個入口網站的連結。</span><span class="sxs-lookup"><span data-stu-id="52485-115">External links from email notifications or SIEM APIs currently contain links to both portals.</span></span> <span data-ttu-id="52485-116">一旦啟用重新導向，這兩個連結將指向 Microsoft 365 Defender，直到舊的連結最終移除為止。</span><span class="sxs-lookup"><span data-stu-id="52485-116">Once redirection is enabled, both links will point to Microsoft 365 Defender until the old link is eventually removed.</span></span> <span data-ttu-id="52485-117">我們鼓勵您採用指向 Microsoft 365 Defender 的新連結。</span><span class="sxs-lookup"><span data-stu-id="52485-117">We encourage you to adopt the new link pointing to Microsoft 365 Defender.</span></span>

<span data-ttu-id="52485-118">如需有關連結和路由的詳細資訊，請參閱下表。</span><span class="sxs-lookup"><span data-stu-id="52485-118">Refer to the table below for more on links and routing.</span></span>
## <a name="siem-api-routing"></a><span data-ttu-id="52485-119">SIEM API 路由</span><span class="sxs-lookup"><span data-stu-id="52485-119">SIEM API routing</span></span>

|<span data-ttu-id="52485-120">**屬性**</span><span class="sxs-lookup"><span data-stu-id="52485-120">**Property**</span></span>  |<span data-ttu-id="52485-121">**關閉重新定向時的目的地**</span><span class="sxs-lookup"><span data-stu-id="52485-121">**Destination when redirection is OFF**</span></span>  |<span data-ttu-id="52485-122">**重新導向時的目的地**</span><span class="sxs-lookup"><span data-stu-id="52485-122">**Destination when redirection is ON**</span></span> | 
|---------|---------|---------|
| <span data-ttu-id="52485-123">LinkToWDATP</span><span class="sxs-lookup"><span data-stu-id="52485-123">LinkToWDATP</span></span> | <span data-ttu-id="52485-124">Securitycenter.windows.com 中的警示頁面</span><span class="sxs-lookup"><span data-stu-id="52485-124">Alert page in securitycenter.windows.com</span></span> | <span data-ttu-id="52485-125">Security.microsoft.com 中的警示頁面</span><span class="sxs-lookup"><span data-stu-id="52485-125">Alert page in security.microsoft.com</span></span>  |
| <span data-ttu-id="52485-126">IncidentLinkToWDATP</span><span class="sxs-lookup"><span data-stu-id="52485-126">IncidentLinkToWDATP</span></span> | <span data-ttu-id="52485-127">Securitycenter.windows.com 中的 [事件] 頁面</span><span class="sxs-lookup"><span data-stu-id="52485-127">Incident page in securitycenter.windows.com</span></span>  | <span data-ttu-id="52485-128">Security.microsoft.com 中的 [事件] 頁面</span><span class="sxs-lookup"><span data-stu-id="52485-128">Incident page in security.microsoft.com</span></span>  |
| <span data-ttu-id="52485-129">LinkToMTP</span><span class="sxs-lookup"><span data-stu-id="52485-129">LinkToMTP</span></span> | <span data-ttu-id="52485-130">Security.microsoft.com 中的警示頁面</span><span class="sxs-lookup"><span data-stu-id="52485-130">Alert page in security.microsoft.com</span></span> | <span data-ttu-id="52485-131">Security.microsoft.com 中的警示頁面</span><span class="sxs-lookup"><span data-stu-id="52485-131">Alert page in security.microsoft.com</span></span>  |
| <span data-ttu-id="52485-132">IncidentLinkToMTP</span><span class="sxs-lookup"><span data-stu-id="52485-132">IncidentLinkToMTP</span></span> | <span data-ttu-id="52485-133">Security.microsoft.com 中的 [事件] 頁面</span><span class="sxs-lookup"><span data-stu-id="52485-133">Incident page in security.microsoft.com</span></span>  | <span data-ttu-id="52485-134">Security.microsoft.com 中的 [事件] 頁面</span><span class="sxs-lookup"><span data-stu-id="52485-134">Incident page in security.microsoft.com</span></span>  

## <a name="email-alert-notifications"></a><span data-ttu-id="52485-135">電子郵件警示通知</span><span class="sxs-lookup"><span data-stu-id="52485-135">Email alert notifications</span></span>

|<span data-ttu-id="52485-136">**屬性**</span><span class="sxs-lookup"><span data-stu-id="52485-136">**Property**</span></span>  |<span data-ttu-id="52485-137">**關閉重新定向時的目的地**</span><span class="sxs-lookup"><span data-stu-id="52485-137">**Destination when redirection is OFF**</span></span>  |<span data-ttu-id="52485-138">**重新導向時的目的地**</span><span class="sxs-lookup"><span data-stu-id="52485-138">**Destination when redirection is ON**</span></span> |
|---------|---------|---------|
| <span data-ttu-id="52485-139">警示頁面</span><span class="sxs-lookup"><span data-stu-id="52485-139">Alert page</span></span>  | <span data-ttu-id="52485-140">Securitycenter.windows.com 中的警示頁面</span><span class="sxs-lookup"><span data-stu-id="52485-140">Alert page in securitycenter.windows.com</span></span>  | <span data-ttu-id="52485-141">Security.microsoft.com 中的警示頁面</span><span class="sxs-lookup"><span data-stu-id="52485-141">Alert page in security.microsoft.com</span></span>  |
| <span data-ttu-id="52485-142">事件頁面</span><span class="sxs-lookup"><span data-stu-id="52485-142">Incident page</span></span>  |<span data-ttu-id="52485-143">Securitycenter.windows.com 中的 [事件] 頁面</span><span class="sxs-lookup"><span data-stu-id="52485-143">Incident page in securitycenter.windows.com</span></span>  | <span data-ttu-id="52485-144">Security.microsoft.com 中的 [事件] 頁面</span><span class="sxs-lookup"><span data-stu-id="52485-144">Incident page in security.microsoft.com</span></span>  
| <span data-ttu-id="52485-145">安全性中心入口網站中的警示頁面</span><span class="sxs-lookup"><span data-stu-id="52485-145">Alert page in security center portal</span></span> | <span data-ttu-id="52485-146">Security.microsoft.com 中的警示頁面</span><span class="sxs-lookup"><span data-stu-id="52485-146">Alert page in security.microsoft.com</span></span> | <span data-ttu-id="52485-147">Security.microsoft.com 中的警示頁面</span><span class="sxs-lookup"><span data-stu-id="52485-147">Alert page in security.microsoft.com</span></span> | 
| <span data-ttu-id="52485-148">安全中心入口網站中的 [事件] 頁面</span><span class="sxs-lookup"><span data-stu-id="52485-148">Incident page in security center portal</span></span> | <span data-ttu-id="52485-149">Security.microsoft.com 中的 [事件] 頁面</span><span class="sxs-lookup"><span data-stu-id="52485-149">Incident page in security.microsoft.com</span></span>  | <span data-ttu-id="52485-150">Security.microsoft.com 中的 [事件] 頁面</span><span class="sxs-lookup"><span data-stu-id="52485-150">Incident page in security.microsoft.com</span></span>  |

## <a name="when-does-this-take-effect"></a><span data-ttu-id="52485-151">何時會生效？</span><span class="sxs-lookup"><span data-stu-id="52485-151">When does this take effect?</span></span> 
<span data-ttu-id="52485-152">一旦啟用，此更新幾乎會立即對某些帳戶生效。</span><span class="sxs-lookup"><span data-stu-id="52485-152">Once enabled, this update might take effect almost immediately for some accounts.</span></span> <span data-ttu-id="52485-153">但重新導向可能需要較長的時間，才會傳播至組織中的每個帳戶。</span><span class="sxs-lookup"><span data-stu-id="52485-153">But the redirection might take longer to propagate to every account in your organization.</span></span> <span data-ttu-id="52485-154">在套用此設定時，作用中會話中的帳戶將不會從其會話中彈出，而且只會在結束其目前的會話之後傳送至 Microsoft 365 Defender，然後重新登入。</span><span class="sxs-lookup"><span data-stu-id="52485-154">Accounts in active sessions while this setting is applied will not be ejected from their session and will only be routed to Microsoft 365 Defender after ending their current session and signing back in again.</span></span>  

### <a name="set-up-portal-redirection"></a><span data-ttu-id="52485-155">設定入口網站重新導向</span><span class="sxs-lookup"><span data-stu-id="52485-155">Set up portal redirection</span></span>
<span data-ttu-id="52485-156">若要開始 Microsoft 365 Defender 的路由帳戶：</span><span class="sxs-lookup"><span data-stu-id="52485-156">To start routing accounts to Microsoft 365 Defender:</span></span>
1. <span data-ttu-id="52485-157">確定您是全域系統管理員或具備 Azure Active directory 中的安全性系統管理員許可權</span><span class="sxs-lookup"><span data-stu-id="52485-157">Make sure you’re a global administrator or have security administrator permissions in Azure Active directory</span></span> 

2. <span data-ttu-id="52485-158">登[入](https://security.microsoft.com/)Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="52485-158">[Sign in](https://security.microsoft.com/) to Microsoft 365 Defender.</span></span>

3. <span data-ttu-id="52485-159">流覽至 **設定**  >  **端點**  >  **一般**  >  **入口** 重新導向或 [按一下這裡](https://security.microsoft.com/preferences2/portal_redirection)。</span><span class="sxs-lookup"><span data-stu-id="52485-159">Navigate to **Settings** > **Endpoints** > **General** > **Portal redirection** or [click here](https://security.microsoft.com/preferences2/portal_redirection).</span></span>  

4. <span data-ttu-id="52485-160">將自動重新定向設定切換為 [ **開啟**]。</span><span class="sxs-lookup"><span data-stu-id="52485-160">Toggle the Automatic redirection setting to **On**.</span></span>

5. <span data-ttu-id="52485-161">按一下 [**啟用**]，將自動重新導向套用至 Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="52485-161">Click **Enable** to apply automatic redirection to Microsoft 365 Defender.</span></span>

>[!IMPORTANT]
><span data-ttu-id="52485-162">啟用此設定不會終止作用中的使用者會話。</span><span class="sxs-lookup"><span data-stu-id="52485-162">Enabling this setting will not terminate active user sessions.</span></span> <span data-ttu-id="52485-163">在套用此設定的情況下，在使用此設定的使用中的帳戶，只會在結束目前的會話並登入後，導向 Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="52485-163">Accounts who are in an active session while this setting is applied will only be directed to Microsoft 365 Defender after ending their current session and signing in again.</span></span>

>[!NOTE]
><span data-ttu-id="52485-164">您必須是全域系統管理員或具備 Azure Active Directory 中的安全性系統管理員許可權，才可啟用或停用此設定。</span><span class="sxs-lookup"><span data-stu-id="52485-164">You must be a global administrator or have security administrator permissions in Azure Active Directory to enable or disable this setting.</span></span>  

## <a name="can-i-go-back-to-using-the-former-portal"></a><span data-ttu-id="52485-165">可以回復使用先前的入口網站嗎？</span><span class="sxs-lookup"><span data-stu-id="52485-165">Can I go back to using the former portal?</span></span>
<span data-ttu-id="52485-166">如果有些專案無法運作，或是您有任何無法透過 Microsoft 365 Defender 完成的專案，我們想要聽說。</span><span class="sxs-lookup"><span data-stu-id="52485-166">If something isn’t working for you or if there’s anything you’re unable to complete through Microsoft 365 Defender, we want to hear about it.</span></span> <span data-ttu-id="52485-167">如果您在重新導向時遇到任何問題，我們會建議您使用提供意見反應提交表單，讓我們知道。</span><span class="sxs-lookup"><span data-stu-id="52485-167">If you’ve encountered any issues with redirection, we encourage you to let us know by using the Give feedback submission form.</span></span>

<span data-ttu-id="52485-168">若要還原為先前的 Microsoft Defender 端點入口網站：</span><span class="sxs-lookup"><span data-stu-id="52485-168">To revert to the former Microsoft Defender for Endpoint portal:</span></span>

1. <span data-ttu-id="52485-169">以全域系統管理員身分登[入](https://security.microsoft.com/)以 Microsoft 365 Defender，或在 Azure Active directory 中使用和帳戶搭配安全性管理員許可權。</span><span class="sxs-lookup"><span data-stu-id="52485-169">[Sign in](https://security.microsoft.com/) to Microsoft 365 Defender as a global administrator or using and account with security administrator permissions in Azure Active directory.</span></span>

2. <span data-ttu-id="52485-170">流覽至 **設定**  >  **端點**  >  **一般**  >  **入口** 重新導向或 [開啟此頁面](https://security.microsoft.com/preferences2/portal_redirection)。</span><span class="sxs-lookup"><span data-stu-id="52485-170">Navigate to **Settings** > **Endpoints** > **General** > **Portal redirection** or [open the page here](https://security.microsoft.com/preferences2/portal_redirection).</span></span>  

3. <span data-ttu-id="52485-171">將自動重新導向設定切換為 [ **關閉**]。</span><span class="sxs-lookup"><span data-stu-id="52485-171">Toggle the Automatic redirection setting to **Off**.</span></span>

4. <span data-ttu-id="52485-172">按一下 [ **停** 用 & 在系統提示時共用意見反應]。</span><span class="sxs-lookup"><span data-stu-id="52485-172">Click **Disable** & share feedback when prompted.</span></span>

<span data-ttu-id="52485-173">您可以隨時重新啟用此設定。</span><span class="sxs-lookup"><span data-stu-id="52485-173">This setting can be enabled again at any time.</span></span> 

<span data-ttu-id="52485-174">一旦停用，帳戶將不再路由傳送至 security.microsoft.com，而您將會再次存取先前的入口網站-securitycenter.windows.com 或 securitycenter.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="52485-174">Once disabled, accounts will no longer be routed to security.microsoft.com, and you will once again have access to the former portal - securitycenter.windows.com or securitycenter.microsoft.com.</span></span> 

## <a name="related-information"></a><span data-ttu-id="52485-175">相關資訊</span><span class="sxs-lookup"><span data-stu-id="52485-175">Related information</span></span>
- [<span data-ttu-id="52485-176">Microsoft 365Defender 概述</span><span class="sxs-lookup"><span data-stu-id="52485-176">Microsoft 365 Defender overview</span></span>](overview-security-center.md)
- [<span data-ttu-id="52485-177">Microsoft 365 defender 中的 Microsoft defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="52485-177">Microsoft Defender for Endpoint in Microsoft 365 Defender</span></span>](microsoft-365-security-center-mde.md)
- [<span data-ttu-id="52485-178">Microsoft 提供整合的 SIEM 和 XDR，以現代化的安全性運作</span><span class="sxs-lookup"><span data-stu-id="52485-178">Microsoft delivers unified SIEM and XDR to modernize security operations</span></span>](https://www.microsoft.com/security/blog/?p=91813) 
- [<span data-ttu-id="52485-179">XDR 和 SIEM 資訊圖表</span><span class="sxs-lookup"><span data-stu-id="52485-179">XDR versus SIEM infographic</span></span>](https://afrait.com/blog/xdr-versus-siem/) 
- [<span data-ttu-id="52485-180">新的 Defender</span><span class="sxs-lookup"><span data-stu-id="52485-180">The New Defender</span></span>](https://afrait.com/blog/the-new-defender/) 
- [<span data-ttu-id="52485-181">關於 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="52485-181">About Microsoft 365 Defender</span></span>](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [<span data-ttu-id="52485-182">Microsoft 安全性入口網站和系統管理中心</span><span class="sxs-lookup"><span data-stu-id="52485-182">Microsoft security portals and admin centers</span></span>](portals.md)