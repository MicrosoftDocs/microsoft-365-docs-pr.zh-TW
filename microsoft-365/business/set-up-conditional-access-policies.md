---
title: 設定 Microsoft 365 活動的條件式存取原則
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
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: 瞭解如何設定 Microsoft 365 活動的條件式存取原則，以增加大量額外的安全性。
ms.openlocfilehash: d7c9cfee2ef00e4ebe231a28ccca185c10f53c6b
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2020
ms.locfileid: "44403011"
---
# <a name="set-up-conditional-access-policies"></a><span data-ttu-id="30f4c-103">設定條件式存取原則</span><span class="sxs-lookup"><span data-stu-id="30f4c-103">Set up conditional access policies</span></span>

<span data-ttu-id="30f4c-104">[條件式存取](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)原則會增加大量額外的安全性。</span><span class="sxs-lookup"><span data-stu-id="30f4c-104">[Conditional access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) policies add substantial additional security.</span></span> <span data-ttu-id="30f4c-105">Microsoft 提供一組為所有客戶建議的基準條件式存取原則。</span><span class="sxs-lookup"><span data-stu-id="30f4c-105">Microsoft provides a set of baseline conditional access policies that are recommended for all customers.</span></span> <span data-ttu-id="30f4c-106">基準原則是一組預先定義的原則，可協助保護組織不受許多常見的攻擊。</span><span class="sxs-lookup"><span data-stu-id="30f4c-106">Baseline policies are a set of predefined policies that help protect organizations against many common attacks.</span></span> <span data-ttu-id="30f4c-107">這些常見的攻擊可能包括密碼噴塗、重新顯示和網路釣魚。</span><span class="sxs-lookup"><span data-stu-id="30f4c-107">These common attacks can include password spray, replay, and phishing.</span></span>

<span data-ttu-id="30f4c-108">這些原則要求系統管理員和使用者在符合特定條件時，輸入第二種形式的驗證（稱為多重驗證或 MFA）。</span><span class="sxs-lookup"><span data-stu-id="30f4c-108">These policies require admins and users to enter a second form of authentication (called multifactor authentication, or MFA) when certain conditions are met.</span></span> <span data-ttu-id="30f4c-109">例如，如果使用者從不同的國家/地區登入，則可能會認為登入是危險的，而且使用者必須提供其他形式的驗證。</span><span class="sxs-lookup"><span data-stu-id="30f4c-109">For example, if a user is signing in from a different country, the sign-in might be considered risky and the user must provide an additional form of authentication.</span></span> 

<span data-ttu-id="30f4c-110">目前的基準原則包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="30f4c-110">Currently, baseline policies include the following:</span></span>
- <span data-ttu-id="30f4c-111">**需要對系統管理員** &ndash; 進行 MFA需要對最具許可權的系統管理員角色（包括全域管理員）進行多重要素驗證。</span><span class="sxs-lookup"><span data-stu-id="30f4c-111">**Require MFA for admins** &ndash; Requires multi-factor authentication for the most privileged administrator roles, including global administrator.</span></span>
- <span data-ttu-id="30f4c-112">**使用者保護** &ndash;只有在登入危險時，才需要使用者的多重要素驗證。</span><span class="sxs-lookup"><span data-stu-id="30f4c-112">**End user protection** &ndash; Requires multi-factor authentication for users only when a sign-in is risky.</span></span> 
- <span data-ttu-id="30f4c-113">**封鎖舊版驗證** &ndash;舊版用戶端應用程式和某些新的應用程式不會使用較新、更安全的驗證通訊協定。</span><span class="sxs-lookup"><span data-stu-id="30f4c-113">**Block legacy authentication** &ndash; Older client apps and some new apps don't use newer, more secure, authentication protocols.</span></span> <span data-ttu-id="30f4c-114">這些繼承應用程式可略過條件式存取原則，並對您的環境進行未授權的存取。</span><span class="sxs-lookup"><span data-stu-id="30f4c-114">These older apps can bypass conditional access policies and gain unauthorized access to your environment.</span></span> <span data-ttu-id="30f4c-115">這個原則會封鎖不支援條件式存取之用戶端的存取權。</span><span class="sxs-lookup"><span data-stu-id="30f4c-115">This policy blocks access from clients that don't support conditional access.</span></span> 
- <span data-ttu-id="30f4c-116">**需要 MFA 進行服務管理** &ndash;需要多重要素驗證，以存取管理工具，包含 Azure 入口網站（您設定基準原則的位置）。</span><span class="sxs-lookup"><span data-stu-id="30f4c-116">**Require MFA for Service Management** &ndash; Requires multi-factor authentication for access to management tools, including Azure portal (where you configure baseline policies).</span></span> 

<span data-ttu-id="30f4c-117">Microsoft 建議您啟用所有的基準原則。</span><span class="sxs-lookup"><span data-stu-id="30f4c-117">Microsoft recommends you enable all of these baseline policies.</span></span> <span data-ttu-id="30f4c-118">啟用這些原則之後，系統會提示系統管理員和使用者註冊 Azure Multii 要素驗證。</span><span class="sxs-lookup"><span data-stu-id="30f4c-118">After these policies are enabled, admins and users will be prompted to register for Azure Multii-Factor authentication.</span></span>

<span data-ttu-id="30f4c-119">如需這些原則的詳細資訊，請參閱[什麼是基準原則](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)？</span><span class="sxs-lookup"><span data-stu-id="30f4c-119">For more information about these policies, see [What are baseline policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)?</span></span>


## <a name="set-up-baseline-policies"></a><span data-ttu-id="30f4c-120">設定基準原則</span><span class="sxs-lookup"><span data-stu-id="30f4c-120">Set up baseline policies</span></span>

1. <span data-ttu-id="30f4c-121">移至[azure 入口網站](https://portal.azure.com)，然後流覽至 [ **azure Active Directory** \> **條件式存取**]。</span><span class="sxs-lookup"><span data-stu-id="30f4c-121">Go to [Azure portal](https://portal.azure.com), and then navigate to **Azure Active Directory** \> **Conditional Access**.</span></span>
    
    <span data-ttu-id="30f4c-122">基準原則會列在頁面上。</span><span class="sxs-lookup"><span data-stu-id="30f4c-122">The baseline policies are listed on the page.</span></span> <br/> <br/>
    <span data-ttu-id="30f4c-123">![列出條件式存取之基準原則的頁面。](../media/baslinepolicies.png)</span><span class="sxs-lookup"><span data-stu-id="30f4c-123">![Page that lists baseline policies for conditional access.](../media/baslinepolicies.png)</span></span>
1. <span data-ttu-id="30f4c-124">請參閱下列每個原則的特定指示：</span><span class="sxs-lookup"><span data-stu-id="30f4c-124">See the following specific instructions for each policy:</span></span>

  - [<span data-ttu-id="30f4c-125">需要對系統管理員進行 MFA</span><span class="sxs-lookup"><span data-stu-id="30f4c-125">Require MFA for admins</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-administrators)
- [<span data-ttu-id="30f4c-126">使用者需要 MFA</span><span class="sxs-lookup"><span data-stu-id="30f4c-126">Require MFA for users</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-end-users)  
 - [<span data-ttu-id="30f4c-127">封鎖舊版驗證</span><span class="sxs-lookup"><span data-stu-id="30f4c-127">Block legacy authentication</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth)
  - [<span data-ttu-id="30f4c-128">需要 MFA 進行服務管理</span><span class="sxs-lookup"><span data-stu-id="30f4c-128">Require MFA for service management</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)

<span data-ttu-id="30f4c-129">您可以設定許多額外的原則，例如要求核准的用戶端應用程式。</span><span class="sxs-lookup"><span data-stu-id="30f4c-129">You can set up many additional policies, such as requiring approved client apps.</span></span> <span data-ttu-id="30f4c-130">如需詳細資訊，請參閱[條件式存取檔](https://docs.microsoft.com/azure/active-directory/conditional-access/)。</span><span class="sxs-lookup"><span data-stu-id="30f4c-130">For more information, see the [Conditional Access Documentation](https://docs.microsoft.com/azure/active-directory/conditional-access/).</span></span>
