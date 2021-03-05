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
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: 瞭解如何要求 MFA 和設定適用于商務用 Microsoft 365 的條件式存取原則。
ms.openlocfilehash: e16b7f4ff7d215ee749435806be214a807cc60a4
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/04/2021
ms.locfileid: "50453666"
---
# <a name="require-multi-factor-authentication-and-set-up-conditional-access-policies"></a><span data-ttu-id="e105a-103">需要多重要素驗證並設定條件式存取原則</span><span class="sxs-lookup"><span data-stu-id="e105a-103">Require multi-factor authentication and set up conditional access policies</span></span>

<span data-ttu-id="e105a-104">您可以使用多重要素驗證和條件式存取原則來保護您的資料存取權。</span><span class="sxs-lookup"><span data-stu-id="e105a-104">You protect access to your data with multi-factor authentication and conditional access policies.</span></span> <span data-ttu-id="e105a-105">這會增加大量額外的安全性。</span><span class="sxs-lookup"><span data-stu-id="e105a-105">These add substantial additional security.</span></span> <span data-ttu-id="e105a-106">Microsoft 提供一組為所有客戶建議的基準條件式存取原則。</span><span class="sxs-lookup"><span data-stu-id="e105a-106">Microsoft provides a set of baseline conditional access policies that are recommended for all customers.</span></span> <span data-ttu-id="e105a-107">基準原則是一組預先定義的原則，可協助保護組織不受許多常見的攻擊。</span><span class="sxs-lookup"><span data-stu-id="e105a-107">Baseline policies are a set of predefined policies that help protect organizations against many common attacks.</span></span> <span data-ttu-id="e105a-108">這些常見的攻擊可能包括密碼噴塗、重新顯示和網路釣魚。</span><span class="sxs-lookup"><span data-stu-id="e105a-108">These common attacks can include password spray, replay, and phishing.</span></span>

<span data-ttu-id="e105a-109">這些原則要求系統管理員和使用者輸入另一種形式的驗證 (稱為多重要素驗證，或在某些情況下進行 MFA) 。</span><span class="sxs-lookup"><span data-stu-id="e105a-109">These policies require admins and users to enter a second form of authentication (called multi-factor authentication, or MFA) under certain conditions.</span></span> <span data-ttu-id="e105a-110">例如，如果您組織中的使用者企圖從不同的國家/地區或從未知的裝置登入 Microsoft 365，該登入可能會被視為危險。</span><span class="sxs-lookup"><span data-stu-id="e105a-110">For example, if a user in your organization tries to sign in to Microsoft 365 from a different country or from an unknown device, the sign-in might be considered risky.</span></span> <span data-ttu-id="e105a-111">使用者必須提供另一種形式的驗證 (例如指紋或程式碼) ，以證明其身分識別。</span><span class="sxs-lookup"><span data-stu-id="e105a-111">The user must provide an extra form of authentication (such as a fingerprint or a code) to prove their identity.</span></span>

<span data-ttu-id="e105a-112">目前的基準原則包括下列原則：</span><span class="sxs-lookup"><span data-stu-id="e105a-112">Currently, the baseline policies include the following policies:</span></span>

- <span data-ttu-id="e105a-113">在 Microsoft 365 系統管理中心中設定：</span><span class="sxs-lookup"><span data-stu-id="e105a-113">Set up in Microsoft 365 admin center:</span></span>
  - <span data-ttu-id="e105a-114">**需要對系統管理員進行 MFA**：對特權最高的系統管理員角色（包括全域管理員）需要多重要素驗證。</span><span class="sxs-lookup"><span data-stu-id="e105a-114">**Require MFA for admins**: Requires multi-factor authentication for the most privileged administrator roles, including global administrator.</span></span>
  - <span data-ttu-id="e105a-115">**使用者保護**：只有在登入危險時，才需要使用者的多重要素驗證。</span><span class="sxs-lookup"><span data-stu-id="e105a-115">**End-user protection**: Requires multi-factor authentication for users only when a sign-in is risky.</span></span> 
- <span data-ttu-id="e105a-116">在 Azure Active Directory 入口網站中設定：</span><span class="sxs-lookup"><span data-stu-id="e105a-116">Set up in Azure Active Directory portal:</span></span>
  - <span data-ttu-id="e105a-117">**封鎖舊版驗證**：舊版用戶端應用程式和某些新的應用程式不會使用較新、更安全的驗證通訊協定。</span><span class="sxs-lookup"><span data-stu-id="e105a-117">**Block legacy authentication**: Older client apps and some new apps don't use newer, more secure, authentication protocols.</span></span> <span data-ttu-id="e105a-118">這些繼承應用程式可略過條件式存取原則，並對您的環境進行未授權的存取。</span><span class="sxs-lookup"><span data-stu-id="e105a-118">These older apps can bypass conditional access policies and gain unauthorized access to your environment.</span></span> <span data-ttu-id="e105a-119">這個原則會封鎖不支援條件式存取之用戶端的存取權。</span><span class="sxs-lookup"><span data-stu-id="e105a-119">This policy blocks access from clients that don't support conditional access.</span></span> 
  - <span data-ttu-id="e105a-120">**需要 MFA 進行服務管理**：在存取管理工具（包括 Azure 入口網站 (，以) 設定基準原則）時，需要多重要素驗證。</span><span class="sxs-lookup"><span data-stu-id="e105a-120">**Require MFA for Service Management**: Requires multi-factor authentication for access to management tools, including Azure portal (where you configure baseline policies).</span></span>

<span data-ttu-id="e105a-121">建議您啟用所有的基準原則。</span><span class="sxs-lookup"><span data-stu-id="e105a-121">We recommend that you enable all of these baseline policies.</span></span> <span data-ttu-id="e105a-122">啟用這些原則之後，系統會提示系統管理員和使用者註冊 Azure AD 多重要素驗證。</span><span class="sxs-lookup"><span data-stu-id="e105a-122">After these policies are enabled, admins and users will be prompted to register for Azure AD Multifactor Authentication.</span></span>

<span data-ttu-id="e105a-123">如需這些原則的詳細資訊，請參閱 [什麼是基準原則](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)？</span><span class="sxs-lookup"><span data-stu-id="e105a-123">For more information about these policies, see [What are baseline policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)?</span></span>

## <a name="require-mfa"></a><span data-ttu-id="e105a-124">需要 MFA</span><span class="sxs-lookup"><span data-stu-id="e105a-124">Require MFA</span></span>

<span data-ttu-id="e105a-125">若要要求所有使用者使用第二種形式的 ID: 登入</span><span class="sxs-lookup"><span data-stu-id="e105a-125">To require that all users sign in with a second form of ID:</span></span>

1. <span data-ttu-id="e105a-126">移至 [系統管理中心] <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> ，然後選擇 [ **設定**]。</span><span class="sxs-lookup"><span data-stu-id="e105a-126">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> and choose **Setup**.</span></span>

2. <span data-ttu-id="e105a-127">在 [安裝] 頁面上，選擇 [**建立更安全** 的智慧卡] 中的 [**查看**]。</span><span class="sxs-lookup"><span data-stu-id="e105a-127">On the Setup page, choose **View** in the **Make sign-in more secure** card.</span></span>

    ![讓登入更安全的卡片。](../media/setupmfa.png)
3. <span data-ttu-id="e105a-129">在 [使登入更安全] 頁面上，選擇 [ **入門**]。</span><span class="sxs-lookup"><span data-stu-id="e105a-129">On the Make sign-in more secure page, choose **Get started**.</span></span>

4. <span data-ttu-id="e105a-130">在 [強化登入安全性] 窗格中，選取 [ **需要系統管理員的多重要素驗證** ] 旁的核取方塊，並 **要求使用者註冊多重要素驗證，並在偵測到風險時，封鎖存取權**。</span><span class="sxs-lookup"><span data-stu-id="e105a-130">On the Strengthen sign-in security pane, select the check boxes next to **Require multi-factor authentication for admins** and **Require users to register for multi-factor authentication and block access if risk is detected**.</span></span>
    <span data-ttu-id="e105a-131">請務必在 [**尋找使用者**] 方塊中，從 MFA 要求中排除 [緊急](m365-campaigns-protect-admin-accounts.md#create-an-emergency-admin-account)或「中斷玻璃」管理帳戶。</span><span class="sxs-lookup"><span data-stu-id="e105a-131">Be sure to exclude the [emergency](m365-campaigns-protect-admin-accounts.md#create-an-emergency-admin-account) or "break-glass" admin account from the MFA requirement in the **Find users** box.</span></span>

    ![增強內建安全性頁面。](../media/requiremfa.png)

5. <span data-ttu-id="e105a-133">選擇頁面底部的 [ **建立原則** ]。</span><span class="sxs-lookup"><span data-stu-id="e105a-133">Choose **Create policy** on the bottom of the page.</span></span>

## <a name="set-up-baseline-policies"></a><span data-ttu-id="e105a-134">設定基準原則</span><span class="sxs-lookup"><span data-stu-id="e105a-134">Set up baseline policies</span></span>

1. <span data-ttu-id="e105a-135">移至 [azure 入口網站](https://portal.azure.com)，然後流覽至 **azure Active Directory** \> **安全性** \> **條件式存取** ，以建立 **新的原則**。</span><span class="sxs-lookup"><span data-stu-id="e105a-135">Go to the [Azure portal](https://portal.azure.com), and then navigate to **Azure Active Directory** \> **Security** \> **Conditional Access** to create a **new policy**.</span></span>

<span data-ttu-id="e105a-136">請參閱下列每個原則的特定指示：</span><span class="sxs-lookup"><span data-stu-id="e105a-136">See the following specific instructions for each policy:</span></span> <br>
    - [<span data-ttu-id="e105a-137">需要對系統管理員進行 MFA</span><span class="sxs-lookup"><span data-stu-id="e105a-137">Require MFA for admins</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-administrators) <br>
    - [<span data-ttu-id="e105a-138">使用者需要 MFA</span><span class="sxs-lookup"><span data-stu-id="e105a-138">Require MFA for users</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-end-users) <br>
    - [<span data-ttu-id="e105a-139">封鎖舊版驗證</span><span class="sxs-lookup"><span data-stu-id="e105a-139">Block legacy authentication</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth) <br>
    - [<span data-ttu-id="e105a-140">需要 MFA 進行服務管理</span><span class="sxs-lookup"><span data-stu-id="e105a-140">Require MFA for service management</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)

> [!NOTE]
> <span data-ttu-id="e105a-141">預覽原則已不存在，使用者將需要建立其本身的原則。</span><span class="sxs-lookup"><span data-stu-id="e105a-141">Preview policies no longer exist and users will need to create their own policies.</span></span>

<span data-ttu-id="e105a-142">您可以設定額外的原則，例如要求核准的用戶端應用程式。</span><span class="sxs-lookup"><span data-stu-id="e105a-142">You can set up extra policies, such as requiring approved client apps.</span></span> <span data-ttu-id="e105a-143">如需詳細資訊，請參閱 [條件式存取檔](https://docs.microsoft.com/azure/active-directory/conditional-access/)。</span><span class="sxs-lookup"><span data-stu-id="e105a-143">For more information, see the [Conditional Access documentation](https://docs.microsoft.com/azure/active-directory/conditional-access/).</span></span>
