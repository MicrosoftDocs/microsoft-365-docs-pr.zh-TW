---
title: 設定條件式存取原則
f1.keywords:
- NOCSH
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
description: 了解如何需要 MFA 和 Microsoft 365 商務版設定條件式存取原則。
ms.openlocfilehash: b65cccf9931da4701157f26ffece7a7c90689094
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41594858"
---
# <a name="require-multi-factor-authentication-and-set-up-conditional-access-policies"></a><span data-ttu-id="8b93b-103">需要多重要素驗證和設定條件式存取原則</span><span class="sxs-lookup"><span data-stu-id="8b93b-103">Require multi-factor authentication and set up conditional access policies</span></span>

<span data-ttu-id="8b93b-104">您的資料與多重要素驗證和條件式存取原則保護的存取。</span><span class="sxs-lookup"><span data-stu-id="8b93b-104">You protect access to your data with multi-factor authentication and conditional access policies.</span></span> <span data-ttu-id="8b93b-105">這些增加大量額外的安全性。</span><span class="sxs-lookup"><span data-stu-id="8b93b-105">These add substantial additional security.</span></span> <span data-ttu-id="8b93b-106">Microsoft 對於所有客戶提供一組建議的比較基準條件式存取原則。</span><span class="sxs-lookup"><span data-stu-id="8b93b-106">Microsoft provides a set of baseline conditional access policies that are recommended for all customers.</span></span> <span data-ttu-id="8b93b-107">[比較基準原則是一組預先定義的原則，以協助保護組織免受許多常見的攻擊。</span><span class="sxs-lookup"><span data-stu-id="8b93b-107">Baseline policies are a set of predefined policies that help protect organizations against many common attacks.</span></span> <span data-ttu-id="8b93b-108">密碼噴灑、 重新顯示和網路釣魚，可以包含這些常見的攻擊。</span><span class="sxs-lookup"><span data-stu-id="8b93b-108">These common attacks can include password spray, replay, and phishing.</span></span>

<span data-ttu-id="8b93b-109">這些原則需要系統管理員和使用者輸入驗證 （稱為多重要素驗證] 或 [MFA） 第二個表單時符合特定條件。</span><span class="sxs-lookup"><span data-stu-id="8b93b-109">These policies require admins and users to enter a second form of authentication (called multi-factor authentication, or MFA) when certain conditions are met.</span></span> <span data-ttu-id="8b93b-110">例如，如果您組織中的使用者嘗試從不同的國家/地區或未知的裝置，登入 Microsoft 365，登入小可能會被視為風險。</span><span class="sxs-lookup"><span data-stu-id="8b93b-110">For example, if a user in your organization tries to sign in to Microsoft 365 from a different country or from an unknown device, the sign-in might be considered risky.</span></span> <span data-ttu-id="8b93b-111">使用者必須提供額外的形式的驗證 （例如指紋或程式碼），以證明其身分識別。</span><span class="sxs-lookup"><span data-stu-id="8b93b-111">The user must provide an extra form of authentication (such as a fingerprint or a code) to prove their identity.</span></span> 

<span data-ttu-id="8b93b-112">目前，基準原則包括下列：</span><span class="sxs-lookup"><span data-stu-id="8b93b-112">Currently, baseline policies include the following:</span></span>
- <span data-ttu-id="8b93b-113">Microsoft 365 系統管理中心中設定：</span><span class="sxs-lookup"><span data-stu-id="8b93b-113">Set up in Microsoft 365 admin center:</span></span>
    - <span data-ttu-id="8b93b-114">**系統管理員需要 MFA** — 最小權限的系統管理員角色，包括全域系統管理員需要多重要素驗證。</span><span class="sxs-lookup"><span data-stu-id="8b93b-114">**Require MFA for admins** — Requires multi-factor authentication for the most privileged administrator roles, including global administrator.</span></span>
    - <span data-ttu-id="8b93b-115">**使用者保護**— 需要多重要素驗證的使用者，只有當時，登入風險。</span><span class="sxs-lookup"><span data-stu-id="8b93b-115">**End user protection** — Requires multi-factor authentication for users only when a sign-in is risky.</span></span> 
- <span data-ttu-id="8b93b-116">設定 Azure Active Directory 入口網站中：</span><span class="sxs-lookup"><span data-stu-id="8b93b-116">Set up in Azure Active Directory portal:</span></span>
    - <span data-ttu-id="8b93b-117">**封鎖舊版驗證**— 較舊的用戶端應用程式和一些新的應用程式不使用較新、 更安全的驗證通訊協定。</span><span class="sxs-lookup"><span data-stu-id="8b93b-117">**Block legacy authentication** — Older client apps and some new apps don't use newer, more secure, authentication protocols.</span></span> <span data-ttu-id="8b93b-118">這些較舊的應用程式可以略過條件式存取原則，且未經授權存取您的環境。</span><span class="sxs-lookup"><span data-stu-id="8b93b-118">These older apps can bypass conditional access policies and gain unauthorized access to your environment.</span></span> <span data-ttu-id="8b93b-119">從用戶端不支援條件式存取此原則封鎖存取。</span><span class="sxs-lookup"><span data-stu-id="8b93b-119">This policy blocks access from clients that don't support conditional access.</span></span> 
    - <span data-ttu-id="8b93b-120">**需要 MFA 的服務管理**-需要多重要素驗證管理工具]，包括 （在您設定基準原則） 的 Azure 入口網站的存取。</span><span class="sxs-lookup"><span data-stu-id="8b93b-120">**Require MFA for Service Management** — Requires multi-factor authentication for access to management tools, including Azure portal (where you configure baseline policies).</span></span> 

<span data-ttu-id="8b93b-121">Microsoft 建議您啟用所有的這些基準原則。</span><span class="sxs-lookup"><span data-stu-id="8b93b-121">Microsoft recommends that you enable all of these baseline policies.</span></span> <span data-ttu-id="8b93b-122">啟用這些原則之後，系統管理員和使用者將會提示註冊 Azure 多重要素驗證。</span><span class="sxs-lookup"><span data-stu-id="8b93b-122">After these policies are enabled, admins and users will be prompted to register for Azure Multi-Factor authentication.</span></span>

<span data-ttu-id="8b93b-123">如需這些原則的詳細資訊，請參閱[什麼是基準原則](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)？</span><span class="sxs-lookup"><span data-stu-id="8b93b-123">For more information about these policies, see [What are baseline policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)?</span></span>


## <a name="require-mfa"></a><span data-ttu-id="8b93b-124">需要 MFA</span><span class="sxs-lookup"><span data-stu-id="8b93b-124">Require MFA</span></span>

<span data-ttu-id="8b93b-125">若要要求所有使用者都登入識別碼的第二個表單：</span><span class="sxs-lookup"><span data-stu-id="8b93b-125">To require that all users sign in with a second form of ID:</span></span>

1. <span data-ttu-id="8b93b-126">移至系統管理中心， <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> ，然後選擇 [**安裝程式**。</span><span class="sxs-lookup"><span data-stu-id="8b93b-126">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> and choose **Setup**.</span></span>

2. <span data-ttu-id="8b93b-127">在 [設定] 頁面上選擇 [**產生登入更安全**卡中的**檢視**。</span><span class="sxs-lookup"><span data-stu-id="8b93b-127">On the Setup page, choose **View** in the **Make sign-in more secure** card.</span></span>


    ![請登入更安全的卡片。](media/setupmfa.png)
3. <span data-ttu-id="8b93b-129">在進行登入更安全] 頁面上，選擇 [**開始**]。</span><span class="sxs-lookup"><span data-stu-id="8b93b-129">On the Make sign-in more secure page, choose **Get started**.</span></span>
 
4. <span data-ttu-id="8b93b-130">在 [加強登入安全性] 窗格中，選取 [**需要系統管理員適用的多重要素驗證**，並**要求使用者註冊 multi-factor authentication 並封鎖存取，如果偵測到風險**] 旁的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="8b93b-130">On the Strengthen sign-in security pane, select the check boxes next to **Require multi-factor authentication for admins** and **Require users to register for multi-factor authentication and block access if risk is detected**.</span></span>
    <span data-ttu-id="8b93b-131">請務必從 MFA 需求**尋找使用者**] 方塊中排除[緊急](m365-campaigns-protect-admin-accounts.md#create-an-emergency-admin-account)或 「 中斷玻璃 「 系統管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="8b93b-131">Be sure to exclude the [emergency](m365-campaigns-protect-admin-accounts.md#create-an-emergency-admin-account) or "break-glass" admin account from the MFA requirement in the **Find users** box.</span></span>
    
    ![加強登入安全性] 頁面。](media/requiremfa.png)

5. <span data-ttu-id="8b93b-133">選擇 [上] 頁面底部的 [**建立原則**。</span><span class="sxs-lookup"><span data-stu-id="8b93b-133">Choose **Create policy** on the bottom of the page.</span></span>

## <a name="set-up-baseline-policies"></a><span data-ttu-id="8b93b-134">[比較基準原則設定</span><span class="sxs-lookup"><span data-stu-id="8b93b-134">Set up baseline policies</span></span>

1. <span data-ttu-id="8b93b-135">移至[Azure 入口網站](https://portal.azure.com)，然後再瀏覽至 [ **Azure Active Directory** \> **條件式存取**。</span><span class="sxs-lookup"><span data-stu-id="8b93b-135">Go to [Azure portal](https://portal.azure.com), and then navigate to **Azure Active Directory** \> **Conditional Access**.</span></span>
    
    <span data-ttu-id="8b93b-136">比較基準原則會列出在頁面上，並且您所見，**需要 MFA 的系統管理員**和**使用者保護**已獲您完成中[需要 MFA](#require-mfa)的步驟之後。</span><span class="sxs-lookup"><span data-stu-id="8b93b-136">The baseline policies are listed on the page, and you can see that **Require MFA for admins** and **End user protection** are already enabled after you completed the steps in [require MFA](#require-mfa).</span></span>

    ![] 頁面會列出基準條件式存取原則。](media/casettings.png)
2. <span data-ttu-id="8b93b-138">請參閱下列的特定指示，針對每個原則：</span><span class="sxs-lookup"><span data-stu-id="8b93b-138">See the following specific instructions for each policy:</span></span>

    - [<span data-ttu-id="8b93b-139">系統管理員需要 MFA</span><span class="sxs-lookup"><span data-stu-id="8b93b-139">Require MFA for admins</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-administrators)
    - [<span data-ttu-id="8b93b-140">使用者需要 MFA</span><span class="sxs-lookup"><span data-stu-id="8b93b-140">Require MFA for users</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-end-users)  
    - [<span data-ttu-id="8b93b-141">封鎖舊版驗證</span><span class="sxs-lookup"><span data-stu-id="8b93b-141">Block legacy authentication</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth)
    - [<span data-ttu-id="8b93b-142">需要 MFA 的服務管理</span><span class="sxs-lookup"><span data-stu-id="8b93b-142">Require MFA for service management</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)

<span data-ttu-id="8b93b-143">您可以設定額外的原則，例如需要核准的用戶端應用程式。</span><span class="sxs-lookup"><span data-stu-id="8b93b-143">You can set up extra policies, such as requiring approved client apps.</span></span> <span data-ttu-id="8b93b-144">如需詳細資訊，請參閱[條件式存取文件](https://docs.microsoft.com/azure/active-directory/conditional-access/)。</span><span class="sxs-lookup"><span data-stu-id="8b93b-144">For more information, see the [Conditional Access documentation](https://docs.microsoft.com/azure/active-directory/conditional-access/).</span></span>
