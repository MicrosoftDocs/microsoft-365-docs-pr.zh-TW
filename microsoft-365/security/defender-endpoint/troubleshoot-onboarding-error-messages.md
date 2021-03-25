---
title: 疑難排解上架問題及錯誤訊息
description: 疑難排解上架問題，以及在完成 Microsoft Defender for Endpoint 的安裝時的錯誤訊息。
keywords: 疑難排解、疑難排解、Azure Active Directory、上架、錯誤訊息、錯誤訊息、microsoft defender for endpoint
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
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: 1b769c1b3e4201802ea6150358568bf57894d305
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185801"
---
# <a name="troubleshoot-subscription-and-portal-access-issues"></a><span data-ttu-id="3b3fb-104">疑難排解訂閱及入口網站存取問題</span><span class="sxs-lookup"><span data-stu-id="3b3fb-104">Troubleshoot subscription and portal access issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3b3fb-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="3b3fb-105">**Applies to:**</span></span>
- [<span data-ttu-id="3b3fb-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="3b3fb-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="3b3fb-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3b3fb-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="3b3fb-108">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="3b3fb-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3b3fb-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="3b3fb-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-troublshootonboarding-abovefoldlink)

<span data-ttu-id="3b3fb-110">此頁面提供疑難排解設定 Microsoft Defender for Endpoint service 時可能發生之問題的詳細步驟。</span><span class="sxs-lookup"><span data-stu-id="3b3fb-110">This page provides detailed steps to troubleshoot issues that might occur when setting up your Microsoft Defender for Endpoint service.</span></span>

<span data-ttu-id="3b3fb-111">如果您收到錯誤訊息，Microsoft Defender 安全中心會提供有關問題的詳細說明，以及提供相關的連結。</span><span class="sxs-lookup"><span data-stu-id="3b3fb-111">If you receive an error message, Microsoft Defender Security Center will provide a detailed explanation on what the issue is and relevant links will be supplied.</span></span>

## <a name="no-subscriptions-found"></a><span data-ttu-id="3b3fb-112">找不到訂閱</span><span class="sxs-lookup"><span data-stu-id="3b3fb-112">No subscriptions found</span></span>

<span data-ttu-id="3b3fb-113">[！提示] 當存取 Microsoft Defender Security Center 時，出現 [ **未找到任何訂閱** ] 訊息，表示用來登入使用者至入口網站的 Azure Active Directory (azure AD) 沒有 Microsoft Defender for Endpoint 授權。</span><span class="sxs-lookup"><span data-stu-id="3b3fb-113">If while accessing Microsoft Defender Security Center you get a **No subscriptions found** message, it means the Azure Active Directory (Azure AD) used to log in the user to the portal, does not have a Microsoft Defender for Endpoint license.</span></span>

<span data-ttu-id="3b3fb-114">可能的原因：</span><span class="sxs-lookup"><span data-stu-id="3b3fb-114">Potential reasons:</span></span>
- <span data-ttu-id="3b3fb-115">Windows E5 和 Office E5 授權是不同的授權。</span><span class="sxs-lookup"><span data-stu-id="3b3fb-115">The Windows E5 and Office E5 licenses are separate licenses.</span></span>
- <span data-ttu-id="3b3fb-116">已購買授權，但未布建至此 Azure AD 實例。</span><span class="sxs-lookup"><span data-stu-id="3b3fb-116">The license was purchased but not provisioned to this Azure AD instance.</span></span>
    - <span data-ttu-id="3b3fb-117">這可能是授權布建問題。</span><span class="sxs-lookup"><span data-stu-id="3b3fb-117">It could be a license provisioning issue.</span></span>
    - <span data-ttu-id="3b3fb-118">這可能是因為您不小心將授權提供給不同的 Microsoft Azure AD，而非用於驗證的服務。</span><span class="sxs-lookup"><span data-stu-id="3b3fb-118">It could be you inadvertently provisioned the license to a different Microsoft Azure AD than the one used for authentication into the service.</span></span>

<span data-ttu-id="3b3fb-119">在這兩種情況下，您應與 Microsoft 支援部門聯繫 [一般 Microsoft Defender For Endpoint support](https://support.microsoft.com/getsupport?wf=0&tenant=ClassicCommercial&oaspworkflow=start_1.0.0.0&locale=en-us&supportregion=en-us&pesid=16055&ccsid=636419533611396913) 或 [大量授權支援](https://www.microsoft.com/licensing/servicecenter/Help/Contact.aspx)。</span><span class="sxs-lookup"><span data-stu-id="3b3fb-119">For both cases, you should contact Microsoft support at [General Microsoft Defender for Endpoint Support](https://support.microsoft.com/getsupport?wf=0&tenant=ClassicCommercial&oaspworkflow=start_1.0.0.0&locale=en-us&supportregion=en-us&pesid=16055&ccsid=636419533611396913) or [Volume license support](https://www.microsoft.com/licensing/servicecenter/Help/Contact.aspx).</span></span>

![找不到訂閱的影像](images/atp-no-subscriptions-found.png)

## <a name="your-subscription-has-expired"></a><span data-ttu-id="3b3fb-121">您的訂閱已過期</span><span class="sxs-lookup"><span data-stu-id="3b3fb-121">Your subscription has expired</span></span>

<span data-ttu-id="3b3fb-122">當存取 Microsoft Defender Security Center 時，您會收到 **您的訂閱已過期** 郵件，您的線上服務訂閱已過期。</span><span class="sxs-lookup"><span data-stu-id="3b3fb-122">If while accessing Microsoft Defender Security Center you get a **Your subscription has expired** message, your online service subscription has expired.</span></span> <span data-ttu-id="3b3fb-123">Microsoft Defender for Endpoint 訂閱，與任何其他線上服務訂閱一樣，都有到期日。</span><span class="sxs-lookup"><span data-stu-id="3b3fb-123">Microsoft Defender for Endpoint subscription, like any other online service subscription, has an expiration date.</span></span> 

<span data-ttu-id="3b3fb-124">您可以選擇在任何時間點更新或擴充授權。</span><span class="sxs-lookup"><span data-stu-id="3b3fb-124">You can choose to renew or extend the license at any point in time.</span></span> <span data-ttu-id="3b3fb-125">當您訂閱已到期日之後存取入口網站時，如果您選擇不要更新授權，您的 **訂閱已到期** 的郵件將會以下載裝置脫離套件的選項呈現。</span><span class="sxs-lookup"><span data-stu-id="3b3fb-125">When accessing the portal after the expiration date a **Your subscription has expired** message will be presented with an option to download the device offboarding package, should you choose to not renew the license.</span></span>

> [!NOTE]
> <span data-ttu-id="3b3fb-126">基於安全性的考慮，用來下架裝置的套件會在下載之日期之後的30天后到期。</span><span class="sxs-lookup"><span data-stu-id="3b3fb-126">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="3b3fb-127">傳送給裝置的已到期的脫離套件會遭到拒絕。</span><span class="sxs-lookup"><span data-stu-id="3b3fb-127">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="3b3fb-128">下載脫離套件時，系統會通知您套件到期日，也會包含在套件名稱中。</span><span class="sxs-lookup"><span data-stu-id="3b3fb-128">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

![訂閱已過期的影像](images/atp-subscription-expired.png)

## <a name="you-are-not-authorized-to-access-the-portal"></a><span data-ttu-id="3b3fb-130">您無權存取入口網站</span><span class="sxs-lookup"><span data-stu-id="3b3fb-130">You are not authorized to access the portal</span></span>

<span data-ttu-id="3b3fb-131">如果您收到的 **是沒有存取入口網站的授權**，請注意 Microsoft Defender for Endpoint 是安全性監控、事件調查和回應產品，如此一來，存取它會受到使用者限制和控制。</span><span class="sxs-lookup"><span data-stu-id="3b3fb-131">If you receive a **You are not authorized to access the portal**, be aware that Microsoft Defender for Endpoint is a security monitoring, incident investigation and response product, and as such, access to it is restricted and controlled by the user.</span></span>
<span data-ttu-id="3b3fb-132">如需詳細資訊，請參閱 [**指派使用者對入口網站的存取權**](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/assign-portal-access-windows-defender-advanced-threat-protection)。</span><span class="sxs-lookup"><span data-stu-id="3b3fb-132">For more information, see, [**Assign user access to the portal**](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/assign-portal-access-windows-defender-advanced-threat-protection).</span></span>

![存取入口網站未獲授權的影像](images/atp-not-authorized-to-access-portal.png)

## <a name="data-currently-isnt-available-on-some-sections-of-the-portal"></a><span data-ttu-id="3b3fb-134">資料目前在入口網站的某些區段中無法使用</span><span class="sxs-lookup"><span data-stu-id="3b3fb-134">Data currently isn't available on some sections of the portal</span></span>
<span data-ttu-id="3b3fb-135">如果入口網站儀表板和其他章節顯示錯誤訊息，例如「資料目前無法使用」：</span><span class="sxs-lookup"><span data-stu-id="3b3fb-135">If the portal dashboard and other sections show an error message such as "Data currently isn't available":</span></span>

![目前無法使用資料的影像](images/atp-data-not-available.png)

<span data-ttu-id="3b3fb-137">您必須允許它底下的 `securitycenter.windows.com` 及其所有子域。</span><span class="sxs-lookup"><span data-stu-id="3b3fb-137">You'll need to allow the `securitycenter.windows.com` and all subdomains under it.</span></span> <span data-ttu-id="3b3fb-138">例如，`*.securitycenter.windows.com`。</span><span class="sxs-lookup"><span data-stu-id="3b3fb-138">For example, `*.securitycenter.windows.com`.</span></span>


## <a name="portal-communication-issues"></a><span data-ttu-id="3b3fb-139">入口網站通訊問題</span><span class="sxs-lookup"><span data-stu-id="3b3fb-139">Portal communication issues</span></span>
<span data-ttu-id="3b3fb-140">如果您在存取入口網站、遺失資料或限制存取入口網站時遇到問題，您必須確認是否允許使用下列 URLs，並將其開啟以進行通訊。</span><span class="sxs-lookup"><span data-stu-id="3b3fb-140">If you encounter issues with accessing the portal, missing data, or restricted access to portions of the portal, you'll need to verify that the following URLs are allowed and open for communication.</span></span>

- `*.blob.core.windows.net`
- `crl.microsoft.com`
- `https://*.microsoftonline-p.com`
- `https://*.securitycenter.windows.com` 
- `https://automatediracs-eus-prd.securitycenter.windows.com`
- `https://login.microsoftonline.com`
- `https://login.windows.net`
- `https://onboardingpackagescusprd.blob.core.windows.net`
- `https://secure.aadcdn.microsoftonline-p.com` 
- `https://securitycenter.windows.com` 
- `https://static2.sharepointonline.com` 



