---
title: 設定條件式存取原則
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- M365-Campaigns
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: 瞭解如何要求 MFA 和設定 Microsoft 365 商務的條件式存取原則。
ms.openlocfilehash: 08e9365e8aad37e2412a6d739b41f2328c1aa277
ms.sourcegitcommit: c452413dff5d5388c9725f38871246237c313e65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/22/2019
ms.locfileid: "35183256"
---
# <a name="require-multi-factor-authentication-and-set-up-conditional-access-policies"></a><span data-ttu-id="6021e-103">需要多重要素驗證, 並設定條件式存取原則</span><span class="sxs-lookup"><span data-stu-id="6021e-103">Require multi-factor authentication and set up conditional access policies</span></span>

<span data-ttu-id="6021e-104">您可以使用多重要素驗證和條件式存取原則來保護您的資料存取。</span><span class="sxs-lookup"><span data-stu-id="6021e-104">You protect access to your data with multi-factor authentication and conditional access policies.</span></span> <span data-ttu-id="6021e-105">這些新增了大量額外的安全性。</span><span class="sxs-lookup"><span data-stu-id="6021e-105">These add substantial additional security.</span></span> <span data-ttu-id="6021e-106">Microsoft 提供一組適用于所有客戶的基準條件式存取原則。</span><span class="sxs-lookup"><span data-stu-id="6021e-106">Microsoft provides a set of baseline conditional access policies that are recommended for all customers.</span></span> <span data-ttu-id="6021e-107">基準原則是一組預先定義的原則, 可協助保護組織不受許多常見攻擊。</span><span class="sxs-lookup"><span data-stu-id="6021e-107">Baseline policies are a set of predefined policies that help protect organizations against many common attacks.</span></span> <span data-ttu-id="6021e-108">這些常見攻擊可能包括密碼噴塗、重新顯示和網路釣魚。</span><span class="sxs-lookup"><span data-stu-id="6021e-108">These common attacks can include password spray, replay, and phishing.</span></span>

<span data-ttu-id="6021e-109">這些原則需要系統管理員和使用者在符合特定條件時輸入第二種形式的驗證 (稱為「多重要素驗證」或「MFA」)。</span><span class="sxs-lookup"><span data-stu-id="6021e-109">These policies require admins and users to enter a second form of authentication (called multi-factor authentication, or MFA) when certain conditions are met.</span></span> <span data-ttu-id="6021e-110">例如, 如果您組織中的使用者嘗試從不同的國家或從未知的裝置登入 Microsoft 365, 則可能會將登入視為危險。</span><span class="sxs-lookup"><span data-stu-id="6021e-110">For example, if a user in your organization tries to sign in to Microsoft 365 from a different country or from an unknown device, the sign-in might be considered risky.</span></span> <span data-ttu-id="6021e-111">使用者必須提供一種額外的驗證形式 (例如指紋或程式碼) 來證明其身分識別。</span><span class="sxs-lookup"><span data-stu-id="6021e-111">The user must provide an extra form of authentication (such as a fingerprint or a code) to prove their identity.</span></span> 

<span data-ttu-id="6021e-112">目前的基準原則包括下列各項:</span><span class="sxs-lookup"><span data-stu-id="6021e-112">Currently, baseline policies include the following:</span></span>
- <span data-ttu-id="6021e-113">在 Microsoft 365 系統管理中心設定:</span><span class="sxs-lookup"><span data-stu-id="6021e-113">Set up in Microsoft 365 admin center:</span></span>
    - <span data-ttu-id="6021e-114">**需要**對系統管理員進行 MFA-對於最具特權的系統管理員角色 (包括全域管理員), 需要多重要素驗證。</span><span class="sxs-lookup"><span data-stu-id="6021e-114">**Require MFA for admins** — Requires multi-factor authentication for the most privileged administrator roles, including global administrator.</span></span>
    - <span data-ttu-id="6021e-115">使用者**保護**—只有當登入有危險時, 才需要使用者的多重要素驗證。</span><span class="sxs-lookup"><span data-stu-id="6021e-115">**End user protection** — Requires multi-factor authentication for users only when a sign-in is risky.</span></span> 
- <span data-ttu-id="6021e-116">在 Azure Active Directory 入口網站中設定:</span><span class="sxs-lookup"><span data-stu-id="6021e-116">Set up in Azure Active Directory portal:</span></span>
    - <span data-ttu-id="6021e-117">**封鎖舊版驗證**-較舊的用戶端應用程式和部分新的應用程式不會使用較新、更安全的驗證通訊協定。</span><span class="sxs-lookup"><span data-stu-id="6021e-117">**Block legacy authentication** — Older client apps and some new apps don't use newer, more secure, authentication protocols.</span></span> <span data-ttu-id="6021e-118">這些較舊的應用程式可以略過條件式存取原則, 並對您的環境進行未經授權的存取。</span><span class="sxs-lookup"><span data-stu-id="6021e-118">These older apps can bypass conditional access policies and gain unauthorized access to your environment.</span></span> <span data-ttu-id="6021e-119">此原則會封鎖不支援條件式存取的用戶端存取權。</span><span class="sxs-lookup"><span data-stu-id="6021e-119">This policy blocks access from clients that don't support conditional access.</span></span> 
    - <span data-ttu-id="6021e-120">**需要 MFA For Service management** --需要多重要素驗證來存取管理工具, 包括 Azure 入口網站 (您設定基準原則)。</span><span class="sxs-lookup"><span data-stu-id="6021e-120">**Require MFA for Service Management** — Requires multi-factor authentication for access to management tools, including Azure portal (where you configure baseline policies).</span></span> 

<span data-ttu-id="6021e-121">Microsoft 建議您啟用所有的基準原則。</span><span class="sxs-lookup"><span data-stu-id="6021e-121">Microsoft recommends you enable all of these baseline policies.</span></span> <span data-ttu-id="6021e-122">啟用這些原則之後, 系統會提示系統管理員和使用者註冊 Azure 多重要素驗證。</span><span class="sxs-lookup"><span data-stu-id="6021e-122">After these policies are enabled, admins and users will be prompted to register for Azure Multi-Factor authentication.</span></span>

<span data-ttu-id="6021e-123">如需這些原則的詳細資訊, 請參閱[何謂基準原則](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)？</span><span class="sxs-lookup"><span data-stu-id="6021e-123">For more information about these policies, see [What are baseline policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)?</span></span>


## <a name="require-mfa"></a><span data-ttu-id="6021e-124">需要 MFA</span><span class="sxs-lookup"><span data-stu-id="6021e-124">Require MFA</span></span>

<span data-ttu-id="6021e-125">若要要求所有使用者使用第二種 ID 形式登入:</span><span class="sxs-lookup"><span data-stu-id="6021e-125">To require that all users sign in with a second form of ID:</span></span>

1. <span data-ttu-id="6021e-126">移至系統管理中心<a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> , 然後選擇 [**設定**]。</span><span class="sxs-lookup"><span data-stu-id="6021e-126">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> and choose **Setup**.</span></span>

2. <span data-ttu-id="6021e-127">在 [安裝程式] 頁面上, 選擇 [**建立登入更安全**的卡] 中的 [ **View** ]。</span><span class="sxs-lookup"><span data-stu-id="6021e-127">On the Setup page, choose **View** in the **Make sign-in more secure** card.</span></span>


    ![請登入更安全的卡。](media/setupmfa.png)
3. <span data-ttu-id="6021e-129">在 [啟用登入更安全] 頁面上, 選擇 [**開始**]。</span><span class="sxs-lookup"><span data-stu-id="6021e-129">On the Make sign-in more secure page, choose **Get started**.</span></span>
 
4. <span data-ttu-id="6021e-130">在 [強化登入安全性] 窗格上, 選取 [**要求系統管理員多重要素驗證**] 旁的核取方塊, 並**要求使用者註冊多重要素驗證, 並在偵測到風險時封鎖存取權**。</span><span class="sxs-lookup"><span data-stu-id="6021e-130">On the Strengthen sign-in security pane, check the check boxes next to **Require multi-factor authentication for admins** and **Require users to register for multi-factor authentication and block access if risk is detected**.</span></span>
    <span data-ttu-id="6021e-131">請務必從 [**尋找使用者**] 方塊中的 MFA 需求排除[緊急](m365-campaigns-protect-admin-accounts.md#create-an-emergency-admin-account)或「中斷玻璃」系統管理帳戶。</span><span class="sxs-lookup"><span data-stu-id="6021e-131">Be sure to exclude the [emergency](m365-campaigns-protect-admin-accounts.md#create-an-emergency-admin-account) or "break-glass" admin account from the MFA requirement in the **Find users** box.</span></span>
    
    ![增強 [內接安全性] 頁面。](media/requiremfa.png)

5. <span data-ttu-id="6021e-133">選擇頁面底部的 [**建立原則**]。</span><span class="sxs-lookup"><span data-stu-id="6021e-133">Choose **Create policy** on the bottom of the page.</span></span>

## <a name="set-up-baseline-policies"></a><span data-ttu-id="6021e-134">設定基準原則</span><span class="sxs-lookup"><span data-stu-id="6021e-134">Set up baseline policies</span></span>

1. <span data-ttu-id="6021e-135">移至[azure 入口網站](https://portal.azure.com), 然後流覽至**azure Active Directory** \> **條件式存取**。</span><span class="sxs-lookup"><span data-stu-id="6021e-135">Go to [Azure portal](https://portal.azure.com), and then navigate to **Azure Active Directory** \> **Conditional Access**.</span></span>
    
    <span data-ttu-id="6021e-136">基準原則會列在頁面上, 您可以在完成[需要 mfa](#require-mfa)的步驟之後, 看到 [需要 mfa 的系統管理員] 和 [使用者保護] 已啟用。</span><span class="sxs-lookup"><span data-stu-id="6021e-136">The baseline policies are listed on the page, and you can see that Require MFA for admins and End user protection are already enabled after you completed the steps in [require MFA](#require-mfa).</span></span>

    ![列出條件式存取的基準原則的頁面。](media/casettings.png)
2. <span data-ttu-id="6021e-138">請參閱每個原則的下列特定指示:</span><span class="sxs-lookup"><span data-stu-id="6021e-138">See the following specific instructions for each policy:</span></span>

    - [<span data-ttu-id="6021e-139">需要對系統管理員進行 MFA</span><span class="sxs-lookup"><span data-stu-id="6021e-139">Require MFA for admins</span></span>](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/howto-baseline-protect-administrators)

       
    -   [<span data-ttu-id="6021e-140">使用者需要 MFA</span><span class="sxs-lookup"><span data-stu-id="6021e-140">Require MFA for users</span></span>](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/howto-baseline-protect-end-users)  
    - [<span data-ttu-id="6021e-141">封鎖舊版驗證</span><span class="sxs-lookup"><span data-stu-id="6021e-141">Block legacy authentication</span></span>](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth)
    - [<span data-ttu-id="6021e-142">需要 MFA 來進行服務管理</span><span class="sxs-lookup"><span data-stu-id="6021e-142">Require MFA for service management</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)

<span data-ttu-id="6021e-143">您可以設定額外的原則, 例如要求核准的用戶端應用程式。</span><span class="sxs-lookup"><span data-stu-id="6021e-143">You can set up extra policies, such as requiring approved client apps.</span></span> <span data-ttu-id="6021e-144">如需詳細資訊, 請參閱[條件式存取檔](https://docs.microsoft.com/azure/active-directory/conditional-access/)。</span><span class="sxs-lookup"><span data-stu-id="6021e-144">See the [Conditional Access Documentation](https://docs.microsoft.com/azure/active-directory/conditional-access/) for more information.</span></span>
