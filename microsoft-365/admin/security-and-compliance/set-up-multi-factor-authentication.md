---
title: 為 Office 365 使用者設定多重要素驗證
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
description: 了解如何使用安全性預設來設定 Office 365 使用者的多重要素驗證。
monikerRange: o365-worldwide
ms.openlocfilehash: 331552a4de21198fe7fbc9980e89bfcd87449ffa
ms.sourcegitcommit: e525bcf073a61e1350484719a0c3ceb6ff0d8db1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/06/2020
ms.locfileid: "43153553"
---
# <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="fdd4b-103">設定多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="fdd4b-103">Set up multi-factor authentication</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="fdd4b-104">如果您在2019年10月21日後購買訂閱或試用版，且意外提示您進行多重要素驗證（MFA），則會自動為您的訂閱啟用[安全性預設值](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)。</span><span class="sxs-lookup"><span data-stu-id="fdd4b-104">If you purchased your subscription or trial after October 21, 2019, and you're unexpectedly prompted for multi-factor authentication (MFA), [security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) have been automatically enabled for your subscription.</span></span>

<span data-ttu-id="fdd4b-105">每個新的商務用 Office 365 或 Microsoft 365 商務版訂閱都會自動開啟安全性預設。</span><span class="sxs-lookup"><span data-stu-id="fdd4b-105">Every new Office 365 for business or Microsoft 365 Business subscription will automatically have security defaults turned on.</span></span> <span data-ttu-id="fdd4b-106">這表示每位使用者都必須在其行動裝置上設定 MFA，並安裝 Microsoft 驗證應用程式。</span><span class="sxs-lookup"><span data-stu-id="fdd4b-106">This means that every user will have to set up MFA and install the Microsoft Authenticator app on their mobile device.</span></span> <span data-ttu-id="fdd4b-107">如需詳細資訊，請參閱[設定 Office 365 的雙步驟驗證](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14)。</span><span class="sxs-lookup"><span data-stu-id="fdd4b-107">For more information, see [Set up 2-step verification for Office 365](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).</span></span>  

<span data-ttu-id="fdd4b-108">每次登入時，需要使用下列九個系統管理員角色來執行其他驗證：</span><span class="sxs-lookup"><span data-stu-id="fdd4b-108">The following nine administrator roles will be required to perform additional authentication every time they sign in:</span></span>
- <span data-ttu-id="fdd4b-109">全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="fdd4b-109">Global administrator</span></span>
- <span data-ttu-id="fdd4b-110">SharePoint 系統管理員</span><span class="sxs-lookup"><span data-stu-id="fdd4b-110">SharePoint administrator</span></span>
- <span data-ttu-id="fdd4b-111">Exchange 系統管理員</span><span class="sxs-lookup"><span data-stu-id="fdd4b-111">Exchange administrator</span></span>
- <span data-ttu-id="fdd4b-112">條件式存取系統管理員</span><span class="sxs-lookup"><span data-stu-id="fdd4b-112">Conditional Access administrator</span></span>
- <span data-ttu-id="fdd4b-113">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="fdd4b-113">Security administrator</span></span>
- <span data-ttu-id="fdd4b-114">服務台系統管理員或密碼管理員</span><span class="sxs-lookup"><span data-stu-id="fdd4b-114">Helpdesk administrator or password administrator</span></span>
- <span data-ttu-id="fdd4b-115">計費管理員</span><span class="sxs-lookup"><span data-stu-id="fdd4b-115">Billing administrator</span></span>
- <span data-ttu-id="fdd4b-116">使用者管理員</span><span class="sxs-lookup"><span data-stu-id="fdd4b-116">User administrator</span></span>
- <span data-ttu-id="fdd4b-117">驗證管理員</span><span class="sxs-lookup"><span data-stu-id="fdd4b-117">Authentication administrator</span></span>

<span data-ttu-id="fdd4b-118">將會在需要時向所有其他使用者要求執行其他驗證。</span><span class="sxs-lookup"><span data-stu-id="fdd4b-118">All other users will be asked to perform additional authentication when needed.</span></span> <span data-ttu-id="fdd4b-119">如需詳細資訊，請參閱[什麼是安全性預設？](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span><span class="sxs-lookup"><span data-stu-id="fdd4b-119">For more information, see [What are security defaults?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span></span>

> [!NOTE]
> <span data-ttu-id="fdd4b-120">您必須是 Office 365 全域系統管理員，才能設定或修改 MFA。</span><span class="sxs-lookup"><span data-stu-id="fdd4b-120">You must be an Office 365 global admin to set up or modify MFA.</span></span> <br><br>
> <span data-ttu-id="fdd4b-121">如果您使用的不是新的 Microsoft 365 系統管理中心，您可以選取位於首頁頂端的 [試用新的系統管理中心] \*\*\*\* 開關將它開啟。</span><span class="sxs-lookup"><span data-stu-id="fdd4b-121">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

<span data-ttu-id="fdd4b-122">如果您先前已使用基準原則設定 MFA，[您必須將其關閉並開啟安全性預設](#move-from-baseline-policies-to-security-defaults)。</span><span class="sxs-lookup"><span data-stu-id="fdd4b-122">If you have previously set up MFA with baseline policies, [you must turn them off and turn on security defaults](#move-from-baseline-policies-to-security-defaults).</span></span> <span data-ttu-id="fdd4b-123">不過，如果您有 Microsoft 365 商務或您的訂閱包含[Azure Active Directory Premium P1 或 Azure Active Directory Premium P2](https://azure.microsoft.com/pricing/details/active-directory/)，您也可以設定[條件式存取](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)原則。</span><span class="sxs-lookup"><span data-stu-id="fdd4b-123">However, if you have Microsoft 365 Business or your subscription includes [Azure Active Directory Premium P1 or Azure Active Directory Premium P2](https://azure.microsoft.com/pricing/details/active-directory/), you can also set up [Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) policies.</span></span> <span data-ttu-id="fdd4b-124">若要使用條件式存取原則，您必須確定已啟用[新式驗證](#enable-modern-authentication-for-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="fdd4b-124">To use conditional access policies, you need to make sure [modern authentication](#enable-modern-authentication-for-your-organization) is enabled.</span></span>

> [!TIP]
> <span data-ttu-id="fdd4b-125">若要向使用者說明如何設定 Authenticator 應用程式，請造訪[搭配 Office 365 使用 Microsoft Authenticator](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411?ui=en-US&rs=en-US&ad=US#ID0EAADAAA=_Step_1)。</span><span class="sxs-lookup"><span data-stu-id="fdd4b-125">To explain to your users how to set up the Authenticator app, please visit [Use Microsoft Authenticator with office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411?ui=en-US&rs=en-US&ad=US#ID0EAADAAA=_Step_1).</span></span>

## <a name="manage-security-defaults"></a><span data-ttu-id="fdd4b-126">管理安全性預設</span><span class="sxs-lookup"><span data-stu-id="fdd4b-126">Manage security defaults</span></span>

1. <span data-ttu-id="fdd4b-127">使用全域系統管理員認證登入[系統管理中心](https://go.microsoft.com/fwlink/p/?linkid=834822)。</span><span class="sxs-lookup"><span data-stu-id="fdd4b-127">Sign in to [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822) with your Global admin credentials.</span></span>
2. <span data-ttu-id="fdd4b-128">移至 [Azure Active Directory 屬性](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)。</span><span class="sxs-lookup"><span data-stu-id="fdd4b-128">Go to [Azure Active Directory Properties](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>

3. <span data-ttu-id="fdd4b-129">在頁面底部，選擇 [管理安全性預設]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fdd4b-129">At the bottom of the page, choose **Manage Security defaults**.</span></span>
4. <span data-ttu-id="fdd4b-130">選擇 **[是]** 啟用安全性預設值，或按一下 [**否**] 以停用安全性預設值，然後選擇 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="fdd4b-130">Choose **Yes** to enable security defaults or **No** to disable security defaults, and then choose **Save**.</span></span>

## <a name="move-from-baseline-policies-to-security-defaults"></a><span data-ttu-id="fdd4b-131">從基準原則移至安全性預設</span><span class="sxs-lookup"><span data-stu-id="fdd4b-131">Move from baseline policies to security defaults</span></span>

1. <span data-ttu-id="fdd4b-132">在[系統管理中心](https://go.microsoft.com/fwlink/p/?linkid=834822)中選取 [設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fdd4b-132">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822), select **Setup**.</span></span>

2. <span data-ttu-id="fdd4b-133">在 [登入與安全性]\*\*\*\* 旁，於 [讓登入更安全]\*\*\*\* 下選取 [檢視]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fdd4b-133">Next to **Sign-in and security**, under **Make sign-in more secure**, select **View**.</span></span>

3. <span data-ttu-id="fdd4b-134">在 [讓登入更安全]\*\*\*\* 下，選取 [管理]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fdd4b-134">Under **Make sign-in more secure**, select **Manage**.</span></span> 

4. <span data-ttu-id="fdd4b-135">在 [Azure 入口網站條件式存取原則]\*\*\*\* 頁面上，選擇 [開啟]\*\*\*\* 的每個基準原則，然後將它們設定為 [關閉]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fdd4b-135">On the **Azure portal Conditional Access - Policies** page,  choose each Baseline policy that is **On**, and set them to **Off**.</span></span>
5. <span data-ttu-id="fdd4b-136">移至 [Azure Active Directory 屬性](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)頁面。</span><span class="sxs-lookup"><span data-stu-id="fdd4b-136">Go to [Azure Active Directory Properties](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) page.</span></span>
6. <span data-ttu-id="fdd4b-137">在頁面底部，選擇 [管理安全性預設]\*\*\*\*，並在 [啟用安全性預設]\*\*\*\* 窗格中，將 [啟用安全性預設]\*\*\*\* 切換設為 [是]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fdd4b-137">On the bottom of the page, choose **Manage Security defaults**, and in the **Enable Security defaults** pane, set **Enable Security defaults** toggle to **Yes**.</span></span> 

## <a name="enable-modern-authentication-for-your-organization"></a><span data-ttu-id="fdd4b-138">為您的組織啟用新式驗證</span><span class="sxs-lookup"><span data-stu-id="fdd4b-138">Enable Modern authentication for your organization</span></span>

<span data-ttu-id="fdd4b-139">所有 Office 2016 用戶端應用程式都透過使用 Active Directory Authentication Library (ADAL) 來支援 MFA。</span><span class="sxs-lookup"><span data-stu-id="fdd4b-139">All Office 2016 client applications support MFA through the use of the Active Directory Authentication Library (ADAL).</span></span> <span data-ttu-id="fdd4b-140">這表示 Office 2016 用戶端不需要 App 密碼。</span><span class="sxs-lookup"><span data-stu-id="fdd4b-140">This means that app passwords aren't required for Office 2016 clients.</span></span> <span data-ttu-id="fdd4b-141">不過，您必須確認您的 Office 365 訂閱已針對 ADAL 或新式驗證啟用。</span><span class="sxs-lookup"><span data-stu-id="fdd4b-141">However, you need to make sure your Office 365 subscription is enabled for ADAL, or modern authentication.</span></span>

1. <span data-ttu-id="fdd4b-142">若要啟用新式驗證，請從[系統管理中心](https://go.microsoft.com/fwlink/p/?linkid=834822)選取 [設定]\*\*\*\* \> [設定]\*\*\*\*，然後在 [服務]\*\*\*\* 索引標籤中，從清單選擇 [新式驗證]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fdd4b-142">To enable modern authentication, from the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822), select **Settings** \> **Settings** and then in the **Services** tab, choose **Modern authentication** from the list.</span></span>

2. <span data-ttu-id="fdd4b-143">在 [新式驗證]\*\*\*\* 面板中，勾選 [啟用新式驗證]\*\*\*\* 方塊。</span><span class="sxs-lookup"><span data-stu-id="fdd4b-143">Check the **Enable modern authentication** box in the **Modern authentication** panel.</span></span> 

    ![已勾選啟用核取方塊的新式驗證面板。](../../media/enablemodernauth.png)
    
> [!IMPORTANT]
> <span data-ttu-id="fdd4b-145">從 2017 年 8 月起，包含商務用 Skype Online 和 Exchange Online 的所有新 Office 365 租用戶，皆會預設啟用新式驗證。</span><span class="sxs-lookup"><span data-stu-id="fdd4b-145">As of August of 2017, all new Office 365 tenants that include Skype for Business online and Exchange online have modern authentication enabled by default.</span></span> <span data-ttu-id="fdd4b-146">若要檢查您的商務用 Skype Online 的新式驗證狀態，您可以使用商務用 Skype Online PowerShell 搭配全域系統管理員認證。</span><span class="sxs-lookup"><span data-stu-id="fdd4b-146">To check your modern authentication status for Skype for Business online, you can use Skype for Business online PowerShell with Global Admin credentials.</span></span> <span data-ttu-id="fdd4b-147">執行 Get-CsOAuthConfiguration 以檢查 -ClientADALAuthOverride 的輸出。</span><span class="sxs-lookup"><span data-stu-id="fdd4b-147">Run Get-CsOAuthConfiguration to check the output of -ClientADALAuthOverride.</span></span> <span data-ttu-id="fdd4b-148">如果 -ClientADALAuthOverride 是 'Allowed'，新式驗證即已開啟。</span><span class="sxs-lookup"><span data-stu-id="fdd4b-148">If -ClientADALAuthOverride is 'Allowed', modern authentication is on.</span></span>
<span data-ttu-id="fdd4b-149">若要檢查您的 Exchange Online 的 MA 狀態，請造訪[啟用 Exchange Online 中的新式驗證](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online)。</span><span class="sxs-lookup"><span data-stu-id="fdd4b-149">To check your MA status for Exchange Online, please visit [Enable modern authentication in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).</span></span>

## <a name="related-articles"></a><span data-ttu-id="fdd4b-150">相關文章</span><span class="sxs-lookup"><span data-stu-id="fdd4b-150">Related articles</span></span>

[<span data-ttu-id="fdd4b-151">保護 Office 365 和 Microsoft 365 商務方案的前 10 個最佳方法</span><span class="sxs-lookup"><span data-stu-id="fdd4b-151">Top 10 ways to secure Office 365 and Microsoft 365 Business plans</span></span>](secure-your-business-data.md)

[<span data-ttu-id="fdd4b-152">為 Windows 裝置上的 Office 2013 啟用新式驗證</span><span class="sxs-lookup"><span data-stu-id="fdd4b-152">Enable Modern Authentication for Office 2013 on Windows devices</span></span>](enable-modern-authentication.md)
