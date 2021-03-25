---
title: 回應遭入侵的電子郵件帳戶
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.collection:
- o365_security_incident_response
- M365-security-compliance
- m365solution-smb
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
localization_priority: Priority
search.appverid:
- MET150
description: 了解如何使用可用工具辨識及回應 Microsoft 365 中遭入侵的電子郵件帳戶。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a1bf2a5dbc7e1fdd447baf76fd051abff88b4b30
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203585"
---
# <a name="responding-to-a-compromised-email-account"></a><span data-ttu-id="6f077-103">回應遭入侵的電子郵件帳戶</span><span class="sxs-lookup"><span data-stu-id="6f077-103">Responding to a Compromised Email Account</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="6f077-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="6f077-104">**Applies to**</span></span>
- [<span data-ttu-id="6f077-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="6f077-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="6f077-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="6f077-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="6f077-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6f077-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="6f077-108">**摘要** 了解如何辨識及回應 Microsoft 365 中遭入侵的電子郵件帳戶。</span><span class="sxs-lookup"><span data-stu-id="6f077-108">**Summary** Learn how to recognize and respond to a compromised email account in Microsoft 365.</span></span>

## <a name="what-is-a-compromised-email-account-in-microsoft-365"></a><span data-ttu-id="6f077-109">什麼是 Microsoft 365 中遭入侵的電子郵件帳戶？</span><span class="sxs-lookup"><span data-stu-id="6f077-109">What is a Compromised Email Account in Microsoft 365?</span></span>

<span data-ttu-id="6f077-110">對 Microsoft 365 信箱、資料和其他服務的存取，是透過使用使用者名稱和密碼或 PIN 之類的認證來控制。</span><span class="sxs-lookup"><span data-stu-id="6f077-110">Access to Microsoft 365 mailboxes, data and other services, is controlled through the use of credentials, for example a user name and password or PIN.</span></span> <span data-ttu-id="6f077-111">當預期使用者以外的其他人竊取這些認證時，遭竊的認證會被視為遭入侵。</span><span class="sxs-lookup"><span data-stu-id="6f077-111">When someone other than the intended user steals those credentials, the stolen credentials are considered to be compromised.</span></span> <span data-ttu-id="6f077-112">攻擊者可以使用這些認證以原始使用者身分登入，並執行非法動作。</span><span class="sxs-lookup"><span data-stu-id="6f077-112">With them the attacker can sign in as the original user and perform illicit actions.</span></span>
<span data-ttu-id="6f077-113">攻擊者可以使用遭竊的認證來存取使用者的 Microsoft 365 信箱、SharePoint 資料夾或使用者 OneDrive 中的檔案。</span><span class="sxs-lookup"><span data-stu-id="6f077-113">Using the stolen credentials, the attacker can access the user's Microsoft 365 mailbox, SharePoint folders, or files in the user's OneDrive.</span></span> <span data-ttu-id="6f077-114">一個常見的動作是攻擊者以原始使用者的身分傳送電子郵件給組織內外的收件者。</span><span class="sxs-lookup"><span data-stu-id="6f077-114">One action commonly seen is the attacker sending emails as the original user to recipients both inside and outside of the organization.</span></span> <span data-ttu-id="6f077-115">當攻擊者以電子郵件寄送資料給外部收件者時，這稱為資料外流。</span><span class="sxs-lookup"><span data-stu-id="6f077-115">When the attacker emails data to external recipients, this is called data exfiltration.</span></span>

## <a name="symptoms-of-a-compromised-microsoft-email-account"></a><span data-ttu-id="6f077-116">遭入侵的 Microsoft 電子郵件帳戶症狀</span><span class="sxs-lookup"><span data-stu-id="6f077-116">Symptoms of a Compromised Microsoft Email Account</span></span>

<span data-ttu-id="6f077-117">使用者可能會注意到並報告其 Microsoft 365 信箱中的異常活動。</span><span class="sxs-lookup"><span data-stu-id="6f077-117">Users might notice and report unusual activity in their Microsoft 365 mailboxes.</span></span> <span data-ttu-id="6f077-118">以下是一些常見的症狀：</span><span class="sxs-lookup"><span data-stu-id="6f077-118">Here are some common symptoms:</span></span>

- <span data-ttu-id="6f077-119">可疑的活動，例如遺失或刪除的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="6f077-119">Suspicious activity, such as missing or deleted emails.</span></span>

- <span data-ttu-id="6f077-120">其他使用者可能會收到來自遭入侵帳戶的電子郵件，該帳戶寄件者的 [寄件備份] 資料夾中不存在對應的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="6f077-120">Other users might receive emails from the compromised account without the corresponding email existing in the **Sent Items** folder of the sender.</span></span>

- <span data-ttu-id="6f077-121">出現不是由預期使用者或系統管理員所建立的收件匣規則。</span><span class="sxs-lookup"><span data-stu-id="6f077-121">The presence of inbox rules that weren't created by the intended user or the administrator.</span></span> <span data-ttu-id="6f077-122">這些規則可能會自動將電子郵件轉寄到未知的地址，或將電子郵件移到 [記事]、[垃圾郵件] 或 [RSS 訂閱] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="6f077-122">These rules may automatically forward emails to unknown addresses or move them to the **Notes**, **Junk Email**, or **RSS Subscriptions** folders.</span></span>

- <span data-ttu-id="6f077-123">全域通訊清單中使用者的顯示名稱可能會變更。</span><span class="sxs-lookup"><span data-stu-id="6f077-123">The user's display name might be changed in the Global Address List.</span></span>

- <span data-ttu-id="6f077-124">使用者的信箱遭封鎖而無法傳送電子郵件。</span><span class="sxs-lookup"><span data-stu-id="6f077-124">The user's mailbox is blocked from sending email.</span></span>

- <span data-ttu-id="6f077-125">在 Microsoft Outlook 或 Outlook 網頁版 (先前稱為 Outlook Web App) 中的 [寄件備份] 或 [刪除的郵件] 資料夾包含常見遭入侵帳戶的郵件，例如「我卡在倫敦了，給我錢」。</span><span class="sxs-lookup"><span data-stu-id="6f077-125">The Sent or Deleted Items folders in Microsoft Outlook or Outlook on the web (formerly known as Outlook Web App) contain common hacked-account messages, such as "I'm stuck in London, send money."</span></span>

- <span data-ttu-id="6f077-126">異常的個人資料變更，例如名稱、電話號碼或郵遞區號已更新。</span><span class="sxs-lookup"><span data-stu-id="6f077-126">Unusual profile changes, such as the name, the telephone number, or the postal code were updated.</span></span>

- <span data-ttu-id="6f077-127">異常的認證變更，例如要求變更密碼多次。</span><span class="sxs-lookup"><span data-stu-id="6f077-127">Unusual credential changes, such as multiple password changes are required.</span></span>

- <span data-ttu-id="6f077-128">最近新增郵件轉寄。</span><span class="sxs-lookup"><span data-stu-id="6f077-128">Mail forwarding was recently added.</span></span>

- <span data-ttu-id="6f077-129">最近新增異常的簽章，例如假銀行簽章或處方藥簽章。</span><span class="sxs-lookup"><span data-stu-id="6f077-129">An unusual signature was recently added, such as a fake banking signature or a prescription drug signature.</span></span>

<span data-ttu-id="6f077-130">如果使用者報告上述的任何症狀，則應該執行進一步調查。</span><span class="sxs-lookup"><span data-stu-id="6f077-130">If a user reports any of the above symptoms, you should perform further investigation.</span></span> <span data-ttu-id="6f077-131">Microsoft 365 安全性與合規性中心和 Azure 入口網站會提供工具，以協助您調查您懷疑可能遭入侵之使用者帳戶的活動。</span><span class="sxs-lookup"><span data-stu-id="6f077-131">The Microsoft 365 Security & Compliance Center and the Azure Portal offer tools to help you investigate the activity of a user account that you suspect may be compromised.</span></span>

- <span data-ttu-id="6f077-132">**安全性與合規性中心的 整合稽核記錄**：檢閱可疑帳戶的所有活動，方法是篩選日期範圍自發生可疑活動之前到目前日期的結果。</span><span class="sxs-lookup"><span data-stu-id="6f077-132">**Unified Audit Logs in the Security & Compliance Center**: Review all the activities for the suspected account by filtering the results for the date range spanning from immediately before the suspicious activity occurred to the current date.</span></span> <span data-ttu-id="6f077-133">請勿在搜尋期間篩選活動。</span><span class="sxs-lookup"><span data-stu-id="6f077-133">Do not filter on the activities during the search.</span></span>

- <span data-ttu-id="6f077-134">**EAC 中的系統管理員稽核記錄**：在 Exchange Online 中，您可以使用 Exchange 系統管理中心 (EAC) 來搜尋及檢閱系統管理員稽核記錄中的項目。</span><span class="sxs-lookup"><span data-stu-id="6f077-134">**Admin Audit logs in the EAC**: In Exchange Online, you can use the Exchange admin center (EAC) to search for and view entries in the administrator audit log.</span></span> <span data-ttu-id="6f077-135">系統管理員稽核記錄會根據 Exchange Online PowerShell Cmdlet 記錄由系統管理員以及已被指派系統管理權限的使用者所執行的特定動作。</span><span class="sxs-lookup"><span data-stu-id="6f077-135">The administrator audit log records specific actions, based on Exchange Online PowerShell cmdlets, performed by administrators and users who have been assigned administrative privileges.</span></span> <span data-ttu-id="6f077-136">系統管理員稽核記錄中的項目會提供執行的 Cmdlet、使用的參數、Cmdlet 的執行者，以及受影響的物件的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="6f077-136">Entries in the administrator audit log provide you with information about what cmdlet was run, which parameters were used, who ran the cmdlet, and what objects were affected.</span></span>

- <span data-ttu-id="6f077-137">**Azure AD 入口網站中的 Azure AD 登入記錄檔和其他風險報告**：檢查這些欄中的值：</span><span class="sxs-lookup"><span data-stu-id="6f077-137">**Azure AD Sign-in logs and other risk reports in the Azure AD portal**: Examine the values in these columns:</span></span>

  - <span data-ttu-id="6f077-138">檢閱 IP 位址</span><span class="sxs-lookup"><span data-stu-id="6f077-138">Review IP address</span></span>
  - <span data-ttu-id="6f077-139">登入位置</span><span class="sxs-lookup"><span data-stu-id="6f077-139">sign-in locations</span></span>
  - <span data-ttu-id="6f077-140">登入時間</span><span class="sxs-lookup"><span data-stu-id="6f077-140">sign-in times</span></span>
  - <span data-ttu-id="6f077-141">登入成功或失敗</span><span class="sxs-lookup"><span data-stu-id="6f077-141">sign-in success or failure</span></span>

## <a name="how-to-secure-and-restore-email-function-to-a-suspected-compromised-microsoft-365-account-and-mailbox"></a><span data-ttu-id="6f077-142">如何保護並將電子郵件功能還原到可疑的遭入侵 Microsoft 365 帳戶和信箱</span><span class="sxs-lookup"><span data-stu-id="6f077-142">How to secure and restore email function to a suspected compromised Microsoft 365 account and mailbox</span></span>

> [!VIDEO https://videoplayercdn.osi.office.net/hub/?csid=ux-cms-en-us-msoffice&uuid=RE2jvOb&AutoPlayVideo=false]

<span data-ttu-id="6f077-143">即使是在您重新取得帳戶的存取權之後，攻擊者可能已新增後門程式項目，使得攻擊者得以繼續控制該帳戶。</span><span class="sxs-lookup"><span data-stu-id="6f077-143">Even after you've regained access to your account, the attacker may have added back-door entries that enable the attacker to resume control of the account.</span></span>

<span data-ttu-id="6f077-144">您必須執行下列所有步驟來重新取得帳戶的存取權，愈快愈好，以確保劫持者不會繼續控制您的帳戶。</span><span class="sxs-lookup"><span data-stu-id="6f077-144">You must do all the following steps to regain access to your account the sooner the better to make sure that the hijacker doesn't resume control your account.</span></span> <span data-ttu-id="6f077-145">這些步驟可協助您移除劫持者可能已新增至您的帳戶的任何後門程式項目。</span><span class="sxs-lookup"><span data-stu-id="6f077-145">These steps help you remove any back-door entries that the hijacker may have added to your account.</span></span> <span data-ttu-id="6f077-146">在您執行這些步驟之後，建議您執行病毒掃描，以確認您的電腦未遭入侵。</span><span class="sxs-lookup"><span data-stu-id="6f077-146">After you do these steps, we recommend that you run a virus scan to make sure that your computer isn't compromised.</span></span>

### <a name="step-1-reset-the-users-password"></a><span data-ttu-id="6f077-147">步驟 1 重設使用者的密碼</span><span class="sxs-lookup"><span data-stu-id="6f077-147">Step 1 Reset the user's password</span></span>

<span data-ttu-id="6f077-148">遵循[重設某人的商務密碼](../../admin/add-users/reset-passwords.md#reset-my-admin-password)中的程序進行。</span><span class="sxs-lookup"><span data-stu-id="6f077-148">Follow the procedures in [Reset a business password for someone](../../admin/add-users/reset-passwords.md#reset-my-admin-password).</span></span>

> [!IMPORTANT]
>
> - <span data-ttu-id="6f077-149">請勿透過電子郵件傳送新密碼給預期的使用者，因為攻擊者此時仍可能對信箱具有存取權。</span><span class="sxs-lookup"><span data-stu-id="6f077-149">Do not send the new password to the intended user through email as the attacker still has access to the mailbox at this point.</span></span>
>
> - <span data-ttu-id="6f077-150">請確定密碼為強式密碼，且包含大寫和小寫字母、至少一個數字，以及至少一個特殊字元。</span><span class="sxs-lookup"><span data-stu-id="6f077-150">Make sure that the password is strong and that it contains upper and lowercase letters, at least one number, and at least one special character.</span></span>
>
> - <span data-ttu-id="6f077-151">請勿重複使用最後五個密碼。</span><span class="sxs-lookup"><span data-stu-id="6f077-151">Don't reuse any of your last five passwords.</span></span> <span data-ttu-id="6f077-152">即使密碼歷程記錄需求可讓您重複使用較新的密碼，您也應該選取攻擊者無法猜測的項目。</span><span class="sxs-lookup"><span data-stu-id="6f077-152">Even though the password history requirement lets you reuse a more recent password, you should select something that the attacker can't guess.</span></span>
>
> - <span data-ttu-id="6f077-153">如果您的內部部署身分識別與 Microsoft 365 同盟，則必須變更您的內部部署密碼，然後必須通知您的系統管理員相關入侵。</span><span class="sxs-lookup"><span data-stu-id="6f077-153">If your on-premises identity is federated with Microsoft 365, you must change your password on-premises, and then you must notify your administrator of the compromise.</span></span>
>
> - <span data-ttu-id="6f077-154">務必更新應用程式密碼。</span><span class="sxs-lookup"><span data-stu-id="6f077-154">Be sure to update app passwords.</span></span> <span data-ttu-id="6f077-155">使用者帳戶密碼重設時，應用程式密碼未自動撤銷。</span><span class="sxs-lookup"><span data-stu-id="6f077-155">App passwords aren't automatically revoked when a user account password reset.</span></span> <span data-ttu-id="6f077-156">使用者應該刪除現有的應用程式密碼，並建立新密碼。</span><span class="sxs-lookup"><span data-stu-id="6f077-156">The user should delete existing app passwords and create new ones.</span></span> <span data-ttu-id="6f077-157">如需指示，請參閱[從其他安全性驗證頁面建立和刪除應用程式密碼](/azure/active-directory/user-help/multi-factor-authentication-end-user-app-passwords#create-and-delete-app-passwords-from-the-additional-security-verification-page)。</span><span class="sxs-lookup"><span data-stu-id="6f077-157">For instructions, see [Create and delete app passwords from the Additional security verification page](/azure/active-directory/user-help/multi-factor-authentication-end-user-app-passwords#create-and-delete-app-passwords-from-the-additional-security-verification-page).</span></span>
>
> - <span data-ttu-id="6f077-158">我們強烈建議您啟用多重要素驗證 (MFA)，以防止入侵，特別是具有系統管理權限的帳戶。</span><span class="sxs-lookup"><span data-stu-id="6f077-158">We highly recommended that you enable Multi-Factor Authentication (MFA) in order to prevent compromise, especially for accounts with administrative privileges.</span></span> <span data-ttu-id="6f077-159">若要深入了解 MFA，請至 [設定多重要素驗證](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="6f077-159">To learn more about MFA, go to [Set up multi-factor authentication](../../admin/security-and-compliance/set-up-multi-factor-authentication.md).</span></span>

### <a name="step-2-remove-suspicious-email-forwarding-addresses"></a><span data-ttu-id="6f077-160">步驟 2 移除可疑的電子郵件轉寄地址</span><span class="sxs-lookup"><span data-stu-id="6f077-160">Step 2 Remove suspicious email forwarding addresses</span></span>

1. <span data-ttu-id="6f077-161">開啟位於 <https://admin.microsoft.com> 的 Microsoft 365 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="6f077-161">Open the Microsoft 365 admin center at <https://admin.microsoft.com></span></span>

2. <span data-ttu-id="6f077-162">移至 [使用者 **]** \> [作用中使用者 **]**。</span><span class="sxs-lookup"><span data-stu-id="6f077-162">Go to **Users** \> **Active users**.</span></span> <span data-ttu-id="6f077-163">尋找發生問題的使用者帳戶，並選取使用者 (列) 而不選取核取方塊。</span><span class="sxs-lookup"><span data-stu-id="6f077-163">Find the user account in question, and select the user (row) without selecting the checkbox.</span></span>

3. <span data-ttu-id="6f077-164">在顯示的詳細資料飛出視窗中，選取 [郵件 **]** 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="6f077-164">In the details flyout that appears, select the **Mail** tab.</span></span>

4. <span data-ttu-id="6f077-165">如果 [電子郵件轉寄 **]** 區段中的值為 [己套用 **]**，請按一下 [管理電子郵件轉寄 **]**。</span><span class="sxs-lookup"><span data-stu-id="6f077-165">If the value in the **Email forwarding** section is **Applied**, click **Manage email forwarding**.</span></span> <span data-ttu-id="6f077-166">在顯示的 [管理電子郵件轉寄 **]** 飛出視窗中，清除 [轉寄所有傳送到此信箱的電子郵件 **]**，然後按一下 [儲存變更 **]**。</span><span class="sxs-lookup"><span data-stu-id="6f077-166">In the **Manage email forwarding** flyout that appears, clear **Forward all email sent to this mailbox**, and then click **Save changes**.</span></span>

### <a name="step-3-disable-any-suspicious-inbox-rules"></a><span data-ttu-id="6f077-167">步驟 3 停用任何可疑的收件匣規則</span><span class="sxs-lookup"><span data-stu-id="6f077-167">Step 3 Disable any suspicious inbox rules</span></span>

1. <span data-ttu-id="6f077-168">使用 Outlook 網頁版登入使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="6f077-168">Sign in to the user's mailbox using Outlook on the web.</span></span>

2. <span data-ttu-id="6f077-169">按一下齒輪圖示並按一下 [郵件]。</span><span class="sxs-lookup"><span data-stu-id="6f077-169">Click on the gear icon and click **Mail**.</span></span>

3. <span data-ttu-id="6f077-170">按一下 [收件匣和整理規則] 並檢閱規則。</span><span class="sxs-lookup"><span data-stu-id="6f077-170">Click **Inbox and sweep rules** and review the rules.</span></span>

4. <span data-ttu-id="6f077-171">停用或刪除可疑的規則。</span><span class="sxs-lookup"><span data-stu-id="6f077-171">Disable or delete suspicious rules.</span></span>

### <a name="step-4-unblock-the-user-from-sending-mail"></a><span data-ttu-id="6f077-172">步驟 4 解除封鎖使用者，使其可以傳送郵件</span><span class="sxs-lookup"><span data-stu-id="6f077-172">Step 4 Unblock the user from sending mail</span></span>

<span data-ttu-id="6f077-173">如果懷疑遭入侵的信箱被非法用來傳送垃圾郵件，則可能是該信箱已被封鎖無法傳送郵件。</span><span class="sxs-lookup"><span data-stu-id="6f077-173">If the suspected compromised mailbox was used illicitly to send spam email, it is likely that the mailbox has been blocked from sending mail.</span></span>

<span data-ttu-id="6f077-174">若要解除封鎖信箱，使其可以傳送郵件，請遵循[傳送垃圾電子郵件之後，從限制的使用者入口網站移除使用者](removing-user-from-restricted-users-portal-after-spam.md)中的程序。</span><span class="sxs-lookup"><span data-stu-id="6f077-174">To unblock a mailbox from sending mail, follow the procedures in [Removing a user from the Restricted Users portal after sending spam email](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

### <a name="step-5-optional-block-the-user-account-from-signing-in"></a><span data-ttu-id="6f077-175">步驟 5 選用：封鎖使用者帳戶，使其無法登入</span><span class="sxs-lookup"><span data-stu-id="6f077-175">Step 5 Optional: Block the user account from signing-in</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6f077-176">您可以封鎖懷疑遭入侵的帳戶，使該帳戶無法登入，直到您認為可以安全地重新啟用存取權為止。</span><span class="sxs-lookup"><span data-stu-id="6f077-176">You can block the suspected compromised account from signing-in until you believe it is safe to re-enable access.</span></span>

1. <span data-ttu-id="6f077-177">開啟 Microsoft 365 系統管理中心，然後移至 [使用者 **]** \> [作用中使用者 **]**。</span><span class="sxs-lookup"><span data-stu-id="6f077-177">Open the Microsoft 365 admin center and go to **Users** \> **Active users**.</span></span>

2. <span data-ttu-id="6f077-178">尋找並選取使用者帳戶，按一下 [更多圖示![]](../../media/ITPro-EAC-MoreOptionsIcon.png)，然後選取 [編輯登入狀態 **]**。</span><span class="sxs-lookup"><span data-stu-id="6f077-178">Find and select the user account, click ![More icon](../../media/ITPro-EAC-MoreOptionsIcon.png), and then select **Edit sign-in status**.</span></span>

3. <span data-ttu-id="6f077-179">在顯示的 **[封鎖登入]** 窗格中，選取 **[封鎖此使用者，使其無法登入]**，然後按一下 **[儲存變更]**。</span><span class="sxs-lookup"><span data-stu-id="6f077-179">On the **Block sign-in** pane that appears, select **Block this user from signing in**, and then click **Save changes**.</span></span>

4. <span data-ttu-id="6f077-180">開啟位於 <admin.protection.outlook.com/ecp/> 的 Exchange 系統管理中心 (EAC)，然後移至 [收件者] > [信箱 **]**。</span><span class="sxs-lookup"><span data-stu-id="6f077-180">Open the Exchange admin center (EAC) at <admin.protection.outlook.com/ecp/>, and go to **Recipients > Mailboxes**.</span></span>

5. <span data-ttu-id="6f077-181">尋找並選取使用者。</span><span class="sxs-lookup"><span data-stu-id="6f077-181">Find and select the select the user.</span></span> <span data-ttu-id="6f077-182">在詳細資料窗格中，執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="6f077-182">In the details pane, do the following steps:</span></span>

   - <span data-ttu-id="6f077-183">在 [電話和語音功能 **]** 區段中，執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="6f077-183">In the **Phone and voice features** section, do the following steps:</span></span>

     - <span data-ttu-id="6f077-184">選取 [停用 Exchange ActiveSync **]**，然後按一下顯示的警告中的 [是 **]**。</span><span class="sxs-lookup"><span data-stu-id="6f077-184">Select **Disable Exchange ActiveSync** and then click **Yes** in the warning that appears.</span></span>
     - <span data-ttu-id="6f077-185">選取 [停用裝置用 OWA **]**，然後按一下顯示的警告中的 [是 **]**。</span><span class="sxs-lookup"><span data-stu-id="6f077-185">Select **Disable OWA for Devices** and then click **Yes** in the warning that appears.</span></span>

   - <span data-ttu-id="6f077-186">在 Outlook 網頁版的 [電子郵件連線 **]** 區段中，按一下 [停用 **]**，然後按一下顯示的警告中的 [是 **]**。</span><span class="sxs-lookup"><span data-stu-id="6f077-186">In the **Email Connectivity** section for Outlook on the web, click **Disable** and then click **Yes** in the warning that appears.</span></span>

### <a name="step-6-optional-remove-the-suspected-compromised-account-from-all-administrative-role-groups"></a><span data-ttu-id="6f077-187">步驟 6 選用：從所有系統管理角色群組移除懷疑遭入侵的帳戶</span><span class="sxs-lookup"><span data-stu-id="6f077-187">Step 6 Optional: Remove the suspected compromised account from all administrative role groups</span></span>

> [!NOTE]
> <span data-ttu-id="6f077-188">保護的帳戶之後，就可以還原系統管理角色群組的成員資格。</span><span class="sxs-lookup"><span data-stu-id="6f077-188">Administrative role group membership can be restored after the account has been secured.</span></span>

1. <span data-ttu-id="6f077-189">使用全域系統管理員帳戶登入：</span><span class="sxs-lookup"><span data-stu-id="6f077-189">Sign in with a global administrator account:</span></span>

2. <span data-ttu-id="6f077-190">在 Microsoft 365 系統管理中心，執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="6f077-190">In the Microsoft 365 admin center, do the following steps:</span></span>

   1. <span data-ttu-id="6f077-191">移至 [使用者 **]** \> [作用中使用者 **]**。</span><span class="sxs-lookup"><span data-stu-id="6f077-191">Go to **Users** \> **Active users**.</span></span>
   2. <span data-ttu-id="6f077-192">尋找並選取使用者帳戶，按一下 [更多圖示![]](../../media/ITPro-EAC-MoreOptionsIcon.png)，然後選取 [管理角色 **]**。</span><span class="sxs-lookup"><span data-stu-id="6f077-192">Find and select the user account, click ![More icon](../../media/ITPro-EAC-MoreOptionsIcon.png), and then select **Manage roles**.</span></span>
   3. <span data-ttu-id="6f077-193">移除指派給帳戶的任何系統管理角色。</span><span class="sxs-lookup"><span data-stu-id="6f077-193">Remove any administrative roles that are assigned to the account.</span></span> <span data-ttu-id="6f077-194">完成後，按一下 [儲存變更 **]**。</span><span class="sxs-lookup"><span data-stu-id="6f077-194">When you're finished, click **Save changes**.</span></span>

3. <span data-ttu-id="6f077-195">在位於 <https://protection.office.com> 的安全性與合規性中心，執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="6f077-195">In the Security & Compliance Center at <https://protection.office.com>, do the following steps:</span></span>

   <span data-ttu-id="6f077-196">選取 [權限 **]**，選取清單中的每個角色群組，並在顯示的詳細資料飛出視窗的 [成員 **]** 區段中尋找該使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="6f077-196">Select **Permissions**, select each role group in the list and look for the user account in the **Members** section of the details flyout that appears.</span></span> <span data-ttu-id="6f077-197">如果角色群組包含該使用者帳戶，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="6f077-197">If the role group contains the user account, do the following steps:</span></span>

   <span data-ttu-id="6f077-198">a.</span><span class="sxs-lookup"><span data-stu-id="6f077-198">a.</span></span> <span data-ttu-id="6f077-199">按一下 [成員 **]** 旁的 [編輯 **]**。</span><span class="sxs-lookup"><span data-stu-id="6f077-199">Click **Edit** next to **Members**.</span></span>
   <span data-ttu-id="6f077-200">b.</span><span class="sxs-lookup"><span data-stu-id="6f077-200">b.</span></span> <span data-ttu-id="6f077-201">顯示的飛出視窗上的 [編輯選擇成員 **]**，按一下 [編輯 **]**。</span><span class="sxs-lookup"><span data-stu-id="6f077-201">On the **Editing Choose members** flyout that appears, click **Edit**.</span></span>
   <span data-ttu-id="6f077-202">c.</span><span class="sxs-lookup"><span data-stu-id="6f077-202">c.</span></span> <span data-ttu-id="6f077-203">在顯示的 [選擇成員 **]** 飛出視窗中，選取該使用者帳戶，然後按一下 [移除 **]**。</span><span class="sxs-lookup"><span data-stu-id="6f077-203">In the **Choose members** flyout that appears, select the user account, and then click **Remove**.</span></span> <span data-ttu-id="6f077-204">完成時，依序按一下 [完成 **]** 和 [儲存 **]**，然後按一下 [關閉 **]**。</span><span class="sxs-lookup"><span data-stu-id="6f077-204">When you're finished, click **Done**, **Save**, and then **Close**.</span></span>

4. <span data-ttu-id="6f077-205">在位於 <admin.protection.outlook.com/ecp/> 的 EAC 中，執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="6f077-205">In the EAC at <admin.protection.outlook.com/ecp/>, do the following steps:</span></span>

   <span data-ttu-id="6f077-206">選取 [權限 **]**，手動選取每個角色群組，然後在詳細資料窗格中，在 [成員 **]** 區段中驗證使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="6f077-206">Select **Permissions**, manually select each role group, and in the details pane, verify the user accounts in the **Members** section.</span></span>  <span data-ttu-id="6f077-207">如果角色群組包含該使用者帳戶，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="6f077-207">If the role group contains the user account, do the following steps:</span></span>

   <span data-ttu-id="6f077-208">a.</span><span class="sxs-lookup"><span data-stu-id="6f077-208">a.</span></span> <span data-ttu-id="6f077-209">選取角色群組，按一下 [編輯 **]** ![編輯圖示](../../media/ITPro-EAC-EditIcon.png)。</span><span class="sxs-lookup"><span data-stu-id="6f077-209">Select the role group, click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>
   <span data-ttu-id="6f077-210">b.</span><span class="sxs-lookup"><span data-stu-id="6f077-210">b.</span></span> <span data-ttu-id="6f077-211">在 [成員 **]** 區段中，選取該使用者帳戶，然後按一下 [移除 **]** ![移除圖示](../../media/ITPro-EAC-RemoveIcon.gif)。</span><span class="sxs-lookup"><span data-stu-id="6f077-211">In the **Member** section, select the user account, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span> <span data-ttu-id="6f077-212">完成後，按一下 [儲存 **]**。</span><span class="sxs-lookup"><span data-stu-id="6f077-212">When you're finished, click **Save**.</span></span>

### <a name="step-7-optional-additional-precautionary-steps"></a><span data-ttu-id="6f077-213">步驟 7 選用：額外的預防步驟</span><span class="sxs-lookup"><span data-stu-id="6f077-213">Step 7 Optional: Additional precautionary steps</span></span>

1. <span data-ttu-id="6f077-214">務必確認您所傳送的項目。</span><span class="sxs-lookup"><span data-stu-id="6f077-214">Make sure that you verify your sent items.</span></span> <span data-ttu-id="6f077-215">您可能需要通知您的連絡人清單上的人員，您的帳戶已遭入侵。</span><span class="sxs-lookup"><span data-stu-id="6f077-215">You may have to inform people on your contacts list that your account was compromised.</span></span> <span data-ttu-id="6f077-216">攻擊者可能會要求他們給予金錢，比方說騙他們說您滯留在不同國家/地區因而缺錢，或是攻擊者也可能傳送病毒給他們來劫持電腦。</span><span class="sxs-lookup"><span data-stu-id="6f077-216">The attacker may have asked them for money, spoofing, for example, that you were stranded in a different country and needed money, or the attacker may send them a virus to also hijack their computers.</span></span>

2. <span data-ttu-id="6f077-217">使用此 Exchange 帳戶作為其備用電子郵件帳戶的任何其他服務可能已遭入侵。</span><span class="sxs-lookup"><span data-stu-id="6f077-217">Any other service that used this Exchange account as its alternative email account may have been compromised.</span></span> <span data-ttu-id="6f077-218">先為您的 Microsoft 365 訂閱執行下列步驟，然後再為您的其他帳戶執行這些步驟。</span><span class="sxs-lookup"><span data-stu-id="6f077-218">First, do these steps for your Microsoft 365 subscription, and then do these steps for your other accounts.</span></span>

3. <span data-ttu-id="6f077-219">確認您的連絡資訊，例如電話號碼及地址，是正確的。</span><span class="sxs-lookup"><span data-stu-id="6f077-219">Make sure that your contact information, such as telephone numbers and addresses, is correct.</span></span>

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a><span data-ttu-id="6f077-220">像網路安全專業人員一般保護 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6f077-220">Secure Microsoft 365 like a cybersecurity pro</span></span>

<span data-ttu-id="6f077-221">您的 Microsoft 365 訂閱隨附一組功能強大的安全性功能，可供您用來保護您的資料和您的使用者。</span><span class="sxs-lookup"><span data-stu-id="6f077-221">Your Microsoft 365 subscription comes with a powerful set of security capabilities that you can use to protect your data and your users.</span></span>  <span data-ttu-id="6f077-222">使用 [Microsoft 365 安全性藍圖 - 前 30 天、前 90 天前和之後的最高優先順序](security-roadmap.md)來實作 Microsoft 建議用來保護您的 Microsoft 365 租用戶的最佳做法。</span><span class="sxs-lookup"><span data-stu-id="6f077-222">Use the [Microsoft 365 security roadmap - Top priorities for the first 30 days, 90 days, and beyond](security-roadmap.md) to implement Microsoft recommended best practices for securing your Microsoft 365 tenant.</span></span>

- <span data-ttu-id="6f077-223">要在前 30 天內完成的工作。</span><span class="sxs-lookup"><span data-stu-id="6f077-223">Tasks to accomplish in the first 30 days.</span></span>  <span data-ttu-id="6f077-224">這些工作會有立即的影響，而且對您的使用者影響較低。</span><span class="sxs-lookup"><span data-stu-id="6f077-224">These have immediate affect and are low-impact to your users.</span></span>

- <span data-ttu-id="6f077-225">要在 90 天內完成的工作。</span><span class="sxs-lookup"><span data-stu-id="6f077-225">Tasks to accomplish in 90 days.</span></span> <span data-ttu-id="6f077-226">這些工作需要多一些時間來計劃及實作，但是可以大幅改善您的安全性狀態。</span><span class="sxs-lookup"><span data-stu-id="6f077-226">These take a bit more time to plan and implement but greatly improve your security posture.</span></span>

- <span data-ttu-id="6f077-227">90 天之後。</span><span class="sxs-lookup"><span data-stu-id="6f077-227">Beyond 90 days.</span></span> <span data-ttu-id="6f077-228">這些增強功能會在您的前 90 天工作內建置。</span><span class="sxs-lookup"><span data-stu-id="6f077-228">These enhancements build in your first 90 days work.</span></span>

## <a name="see-also"></a><span data-ttu-id="6f077-229">請參閱</span><span class="sxs-lookup"><span data-stu-id="6f077-229">See also</span></span>

- [<span data-ttu-id="6f077-230">偵測並修復 Microsoft 365 中 Outlook 規則與自訂表單插入式攻擊</span><span class="sxs-lookup"><span data-stu-id="6f077-230">Detect and Remediate Outlook Rules and Custom Forms Injections Attacks in Microsoft 365</span></span>](detect-and-remediate-outlook-rules-forms-attack.md)

- [<span data-ttu-id="6f077-231">網際網路犯罪客訴中心</span><span class="sxs-lookup"><span data-stu-id="6f077-231">Internet Crime Complaint Center</span></span>](https://www.ic3.gov/Home/Ransomware)

- [<span data-ttu-id="6f077-232">美國證券交易委員會 -「網路釣魚」詐騙</span><span class="sxs-lookup"><span data-stu-id="6f077-232">Securities and Exchange Commission - "Phishing" Fraud</span></span>](https://www.sec.gov/investor/pubs/phishing.htm)

- <span data-ttu-id="6f077-233">若要直接向 Microsoft 和您的系統管理員檢舉垃圾郵件，[請使用檢舉訊息增益集](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)</span><span class="sxs-lookup"><span data-stu-id="6f077-233">To report spam email directly to Microsoft and your admin [Use the Report Message add-in](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)</span></span>