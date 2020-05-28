---
title: 密碼原則建議
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9fa2539a-2211-41fd-85a0-bc37b9619ca4
description: 了解如何加強貴組織對密碼攻擊的防護，以及為何應禁用常見密碼並啟用以風險為根據的多重要素驗證。
ms.openlocfilehash: b4437f2af409fa3040894a1b0f802140df169635
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399311"
---
# <a name="password-policy-recommendations"></a><span data-ttu-id="01454-103">密碼原則建議</span><span class="sxs-lookup"><span data-stu-id="01454-103">Password policy recommendations</span></span>
 
<span data-ttu-id="01454-104">身為組織的系統管理員，您必須為貴組織中的使用者設定密碼原則。</span><span class="sxs-lookup"><span data-stu-id="01454-104">As the admin of an organization, you're responsible for setting password policy for users in your organization.</span></span> <span data-ttu-id="01454-105">設定密碼原則相當複雜且令人困惑，因此本文提供加強貴組織對密碼攻擊的防護的建議。</span><span class="sxs-lookup"><span data-stu-id="01454-105">Setting password policy can be complicated and confusing, and this article provides recommendations to make your organization more secure against password attacks.</span></span>
  
<span data-ttu-id="01454-106">若要判斷貴組織中的 Microsoft 365 密碼到期頻率，請參閱[設定 Microsoft 365 的密碼到期原則](../manage/set-password-expiration-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="01454-106">To determine how often Microsoft 365 passwords expire in your organization, see [Set password expiration policy for Microsoft 365](../manage/set-password-expiration-policy.md).</span></span>
  
## <a name="understanding-password-recommendations"></a><span data-ttu-id="01454-107">了解密碼建議</span><span class="sxs-lookup"><span data-stu-id="01454-107">Understanding password recommendations</span></span>

<span data-ttu-id="01454-108">良好的密碼實踐分為幾大類：</span><span class="sxs-lookup"><span data-stu-id="01454-108">Good password practices fall into a few broad categories:</span></span>
  
- <span data-ttu-id="01454-109">**抵禦常見攻擊**：這涉及選擇讓使用者在何處輸入密碼 (具有良好惡意程式碼偵測的已知和信任的裝置、經過驗證的網站)，以及選擇要選用哪個密碼 (長度和唯一性)。</span><span class="sxs-lookup"><span data-stu-id="01454-109">**Resisting common attacks** This involves the choice of where users enter passwords (known and trusted devices with good malware detection, validated sites), and the choice of what password to choose (length and uniqueness).</span></span>

- <span data-ttu-id="01454-110">**包含成功的攻擊**：包含成功駭客攻擊是指限制僅向特定服務公開，或在使用者密碼遭竊的情況下完全防止該損失。</span><span class="sxs-lookup"><span data-stu-id="01454-110">**Containing successful attacks** Containing successful hacker attacks is about limiting exposure to a specific service, or preventing that damage altogether, if a user's password gets stolen.</span></span> <span data-ttu-id="01454-111">例如，確保社交網路認證外洩不會導致銀行帳戶易受攻擊，也不會讓防護較弱的帳戶接受重要帳戶的重設連結。</span><span class="sxs-lookup"><span data-stu-id="01454-111">For example, ensuring that a breach of your social networking credentials doesn't make your bank account vulnerable, or not letting a poorly guarded account accept reset links for an important account.</span></span>

- <span data-ttu-id="01454-112">**了解人的天性**：許多有效的密碼實踐都在面對自然的人類行為時失敗。</span><span class="sxs-lookup"><span data-stu-id="01454-112">**Understanding human nature** Many valid password practices fail in the face of natural human behaviors.</span></span> <span data-ttu-id="01454-113">了解人的天性至關重要，因為研究結果顯示，幾乎每條強加於使用者的規則都會導致密碼品質降低。</span><span class="sxs-lookup"><span data-stu-id="01454-113">Understanding human nature is critical because research shows that almost every rule you impose on your users will result in a weakening of password quality.</span></span> <span data-ttu-id="01454-114">長度要求、特殊字元要求和密碼變更要求都會導致密碼標準化，讓攻擊者更容易猜測或破解密碼。</span><span class="sxs-lookup"><span data-stu-id="01454-114">Length requirements, special character requirements, and password change requirements all result in normalization of passwords, which makes it easier for attackers to guess or crack passwords.</span></span>

## <a name="password-guidelines-for-administrators"></a><span data-ttu-id="01454-115">系統管理員的密碼指導方針</span><span class="sxs-lookup"><span data-stu-id="01454-115">Password guidelines for administrators</span></span>

<span data-ttu-id="01454-116">加強密碼系統安全的主要目標是密碼多樣性。</span><span class="sxs-lookup"><span data-stu-id="01454-116">The primary goal of a more secure password system is password diversity.</span></span> <span data-ttu-id="01454-117">您希望密碼原則包含許多不同且難以猜測的密碼。</span><span class="sxs-lookup"><span data-stu-id="01454-117">You want your password policy to contain lots of different and hard to guess passwords.</span></span> <span data-ttu-id="01454-118">以下是一些讓貴組織盡可能安全的建議。</span><span class="sxs-lookup"><span data-stu-id="01454-118">Here are a few recommendations for keeping your organization as secure as possible.</span></span>
  
- <span data-ttu-id="01454-119">維持至少 8 個字元的長度要求 (更長不一定更好)</span><span class="sxs-lookup"><span data-stu-id="01454-119">Maintain an 8-character minimum length requirement (longer isn't necessarily better)</span></span>

- <span data-ttu-id="01454-120">不設定字元構成要求。</span><span class="sxs-lookup"><span data-stu-id="01454-120">Don't require character composition requirements.</span></span> <span data-ttu-id="01454-121">例如，\*&amp;(^%$</span><span class="sxs-lookup"><span data-stu-id="01454-121">For example, \*&amp;(^%$</span></span>

- <span data-ttu-id="01454-122">不要求使用者帳戶定期重設密碼</span><span class="sxs-lookup"><span data-stu-id="01454-122">Don't require mandatory periodic password resets for user accounts</span></span>

- <span data-ttu-id="01454-123">禁止常見密碼，使系統中不存在容易受到攻擊的密碼</span><span class="sxs-lookup"><span data-stu-id="01454-123">Ban common passwords, to keep the most vulnerable passwords out of your system</span></span>

- <span data-ttu-id="01454-124">教育使用者不要將其組織密碼重複用於與工作無關的用途</span><span class="sxs-lookup"><span data-stu-id="01454-124">Educate your users to not re-use their organization passwords for non-work related purposes</span></span>

- <span data-ttu-id="01454-125">強制註冊[多重要素驗證](../security-and-compliance/set-up-multi-factor-authentication.md)</span><span class="sxs-lookup"><span data-stu-id="01454-125">Enforce registration for [multi-factor authentication](../security-and-compliance/set-up-multi-factor-authentication.md)</span></span>

- <span data-ttu-id="01454-126">克服以風險為根據的多重要素驗證挑戰</span><span class="sxs-lookup"><span data-stu-id="01454-126">Enable risk-based multi-factor authentication challenges</span></span>

### <a name="password-guidance-for-your-users"></a><span data-ttu-id="01454-127">使用者密碼指導方針</span><span class="sxs-lookup"><span data-stu-id="01454-127">Password guidance for your users</span></span>

<span data-ttu-id="01454-128">以下是提供貴組織使用者的一些密碼指導方針。</span><span class="sxs-lookup"><span data-stu-id="01454-128">Here's some password guidance for users in your organization.</span></span> <span data-ttu-id="01454-129">請務必讓您的使用者了解這些建議，並在組織層級強制執行建議的密碼原則。</span><span class="sxs-lookup"><span data-stu-id="01454-129">Make sure to let your users know about these recommendations and enforce the recommended password policies at the organizational level.</span></span>
  
- <span data-ttu-id="01454-130">請勿使用在任何其他網站上所使用的相同或相似密碼</span><span class="sxs-lookup"><span data-stu-id="01454-130">Don't use a password that is the same or similar to one you use on any other websites</span></span>

- <span data-ttu-id="01454-131">請勿只用一個單字，例如 **password**，也不要使用常用片語，例如 **Iloveyou**</span><span class="sxs-lookup"><span data-stu-id="01454-131">Don't use a single word, for example, **password**, or a commonly-used phrase like **Iloveyou**</span></span>

- <span data-ttu-id="01454-132">使密碼變得難以猜測，讓即使熟悉您的人也難以猜測，例如，不要使用朋友和家人的姓名和生日、喜歡的樂團，以及您喜歡使用的語句</span><span class="sxs-lookup"><span data-stu-id="01454-132">Make passwords hard to guess, even by those who know a lot about you, such as the names and birthdays of your friends and family, your favorite bands, and phrases you like to use</span></span>

## <a name="some-common-approaches-and-their-negative-impacts"></a><span data-ttu-id="01454-133">一些常見做法及其負面影響</span><span class="sxs-lookup"><span data-stu-id="01454-133">Some common approaches and their negative impacts</span></span>

<span data-ttu-id="01454-134">以下是一些最常使用的密碼管理做法，但是研究結果警告我們注意這些做法的負面影響。</span><span class="sxs-lookup"><span data-stu-id="01454-134">These are some of the most commonly used password management practices, but research warns us about the negative impacts of them.</span></span>
  
### <a name="password-expiration-requirements-for-users"></a><span data-ttu-id="01454-135">使用者密碼到期要求</span><span class="sxs-lookup"><span data-stu-id="01454-135">Password expiration requirements for users</span></span>

<span data-ttu-id="01454-136">密碼到期要求弊大於利，因為這些要求會讓使用者選擇可預測的密碼，即由彼此密切相關的連續字詞和數字組成的密碼。</span><span class="sxs-lookup"><span data-stu-id="01454-136">Password expiration requirements do more harm than good, because these requirements make users select predictable passwords, composed of sequential words and numbers which are closely related to each other.</span></span> <span data-ttu-id="01454-137">在這些情況下，下一個密碼可根據先前的密碼來預測。</span><span class="sxs-lookup"><span data-stu-id="01454-137">In these cases, the next password can be predicted based on the previous password.</span></span> <span data-ttu-id="01454-138">密碼到期要求不會提供任何控制優勢，因為網路罪犯總會在盜取憑證後立即使用憑證。</span><span class="sxs-lookup"><span data-stu-id="01454-138">Password expiration requirements offer no containment benefits because cyber criminals almost always use credentials as soon as they compromise them.</span></span>
  
### <a name="requiring-long-passwords"></a><span data-ttu-id="01454-139">要求使用長密碼</span><span class="sxs-lookup"><span data-stu-id="01454-139">Requiring long passwords</span></span>

<span data-ttu-id="01454-140">密碼長度要求 (大於約 10 個字元) 可能會導致可預測且不必要的使用者行為。</span><span class="sxs-lookup"><span data-stu-id="01454-140">Password length requirements (greater than about 10 characters) can result in user behavior that is predictable and undesirable.</span></span> <span data-ttu-id="01454-141">例如，必須具有 16 個字元密碼的使用者可能會選擇 **fourfourfourfour** 或 **passwordpassword** 等符合字元長度要求但不難猜測的重複模式。</span><span class="sxs-lookup"><span data-stu-id="01454-141">For example, users who are required to have a 16-character password may choose repeating patterns like **fourfourfourfour** or **passwordpassword** that meet the character length requirement but aren't hard to guess.</span></span> <span data-ttu-id="01454-142">此外，長度要求會提高使用者採用其他不安全做法的機會，例如將密碼寫下來、重複使用密碼，或將密碼不加密地儲存在文件中。</span><span class="sxs-lookup"><span data-stu-id="01454-142">Additionally, length requirements increase the chances that users will adopt other insecure practices, such as writing their passwords down, re-using them, or storing them unencrypted in their documents.</span></span> <span data-ttu-id="01454-143">若要鼓勵使用者考慮使用唯一密碼，建議您維持符合 8 個字元的最小長度要求。</span><span class="sxs-lookup"><span data-stu-id="01454-143">To encourage users to think about a unique password, we recommend keeping a reasonable 8-character minimum length requirement.</span></span> 
  
### <a name="requiring-the-use-of-multiple-character-sets"></a><span data-ttu-id="01454-144">要求使用多個字元集</span><span class="sxs-lookup"><span data-stu-id="01454-144">Requiring the use of multiple character sets</span></span>

<span data-ttu-id="01454-145">密碼複雜性要求會縮減金鑰空間，並讓使用者以可預測的方式行動，因此弊大於利。</span><span class="sxs-lookup"><span data-stu-id="01454-145">Password complexity requirements reduce key space and cause users to act in predictable ways, doing more harm than good.</span></span> <span data-ttu-id="01454-146">大多數系統都會強制實施一定程度的密碼複雜性要求。</span><span class="sxs-lookup"><span data-stu-id="01454-146">Most systems enforce some level of password complexity requirements.</span></span> <span data-ttu-id="01454-147">例如，密碼需要使用下列所有三種類別的字元：</span><span class="sxs-lookup"><span data-stu-id="01454-147">For example, passwords need characters from all three of the following categories:</span></span>
  
- <span data-ttu-id="01454-148">大寫字元 </span><span class="sxs-lookup"><span data-stu-id="01454-148">uppercase characters</span></span>

- <span data-ttu-id="01454-149">小寫字元</span><span class="sxs-lookup"><span data-stu-id="01454-149">lowercase characters</span></span>

- <span data-ttu-id="01454-150">非英數字元</span><span class="sxs-lookup"><span data-stu-id="01454-150">non-alphanumeric characters</span></span>

<span data-ttu-id="01454-151">大多數使用者都會使用類似的模式，例如，第一個位置使用大寫字母、最後一位使用符號，倒數第 2 位使用數字。</span><span class="sxs-lookup"><span data-stu-id="01454-151">Most people use similar patterns, for example, a capital letter in the first position, a symbol in the last, and a number in the last 2.</span></span> <span data-ttu-id="01454-152">網路罪犯知道這一點，因此他們在執行字典攻擊時會使用最常見的替換，例如：$ 替換為 s、@ 替換為 a，1 替換為 l。</span><span class="sxs-lookup"><span data-stu-id="01454-152">Cyber criminals know this, so they run their dictionary attacks using the most common substitutions, "$" for "s", "@" for "a," "1" for "l".</span></span> <span data-ttu-id="01454-153">強制使用者選擇大寫、小寫、數字、特殊字元的組合會造成負面影響。</span><span class="sxs-lookup"><span data-stu-id="01454-153">Forcing your users to choose a combination of upper, lower, digits, special characters has a negative effect.</span></span> <span data-ttu-id="01454-154">有些複雜性要求甚至會妨礙使用者使用安全易記的密碼，並迫使他們採用安全性較低且更難記住的密碼。</span><span class="sxs-lookup"><span data-stu-id="01454-154">Some complexity requirements even prevent users from using secure and memorable passwords, and force them into coming up with less secure and less memorable passwords.</span></span>
  
## <a name="successful-patterns"></a><span data-ttu-id="01454-155">成功的模式</span><span class="sxs-lookup"><span data-stu-id="01454-155">Successful Patterns</span></span>

<span data-ttu-id="01454-156">相比之下，以下是鼓勵密碼多樣性的一些建議。</span><span class="sxs-lookup"><span data-stu-id="01454-156">In contrast, here are some recommendations in encouraging password diversity.</span></span>
  
### <a name="ban-common-passwords"></a><span data-ttu-id="01454-157">禁用常見密碼</span><span class="sxs-lookup"><span data-stu-id="01454-157">Ban common passwords</span></span>

<span data-ttu-id="01454-158">建立密碼時，您應對使用者提出的最重要的密碼要求是禁用常見密碼，使貴組織更不容易受到暴力密碼破解攻擊。</span><span class="sxs-lookup"><span data-stu-id="01454-158">The most important password requirement you should put on your users when creating passwords is to ban the use of common passwords to reduce your organization's susceptibility to brute force password attacks.</span></span> <span data-ttu-id="01454-159">常見的使用者密碼包括 **abdcefg**、**password**、**monkey**。</span><span class="sxs-lookup"><span data-stu-id="01454-159">Common user passwords include, **abdcefg**, **password**, **monkey**.</span></span>
  
### <a name="educate-users-to-not-re-use-organization-passwords-anywhere-else"></a><span data-ttu-id="01454-160">教育使用者不要在其他位置重複使用組織密碼</span><span class="sxs-lookup"><span data-stu-id="01454-160">Educate users to not re-use organization passwords anywhere else</span></span>

<span data-ttu-id="01454-161">要傳達給組織內部使用者的最重要訊息之一是不要在任何其他位置重複使用其組織密碼。</span><span class="sxs-lookup"><span data-stu-id="01454-161">One of the most important messages to get across to users in your organization is to not re-use their organization password anywhere else.</span></span> <span data-ttu-id="01454-162">在外部網站使用組織密碼會大幅增加網路罪犯盜用這些密碼的可能性。</span><span class="sxs-lookup"><span data-stu-id="01454-162">The use of organization passwords in external websites greatly increases the likelihood that cyber criminals will compromise these passwords.</span></span>
  
### <a name="enforce-multi-factor-authentication-registration"></a><span data-ttu-id="01454-163">強制執行多重要素驗證註冊</span><span class="sxs-lookup"><span data-stu-id="01454-163">Enforce Multi-Factor Authentication registration</span></span>

<span data-ttu-id="01454-164">請確保您的使用者更新連絡人和安全性資訊，例如備用電子郵件地址、電話號碼或註冊接收推播通知的裝置，以便讓使用者應對安全性挑戰及收到安全性事件通知。</span><span class="sxs-lookup"><span data-stu-id="01454-164">Make sure your users update contact and security information, like an alternate email address, phone number, or a device registered for push notifications, so they can respond to security challenges and be notified of security events.</span></span> <span data-ttu-id="01454-165">更新的連絡人和安全性資訊可協助使用者在忘記密碼時或其他人嘗試接管其帳戶時驗證他們的身分。</span><span class="sxs-lookup"><span data-stu-id="01454-165">Updated contact and security information helps users verify their identity if they ever forget their password, or if someone else tries to take over their account.</span></span> <span data-ttu-id="01454-166">並在登入嘗試或變更密碼等安全性事件的情況下提供頻外通知頻道。</span><span class="sxs-lookup"><span data-stu-id="01454-166">It also provides an out of band notification channel in the case of security events such as login attempts or changed passwords.</span></span> 
  
<span data-ttu-id="01454-167">若要深入瞭解，請參閱[設定多重要素驗證](../security-and-compliance/set-up-multi-factor-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="01454-167">To learn more, see [Set up multi-factor authentication](../security-and-compliance/set-up-multi-factor-authentication.md).</span></span>
  
### <a name="enable-risk-based-multi-factor-authentication"></a><span data-ttu-id="01454-168">啟用以風險為根據的多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="01454-168">Enable risk-based multi-factor authentication</span></span>

<span data-ttu-id="01454-169">以風險為根據的多重要素驗證可確保系統偵測到可疑活動時，能迫使使用者確保其為合法帳戶擁有者。</span><span class="sxs-lookup"><span data-stu-id="01454-169">Risk-based multi-factor authentication ensures that when our system detects suspicious activity, it can challenge the user to ensure that they are the legitimate account owner.</span></span> 
  
## <a name="want-to-know-more-recommended-reading"></a><span data-ttu-id="01454-170">想要進一步了解嗎？</span><span class="sxs-lookup"><span data-stu-id="01454-170">Want to know more?</span></span> <span data-ttu-id="01454-171">建議閱讀</span><span class="sxs-lookup"><span data-stu-id="01454-171">Recommended reading</span></span>

- <span data-ttu-id="01454-172">[Do Strong Web Passwords Accomplish Anything?](https://go.microsoft.com/fwlink/p/?linkid=861008) (強大的網站密碼是否有用？)</span><span class="sxs-lookup"><span data-stu-id="01454-172">[Do Strong Web Passwords Accomplish Anything?](https://go.microsoft.com/fwlink/p/?linkid=861008)</span></span>

- <span data-ttu-id="01454-173">[Password Portfolios and the Finite-Effort User](https://go.microsoft.com/fwlink/p/?linkid=861014) (密碼組合和努力有限的使用者)</span><span class="sxs-lookup"><span data-stu-id="01454-173">[Password Portfolios and the Finite-Effort User](https://go.microsoft.com/fwlink/p/?linkid=861014)</span></span>

- <span data-ttu-id="01454-174">[Preventing Weak Passwords by Reading Users' Minds](https://go.microsoft.com/fwlink/p/?linkid=861015) (透過閱讀使用者的思維來防止弱式密碼)</span><span class="sxs-lookup"><span data-stu-id="01454-174">[Preventing Weak Passwords by Reading Users' Minds](https://go.microsoft.com/fwlink/p/?linkid=861015)</span></span>

- <span data-ttu-id="01454-175">[Choosing Secure Passwords](https://go.microsoft.com/fwlink/p/?linkid=861016) (選擇安全密碼)</span><span class="sxs-lookup"><span data-stu-id="01454-175">[Choosing Secure Passwords](https://go.microsoft.com/fwlink/p/?linkid=861016)</span></span>

- <span data-ttu-id="01454-176">[Time to rethink mandatory password changes](https://go.microsoft.com/fwlink/p/?linkid=861018) (是時候重新思考強制密碼變更了)</span><span class="sxs-lookup"><span data-stu-id="01454-176">[Time to rethink mandatory password changes](https://go.microsoft.com/fwlink/p/?linkid=861018)</span></span>

- <span data-ttu-id="01454-177">[Worst Passwords of 2015](https://go.microsoft.com/fwlink/p/?linkid=861020) (2015 年最差密碼)</span><span class="sxs-lookup"><span data-stu-id="01454-177">[Worst Passwords of 2015](https://go.microsoft.com/fwlink/p/?linkid=861020)</span></span>

- <span data-ttu-id="01454-178">[Download files from the web](https://go.microsoft.com/fwlink/p/?linkid=861029) (從網頁下載檔案)</span><span class="sxs-lookup"><span data-stu-id="01454-178">[Download files from the web](https://go.microsoft.com/fwlink/p/?linkid=861029)</span></span>
