---
title: 將 Microsoft Defender 中的帳戶重新導向至新的 Microsoft 365 安全中心（Office 365）
description: 如何從 Office 365 的 Defender 重新導向至 Microsoft 365 安全中心。
keywords: Microsoft 365 安全性中心，開始使用 Microsoft 365 安全性中心，安全性中心重新導向
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
ms.openlocfilehash: 2a4b122b3ef3a1ddaf61d8f9373bec3e721db177
ms.sourcegitcommit: 07e536f1a6e335f114da55048844e4a866fe731b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2021
ms.locfileid: "52651377"
---
# <a name="redirecting-accounts-from-microsoft-defender-for-office-365-to-the-microsoft-365-security-center"></a><span data-ttu-id="7e82a-104">將帳戶從 Microsoft Defender 重新導向至 Microsoft 365 安全中心的 Office 365</span><span class="sxs-lookup"><span data-stu-id="7e82a-104">Redirecting accounts from Microsoft Defender for Office 365 to the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="7e82a-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="7e82a-105">**Applies to:**</span></span>

- <span data-ttu-id="7e82a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7e82a-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="7e82a-107">適用於 Office 365 的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="7e82a-107">Defender for Office 365</span></span>

<span data-ttu-id="7e82a-108">本文說明如何透過從先前的 Microsoft 安全性與合規性 (中心自動重新導向，將帳戶路由傳送至 Microsoft 365 的安全性中心，) Microsoft 365 的安全性中心 (security.microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="7e82a-108">This article explains how to route accounts to the Microsoft 365 security center by enabling automatic redirection from the former Microsoft Security and Compliance Center (protection.office.com or securitycenter.microsoft.com), to the Microsoft 365 security center (security.microsoft.com).</span></span>

## <a name="what-to-expect"></a><span data-ttu-id="7e82a-109">預期的專案</span><span class="sxs-lookup"><span data-stu-id="7e82a-109">What to expect</span></span>
<span data-ttu-id="7e82a-110">在啟用並使用自動重新導向後，在 Office 365 安全性和合規性 (protection.office.com) 中存取安全性相關功能的使用者，將會自動路由到 Microsoft 365 的安全性中心 (https://security.microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="7e82a-110">Once automatic redirection is enabled and active, users accessing the security-related capabilities in  Office 365 Security and Compliance (protection.office.com), will be automatically routed to the Microsoft 365 security center (https://security.microsoft.com).</span></span>  

<span data-ttu-id="7e82a-111">深入瞭解已變更的專案： [Microsoft 365 security center 中的 Microsoft Defender for Office 365](microsoft-365-security-center-mdo.md)。</span><span class="sxs-lookup"><span data-stu-id="7e82a-111">Learn more about what’s changed: [Microsoft Defender for Office 365 in the Microsoft 365 security center](microsoft-365-security-center-mdo.md).</span></span>

<span data-ttu-id="7e82a-112">開啟自動重新導向時，當使用者使用 Office 365 安全性與合規性中心的安全性功能時，會將使用者路由傳送至 Microsoft 365 的安全性中心。</span><span class="sxs-lookup"><span data-stu-id="7e82a-112">With automatic redirection turned on, users will be routed to Microsoft 365 security center when they use security capabilities in the Office 365 Security and Compliance Center.</span></span>

<span data-ttu-id="7e82a-113">包括「威脅管理」區段和「威脅管理」儀表板與報告中的功能。</span><span class="sxs-lookup"><span data-stu-id="7e82a-113">These include capabilities in the Threat Management section and the Threat Management dashboard and reports.</span></span> <span data-ttu-id="7e82a-114">與安全性無關的 Office 365 安全性與合規性中心中的專案不會重新導向到 Microsoft 365 的安全性中心。</span><span class="sxs-lookup"><span data-stu-id="7e82a-114">Items in the Office 365 Security and Compliance Center that are not related to security are not redirected to the Microsoft 365 security center.</span></span>

<span data-ttu-id="7e82a-115">可在 Microsoft 365 規範中心內找到相容性相關專案，以及郵件流程相關專案可以在 Exchange 系統管理中心找到。</span><span class="sxs-lookup"><span data-stu-id="7e82a-115">Compliance-related items can be found in the Microsoft 365 compliance center, and mail-flow related items can be found in the Exchange admin center.</span></span>

<span data-ttu-id="7e82a-116">所有其他功能（不論服務兩者的相容性相關或功能）不會受到重新導向的影響。</span><span class="sxs-lookup"><span data-stu-id="7e82a-116">All other capabilities, whether compliance-related or capabilities that serve both are not affected by redirection.</span></span> <span data-ttu-id="7e82a-117">Office 365 的安全性警示會出現在 Microsoft 365 安全性中心和 Office 365 安全性與合規性中心，但不會重定向。</span><span class="sxs-lookup"><span data-stu-id="7e82a-117">Office 365 security alerts appear in both the Microsoft 365 security center and the Office 365 Security and Compliance center, without redirection.</span></span>  

### <a name="set-up-portal-redirection"></a><span data-ttu-id="7e82a-118">設定入口網站重新導向</span><span class="sxs-lookup"><span data-stu-id="7e82a-118">Set up portal redirection</span></span>
<span data-ttu-id="7e82a-119">若要在 security.microsoft.com 中啟動路由帳戶至 Microsoft 365 的安全性中心：</span><span class="sxs-lookup"><span data-stu-id="7e82a-119">To start routing accounts to the Microsoft 365 security center at security.microsoft.com:</span></span>

1. <span data-ttu-id="7e82a-120">請確認您是全域系統管理員或具備 Azure Active directory 中的安全性系統管理員許可權。</span><span class="sxs-lookup"><span data-stu-id="7e82a-120">Make sure you’re a global administrator or have security administrator permissions in Azure Active directory.</span></span>
2. <span data-ttu-id="7e82a-121">登[入](https://security.microsoft.com/)Microsoft 365 的安全性中心。</span><span class="sxs-lookup"><span data-stu-id="7e82a-121">[Sign in](https://security.microsoft.com/) to the Microsoft 365 security center.</span></span>
3. <span data-ttu-id="7e82a-122">流覽至 **設定**  >  **電子郵件 &** 共同作業  >  **入口網站** 重新導向。</span><span class="sxs-lookup"><span data-stu-id="7e82a-122">Navigate to **Settings** > **Email & collaboration** > **Portal redirection**.</span></span>  
4. <span data-ttu-id="7e82a-123">將自動重新定向設定切換為 [ **開啟**]。</span><span class="sxs-lookup"><span data-stu-id="7e82a-123">Toggle the Automatic redirection setting to **On**.</span></span>
5. <span data-ttu-id="7e82a-124">按一下 [**啟用**]，將自動重新導向套用至 Microsoft 365 的安全性中心入口網站。</span><span class="sxs-lookup"><span data-stu-id="7e82a-124">Click **Enable** to apply automatic redirection to the Microsoft 365 security center portal.</span></span>

> [!NOTE]
> <span data-ttu-id="7e82a-125">在啟用重新導向後，套用此設定時，作用中會話中的帳戶將不會從其會話中彈出，而且只會在結束目前的會話並重新登入後，路由傳送至 Microsoft 365 的安全性中心。</span><span class="sxs-lookup"><span data-stu-id="7e82a-125">After redirection is enabled, accounts in active sessions while this setting is applied will not be ejected from their session and will only be routed to the Microsoft 365 security center after ending their current session and signing back in again.</span></span>

## <a name="can-i-go-back-to-using-the-former-portal"></a><span data-ttu-id="7e82a-126">可以回復使用先前的入口網站嗎？</span><span class="sxs-lookup"><span data-stu-id="7e82a-126">Can I go back to using the former portal?</span></span>
<span data-ttu-id="7e82a-127">如果有些專案無法運作，或是您使用「門戶意見」入口網站無法 Microsoft 365 完成的任何專案，我們想要使用「入口意見反應」選項來聽取相關專案。</span><span class="sxs-lookup"><span data-stu-id="7e82a-127">If something isn’t working for you or if there’s anything you’re unable to complete through the Microsoft 365 security center portal, we want to hear about it using the portal feedback option.</span></span> <span data-ttu-id="7e82a-128">如果您在重新導向時遇到任何問題，請告訴我們。</span><span class="sxs-lookup"><span data-stu-id="7e82a-128">If you’ve encountered any issues with redirection, please let us know.</span></span>

<span data-ttu-id="7e82a-129">若要還原為先前的入口網站：</span><span class="sxs-lookup"><span data-stu-id="7e82a-129">To revert to the former portal:</span></span>

1. <span data-ttu-id="7e82a-130">以全域系統管理員身分登[入](https://security.microsoft.com/)Microsoft 365 的安全性中心，或在 Azure Active directory 中使用和帳戶搭配安全性管理員許可權。</span><span class="sxs-lookup"><span data-stu-id="7e82a-130">[Sign in](https://security.microsoft.com/) to the Microsoft 365 security center as a global administrator or using and account with security administrator permissions in Azure Active directory.</span></span>

2. <span data-ttu-id="7e82a-131">流覽至 **設定**  >  **電子郵件 &** 共同作業  >  **入口網站** 重新導向。</span><span class="sxs-lookup"><span data-stu-id="7e82a-131">Navigate to **Settings** > **Email & collaboration** > **Portal redirection**.</span></span>   

3. <span data-ttu-id="7e82a-132">將自動重新導向設定切換為 [ **關閉**]。</span><span class="sxs-lookup"><span data-stu-id="7e82a-132">Toggle the Automatic redirection setting to **Off**.</span></span>

4. <span data-ttu-id="7e82a-133">按一下 [ **停** 用 & 在系統提示時共用意見反應]。</span><span class="sxs-lookup"><span data-stu-id="7e82a-133">Click **Disable** & share feedback when prompted.</span></span>

<span data-ttu-id="7e82a-134">您可以隨時重新啟用此設定。</span><span class="sxs-lookup"><span data-stu-id="7e82a-134">This setting can be enabled again at any time.</span></span>

<span data-ttu-id="7e82a-135">一旦停用，帳戶將不再路由傳送至 security.microsoft.com，而您將會再次存取先前的入口網站-securitycenter.windows.com 或 securitycenter.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="7e82a-135">Once disabled, accounts will no longer be routed to security.microsoft.com, and you will once again have access to the former portal - securitycenter.windows.com or securitycenter.microsoft.com.</span></span>

## <a name="related-information"></a><span data-ttu-id="7e82a-136">相關資訊</span><span class="sxs-lookup"><span data-stu-id="7e82a-136">Related information</span></span>
- [<span data-ttu-id="7e82a-137">Microsoft 365 安全性中心概觀</span><span class="sxs-lookup"><span data-stu-id="7e82a-137">Microsoft 365 security center overview</span></span>](overview-security-center.md)
- [<span data-ttu-id="7e82a-138">Microsoft 365 security center 中的 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="7e82a-138">Microsoft Defender for Endpoint in the Microsoft 365 security center</span></span>](microsoft-365-security-center-mde.md)
- [<span data-ttu-id="7e82a-139">Microsoft 提供整合的 SIEM 和 XDR，以現代化的安全性運作</span><span class="sxs-lookup"><span data-stu-id="7e82a-139">Microsoft delivers unified SIEM and XDR to modernize security operations</span></span>](https://www.microsoft.com/security/blog/?p=91813) 
- [<span data-ttu-id="7e82a-140">XDR 和 SIEM 資訊圖表</span><span class="sxs-lookup"><span data-stu-id="7e82a-140">XDR versus SIEM infographic</span></span>](https://afrait.com/blog/xdr-versus-siem/) 
- [<span data-ttu-id="7e82a-141">新的 Defender</span><span class="sxs-lookup"><span data-stu-id="7e82a-141">The New Defender</span></span>](https://afrait.com/blog/the-new-defender/) 
- [<span data-ttu-id="7e82a-142">關於 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7e82a-142">About Microsoft 365 Defender</span></span>](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [<span data-ttu-id="7e82a-143">Microsoft 安全性入口網站和系統管理中心</span><span class="sxs-lookup"><span data-stu-id="7e82a-143">Microsoft security portals and admin centers</span></span>](portals.md)
