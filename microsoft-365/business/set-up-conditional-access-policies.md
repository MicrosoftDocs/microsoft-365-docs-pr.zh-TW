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
search.appverid:
- BCS160
- MET150
- MOE150
description: 瞭解如何設定 Microsoft 365 活動的條件式存取原則，以增加大量額外的安全性。
ms.openlocfilehash: 26fadecc69486d7931dac069d8f53061592f397f
ms.sourcegitcommit: e525bcf073a61e1350484719a0c3ceb6ff0d8db1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/06/2020
ms.locfileid: "43153759"
---
# <a name="set-up-conditional-access-policies"></a><span data-ttu-id="cb39a-103">設定條件式存取原則</span><span class="sxs-lookup"><span data-stu-id="cb39a-103">Set up Conditional Access policies</span></span>

<span data-ttu-id="cb39a-104">[條件式存取](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)原則會增加大量額外的安全性。</span><span class="sxs-lookup"><span data-stu-id="cb39a-104">[Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) policies add substantial additional security.</span></span> <span data-ttu-id="cb39a-105">Microsoft 提供一組為所有客戶建議的基準條件式存取原則。</span><span class="sxs-lookup"><span data-stu-id="cb39a-105">Microsoft provides a set of baseline Conditional Access policies that are recommended for all customers.</span></span> <span data-ttu-id="cb39a-106">基準原則是一組預先定義的原則，可協助保護組織不受許多常見的攻擊。</span><span class="sxs-lookup"><span data-stu-id="cb39a-106">Baseline policies are a set of predefined policies that help protect organizations against many common attacks.</span></span> <span data-ttu-id="cb39a-107">這些常見的攻擊可能包括密碼噴塗、重新顯示和網路釣魚。</span><span class="sxs-lookup"><span data-stu-id="cb39a-107">These common attacks can include password spray, replay, and phishing.</span></span>

<span data-ttu-id="cb39a-108">這些原則要求系統管理員和使用者在符合特定條件時，輸入第二種形式的驗證（稱為多重驗證或 MFA）。</span><span class="sxs-lookup"><span data-stu-id="cb39a-108">These policies require admins and users to enter a second form of authentication (called multifactor authentication, or MFA) when certain conditions are met.</span></span> <span data-ttu-id="cb39a-109">例如，如果使用者從不同的國家/地區登入，則可能會認為登入是危險的，而且使用者必須提供其他形式的驗證。</span><span class="sxs-lookup"><span data-stu-id="cb39a-109">For example, if a user is signing in from a different country, the sign-in might be considered risky and the user must provide an additional form of authentication.</span></span> 

<span data-ttu-id="cb39a-110">目前的基準原則包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="cb39a-110">Currently, baseline policies include the following:</span></span>
- <span data-ttu-id="cb39a-111">**需要** &ndash;對系統管理員進行 MFA，必須對特權最高的系統管理員角色（包括全域管理員）進行多重要素驗證。</span><span class="sxs-lookup"><span data-stu-id="cb39a-111">**Require MFA for admins** &ndash; Requires multi-factor authentication for the most privileged administrator roles, including global administrator.</span></span>
- <span data-ttu-id="cb39a-112">只有在登入危險時 **，使用者才** &ndash;需要使用者的多重要素驗證。</span><span class="sxs-lookup"><span data-stu-id="cb39a-112">**End user protection** &ndash; Requires multi-factor authentication for users only when a sign-in is risky.</span></span> 
- <span data-ttu-id="cb39a-113">**封鎖舊版驗證** &ndash;舊版用戶端應用程式和某些新的應用程式不會使用較新、更安全的驗證通訊協定。</span><span class="sxs-lookup"><span data-stu-id="cb39a-113">**Block legacy authentication** &ndash; Older client apps and some new apps don't use newer, more secure, authentication protocols.</span></span> <span data-ttu-id="cb39a-114">這些繼承應用程式可略過條件式存取原則，並對您的環境進行未授權的存取。</span><span class="sxs-lookup"><span data-stu-id="cb39a-114">These older apps can bypass Conditional Access policies and gain unauthorized access to your environment.</span></span> <span data-ttu-id="cb39a-115">這個原則會封鎖不支援條件式存取之用戶端的存取權。</span><span class="sxs-lookup"><span data-stu-id="cb39a-115">This policy blocks access from clients that don't support Conditional Access.</span></span> 
- <span data-ttu-id="cb39a-116">**需要 MFA for Service management** &ndash;才能存取管理工具（包括 Azure 入口網站（您設定基準原則）的多重要素驗證。</span><span class="sxs-lookup"><span data-stu-id="cb39a-116">**Require MFA for Service Management** &ndash; Requires multi-factor authentication for access to management tools, including Azure portal (where you configure baseline policies).</span></span> 

<span data-ttu-id="cb39a-117">Microsoft 建議您啟用所有的基準原則。</span><span class="sxs-lookup"><span data-stu-id="cb39a-117">Microsoft recommends you enable all of these baseline policies.</span></span> <span data-ttu-id="cb39a-118">啟用這些原則之後，系統會提示系統管理員和使用者註冊 Azure Multii 要素驗證。</span><span class="sxs-lookup"><span data-stu-id="cb39a-118">After these policies are enabled, admins and users will be prompted to register for Azure Multii-Factor authentication.</span></span>

<span data-ttu-id="cb39a-119">如需這些原則的詳細資訊，請參閱[什麼是基準原則](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)？</span><span class="sxs-lookup"><span data-stu-id="cb39a-119">For more information about these policies, see [What are baseline policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)?</span></span>


## <a name="set-up-baseline-policies"></a><span data-ttu-id="cb39a-120">設定基準原則</span><span class="sxs-lookup"><span data-stu-id="cb39a-120">Set up baseline policies</span></span>

1. <span data-ttu-id="cb39a-121">移至[azure 入口網站](https://portal.azure.com)，然後流覽至 [ **azure Active Directory** \> **條件式存取**]。</span><span class="sxs-lookup"><span data-stu-id="cb39a-121">Go to [Azure portal](https://portal.azure.com), and then navigate to **Azure Active Directory** \> **Conditional Access**.</span></span>
    
    <span data-ttu-id="cb39a-122">基準原則會列在頁面上。</span><span class="sxs-lookup"><span data-stu-id="cb39a-122">The baseline policies are listed on the page.</span></span> <br/> <br/>
    <span data-ttu-id="cb39a-123">![列出條件式存取之基準原則的頁面。](../media/baslinepolicies.png)</span><span class="sxs-lookup"><span data-stu-id="cb39a-123">![Page that lists baseline policies for Conditional Access.](../media/baslinepolicies.png)</span></span>
1. <span data-ttu-id="cb39a-124">請參閱下列每個原則的特定指示：</span><span class="sxs-lookup"><span data-stu-id="cb39a-124">See the following specific instructions for each policy:</span></span>

  - [<span data-ttu-id="cb39a-125">需要對系統管理員進行 MFA</span><span class="sxs-lookup"><span data-stu-id="cb39a-125">Require MFA for admins</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-administrators)
- [<span data-ttu-id="cb39a-126">使用者需要 MFA</span><span class="sxs-lookup"><span data-stu-id="cb39a-126">Require MFA for users</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-end-users)  
 - [<span data-ttu-id="cb39a-127">封鎖舊版驗證</span><span class="sxs-lookup"><span data-stu-id="cb39a-127">Block legacy authentication</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth)
  - [<span data-ttu-id="cb39a-128">需要 MFA 進行服務管理</span><span class="sxs-lookup"><span data-stu-id="cb39a-128">Require MFA for service management</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)

<span data-ttu-id="cb39a-129">您可以設定許多額外的原則，例如要求核准的用戶端應用程式。</span><span class="sxs-lookup"><span data-stu-id="cb39a-129">You can set up many additional policies, such as requiring approved client apps.</span></span> <span data-ttu-id="cb39a-130">如需詳細資訊，請參閱[條件式存取檔](https://docs.microsoft.com/azure/active-directory/conditional-access/)。</span><span class="sxs-lookup"><span data-stu-id="cb39a-130">For more information, see the [Conditional Access Documentation](https://docs.microsoft.com/azure/active-directory/conditional-access/).</span></span>
