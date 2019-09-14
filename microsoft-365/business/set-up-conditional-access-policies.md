---
title: 設定 Microsoft 365 行銷活動的條件式存取原則
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
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: 了解如何為 Microsoft 365 行銷活動設定條件式存取原則。
ms.openlocfilehash: 614e3a6e13a14114f40ecf87bf936d4165744503
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/14/2019
ms.locfileid: "36982374"
---
# <a name="set-up-conditional-access-policies"></a><span data-ttu-id="d6c3f-103">設定條件式存取原則</span><span class="sxs-lookup"><span data-stu-id="d6c3f-103">Set up conditional access policies</span></span>

<span data-ttu-id="d6c3f-104">[條件式存取](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)原則新增 substancial 額外的安全性。</span><span class="sxs-lookup"><span data-stu-id="d6c3f-104">[Conditional access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) policies add substancial additional security.</span></span> <span data-ttu-id="d6c3f-105">Microsoft 對於所有客戶提供一組建議的比較基準條件式存取原則。</span><span class="sxs-lookup"><span data-stu-id="d6c3f-105">Microsoft provides a set of baseline conditional access policies that are recommended for all customers.</span></span> <span data-ttu-id="d6c3f-106">[比較基準原則是一組預先定義的原則，以協助保護組織免受許多常見的攻擊。</span><span class="sxs-lookup"><span data-stu-id="d6c3f-106">Baseline policies are a set of predefined policies that help protect organizations against many common attacks.</span></span> <span data-ttu-id="d6c3f-107">密碼噴灑、 重新顯示和網路釣魚，可以包含這些常見的攻擊。</span><span class="sxs-lookup"><span data-stu-id="d6c3f-107">These common attacks can include password spray, replay, and phishing.</span></span>

<span data-ttu-id="d6c3f-108">這些原則需要系統管理員和使用者輸入驗證 （稱為多重要素驗證] 或 [MFA） 第二個表單時符合特定條件。</span><span class="sxs-lookup"><span data-stu-id="d6c3f-108">These policies require admins and users to enter a second form of authentication (called multifactor authentication, or MFA) when certain conditions are met.</span></span> <span data-ttu-id="d6c3f-109">例如，如果使用者從不同的國家/地區登入，登入小可能會被視為風險，使用者必須提供其他形式的驗證。</span><span class="sxs-lookup"><span data-stu-id="d6c3f-109">For example, if a user is signing in from a different country, the sign-in might be considered risky and the user must provide an additional form of authentication.</span></span> 

<span data-ttu-id="d6c3f-110">目前，基準原則包括下列：</span><span class="sxs-lookup"><span data-stu-id="d6c3f-110">Currently, baseline policies include the following:</span></span>
- <span data-ttu-id="d6c3f-111">**系統管理員需要 MFA** — 最小權限的系統管理員角色，包括全域系統管理員需要多重要素驗證。</span><span class="sxs-lookup"><span data-stu-id="d6c3f-111">**Require MFA for admins** — Requires multi-factor authentication for the most privileged administrator roles, including global administrator.</span></span>
- <span data-ttu-id="d6c3f-112">**使用者保護**— 需要多重要素驗證的使用者，只有當時，登入風險。</span><span class="sxs-lookup"><span data-stu-id="d6c3f-112">**End user protection** — Requires multi-factor authentication for users only when a sign-in is risky.</span></span> 
- <span data-ttu-id="d6c3f-113">**封鎖舊版驗證**— 較舊的用戶端應用程式和一些新的應用程式不使用較新、 更安全的驗證通訊協定。</span><span class="sxs-lookup"><span data-stu-id="d6c3f-113">**Block legacy authentication** — Older client apps and some new apps don't use newer, more secure, authentication protocols.</span></span> <span data-ttu-id="d6c3f-114">這些較舊的應用程式可以略過條件式存取原則，且未經授權存取您的環境。</span><span class="sxs-lookup"><span data-stu-id="d6c3f-114">These older apps can bypass conditional access policies and gain unauthorized access to your environment.</span></span> <span data-ttu-id="d6c3f-115">從用戶端不支援條件式存取此原則封鎖存取。</span><span class="sxs-lookup"><span data-stu-id="d6c3f-115">This policy blocks access from clients that don't support conditional access.</span></span> 
- <span data-ttu-id="d6c3f-116">**需要 MFA 的服務管理**-需要多重要素驗證管理工具]，包括 （在您設定基準原則） 的 Azure 入口網站的存取。</span><span class="sxs-lookup"><span data-stu-id="d6c3f-116">**Require MFA for Service Management** — Requires multi-factor authentication for access to management tools, including Azure portal (where you configure baseline policies).</span></span> 

<span data-ttu-id="d6c3f-117">Microsoft 建議您啟用所有的這些基準原則。</span><span class="sxs-lookup"><span data-stu-id="d6c3f-117">Microsoft recommends you enable all of these baseline policies.</span></span> <span data-ttu-id="d6c3f-118">啟用這些原則之後，系統管理員和使用者將會提示註冊為 Azure Multii 雙因素驗證。</span><span class="sxs-lookup"><span data-stu-id="d6c3f-118">After these policies are enabled, admins and users will be prompted to register for Azure Multii-Factor authentication.</span></span>

<span data-ttu-id="d6c3f-119">如需這些原則的詳細資訊，請參閱[什麼是基準原則](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)？</span><span class="sxs-lookup"><span data-stu-id="d6c3f-119">For more information about these policies, see [What are baseline policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)?</span></span>


## <a name="set-up-baseline-policies"></a><span data-ttu-id="d6c3f-120">[比較基準原則設定</span><span class="sxs-lookup"><span data-stu-id="d6c3f-120">Set up baseline policies</span></span>

1. <span data-ttu-id="d6c3f-121">移至[Azure 入口網站](https://portal.azure.com)，然後再瀏覽至 [ **Azure Active Directory** \> **條件式存取**。</span><span class="sxs-lookup"><span data-stu-id="d6c3f-121">Go to [Azure portal](https://portal.azure.com), and then navigate to **Azure Active Directory** \> **Conditional Access**.</span></span>
    
    <span data-ttu-id="d6c3f-122">[比較基準原則會列在 [] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="d6c3f-122">The baseline policies are listed on the page.</span></span> <br/> <br/>
    <span data-ttu-id="d6c3f-123">![] 頁面會列出基準條件式存取原則。](media/baslinepolicies.png)</span><span class="sxs-lookup"><span data-stu-id="d6c3f-123">![Page that lists baseline policies for conditional access.](media/baslinepolicies.png)</span></span>
1. <span data-ttu-id="d6c3f-124">請參閱下列的特定指示，針對每個原則：</span><span class="sxs-lookup"><span data-stu-id="d6c3f-124">See the following specific instructions for each policy:</span></span>

  - [<span data-ttu-id="d6c3f-125">系統管理員需要 MFA</span><span class="sxs-lookup"><span data-stu-id="d6c3f-125">Require MFA for admins</span></span>](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/howto-baseline-protect-administrators)
- [<span data-ttu-id="d6c3f-126">使用者需要 MFA</span><span class="sxs-lookup"><span data-stu-id="d6c3f-126">Require MFA for users</span></span>](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/howto-baseline-protect-end-users)  
 - [<span data-ttu-id="d6c3f-127">封鎖舊版驗證</span><span class="sxs-lookup"><span data-stu-id="d6c3f-127">Block legacy authentication</span></span>](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth)
  - [<span data-ttu-id="d6c3f-128">需要 MFA 的服務管理</span><span class="sxs-lookup"><span data-stu-id="d6c3f-128">Require MFA for service management</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)

<span data-ttu-id="d6c3f-129">您可以設定許多額外的原則，例如需要核准的用戶端應用程式。</span><span class="sxs-lookup"><span data-stu-id="d6c3f-129">You can set up many additional policies, such as requiring approved client apps.</span></span> <span data-ttu-id="d6c3f-130">請參閱如需詳細資訊的[條件式存取文件](https://docs.microsoft.com/azure/active-directory/conditional-access/)。</span><span class="sxs-lookup"><span data-stu-id="d6c3f-130">See the [Conditional Access Documentation](https://docs.microsoft.com/azure/active-directory/conditional-access/) for more information.</span></span>