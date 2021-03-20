---
title: 將帳戶從 Microsoft Defender for Endpoint 重新導向至 Microsoft 365 安全中心
description: 如何將帳戶和會話從 Defender for Endpoint 重新導向至 Microsoft 365 安全中心。
keywords: Microsoft 365 安全性中心，快速入門 Microsoft 365 安全性中心，安全性中心重新導向
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: bdad55a98dba868d45ecea383ba379108ee5305a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906755"
---
# <a name="redirecting-accounts-from-microsoft-defender-for-endpoint-to-the-microsoft-365-security-center"></a><span data-ttu-id="761aa-104">將帳戶從 Microsoft Defender for Endpoint 重新導向至 Microsoft 365 安全中心</span><span class="sxs-lookup"><span data-stu-id="761aa-104">Redirecting accounts from Microsoft Defender for Endpoint to the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="761aa-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="761aa-105">**Applies to:**</span></span>
- <span data-ttu-id="761aa-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="761aa-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="761aa-107">適用於端點的 Defender</span><span class="sxs-lookup"><span data-stu-id="761aa-107">Defender for Endpoint</span></span>

<span data-ttu-id="761aa-108">在與 Microsoft 的跨網域方法進行威脅防護時，SIEM 及擴充偵測和回應 (XDR) ，我們已 rebranded Microsoft Defender Advanced 威脅防護做為 Microsoft Defender for Endpoint，並將其整合到單一整合入口網站-Microsoft 365 的安全性中心。</span><span class="sxs-lookup"><span data-stu-id="761aa-108">In alignment with Microsoft’s cross-domain approach to threat protection with SIEM and Extended detection and response (XDR), we’ve rebranded Microsoft Defender Advanced Threat Protection as Microsoft Defender for Endpoint and unified it into a single integrated portal - the Microsoft 365 security center.</span></span>

<span data-ttu-id="761aa-109">本指南說明如何透過從從前的 Microsoft Defender for 端點入口網站自動重新導向 (securitycenter.windows.com 或 securitycenter.microsoft.com) 至 Microsoft 365 安全性中心入口網站 (security.microsoft.com) ，將帳戶路由傳送至 Microsoft 365 的安全性中心。</span><span class="sxs-lookup"><span data-stu-id="761aa-109">This guide explains how to route accounts to the Microsoft 365 security center by enabling automatic redirection from the former Microsoft Defender for Endpoint portal (securitycenter.windows.com or securitycenter.microsoft.com), to the Microsoft 365 security center portal (security.microsoft.com).</span></span>

> [!NOTE]
> <span data-ttu-id="761aa-110">Microsoft 365 security center 中的 microsoft Defender for Endpoint 可將存取權授與 [受管理的安全性服務提供者。 (MSSPs) ](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) 在 [microsoft Defender security center 中授](./mssp-access.md)與存取權的方式相同。</span><span class="sxs-lookup"><span data-stu-id="761aa-110">Microsoft Defender for Endpoint in the Microsoft 365 security center supports [granting access to managed security service providers (MSSPs)](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) in the same that way access is [granted in the Microsoft Defender security center](./mssp-access.md).</span></span>

## <a name="what-to-expect"></a><span data-ttu-id="761aa-111">預期的專案</span><span class="sxs-lookup"><span data-stu-id="761aa-111">What to expect</span></span>
<span data-ttu-id="761aa-112">啟用自動重新導向後，在 securitycenter.windows.com 或 securitycenter.microsoft.com 存取先前的 Microsoft Defender for Endpoint 入口網站的帳戶將會自動路由傳送至 Microsoft 365 security center 入口網站，security.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="761aa-112">Once automatic redirection is enabled, accounts accessing the former Microsoft Defender for Endpoint portal at securitycenter.windows.com or securitycenter.microsoft.com, will be automatically routed to the Microsoft 365 security center portal at security.microsoft.com.</span></span>
 
<span data-ttu-id="761aa-113">深入瞭解已變更的專案： [microsoft 365 security center 的 Microsoft Defender For Endpoint](microsoft-365-security-center-mde.md)。</span><span class="sxs-lookup"><span data-stu-id="761aa-113">Learn more about what’s changed: [Microsoft Defender for Endpoint in the Microsoft 365 security center](microsoft-365-security-center-mde.md).</span></span>

<span data-ttu-id="761aa-114">這包括透過瀏覽器直接存取先前入口網站的重新導向，包含指向前 securitycenter.windows.com 入口網站的連結，例如電子郵件通知中的連結，以及 SIEM API 通話傳回的連結。</span><span class="sxs-lookup"><span data-stu-id="761aa-114">This includes redirection for direct access to the former portal via browser, including links pointing towards the former securitycenter.windows.com portal - such as links in email notifications, and links returned by SIEM API calls.</span></span>  

 <span data-ttu-id="761aa-115">電子郵件通知或 SIEM APIs 中的外部連結目前包含這兩個入口網站的連結。</span><span class="sxs-lookup"><span data-stu-id="761aa-115">External links from email notifications or SIEM APIs currently contain links to both portals.</span></span> <span data-ttu-id="761aa-116">一旦啟用重新導向，這兩個連結都會指向 Microsoft 365 的安全性中心，直到舊的連結最終移除為止。</span><span class="sxs-lookup"><span data-stu-id="761aa-116">Once redirection is enabled, both links will point to the Microsoft 365 security center until the old link is eventually removed.</span></span> <span data-ttu-id="761aa-117">我們鼓勵您採用指向 Microsoft 365 安全中心的新連結。</span><span class="sxs-lookup"><span data-stu-id="761aa-117">We encourage you to adopt the new link pointing to the Microsoft 365 security center.</span></span>

<span data-ttu-id="761aa-118">如需有關連結和路由的詳細資訊，請參閱下表。</span><span class="sxs-lookup"><span data-stu-id="761aa-118">Refer to the table below for more on links and routing.</span></span>
## <a name="siem-api-routing"></a><span data-ttu-id="761aa-119">SIEM API 路由</span><span class="sxs-lookup"><span data-stu-id="761aa-119">SIEM API routing</span></span>

|<span data-ttu-id="761aa-120">**屬性**</span><span class="sxs-lookup"><span data-stu-id="761aa-120">**Property**</span></span>  |<span data-ttu-id="761aa-121">**關閉重新定向時的目的地**</span><span class="sxs-lookup"><span data-stu-id="761aa-121">**Destination when redirection is OFF**</span></span>  |<span data-ttu-id="761aa-122">**重新導向時的目的地**</span><span class="sxs-lookup"><span data-stu-id="761aa-122">**Destination when redirection is ON**</span></span> | 
|---------|---------|---------|
| <span data-ttu-id="761aa-123">LinkToWDATP</span><span class="sxs-lookup"><span data-stu-id="761aa-123">LinkToWDATP</span></span> | <span data-ttu-id="761aa-124">Securitycenter.windows.com 中的警示頁面</span><span class="sxs-lookup"><span data-stu-id="761aa-124">Alert page in securitycenter.windows.com</span></span> | <span data-ttu-id="761aa-125">Security.microsoft.com 中的警示頁面</span><span class="sxs-lookup"><span data-stu-id="761aa-125">Alert page in security.microsoft.com</span></span>  |
| <span data-ttu-id="761aa-126">IncidentLinkToWDATP</span><span class="sxs-lookup"><span data-stu-id="761aa-126">IncidentLinkToWDATP</span></span> | <span data-ttu-id="761aa-127">Securitycenter.windows.com 中的 [事件] 頁面</span><span class="sxs-lookup"><span data-stu-id="761aa-127">Incident page in securitycenter.windows.com</span></span>  | <span data-ttu-id="761aa-128">Security.microsoft.com 中的 [事件] 頁面</span><span class="sxs-lookup"><span data-stu-id="761aa-128">Incident page in security.microsoft.com</span></span>  |
| <span data-ttu-id="761aa-129">LinkToMTP</span><span class="sxs-lookup"><span data-stu-id="761aa-129">LinkToMTP</span></span> | <span data-ttu-id="761aa-130">Security.microsoft.com 中的警示頁面</span><span class="sxs-lookup"><span data-stu-id="761aa-130">Alert page in security.microsoft.com</span></span> | <span data-ttu-id="761aa-131">Security.microsoft.com 中的警示頁面</span><span class="sxs-lookup"><span data-stu-id="761aa-131">Alert page in security.microsoft.com</span></span>  |
| <span data-ttu-id="761aa-132">IncidentLinkToMTP</span><span class="sxs-lookup"><span data-stu-id="761aa-132">IncidentLinkToMTP</span></span> | <span data-ttu-id="761aa-133">Security.microsoft.com 中的 [事件] 頁面</span><span class="sxs-lookup"><span data-stu-id="761aa-133">Incident page in security.microsoft.com</span></span>  | <span data-ttu-id="761aa-134">Security.microsoft.com 中的 [事件] 頁面</span><span class="sxs-lookup"><span data-stu-id="761aa-134">Incident page in security.microsoft.com</span></span>  

## <a name="email-alert-notifications"></a><span data-ttu-id="761aa-135">電子郵件警示通知</span><span class="sxs-lookup"><span data-stu-id="761aa-135">Email alert notifications</span></span>

|<span data-ttu-id="761aa-136">**屬性**</span><span class="sxs-lookup"><span data-stu-id="761aa-136">**Property**</span></span>  |<span data-ttu-id="761aa-137">**關閉重新定向時的目的地**</span><span class="sxs-lookup"><span data-stu-id="761aa-137">**Destination when redirection is OFF**</span></span>  |<span data-ttu-id="761aa-138">**重新導向時的目的地**</span><span class="sxs-lookup"><span data-stu-id="761aa-138">**Destination when redirection is ON**</span></span> |
|---------|---------|---------|
| <span data-ttu-id="761aa-139">警示頁面</span><span class="sxs-lookup"><span data-stu-id="761aa-139">Alert page</span></span>  | <span data-ttu-id="761aa-140">Securitycenter.windows.com 中的警示頁面</span><span class="sxs-lookup"><span data-stu-id="761aa-140">Alert page in securitycenter.windows.com</span></span>  | <span data-ttu-id="761aa-141">Security.microsoft.com 中的警示頁面</span><span class="sxs-lookup"><span data-stu-id="761aa-141">Alert page in security.microsoft.com</span></span>  |
| <span data-ttu-id="761aa-142">事件頁面</span><span class="sxs-lookup"><span data-stu-id="761aa-142">Incident page</span></span>  |<span data-ttu-id="761aa-143">Securitycenter.windows.com 中的 [事件] 頁面</span><span class="sxs-lookup"><span data-stu-id="761aa-143">Incident page in securitycenter.windows.com</span></span>  | <span data-ttu-id="761aa-144">Security.microsoft.com 中的 [事件] 頁面</span><span class="sxs-lookup"><span data-stu-id="761aa-144">Incident page in security.microsoft.com</span></span>  
| <span data-ttu-id="761aa-145">安全性中心入口網站中的警示頁面</span><span class="sxs-lookup"><span data-stu-id="761aa-145">Alert page in security center portal</span></span> | <span data-ttu-id="761aa-146">Security.microsoft.com 中的警示頁面</span><span class="sxs-lookup"><span data-stu-id="761aa-146">Alert page in security.microsoft.com</span></span> | <span data-ttu-id="761aa-147">Security.microsoft.com 中的警示頁面</span><span class="sxs-lookup"><span data-stu-id="761aa-147">Alert page in security.microsoft.com</span></span> | 
| <span data-ttu-id="761aa-148">安全中心入口網站中的 [事件] 頁面</span><span class="sxs-lookup"><span data-stu-id="761aa-148">Incident page in security center portal</span></span> | <span data-ttu-id="761aa-149">Security.microsoft.com 中的 [事件] 頁面</span><span class="sxs-lookup"><span data-stu-id="761aa-149">Incident page in security.microsoft.com</span></span>  | <span data-ttu-id="761aa-150">Security.microsoft.com 中的 [事件] 頁面</span><span class="sxs-lookup"><span data-stu-id="761aa-150">Incident page in security.microsoft.com</span></span>  |

## <a name="when-does-this-take-effect"></a><span data-ttu-id="761aa-151">何時會生效？</span><span class="sxs-lookup"><span data-stu-id="761aa-151">When does this take effect?</span></span> 
<span data-ttu-id="761aa-152">一旦啟用，此更新幾乎會立即對某些帳戶生效。</span><span class="sxs-lookup"><span data-stu-id="761aa-152">Once enabled, this update might take effect almost immediately for some accounts.</span></span> <span data-ttu-id="761aa-153">但重新導向可能需要較長的時間，才會傳播至組織中的每個帳戶。</span><span class="sxs-lookup"><span data-stu-id="761aa-153">But the redirection might take longer to propagate to every account in your organization.</span></span> <span data-ttu-id="761aa-154">在套用此設定時，作用中會話中的帳戶將不會從其會話中彈出，而且只會在結束目前的會話並重新登入後，路由傳送至 Microsoft 365 的安全性中心。</span><span class="sxs-lookup"><span data-stu-id="761aa-154">Accounts in active sessions while this setting is applied will not be ejected from their session and will only be routed to the Microsoft 365 security center after ending their current session and signing back in again.</span></span>  

### <a name="set-up-portal-redirection"></a><span data-ttu-id="761aa-155">設定入口網站重新導向</span><span class="sxs-lookup"><span data-stu-id="761aa-155">Set up portal redirection</span></span>
<span data-ttu-id="761aa-156">若要啟動路由帳戶至 Microsoft 365 的安全性中心：</span><span class="sxs-lookup"><span data-stu-id="761aa-156">To start routing accounts to the Microsoft 365 security center:</span></span>
1. <span data-ttu-id="761aa-157">確定您是全域系統管理員或具備 Azure Active directory 中的安全性系統管理員許可權</span><span class="sxs-lookup"><span data-stu-id="761aa-157">Make sure you’re a global administrator or have security administrator permissions in Azure Active directory</span></span> 

2. <span data-ttu-id="761aa-158">登[入](https://security.microsoft.com/)Microsoft 365 的安全性中心。</span><span class="sxs-lookup"><span data-stu-id="761aa-158">[Sign in](https://security.microsoft.com/) to the Microsoft 365 security center.</span></span>

3. <span data-ttu-id="761aa-159">流覽至 **設定**  >  **端點**  >  **一般**  >  **入口** 重新導向或 [按一下這裡](https://security.microsoft.com/preferences2/portal_redirection)。</span><span class="sxs-lookup"><span data-stu-id="761aa-159">Navigate to **Settings** > **Endpoints** > **General** > **Portal redirection** or [click here](https://security.microsoft.com/preferences2/portal_redirection).</span></span>  

4. <span data-ttu-id="761aa-160">將自動重新定向設定切換為 [ **開啟**]。</span><span class="sxs-lookup"><span data-stu-id="761aa-160">Toggle the Automatic redirection setting to **On**.</span></span>

5. <span data-ttu-id="761aa-161">按一下 [ **啟用** ]，將自動重新導向套用至 Microsoft 365 安全性中心入口網站。</span><span class="sxs-lookup"><span data-stu-id="761aa-161">Click **Enable** to apply automatic redirection to the Microsoft 365 security center portal.</span></span>

>[!IMPORTANT]
><span data-ttu-id="761aa-162">啟用此設定不會終止作用中的使用者會話。</span><span class="sxs-lookup"><span data-stu-id="761aa-162">Enabling this setting will not terminate active user sessions.</span></span> <span data-ttu-id="761aa-163">在應用此設定的情況下，在使用此設定的使用中會話的帳戶，只會在結束其目前的會話並登入後，導向至 Microsoft 365 的安全中心。</span><span class="sxs-lookup"><span data-stu-id="761aa-163">Accounts who are in an active session while this setting is applied will only be directed to the Microsoft 365 security center after ending their current session and signing in again.</span></span>

>[!NOTE]
><span data-ttu-id="761aa-164">您必須是全域系統管理員或具備 Azure Active Directory 中的安全性系統管理員許可權，才可啟用或停用此設定。</span><span class="sxs-lookup"><span data-stu-id="761aa-164">You must be a global administrator or have security administrator permissions in Azure Active Directory to enable or disable this setting.</span></span>  

## <a name="can-i-go-back-to-using-the-former-portal"></a><span data-ttu-id="761aa-165">可以回復使用先前的入口網站嗎？</span><span class="sxs-lookup"><span data-stu-id="761aa-165">Can I go back to using the former portal?</span></span>
<span data-ttu-id="761aa-166">如果有些專案無法運作，或是您沒有透過 Microsoft 365 安全性中心入口網站完成的任何專案，我們想要聽說它。</span><span class="sxs-lookup"><span data-stu-id="761aa-166">If something isn’t working for you or if there’s anything you’re unable to complete through the Microsoft 365 security center portal, we want to hear about it.</span></span> <span data-ttu-id="761aa-167">如果您在重新導向時遇到任何問題，我們會建議您使用提供意見反應提交表單，讓我們知道。</span><span class="sxs-lookup"><span data-stu-id="761aa-167">If you’ve encountered any issues with redirection, we encourage you to let us know by using the Give feedback submission form.</span></span>

<span data-ttu-id="761aa-168">若要還原為先前的 Microsoft Defender 端點入口網站：</span><span class="sxs-lookup"><span data-stu-id="761aa-168">To revert to the former Microsoft Defender for Endpoint portal:</span></span>

1. <span data-ttu-id="761aa-169">以全域系統管理員身分登[入](https://security.microsoft.com/)Microsoft 365 的安全性中心，或在 Azure Active directory 中使用和帳戶搭配安全性管理員許可權。</span><span class="sxs-lookup"><span data-stu-id="761aa-169">[Sign in](https://security.microsoft.com/) to the Microsoft 365 security center as a global administrator or using and account with security administrator permissions in Azure Active directory.</span></span>

2. <span data-ttu-id="761aa-170">流覽至 **設定**  >  **端點**  >  **一般**  >  **入口網站** 重新導向或 [開啟頁面](https://security.microsoft.com/preferences2/portal_redirection)。</span><span class="sxs-lookup"><span data-stu-id="761aa-170">Navigate to **Settings** > **Endpoints** > **General** > **Portal redirection** or [open the page here](https://security.microsoft.com/preferences2/portal_redirection).</span></span>  

3. <span data-ttu-id="761aa-171">將自動重新導向設定切換為 [ **關閉**]。</span><span class="sxs-lookup"><span data-stu-id="761aa-171">Toggle the Automatic redirection setting to **Off**.</span></span>

4. <span data-ttu-id="761aa-172">按一下 [ **停** 用 & 在系統提示時共用意見反應]。</span><span class="sxs-lookup"><span data-stu-id="761aa-172">Click **Disable** & share feedback when prompted.</span></span>

<span data-ttu-id="761aa-173">您可以隨時重新啟用此設定。</span><span class="sxs-lookup"><span data-stu-id="761aa-173">This setting can be enabled again at any time.</span></span> 

<span data-ttu-id="761aa-174">一旦停用，帳戶將不再路由傳送至 security.microsoft.com，而您將會再次存取先前的入口網站-securitycenter.windows.com 或 securitycenter.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="761aa-174">Once disabled, accounts will no longer be routed to security.microsoft.com, and you will once again have access to the former portal - securitycenter.windows.com or securitycenter.microsoft.com.</span></span> 

## <a name="related-information"></a><span data-ttu-id="761aa-175">相關資訊</span><span class="sxs-lookup"><span data-stu-id="761aa-175">Related information</span></span>
- [<span data-ttu-id="761aa-176">Microsoft 365 安全性中心概觀</span><span class="sxs-lookup"><span data-stu-id="761aa-176">Microsoft 365 security center overview</span></span>](overview-security-center.md)
- [<span data-ttu-id="761aa-177">Microsoft 365 security center 中的 microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="761aa-177">Microsoft Defender for Endpoint in the Microsoft 365 security center</span></span>](microsoft-365-security-center-mde.md)
- [<span data-ttu-id="761aa-178">Microsoft 提供整合的 SIEM 和 XDR，以現代化的安全性運作</span><span class="sxs-lookup"><span data-stu-id="761aa-178">Microsoft delivers unified SIEM and XDR to modernize security operations</span></span>](https://www.microsoft.com/security/blog/?p=91813) 
- [<span data-ttu-id="761aa-179">XDR 和 SIEM 資訊圖表</span><span class="sxs-lookup"><span data-stu-id="761aa-179">XDR versus SIEM infographic</span></span>](https://afrait.com/blog/xdr-versus-siem/) 
- [<span data-ttu-id="761aa-180">新的 Defender</span><span class="sxs-lookup"><span data-stu-id="761aa-180">The New Defender</span></span>](https://afrait.com/blog/the-new-defender/) 
- [<span data-ttu-id="761aa-181">關於 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="761aa-181">About Microsoft 365 Defender</span></span>](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [<span data-ttu-id="761aa-182">Microsoft 安全性入口網站和系統管理中心</span><span class="sxs-lookup"><span data-stu-id="761aa-182">Microsoft security portals and admin centers</span></span>](portals.md)