---
title: 為使用者設定多重要素驗證
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 8f0454b2-f51a-4d9c-bcde-2c48e41621c6
description: 瞭解如何使用安全性預設值為使用者設定多重要素驗證。
monikerRange: o365-worldwide
ms.openlocfilehash: c4ea6037b34d29f2d1e05e248e03e49ee6b06f56
ms.sourcegitcommit: 22e9f54d0d3ead2be91a38d49325308c70f43f90
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/15/2020
ms.locfileid: "44262372"
---
# <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="de761-103">設定多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="de761-103">Set up multi-factor authentication</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="de761-104">如果您在2019年10月21日後購買訂閱或試用版，且意外提示您進行多重要素驗證（MFA），則會自動為您的訂閱啟用[安全性預設值](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)。</span><span class="sxs-lookup"><span data-stu-id="de761-104">If you purchased your subscription or trial after October 21, 2019, and you're unexpectedly prompted for multi-factor authentication (MFA), [security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) have been automatically enabled for your subscription.</span></span>

<span data-ttu-id="de761-105">每個新的 Microsoft 365 訂閱都會自動開啟[安全性預設值](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)。</span><span class="sxs-lookup"><span data-stu-id="de761-105">Every new Microsoft 365 subscription will automatically have [security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) turned on.</span></span> <span data-ttu-id="de761-106">這表示每位使用者都必須設定多重要素驗證（MFA），並在其行動裝置上安裝 Microsoft 驗證應用程式。</span><span class="sxs-lookup"><span data-stu-id="de761-106">This means that every user will have to set up multi-factor authentication (MFA) and install the Microsoft Authenticator app on their mobile device.</span></span> <span data-ttu-id="de761-107">如需詳細資訊，請參閱[Set UP MFA for a Microsoft 365 account](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14)。</span><span class="sxs-lookup"><span data-stu-id="de761-107">For more information, see [Set up MFA for a Microsoft 365 account](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).</span></span>

<span data-ttu-id="de761-108">每次登入時，需要使用下列九個系統管理員角色來執行其他驗證：</span><span class="sxs-lookup"><span data-stu-id="de761-108">The following nine administrator roles will be required to perform additional authentication every time they sign in:</span></span>

- <span data-ttu-id="de761-109">全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="de761-109">Global administrator</span></span>
- <span data-ttu-id="de761-110">SharePoint 系統管理員</span><span class="sxs-lookup"><span data-stu-id="de761-110">SharePoint administrator</span></span>
- <span data-ttu-id="de761-111">Exchange 系統管理員</span><span class="sxs-lookup"><span data-stu-id="de761-111">Exchange administrator</span></span>
- <span data-ttu-id="de761-112">條件式存取系統管理員</span><span class="sxs-lookup"><span data-stu-id="de761-112">Conditional Access administrator</span></span>
- <span data-ttu-id="de761-113">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="de761-113">Security administrator</span></span>
- <span data-ttu-id="de761-114">服務台系統管理員或密碼管理員</span><span class="sxs-lookup"><span data-stu-id="de761-114">Helpdesk administrator or password administrator</span></span>
- <span data-ttu-id="de761-115">計費管理員</span><span class="sxs-lookup"><span data-stu-id="de761-115">Billing administrator</span></span>
- <span data-ttu-id="de761-116">使用者管理員</span><span class="sxs-lookup"><span data-stu-id="de761-116">User administrator</span></span>
- <span data-ttu-id="de761-117">驗證管理員</span><span class="sxs-lookup"><span data-stu-id="de761-117">Authentication administrator</span></span>

<span data-ttu-id="de761-118">將會在需要時向所有其他使用者要求執行其他驗證。</span><span class="sxs-lookup"><span data-stu-id="de761-118">All other users will be asked to perform additional authentication when needed.</span></span>

> [!NOTE]
> <span data-ttu-id="de761-119">您必須是全域系統管理員才能設定或修改 MFA</span><span class="sxs-lookup"><span data-stu-id="de761-119">You must be a global admin to set up or modify MFA</span></span> <br><br>
> <span data-ttu-id="de761-120">如果您使用的不是新的 Microsoft 365 系統管理中心，您可以選取位於首頁頂端的 \*\*[試用新的系統管理中心] \*\*開關將它開啟。</span><span class="sxs-lookup"><span data-stu-id="de761-120">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

<span data-ttu-id="de761-121">如果您先前已設定具有基準原則的 MFA，[您必須將其關閉以開啟安全性預設值](#move-from-baseline-policies-to-security-defaults)。</span><span class="sxs-lookup"><span data-stu-id="de761-121">If you have previously set up MFA with baseline policies, [you must turn them off to turn on security defaults](#move-from-baseline-policies-to-security-defaults).</span></span> <span data-ttu-id="de761-122">不過，如果您有 Microsoft 365 商務或您的訂閱包含[Azure Active Directory Premium P1 或 Azure Active Directory Premium P2](https://azure.microsoft.com/pricing/details/active-directory/)，您也可以設定[條件式存取](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)原則。</span><span class="sxs-lookup"><span data-stu-id="de761-122">However, if you have Microsoft 365 Business or your subscription includes [Azure Active Directory Premium P1 or Azure Active Directory Premium P2](https://azure.microsoft.com/pricing/details/active-directory/), you can also set up [Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) policies.</span></span> <span data-ttu-id="de761-123">若要使用條件式存取原則，您必須確定已停用安全性預設值，且已啟用[新式驗證](#enable-modern-authentication-for-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="de761-123">To use Conditional Access policies, you need to make sure security defaults are disabled and [modern authentication](#enable-modern-authentication-for-your-organization) is enabled.</span></span>

> [!TIP]
> <span data-ttu-id="de761-124">若要向您的使用者說明如何設定 Microsoft 驗證器應用程式，請參閱[使用 Microsoft 驗證與 Office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411)。</span><span class="sxs-lookup"><span data-stu-id="de761-124">To explain to your users how to set up the Microsoft Authenticator app, see [Use Microsoft Authenticator with Office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411).</span></span>

## <a name="manage-security-defaults"></a><span data-ttu-id="de761-125">管理安全性預設</span><span class="sxs-lookup"><span data-stu-id="de761-125">Manage security defaults</span></span>

1. <span data-ttu-id="de761-126">使用全域系統管理員認證登入[系統管理中心](https://go.microsoft.com/fwlink/p/?linkid=834822)。</span><span class="sxs-lookup"><span data-stu-id="de761-126">Sign in to the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822) with global admin credentials.</span></span>
2. <span data-ttu-id="de761-127">移至 [ [Azure Active Directory-屬性] 頁面](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)。</span><span class="sxs-lookup"><span data-stu-id="de761-127">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
3. <span data-ttu-id="de761-128">在頁面底部，選擇 [管理安全性預設]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="de761-128">At the bottom of the page, choose **Manage Security defaults**.</span></span>
4. <span data-ttu-id="de761-129">選擇 **[是]** 啟用安全性預設值，並選擇 [**否**] 以停用安全性預設值，然後選擇 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="de761-129">Choose **Yes** to enable security defaults and **No** to disable security defaults, and then choose **Save**.</span></span>

## <a name="move-from-baseline-policies-to-security-defaults"></a><span data-ttu-id="de761-130">從基準原則移至安全性預設</span><span class="sxs-lookup"><span data-stu-id="de761-130">Move from baseline policies to security defaults</span></span>

1. <span data-ttu-id="de761-131">移至 [[條件式存取原則] 頁面](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies)。</span><span class="sxs-lookup"><span data-stu-id="de761-131">Go to the [Conditional Access - Policies page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span></span>
2. <span data-ttu-id="de761-132">選擇 [**開啟**的每一個基準原則]，並將 [**啟用原則**] 設定為 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="de761-132">Choose each baseline policy that is **On** and set **Enable policy** to **Off**.</span></span>
3. <span data-ttu-id="de761-133">移至 [ [Azure Active Directory-屬性] 頁面](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)。</span><span class="sxs-lookup"><span data-stu-id="de761-133">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
4. <span data-ttu-id="de761-134">在頁面底部，選擇 [**管理安全性預設值**]，然後在 [**啟用安全性預設**值] 窗格中，設定 [**啟用安全性預設值**] 切換為 **[是]**，然後選擇 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="de761-134">On the bottom of the page, choose **Manage Security defaults**, and in the **Enable Security defaults** pane, set **Enable Security defaults** toggle to **Yes**, and then choose **Save**.</span></span> 

## <a name="enable-modern-authentication-for-your-organization"></a><span data-ttu-id="de761-135">為您的組織啟用新式驗證</span><span class="sxs-lookup"><span data-stu-id="de761-135">Enable modern authentication for your organization</span></span>

<span data-ttu-id="de761-136">所有 Office 2016 用戶端應用程式都透過使用 Active Directory Authentication Library (ADAL) 來支援 MFA。</span><span class="sxs-lookup"><span data-stu-id="de761-136">All Office 2016 client applications support MFA through the use of the Active Directory Authentication Library (ADAL).</span></span> <span data-ttu-id="de761-137">這表示 Office 2016 用戶端不需要 App 密碼。</span><span class="sxs-lookup"><span data-stu-id="de761-137">This means that app passwords aren't required for Office 2016 clients.</span></span> <span data-ttu-id="de761-138">如需詳細資訊，請參閱[本文](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-mfasettings#app-passwords)。</span><span class="sxs-lookup"><span data-stu-id="de761-138">See [this article](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-mfasettings#app-passwords) for more information.</span></span>

<span data-ttu-id="de761-139">不過，您必須確定已啟用 ADAL 或新式驗證的 Microsoft 365 訂閱。</span><span class="sxs-lookup"><span data-stu-id="de761-139">However, you need to make sure your Microsoft 365 subscription is enabled for ADAL, or modern authentication.</span></span>

1. <span data-ttu-id="de761-140">若要啟用新式驗證，請從系統[管理中心](https://go.microsoft.com/fwlink/p/?linkid=834822)選取 [**設定** \> **組織設定**]，然後在 [**服務**] 索引標籤中，挑選清單中的 [**新式驗證**]。</span><span class="sxs-lookup"><span data-stu-id="de761-140">To enable modern authentication, from the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822), select **Settings** \> **Org Settings** and then in the **Services** tab, choose **Modern authentication** from the list.</span></span>

2. <span data-ttu-id="de761-141">在 [**新式驗證**] 面板中，選取 [**啟用新式驗證（建議）** ] 方塊，然後選擇 [**儲存變更**]。</span><span class="sxs-lookup"><span data-stu-id="de761-141">Check the **Enable modern authentication (recommended)** box in the **Modern authentication** panel, and then choose **Save changes**.</span></span> 

    ![已勾選啟用核取方塊的新式驗證面板。](../../media/enablemodernauth.png)
    
> [!IMPORTANT]
> <span data-ttu-id="de761-143">到2017年8月為止，所有包含商務用 Skype online 和 Exchange online 的新 Microsoft 365 訂閱預設都會啟用新式驗證。</span><span class="sxs-lookup"><span data-stu-id="de761-143">As of August of 2017, all new Microsoft 365 subscriptions that include Skype for Business online and Exchange online have modern authentication enabled by default.</span></span> <span data-ttu-id="de761-144">若要檢查您的商務用 Skype Online 的新式驗證狀態，您可以使用商務用 Skype Online PowerShell 搭配全域系統管理員認證。</span><span class="sxs-lookup"><span data-stu-id="de761-144">To check your modern authentication status for Skype for Business online, you can use Skype for Business online PowerShell with Global Admin credentials.</span></span> <span data-ttu-id="de761-145">執行 Get-CsOAuthConfiguration 以檢查 -ClientADALAuthOverride 的輸出。</span><span class="sxs-lookup"><span data-stu-id="de761-145">Run Get-CsOAuthConfiguration to check the output of -ClientADALAuthOverride.</span></span> <span data-ttu-id="de761-146">如果 -ClientADALAuthOverride 是 'Allowed'，新式驗證即已開啟。</span><span class="sxs-lookup"><span data-stu-id="de761-146">If -ClientADALAuthOverride is 'Allowed', modern authentication is on.</span></span>
<span data-ttu-id="de761-147">若要檢查您的 Exchange Online 的 MA 狀態，請造訪[啟用 Exchange Online 中的新式驗證](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online)。</span><span class="sxs-lookup"><span data-stu-id="de761-147">To check your MA status for Exchange Online, please visit [Enable modern authentication in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).</span></span>

## <a name="related-articles"></a><span data-ttu-id="de761-148">相關文章</span><span class="sxs-lookup"><span data-stu-id="de761-148">Related articles</span></span>

[<span data-ttu-id="de761-149">保護商務用 Microsoft 365 方案的十大方式</span><span class="sxs-lookup"><span data-stu-id="de761-149">Top 10 ways to secure Microsoft 365 for business plans</span></span>](secure-your-business-data.md)

[<span data-ttu-id="de761-150">為 Windows 裝置上的 Office 2013 啟用新式驗證</span><span class="sxs-lookup"><span data-stu-id="de761-150">Enable Modern Authentication for Office 2013 on Windows devices</span></span>](enable-modern-authentication.md)
